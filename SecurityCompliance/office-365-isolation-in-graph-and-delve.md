---
title: 在 Office 中的 office 365 租用戶隔離圖形及探索
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 摘要： 租用戶隔離 Delve 及 Office 圖形中說明。
ms.openlocfilehash: cb1b432dccff6c4f890ef4aeb8ea4c19989b09d5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216803"
---
# <a name="tenant-isolation-in-the-office-graph-and-delve"></a><span data-ttu-id="b69e3-103">Office Graph 與 Delve 中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="b69e3-103">Tenant Isolation in the Office Graph and Delve</span></span>

## <a name="tenant-isolation-in-the-office-graph"></a><span data-ttu-id="b69e3-104">在 Office 圖中顯示的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="b69e3-104">Tenant Isolation in the Office Graph</span></span>
<span data-ttu-id="b69e3-p101">[Office 圖表](https://dev.office.com/officegraph)模型活動在 Office 365 服務、 商務、 Azure Active Directory、 及詳細資訊，包括 Exchange Online、 SharePoint Online、 Yammer、 Skype 及其他 Microsoft 服務或協力廠商服務外部服務。Office 圖表元件可用整個 Office 365 中。Office 圖表代表一群內容及活動，與發生跨整個 Office 套件的兩者之間的關係。它會使用複雜的機器學習技術 （英文） 連線至相關的內容、 對話及周圍這些人員的人員。例如承租人索引 SharePoint Online 中的有 Office 圖表索引用來提供 Delve 查詢服務、 SharePoint Online 中的 「 分析處理引擎用來儲存信號和計算前瞻、 與 Exchange Online 會計算每位使用者做為輸入到租用戶分析的收件者快取。</span><span class="sxs-lookup"><span data-stu-id="b69e3-p101">The [Office Graph](https://dev.office.com/officegraph) models activity in Office 365 services, including Exchange Online, SharePoint Online, Yammer, Skype for Business, Azure Active Directory, and more, and in external services, such as other Microsoft services or third-party services. Office Graph components are used throughout Office 365. The Office Graph represents a collection of content and activity, and the relationships between them that happen across the entire Office suite. It uses sophisticated machine learning techniques to connect people to the relevant content, conversations and people around them. For example, the tenant index in SharePoint Online has an Office Graph index that is used to serve Delve queries, the Analytics Processing Engine in SharePoint Online is used to store signals and calculate insights, and Exchange Online calculates each user's recipient cache as input into tenant analytics.</span></span>

<span data-ttu-id="b69e3-p102">Office 圖表包含企業物件，例如人員及文件，以及關係與這些物件之間的互動的相關資訊。*邊緣*以表示關聯及互動。Office 圖表被區分依承租人如此邊緣能夠只存在於相同租用中的*節點*之間。*節點*為具有統一資源識別元 (URI)、 節點類型、 存取控制清單，以及一組 facet 包含*中繼資料*與邊緣的實體。每個節點相關聯的中繼資料與邊緣、 排入*facet*如常見的知識模型所示。*中繼資料*被具名內容儲存在其可用為搜尋、 篩選或分析 office 圖表內的節點上。*Facet*是邏輯的一組的中繼資料與在節點上的邊緣。每個 facet 說明一個節點的外觀。</span><span class="sxs-lookup"><span data-stu-id="b69e3-p102">The Office Graph contains information about enterprise objects, such as people and documents, as well as the relationships and interactions among these objects. The relationships and interactions are represented as *edges*. The Office Graph is segmented by tenant such that edges can only exist between *nodes* in the same tenancy. A *node* is an entity with a Uniform Resource Identifier (URI), node type, access control list, and a set of facets containing *metadata* and edges. Each node has associated metadata and edges, arranged into *facets* as in the Common Knowledge Model. *Metadata* are named properties stored on a node which can be used for searching, filtering, or analysis within the office graph. A *facet* is a logical collection of metadata and edges on a node. Each facet describes one aspect of a node.</span></span> 

<span data-ttu-id="b69e3-p103">Office 圖表不會將所有資料移入單一存放庫 ；而是儲存中繼資料與其他地方儲存的資料相關的關係。Office 圖表是由數個資料儲存區和處理元件所組成：</span><span class="sxs-lookup"><span data-stu-id="b69e3-p103">The Office Graph does not bring all the data into a single repository; rather, it stores metadata and relationships about data that lives elsewhere. The Office Graph consists of several data stores and processing components:</span></span>
- <span data-ttu-id="b69e3-120">租用戶圖存放區提供有效率的分析最適合的大量儲存區。</span><span class="sxs-lookup"><span data-stu-id="b69e3-120">The Tenant Graph Store provides bulk storage optimized for efficient analytics.</span></span>
- <span data-ttu-id="b69e3-121">作用中的內容快取提供至作用中節點的快速隨機存取和磁碟機使用者體驗的邊緣。</span><span class="sxs-lookup"><span data-stu-id="b69e3-121">The Active Content Cache provides quick random access to active node and edges to drive user experiences.</span></span>
- <span data-ttu-id="b69e3-122">輸入的路由器通知元件內部和外部的用戶圖的變更。</span><span class="sxs-lookup"><span data-stu-id="b69e3-122">The input router notifies components internal and external of changes to the tenant graph.</span></span>

<span data-ttu-id="b69e3-p104">分析內每個工作負載推斷前瞻相關租用戶全計算並加以推送到用戶圖。租用戶分析的原因 over 租用中的所有活動產生算行為的模式。例如，Exchange Online 計算有效率地原因每位使用者的信箱上的分析與每個使用者的收件者快取。這些個別使用者分析會產生一組*RecipientCache 邊緣*的每個人，在其中接下來推送至租用戶圖。這會保持不變部分接近位置儘可能的來源資料的分析處理。</span><span class="sxs-lookup"><span data-stu-id="b69e3-p104">Analytics within each workload deduce insights relevant to the tenant-wide calculations and push them to the tenant graph. Tenant analytics reasons over all activity in a tenancy to produce insights into patterns of behavior. For example, Exchange Online calculates the recipient cache for each user with analytics that efficiently reason over each user's mailbox. These per-user analytics produce a set of *RecipientCache Edges* on each person, which are in turn pushed to the tenant graph. This keeps the as much of the analytics processing as close to the source data as possible.</span></span>

## <a name="tenant-isolation-in-delve"></a><span data-ttu-id="b69e3-128">在租用戶隔離探索</span><span class="sxs-lookup"><span data-stu-id="b69e3-128">Tenant Isolation in Delve</span></span>
<span data-ttu-id="b69e3-p105">如前文所述，Office 圖力量他人探索和共同作業在其 enterprise 中，目前活動的體驗，並提供實體為主的平台原因的分析內容及活動上不同工作負載與超過 Office 365。探索是第一個由 Office 圖提供這類經驗。探索是透過 Office 圖表至 Office 365 使用者會內容從 Office 365 和 Yammer Enterprise 呈現 Office 365 web 功能。網站體驗將資料顯示為每個特定主題，例如*周圍我的 [趨勢*] 或 [*修改由我*的不同區。每個版包含數個文件卡片顯示摘要文字與文件中的圖片。卡片可讓使用者執行像是開啟文件或文件的 Yammer] 頁面上作業。沒有顯示最相關的文件的這個人 Office 365 租用戶和可以呼叫 Exchange Online 或企業版 Skype 互動與該連絡人的圖示中的每個人的頁面。Delve 根據 Office 圖表 API，因為它是租用戶為基礎的隔離該 API 所繫結。</span><span class="sxs-lookup"><span data-stu-id="b69e3-p105">As mentioned previously, the Office Graph powers experiences that help people discover and collaborate on current activities in their enterprise, and provides an entity-centric platform for analytics to reason over content and activity across workloads and beyond Office 365. Delve is the first such experience powered by the Office Graph. Delve is an Office 365 web experience that surfaces content from Office 365 and Yammer Enterprise to Office 365 users via the Office Graph. The web experience displays data as different boards, each with a certain topic, such as *Trending around me* or *Modified by me*. Each board consists of several document cards that display summary text and a picture from the document. The card lets users do things like open the document or a Yammer page for the document. There is a page for each person in an Office 365 tenant that displays the most relevant documents for this person, and icons that can invoke Exchange Online or Skype for Business for interacting with that person. Because Delve is based on the Office Graph API, it is bound by the tenant-based isolation of that API.</span></span>