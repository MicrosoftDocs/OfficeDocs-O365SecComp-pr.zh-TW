---
title: Office 365 中的系統管理存取控制
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '摘要: Office 365 的系統管理存取控制和資料分類的簡介。'
ms.openlocfilehash: 38519fe4e9c05e3468ac3f9f6367c096fb64d195
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520693"
---
# <a name="administrative-access-controls-in-office-365"></a><span data-ttu-id="833bf-103">Office 365 中的系統管理存取控制</span><span class="sxs-lookup"><span data-stu-id="833bf-103">Administrative Access Controls in Office 365</span></span> 

<span data-ttu-id="833bf-104">Microsoft 已投入大量的系統和控制項, 可自動化大部分的 Office 365 作業, 並故意限制 Microsoft 對客戶內容的存取。</span><span class="sxs-lookup"><span data-stu-id="833bf-104">Microsoft has invested heavily in systems and controls that automate most Office 365 operations while intentionally limiting access to customer content by Microsoft.</span></span> <span data-ttu-id="833bf-105">人管理服務, 而軟體則會操作服務。</span><span class="sxs-lookup"><span data-stu-id="833bf-105">Humans govern the service, and software operates the service.</span></span> <span data-ttu-id="833bf-106">這可讓 Microsoft 以規模來管理 Office 365, 並管理對客戶內容內部威脅的風險。</span><span class="sxs-lookup"><span data-stu-id="833bf-106">This enables Microsoft to manage Office 365 at scale and manage the risks of internal threats to customer content.</span></span>

<span data-ttu-id="833bf-107">根據預設, Microsoft 工程師的系統管理許可權為零, 而在 Office 365 中則不會有客戶內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="833bf-107">By default, Microsoft engineers have zero standing administrative privileges and zero standing access to customer content in Office 365.</span></span> <span data-ttu-id="833bf-108">Microsoft 工程師可在有限的時間內擁有對客戶內容的有限、已審核和安全的存取權。</span><span class="sxs-lookup"><span data-stu-id="833bf-108">A Microsoft engineer can have limited, audited, and secured access to a customer's content for a limited amount of time.</span></span> <span data-ttu-id="833bf-109">只有在服務作業需要時才可存取, 而且只有在 Microsoft 資深管理的成員核准時才能存取。</span><span class="sxs-lookup"><span data-stu-id="833bf-109">Access is only when necessary for service operations and only when approved by a member of Microsoft senior management.</span></span> <span data-ttu-id="833bf-110">對於客戶加密箱授權的客戶, 客戶會對其主控于 Office 365 的內容提供核准。</span><span class="sxs-lookup"><span data-stu-id="833bf-110">For Customer Lockbox licensed customers, the customer provides access approval to their content hosted on Office 365.</span></span>

<span data-ttu-id="833bf-111">Microsoft 會使用多種形式的雲端傳遞來提供線上服務:</span><span class="sxs-lookup"><span data-stu-id="833bf-111">Microsoft provides online services using multiple forms of cloud delivery:</span></span>

- <span data-ttu-id="833bf-112">**公用群:** 包含多租使用者版本的 Office 365、Azure 和其他託管于北美、南美洲、歐洲、亞洲、澳大利亞等的服務。</span><span class="sxs-lookup"><span data-stu-id="833bf-112">**Public Clouds:** Includes multi-tenant versions of Office 365, Azure, and other services hosted in North America, South America, Europe, Asia, Australia, etc.</span></span>
- <span data-ttu-id="833bf-113">**國家雲彩:** 包含美國以外的所有以及主權和協力廠商運作的雲彩 (除了先前所述的地方), 例如中國的 Office 365 (由世紀運作), 以及德國的 Office 365 (由 Microsoft 運作, 但在德文資料受託人的模型下)。德國 Telekom, 控制並監控 Microsoft 對客戶資料和包含客戶資料的系統的存取。</span><span class="sxs-lookup"><span data-stu-id="833bf-113">**National Clouds:** Includes all sovereign and third party-operated clouds outside of the United States (except ones noted previously), such as Office 365 in China (operated by 21Vianet), and Office 365 in Germany (operated by Microsoft, but under a model in which a German data trustee, Deutsche Telekom, controls and monitors Microsoft's access to Customer Data and systems that contain Customer Data).</span></span>
- <span data-ttu-id="833bf-114">**政府雲彩:** 包含適用于美國政府客戶的 Office 365 和 Azure 服務。</span><span class="sxs-lookup"><span data-stu-id="833bf-114">**Government Clouds:** Includes Office 365 and Azure services that are available to United States government customers.</span></span>

<span data-ttu-id="833bf-115">基於本文的目的, Office 365 服務包括:</span><span class="sxs-lookup"><span data-stu-id="833bf-115">For purposes of this article, Office 365 services include:</span></span>

- [<span data-ttu-id="833bf-116">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="833bf-116">Exchange Online</span></span>](https://docs.microsoft.com/Exchange/exchange-online)
- [<span data-ttu-id="833bf-117">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="833bf-117">Exchange Online Protection</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [<span data-ttu-id="833bf-118">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="833bf-118">SharePoint Online</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [<span data-ttu-id="833bf-119">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="833bf-119">OneDrive for Business</span></span>](https://docs.microsoft.com/OneDrive/onedrive)
- [<span data-ttu-id="833bf-120">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="833bf-120">Skype for Business</span></span>](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [<span data-ttu-id="833bf-121">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="833bf-121">Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [<span data-ttu-id="833bf-122">Yammer</span><span class="sxs-lookup"><span data-stu-id="833bf-122">Yammer</span></span>](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="office-365-access-controls"></a><span data-ttu-id="833bf-123">Office 365 存取控制</span><span class="sxs-lookup"><span data-stu-id="833bf-123">Office 365 Access Controls</span></span>

<span data-ttu-id="833bf-124">針對存取控制目的, Microsoft 會將 Office 365 資料分類為客戶資料或其他類型的資料。</span><span class="sxs-lookup"><span data-stu-id="833bf-124">For access control purposes, Microsoft categorizes Office 365 data as Customer data or other types of data.</span></span>

### <a name="customer-data"></a><span data-ttu-id="833bf-125">客戶資料</span><span class="sxs-lookup"><span data-stu-id="833bf-125">Customer data</span></span>

<span data-ttu-id="833bf-126">客戶資料是指使用 Office 365 服務時, 或代表客戶提供的所有資料。</span><span class="sxs-lookup"><span data-stu-id="833bf-126">Customer data is all data provided by or on behalf of a customer when using Office 365 services.</span></span> <span data-ttu-id="833bf-127">這是由 Office 365 使用者直接建立或上傳的客戶內容, 包括:</span><span class="sxs-lookup"><span data-stu-id="833bf-127">This is customer content directly created or uploaded by Office 365 users, including:</span></span>

- <span data-ttu-id="833bf-128">電子郵件</span><span class="sxs-lookup"><span data-stu-id="833bf-128">Emails</span></span>
- <span data-ttu-id="833bf-129">SharePoint Online 內容</span><span class="sxs-lookup"><span data-stu-id="833bf-129">SharePoint Online content</span></span>
- <span data-ttu-id="833bf-130">立即訊息</span><span class="sxs-lookup"><span data-stu-id="833bf-130">Instant messages</span></span>
- <span data-ttu-id="833bf-131">行事曆專案</span><span class="sxs-lookup"><span data-stu-id="833bf-131">Calendar items</span></span>
- <span data-ttu-id="833bf-132">文件</span><span class="sxs-lookup"><span data-stu-id="833bf-132">Documents</span></span>
- <span data-ttu-id="833bf-133">Contacts</span><span class="sxs-lookup"><span data-stu-id="833bf-133">Contacts</span></span>
- <span data-ttu-id="833bf-134">使用者身分識別資訊 (EUII) (是使用者特有或 linkable 給個別使用者, 但不包含客戶內容) 的資料。</span><span class="sxs-lookup"><span data-stu-id="833bf-134">End-user identifiable information (EUII) (data that is unique to a user or that is linkable to an individual user but does not include customer content).</span></span>

### <a name="other-types-of-data"></a><span data-ttu-id="833bf-135">其他類型的資料</span><span class="sxs-lookup"><span data-stu-id="833bf-135">Other types of data</span></span>

<span data-ttu-id="833bf-136">其他類型的資料包括:</span><span class="sxs-lookup"><span data-stu-id="833bf-136">Other types of data include:</span></span>

- <span data-ttu-id="833bf-137">**帳戶資料:** 包含管理資料 (系統管理員在註冊或購買服務時提供的資訊), 以及付款資料 (有關付款儀器的資訊, 例如信用卡詳細資訊)。</span><span class="sxs-lookup"><span data-stu-id="833bf-137">**Account data:** Includes administrative data (information provided by administrators when they sign-up or purchase services), and payment data (information about payment instruments, such as credit card details).</span></span>
- <span data-ttu-id="833bf-138">**組織識別資訊:** 包含用來識別租使用者、使用狀況資料, 而不是 linkable 給個別使用者或包含在客戶內容中的資料。</span><span class="sxs-lookup"><span data-stu-id="833bf-138">**Organizationally identifiable information:** Includes data used to identify a tenant, usage data, and not linkable to an individual user or included in customer content.</span></span>
- <span data-ttu-id="833bf-139">**系統中繼資料:** 包含服務記錄檔, 其中包含有關訂閱和承租人的設定設定、系統狀態、Microsoft IP 位址及技術資訊。</span><span class="sxs-lookup"><span data-stu-id="833bf-139">**System metadata:** Includes service logs that contain configuration settings, system status, Microsoft IP addresses, and technical information about subscriptions and tenants.</span></span>

<span data-ttu-id="833bf-140">Microsoft 已建立存取控制機制, 以確保任何人都無法撤銷對客戶資料或存取控制資料的存取。</span><span class="sxs-lookup"><span data-stu-id="833bf-140">Microsoft has established access control mechanisms to ensure that no one has unapproved access to Customer Data or access control data.</span></span> <span data-ttu-id="833bf-141">存取控制資料可管理環境內其他類型的資料或功能的存取, 包括對客戶內容或 EUII、Microsoft 密碼、安全性憑證及其他驗證相關資料的存取。</span><span class="sxs-lookup"><span data-stu-id="833bf-141">Access control data manages access to other types of data or functions within the environment, including access to customer content or EUII, Microsoft passwords, security certificates, and other authentication-related data.</span></span> <span data-ttu-id="833bf-142">存取控制機制也會防止未核准的實體、邏輯或遠端存取 Office 365 生產環境。</span><span class="sxs-lookup"><span data-stu-id="833bf-142">Access control mechanisms also guard against unapproved physical, logical, or remote access to the Office 365 production environment.</span></span>

<span data-ttu-id="833bf-143">Microsoft 適用于運作 Office 365 的 access 控制項有三種類別:</span><span class="sxs-lookup"><span data-stu-id="833bf-143">There are three categories of access controls used by Microsoft for operating Office 365:</span></span>

- <span data-ttu-id="833bf-144">隔離控制項</span><span class="sxs-lookup"><span data-stu-id="833bf-144">Isolation Controls</span></span>
- <span data-ttu-id="833bf-145">人員控制項</span><span class="sxs-lookup"><span data-stu-id="833bf-145">Personnel Controls</span></span>
- <span data-ttu-id="833bf-146">技術控制項</span><span class="sxs-lookup"><span data-stu-id="833bf-146">Technology Controls</span></span>

<span data-ttu-id="833bf-147">結合時, 這些控制項可協助防止和偵測 Office 365 中的惡意動作。</span><span class="sxs-lookup"><span data-stu-id="833bf-147">When combined, these controls help prevent and detect malicious actions in Office 365.</span></span> <span data-ttu-id="833bf-148">除了 Microsoft 所使用的隔離、人員和技術控制項, 還有第四種類別的控制項: 由客戶實施的控制項。</span><span class="sxs-lookup"><span data-stu-id="833bf-148">In addition to the isolation, personnel, and technology controls used by Microsoft, there is a fourth category of controls: those implemented by customers.</span></span>

<span data-ttu-id="833bf-149">Office 365 可讓您管理資料, 就像在內部部署環境中管理資料一樣。</span><span class="sxs-lookup"><span data-stu-id="833bf-149">Office 365 allows you to manage data the same way data is managed in on-premises environments.</span></span> <span data-ttu-id="833bf-150">註冊 Office 365 組織的人員會自動成為全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="833bf-150">The person who signs up an organization for Office 365 automatically becomes a global administrator.</span></span> <span data-ttu-id="833bf-151">全域系統管理員可以存取管理入口網站中的所有功能, 並且可以:</span><span class="sxs-lookup"><span data-stu-id="833bf-151">The global admin has access to all features in Management Portals and can:</span></span>

- <span data-ttu-id="833bf-152">建立或編輯使用者</span><span class="sxs-lookup"><span data-stu-id="833bf-152">Create or edit users</span></span>
- <span data-ttu-id="833bf-153">指派系統管理員角色給其他人</span><span class="sxs-lookup"><span data-stu-id="833bf-153">Assign admin roles to others</span></span>
- <span data-ttu-id="833bf-154">重設使用者密碼</span><span class="sxs-lookup"><span data-stu-id="833bf-154">Reset user passwords</span></span>
- <span data-ttu-id="833bf-155">管理使用者授權</span><span class="sxs-lookup"><span data-stu-id="833bf-155">Manage user licenses</span></span>
- <span data-ttu-id="833bf-156">管理網域</span><span class="sxs-lookup"><span data-stu-id="833bf-156">Manage domains</span></span>
- <span data-ttu-id="833bf-157">核准客戶加密箱要求</span><span class="sxs-lookup"><span data-stu-id="833bf-157">Approve Customer Lockbox requests</span></span>

<span data-ttu-id="833bf-158">建議每個組織至少設定兩個系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="833bf-158">We recommend that each organization configure at least two admin accounts.</span></span> <span data-ttu-id="833bf-159">對於大型企業組織, 我們建議以不同的功能為特定的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="833bf-159">For large enterprise organizations, we recommend specialized admin accounts that serve different functions.</span></span>

<span data-ttu-id="833bf-160">如需指派系統管理員角色及許可權的詳細資訊, 請參閱[在 office 365 中指派系統管理員角色](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504)和[關於 Office 365 系統管理員角色](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D)。</span><span class="sxs-lookup"><span data-stu-id="833bf-160">For information about assigning admin roles and permissions, see [Assigning admin roles in Office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) and [About Office 365 admin roles](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D).</span></span>

## <a name="related-links"></a><span data-ttu-id="833bf-161">相關連結</span><span class="sxs-lookup"><span data-stu-id="833bf-161">Related Links</span></span>

- [<span data-ttu-id="833bf-162">隔離控制項</span><span class="sxs-lookup"><span data-stu-id="833bf-162">Isolation Controls</span></span>](office-365-isolation-controls.md)
- [<span data-ttu-id="833bf-163">人員控制項</span><span class="sxs-lookup"><span data-stu-id="833bf-163">Personnel Controls</span></span>](office-365-personnel-controls.md)
- [<span data-ttu-id="833bf-164">技術控制項</span><span class="sxs-lookup"><span data-stu-id="833bf-164">Technology Controls</span></span>](office-365-technology-controls.md)
- [<span data-ttu-id="833bf-165">監視及稽核的存取控制</span><span class="sxs-lookup"><span data-stu-id="833bf-165">Monitoring and Auditing Access Controls</span></span>](office-365-monitoring-and-auditing-access-controls.md)
- [<span data-ttu-id="833bf-166">Yammer 企業存取控制</span><span class="sxs-lookup"><span data-stu-id="833bf-166">Yammer Enterprise Access Controls</span></span>](office-365-yammer-enterprise-access-controls.md)