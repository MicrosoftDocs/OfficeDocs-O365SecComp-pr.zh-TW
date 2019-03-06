---
title: 資料外洩防護原則概觀
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MET150
description: 使用 Office 365 安全性中的資料外洩防護 (DLP) 原則&amp;合規性中心，您可以識別、 監視和自動保護 Office 365 中的敏感資訊。
ms.openlocfilehash: 53f9e3b4fca296c35d4c07b912a9bd1d41e62fc8
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410868"
---
# <a name="overview-of-data-loss-prevention-policies"></a><span data-ttu-id="e8f8f-103">資料外洩防護原則概觀</span><span class="sxs-lookup"><span data-stu-id="e8f8f-103">Overview of data loss prevention policies</span></span>

<span data-ttu-id="e8f8f-104">為了符合企業標準和產業規定，組織必須保護敏感資訊並防止意外洩漏。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-104">To comply with business standards and industry regulations, organizations need to protect sensitive information and prevent its inadvertent disclosure.</span></span> <span data-ttu-id="e8f8f-105">舉例來說，您想要防止洩漏到組織外的敏感資訊，可能包括財務資料或個人識別資訊 (PII)，例如信用卡號碼、身分證字號或健康記錄等。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-105">Examples of sensitive information that you might want to prevent from leaking outside your organization include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records.</span></span> <span data-ttu-id="e8f8f-106">使用 Office 365 安全性中的資料外洩防護 (DLP) 原則&amp;合規性中心，您可以識別、 監視和自動保護 Office 365 中的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-106">With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.</span></span>
  
<span data-ttu-id="e8f8f-107">採用 DLP 原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-107">With a DLP policy, you can:</span></span>
  
- <span data-ttu-id="e8f8f-108">**識別許多不同的位置，例如 Exchange Online、 SharePoint Online 和商務用 OneDrive 的敏感資訊。**</span><span class="sxs-lookup"><span data-stu-id="e8f8f-108">**Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, and OneDrive for Business.**</span></span>
    
    <span data-ttu-id="e8f8f-109">例如，您可以識別任何含有任何 OneDrive for Business 網站中儲存的信用卡卡號的文件，或您可以監視 OneDrive 網站的特定對象。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-109">For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.</span></span>
    
- <span data-ttu-id="e8f8f-110">**防止意外共用敏感資訊**。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-110">**Prevent the accidental sharing of sensitive information**.</span></span> 
    
    <span data-ttu-id="e8f8f-111">例如，您可以識別任何文件或電子郵件包含與組織外部人員共用的健康記錄並再自動封鎖存取該文件或封鎖傳送的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-111">For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.</span></span>
    
- <span data-ttu-id="e8f8f-112">**監視和保護 Excel 2016、PowerPoint 2016 和 Word 2016 桌面版中的敏感資訊。**</span><span class="sxs-lookup"><span data-stu-id="e8f8f-112">**Monitor and protect sensitive information in the desktop versions of Excel 2016, PowerPoint 2016, and Word 2016.**</span></span>
    
    <span data-ttu-id="e8f8f-113">就像在 Exchange Online、 SharePoint Online 和商務用 OneDrive，這些 Office 2016 桌面程式包含的相同功能，以識別機密資訊，並套用 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-113">Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office 2016 desktop programs include the same capabilities to identify sensitive information and apply DLP policies.</span></span> <span data-ttu-id="e8f8f-114">DLP 可在多人共用這些 Office 2016 程式中的內容時提供持續監視的功能。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-114">DLP provides continuous monitoring when people share content in these Office 2016 programs.</span></span>
    
- <span data-ttu-id="e8f8f-115">**協助使用者了解如何符合規範，而不中斷其工作流程。**</span><span class="sxs-lookup"><span data-stu-id="e8f8f-115">**Help users learn how to stay compliant without interrupting their workflow.**</span></span>
    
    <span data-ttu-id="e8f8f-116">您可以讓使用者了解 DLP 原則，協助他們符合規範，而不會封鎖其工作。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-116">You can educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="e8f8f-117">例如，如果某個使用者嘗試共用含有敏感資訊的文件，DLP 原則可以傳送電子郵件通知給他們，同時在文件庫的內容中顯示原則提示，允許他們因為正當商務理由而覆寫原則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-117">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span> <span data-ttu-id="e8f8f-118">相同的原則提示也會出現在 Outlook web、 Outlook 2013 和更新版本，Excel 2016、 PowerPoint 2016 和 Word 2016。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-118">The same policy tips also appear in Outlook on the web, Outlook 2013 and later, Excel 2016, PowerPoint 2016, and Word 2016.</span></span>
    
- <span data-ttu-id="e8f8f-119">**檢視 DLP 報告以瞭解有哪些內容符合貴組織的 DLP 原則。**</span><span class="sxs-lookup"><span data-stu-id="e8f8f-119">**View DLP reports showing content that matches your organization's DLP policies.**</span></span>
    
    <span data-ttu-id="e8f8f-120">若要評估您的組織遵守 DLP 原則的程度，您可以查看每一個原則和規則在一段時間內有多少個相符項目。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-120">To assess how your organization is complying with a DLP policy, you can see how many matches each policy and rule has over time.</span></span> <span data-ttu-id="e8f8f-121">如果 DLP 原則允許覆寫原則提示，並報告為誤判的使用者，您也可以檢視使用者已回報。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-121">If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported.</span></span>
    
<span data-ttu-id="e8f8f-122">您建立及管理 Office 365 安全性資料遺失防護] 頁面上的 DLP 原則&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-122">You create and manage DLP policies on the Data loss prevention page in the Office 365 Security &amp; Compliance Center.</span></span>
  
![Office 365 安全性中的資料外洩防護頁面&amp;合規性中心](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a><span data-ttu-id="e8f8f-124">DLP 原則的內容</span><span class="sxs-lookup"><span data-stu-id="e8f8f-124">What a DLP policy contains</span></span>

<span data-ttu-id="e8f8f-125">DLP 原則包含一些基本事項：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-125">A DLP policy contains a few basic things:</span></span>
  
- <span data-ttu-id="e8f8f-126">若要保護的內容-**位置**例如 Exchange Online、 SharePoint Online 和 OneDrive for Business 網站的位置。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-126">Where to protect the content - **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites.</span></span> 
    
- <span data-ttu-id="e8f8f-127">何時及如何藉由執行強制包含下列要素的**規則**來保護內容：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-127">When and how to protect the content by enforcing **rules** comprised of:</span></span> 
    
  - <span data-ttu-id="e8f8f-128">**條件**會強制執行規則-之前，必須符合的內容，例如尋找僅適用於包含身分證號碼指與組織外部人員共用的內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-128">**Conditions** the content must match before the rule is enforced -- for example, look only for content containing Social Security numbers that's been shared with people outside your organization.</span></span> 
    
  - <span data-ttu-id="e8f8f-129">您要規則在找到符合條件的內容時自動採取的**動作** -- 例如封鎖文件的存取，以及傳送電子郵件通知給使用者和法務人員。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-129">**Actions** that you want the rule to take automatically when content matching the conditions is found -- for example, block access to the document and send both the user and compliance officer an email notification.</span></span> 
    
<span data-ttu-id="e8f8f-130">您可以使用規則來達到特定的保護需求，然後使用 DLP 原則將常見保護需求分組在一起，例如所有需要遵守特定法規的規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-130">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="e8f8f-131">例如，您的 DLP 原則可能協助您偵測是否存在受到健康保險流通與責任法案 (HIPAA) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-131">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA).</span></span> <span data-ttu-id="e8f8f-132">此 DLP 原則可以幫助保護所有 SharePoint Online 網站和所有 OneDrive for Business 網站 （位置） 的 HIPAA 資料 （什麼） 所尋找的任何含有與組織外部人員 (共用此敏感資訊的文件條件） 然後封鎖文件的存取，並傳送通知 （動作）。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-132">This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions).</span></span> <span data-ttu-id="e8f8f-133">這些需求會儲存為個別規則並一起分組為 DLP 原則，以簡化管理和報告。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-133">These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![圖表顯示 DLP 原則包含位置和規則](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a><span data-ttu-id="e8f8f-135">位置</span><span class="sxs-lookup"><span data-stu-id="e8f8f-135">Locations</span></span>

<span data-ttu-id="e8f8f-136">DLP 原則可以尋找和 Office 365 敏感資訊保護，是否該資訊位於 Exchange Online、 SharePoint Online 或商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-136">A DLP policy can find and protect sensitive information across Office 365, whether that information is located in Exchange Online, SharePoint Online, or OneDrive for Business.</span></span> <span data-ttu-id="e8f8f-137">您可以輕鬆選擇保護所有 SharePoint 網站或 OneDrive 帳戶，只是特定網站或帳戶或所有的信箱。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-137">You can easily choose to protect all SharePoint sites or OneDrive accounts, just specific sites or accounts, or all mailboxes.</span></span> <span data-ttu-id="e8f8f-138">請注意，它還不能以選取特定使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-138">Note that it's not yet possible to select just the mailboxes of specific users.</span></span>
  
![DLP 原則可以套用的位置選項](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
<span data-ttu-id="e8f8f-140">注意： 如果您選擇要包含或排除特定的 SharePoint 網站或 OneDrive 帳戶，DLP 原則可以包含超過 100 這類包含與排除。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-140">Note that if you choose to include or exclude specific SharePoint sites or OneDrive accounts, a DLP policy can contain no more than 100 such inclusions and exclusions.</span></span> <span data-ttu-id="e8f8f-141">雖然這項限制存在，了解您可以套用全組織原則或套用到整個組織的原則來超過此限制。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-141">Although this limit exists, understand that you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>
  
### <a name="rules"></a><span data-ttu-id="e8f8f-142">規則</span><span class="sxs-lookup"><span data-stu-id="e8f8f-142">Rules</span></span>

<span data-ttu-id="e8f8f-143">規則是什麼強制執行您的業務需求，在您的組織內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-143">Rules are what enforce your business requirements on your organization's content.</span></span> <span data-ttu-id="e8f8f-144">一項原則包含一或多個規則，而每個規則是由條件和動作所組成。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-144">A policy contains one or more rules, and each rule consists of conditions and actions.</span></span> <span data-ttu-id="e8f8f-145">對每個規則而言，條件符合時，就會自動採取動作。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-145">For each rule, when the conditions are met, the actions are taken automatically.</span></span> <span data-ttu-id="e8f8f-146">規則會依序執行，開頭中每個原則的最高優先順序規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-146">Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="e8f8f-147">規則也提供選項，以通知 （搭配原則提示和電子郵件通知） 的使用者和系統管理員 （處理電子郵件附隨報告） 的內容符合規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-147">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="e8f8f-148">在此規則的元件，每個說明如下。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-148">Here are the components of a rule, each explained below.</span></span>
  
![DLP 規則編輯器的區段](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="e8f8f-150">條件</span><span class="sxs-lookup"><span data-stu-id="e8f8f-150">Conditions</span></span>

<span data-ttu-id="e8f8f-151">條件很重要，因為它們決定何種類型的資訊您正在尋找，以及何時採取動作。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-151">Conditions are important because they determine what types of information you're looking for, and when to take an action.</span></span> <span data-ttu-id="e8f8f-152">例如，您可能會選擇要忽略內容包含護照號碼，除非內容包含此類十個以上的數字，並與組織外部人員共用。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-152">For example, you might choose to ignore content containing passport numbers unless the content contains more than ten such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="e8f8f-153">條件焦點上**的內容**，例如您要尋找的敏感資訊類型，以及**內容**，例如文件共用與人員。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-153">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with.</span></span> <span data-ttu-id="e8f8f-154">您可以使用條件來將不同的動作指派給不同風險層級 -- 例如，相較於與組織外部人員共用的敏感內容，內部共用的敏感內容風險可能較低，所需的動作也較少。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-154">You can use conditions to assign different actions to different risk levels -- for example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![清單會顯示可用的 DLP 條件](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="e8f8f-156">目前可用的條件可以判斷：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-156">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="e8f8f-157">內容包含敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-157">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="e8f8f-158">內容包含標籤。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-158">Content contains a label.</span></span> <span data-ttu-id="e8f8f-159">如需詳細資訊，請參閱以下區段 [[使用標籤作為 DLP 原則的條件](data-loss-prevention-policies.md#label)。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-159">For more information, see the below section [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#label).</span></span>
    
- <span data-ttu-id="e8f8f-160">內容是否與組織外部或內部人員共用。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-160">Content is shared with people outside or inside your organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="e8f8f-161">敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="e8f8f-161">Types of sensitive information</span></span>

<span data-ttu-id="e8f8f-162">DLP 原則可協助保護敏感資訊，指**敏感資訊類型**。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-162">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="e8f8f-163">Office 365 包含許多不同區域多種常見敏感資訊類型可供您使用，例如信用卡號碼、銀行帳戶號碼、身分證號碼和護照號碼。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-163">Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![可用的敏感資訊類型清單](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="e8f8f-165">例如信用卡號碼敏感資訊類型尋找 DLP 原則，它不會只尋找 16 位數的數字。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-165">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number.</span></span> <span data-ttu-id="e8f8f-166">使用下列各項的組合可定義和偵測每種敏感資訊類型：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-166">Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="e8f8f-167">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e8f8f-167">Keywords</span></span>
    
- <span data-ttu-id="e8f8f-168">驗證總和檢查碼或結構的內部函數</span><span class="sxs-lookup"><span data-stu-id="e8f8f-168">Internal functions to validate checksums or composition</span></span>
    
- <span data-ttu-id="e8f8f-169">用以尋找模式相符項目的規則運算式評估</span><span class="sxs-lookup"><span data-stu-id="e8f8f-169">Evaluation of regular expressions to find pattern matches</span></span>
    
- <span data-ttu-id="e8f8f-170">其他內容檢查</span><span class="sxs-lookup"><span data-stu-id="e8f8f-170">Other content examination</span></span>
    
<span data-ttu-id="e8f8f-171">這有助於 DLP 偵測達到高度準確性同時減少誤判能夠中斷 peoples 的工作數目。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-171">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="e8f8f-172">動作</span><span class="sxs-lookup"><span data-stu-id="e8f8f-172">Actions</span></span>

<span data-ttu-id="e8f8f-173">當內容符合規則的條件時，您可以套用動作以自動保護內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-173">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![可用的 DLP 動作清單](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="e8f8f-175">目前可用的動作，您可以進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-175">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="e8f8f-176">**限制內容的存取權**對於網站內容，這表示文件的權限受到限制的所有人，主要網站集合管理員、 文件擁有者和上次修改文件的人員除外。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-176">**Restrict access to the content** For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> <span data-ttu-id="e8f8f-177">這些人員可以從文件中移除敏感資訊，或採取其他補救措施。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-177">These people can remove the sensitive information from the document or take other remedial action.</span></span> <span data-ttu-id="e8f8f-178">當文件符合規範時，將會自動還原原始權限。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-178">When the document is in compliance, the original permissions will be automatically restored.</span></span> <span data-ttu-id="e8f8f-179">當文件的存取遭到封鎖時，文件在網站上的文件庫中會顯示一個特殊原則提示圖示。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-179">When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
    ![顯示文件存取的原則提示被封鎖](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    <span data-ttu-id="e8f8f-181">電子郵件內容，此巨集指令會封鎖傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-181">For email content, this action blocks the message from being sent.</span></span> <span data-ttu-id="e8f8f-182">根據 DLP 規則的設定方式，寄件者將會看到 NDR 或 （如果此規則使用通知） 的原則提示及/或電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-182">Depending on how the DLP rule is configured, the sender will see an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
    ![警告未經授權的收件者必須從郵件中移除](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="e8f8f-184">使用者通知與使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="e8f8f-184">User notifications and user overrides</span></span>

<span data-ttu-id="e8f8f-185">您可以使用通知，並且會覆寫教育使用者有關 DLP 原則，並協助他們持續相容，而不封鎖他們的工作。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-185">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="e8f8f-186">例如，如果某個使用者嘗試共用含有敏感資訊的文件，DLP 原則可以傳送電子郵件通知給他們，同時在文件庫的內容中顯示原則提示，允許他們因為正當商務理由而覆寫原則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-186">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![使用者通知與使用者會覆寫 DLP 規則編輯器的區段](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="e8f8f-188">電子郵件可以通知傳送、 共用，或上次修改的內容和，網站內容、 主要網站集合管理員及文件擁有者的人員。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-188">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner.</span></span> <span data-ttu-id="e8f8f-189">此外，您可以新增或移除任何一個您選擇從電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-189">In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="e8f8f-190">除了傳送電子郵件通知，使用者所顯示的通知原則提示：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-190">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="e8f8f-191">在 Outlook 2013 和更新版本及 outlook 網頁版。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-191">In Outlook 2013 and later and Outlook on the web.</span></span>
    
- <span data-ttu-id="e8f8f-192">文件上的 SharePoint Online 或 OneDrive for Business 網站。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-192">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="e8f8f-193">在 Excel 2016、 PowerPoint 2016 和 Word 2016 中，當文件儲存在網站上包含在 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-193">In Excel 2016, PowerPoint 2016, and Word 2016, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="e8f8f-194">電子郵件通知和原則提示說明內容與 DLP 原則的衝突的原因。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-194">The email notification and policy tip explain why content conflicts with a DLP policy.</span></span> <span data-ttu-id="e8f8f-195">經選擇後，電子郵件通知和原則提示將可讓使用者藉由回報為誤判或提供正當業務理由來覆寫規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-195">If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification.</span></span> <span data-ttu-id="e8f8f-196">這可協助您將 DLP 原則正確的相關資訊傳達給使用者，並強制執行這些原則而不會妨礙到其正常工作。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-196">This can help you educate users about your DLP policies and enforce them without preventing people from doing their work.</span></span> <span data-ttu-id="e8f8f-197">覆寫及誤判的相關資訊也會記錄並回報 (請參閱以下關於 DLP 報告的資訊)，並納入事件報告中 (下一節)，以便法務人員可以定期檢閱此資訊。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-197">Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="e8f8f-198">以下是什麼原則提示看起來像在 OneDrive 商務帳戶。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-198">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![在 OneDrive 帳戶中的文件的原則提示](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a><span data-ttu-id="e8f8f-200">事件報告</span><span class="sxs-lookup"><span data-stu-id="e8f8f-200">Incident reports</span></span>

<span data-ttu-id="e8f8f-201">時於符合規則，您可以傳送給您的法務 （或任何您選擇的人員） 附隨報告與事件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-201">When a rule is matched, you can send an incident report to your compliance officer (or any people you choose) with details of the event.</span></span> <span data-ttu-id="e8f8f-202">此報告中包含的項目相符，實際內容符合規則，以及上次修改內容的人員名稱的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-202">This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content.</span></span> <span data-ttu-id="e8f8f-203">對於電子郵件，報告也包括附件形式原始郵件符合 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-203">For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>
  
![設定事件報告的頁面](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="e8f8f-205">分組和邏輯運算子</span><span class="sxs-lookup"><span data-stu-id="e8f8f-205">Grouping and logical operators</span></span>

<span data-ttu-id="e8f8f-206">通常您的 DLP 原則具有簡單的需求，例如找出包含美國社會安全號碼的所有內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-206">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number.</span></span> <span data-ttu-id="e8f8f-207">不過，在其他情況下，您的 DLP 原則可能需要以識別定義多鬆散資料。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-207">However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="e8f8f-208">例如，若要識別內容受到美國健康保險法案 (HIPAA)，您需要尋找：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-208">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="e8f8f-209">包含特定類型的敏感資訊，例如美國社會安全號碼或藥物執法機構 (DEA) 編號的內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-209">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="e8f8f-210">AND</span><span class="sxs-lookup"><span data-stu-id="e8f8f-210">AND</span></span>
    
- <span data-ttu-id="e8f8f-211">內容是更容易識別，例如溝通關於病患照護或醫療服務提供的說明。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-211">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided.</span></span> <span data-ttu-id="e8f8f-212">用於識別此內容需要比對關鍵字非常大型的關鍵字清單，例如國際分類的治療法 （ICD-9-CM 或 ICD-10-CM）。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-212">Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="e8f8f-213">您輕鬆地可以使用群組及邏輯運算子 (AND、 OR) 來識別此類鬆散已定義的資料。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-213">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR).</span></span> <span data-ttu-id="e8f8f-214">當您建立的 DLP 原則時，您可以：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-214">When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="e8f8f-215">群組敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-215">Group sensitive information types.</span></span>
    
- <span data-ttu-id="e8f8f-216">選擇 [自己的群組和群組內的機密資訊類型之間的邏輯運算子。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-216">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="e8f8f-217">選擇群組內的運算子</span><span class="sxs-lookup"><span data-stu-id="e8f8f-217">Choosing the operator within a group</span></span>

<span data-ttu-id="e8f8f-218">在群組中，您可以選擇是否任一或所有該群組中的條件必須滿足符合規則的內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-218">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![顯示群組內的運算子的群組](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="e8f8f-220">新增群組</span><span class="sxs-lookup"><span data-stu-id="e8f8f-220">Adding a group</span></span>

<span data-ttu-id="e8f8f-221">您可以快速地加入群組，其中可以有自己的條件與該群組內的運算子。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-221">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![新增群組] 按鈕](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="e8f8f-223">選擇群組之間的運算子</span><span class="sxs-lookup"><span data-stu-id="e8f8f-223">Choosing the operator between groups</span></span>

<span data-ttu-id="e8f8f-224">之間群組，您可以選擇是否必須符合規則的內容符合中只有一個群組或群組的所有條件。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-224">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="e8f8f-225">例如，內建的**美國 HIPAA**原則已使用**AND**運算子群組之間，使它會識別包含內容的規則：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-225">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="e8f8f-226">從群組**PII 識別碼**（至少一個 SSN 號碼**或**DEA 號碼）</span><span class="sxs-lookup"><span data-stu-id="e8f8f-226">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="e8f8f-227">**AND**</span><span class="sxs-lookup"><span data-stu-id="e8f8f-227">**AND**</span></span>
    
- <span data-ttu-id="e8f8f-228">從群組**醫療字詞**（至少一個 ICD-9-CM 關鍵字**或**的 ICD-10-CM 關鍵字）</span><span class="sxs-lookup"><span data-stu-id="e8f8f-228">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![顯示群組之間的運算子的群組](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="e8f8f-230">依據處理規則優先順序</span><span class="sxs-lookup"><span data-stu-id="e8f8f-230">The priority by which rules are processed</span></span>

<span data-ttu-id="e8f8f-231">當您在原則建立規則時，每個規則被指派優先順序，它會建立的順序-也就是說，建立的規則首先有第一優先，第二個建立的規則有第二個優先順序，依此類推。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-231">When you create rules in a policy, each rule is assigned a priority in the order in which it's created - meaning, the rule created first has first priority, the rule created second has second priority, and so on.</span></span> <span data-ttu-id="e8f8f-232">建立規則之後，就無法變更其優先順序，除非藉由刪除並重新建立它。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-232">After you create a rule, its priority can't be changed, except by deleting and re-creating it.</span></span>
  
![依優先順序的規則](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
<span data-ttu-id="e8f8f-234">根據規則評估內容時，這些規則會處理依優先順序。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-234">When content is evaluated against rules, the rules are processed in priority order.</span></span> <span data-ttu-id="e8f8f-235">如果內容符合多個規則，這些規則會處理依優先順序，並強制執行的最嚴格的巨集指令。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-235">If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced.</span></span> <span data-ttu-id="e8f8f-236">例如，如果內容符合所有下列規則，規則 3 已強制執行因為它是最高優先順序、 最嚴格規則：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-236">For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="e8f8f-237">規則 1： 僅通知使用者</span><span class="sxs-lookup"><span data-stu-id="e8f8f-237">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="e8f8f-238">規則 2： 通知使用者，限制存取權，並允許使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="e8f8f-238">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="e8f8f-239">規則 3： 通知使用者，限制存取權，並不允許使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="e8f8f-239">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="e8f8f-240">規則 4： 僅通知使用者</span><span class="sxs-lookup"><span data-stu-id="e8f8f-240">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="e8f8f-241">規則 5： 限制存取</span><span class="sxs-lookup"><span data-stu-id="e8f8f-241">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="e8f8f-242">規則 6： 通知使用者，限制存取權，並不允許使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="e8f8f-242">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="e8f8f-243">在這個範例中，請注意，針對所有規則相符項目會記錄在稽核記錄中 DLP 報告，顯示即使最嚴格規則會強制執行。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-243">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="e8f8f-244">關於原則提示，請注意:</span><span class="sxs-lookup"><span data-stu-id="e8f8f-244">With respect to policy tips, note that:</span></span>
  
- <span data-ttu-id="e8f8f-245">僅限的原則提示從最高的優先順序，將會顯示最嚴格規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-245">Only the policy tip from the highest priority, most restrictive rule will be shown.</span></span> <span data-ttu-id="e8f8f-246">例如，原則提示從一個規則，透過從一個規則，只會傳送通知原則提示也會顯示封鎖內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-246">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="e8f8f-247">這可防止人員看到 cascade 的原則提示。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-247">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="e8f8f-248">如果中的原則提示最嚴格規則允許人員覆寫規則，則覆寫此規則也會覆寫任何其他內容符合的規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-248">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="e8f8f-249">調整規則，以使其更容易或難符合</span><span class="sxs-lookup"><span data-stu-id="e8f8f-249">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="e8f8f-250">人員建立並開啟其 DLP 原則之後，他們有時遇到下列問題：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-250">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="e8f8f-251">**不是**敏感資訊比對規則-換句話說，太多誤判太多內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-251">Too much content that **is not** sensitive information matches the rules - in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="e8f8f-252">**敏感資訊**比對規則-換句話說，而不被強制執行動作的敏感資訊為基礎的太少內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-252">Too little content that **is** sensitive information matches the rules - in other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="e8f8f-253">若要解決這些問題，您可以藉由調整的執行個體計數調整您的規則，並比對正確性，使其更困難或更容易以符合規則的內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-253">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules.</span></span> <span data-ttu-id="e8f8f-254">規則中使用每個敏感資訊類型都有兩個執行個體計數和比對正確性。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-254">Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="e8f8f-255">執行個體計數</span><span class="sxs-lookup"><span data-stu-id="e8f8f-255">Instance count</span></span>

<span data-ttu-id="e8f8f-256">執行個體計數只表示的特定類型的敏感資訊的多少項目必須要有符合規則的內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-256">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule.</span></span> <span data-ttu-id="e8f8f-257">例如，內容會比對規則，如下所示介於 1 到 9 之間的 if 唯一美國或英國</span><span class="sxs-lookup"><span data-stu-id="e8f8f-257">For example, content will match the rule shown below if between 1 and 9 unique U.S. or U.K.</span></span> <span data-ttu-id="e8f8f-258">識別護照號碼。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-258">passport numbers are identified.</span></span>
  
<span data-ttu-id="e8f8f-259">請注意執行個體計數包含只敏感資訊類型和關鍵字**唯一**相符項目。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-259">Note that the instance count includes only **unique** matches for sensitive information types and keywords.</span></span> <span data-ttu-id="e8f8f-260">例如，如果電子郵件包含相同的信用卡號碼的 10 個項目，這些 10 個項目就會視為信用卡號碼的單一執行個體。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-260">For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span> 
  
<span data-ttu-id="e8f8f-261">若要使用執行個體計數調整規則，本指南很簡單：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-261">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="e8f8f-262">若要讓規則來比對更容易，減少**最小**計數和/或增加的**最大**計數。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-262">To make the rule easier to match, decrease the **min** count and/or increase the **max** count.</span></span> <span data-ttu-id="e8f8f-263">您也可以設定**最大\*\*\*\*任何**要刪除的數值。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-263">You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="e8f8f-264">若要更難符合規則，請增加 [**最小**計數。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-264">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="e8f8f-265">一般而言，您可以使用限制較少的動作，例如將使用者通知傳送中具有較低的執行個體計數 (例如，1-9) 的規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-265">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9).</span></span> <span data-ttu-id="e8f8f-266">並使用更嚴格的動作，例如限制內容的存取，而不讓使用者覆寫，在具有較高的執行個體計數 （例如 10 任何） 的規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-266">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![在規則編輯器中的執行個體計數](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="e8f8f-268">比對正確性</span><span class="sxs-lookup"><span data-stu-id="e8f8f-268">Match accuracy</span></span>

<span data-ttu-id="e8f8f-269">如前所述，敏感資訊類型定義，及使用不同類型的辨識項的組合來偵測。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-269">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence.</span></span> <span data-ttu-id="e8f8f-270">通常，敏感資訊類型被定義多個這類組合，稱為模式。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-270">Commonly, a sensitive information type is defined by multiple such combinations, called patterns.</span></span> <span data-ttu-id="e8f8f-271">需要較少證據的模式具有較低的比對正確性 （或 [信賴等級） 時需要更多辨識來具有較高的比對正確性 （或信賴等級） 的模式。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-271">A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level).</span></span> <span data-ttu-id="e8f8f-272">若要深入了解每個敏感資訊類型所使用的信賴等級與實際的模式，請參閱[敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-272">To learn more about the actual patterns and confidence levels used by every sensitive information type, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
<span data-ttu-id="e8f8f-273">例如，名為信用卡號碼敏感資訊類型會定義兩種模式：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-273">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="e8f8f-274">需要的 65%信賴模式：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-274">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="e8f8f-275">信用卡號碼的號碼格式。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-275">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="e8f8f-276">通過總和檢查碼數目。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-276">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="e8f8f-277">需要的 85%信賴模式：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-277">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="e8f8f-278">信用卡號碼的號碼格式。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-278">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="e8f8f-279">通過總和檢查碼數目。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-279">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="e8f8f-280">關鍵字或到期日的正確格式。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-280">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="e8f8f-281">您可以使用這些信賴等級 （或比對正確性） 中您的規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-281">You can use these confidence levels (or match accuracy) in your rules.</span></span> <span data-ttu-id="e8f8f-282">一般而言，您可以使用限制較少的動作，例如將使用者通知傳送中具有較低的比對正確性的規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-282">Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy.</span></span> <span data-ttu-id="e8f8f-283">並使用更嚴格的動作，例如限制內容的存取，而不讓使用者覆寫，在具有較高的比對正確性的規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-283">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="e8f8f-284">請務必了解當特定類型的敏感資訊，例如信用卡號碼，且識別內容中，會傳回只有單一信賴等級：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-284">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="e8f8f-285">如果所有的相符項目都是單一的模式，則會傳回該模式的信賴等級。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-285">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="e8f8f-286">如果有多個模式比對的比對 （亦即，有兩個不同的信賴等級的相符項目），則會傳回高於任何單獨的單一模式的信賴等級。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-286">If there are matches for more than one pattern (i.e., there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned.</span></span> <span data-ttu-id="e8f8f-287">這是麻煩的部分。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-287">This is the tricky part.</span></span> <span data-ttu-id="e8f8f-288">例如，如信用卡、 65%和 85%模式都符合，如果信賴等級傳回敏感資訊類型是大於 90%，因為更多辨識來表示更多的信賴度。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-288">For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="e8f8f-289">因此如果您想要建立這兩個是互斥的規則，如信用卡、 一個用於 65%比對正確性，一個用於 85%比對正確性，比對正確性的範圍看起來像這樣。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-289">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this.</span></span> <span data-ttu-id="e8f8f-290">第一個規則挑選只比對的 65%圖樣。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-290">The first rule picks up only matches of the 65% pattern.</span></span> <span data-ttu-id="e8f8f-291">第二個規則可以挑選符合與**至少一個**85%相符項目**可能有**其他較低信賴相符項目。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-291">The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![兩個規則的比對正確性不同範圍](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="e8f8f-293">基於這些理由，是使用不同的相符項目精確度建立規則的指引：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-293">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="e8f8f-294">最低信賴等級通常會使用**min**和**max** （不提供範圍） 的相同的值。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-294">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="e8f8f-295">最高的信賴等級通常是，範圍從較低的信賴等級的正上方到 100。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-295">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="e8f8f-296">任何中間的信賴等級通常介於正上方低信賴等級來剛下方的較高的信賴等級。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-296">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="e8f8f-297">使用標籤做為 DLP 原則的條件</span><span class="sxs-lookup"><span data-stu-id="e8f8f-297">Using a label as a condition in a DLP policy</span></span>

<span data-ttu-id="e8f8f-298">您可以建立標籤，然後：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-298">You can create a label and then:</span></span>
  
- <span data-ttu-id="e8f8f-299">**發佈**，以便使用者可看見並以手動方式將標籤套用到內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-299">**Publish** it, so that end users can see and manually apply the label to content.</span></span> 
    
- <span data-ttu-id="e8f8f-300">它的內容符合您選擇的條件時**自動套用**。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-300">**Auto-apply** it to content that matches the conditions that you choose.</span></span> 
    
<span data-ttu-id="e8f8f-301">如需標籤的詳細資訊，請參閱 < <b0>Overview of 保留標籤</b0>。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-301">For more information about labels, see [Overview of retention labels](labels.md).</span></span>
  
<span data-ttu-id="e8f8f-302">建立標籤之後，然後在您的 DLP 原則中使用該標籤做為條件。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-302">After you create a label, you can then use that label as a condition in your DLP policies.</span></span> <span data-ttu-id="e8f8f-303">例如，您可能想要這麼做，因為：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-303">For example, you might want to do this because:</span></span>
  
- <span data-ttu-id="e8f8f-304">您發佈標籤名為 2 私人 3**機密文件**，以便您組織中的人員可以手動將標籤套用至機密電子郵件和文件。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-304">You published a label named **Confidential**, so that people in your organization can manually apply the label to confidential email and documents.</span></span> <span data-ttu-id="e8f8f-305">使用此標籤作為 DLP 原則的條件，您可以限制標示**2 私人 3 機密**與組織外部人員共用的內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-305">By using this label as a condition in your DLP policy, you can restrict content labeled **Confidential** from being shared with people outside your organization.</span></span> 
    
- <span data-ttu-id="e8f8f-306">您建立名為**高山屋**該名稱的專案的標籤，且然後此標籤自動套用到包含關鍵字"高山 House"的內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-306">You created a label named **Alpine House** for a project of that name, and then applied that label automatically to content containing the keywords "Alpine House".</span></span> <span data-ttu-id="e8f8f-307">藉由使用此標籤作為 DLP 原則中的條件，您可以顯示原則提示使用者即將要與組織外部人員共用此內容時，可。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-307">By using this label as a condition in your DLP policy, you can show a policy tip to end users when they're about to share this content with someone outside your organization.</span></span> 
    
- <span data-ttu-id="e8f8f-308">您發佈標籤名為**稅務記錄**，以便記錄管理員可以手動將標籤套用至需要分類為記錄的內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-308">You published a label named **Tax record**, so that your records manager can manually apply the label to content that needs to be classified as a record.</span></span> <span data-ttu-id="e8f8f-309">使用此標籤作為 DLP 原則的條件，您可以查看有搭配其他類型的敏感資訊，例如 ITINs 或 Ssn; 此標籤的內容將保護動作套用到內容標示為**稅務記錄**;取得關於 DLP 原則的詳細的活動報告中的 DLP 報告並稽核記錄資料。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-309">By using this label as a condition in your DLP policy, you can look for content with this label in conjunction with other types of sensitive information such as ITINs or SSNs; apply protection actions to content labeled **Tax record**; and get detailed activity reports about the DLP policy from the DLP reports and audit log data.</span></span> 
    
- <span data-ttu-id="e8f8f-310">您發佈至 Exchange 信箱和主管群組中的 OneDrive 帳戶名為**高階主管的領導團隊-機密**的標籤。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-310">You published a label named **Executive Leadership Team - Sensitive** to the Exchange mailboxes and OneDrive accounts of a group of executives.</span></span> <span data-ttu-id="e8f8f-311">使用此標籤作為 DLP 原則的條件，您可以強制保留和保護動作在相同的子集合的內容和使用者。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-311">By using this label as a condition in your DLP policy, you can enforce both retention and protection actions on the same subset of content and users.</span></span> 
    
<span data-ttu-id="e8f8f-312">使用標籤做為在您的 DLP 規則條件，可以您選擇性地強制執行一組特定的內容、 位置或使用者保護動作。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-312">By using labels as a condition in your DLP rules, can you selectively enforce protection actions on a specific set of content, locations, or users.</span></span>
  
![做為條件的標籤](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

### <a name="support-for-sensitivity-labels-is-coming"></a><span data-ttu-id="e8f8f-314">即將敏感度標籤的支援</span><span class="sxs-lookup"><span data-stu-id="e8f8f-314">Support for sensitivity labels is coming</span></span>

<span data-ttu-id="e8f8f-315">請注意，您可以做為條件，而不是[敏感度標籤](sensitivity-labels.md)，目前使用只保留標籤。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-315">Note that you can currently use only a retention label as a condition, not a [sensitivity label](sensitivity-labels.md).</span></span> <span data-ttu-id="e8f8f-316">我們目前正在使用敏感度標籤在這種情況的支援。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-316">We're currently working on support for using a sensitivity label in this condition.</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="e8f8f-317">這項功能與其他功能關聯的方式</span><span class="sxs-lookup"><span data-stu-id="e8f8f-317">How this feature relates to other features</span></span>

<span data-ttu-id="e8f8f-318">許多功能可以套用至包含敏感資訊的內容：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-318">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="e8f8f-319">[保留標籤](labels.md#applying-a-retention-label-automatically-based-on-conditions)和[保留原則](retention-policies.md)兩者都可以強制執行此內容的**保留**動作。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-319">A [retention label](labels.md#applying-a-retention-label-automatically-based-on-conditions) and a [retention policy](retention-policies.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="e8f8f-320">DLP 原則可以強制執行此內容的**保護**動作。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-320">A DLP policy can enforce **protection** actions on this content.</span></span> <span data-ttu-id="e8f8f-321">且之前強制執行這些動作，DLP 原則可能需要其他條件以符合除了包含標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-321">And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![功能可以套用至敏感資訊的圖表](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="e8f8f-323">請注意，DLP 原則比標籤或保留原則套用至敏感資訊的更豐富偵測功能。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-323">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information.</span></span> <span data-ttu-id="e8f8f-324">DLP 原則可以強制執行內容包含敏感資訊的保護措施，以及如果敏感資訊會移除內容，這些防護動作都復原的內容掃描下一次。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-324">A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned.</span></span> <span data-ttu-id="e8f8f-325">但如果保留原則或標籤套用至包含敏感資訊的內容，即使移除機密資訊的無法復原一次性巨集指令。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-325">But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information's removed.</span></span>
  
<span data-ttu-id="e8f8f-326">使用標籤作為 DLP 原則的條件，您可以強制保留和保護的動作，以該標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-326">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label.</span></span> <span data-ttu-id="e8f8f-327">您可以將內容包含包含敏感資訊的內容完全一樣的標籤-標籤和敏感資訊類型是用來分類內容，以便您可以強制執行動作會在內容上的內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-327">You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![使用標籤做為條件的 DLP 原則的圖表](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="e8f8f-329">簡單的設定與進階設定</span><span class="sxs-lookup"><span data-stu-id="e8f8f-329">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="e8f8f-330">當您建立的 DLP 原則時，您將會選擇之間簡單] 或 [進階] 設定：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-330">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="e8f8f-331">**簡單的設定**可以輕鬆建立 DLP 原則的最常見的類型，而不使用規則編輯器來建立或修改的規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-331">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="e8f8f-332">**進階設定**可用於在規則編輯器讓您每項設定 DLP 原則的完整控制權。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-332">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="e8f8f-333">別擔心，實際上，簡單的設定和進階的設定的運作方式完全相同，藉由執行強制以下組成的條件和動作-僅使用簡單的設定規則，您沒有看到規則編輯器。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-333">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions -- only with simple settings, you don't see the rule editor.</span></span> <span data-ttu-id="e8f8f-334">它是建立 DLP 原則快速方法。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-334">It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="e8f8f-335">簡單的設定</span><span class="sxs-lookup"><span data-stu-id="e8f8f-335">Simple settings</span></span>

<span data-ttu-id="e8f8f-336">到目前為止，最常見的 DLP 案例建立原則以協助保護與外部組織，並採取自動的補救動作，例如限制可以存取內容的人員共用的內容包含敏感資訊傳送使用者或系統管理員通知及稽核更新調查的事件。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-336">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remedial action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation.</span></span> <span data-ttu-id="e8f8f-337">人員使用 DLP 以防止意外洩漏的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-337">People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="e8f8f-338">為了簡化達成此目的，當您建立的 DLP 原則時，您可以選擇**使用簡單的設定**。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-338">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**.</span></span> <span data-ttu-id="e8f8f-339">這些設定可提供您需要實作最常見的 DLP 原則，而不必在規則編輯器而進入的所有項目。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-339">These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![DLP 簡單和進階設定選項](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="e8f8f-341">進階設定</span><span class="sxs-lookup"><span data-stu-id="e8f8f-341">Advanced settings</span></span>

<span data-ttu-id="e8f8f-342">如果您需要建立更多自訂的 DLP 原則，您可以選擇**使用進階設定]**。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-342">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="e8f8f-343">進階的設定為您提供規則編輯器，其中具有完整控制權每個可能的選項，包括執行個體計數和比對正確性 （信賴等級） 為每個規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-343">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="e8f8f-344">若要快速跳至] 區段中，按一下上方導覽列中的規則編輯器]，以移至下該區段中的項目。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-344">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![DLP 規則編輯器的上方導覽功能表](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="e8f8f-346">DLP 原則範本</span><span class="sxs-lookup"><span data-stu-id="e8f8f-346">DLP policy templates</span></span>

<span data-ttu-id="e8f8f-347">建立 DLP 原則的第一個步驟選擇要保護的資訊。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-347">The first step in creating a DLP policy is choosing what information to protect.</span></span> <span data-ttu-id="e8f8f-348">開始使用 DLP 範本，您可以儲存建置一組新的規則從頭，並找出哪些類型的資訊應該包含預設的工作。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-348">By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default.</span></span> <span data-ttu-id="e8f8f-349">然後，您可以新增至，或修改這些需求來微調規則，以符合貴組織的特定需求。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-349">You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="e8f8f-350">預先設定的 DLP 原則範本可協助您偵測特定類型的敏感資訊，例如 HIPAA 資料、 PCI-DSS 資料、 Gramm-leach-bliley 金融服務業現代化法案資料或甚至是特定地區設定個人識別資訊 (P.I.)。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-350">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.).</span></span> <span data-ttu-id="e8f8f-351">為了讓您能輕鬆地尋找並保護常見的敏感資訊類型，Office 365 中包含的原則範本納入了最常見的敏感資訊類型，讓您快速著手使用。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-351">To make it easy for you to find and protect common types of sensitive information, the policy templates included in Office 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![資料外洩防護原則的範本清單，重點在於針對美國的範本愛國者法案](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="e8f8f-353">您的組織可能也有它自己的特定需求，這時您可以從頭開始建立 DLP 原則藉由選擇 [**自訂原則**] 選項。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-353">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option.</span></span> <span data-ttu-id="e8f8f-354">自訂原則是空的而且包含任何預設的規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-354">A custom policy is empty and contains no premade rules.</span></span> 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a><span data-ttu-id="e8f8f-355">以測試模式逐漸推出 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="e8f8f-355">Roll out DLP policies gradually with test mode</span></span>

<span data-ttu-id="e8f8f-356">建立 DLP 原則時，您應考慮逐漸推出這些原則，以便在完全強制執行之前評估其影響及測試其效果。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-356">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them.</span></span> <span data-ttu-id="e8f8f-357">例如，您不想要不小心封鎖存取數千名人員需要存取權，才能完成其工作的文件的新 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-357">For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.</span></span>
  
<span data-ttu-id="e8f8f-358">如果您正在建立 DLP 原則與重大影響，建議下列順序：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-358">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="e8f8f-359">**在不搭配原則提示就測試模式中的啟動**，然後使用 DLP 報告，以及任何附隨報告來評估影響。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-359">**Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact.</span></span> <span data-ttu-id="e8f8f-360">您可以使用 DLP 報告來檢視原則相符項目的號碼、位置、類型和嚴重性。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-360">You can use DLP reports to view the number, location, type, and severity of policy matches.</span></span> <span data-ttu-id="e8f8f-361">根據結果，您可以視需要微調規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-361">Based on the results, you can fine tune the rules as needed.</span></span> <span data-ttu-id="e8f8f-362">在測試模式中，DLP 原則不會影響您的組織中工作人員的生產力。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-362">In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
2. <span data-ttu-id="e8f8f-p152">**移至測試模式並顯示通知和原則提示**，以便您開始教導使用者相關規範原則及熟悉即將套用的規則。在這個階段，您也可以要求使用者回報誤判，以便您進一步調整規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-p152">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span> 
    
3. <span data-ttu-id="e8f8f-365">**開始完整強制執行原則**，使套用規則中的動作和內容的保護。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-365">**Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected.</span></span> <span data-ttu-id="e8f8f-366">繼續監視 DLP 報告以及任何事件報告或通知，確保得到您想要的結果。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-366">Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
![使用測試模式和開啟原則的選項](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
<span data-ttu-id="e8f8f-368">您可以隨時關 DLP 原則，這會影響原則中的所有規則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-368">You can turn off a DLP policy at any time, which affects all rules in the policy.</span></span> <span data-ttu-id="e8f8f-369">不過，每個規則可以也會關閉個別切換在規則編輯器中的其狀態。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-369">However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>
  
![在原則中關閉規則的選項](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)
  
## <a name="dlp-reports"></a><span data-ttu-id="e8f8f-371">DLP 報告</span><span class="sxs-lookup"><span data-stu-id="e8f8f-371">DLP reports</span></span>

<span data-ttu-id="e8f8f-372">在建立並開啟您的 DLP 原則之後，您會想要確認他們正在如您預期運作，並協助您符合規範。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-372">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant.</span></span> <span data-ttu-id="e8f8f-373">透過 DLP 報告，您可以快速檢視一段時間內的 DLP 原則和規則相符項目的數目，以及誤判和覆寫的數目。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-373">With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides.</span></span> <span data-ttu-id="e8f8f-374">針對每份報告，您可以依據位置、時間範圍篩選這些相符項目，甚至將其範圍縮小到特定原則、規則或動作。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-374">For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="e8f8f-375">透過 DLP 報告，您將可取得深入的商業資訊，並且：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-375">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="e8f8f-376">將重點放在特定時段，以了解尖峰和趨勢的原因。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-376">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="e8f8f-377">探索違反貴組織的符合性原則的商務程序。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-377">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="e8f8f-378">了解 DLP 原則帶來的任何業務影響。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-378">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="e8f8f-379">此外，您可以使用 DLP 報告來微調您所執行的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-379">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![安全性與合規性中心內的報告儀表板](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="e8f8f-381">DLP 原則的運作方式</span><span class="sxs-lookup"><span data-stu-id="e8f8f-381">How DLP policies work</span></span>

<span data-ttu-id="e8f8f-p156">DLP 會使用深度內容分析 (不只是簡單的文字掃描) 來偵測敏感資訊。此深度內容分析會使用關鍵字比對、字典比對、規則運算式評估、內部函數和其他方法來偵測符合 DLP 原則的內容。可能只有一小部分的資料會被視為敏感資訊。DLP 原則可識別、監視和自動保護該項資料，而不會妨礙或影響到使用其餘內容的人員。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-p156">DLP detects sensitive information by using deep content analysis (not just a simple text scan). This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies. Potentially only a small percentage of your data is considered sensitive. A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="e8f8f-386">原則會同步處理</span><span class="sxs-lookup"><span data-stu-id="e8f8f-386">Policies are synced</span></span>

<span data-ttu-id="e8f8f-387">安全性建立 DLP 原則之後&amp;合規性中心，已儲存在中央原則存放區，並再同步處理至各種內容來源，包括：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-387">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="e8f8f-388">Exchange Online，並從有網頁型 Outlook 和 Outlook 2013 和更新版本</span><span class="sxs-lookup"><span data-stu-id="e8f8f-388">Exchange Online, and from there to Outlook on the web and Outlook 2013 and later</span></span>
    
- <span data-ttu-id="e8f8f-389">商務用 OneDrive 網站</span><span class="sxs-lookup"><span data-stu-id="e8f8f-389">OneDrive for Business sites</span></span>
    
- <span data-ttu-id="e8f8f-390">SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="e8f8f-390">SharePoint Online sites</span></span>
    
- <span data-ttu-id="e8f8f-391">Office 2016 桌面程式 (Excel 2016、PowerPoint 2016 和 Word 2016)</span><span class="sxs-lookup"><span data-stu-id="e8f8f-391">Office 2016 desktop programs (Excel 2016, PowerPoint 2016, and Word 2016)</span></span>
    
<span data-ttu-id="e8f8f-392">原則同步處理至正確的位置之後，它會開始評估內容並強制執行動作。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-392">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="e8f8f-393">商務用 OneDrive 和 SharePoint Online 網站中的原則評估</span><span class="sxs-lookup"><span data-stu-id="e8f8f-393">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="e8f8f-394">跨所有的 SharePoint Online 網站和商務用 OneDrive 網站，經常變更文件-他們正在不斷建立、 編輯、 共用及等等。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-394">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on.</span></span> <span data-ttu-id="e8f8f-395">這表示文件可能會隨時違反或符合 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-395">This means documents can conflict or become compliant with a DLP policy at any time.</span></span> <span data-ttu-id="e8f8f-396">例如，人員可以將不含敏感資訊文件上傳到小組網站，而後另一個人可以編輯同一份文件並在其中加入敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-396">For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="e8f8f-397">因此，DLP 原則會頻繁地在背景中檢查文件是否有原則相符項目。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-397">For this reason, DLP policies check documents for policy matches frequently in the background.</span></span> <span data-ttu-id="e8f8f-398">您可以將此視為非同步原則評估。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-398">You can think of this as asynchronous policy evaluation.</span></span>
  
<span data-ttu-id="e8f8f-399">以下是其運作方式。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-399">Here's how it works.</span></span> <span data-ttu-id="e8f8f-400">為人員新增或變更其網站中的文件，搜尋引擎會掃描內容，以便您稍後再搜尋的方式。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-400">As people add or change documents in their sites, the search engine scans the content, so that you can search for it later.</span></span> <span data-ttu-id="e8f8f-401">當發生此問題時，內容也掃描的敏感資訊，並檢查是否它共用。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-401">While this is happening, the content's also scanned for sensitive information and to check if it's shared.</span></span> <span data-ttu-id="e8f8f-402">找不到任何敏感資訊儲存安全地在搜尋索引，以便只有 「 規範小組可以存取它，但不是一般使用者。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-402">Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users.</span></span> <span data-ttu-id="e8f8f-403">您已開啟的每個 DLP 原則在背景中執行 （非同步），檢查經常符合原則之內容的搜尋及套用動作，以防止不慎外洩。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-403">Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![圖表顯示如何 DLP 原則評估內容以非同步方式](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<span data-ttu-id="e8f8f-p160">最後，文件可能會違反 DLP 原則，但也可能會符合 DLP 原則。例如，如果人員在文件中加入信用卡號碼，有可能會導致 DLP 原則自動封鎖文件的存取。但如果人員稍後移除敏感資訊，則會在下次依據原則進行評估時自動復原動作 (在此案例中為封鎖)。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-p160">Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy. For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically. But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="e8f8f-408">DLP 會評估任何可編製索引的內容。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-408">DLP evaluates any content that can be indexed.</span></span> <span data-ttu-id="e8f8f-409">如需有關預設會編目哪些檔案類型的詳細資訊，請參閱[預設編目檔案副檔名及剖析的 SharePoint Server 2013 中的檔案類型](https://go.microsoft.com/fwlink/p/?LinkID=627430)。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-409">For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server 2013](https://go.microsoft.com/fwlink/p/?LinkID=627430).</span></span>
  
### <a name="policy-evaluation-in-exchange-online-outlook-2013-and-later-and-outlook-on-the-web"></a><span data-ttu-id="e8f8f-410">Exchange Online、 Outlook 2013 和更新版本和 outlook 網頁版中的原則評估</span><span class="sxs-lookup"><span data-stu-id="e8f8f-410">Policy evaluation in Exchange Online, Outlook 2013 and later, and Outlook on the web</span></span>

<span data-ttu-id="e8f8f-411">當您建立包含 Exchange Online 做為位置的 DLP 原則時，此原則的同步處理從 Office 365 安全性&amp;合規性中心至 Exchange Online 中，然後再從 Exchange Online，以在網頁型 Outlook 和 Outlook 2013 和更新版本。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-411">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook 2013 and later.</span></span>
  
<span data-ttu-id="e8f8f-412">在 Outlook 中正在撰寫郵件，使用者即可看到原則提示時所建立的內容會根據 DLP 原則評估。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-412">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies.</span></span> <span data-ttu-id="e8f8f-413">與郵件傳送後，它會根據 DLP 原則評估作為一般郵件流程，以及 Exchange 郵件流程規則 （也稱為傳輸規則） 和在 Exchange 系統管理中心中建立的 DLP 原則的一部分 （請參閱下一節以取得更多資訊）。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-413">And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange mail flow rules (also known as transport rules) and DLP policies created in the Exchange admin center (see the next section for more info).</span></span> <span data-ttu-id="e8f8f-414">DLP 原則會掃描郵件和任何附件。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-414">DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-2016-desktop-programs"></a><span data-ttu-id="e8f8f-415">Office 2016 桌面程式中的原則評估</span><span class="sxs-lookup"><span data-stu-id="e8f8f-415">Policy evaluation in the Office 2016 desktop programs</span></span>

<span data-ttu-id="e8f8f-416">Excel 2016、PowerPoint 2016 和 Word 2016 都具有與 SharePoint Online 和商務用 OneDrive 相同的功能，可識別敏感資訊並套用 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-416">Excel 2016, PowerPoint 2016, and Word 2016 include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="e8f8f-417">這些 Office 2016 程式同步處理其直接從中央原則存放區的 DLP 原則，然後再根據 DLP 原則的內容持續評估，當人員搭配開啟從網站中的 DLP 原則所包含的文件。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-417">These Office 2016 programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="e8f8f-418">Office 2016 中的 DLP 原則評估依設計並不會影響程式的效能或內容使用者的產能。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-418">DLP policy evaluation in Office 2016 is designed not to affect the performance of the programs or the productivity of people working on content.</span></span> <span data-ttu-id="e8f8f-419">如果他們正在處理大型文件，或使用者的電腦為忙碌，可能需要幾秒顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-419">If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>
  
## <a name="permissions"></a><span data-ttu-id="e8f8f-420">權限</span><span class="sxs-lookup"><span data-stu-id="e8f8f-420">Permissions</span></span>

<span data-ttu-id="e8f8f-421">會建立 DLP 原則的規範小組成員需要權限給安全性群組&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-421">Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="e8f8f-422">根據預設，您的租用戶系統管理員將能夠存取此位置並可授與法務人員及其他人員存取安全性&amp;合規性中心，而不提供他們取得所有租用戶管理員的權限若要這麼做，我們建議您：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-422">By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="e8f8f-423">在 Office 365 中建立一個群組，並將法務人員新增至此群組。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-423">Create a group in Office 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="e8f8f-424">建立角色群組的安全性**權限**] 頁面上&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-424">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 
    
3. <span data-ttu-id="e8f8f-425">將 Office 365 群組新增至此角色群組。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-425">Add the Office 365 group to the role group.</span></span>
    
<span data-ttu-id="e8f8f-426">如需詳細資訊，請參閱[Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-426">For more information, see [Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="e8f8f-427">需要這些權限才能建立及套用 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-427">These permissions are required only to create and apply a DLP policy.</span></span> <span data-ttu-id="e8f8f-428">原則強制執行不需要內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-428">Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="e8f8f-429">尋找 DLP 指令程式</span><span class="sxs-lookup"><span data-stu-id="e8f8f-429">Find the DLP cmdlets</span></span>

<span data-ttu-id="e8f8f-430">若要使用之 cmdlet 的大部分 security&amp;合規性中心，您需要：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-430">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="e8f8f-431">使用遠端 PowerShell 連線到 Office 365 安全性與合規性中心</span><span class="sxs-lookup"><span data-stu-id="e8f8f-431">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="e8f8f-432">使用下列任何一這些[Office 365 安全性&amp;合規性中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="e8f8f-432">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="e8f8f-433">不過，DLP 報告需要提取資料從 Office 365，包括 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-433">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="e8f8f-434">基於這個理由，DLP 報告指令程式可供在 Exchange Online Powershell-而不是以安全性&amp;合規性中心 Powershell。</span><span class="sxs-lookup"><span data-stu-id="e8f8f-434">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="e8f8f-435">因此，若要使用 cmdlet 的 DLP 報告，您必須：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-435">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="e8f8f-436">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e8f8f-436">Connect to Exchange Online using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="e8f8f-437">使用這些 cmdlet 的任何 DLP 報告：</span><span class="sxs-lookup"><span data-stu-id="e8f8f-437">Use any of these cmdlets for the DLP reports:</span></span>
    
  - [<span data-ttu-id="e8f8f-438">Get-dlpdetectionsreport</span><span class="sxs-lookup"><span data-stu-id="e8f8f-438">Get-DlpDetectionsReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
  - [<span data-ttu-id="e8f8f-439">Get-dlpdetailreport</span><span class="sxs-lookup"><span data-stu-id="e8f8f-439">Get-DlpDetailReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    
## <a name="more-information"></a><span data-ttu-id="e8f8f-440">其他資訊</span><span class="sxs-lookup"><span data-stu-id="e8f8f-440">More information</span></span>

- [<span data-ttu-id="e8f8f-441">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="e8f8f-441">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="e8f8f-442">傳送通知並顯示原則提示的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="e8f8f-442">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="e8f8f-443">建立 DLP 原則來保護具有 FCI 或其他屬性的文件</span><span class="sxs-lookup"><span data-stu-id="e8f8f-443">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="e8f8f-444">DLP 原則範本包含哪些內容</span><span class="sxs-lookup"><span data-stu-id="e8f8f-444">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="e8f8f-445">機密資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="e8f8f-445">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="e8f8f-446">DLP 功能所尋找的項目</span><span class="sxs-lookup"><span data-stu-id="e8f8f-446">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="e8f8f-447">建立自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="e8f8f-447">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    

