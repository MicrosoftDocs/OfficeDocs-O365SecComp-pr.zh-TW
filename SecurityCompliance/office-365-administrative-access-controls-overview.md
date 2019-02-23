---
title: Office 365 中的系統管理存取控制
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
description: 摘要： Office 365 系統管理存取控制項和資料分類的概觀。
ms.openlocfilehash: b23fcdcb6c790b3860a24a555424beb3bb99e4f4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216023"
---
# <a name="administrative-access-controls-in-office-365"></a><span data-ttu-id="d83a3-103">Office 365 中的系統管理存取控制</span><span class="sxs-lookup"><span data-stu-id="d83a3-103">Administrative Access Controls in Office 365</span></span> 

## <a name="introduction"></a><span data-ttu-id="d83a3-104">簡介</span><span class="sxs-lookup"><span data-stu-id="d83a3-104">Introduction</span></span>
<span data-ttu-id="d83a3-p101">Microsoft 已投資嚴重與據以在系統及自動化大部分的 Office 365 作業時刻意限制客戶內容的 Microsoft access 的控制項。人們控管服務及軟體的操作服務。這可讓 Microsoft Office 365 管理向外延展，以及管理客戶內容惡意執行者，例如 Microsoft 工程師，依此類推矛網路釣魚內部威脅的風險。</span><span class="sxs-lookup"><span data-stu-id="d83a3-p101">Microsoft has invested heavily and accordingly in systems and controls that automate most Office 365 operations while intentionally limiting Microsoft's access to customer content. Humans govern the service, and software operates the service. This enables Microsoft to manage Office 365 at scale, as well as manage the risks of internal threats to customer content such as malicious actors, the spear-phishing of a Microsoft engineer, and so forth.</span></span>

<span data-ttu-id="d83a3-p102">根據預設，Microsoft 工程師會有零出位置管理權限和客戶內容零出位置存取 Office 365 中。Microsoft 工程師可以有限制、 稽核、 及安全存取客戶內容的有限的時間，但是只有當時所需的服務作業且時由 Microsoft 資深管理 （及成員的客戶而言核准授權給客戶 Lockbox 功能，客戶）。</span><span class="sxs-lookup"><span data-stu-id="d83a3-p102">By default, Microsoft engineers have zero standing administrative privileges and zero standing access to customer content in Office 365. A Microsoft engineer can have limited, audited, and secured access to a customer's content for a limited amount of time, but only when necessary for service operations, and only when approved by a member of Microsoft senior management (and for customers that are licensed for the Customer Lockbox feature, the customer).</span></span>

<span data-ttu-id="d83a3-110">Microsoft 提供線上服務，包括 Office 365 中，使用多個表單的雲端傳遞：</span><span class="sxs-lookup"><span data-stu-id="d83a3-110">Microsoft provides online services, including Office 365, using multiple forms of cloud delivery:</span></span>

- <span data-ttu-id="d83a3-111">**公用 Cloud** -包含多租用戶版本的 Office 365、 Azure、 和裝載於 「 北美地區 」、 南美洲、 歐洲、 亞洲、 澳洲等其他服務。</span><span class="sxs-lookup"><span data-stu-id="d83a3-111">**Public Clouds** - includes multi-tenant versions of Office 365, Azure, and other services that are hosted in North America, South America, Europe, Asia, Australia, etc.</span></span>
- <span data-ttu-id="d83a3-112">**國民雲朵**-例如中國 （這由 21Vianet 21vianet) 中的 Office 365 與 Office 365 德國包括 （但不包括這些上方另有說明），美國以外的所有統領和第三方 21vianet 雲朵 (這由 Microsoft 21vianet 但在 [下一種模型德文資料者，Deutsche Telekom 控制及監視客戶資料並包含客戶資料的系統的 Microsoft access）。</span><span class="sxs-lookup"><span data-stu-id="d83a3-112">**National Clouds** - includes all sovereign and third party-operated clouds outside of the United States (except for those noted above), such as Office 365 in China (which is operated by 21Vianet), and Office 365 in Germany (which is operated by Microsoft but under a model in which a German data trustee, Deutsche Telekom, controls and monitors Microsoft's access to Customer Data and systems that contain Customer Data).</span></span>
- <span data-ttu-id="d83a3-113">**政府雲朵**-包含可用來美國政府客戶的 Office 365 和 Azure 服務。</span><span class="sxs-lookup"><span data-stu-id="d83a3-113">**Government Clouds** - includes Office 365 and Azure services that are available to United States government customers.</span></span>

<span data-ttu-id="d83a3-p103">基於本文的詳細資訊，Office 365 服務包括[Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)、 [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)、 [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) （包括[OneDrive for Business](https://docs.microsoft.com/OneDrive/onedrive)） 和[Skype for Business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)的其他資訊關於某些[Yammer Enterprise](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)存取控制項。其他 Office 365 服務已超出本文範圍。</span><span class="sxs-lookup"><span data-stu-id="d83a3-p103">For purposes of this article, Office 365 services include [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online), [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview), [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) (including [OneDrive for Business](https://docs.microsoft.com/OneDrive/onedrive)) and [Skype for Business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online), with additional information about some [Yammer Enterprise](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US) access controls. Other Office 365 services are out of scope for this article.</span></span>

## <a name="office-365-access-controls"></a><span data-ttu-id="d83a3-116">Office 365 的存取控制</span><span class="sxs-lookup"><span data-stu-id="d83a3-116">Office 365 Access Controls</span></span>
<span data-ttu-id="d83a3-p104">基於存取控制，Office 365 的資料會歸類為客戶資料或其他類型的資料。客戶資料是由或代表 「 客戶使用的 Office 365 服務，例如客戶內容 （內容直接建立或由 Office 365 使用者包括電子郵件、 SharePoint Online 內容、 立即訊息、 上傳到客戶提供的所有資料行事曆項目、 文件及儲存在 Office 365 中的連絡人） 和使用者識別資訊 (EUII) （這是唯一的使用者，或資料的連結給個別使用者但不包括客戶內容）。</span><span class="sxs-lookup"><span data-stu-id="d83a3-p104">For access control purposes, Office 365 data is categorized as either Customer Data or other types of data. Customer Data is all data provided by or on behalf of a customer through the customer's use of Office 365 services, such as customer content (content directly created or uploaded by Office 365 users including emails, SharePoint Online content, instant messages, calendar items, documents, and contacts stored in Office 365) and end-user identifiable information (EUII) (data that is unique to a user or that is linkable to an individual user but does not include customer content).</span></span> 

<span data-ttu-id="d83a3-119">其他類型的資料包含帳戶資料 （包括系統管理的資料，這是當他們註冊或購買服務及付款儀器，例如信用的相關資訊的付款資料卡片詳細資料時由系統管理員所提供的資訊）公司識別資訊 (可用來識別租用戶; 的資料或使用狀況資料 ； 它不是連結至個別使用者並不包含客戶內容)，與系統中繼資料 （包括包含的組態設定的服務記錄檔系統狀態、 Microsoft IP 位址和訂閱及租用戶的技術資訊）。</span><span class="sxs-lookup"><span data-stu-id="d83a3-119">Other types of data include account data (includes administrative data, which is the information provided by administrators when they sign-up or purchase services, and payment data, which is information about payment instruments, such as credit card details), organizationally identifiable information (data that can be used to identify a tenant; or usage data; it is not linkable to an individual user and does not include customer content), and system metadata (includes service logs that contain configuration settings, system status, Microsoft IP addresses, and technical information about subscriptions and tenants).</span></span>

<span data-ttu-id="d83a3-120">Microsoft 已建立存取控制機制來確定無人具有未的資料的存取權的客戶資料或存取控制 (用來管理存取其他類型的資料或在函數中的環境，包括存取客戶內容或 EUII ； 它包含 Microsoft 密碼、 安全性憑證和驗證相關的其他資料） 或未實體、 邏輯、 或遠端存取 Office 365 實際執行環境。</span><span class="sxs-lookup"><span data-stu-id="d83a3-120">Microsoft has established access control mechanisms to ensure that no one has unapproved access to Customer Data or access control data (used to manage access to other types of data or functions within the environment, including access to customer content or EUII; it includes Microsoft passwords, security certificates, and other authentication-related data) or unapproved physical, logical, or remote access to the Office 365 production environment.</span></span>

<span data-ttu-id="d83a3-121">使用 Microsoft 的操作 Office 365 的存取控制項可分為三種類別：</span><span class="sxs-lookup"><span data-stu-id="d83a3-121">The access controls used by Microsoft for operating Office 365 can be grouped into three categories:</span></span>
- <span data-ttu-id="d83a3-122">隔離控制項</span><span class="sxs-lookup"><span data-stu-id="d83a3-122">Isolation Controls</span></span>
- <span data-ttu-id="d83a3-123">人員控制項</span><span class="sxs-lookup"><span data-stu-id="d83a3-123">Personnel Controls</span></span>
- <span data-ttu-id="d83a3-124">技術控制項</span><span class="sxs-lookup"><span data-stu-id="d83a3-124">Technology Controls</span></span>

<span data-ttu-id="d83a3-p105">當組合，這些控制項協助防止與 Office 365 中偵測到惡意的動作。除了隔離、 人員及 Microsoft 所使用的技術控制項中，有控制項的第四個類別： 所實作的客戶。</span><span class="sxs-lookup"><span data-stu-id="d83a3-p105">When combined, these controls help prevent and detect malicious actions in Office 365. In addition to the isolation, personnel, and technology controls used by Microsoft, there is a fourth category of controls: those implemented by customers.</span></span>

<span data-ttu-id="d83a3-p106">Office 365 可讓您管理在內部部署環境中受管理的相同方式資料中有多少資料。會設定組織的 Office 365 自動的人員會變成全域管理員 (admin)。全域管理員具有管理入口網站 （例如管理中心和遠端 PowerShell） 中的所有功能的存取權及可以建立或編輯使用者、 將系統管理員角色指派給其他人、 重設使用者密碼、 管理使用者授權、 管理網域，並核准客戶 Lockbox總而言之的要求。我們建議每個組織要指定至少兩種管理帳戶]，並根據貴組織的大小，您可能會想要指定數個系統管理員提供不同功能。如需指派管理角色和權限的資訊，請參閱[指派 Office 365 中的系統管理員角色](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504)和[有關 Office 365 系統管理員角色](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D)。</span><span class="sxs-lookup"><span data-stu-id="d83a3-p106">Office 365 allows you to manage your data much in the same way data is managed in on-premises environments. The person who signs up an organization for Office 365 automatically becomes a global administrator (admin). The global admin has access to all features in the management portals (e.g., admin centers and remote PowerShell), and can create or edit users, assign admin roles to others, reset user passwords, manage user licenses, manage domains, and approve Customer Lockbox requests, among other things. We recommend that each organization designate at least two admin accounts, and depending on the size of your organization, you may want to designate several admins who serve different functions. For information about assigning admin roles and permissions, see [Assigning admin roles in Office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) and [About Office 365 admin roles](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D).</span></span>


## <a name="related-links"></a><span data-ttu-id="d83a3-132">相關的連結</span><span class="sxs-lookup"><span data-stu-id="d83a3-132">Related Links</span></span>

- [<span data-ttu-id="d83a3-133">隔離控制項</span><span class="sxs-lookup"><span data-stu-id="d83a3-133">Isolation Controls</span></span>](office-365-isolation-controls.md)
- [<span data-ttu-id="d83a3-134">人員控制項</span><span class="sxs-lookup"><span data-stu-id="d83a3-134">Personnel Controls</span></span>](office-365-personnel-controls.md)
- [<span data-ttu-id="d83a3-135">技術控制項</span><span class="sxs-lookup"><span data-stu-id="d83a3-135">Technology Controls</span></span>](office-365-technology-controls.md)
- [<span data-ttu-id="d83a3-136">監視及稽核的存取控制</span><span class="sxs-lookup"><span data-stu-id="d83a3-136">Monitoring and Auditing Access Controls</span></span>](office-365-monitoring-and-auditing-access-controls.md)
- [<span data-ttu-id="d83a3-137">Yammer 企業存取控制</span><span class="sxs-lookup"><span data-stu-id="d83a3-137">Yammer Enterprise Access Controls</span></span>](office-365-yammer-enterprise-access-controls.md)