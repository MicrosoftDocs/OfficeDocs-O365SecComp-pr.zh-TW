---
title: Office 365 中的監督原則
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: 了解 Office 365 中的監督原則
ms.openlocfilehash: 0c76ba5b17277d8bd441810415e7e9acd1adbf36
ms.sourcegitcommit: 3cb775e60b3806b66568ed2f9664c17ef96ca8de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/28/2019
ms.locfileid: "29603523"
---
# <a name="supervision-policies-in-office-365"></a><span data-ttu-id="ae0ec-103">Office 365 中的監督原則</span><span class="sxs-lookup"><span data-stu-id="ae0ec-103">Supervision policies in Office 365</span></span>

<span data-ttu-id="ae0ec-p101">Office 365 中的監督原則可讓您擷取員工檢查所指定檢閱者通訊。您可以定義擷取內部和外部的電子郵件、 Microsoft 小組或組織中的第 3 廠商通訊的特定原則。檢閱者然後可以檢查並確定其符合您組織的郵件標準訊息並加以解決與分類類型。這些原則也有助於克服許多現代規範挑戰，包括監控增加時的通訊通道，增加大量郵件資料和法規強制執行 & 罰的風險的類型。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p101">Supervision policies in Office 365 allow you to capture employee communications for examination by designated reviewers. You can define specific policies that capture internal and external email, Microsoft Teams, or 3rd-party communications in your organization. Reviewers can then examine the messages to make sure they are compliant with your organization's message standards and resolve them with classification type. These policies can also help you overcome many modern compliance challenges, including monitoring increasing types of communication channels, increasing volume of message data, and regulatory enforcement & the risk of fines.</span></span>

<span data-ttu-id="ae0ec-p102">在某些組織中，可能會發生之 IT 支援與 [規範管理] 群組之間的責任區隔。Office 365 支援監督原則支援功能和原則的組態設定租用和作用於擷取通訊之間的區隔。例如，組織的 IT 群組可能負責設定角色權限與群組可支援監督原則設定及管理組織的規範小組。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p102">In some organizations, there may be a separation of duties between IT support and the compliance management group. Office 365 supports the separation between configuring the tenant with supervision policy support features and the configuration of policies and acting on captured communications. For example, the IT group for an organization may be responsible for setting up role permissions and groups to support supervision policies that are configured and managed by the organization's compliance team.</span></span>

## <a name="scenarios-for-supervision-policies"></a><span data-ttu-id="ae0ec-111">監督原則的案例</span><span class="sxs-lookup"><span data-stu-id="ae0ec-111">Scenarios for supervision policies</span></span>

<span data-ttu-id="ae0ec-112">監督原則可協助您組織中數個區域的監控通訊：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-112">Supervision policies can assist monitoring communications in your organization in several areas:</span></span>

- <span data-ttu-id="ae0ec-113">**公司原則**</span><span class="sxs-lookup"><span data-stu-id="ae0ec-113">**Corporate policies**</span></span>

    <span data-ttu-id="ae0ec-p103">員工必須符合可接受的使用、 道德標準以及其他公司的原則中所有業務相關的通訊。監督原則可以偵測違反原則，並協助您採取更正動作以協助減輕這類事件。例如，您可以監視您的組織如騷擾或不適當或不良語言員工通訊中使用的潛在人力資源違規。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p103">Employees must comply with acceptable use, ethical standards, and other corporate policies in all their business-related communications. Supervision policies can detect policy violations and help you take corrective actions to help mitigate these types of incidents. For example, you could monitor your organization for potential human resources violations such as harassment or the use of inappropriate or offensive language in employee communications.</span></span>

- <span data-ttu-id="ae0ec-117">**風險管理**</span><span class="sxs-lookup"><span data-stu-id="ae0ec-117">**Risk management**</span></span>

    <span data-ttu-id="ae0ec-p104">組織負責分散式整個其基礎結構與公司網路系統中的所有通訊。使用監督原則有助於找出潛在的法律衝擊和風險可協助他們可以損壞公司的作業之前風險降到最低。例如，您無法監視貴組織如即將來臨併、 合併、 獲利揭露、 重新組織或領導小組變更機密專案未經授權的通訊。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p104">Organizations are responsible to all communications distributed throughout their infrastructure and corporate network systems. Using supervision policies to help identify and manage potential legal exposure and risk can help minimize risks before they can damage corporate operations. For example, you could monitor your organization for unauthorized communications for confidential projects such as upcoming acquisitions, mergers, earnings disclosures, reorganizations, or leadership team changes.</span></span>

- <span data-ttu-id="ae0ec-121">**法規符合性**</span><span class="sxs-lookup"><span data-stu-id="ae0ec-121">**Regulatory compliance**</span></span>

    <span data-ttu-id="ae0ec-p105">大多數的組織必須遵守某些類型的法規遵循標準 （英文） 作為其一般作業的程序的一部分。這些規定通常需要實作的監督某些類型的組織或負責監督通訊的程序適用於其產業。財務產業法規授權單位 (FINRA) 規則 3110 是必要項目已經備妥監督的程序的組織要監視其員工的活動的良好範例和其執行的企業的類型。另一個範例可能需要在監視 broker-協會您組織中來防範潛在 money laundering、 貿易內部、 夥伴或賄賂活動。監督原則可協助組織符合這些需求提供監視及報告上公司通訊的程序。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p105">Most organizations must comply with some type of regulatory compliance standards as part of their normal operating procedures. These regulations often require organizations to implement some type of supervisory or oversight process for messaging that is appropriate for their industry. The Financial Industry Regulatory Authority (FINRA) Rule 3110 is a good example of a requirement for organizations to have supervisory procedures in place to monitor the activities of its employees and the types of businesses in which it engages. Another example may be a need to monitor broker-dealers in your organization to safeguard against potential money-laundering, insider trading, collusion, or bribery activities. Supervision policies can help your organization meet these requirements by providing a process to both monitor and report on corporate communications.</span></span>

## <a name="feature-components"></a><span data-ttu-id="ae0ec-127">功能元件</span><span class="sxs-lookup"><span data-stu-id="ae0ec-127">Feature components</span></span>

### <a name="supervision-policy"></a><span data-ttu-id="ae0ec-128">監督原則</span><span class="sxs-lookup"><span data-stu-id="ae0ec-128">Supervision policy</span></span>

<span data-ttu-id="ae0ec-p106">您將建立監督原則中安全性 & 規範中心。這些原則定義的通訊與使用者會受到組織中的檢閱，定義自訂條件通訊必須符合，並指定誰應該執行檢閱 （英文）。包含在角色群組可以設定原則和已指派給此角色的任何人監督檢閱的使用者可以存取監督頁面的 [下資料管理在 Office 365 安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p106">You'll create supervision policies in the Security & Compliance Center. These policies define which communications and users are subject to review in your organization, define custom conditions that the communications must meet, and specifies who should perform reviews. Users included in the Supervisory Review role group can set up policies and anyone who has this role assigned can access the Supervision page under Data Governance in the Office 365 Security & Compliance Center.</span></span>

### <a name="supervised-users"></a><span data-ttu-id="ae0ec-132">監督的使用者</span><span class="sxs-lookup"><span data-stu-id="ae0ec-132">Supervised users</span></span>

<span data-ttu-id="ae0ec-p107">在您開始使用監督之前，您需要決定誰會有檢閱其通訊。在原則中，您將使用使用者電子郵件地址來識別的個人或群組的管理人員。這些群組的一些範例為 Office 365 Groups、 Exchange 為基礎的通訊群組清單及 Microsoft 小組通道。您也可以排除特定使用者或群組的監督的群組或群組的清單中包含的監督。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p107">Before you start using supervision, you'll need to determine who will have their communications reviewed. In the policy, you'll use user email addresses to identify individuals or groups of people to supervise. Some examples of these groups are Office 365 Groups, Exchange-based distribution lists, and Microsoft Teams channels. You also can exclude specific users or groups from supervision that are included within a supervised group or a list of groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae0ec-p108">監視的監督原則的所有使用者必須具有進階規範附加元件可以是 Office 365 企業版 E3 授權或包含在 Office 365 企業版 E5 訂閱。如果您未有現有的企業 E5 計劃以及要嘗試監督，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p108">All users monitored by supervision policies must have either an Office 365 Enterprise E3 license with the Advanced Compliance add-on or be included in an Office 365 Enterprise E5 subscription. If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>

### <a name="reviewers"></a><span data-ttu-id="ae0ec-139">檢閱者</span><span class="sxs-lookup"><span data-stu-id="ae0ec-139">Reviewers</span></span>

<span data-ttu-id="ae0ec-p109">當您建立監督原則，時請將決定誰可以執行的監督使用者的郵件檢閱 （英文）。在原則中，您將使用識別的個人或群組的人員可供檢閱監督的通訊的使用者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p109">When you create a supervision policy, you'll also determine who will perform the reviews of the messages of the supervised users. In the policy, you'll use user email addresses to identify individuals or groups of people to review supervised communications.</span></span>

### <a name="groups-for-supervised-users-and-reviewers"></a><span data-ttu-id="ae0ec-142">監督的使用者和檢閱者群組</span><span class="sxs-lookup"><span data-stu-id="ae0ec-142">Groups for supervised users and reviewers</span></span>

<span data-ttu-id="ae0ec-p110">若要簡化您的安裝程式，建立人員有其檢閱的通訊群組和人員將檢閱這些通訊群組。如果您使用的群組，您可能需要數個。例如，如果您想要監視的人員、 兩個不同的群組之間的通訊，或者您想要指定無法移至要指導的群組。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p110">To simplify your setup, create groups for people who will have their communication reviewed and groups for people who will review those communications. If you're using groups, you might need several. For example, if you want to monitor communications between two distinct groups of people, or if you want to specify a group that isn't going to be supervised.</span></span>

### <a name="supported-communication-types"></a><span data-ttu-id="ae0ec-146">支援的通訊類型</span><span class="sxs-lookup"><span data-stu-id="ae0ec-146">Supported communication types</span></span>

<span data-ttu-id="ae0ec-147">監督原則，您可以選擇監視中一或多個下列通訊平台的郵件：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-147">With supervision policies, you can choose to monitor messages in one or more of the following communication platforms:</span></span>

- <span data-ttu-id="ae0ec-p111">**Exchange 電子郵件：** 您的 Office 365 訂閱的一部分託管於 Exchange Online 的信箱位於所有合格的訊息監督。電子郵件和附件符合監督原則條件會立即可用的監控和監督報告中。支援的附件類型如下：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p111">**Exchange email:** Mailboxes that are hosted on Exchange Online as part of your Office 365 subscription are all eligible for message supervision. Emails and attachments matching supervision policy conditions are instantly available for monitoring and in supervision reports. Supported attachment types are:</span></span>

    - <span data-ttu-id="ae0ec-151">Microsoft Word (.docx)</span><span class="sxs-lookup"><span data-stu-id="ae0ec-151">Microsoft Word (.docx)</span></span>
    - <span data-ttu-id="ae0ec-152">Microsoft Excel (.xlsx)</span><span class="sxs-lookup"><span data-stu-id="ae0ec-152">Microsoft Excel (.xlsx)</span></span>
    - <span data-ttu-id="ae0ec-153">Microsoft PowerPoint (.pptx)</span><span class="sxs-lookup"><span data-stu-id="ae0ec-153">Microsoft PowerPoint (.pptx)</span></span>

- <span data-ttu-id="ae0ec-p112">**的 Microsoft 小組：** 可以指導聊天通訊和中公用及私人的 Microsoft 小組通道和個別的聊天室關聯的附件。比對監督原則條件的小組聊天室處理一次每 24 個小時和則都可監視和監督報告中。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p112">**Microsoft Teams:** Chat communications and associated attachments in both public and private Microsoft Teams channels and individual chats can be supervised. Teams chats matching supervision policy conditions are processed once every 24 hours and then are available for monitoring and in supervision reports.</span></span>
- <span data-ttu-id="ae0ec-p113">**協力廠商來源：** 您可以管理通訊從協力廠商來源 (從 Facebook 或投寄箱 like) 如果您已在組織中此資料匯入到 Office 365 信箱。[解如何將 Office 365 的第 3 廠商資料匯入](https://docs.microsoft.com/office365/securitycompliance/archiving-third-party-data)。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p113">**Third-party sources:** You can supervise communications from third-party sources (like from Facebook or DropBox) if you've imported this data into Office 365 mailboxes in your organization. [Learn how to import 3rd-party data into Office 365](https://docs.microsoft.com/office365/securitycompliance/archiving-third-party-data).</span></span>

### <a name="policy-settings"></a><span data-ttu-id="ae0ec-158">原則設定</span><span class="sxs-lookup"><span data-stu-id="ae0ec-158">Policy settings</span></span>

#### <a name="direction"></a><span data-ttu-id="ae0ec-159">方向</span><span class="sxs-lookup"><span data-stu-id="ae0ec-159">Direction</span></span>

<span data-ttu-id="ae0ec-p114">根據預設，**方向是**條件會顯示，且無法移除。個別或一起可選擇在原則中的通訊方向設定：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p114">By default, the **Direction is** condition is displayed and can't be removed. Communication direction settings in a policy can be chosen individually or together:</span></span>

- <span data-ttu-id="ae0ec-162">**輸入**-您可以選擇**輸入**檢閱就會傳送**至**管理**從**人員選擇的人員不包含在原則中的通訊。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-162">**Inbound** - You can choose **Inbound** to review communications that are sent **to** the people you chose to supervise **from** people not included in the policy.</span></span>
- <span data-ttu-id="ae0ec-163">**輸出**-您可以選擇**輸出**若您想要檢閱傳送**從**原則中未包含管理**至**人員選擇的人員通訊。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-163">**Outbound** - You can choose **Outbound** if you want to review communications that are sent **from** the people you chose to supervise **to** people not included in the policy.</span></span>
- <span data-ttu-id="ae0ec-164">**Internal** -您可以選擇**內部**通訊傳送**之間**檢閱您指定的人員在原則中。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-164">**Internal** - You can choose **Internal** to review communications sent **between** the people you identified in the policy.</span></span>

#### <a name="sensitive-information-types"></a><span data-ttu-id="ae0ec-165">敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="ae0ec-165">Sensitive information types</span></span>

<span data-ttu-id="ae0ec-p115">您可以選擇包含敏感資訊類型監督原則的一部分。敏感資訊類型是可以協助識別及保護信用卡號、 銀行帳戶號碼、 護照號碼及其他任一預先定義或自訂的資料類型。Office 365[資料外洩防護 (DLP)](data-loss-prevention-policies.md)的一部分的機密資訊設定可以運用模式、 字元鄰近、 信賴等級及即使自訂資料類型，以找出問題及標示可能機密的內容。預設敏感資訊類型如下：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p115">You have the option of including sensitive information types as part of your supervision policy. Sensitive information types are either pre-defined or custom data types that can help identify and protect credit card numbers, bank account numbers, passport numbers, and more. As a part of Office 365 [data loss prevention (DLP)](data-loss-prevention-policies.md), the sensitive information configuration can leverage patterns, character proximity, confidence levels, and even custom data types to help identify and flag content that may be sensitive. The default sensitive information types are:</span></span>

- <span data-ttu-id="ae0ec-170">財務</span><span class="sxs-lookup"><span data-stu-id="ae0ec-170">Financial</span></span>
- <span data-ttu-id="ae0ec-171">醫療和健康情況</span><span class="sxs-lookup"><span data-stu-id="ae0ec-171">Medical and health</span></span>
- <span data-ttu-id="ae0ec-172">隱私權</span><span class="sxs-lookup"><span data-stu-id="ae0ec-172">Privacy</span></span>
- <span data-ttu-id="ae0ec-173">自訂的資訊類型</span><span class="sxs-lookup"><span data-stu-id="ae0ec-173">Custom information type</span></span>

<span data-ttu-id="ae0ec-174">若要深入了解敏感資訊的詳細資訊與預設類型中的模式，請參閱[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-174">To learn more about sensitive information details and the patterns included in the default types, see [What sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

#### <a name="custom-keyword-dictionaries"></a><span data-ttu-id="ae0ec-175">自訂關鍵字字典</span><span class="sxs-lookup"><span data-stu-id="ae0ec-175">Custom keyword dictionaries</span></span>

<span data-ttu-id="ae0ec-p116">設定自訂關鍵字字典 （或 lexicons） 可提供簡單管理的關鍵字專屬於組織或產業及可支援最多 100000 個字詞每個字典。必要時，您可以將多個關鍵字自訂字典套用至單一原則或需要個別原則單一關鍵字字典。這些字典中監督原則指派給與可以源自 （例如.csv 或.txt 清單） 檔案或從清單中您可以[直接在 PowerShell 指令程式輸入](create-a-keyword-dictionary.md)。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p116">Configuring custom keyword dictionaries (or lexicons) can provide simple management of keywords specific to your organization or industry and can support up to 100,000 terms per dictionary. If needed, you can apply multiple custom keyword dictionaries to a single policy or have a single keyword dictionary per policy. These dictionaries are assigned in a supervision policy and can be sourced from a file (such as a .csv or .txt list), or from a list you can [enter directly in a PowerShell cmdlet](create-a-keyword-dictionary.md).</span></span>

#### <a name="conditional-settings"></a><span data-ttu-id="ae0ec-179">設定格式化的條件的設定</span><span class="sxs-lookup"><span data-stu-id="ae0ec-179">Conditional settings</span></span>

<span data-ttu-id="ae0ec-180">您選擇之原則的條件將套用通訊 (從 Facebook 或投寄箱 like) 您組織中的電子郵件和第 3 廠商來源。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-180">The conditions you choose for the policy will apply to communications from both email and 3rd-party sources in your organization (like from Facebook or DropBox).</span></span>

<span data-ttu-id="ae0ec-181">下表說明更多關於每一項條件。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-181">The following table explains more about each condition.</span></span>
  
|<span data-ttu-id="ae0ec-182">**條件**</span><span class="sxs-lookup"><span data-stu-id="ae0ec-182">**Condition**</span></span>|<span data-ttu-id="ae0ec-183">**如何使用此條件**</span><span class="sxs-lookup"><span data-stu-id="ae0ec-183">**How to use this condition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ae0ec-184">從任何這些網域接收郵件</span><span class="sxs-lookup"><span data-stu-id="ae0ec-184">Message is received from any of these domains</span></span>  <br><br> <span data-ttu-id="ae0ec-185">從任何這些網域不接收郵件</span><span class="sxs-lookup"><span data-stu-id="ae0ec-185">Message is not received from any of these domains</span></span> | <span data-ttu-id="ae0ec-p117">若要將原則套用特定的網域是包含或排除在接收郵件時，輸入每個網域並使用逗號分隔多個網域。您輸入每個網域會分別套用 （只有其中一個這些網域必須套用適用於將原則套用至郵件）。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p117">To apply the policy when certain domains are included or excluded in a received message, enter each domain and separate multiple domains with a comma. Each domain you enter will be applied separately (only one of these domains must apply for the policy to apply to the message).</span></span> |
|<span data-ttu-id="ae0ec-188">郵件傳送給任何這些網域</span><span class="sxs-lookup"><span data-stu-id="ae0ec-188">Message is sent to any of these domains</span></span>  <br><br> <span data-ttu-id="ae0ec-189">訊息不會傳送到任何這些網域</span><span class="sxs-lookup"><span data-stu-id="ae0ec-189">Message is not sent to  any of these domains</span></span> | <span data-ttu-id="ae0ec-p118">若要將原則套用特定的網域是包含或排除在已傳送郵件時，輸入每個網域並使用逗號分隔多個網域。您輸入每個網域會分別套用 （只有其中一個這些網域必須套用適用於將原則套用至郵件）。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p118">To apply the policy when certain domains are included or excluded in a sent message, enter each domain and separate multiple domains with a comma. Each domain you enter will be applied separately (only one of these domains must apply for the policy to apply to the message).</span></span> |
|<span data-ttu-id="ae0ec-192">郵件被分類與任何這些標籤</span><span class="sxs-lookup"><span data-stu-id="ae0ec-192">Message is classified with any of these labels</span></span>  <br><br> <span data-ttu-id="ae0ec-193">郵件未分類與任何這些標籤</span><span class="sxs-lookup"><span data-stu-id="ae0ec-193">Message is not classified with any of these labels</span></span> | <span data-ttu-id="ae0ec-p119">若要將原則套用時內含或排除在郵件中某些保留標籤。您必須分別設定保留標籤並設定的標籤可以選擇此條件的一部分。您選擇每個標籤會分別套用 （僅需一個這些標籤必須套用適用於將原則套用至郵件）。如需設定保留標籤的詳細資訊，請參閱 ＜ [Overview of 保留標籤](https://docs.microsoft.com/office365/securitycompliance/labels)。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p119">To apply the policy when certain retention labels are included or excluded in a message. Retention labels must be configured separately and configured labels can be chosen as part of this condition. Each label you choose will be applied separately (only one of these labels must apply for the policy to apply to the message). For more information about configuring retention labels, see [Overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>|
|<span data-ttu-id="ae0ec-198">郵件包含任何這些字詞</span><span class="sxs-lookup"><span data-stu-id="ae0ec-198">Message contains any of these words</span></span>  <br><br> <span data-ttu-id="ae0ec-199">郵件包含任何這些字詞</span><span class="sxs-lookup"><span data-stu-id="ae0ec-199">Message contains none of these words</span></span> | <span data-ttu-id="ae0ec-p120">若要將原則套用包含或排除在郵件中特定單字或片語時，輸入每個單字或片語分列一行。您輸入的文字的每一行會分別套用 （僅需一個的這些行必須套用適用於將原則套用至郵件）。如需輸入單字或片語的詳細資訊，請參閱 [下一步] 區段中[比對字與詞至電子郵件或附件](supervision-policies.md#Matchwords)。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p120">To apply the policy when certain words or phrases are included or excluded in a message, enter each word or phrase on a separate line. Each line of words you enter will be applied separately (only one of these lines must apply for the policy to apply to the message). For more information about entering words or phrases, see the next section [Matching words and phrases to emails or attachments](supervision-policies.md#Matchwords).</span></span>|
|<span data-ttu-id="ae0ec-203">附件中包含任何這些字詞</span><span class="sxs-lookup"><span data-stu-id="ae0ec-203">Attachment contains any of these words</span></span>  <br><br> <span data-ttu-id="ae0ec-204">附件包含任何這些字詞</span><span class="sxs-lookup"><span data-stu-id="ae0ec-204">Attachment contains none of these words</span></span> | <span data-ttu-id="ae0ec-p121">若要將原則套用包含或排除在郵件附件 （例如 Word 文件） 中特定單字或片語時，輸入每個單字或片語分列一行。您輸入的文字的每一行會分別套用 （僅限一行必須套用適用於將原則套用至附件）。如需輸入單字或片語的詳細資訊，請參閱 [下一步] 區段中[比對字與詞至電子郵件或附件](supervision-policies.md#Matchwords)。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p121">To apply the policy when certain words or phrases are included or excluded in a message attachment (such as a Word document), enter each word or phrase on a separate line. Each line of words you enter will be applied separately (only one line must apply for the policy to apply to the attachment). For more information about entering words or phrases, see the next section [Matching words and phrases to emails or attachments](supervision-policies.md#Matchwords).</span></span>|
|<span data-ttu-id="ae0ec-208">附件是任何這些檔案類型</span><span class="sxs-lookup"><span data-stu-id="ae0ec-208">Attachment is any of these file types</span></span>  <br><br> <span data-ttu-id="ae0ec-209">附件為 none 這些檔案類型</span><span class="sxs-lookup"><span data-stu-id="ae0ec-209">Attachment is none of these file types</span></span> | <span data-ttu-id="ae0ec-p122">若要管理包括或排除特定類型的附件的通訊，請輸入副檔名 （例如.exe 或.pdf）。如果您想要包含或排除多個副檔名，輸入這些在個別行上。只有一個附件副檔名必須套用之原則的相符。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p122">To supervise communications that include or exclude specific types of attachments, enter the file extensions (such as .exe or .pdf). If you want to include or exclude multiple file extensions, enter these on separate lines. Only one attachment extension needs to match for the policy to apply.</span></span>|
|<span data-ttu-id="ae0ec-213">郵件大小大於</span><span class="sxs-lookup"><span data-stu-id="ae0ec-213">Message size is larger than</span></span>  <br><br> <span data-ttu-id="ae0ec-214">郵件大小大於不</span><span class="sxs-lookup"><span data-stu-id="ae0ec-214">Message size is not larger than</span></span> | <span data-ttu-id="ae0ec-p123">若要檢閱根據特定大小的郵件，請使用這些條件來指定一則訊息可以隨時檢閱之前的最大值或最小大小。例如，如果您指定**的郵件大小大於** \> **1.0 MB**，所有郵件 1.01 MB 且更大會遵循檢閱。您可以選擇位元組、 kb、 （mb） 或 gb 此情況。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p123">To review messages based on a certain size, use these conditions to specify the maximum or minimum size a message can be before it is subject to review. For example, if you specify **Message size is larger than** \> **1.0 MB**, all messages that are 1.01 MB and larger will be subject to review. You can choose bytes, kilobytes, megabytes, or gigabytes for this condition.</span></span>|
|<span data-ttu-id="ae0ec-218">附件為大於</span><span class="sxs-lookup"><span data-stu-id="ae0ec-218">Attachment is larger than</span></span>  <br><br> <span data-ttu-id="ae0ec-219">附件是不大於</span><span class="sxs-lookup"><span data-stu-id="ae0ec-219">Attachment is not larger than</span></span> | <span data-ttu-id="ae0ec-p124">若要檢閱其附件的大小為基礎的郵件，請指定附件的最大值或最小大小可以是之前郵件和其附件會受到檢閱。例如，如果您指定**附件大於** \> **2.0 MB**附件的所有郵件 2.01 MB 及移轉會遵循檢閱。您可以選擇位元組、 kb、 （mb） 或 gb 此情況。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p124">To review messages based on the size of their attachments, specify the maximum or minimum size an attachment can be before the message and its attachments are subject to review. For example, if you specify **Attachment is larger than** \> **2.0 MB**, all messages with attachments 2.01 MB and over will be subject to review. You can choose bytes, kilobytes, megabytes, or gigabytes for this condition.</span></span>|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a><span data-ttu-id="ae0ec-223">對電子郵件或附件比對單字和字詞</span><span class="sxs-lookup"><span data-stu-id="ae0ec-223">Matching words and phrases to emails or attachments</span></span>
<span data-ttu-id="ae0ec-224"><a name="Matchwords"> </a></span><span class="sxs-lookup"><span data-stu-id="ae0ec-224"></span></span>

<span data-ttu-id="ae0ec-p125">您輸入的文字的每一行會分別套用 （僅限一行必須套用適用於電子郵件或附件套用原則條件）。例如，我們使用條件、**郵件包含任何這些字詞**，關鍵字"也"及"內部貿易"在個別行上。原則會套用到任何包含"也"一字或片語"內部貿易"的訊息。僅有一個這些單字或片語的必須發生以套用此原則條件。在訊息或附件中的文字必須完全符合您的輸入。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p125">Each line of words you enter will be applied separately (only one line must apply for the policy condition to apply to the email or attachment). For example, let's use the condition, **Message contains any of these words**, with the keywords "banker" and "insider trading" on separate lines. The policy will apply to any messages that includes the word "banker" or the phrase "insider trading". Only one of these words or phrases must occur for this policy condition to apply. Words in the message or attachment must exactly match what you enter.</span></span>
  
##### <a name="entering-multiple-conditions"></a><span data-ttu-id="ae0ec-230">輸入多個條件</span><span class="sxs-lookup"><span data-stu-id="ae0ec-230">Entering multiple conditions</span></span>

<span data-ttu-id="ae0ec-p126">如果您輸入多個條件、 Office 365 使用的所有條件一起決定何時要將原則套用至通訊項目。當您設定多個條件時，他們必須所有符合將原則套用，除非您輸入的例外狀況。例如，假設您需要建立如果郵件包含單字"貿易"且大於 2 MB 應套用原則。不過，如果郵件也包含單字"Contoso 財務的已核准 」，應該不會套用原則。因此，在此例中的三種條件就是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p126">If you enter multiple conditions, Office 365 uses all the conditions together to determine when to apply the policy to communication items. When you set up multiple conditions, they must all be met for the policy to apply, unless you enter an exception. For example, let's say you need to create a policy that should apply if a message contains the word "trade", and is larger than 2MB. However, if the message also contains the words "Approved by Contoso financial", the policy should not apply. Thus, in this case, the three conditions would be as follows:</span></span>
  
- <span data-ttu-id="ae0ec-236">**郵件包含任何這些字詞**、 使用關鍵字"貿易"</span><span class="sxs-lookup"><span data-stu-id="ae0ec-236">**Message contains any of these words**, with the keywords "trade"</span></span>

- <span data-ttu-id="ae0ec-237">**郵件大小大於**，以值 2 MB</span><span class="sxs-lookup"><span data-stu-id="ae0ec-237">**Message size is larger than**, with the value 2 MB</span></span>

- <span data-ttu-id="ae0ec-238">**郵件包含不含這些字**、 使用關鍵字"Contoso 財務小組的已核准 」。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-238">**Message contains none of these words**, with the keywords "Approved by Contoso financial team".</span></span>

#### <a name="review-percentage"></a><span data-ttu-id="ae0ec-239">檢閱百分比</span><span class="sxs-lookup"><span data-stu-id="ae0ec-239">Review percentage</span></span>

<span data-ttu-id="ae0ec-p127">您可以指定如果您想要減少可供檢閱的內容量由監督原則的所有通訊的百分比。我們隨機將符合您所選擇的條件的總百分比從選取的內容量。如果您想檢閱者的所有項目時，您可以輸入**100%** 監督原則中。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p127">You can specify a percentage of all the communications governed by a supervision policy if you want to reduce the amount of content to review. We'll randomly select that amount of content from the total percentage that matched the conditions you chose. If you want reviewers to review all items, you can enter **100%** in a supervision policy.</span></span>

## <a name="monitoring--managing"></a><span data-ttu-id="ae0ec-243">監視 & 管理</span><span class="sxs-lookup"><span data-stu-id="ae0ec-243">Monitoring & managing</span></span>

<span data-ttu-id="ae0ec-p128">監控的監督原則結果並套用解析度標記為簡單且方便。您可以快速查看檢閱過的項目、 使用者及下監督、 群組及使用者和群組指定為 [檢閱者的狀態。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p128">Monitoring the results of your supervision policies and applying a resolution tag is easy and convenient. You can quickly see the status of reviewed items, the users and groups under supervision, and the users and groups designated as reviewers.</span></span>

### <a name="supervision-policy-dashboard"></a><span data-ttu-id="ae0ec-246">監督原則儀表板</span><span class="sxs-lookup"><span data-stu-id="ae0ec-246">Supervision policy dashboard</span></span>

<span data-ttu-id="ae0ec-p129">若要管理監督原則結果並解決未完成的項目最簡單的方法是使用監督原則儀表板。此儀表板可讓檢閱者快速查看的項目需要檢閱、 為項目執行動作及先前檢閱結果的檢閱和解析針對每個監督原則的項目。您可以存取 Office 365 安全性 &**監督**規範中心的監督原則儀表板 > *您的自訂原則* > **開啟**。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p129">The easiest way to manage supervision policy results and to resolve outstanding items is to use the supervision policy dashboard. This dashboard allows reviewers to quickly see the items that need to be reviewed, take action on an item, and review the results of previously reviewed and resolved items for each supervision policy. You can access the supervision policy dashboard in the Office 365 Security & Compliance Center at **Supervision** > *Your Custom Policy* > **Open**.</span></span>

#### <a name="dashboard-home"></a><span data-ttu-id="ae0ec-250">儀表板首頁</span><span class="sxs-lookup"><span data-stu-id="ae0ec-250">Dashboard Home</span></span>

<span data-ttu-id="ae0ec-p130">儀表板**首頁**] 頁面上有幾個區段可協助您快速取得監督原則中的 [巨集指令。以下是您可以：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p130">The dashboard **Home** page has several sections to help you quickly take action on your supervision policies. Here you can:</span></span>

- <span data-ttu-id="ae0ec-253">快速檢閱擱置中及已解析醒目提示日當週</span><span class="sxs-lookup"><span data-stu-id="ae0ec-253">Quickly review the pending and resolved highlights for the week</span></span>
- <span data-ttu-id="ae0ec-254">請參閱監督的使用者及群組清單的監督針對所選取的原則</span><span class="sxs-lookup"><span data-stu-id="ae0ec-254">See a list of the supervised users and supervised groups for the selected policy</span></span>
- <span data-ttu-id="ae0ec-255">請參閱檢閱者的清單及檢閱小組的所選取的原則</span><span class="sxs-lookup"><span data-stu-id="ae0ec-255">See a list of the reviewers and review teams for the selected policy</span></span>
- <span data-ttu-id="ae0ec-256">查看哪些通訊平台具有下監督原則的內容。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-256">See which communication platforms have content under supervision for the policy.</span></span>

#### <a name="supervise-tab"></a><span data-ttu-id="ae0ec-257">管理] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="ae0ec-257">Supervise tab</span></span>

<span data-ttu-id="ae0ec-p131">[ **Supervise** ] 索引標籤是其中檢閱者可以採取動作並解析項目所識別所選取的原則。以下是您可以：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p131">The **Supervise** tab is where reviewers can take action and resolve items identified by the selected policy. Here you can:</span></span>

- <span data-ttu-id="ae0ec-260">篩選擱置相容且不相容問題的項目</span><span class="sxs-lookup"><span data-stu-id="ae0ec-260">Filter by pending, compliant, non-compliant, and questionable items</span></span>
- <span data-ttu-id="ae0ec-p132">標記為相容、 非相容或問題的單一項目。您也可以記錄項目，來協助釐清標記所採取的動作的註解。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p132">Tag a single item as compliant, non-compliant, or questionable. You can also record a comment with the item to help clarify the tagging action taken.</span></span>
- <span data-ttu-id="ae0ec-p133">大量標記為相容、 非相容或問題的多個項目。您也可以記錄可協助釐清標記所採取的動作的多個項目與註解。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p133">Bulk tag multiple items as compliant, non-compliant, or questionable. You can also record a comment with multiple items to help clarify the tagging action taken.</span></span>
- <span data-ttu-id="ae0ec-265">檢視的單一項目，包括誰解析項目、 日期和時間的動作、 解析度標記，且任何包含註解標記歷程的記錄。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-265">View the history of the tagging for a single item, including who resolved the item, the date and time of the action, the resolution tag, and any included comments.</span></span>
- <span data-ttu-id="ae0ec-p134">重新分類先前檢閱為相容、 非相容或問題的項目。您也可以記錄與單一或多個項目以協助釐清重新分類會採取的註解。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p134">Reclassify previously reviewed items as compliant, non-compliant, or questionable. You can also record a comment with single or multiple items to help clarify the reclassification action taken.</span></span>

#### <a name="resolved-items-tab"></a><span data-ttu-id="ae0ec-268">解析項目] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="ae0ec-268">Resolved Items tab</span></span>

<span data-ttu-id="ae0ec-p135">**解析項目**] 索引標籤是檢閱者可以在其中檢視所選取的原則的所有先前已解析項目。以下是您可以：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p135">The **Resolved Items** tab is where reviewers can view all previously resolved items for the selected policy. Here you can:</span></span>

- <span data-ttu-id="ae0ec-271">快速檢視和排序的主旨、 寄件者和解析項目的日期。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-271">Quickly view and sort the subject, sender, and date of resolved items.</span></span>
- <span data-ttu-id="ae0ec-272">檢視所有選取的項目分類和註解歷程記錄</span><span class="sxs-lookup"><span data-stu-id="ae0ec-272">View the classification and comment history of any selected item</span></span>

### <a name="other-ways-to-review-items"></a><span data-ttu-id="ae0ec-273">若要檢閱項目的其他方式</span><span class="sxs-lookup"><span data-stu-id="ae0ec-273">Other ways to review items</span></span>

<span data-ttu-id="ae0ec-274">如果檢閱者偏好不使用 Office 365 的監督儀表板，他們也可以檢閱並管理項目收集監督原則的其他選項。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-274">If reviewers would prefer not to use the supervision dashboard in Office 365, they also have other options to review and manage items collected by supervision policies.</span></span>

#### <a name="outlook-on-the-web"></a><span data-ttu-id="ae0ec-275">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="ae0ec-275">Outlook on the web</span></span>

<span data-ttu-id="ae0ec-p136">使用者指定為監督原則中的檢閱者可以使用 Outlook web 上的檢閱並解析監督項目。監督增益集會自動安裝在 web 上的 Outlook 中所指定之原則的所有檢閱者的。可供檢閱者已設定的監督原則共用資料夾的組織會不需要任何額外的設定。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p136">Users designated as reviewers in a supervision policy can use Outlook on the web to review and resolved supervision items. The Supervision add-in is installed automatically in Outlook on the web for all reviewers you specified in the policy. No extra configuration is needed by your organization for supervision policy shared folders to be available for configured reviewers.</span></span>

<span data-ttu-id="ae0ec-279">使用 Outlook web 上的，檢閱者可以：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-279">Using Outlook on the web, reviewers can:</span></span>

- <span data-ttu-id="ae0ec-280">檢視相容、 非相容、 問題，並解析狀態篩選過的項目</span><span class="sxs-lookup"><span data-stu-id="ae0ec-280">View filtered items by compliant, non-compliant, questionable, and resolved status</span></span>
- <span data-ttu-id="ae0ec-p137">標記的單一項目為相容、 非相容、 問題，或解析。您也可以記錄項目，來協助釐清標記所採取的動作的註解。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p137">Tag a single item as compliant, non-compliant, questionable, or resolved. You can also record a comment with the item to help clarify the tagging action taken.</span></span>
- <span data-ttu-id="ae0ec-283">檢視的單一項目，包括誰解析項目、 日期和時間的動作、 解析度標記，且任何包含註解標記歷程的記錄。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-283">View the history of the tagging for a single item, including who resolved the item, the date and time of the action, the resolution tag, and any included comments.</span></span>
- <span data-ttu-id="ae0ec-p138">重新分類先前檢閱為相容、 非相容或問題的項目。您也可以記錄可協助釐清重新分類會採取的單一項目與註解。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p138">Reclassify previously reviewed items as compliant, non-compliant, or questionable. You can also record a comment with single items to help clarify the reclassification action taken.</span></span>

#### <a name="microsoft-outlook"></a><span data-ttu-id="ae0ec-286">Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="ae0ec-286">Microsoft Outlook</span></span>

<span data-ttu-id="ae0ec-p139">若要檢閱監督原則所識別的通訊，請檢閱者也可以監督增益集來使用 Microsoft outlook。不過，檢閱者必須執行完成某些步驟，以安裝在桌面的 Outlook 版本。如需安裝監督增益集 outlook 的詳細指引，請參閱 ＜ [Configure 監督原則](configure-supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p139">To review communications identified by a supervision policy, reviewers can also use the Supervision add-in for Microsoft Outlook. However, reviewers must run through some steps to install it in the desktop version of Outlook. For detailed guidance about installing the Supervision add-in for Outlook, see [Configure supervision policies](configure-supervision-policies.md).</span></span>

<span data-ttu-id="ae0ec-290">使用 Outlook、 檢閱者可以：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-290">Using Outlook, reviewers can:</span></span>

- <span data-ttu-id="ae0ec-291">檢視相容、 非相容、 問題，並解析狀態篩選過的項目</span><span class="sxs-lookup"><span data-stu-id="ae0ec-291">View filtered items by compliant, non-compliant, questionable, and resolved status</span></span>
- <span data-ttu-id="ae0ec-p140">標記的單一項目為相容、 非相容、 問題，或解析。您也可以記錄項目，來協助釐清標記所採取的動作的註解。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p140">Tag a single item as compliant, non-compliant, questionable, or resolved. You can also record a comment with the item to help clarify the tagging action taken.</span></span>
- <span data-ttu-id="ae0ec-294">檢視的單一項目，包括誰解析項目、 日期和時間的動作、 解析度標記，且任何包含註解標記歷程的記錄。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-294">View the history of the tagging for a single item, including who resolved the item, the date and time of the action, the resolution tag, and any included comments.</span></span>
- <span data-ttu-id="ae0ec-p141">重新分類先前檢閱為相容、 非相容或問題的項目。您也可以記錄可協助釐清重新分類會採取的單一項目與註解。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p141">Reclassify previously reviewed items as compliant, non-compliant, or questionable. You can also record a comment with single items to help clarify the reclassification action taken.</span></span>

## <a name="reporting"></a><span data-ttu-id="ae0ec-297">報告</span><span class="sxs-lookup"><span data-stu-id="ae0ec-297">Reporting</span></span>

<span data-ttu-id="ae0ec-p142">若要查看檢閱活動層級原則和檢閱者使用監督報告。每個原則，您也可以檢閱活動的目前狀態檢視 live 的統計資料。您可以使用監督報告：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p142">Use the supervision reports to see the review activity at the policy and reviewer level. For each policy, you can also view live statistics on the current state of review activity. You can use the supervision reports to:</span></span>
  
- <span data-ttu-id="ae0ec-301">確認您的原則運作如您預期。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-301">Verify that your policies are working as you intended.</span></span>
- <span data-ttu-id="ae0ec-302">了解多少通訊所識別供檢閱。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-302">Find out how many communications are being identified for review.</span></span>
- <span data-ttu-id="ae0ec-p143">深入了解多少通訊不相容並傳遞哪些檢閱。這項資訊可協助您決定是否要調整成您的原則或變更檢閱者的數目。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p143">Find out how many communications aren't compliant and which ones are passing review. This information can help you decide whether to fine-tune your policies or change the number of reviewers.</span></span>

### <a name="view-the-supervision-report"></a><span data-ttu-id="ae0ec-305">檢視監督報告</span><span class="sxs-lookup"><span data-stu-id="ae0ec-305">View the Supervision report</span></span>

1. <span data-ttu-id="ae0ec-306">登入 Office 365 組織中的檢視監督報告的權限的管理帳戶使用的認證[安全性 & 規範中心](https://protection.office.com/)。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-306">Sign into the [Security & Compliance Center](https://protection.office.com/) using the credentials for an admin account in your Office 365 organization that has permissions to view supervision reports.</span></span>
2. <span data-ttu-id="ae0ec-p144">移至其中一個**報告** \> **儀表板**或**監督**。您會看見報告與目前的監督原則活動的摘要 widget 監督。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p144">Go to either **Reports** \> **Dashboard** or **Supervision**. You'll see a supervision reporting widget with a summary of current supervision policy activity.</span></span>
3. <span data-ttu-id="ae0ec-309">選取 [以開啟 [詳細資料報告] 頁面上的**監督**widget。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-309">Select the **Supervision** widget to open the detailed report page.</span></span>

> [!NOTE]
> <span data-ttu-id="ae0ec-p145">如果您不可以存取 [**報告**] 頁面上，核取您正在監督檢閱角色群組的成員，[讓組織中可用的監督](configure-supervision-policies.md)所述。要包含在此角色群組可讓您建立及管理監督原則並執行報表。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p145">If you aren't able to access the **Reports** page, check that you're a member of the Supervisory Review role group, as described in [Make supervision available in your organization](configure-supervision-policies.md). Being included in this role group lets you create and manage supervision polices and run the report.</span></span>
  
### <a name="how-to-use-the-report"></a><span data-ttu-id="ae0ec-312">如何使用報告</span><span class="sxs-lookup"><span data-stu-id="ae0ec-312">How to use the report</span></span>

<span data-ttu-id="ae0ec-p146">當監督原則識別檢閱通訊訊息時、 電子郵件會傳遞至檢閱者監督資料夾中 Outlook 和 Outlook web app。這份報告會列出每個原則的名稱及通訊數目檢閱程序中的每一階段。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p146">When a supervision policy identifies a communication message for review, the email is delivered to the reviewer's Supervision folder in Outlook and Outlook web app. This report lists each policy's name and the number of communications at each stage in the review process.</span></span>
  
<span data-ttu-id="ae0ec-315">使用報告：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-315">Use the report to:</span></span>
  
- <span data-ttu-id="ae0ec-316">檢視資料的所有或特定的原則。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-316">View data for all or specific policies.</span></span>
- <span data-ttu-id="ae0ec-317">檢視資料標籤類型分組 （例如符合標準、 Questionable 等等）、 檢閱者或訊息類型。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-317">View data grouped by tag type (such as Compliant, Questionable, etc.), reviewer, or message type.</span></span>
- <span data-ttu-id="ae0ec-318">將資料匯出為 CSV 檔案根據活動日期、 原則及因檢閱活動。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-318">Export data to a CSV file based on activity date, policy, and by reviewer activity.</span></span>
- <span data-ttu-id="ae0ec-319">篩選根據活動日期、 標記類型、 檢閱、 與郵件類型的資料。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-319">Filter data based on activity date, tag type, reviewer, and message type.</span></span>

<span data-ttu-id="ae0ec-320">以下是分解您可能會看到 [**標記類型**] 欄中的值。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-320">Here's a breakdown of the values you might see in the **Tag type** column.</span></span>
  
|<span data-ttu-id="ae0ec-321">**標記類型**</span><span class="sxs-lookup"><span data-stu-id="ae0ec-321">**Tag type**</span></span>|<span data-ttu-id="ae0ec-322">**其意思**</span><span class="sxs-lookup"><span data-stu-id="ae0ec-322">**What it means**</span></span>|
|:-----|:-----|
| <span data-ttu-id="ae0ec-323">不檢閱</span><span class="sxs-lookup"><span data-stu-id="ae0ec-323">Not Reviewed</span></span> | <span data-ttu-id="ae0ec-p147">尚未檢視的電子郵件數目。這些電子郵件送交檢閱 Office 365 監督儀表板中或 Outlook/Outlook Web App 中的檢閱者監督資料夾中。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p147">The number of emails that have not been reviewed yet. These emails are awaiting review in the Office 365 supervision dashboard or in the reviewer's supervision folder in Outlook/Outlook Web App.</span></span>|
| <span data-ttu-id="ae0ec-326">相容</span><span class="sxs-lookup"><span data-stu-id="ae0ec-326">Compliant</span></span> | <span data-ttu-id="ae0ec-p148">檢閱並標示為相容的電子郵件數目。這些訊息還是需要解析。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p148">The number of emails reviewed and marked as compliant. These messages still need to be resolved.</span></span> |
| <span data-ttu-id="ae0ec-329">問題</span><span class="sxs-lookup"><span data-stu-id="ae0ec-329">Questionable</span></span> | <span data-ttu-id="ae0ec-p149">檢閱並標示問題的電子郵件數目。這可以做為標幟 ；其他檢閱者可協助檢查電子郵件是否需要將正在調查規範。這些訊息還是需要解析。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p149">The number of emails reviewed and marked questionable. This acts as a flag; other reviewers can help check whether an email needs investigation for compliance. These messages still need to be resolved.</span></span> |
| <span data-ttu-id="ae0ec-333">非相容 （使用中）</span><span class="sxs-lookup"><span data-stu-id="ae0ec-333">Non-Compliant (Active)</span></span> | <span data-ttu-id="ae0ec-334">非相容的目前調查檢閱者的電子郵件數目。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-334">The number of non-compliant emails that reviewers are currently investigating.</span></span> |
| <span data-ttu-id="ae0ec-335">非相容 （解析）</span><span class="sxs-lookup"><span data-stu-id="ae0ec-335">Non-Compliant (Resolved)</span></span> | <span data-ttu-id="ae0ec-336">檢閱者調查並解決非相容電子郵件數目。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-336">The number of non-compliant emails that reviewers investigated and resolved.</span></span> |
| <span data-ttu-id="ae0ec-337">瀏覽原則</span><span class="sxs-lookup"><span data-stu-id="ae0ec-337">Hit Policy</span></span> | <span data-ttu-id="ae0ec-338">總數 （每日） 從 Exchange、 小組及協力廠商資料來源的比對監督原則所定義的一或多個條件的郵件</span><span class="sxs-lookup"><span data-stu-id="ae0ec-338">The total number (daily) of messages from Exchange, Teams, and third-party data sources that matched one or more conditions defined in a supervision policy</span></span> |
| <span data-ttu-id="ae0ec-339">在 Purview</span><span class="sxs-lookup"><span data-stu-id="ae0ec-339">In Purview</span></span> | <span data-ttu-id="ae0ec-340">總數 （每日） 從 Exchange、 小組及協力廠商資料來源的監督原則所掃描的郵件</span><span class="sxs-lookup"><span data-stu-id="ae0ec-340">The total number (daily) of messages from Exchange, Teams, and third-party data sources scanned by a supervision policy</span></span> |
| <span data-ttu-id="ae0ec-341">已解決</span><span class="sxs-lookup"><span data-stu-id="ae0ec-341">Resolved</span></span> | <span data-ttu-id="ae0ec-342">從 Exchange、 小組及已被分類為**已解決**的協力廠商資料來源的訊息總數</span><span class="sxs-lookup"><span data-stu-id="ae0ec-342">The total number of messages from Exchange, Teams, and third-party data sources that have been classified as **Resolved**</span></span>|

> [!NOTE]
> <span data-ttu-id="ae0ec-p150">監督原則必須先佈建才會出現在此報告。此外，如果會刪除原則，仍會顯示歷程資料。不過，它們指定為 「 非存在原則 」 及**匯出**函數無法使用。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p150">Supervision policies must first be provisioned before they will appear in this report. Additionally, if policies are deleted, historical data is still shown. However, they're indicated as a "Non-existent policy" and the **Export** function isn't available.</span></span>

## <a name="auditing"></a><span data-ttu-id="ae0ec-346">稽核</span><span class="sxs-lookup"><span data-stu-id="ae0ec-346">Auditing</span></span>

<span data-ttu-id="ae0ec-p151">在某些情況下，您需要提供資訊給法規或規範稽核者以證明監督的員工活動和通訊。這可能是相關聯的已定義的原則或只要監督原則已變更或更新的所有監督活動的摘要。監督原則都具有內建的稽核線索完成整備的內部或外部稽核。證明監督的程序可以具有監視監督原則的每個動作的詳細的稽核記錄所示。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-p151">In some instances, you'll need to provide information to regulatory or compliance auditors to prove supervision of employee activities and communications. This may be a summary of all supervisory activities associated with a defined policy or anytime a supervision policy was changed or updated. Supervision policies have built-in audit trails for complete readiness for internal or external audits. Proof of supervisory procedures can be demonstrated with a detailed audit history of every action monitored by your supervision policies.</span></span>

<span data-ttu-id="ae0ec-351">下列的監督原則活動稽核及可以使用整合的 Office 365 稽核記錄檔檢視：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-351">The following supervision policy activities are audited and can be viewed using the unified Office 365 audit logs:</span></span>

|<span data-ttu-id="ae0ec-352">**活動**</span><span class="sxs-lookup"><span data-stu-id="ae0ec-352">**Activity**</span></span>|<span data-ttu-id="ae0ec-353">**相關聯的命令**</span><span class="sxs-lookup"><span data-stu-id="ae0ec-353">**Associated commands**</span></span>|
|:-----|:-----|
| <span data-ttu-id="ae0ec-354">建立原則</span><span class="sxs-lookup"><span data-stu-id="ae0ec-354">Creating a policy</span></span> | <span data-ttu-id="ae0ec-355">新 SupervisoryReviewPolicy</span><span class="sxs-lookup"><span data-stu-id="ae0ec-355">New-SupervisoryReviewPolicy</span></span> <br> <span data-ttu-id="ae0ec-356">新 SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="ae0ec-356">New-SupervisoryReviewRule</span></span> |
| <span data-ttu-id="ae0ec-357">編輯原則</span><span class="sxs-lookup"><span data-stu-id="ae0ec-357">Editing a policy</span></span> | <span data-ttu-id="ae0ec-358">設定 SupervisoryReviewPolicy</span><span class="sxs-lookup"><span data-stu-id="ae0ec-358">Set-SupervisoryReviewPolicy</span></span> <br> <span data-ttu-id="ae0ec-359">設定 SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="ae0ec-359">Set-SupervisoryReviewRule</span></span> |
| <span data-ttu-id="ae0ec-360">刪除原則</span><span class="sxs-lookup"><span data-stu-id="ae0ec-360">Deleting a policy</span></span>| <span data-ttu-id="ae0ec-361">移除 SupervisoryReviewPolicy</span><span class="sxs-lookup"><span data-stu-id="ae0ec-361">Remove-SupervisoryReviewPolicy</span></span> |

<span data-ttu-id="ae0ec-362">可以使用整合的稽核記錄搜尋函數來擷取稽核或使用[搜尋 UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-362">The audits can be retrieved using the unified audit log search function or by using the [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) PowerShell cmdlet.</span></span>

<span data-ttu-id="ae0ec-363">例如下, 面範例會傳回所有監督檢閱活動 （原則和規則） 的活動及列出各項的詳細的資訊：</span><span class="sxs-lookup"><span data-stu-id="ae0ec-363">For example, the following example returns the activities for the all the supervisory review activities (policies and rules) and lists detailed information for each:</span></span>

```
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"} | fl CreationDate,Operations,UserIds,AuditData 
```

<span data-ttu-id="ae0ec-364">除了監督報表和記錄檔中所提供的資訊，您也可以使用[Get SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewactivity?view=exchange-ps) PowerShell 指令程式來傳回所有的監督的完整詳細的清單原則活動。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-364">In addition to information provided in the supervision reports and logs, you can also use the [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewactivity?view=exchange-ps) PowerShell cmdlet to return a complete detailed listing of all supervision policy activities.</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="ae0ec-365">準備好開始？</span><span class="sxs-lookup"><span data-stu-id="ae0ec-365">Ready to get started?</span></span>

<span data-ttu-id="ae0ec-366">若要啟動 [設定您的組織的監督原則，請參閱 ＜ [Configure 監督原則](configure-supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ae0ec-366">To start configuring supervision policies for your organization, see [Configure supervision policies](configure-supervision-policies.md).</span></span>