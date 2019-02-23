---
title: 資料外洩防護原則概觀
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 1966b2a7-d1e2-4d92-ab61-42efbb137f5e
description: 與 Office 365 安全性資料外洩防護 (DLP) 原則&amp;規範中心，您可以識別、 監視和自動跨 Office 365 保護敏感資料。
ms.openlocfilehash: bf30e7de625903c3cce53407901f627ef1345d66
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218973"
---
# <a name="overview-of-data-loss-prevention-policies"></a><span data-ttu-id="3c9d0-103">資料外洩防護原則概觀</span><span class="sxs-lookup"><span data-stu-id="3c9d0-103">Overview of data loss prevention policies</span></span>

<span data-ttu-id="3c9d0-p101">遵守商務標準與產業法規、 組織需要保護敏感資訊並防止其由於意外的揭露。您可能會想要防止遺漏組織外部的敏感資訊的範例包括財務資料或個人識別資訊 (PII) 等狀況記錄、 社會安全編號，或是信用卡號。與 Office 365 安全性資料外洩防護 (DLP) 原則&amp;規範中心，您可以識別、 監視和自動跨 Office 365 保護敏感資料。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p101">To comply with business standards and industry regulations, organizations need to protect sensitive information and prevent its inadvertent disclosure. Examples of sensitive information that you might want to prevent from leaking outside your organization include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.</span></span>
  
<span data-ttu-id="3c9d0-107">採用 DLP 原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-107">With a DLP policy, you can:</span></span>
  
- <span data-ttu-id="3c9d0-108">**識別所有許多位置，例如 Exchange Online、 SharePoint Online 和 OneDrive for Business 的機密資訊。**</span><span class="sxs-lookup"><span data-stu-id="3c9d0-108">**Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, and OneDrive for Business.**</span></span>
    
    <span data-ttu-id="3c9d0-109">例如，您可以識別包含儲存在任何 OneDrive for Business 網站是信用卡號任何文件或您可以監視 OneDrive 網站的特定人員。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-109">For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.</span></span>
    
- <span data-ttu-id="3c9d0-110">**防止意外共用敏感資訊**。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-110">**Prevent the accidental sharing of sensitive information**.</span></span> 
    
    <span data-ttu-id="3c9d0-111">例如，您可以找出任何文件或電子郵件包含與您的組織外部人員共用的狀況記錄及自動封鎖的存取權的文件或封鎖阻止傳送的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-111">For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.</span></span>
    
- <span data-ttu-id="3c9d0-112">**監視和保護 Excel 2016、PowerPoint 2016 和 Word 2016 桌面版中的敏感資訊。**</span><span class="sxs-lookup"><span data-stu-id="3c9d0-112">**Monitor and protect sensitive information in the desktop versions of Excel 2016, PowerPoint 2016, and Word 2016.**</span></span>
    
    <span data-ttu-id="3c9d0-p102">就像是在 Exchange Online、 SharePoint Online 和 OneDrive for Business，這些 Office 2016 桌上型程式包含識別敏感資訊並將 DLP 原則套用至相同的功能。DLP 提供持續的監視人員共用這些 Office 2016 應用程式中的內容時。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p102">Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office 2016 desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office 2016 programs.</span></span>
    
- <span data-ttu-id="3c9d0-115">**協助使用者了解如何符合規範，而不中斷其工作流程。**</span><span class="sxs-lookup"><span data-stu-id="3c9d0-115">**Help users learn how to stay compliant without interrupting their workflow.**</span></span>
    
    <span data-ttu-id="3c9d0-p103">您可以對您使用者 DLP 原則教育訓練，協助他們保持相容而不會封鎖他們的工作。例如，如果使用者嘗試共用文件包含機密資訊，DLP 原則可以將電子郵件通知傳送給他們與允許他們如果有公司會覆寫原則的文件庫的內容中顯示原則提示理由。相同的原則提示也會出現在網頁伺服器、 Outlook 2013 及更新版本，Excel 2016、 PowerPoint 2016 與 Word 2016 在 Outlook 中。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p103">You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook 2013 and later, Excel 2016, PowerPoint 2016, and Word 2016.</span></span>
    
- <span data-ttu-id="3c9d0-119">**檢視 DLP 報告顯示符合貴組織的 DLP 原則的內容。**</span><span class="sxs-lookup"><span data-stu-id="3c9d0-119">**View DLP reports showing content that matches your organization's DLP policies.**</span></span>
    
    <span data-ttu-id="3c9d0-p104">若要評估貴組織遵守 DLP 原則的方式，您可以看到多少會比對每個原則和規則有一段時間。如果 DLP 原則可讓使用者覆寫原則提示，並報告為誤判，您也可以檢視使用者均報告。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p104">To assess how your organization is complying with a DLP policy, you can see how many matches each policy and rule has over time. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported.</span></span>
    
<span data-ttu-id="3c9d0-122">建立及管理 Office 365 安全性資料遺失防護] 頁面上的 DLP 原則&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-122">You create and manage DLP policies on the Data loss prevention page in the Office 365 Security &amp; Compliance Center.</span></span>
  
![資料遺失防護] 頁面上的 Office 365 安全性&amp;規範中心](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a><span data-ttu-id="3c9d0-124">DLP 原則的內容</span><span class="sxs-lookup"><span data-stu-id="3c9d0-124">What a DLP policy contains</span></span>

<span data-ttu-id="3c9d0-125">DLP 原則包含一些基本事項：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-125">A DLP policy contains a few basic things:</span></span>
  
- <span data-ttu-id="3c9d0-126">若要保護的內容-**位置**例如 Exchange Online、 SharePoint Online 和 OneDrive for Business 的網站位置。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-126">Where to protect the content - **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites.</span></span> 
    
- <span data-ttu-id="3c9d0-127">何時及如何藉由執行強制包含下列要素的**規則**來保護內容：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-127">When and how to protect the content by enforcing **rules** comprised of:</span></span> 
    
  - <span data-ttu-id="3c9d0-128">**條件**內容必須符合才會強制執行規則-例如尋找只包含社會安全編號已與組織外部人員共用的內容。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-128">**Conditions** the content must match before the rule is enforced -- for example, look only for content containing Social Security numbers that's been shared with people outside your organization.</span></span> 
    
  - <span data-ttu-id="3c9d0-129">您要規則在找到符合條件的內容時自動採取的**動作** -- 例如封鎖文件的存取，以及傳送電子郵件通知給使用者和法務人員。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-129">**Actions** that you want the rule to take automatically when content matching the conditions is found -- for example, block access to the document and send both the user and compliance officer an email notification.</span></span> 
    
<span data-ttu-id="3c9d0-130">您可以使用規則來符合特定保護需求，並再使用 DLP 原則來群組在一起常見保護需求，例如所有符合特定法規所需的規則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-130">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="3c9d0-p105">例如，您可能會有 DLP 原則可協助您偵測受限於健康保險流通與責任法案 (HIPAA) 的資訊的目前狀態。此 DLP 原則可協助保護 HIPAA 資料 （英文） 跨所有 SharePoint Online 網站和所有 OneDrive for Business 的網站 （位置） 來尋找任何含有機密資訊 (您組織外部人員共用的文件條件） 然後封鎖存取文件並傳送通知 （動作）。這些需求會儲存為個別的規則及分組以簡化管理和報告的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p105">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA). This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions). These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![圖表顯示 DLP 原則包含位置和規則](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a><span data-ttu-id="3c9d0-135">位置</span><span class="sxs-lookup"><span data-stu-id="3c9d0-135">Locations</span></span>

<span data-ttu-id="3c9d0-p106">DLP 原則可尋找並保護跨 Office 365 的機密資訊是否該資訊位於 Exchange Online、 SharePoint Online、 或 OneDrive for Business。您可以輕鬆地選擇以保護所有 SharePoint 網站或 OneDrive 帳戶只是特定網站或帳戶或所有的信箱。請注意它尚未可能選取剛之特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p106">A DLP policy can find and protect sensitive information across Office 365, whether that information is located in Exchange Online, SharePoint Online, or OneDrive for Business. You can easily choose to protect all SharePoint sites or OneDrive accounts, just specific sites or accounts, or all mailboxes. Note that it's not yet possible to select just the mailboxes of specific users.</span></span>
  
![DLP 原則可以套用的位置選項](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
<span data-ttu-id="3c9d0-p107">請注意如果您選擇以包含或排除特定的 SharePoint 網站或 OneDrive 帳戶，DLP 原則可以包含不超過 100 這類包含與排除。雖然此限制存在，了解您可以藉由套用 [全組織的原則] 或 [套用至整個位置原則超過此限制。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p107">Note that if you choose to include or exclude specific SharePoint sites or OneDrive accounts, a DLP policy can contain no more than 100 such inclusions and exclusions. Although this limit exists, understand that you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>
  
### <a name="rules"></a><span data-ttu-id="3c9d0-142">規則</span><span class="sxs-lookup"><span data-stu-id="3c9d0-142">Rules</span></span>

<span data-ttu-id="3c9d0-p108">規則是什麼強制執行您對您的組織內容的業務需求。原則都包含一或多個規則和每個規則包含條件和動作。每個規則、 條件符合時採取動作自動。規則會依序執行，開頭中的每個原則的最高優先順序規則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p108">Rules are what enforce your business requirements on your organization's content. A policy contains one or more rules, and each rule consists of conditions and actions. For each rule, when the conditions are met, the actions are taken automatically. Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="3c9d0-147">規則也提供選項來通知 （搭配原則提示及電子郵件通知） 的使用者和系統管理員 （具有電子郵件附隨報告） 此內容具有符合的規則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-147">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="3c9d0-148">以下是規則元件、 解釋各個下方。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-148">Here are the components of a rule, each explained below.</span></span>
  
![DLP 規則編輯器的區段](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="3c9d0-150">條件</span><span class="sxs-lookup"><span data-stu-id="3c9d0-150">Conditions</span></span>

<span data-ttu-id="3c9d0-p109">條件至關重要，因為決定何種類型的您要尋找的資訊和何時要採取的動作。例如，您可能會選擇除非內容包含超過 10 個這種數字及與組織外部人員共用搜尋時忽略內容包含護照號碼。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p109">Conditions are important because they determine what types of information you're looking for, and when to take an action. For example, you might choose to ignore content containing passport numbers unless the content contains more than ten such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="3c9d0-p110">條件整個計畫重心在**內容**，例如哪些類型的機密資訊您在這裡尋找、 和**內容**，例如文件共用與人員。您可以使用條件將指派給不同的風險層級的不同動作--例如內部共用的敏感內容可能會是較低的風險和需要較少的動作較寫與組織外部人員共用的內容。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p110">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with. You can use conditions to assign different actions to different risk levels -- for example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![清單會顯示可用的 DLP 條件](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="3c9d0-156">目前可用的條件可以判斷：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-156">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="3c9d0-157">內容包含敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-157">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="3c9d0-p111">內容包含標籤。如需詳細資訊，請參閱以下一節[使用做為條件 DLP 原則中的標籤](data-loss-prevention-policies.md#label)。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p111">Content contains a label. For more information, see the below section [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#label).</span></span>
    
- <span data-ttu-id="3c9d0-160">內容是否與組織外部或內部人員共用。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-160">Content is shared with people outside or inside your organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="3c9d0-161">敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="3c9d0-161">Types of sensitive information</span></span>

<span data-ttu-id="3c9d0-p112">DLP 原則可協助保護機密資訊，這會定義為**敏感資訊類型**。Office 365 跨準備好讓您可以使用，例如信用卡號、 銀行帳戶號碼、 國家識別碼數字及護照號碼的許多不同區域包含許多常用的敏感資訊類型的定義。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p112">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**. Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![可用的敏感資訊類型清單](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="3c9d0-p113">當 DLP 原則看起來是信用卡號等機密資訊類型時，它只是看起來不 16 位數號碼。每個敏感資訊類型定義及偵測到的組合：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p113">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number. Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="3c9d0-167">關鍵字</span><span class="sxs-lookup"><span data-stu-id="3c9d0-167">Keywords</span></span>
    
- <span data-ttu-id="3c9d0-168">驗證總和檢查碼或結構的內部函數</span><span class="sxs-lookup"><span data-stu-id="3c9d0-168">Internal functions to validate checksums or composition</span></span>
    
- <span data-ttu-id="3c9d0-169">用以尋找模式相符項目的規則運算式評估</span><span class="sxs-lookup"><span data-stu-id="3c9d0-169">Evaluation of regular expressions to find pattern matches</span></span>
    
- <span data-ttu-id="3c9d0-170">其他內容檢查</span><span class="sxs-lookup"><span data-stu-id="3c9d0-170">Other content examination</span></span>
    
<span data-ttu-id="3c9d0-171">這有助於 DLP 偵測達到高程度的正確性同時減少誤判能夠中斷人員的工作數目。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-171">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="3c9d0-172">動作</span><span class="sxs-lookup"><span data-stu-id="3c9d0-172">Actions</span></span>

<span data-ttu-id="3c9d0-173">當內容符合的條件規則中時，您可以套用自動保護內容的動作。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-173">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![可用的 DLP 動作清單](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="3c9d0-175">立即可用的動作，您可以進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-175">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="3c9d0-p114">**Restrict 內容的存取權**網站內容，這表示文件的權限受到限制的主要網站集合管理員、 文件擁有者及上次修改文件的人以外的任何人。這些人員可以從文件移除機密資訊或採取其他補救措施。在符合性文件時，將會自動還原原始的權限。當封鎖存取文件時，文件會出現在網站上的文件庫中的特殊原則提示圖示。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p114">**Restrict access to the content** For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document. These people can remove the sensitive information from the document or take other remedial action. When the document is in compliance, the original permissions will be automatically restored. When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
    ![顯示文件存取的原則提示被封鎖](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    <span data-ttu-id="3c9d0-p115">電子郵件內容此動作會封鎖阻止傳送郵件。依據如何設定的 DLP 規則、 寄件者將會看到 NDR 或 （如果使用的規則通知） 的原則提示及/或電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p115">For email content, this action blocks the message from being sent. Depending on how the DLP rule is configured, the sender will see an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
    ![未經授權的收件者必須從郵件中移除的警告](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="3c9d0-184">使用者通知與使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="3c9d0-184">User notifications and user overrides</span></span>

<span data-ttu-id="3c9d0-p116">您可以使用通知及對您使用者 DLP 原則教育訓練及協助他們保持相容而不會封鎖他們的工作會覆寫。例如，如果使用者嘗試共用文件包含機密資訊，DLP 原則可以將電子郵件通知傳送給他們與允許他們如果有公司會覆寫原則的文件庫的內容中顯示原則提示理由。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p116">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![使用者通知與使用者會覆寫 DLP 規則編輯器的區段](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="3c9d0-p117">電子郵件可以通知傳送、 共用，或上次修改的內容和、 網站內容、 主要網站集合管理員及文件擁有者的人員。此外，您可以新增或移除任何一個您選擇的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p117">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner. In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="3c9d0-190">除了傳送的電子郵件通知，使用者通知會顯示原則提示：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-190">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="3c9d0-191">在 Outlook 2013 及更新版本及 Outlook web 上。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-191">In Outlook 2013 and later and Outlook on the web.</span></span>
    
- <span data-ttu-id="3c9d0-192">文件上的 SharePoint Online 或 OneDrive for Business 網站。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-192">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="3c9d0-193">在 Excel 2016 PowerPoint 2016 和 Word 2016，當文件儲存在網站上隨附於 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-193">In Excel 2016, PowerPoint 2016, and Word 2016, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="3c9d0-p118">電子郵件通知與原則提示說明為何內容與 DLP 原則與相衝突。如果您選擇的電子郵件通知和原則提示可以讓使用者覆寫規則報告為誤判或提供業務上理由。這可協助您對使用者 DLP 原則教育訓練及強制它們不防止使用者執行其工作。覆寫及誤判資訊也報表 （請參閱以下有關 DLP 報告） 的記錄及事件中包含報表 （下一節），以便法務可以定期檢閱此資訊。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p118">The email notification and policy tip explain why content conflicts with a DLP policy. If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification. This can help you educate users about your DLP policies and enforce them without preventing people from doing their work. Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="3c9d0-198">以下是看到原則提示外觀的 onedrive for Business 帳戶。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-198">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![文件中的 OneDrive 帳戶的原則提示](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a><span data-ttu-id="3c9d0-200">事件報告</span><span class="sxs-lookup"><span data-stu-id="3c9d0-200">Incident reports</span></span>

<span data-ttu-id="3c9d0-p119">當可於符合規則時，您可以傳送給您法務 （或任何您選擇的人員） 附隨報告使用事件的詳細資訊。這份報告包含的項目已符合比對規則及上次修改內容的人員名稱的實際內容的相關資訊。之電子郵件，報告也包含附件形式原始郵件符合 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p119">When a rule is matched, you can send an incident report to your compliance officer (or any people you choose) with details of the event. This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content. For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>
  
![設定事件報告的頁面](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="3c9d0-205">群組及邏輯運算子</span><span class="sxs-lookup"><span data-stu-id="3c9d0-205">Grouping and logical operators</span></span>

<span data-ttu-id="3c9d0-p120">通常您的 DLP 原則具有簡單的需求，例如找出包含美國社會安全號碼的所有內容。不過，在其他情況下，DLP 原則可能需要識別更鬆散已定義的資料。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p120">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number. However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="3c9d0-208">例如，若要識別內容受限於美國醫療保險法案 (HIPAA)，您需要尋找：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-208">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="3c9d0-209">包含機密資訊，例如美國社會安全號碼或藥物強制執行機構 (DEA) 編號的特定類型的內容。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-209">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="3c9d0-210">AND</span><span class="sxs-lookup"><span data-stu-id="3c9d0-210">AND</span></span>
    
- <span data-ttu-id="3c9d0-p121">內容的是更難識別，例如通訊有關病患照顧或醫療服務所提供的說明。用於識別此內容需要比對等國際分類的治療法 （ICD-9-CM 或 ICD-10-CM） 的極大的關鍵字清單中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p121">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided. Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="3c9d0-p122">您可以輕鬆地識別這類鬆散已定義的資料，使用群組及邏輯運算子 (AND、 OR)。當您建立的 DLP 原則時，您可以：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p122">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR). When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="3c9d0-215">群組敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-215">Group sensitive information types.</span></span>
    
- <span data-ttu-id="3c9d0-216">選擇自己的群組和群組中的敏感資訊類型之間的邏輯運算子。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-216">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="3c9d0-217">選擇群組中的運算子</span><span class="sxs-lookup"><span data-stu-id="3c9d0-217">Choosing the operator within a group</span></span>

<span data-ttu-id="3c9d0-218">在群組中，您可以選擇是否任一或所有該群組中的條件必須滿足要比對此規則之內容。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-218">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![顯示群組內的 operators 群組](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="3c9d0-220">新增群組</span><span class="sxs-lookup"><span data-stu-id="3c9d0-220">Adding a group</span></span>

<span data-ttu-id="3c9d0-221">您可以快速地新增群組可以擁有自己的條件及該群組中的運算子。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-221">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![[新增群組] 按鈕](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="3c9d0-223">選擇群組之間的運算子</span><span class="sxs-lookup"><span data-stu-id="3c9d0-223">Choosing the operator between groups</span></span>

<span data-ttu-id="3c9d0-224">之間群組，您可以選擇是否必須滿足只是一個群組或所有項目之群組中的條件來比對此規則之內容。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-224">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="3c9d0-225">例如，內建**美國 HIPAA**原則都具有使它會識別包含的內容會使用**AND**運算子群組之間的規則：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-225">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="3c9d0-226">從群組**PII 識別碼**(至少一個 SSN number**或**DEA)</span><span class="sxs-lookup"><span data-stu-id="3c9d0-226">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="3c9d0-227">**AND**</span><span class="sxs-lookup"><span data-stu-id="3c9d0-227">**AND**</span></span>
    
- <span data-ttu-id="3c9d0-228">從群組**醫療字詞**（至少一個 ICD-9-CM 關鍵字**或**的 ICD-10-CM 關鍵字）</span><span class="sxs-lookup"><span data-stu-id="3c9d0-228">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![顯示群組之間的運算子的群組](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="3c9d0-230">所處理的規則優先順序</span><span class="sxs-lookup"><span data-stu-id="3c9d0-230">The priority by which rules are processed</span></span>

<span data-ttu-id="3c9d0-p123">當您建立原則規則時，每個規則指派的優先順序順序在其中建立-表示，建立的規則前必須第一個優先順序、 建立第二個規則具有第二個優先順序等等。建立規則後，就無法變更其優先順序，刪除並重新建立它除外。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p123">When you create rules in a policy, each rule is assigned a priority in the order in which it's created - meaning, the rule created first has first priority, the rule created second has second priority, and so on. After you create a rule, its priority can't be changed, except by deleting and re-creating it.</span></span>
  
![規則優先順序](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
<span data-ttu-id="3c9d0-p124">根據規則評估內容時，這些規則會處理優先順序。如果內容符合多個規則，這些規則會處理會依照優先順序和最嚴格巨集指令會強制執行。例如，如果內容符合所有以下規則，規則 3 會強制執行因為它是最高優先順序、 最嚴格規則：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p124">When content is evaluated against rules, the rules are processed in priority order. If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced. For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="3c9d0-237">規則 1： 只會通知使用者</span><span class="sxs-lookup"><span data-stu-id="3c9d0-237">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="3c9d0-238">規則 2： 通知使用者、 限制存取，並允許使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="3c9d0-238">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="3c9d0-239">規則 3： 通知使用者、 限制存取，並不允許使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="3c9d0-239">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="3c9d0-240">規則 4： 僅通知使用者</span><span class="sxs-lookup"><span data-stu-id="3c9d0-240">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="3c9d0-241">規則 5： 限制存取</span><span class="sxs-lookup"><span data-stu-id="3c9d0-241">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="3c9d0-242">規則 6： 通知使用者、 限制存取，並不允許使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="3c9d0-242">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="3c9d0-243">在這個範例中，記的所有規則相符會記錄在稽核記錄並顯示在 DLP 報告中，即使最嚴格的規則會強制執行。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-243">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="3c9d0-244">表示原則提示，請注意：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-244">With respect to policy tips, note that:</span></span>
  
- <span data-ttu-id="3c9d0-p125">僅限的原則提示從最高的優先順序，將會顯示最嚴格的規則。例如，原則提示從會透過直接傳送通知的規則從原則提示顯示組塊內容的存取權的規則。這可防止看到重疊顯示原則提示的人員。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p125">Only the policy tip from the highest priority, most restrictive rule will be shown. For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification. This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="3c9d0-248">如果最嚴格規則中的原則提示允許人員覆寫規則，則覆寫此規則也將會覆寫內容符合的任何其他規則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-248">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="3c9d0-249">調整，使其更容易或更困難以符合的規則</span><span class="sxs-lookup"><span data-stu-id="3c9d0-249">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="3c9d0-250">人員建立並開啟其 DLP 原則後，有時執行發生下列問題：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-250">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="3c9d0-251">**不是**敏感資訊比對規則-換句話說，太多誤判太多內容。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-251">Too much content that **is not** sensitive information matches the rules - in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="3c9d0-252">太少的內容**是**敏感資訊比對規則-換句話說，保護不被強制執行動作的機密資訊為基礎。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-252">Too little content that **is** sensitive information matches the rules - in other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="3c9d0-p126">若要解決這些問題，您可以調整規則的執行個體計數調整且符合正確性使其更困難或更容易以符合規則的內容。每個規則中使用的敏感資訊類型都有兩個執行個體計數和比對的正確性。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p126">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules. Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="3c9d0-255">執行個體計數</span><span class="sxs-lookup"><span data-stu-id="3c9d0-255">Instance count</span></span>

<span data-ttu-id="3c9d0-p127">執行個體計數只是表示特定的敏感資訊類型的多少項目必須要有要比對此規則的內容。例如，內容將符合以下是否介於 1 到 9 唯一美國或英國護照號碼所識別的規則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p127">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule. For example, content will match the rule shown below if between 1 and 9 unique U.S. or U.K. passport numbers are identified.</span></span>
  
<span data-ttu-id="3c9d0-p128">請注意的執行個體計數包括僅敏感資訊類型和關鍵字**唯一**相符項目。例如，如果電子郵件包含相同的信用卡號的 10 個項目，這些 10 個項目就會視為是信用卡號的單一執行個體。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p128">Note that the instance count includes only **unique** matches for sensitive information types and keywords. For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span> 
  
<span data-ttu-id="3c9d0-261">若要使用執行個體計數調整規則，指導很簡單：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-261">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="3c9d0-p129">若要方便規則來比對，減少的**分鐘**數和/或增加的**最大**計數。您也可以設定**最大**至**任何**所刪除的數值。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p129">To make the rule easier to match, decrease the **min** count and/or increase the **max** count. You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="3c9d0-264">如果要讓規則來比對更困難，增加的**分鐘**數。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-264">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="3c9d0-p130">一般而言，您可以使用限制較少的動作，例如傳送使用者通知中以較低的執行個體計數 (例如 1-9) 的規則。並使用更嚴格的動作，例如限制不允許使用者覆寫規則具有較高的執行個體計數 （例如 10 任何） 中存取內容。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p130">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9). And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![規則編輯器中的執行個體計數](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="3c9d0-268">比對的正確性</span><span class="sxs-lookup"><span data-stu-id="3c9d0-268">Match accuracy</span></span>

<span data-ttu-id="3c9d0-p131">如前文所述，敏感資訊類型定義及使用不同類型的辨識項的組合來偵測。通常，由多個這類組合，呼叫模式定義敏感資訊類型。需要較少證據圖樣具有較低的相符項目正確性 （或 [信賴等級） 時需要更多的證據具有較高的相符項目正確性 （或信賴等級） 的模式。若要深入了解的實際模式和每個敏感資訊類型所使用的信賴等級，請參閱[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p131">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence. Commonly, a sensitive information type is defined by multiple such combinations, called patterns. A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level). To learn more about the actual patterns and confidence levels used by every sensitive information type, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
<span data-ttu-id="3c9d0-273">例如，名為信用卡號的機密資訊類型定義兩種模式：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-273">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="3c9d0-274">65%信賴需要使用模式：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-274">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="3c9d0-275">信用卡號編號的格式。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-275">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="3c9d0-276">通過總和檢查碼數目。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-276">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="3c9d0-277">85%信賴需要使用模式：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-277">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="3c9d0-278">信用卡號編號的格式。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-278">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="3c9d0-279">通過總和檢查碼數目。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-279">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="3c9d0-280">關鍵字或右邊格式到期。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-280">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="3c9d0-p132">您可以使用這些信賴等級 （或比對的正確性） 中的規則。一般而言，您可以使用限制較少的動作，例如傳送使用者通知中以較低的相符項目正確性的規則。並使用更嚴格的動作，例如限制不允許使用者覆寫具有較高的相符項目正確性規則中存取內容。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p132">You can use these confidence levels (or match accuracy) in your rules. Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy. And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="3c9d0-284">請務必了解當內容中所識別特定類型的機密資訊，例如信用卡頁碼，會傳回只有單一信賴等級：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-284">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="3c9d0-285">如果全部的相符項目是單一模式，則會傳回該模式信賴等級。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-285">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="3c9d0-p133">如果有多個圖樣的相符 （亦即有與兩個不同的信賴等級的相符項目），傳回高於任何單一模式單獨的信賴等級。這是麻煩的部分。例如為信用卡，如果 65%和 85%模式比對的信賴等級傳回敏感資訊類型是大於 90%的因為詳細證據表示多個信賴。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p133">If there are matches for more than one pattern (i.e., there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned. This is the tricky part. For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="3c9d0-p134">因此如果您想要建立兩個互斥信用卡、 另一個用於 65%相符項目精準度和 85%相符的正確性，一種規則的相符項目正確性範圍起來如下。第一個規則挑選只比對的 65%圖樣。第二個規則可以挑選符合**至少一個**85%相符項目及**可以可能有**其他較低信賴相符項目。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p134">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this. The first rule picks up only matches of the 65% pattern. The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![兩個不同的相符項目正確性的範圍規則](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="3c9d0-293">基於這些原因，以不同的比對精確度建立規則的指引是：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-293">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="3c9d0-294">最低的信賴等級通常會使用**min**和**max** （不範圍） 的值相同。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-294">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="3c9d0-295">最高的信賴等級通常是介於正上方的較低的信賴等級為 100。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-295">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="3c9d0-296">任何中間信賴等級通常範圍是從較低信賴等級設下方的較高的信賴等級的正上方。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-296">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="3c9d0-297">使用標籤做為 DLP 原則的條件</span><span class="sxs-lookup"><span data-stu-id="3c9d0-297">Using a label as a condition in a DLP policy</span></span>

<span data-ttu-id="3c9d0-298">您可以建立標籤然後：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-298">You can create a label and then:</span></span>
  
- <span data-ttu-id="3c9d0-299">**發佈**，使用者可以看到和手動將標籤套用至內容。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-299">**Publish** it, so that end users can see and manually apply the label to content.</span></span> 
    
- <span data-ttu-id="3c9d0-300">**自動套用**的內容符合您所選擇的條件。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-300">**Auto-apply** it to content that matches the conditions that you choose.</span></span> 
    
<span data-ttu-id="3c9d0-301">如需標籤的詳細資訊，請參閱 ＜ [Overview of 保留標籤](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-301">For more information about labels, see [Overview of retention labels](labels.md).</span></span>
  
<span data-ttu-id="3c9d0-p135">建立標籤之後，然後 DLP 原則中使用該標籤做為條件。例如，您可能會想要因為執行這項作業：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p135">After you create a label, you can then use that label as a condition in your DLP policies. For example, you might want to do this because:</span></span>
  
- <span data-ttu-id="3c9d0-p136">您發佈標籤名為 2 私人 3**機密文件**，以便在組織中的人員可以手動套用至機密的電子郵件和文件的標籤。使用這個標籤做為條件 DLP 原則中，您可以限制標示**2 私人 3 機密**從與您組織外部人員共用的內容。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p136">You published a label named **Confidential**, so that people in your organization can manually apply the label to confidential email and documents. By using this label as a condition in your DLP policy, you can restrict content labeled **Confidential** from being shared with people outside your organization.</span></span> 
    
- <span data-ttu-id="3c9d0-p137">您建立名為**高山門牌**該名稱的專案的標籤及自動內容包含關鍵字"高山 House"套用該標籤。藉由使用這個標籤做為條件 DLP 原則中，您可以向使用者顯示原則提示時它們是要與組織外的某個人共用此內容。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p137">You created a label named **Alpine House** for a project of that name, and then applied that label automatically to content containing the keywords "Alpine House". By using this label as a condition in your DLP policy, you can show a policy tip to end users when they're about to share this content with someone outside your organization.</span></span> 
    
- <span data-ttu-id="3c9d0-p138">您發佈名為**稅記錄**的標籤，讓記錄管理員可以手動將標籤套用至分類為記錄所需的內容。使用這個標籤做為條件 DLP 原則中，您可以查看此標籤與其他類型的 ITINs 或 SSNs; 等機密資訊一起使用的內容將保護動作套用至內容標示**稅記錄**；取得有關 DLP 原則的詳細的活動報告從 DLP 報告並稽核記錄檔資料。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p138">You published a label named **Tax record**, so that your records manager can manually apply the label to content that needs to be classified as a record. By using this label as a condition in your DLP policy, you can look for content with this label in conjunction with other types of sensitive information such as ITINs or SSNs; apply protection actions to content labeled **Tax record**; and get detailed activity reports about the DLP policy from the DLP reports and audit log data.</span></span> 
    
- <span data-ttu-id="3c9d0-p139">您發佈至 Exchange 信箱和主管群組中的 OneDrive 帳戶名為**Executive 領導小組機密**的標籤。使用這個標籤做為條件 DLP 原則中，您可以強制執行保留及保護動作在相同的子集合的內容和使用者。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p139">You published a label named **Executive Leadership Team - Sensitive** to the Exchange mailboxes and OneDrive accounts of a group of executives. By using this label as a condition in your DLP policy, you can enforce both retention and protection actions on the same subset of content and users.</span></span> 
    
<span data-ttu-id="3c9d0-312">使用標籤作為 DLP 規則條件，可以您選擇性地強制上一組特定的內容、 位置、 或使用者的保護動作。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-312">By using labels as a condition in your DLP rules, can you selectively enforce protection actions on a specific set of content, locations, or users.</span></span>
  
![做為條件的標籤](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

### <a name="support-for-sensitivity-labels-is-coming"></a><span data-ttu-id="3c9d0-314">即將支援的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="3c9d0-314">Support for sensitivity labels is coming</span></span>

<span data-ttu-id="3c9d0-p140">請注意您目前可使用保留標籤做為條件、 不[區分大小寫標籤](sensitivity-labels.md)。我們目前使用這種情況中使用的敏感度標籤的支援。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p140">Note that you can currently use only a retention label as a condition, not a [sensitivity label](sensitivity-labels.md). We're currently working on support for using a sensitivity label in this condition.</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="3c9d0-317">這項功能與其他功能的方式</span><span class="sxs-lookup"><span data-stu-id="3c9d0-317">How this feature relates to other features</span></span>

<span data-ttu-id="3c9d0-318">數項功能可套用至包含敏感資訊的內容：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-318">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="3c9d0-319">[保留標籤](labels.md#applying-a-retention-label-automatically-based-on-conditions)和[保留原則](retention-policies.md)可以同時強制對此內容**保留**動作。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-319">A [retention label](labels.md#applying-a-retention-label-automatically-based-on-conditions) and a [retention policy](retention-policies.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="3c9d0-p141">DLP 原則可以強制**保護**動作的此內容。與之前強制執行這些動作，DLP 原則可能需要其他條件以符合除了包含標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p141">A DLP policy can enforce **protection** actions on this content. And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![功能可套用至敏感資訊的圖表](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="3c9d0-p142">請注意 DLP 原則比標籤或保留原則套用至敏感資訊的豐富偵測功能。DLP 原則可以強制保護措施包含敏感資訊的內容與已從內容移除機密資訊則那些防護動作都復原的內容掃描下一次。但如果保留原則或標籤套用至包含敏感資訊的內容，即使移除機密資訊將不能復原一次性動作。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p142">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information. A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned. But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information's removed.</span></span>
  
<span data-ttu-id="3c9d0-p143">使用標籤做為條件 DLP 原則中，您可以強制執行該標籤中的內容保留及保護動作。您可以考量的內容包含包含敏感資訊的內容完全一樣的標籤-標籤和敏感資訊類型是用來分類內容，以便您可以強制執行動作對該內容的屬性。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p143">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label. You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![使用標籤做為條件的 DLP 原則的圖表](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="3c9d0-329">簡易設定與進階設定</span><span class="sxs-lookup"><span data-stu-id="3c9d0-329">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="3c9d0-330">當您建立的 DLP 原則時，您將會選擇簡單] 或 [進階] 設定：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-330">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="3c9d0-331">**簡單的設定**可以輕鬆建立 DLP 原則的最常見的類型而不使用規則編輯器 」 來建立或修改規則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-331">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="3c9d0-332">**進階設定**可用於規則編輯器提供 DLP 原則的每個設定的完整控制權。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-332">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="3c9d0-p144">不要擔心在幕後簡單的設定和進階的設定適用於完全相同，來強制執行規則的條件和動作-僅限具有簡單設定包含下列、 看不到規則編輯器。它是很快建立 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p144">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions -- only with simple settings, you don't see the rule editor. It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="3c9d0-335">簡單的設定</span><span class="sxs-lookup"><span data-stu-id="3c9d0-335">Simple settings</span></span>

<span data-ttu-id="3c9d0-p145">到目前為止，最常用的 DLP 案例建立來保護內容包含敏感資訊外您的組織並善加例如限制自動補救措施可以存取內容的人共用原則傳送使用者或系統通知和稽核更新調查有關的事件。人員使用 DLP 以避免由於意外敏感資訊的揭露。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p145">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remedial action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation. People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="3c9d0-p146">為了簡化達成這項目標，當您建立的 DLP 原則時，您可以選擇**使用簡單的設定**。這些設定會提供實作最常見的 DLP 原則，而不必移到規則編輯器所需的所有項目。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p146">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**. These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![DLP 簡單] 和 [進階設定選項](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="3c9d0-341">進階設定</span><span class="sxs-lookup"><span data-stu-id="3c9d0-341">Advanced settings</span></span>

<span data-ttu-id="3c9d0-342">如果您需要建立更多自訂的 DLP 原則，您可以選擇**使用進階設定**。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-342">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="3c9d0-343">進階的設定可提供您規則編輯器中，您可完全控制每個可能的選項，包括的執行個體計數及比對每個規則的正確性 （信賴等級）。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-343">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="3c9d0-344">若要快速跳至] 區段中，按一下上方導覽列中的規則編輯器移至下該區段中的項目。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-344">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![上方導覽列] 功能表中的 DLP 規則編輯器](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="3c9d0-346">DLP 原則範本</span><span class="sxs-lookup"><span data-stu-id="3c9d0-346">DLP policy templates</span></span>

<span data-ttu-id="3c9d0-p147">建立 DLP 原則的第一個步驟選擇要保護哪些資訊。開始使用 DLP 範本，您可以儲存建立一組新的規則從零開始，並找出哪些類型的資訊應該包含預設的工作。然後可以新增至或修改這些需求，以微調以符合組織的特定需求的規則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p147">The first step in creating a DLP policy is choosing what information to protect. By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default. You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="3c9d0-p148">預先設定的 DLP 原則範本可協助您偵測特定的敏感資訊，例如 HIPAA 資料、 PCI-DSS 資料、 Gramm-leach-bliley 金融服務業現代化法案資料或甚至是特定地區設定的個人識別資訊 (P.I.) 類型。若要方便您尋找並保護常見的敏感資訊類型、 已包含在 Office 365 中的原則範本包含最常見的敏感資訊類型時所需的您開始。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p148">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.). To make it easy for you to find and protect common types of sensitive information, the policy templates included in Office 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![資料外洩防護原則的範本清單，重點在於針對美國的範本愛國者法案](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="3c9d0-p149">您的組織可能也有自己的特定需求、 在此情況下您可以建立的 DLP 原則從頭選擇的**自訂原則**選項。自訂原則是空白的包含沒有預設的規則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p149">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option. A custom policy is empty and contains no premade rules.</span></span> 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a><span data-ttu-id="3c9d0-355">以測試模式逐漸推出 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="3c9d0-355">Roll out DLP policies gradually with test mode</span></span>

<span data-ttu-id="3c9d0-p150">當您建立 DLP 原則時，則應考慮啟用它們逐漸評估影響並之前先在完整執行測試其有效性。例如，您不想要不小心封鎖數以千計的人員以取得完成其工作需要的存取權的文件的新 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p150">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.</span></span>
  
<span data-ttu-id="3c9d0-358">如果您具有大型的潛在影響建立 DLP 原則，建議您遵循此順序：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-358">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="3c9d0-p151">**在不搭配原則提示的測試模式中啟動**與再使用 DLP 報告和任何事件報告來評估影響。您可以使用 DLP 報告檢視數目、 位置、 類型及原則相符的嚴重性。根據結果，您可以進行微調規則所需。在測試模式中 DLP 原則不會影響人員在組織中使用的產的能。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p151">**Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
2. <span data-ttu-id="3c9d0-p152">**移至測試模式與通知及原則提示**，讓您可以開始教導規範原則相關的使用者，以及準備要套用規則。在此階段中，您也可以要求使用者報告誤判，讓您可以進一步調整規則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p152">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span> 
    
3. <span data-ttu-id="3c9d0-p153">**開始完整的強制執行原則上**以便套用規則的動作和內容的 [受保護。繼續進行監視 DLP 報告任何附隨報告或以確保結果是您想要的通知。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p153">**Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
![使用測試模式和開啟原則的選項](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
<span data-ttu-id="3c9d0-p154">您可以關閉在任何時候，而這會影響原則中的所有規則的 DLP 原則。不過，每個規則可以也關閉個別切換規則編輯器中的狀態。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p154">You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>
  
![在原則中關閉規則的選項](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)
  
## <a name="dlp-reports"></a><span data-ttu-id="3c9d0-371">DLP 報告</span><span class="sxs-lookup"><span data-stu-id="3c9d0-371">DLP reports</span></span>

<span data-ttu-id="3c9d0-p155">建立並開啟 DLP 原則後，您將想要確認其是以您預期運作幫助您保持相容。DLP 報告，您可以快速檢視的 DLP 原則和規則比對一段時間和誤判數目，會覆寫。針對每個報告，您可以篩選的時間範圍的位置這些相符項目並即使縮小至特定的原則、 規則或巨集指令。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p155">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant. With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides. For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="3c9d0-375">透過 DLP 報告，您將可取得深入的商業資訊，並且：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-375">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="3c9d0-376">將重點放在特定時段，以了解尖峰和趨勢的原因。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-376">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="3c9d0-377">探索違反組織的規範遵守原則的商務程序。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-377">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="3c9d0-378">了解 DLP 原則帶來的任何業務影響。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-378">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="3c9d0-379">此外，您可以使用 DLP 報告來微調您所執行的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-379">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![安全性和規範中心 」 中的報表儀表板](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="3c9d0-381">DLP 原則的運作方式</span><span class="sxs-lookup"><span data-stu-id="3c9d0-381">How DLP policies work</span></span>

<span data-ttu-id="3c9d0-p156">DLP 會使用深度內容分析 (不只是簡單的文字掃描) 來偵測敏感資訊。此深度內容分析會使用關鍵字比對、字典比對、規則運算式評估、內部函數和其他方法來偵測符合 DLP 原則的內容。可能只有一小部分的資料會被視為敏感資訊。DLP 原則可識別、監視和自動保護該項資料，而不會妨礙或影響到使用其餘內容的人員。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p156">DLP detects sensitive information by using deep content analysis (not just a simple text scan). This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies. Potentially only a small percentage of your data is considered sensitive. A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="3c9d0-386">原則會同步處理</span><span class="sxs-lookup"><span data-stu-id="3c9d0-386">Policies are synced</span></span>

<span data-ttu-id="3c9d0-387">在 [安全性] 中建立的 DLP 原則之後&amp;規範中心已儲存在中央原則存放區，並再同步處理至各種內容來源，包括：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-387">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="3c9d0-388">Exchange Online，並從有至網路上的 Outlook 和 Outlook 2013 及更新版本</span><span class="sxs-lookup"><span data-stu-id="3c9d0-388">Exchange Online, and from there to Outlook on the web and Outlook 2013 and later</span></span>
    
- <span data-ttu-id="3c9d0-389">商務用 OneDrive 網站</span><span class="sxs-lookup"><span data-stu-id="3c9d0-389">OneDrive for Business sites</span></span>
    
- <span data-ttu-id="3c9d0-390">SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="3c9d0-390">SharePoint Online sites</span></span>
    
- <span data-ttu-id="3c9d0-391">Office 2016 桌面程式 (Excel 2016、PowerPoint 2016 和 Word 2016)</span><span class="sxs-lookup"><span data-stu-id="3c9d0-391">Office 2016 desktop programs (Excel 2016, PowerPoint 2016, and Word 2016)</span></span>
    
<span data-ttu-id="3c9d0-392">原則的同步處理至正確位置之後，開始評估內容並強制執行動作。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-392">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="3c9d0-393">商務用 OneDrive 和 SharePoint Online 網站中的原則評估</span><span class="sxs-lookup"><span data-stu-id="3c9d0-393">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="3c9d0-p157">經常變更文件中的所有 SharePoint Online 網站與 OneDrive for Business 的網站、 — 他們正在持續要建立、 編輯、 共用及等等。這表示文件可產生衝突或任何時候成為符合 DLP 原則。例如人員可以上傳不包含機密資訊至其小組網站、 文件，但稍後其他人可以編輯相同文件並新增至其中的機密資訊。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p157">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on. This means documents can conflict or become compliant with a DLP policy at any time. For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="3c9d0-p158">因此，DLP 原則會頻繁地在背景中檢查文件是否有原則相符項目。您可以將此視為非同步原則評估。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p158">For this reason, DLP policies check documents for policy matches frequently in the background. You can think of this as asynchronous policy evaluation.</span></span>
  
<span data-ttu-id="3c9d0-p159">以下是其運作方式。當人員新增或變更其網站中的文件、 搜尋引擎會掃描內容、，讓您可以搜尋其更新版本。當發生此問題時，將內容也掃描敏感資訊] 核取為共用。使規範小組可以存取它，但不是一般使用者找到任何敏感資訊就是安全地儲存在搜尋索引中。您已開啟的每個 DLP 原則執行背景中 （非同步），檢查常見問題的任何符合原則的內容搜尋與套用防止不小心遺漏的動作。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p159">Here's how it works. As people add or change documents in their sites, the search engine scans the content, so that you can search for it later. While this is happening, the content's also scanned for sensitive information and to check if it's shared. Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users. Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![圖表顯示如何 DLP 原則評估內容以非同步方式](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<span data-ttu-id="3c9d0-p160">最後，文件可能會違反 DLP 原則，但也可能會符合 DLP 原則。例如，如果人員在文件中加入信用卡號碼，有可能會導致 DLP 原則自動封鎖文件的存取。但如果人員稍後移除敏感資訊，則會在下次依據原則進行評估時自動復原動作 (在此案例中為封鎖)。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p160">Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy. For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically. But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="3c9d0-p161">DLP 評估編製索引的任何內容。預設會編目哪些檔案類型的詳細資訊，請參閱[預設編目檔案副檔名及剖析 SharePoint Server 2013 中的檔案類型](https://go.microsoft.com/fwlink/p/?LinkID=627430)。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p161">DLP evaluates any content that can be indexed. For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server 2013](https://go.microsoft.com/fwlink/p/?LinkID=627430).</span></span>
  
### <a name="policy-evaluation-in-exchange-online-outlook-2013-and-later-and-outlook-on-the-web"></a><span data-ttu-id="3c9d0-410">Exchange Online、 Outlook 2013 及更新版本，以及在 web 上的 Outlook 中的原則評估</span><span class="sxs-lookup"><span data-stu-id="3c9d0-410">Policy evaluation in Exchange Online, Outlook 2013 and later, and Outlook on the web</span></span>

<span data-ttu-id="3c9d0-411">當您建立包含 Exchange Online 作為位置的 DLP 原則時，該原則的同步處理從 Office 365 安全性&amp;規範中心至 Exchange Online，然後從 Exchange Online 至網路上的 Outlook 和 Outlook 2013 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-411">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook 2013 and later.</span></span>
  
<span data-ttu-id="3c9d0-p162">當郵件被包含在 Outlook 中時，使用者可以查看原則提示就會對 DLP 原則評估所建立的內容。與傳送的訊息之後，評估針對 DLP 原則的郵件流程，以及 Exchange 傳輸規則和 DLP 原則在 Exchange 系統管理中心中建立標準一部分 （請參閱 [下一步] 區段中的詳細資訊）。DLP 原則會掃描郵件和任何附件。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p162">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies. And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange transport rules and DLP policies created in the Exchange Admin Center (see the next section for more info). DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-2016-desktop-programs"></a><span data-ttu-id="3c9d0-415">Office 2016 桌面程式中的原則評估</span><span class="sxs-lookup"><span data-stu-id="3c9d0-415">Policy evaluation in the Office 2016 desktop programs</span></span>

<span data-ttu-id="3c9d0-p163">Excel 2016、 PowerPoint 2016 和 Word 2016 包含識別敏感資訊並套用 DLP 原則做為 SharePoint Online 和 OneDrive for Business 的同一個功能。這些 Office 2016 程式同步處理直接從中央原則存放區及其 DLP 原則並人員使用隨附的 DLP 原則的網站從開啟的文件時再持續評估針對 DLP 原則的內容。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p163">Excel 2016, PowerPoint 2016, and Word 2016 include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business. These Office 2016 programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="3c9d0-p164">DLP 原則評估 Office 2016 中的設計目的不會影響效能的程式或內容上使用的人員的生產力。如果他們正在處理大型文件，或使用者的電腦正在忙碌，可能需要幾秒鐘的原則提示出現。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p164">DLP policy evaluation in Office 2016 is designed not to affect the performance of the programs or the productivity of people working on content. If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>
  
## <a name="permissions"></a><span data-ttu-id="3c9d0-420">權限</span><span class="sxs-lookup"><span data-stu-id="3c9d0-420">Permissions</span></span>

<span data-ttu-id="3c9d0-p165">會建立 DLP 原則規範小組成員需要安全性權限&amp;規範中心。根據預設，您的租用戶系統管理員將具有此位置的存取並可授與法務人員及其他人存取安全性&amp;規範中心，但不授與之所有權限的租用戶管理]。若要這樣做，我們建議您：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p165">Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="3c9d0-423">在 Office 365 中建立一個群組，並將法務人員新增至此群組。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-423">Create a group in Office 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="3c9d0-424">建立角色群組的安全性**權限**] 頁面上&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-424">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 
    
3. <span data-ttu-id="3c9d0-425">將 Office 365 群組新增至此角色群組。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-425">Add the Office 365 group to the role group.</span></span>
    
<span data-ttu-id="3c9d0-426">如需詳細資訊，請參閱[Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-426">For more information, see [Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="3c9d0-p166">需要這些權限才能建立及套用 DLP 原則。原則強制執行不需要內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p166">These permissions are required only to create and apply a DLP policy. Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="3c9d0-429">尋找 DLP 指令程式</span><span class="sxs-lookup"><span data-stu-id="3c9d0-429">Find the DLP cmdlets</span></span>

<span data-ttu-id="3c9d0-430">若要使用大部分的指令程式以安全性&amp;規範中心，您必須：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-430">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="3c9d0-431">使用遠端 PowerShell 連線到 Office 365 安全性與合規性中心</span><span class="sxs-lookup"><span data-stu-id="3c9d0-431">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="3c9d0-432">使用下列任何一這些[Office 365 安全性&amp;規範中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="3c9d0-432">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="3c9d0-p167">不過，DLP 報告需要跨 Office 365，包括 Exchange Online 提取資料。有此原因的 DLP 報告指令程式可用在 Exchange Online Powershell-不在安全性&amp;規範中心 Powershell。因此，若要使用 DLP 報告指令程式，您需要：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-p167">However, DLP reports need pull data from across Office 365, including Exchange Online. For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell. Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="3c9d0-436">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3c9d0-436">Connect to Exchange Online using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="3c9d0-437">使用這些 cmdlet 的任何 DLP 報告：</span><span class="sxs-lookup"><span data-stu-id="3c9d0-437">Use any of these cmdlets for the DLP reports:</span></span>
    
  - [<span data-ttu-id="3c9d0-438">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="3c9d0-438">Get-DlpDetectionsReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
  - [<span data-ttu-id="3c9d0-439">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="3c9d0-439">Get-DlpDetailReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    
## <a name="more-information"></a><span data-ttu-id="3c9d0-440">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="3c9d0-440">More information</span></span>

- [<span data-ttu-id="3c9d0-441">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="3c9d0-441">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="3c9d0-442">針對 DLP 原則傳送通知並顯示原則提示</span><span class="sxs-lookup"><span data-stu-id="3c9d0-442">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="3c9d0-443">建立 DLP 原則來保護具有 FCI 或其他屬性的文件</span><span class="sxs-lookup"><span data-stu-id="3c9d0-443">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="3c9d0-444">DLP 原則範本包含哪些內容</span><span class="sxs-lookup"><span data-stu-id="3c9d0-444">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="3c9d0-445">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="3c9d0-445">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="3c9d0-446">DLP 功能所尋找的項目</span><span class="sxs-lookup"><span data-stu-id="3c9d0-446">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="3c9d0-447">建立自訂的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="3c9d0-447">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    

