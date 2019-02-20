---
title: Office 365 租用戶隔離中的 Office 365 搜尋
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 摘要： 在 Office 365 搜尋的租用戶隔離說明。
ms.openlocfilehash: b9faae9f1d61af181807f60243890b5115c0d679
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090805"
---
# <a name="tenant-isolation-in-office-365-search"></a><span data-ttu-id="98e50-103">Office 365 搜尋中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="98e50-103">Tenant Isolation in Office 365 Search</span></span>
<span data-ttu-id="98e50-p101">SharePoint Online 搜尋使用平衡與理想的資訊洩漏租用戶之間的共用的資料結構的效率的租用戶分離模型。使用此模型中，我們會防止從搜尋功能：</span><span class="sxs-lookup"><span data-stu-id="98e50-p101">SharePoint Online search uses a tenant separation model that balances the efficiency of shared data structures with protection against information leaking between tenants. With this model, we prevent the Search features from:</span></span>
- <span data-ttu-id="98e50-106">傳回查詢結果包含來自其他租用戶的文件</span><span class="sxs-lookup"><span data-stu-id="98e50-106">Returning query results that contain documents from other tenants</span></span>
- <span data-ttu-id="98e50-107">公開查詢結果中足夠資訊可讓積極且熟練的使用者無法推斷其他租用戶的相關資訊</span><span class="sxs-lookup"><span data-stu-id="98e50-107">Exposing sufficient information in query results that a skilled user could infer information about other tenants</span></span>
- <span data-ttu-id="98e50-108">顯示結構描述] 或 [從另一個承租人的設定</span><span class="sxs-lookup"><span data-stu-id="98e50-108">Showing schema or settings from another tenant</span></span>
- <span data-ttu-id="98e50-109">混用分析處理承租人或錯誤的租用戶中的儲存區結果之間的資訊</span><span class="sxs-lookup"><span data-stu-id="98e50-109">Mixing analytics processing information between tenants or store results in the wrong tenant</span></span>
- <span data-ttu-id="98e50-110">使用來自另一個承租人的字典項目</span><span class="sxs-lookup"><span data-stu-id="98e50-110">Using dictionary entries from another tenant</span></span>

<span data-ttu-id="98e50-p102">針對每種承租人資料類型，我們使用一或多個圖層的保護在程式碼來避免意外遺漏的資訊。最重要的資料有大部分的以確保單一缺失不會導致實際或視為資訊外洩保護層級。</span><span class="sxs-lookup"><span data-stu-id="98e50-p102">For each type of tenant data, we use one or more layers of protection in the code to prevent accidental leaking of information. The most critical data has the most layers of protection to make sure that a single defect doesn't result in actual or perceived information leakage.</span></span>

## <a name="tenant-separation-for-the-search-index"></a><span data-ttu-id="98e50-113">搜尋索引的租用戶分離</span><span class="sxs-lookup"><span data-stu-id="98e50-113">Tenant Separation for the Search Index</span></span>
<span data-ttu-id="98e50-p103">在裝載索引元件的伺服器的磁碟上儲存的搜尋索引及承租人共用索引檔案。租用戶編製索引文件都可以看到僅針對該租用戶的查詢。三個獨立的機制防止資訊洩漏：</span><span class="sxs-lookup"><span data-stu-id="98e50-p103">The search index is stored on disk in the servers hosting the index components and the tenants share the index files. A tenant's indexed documents are visible only for queries for that tenant. Three independent mechanisms prevent information leakage:</span></span>
- <span data-ttu-id="98e50-117">租用戶識別碼篩選</span><span class="sxs-lookup"><span data-stu-id="98e50-117">Tenant ID filtering</span></span>
- <span data-ttu-id="98e50-118">租用戶識別碼字詞前面加上</span><span class="sxs-lookup"><span data-stu-id="98e50-118">Tenant ID term prefixing</span></span>
- <span data-ttu-id="98e50-119">ACL 檢查</span><span class="sxs-lookup"><span data-stu-id="98e50-119">ACL checks</span></span>

<span data-ttu-id="98e50-120">所有三個機制必須搜尋以返回了錯誤的租用戶中的文件的失敗。</span><span class="sxs-lookup"><span data-stu-id="98e50-120">All three mechanisms would have to fail for Search to return documents to the wrong tenant.</span></span>

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a><span data-ttu-id="98e50-121">租用戶識別碼篩選與租用戶識別碼字詞前面加上</span><span class="sxs-lookup"><span data-stu-id="98e50-121">Tenant ID Filtering and Tenant ID Term Prefixing</span></span>
<span data-ttu-id="98e50-p104">搜尋的前置詞索引與租用戶識別碼全文檢索索引中每個字詞例如，當詞"*foo*"租用戶識別碼為"*123*"編製索引，全文檢索索引中的項目是"*123foo。*"</span><span class="sxs-lookup"><span data-stu-id="98e50-p104">Search prefixes every term that is indexed in the full-text index with the tenant ID. For example, when the term "*foo*" is indexed for a tenant with an ID of "*123*", the entry in the full-text index is "*123foo.*"</span></span>

<span data-ttu-id="98e50-p105">每個查詢會轉換成包含租用戶識別碼呼叫租用戶識別碼篩選程序。例如，"*foo*"的查詢會轉換成"<*guid*>。*foo*和*tenantID*: <*guid*>"，其中 <*guid*> 代表承租人執行查詢。此查詢轉換此時間內每個索引節點及查詢皆內容處理影響它。租用戶識別碼為新增至每個查詢，因為無法推斷其他租用戶中某個字詞的頻率來尋找在最佳排名一個租用戶中比對。</span><span class="sxs-lookup"><span data-stu-id="98e50-p105">Every query is converted to include the tenant ID using a process called tenant ID filtering. For example, the query "*foo*" is converted to "<*guid*>.*foo* AND *tenantID*:<*guid*>", where <*guid*> represents the tenant performing the query. This query conversion occurs within each index node and neither query nor content processing can influence it. Because the tenant ID is added to every query, the frequency of a term in other tenants can't be inferred by looking at best match ranking in one tenant.</span></span>

<span data-ttu-id="98e50-p106">租用戶識別碼字詞前面加上發生只能在全文檢索索引。擁有搜尋，例如"*標題： foo*"移至 [綜合搜尋索引不租用戶識別碼所前面上字詞而是擁有搜尋被以欄位名稱。例如，"*標題： foo*"的查詢轉換成"*fields.title:foo AND fields.tenantID*: <*guid*>。 」由於字詞的頻率不會影響排名的拜訪人次綜合搜尋索引中，有不需要由字詞前面加上的租用戶分離。Like"*標題： foo*"fielded 搜尋承租人內容分隔取決於查詢轉換所篩選的租用戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="98e50-p106">Tenant ID term prefixing occurs only in the full-text index. Fielded searches, such as "*title:foo*", go to a synthetic search index where terms aren't prefixed by tenant ID. Instead, fielded searches are prefixed with the field name. For example, the query "*title:foo*" is converted to "*fields.title:foo AND fields.tenantID*:<*guid*>." Because the frequency of a term doesn't influence ranking of hits in the synthetic search index, there's no need for tenant separation by term prefixing. For a fielded search like "*title:foo*", tenant content separation depends on tenant ID filtering by query conversion.</span></span>

## <a name="document-access-control-list-checks"></a><span data-ttu-id="98e50-134">文件存取控制清單檢查</span><span class="sxs-lookup"><span data-stu-id="98e50-134">Document Access Control List Checks</span></span>
<span data-ttu-id="98e50-p107">搜尋控制項存取透過儲存在搜尋索引中的 Acl 的文件。每個項目會包含一組字詞的特殊的 ACL] 欄位中編製索引。ACL] 欄位包含群組或使用者可以檢視文件的每一個字詞。每個查詢進一步強化存取控制項目 (ACE) 條款，另一個適用於已驗證的使用者所屬的每個群組的清單。</span><span class="sxs-lookup"><span data-stu-id="98e50-p107">Search controls access to documents through ACLs that are saved in the search index. Every item is indexed with a set of terms in a special ACL field. The ACL field contains one term per group or user that can view the document. Every query is augmented with a list of access control entry (ACE) terms, one for each group to which the authenticated user belongs.</span></span>

<span data-ttu-id="98e50-139">例如，查詢 like"<*guid*>。*foo AND tenantID*: <*guid*>"會變成："<*guid*>。*foo AND tenantID*: <*guid*> *AND* (*docACL：*<*ace1*> *OR docACL*: <*ace2*> *OR docACL*: <*ace3*> *...*)"</span><span class="sxs-lookup"><span data-stu-id="98e50-139">For example, a query like "<*guid*>.*foo AND tenantID*:<*guid*>" becomes: "<*guid*>.*foo AND tenantID*:<*guid*> *AND* (*docACL:*<*ace1*> *OR docACL*:<*ace2*> *OR docACL*:<*ace3*> *...*)"</span></span>

<span data-ttu-id="98e50-p108">因為使用者和群組識別碼及稱做 Ace 是唯一的這提供額外的僅限某些使用者看到的文件的租用戶之間的安全性層級。是相同的特殊 「 所有人以外的外部使用者 」 案例授與存取權的租用戶中的一般使用者的 ACE。但因為 Ace 針對 「 所有人 」 之所有租用戶相同，公用文件的租用戶分離取決於租用戶識別碼篩選。拒絕 Ace 也支援。查詢增強將會移除文件結果拒絕 ACE 相符時的子句。</span><span class="sxs-lookup"><span data-stu-id="98e50-p108">Because user and group identifiers and hence ACEs are unique, this provides an extra level of security between tenants for documents that are only visible to some users. The same is the case for the special "Everyone except external users" ACE that grants access to regular users in the tenant. But since ACEs for "Everyone" are the same for all tenants, tenant separation for public documents depends on tenant ID filtering. Deny ACEs are also supported. The query augmentation adds a clause that removes a document from the result when there is a match with a deny ACE.</span></span>

<span data-ttu-id="98e50-p109">在 Exchange Online 搜尋索引會分割上的個別使用者的信箱，而不是如同 SharePoint Online 的租用戶識別碼 （訂閱識別碼） 的信箱識別碼。分隔機制相當於 SharePoint Online、 但沒有任何 ACL 篩選。</span><span class="sxs-lookup"><span data-stu-id="98e50-p109">In Exchange Online search, the index is partitioned on mailbox ID for individual user's mailboxes instead of tenant ID (subscription ID) as in SharePoint Online. The partitioning mechanism is the same as SharePoint Online, but there is no ACL filtering.</span></span>
