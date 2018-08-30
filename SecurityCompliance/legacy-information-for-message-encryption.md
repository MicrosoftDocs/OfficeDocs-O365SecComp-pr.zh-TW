---
title: Office 365 郵件加密的舊版資訊
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/4/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
description: 如果您尚未尚未移動 Office 365 組織到新的 OME 功能，但您已部署 OME，本文資訊適用於您組織。Microsoft 建議您將移至新的 OME 功能一旦是組織的合理的計劃。指示，請參閱 ＜ Set up 新建置上方的 Azure 資訊保護的 Office 365 郵件加密功能。如果您想要了解更多有關的新功能如何運作前，請參閱 Office 365 郵件加密。本文的其餘部分是指 OME 行為的新 OME 功能發行前。
ms.openlocfilehash: d5b21cbe0004ca7bda38085bd5d8ef5f2a22b04e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526839"
---
# <a name="legacy-information-for-office-365-message-encryption"></a><span data-ttu-id="9e701-107">Office 365 郵件加密的舊版資訊</span><span class="sxs-lookup"><span data-stu-id="9e701-107">Legacy information for Office 365 Message Encryption</span></span>

<span data-ttu-id="9e701-p102">如果您尚未尚未移動 Office 365 組織到新的 OME 功能，但您已部署 OME，本文資訊適用於您組織。Microsoft 建議您將移至新的 OME 功能一旦是組織的合理的計劃。指示，請參閱[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護](set-up-new-message-encryption-capabilities.md)。如果您想要了解更多有關的新功能如何運作前，請參閱[Office 365 郵件加密](ome.md)。本文的其餘部分是指 OME 行為的新 OME 功能發行前。</span><span class="sxs-lookup"><span data-stu-id="9e701-p102">If you haven't yet moved your Office 365 organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization. Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md). The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>
  
<span data-ttu-id="9e701-p103">與 Office 365 郵件加密，您的組織可以傳送和接收組織內外的人員之間的加密電子郵件訊息。Office 365 郵件加密適用於 Outlook.com、 Yahoo、 Gmail、 及其他電子郵件服務。電子郵件訊息加密有助於確保只有預定的收件者可以檢視郵件內容。</span><span class="sxs-lookup"><span data-stu-id="9e701-p103">With Office 365 Message Encryption, your organization can send and receive encrypted email messages between people inside and outside your organization. Office 365 Message Encryption works with Outlook.com, Yahoo, Gmail, and other email services. Email message encryption helps ensure that only intended recipients can view message content.</span></span>
  
<span data-ttu-id="9e701-116">以下為一些範例：</span><span class="sxs-lookup"><span data-stu-id="9e701-116">Here are some examples:</span></span>
  
- <span data-ttu-id="9e701-117">銀行員工將信用卡帳單傳送給客戶</span><span class="sxs-lookup"><span data-stu-id="9e701-117">A bank employee sends credit card statements to customers</span></span>
    
- <span data-ttu-id="9e701-118">保險公司代表將細節提供給客戶原則的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="9e701-118">An insurance company representative provides policy details to customers</span></span>
    
- <span data-ttu-id="9e701-119">抵押仲介要求之客戶的意見貸款申請的財務資訊</span><span class="sxs-lookup"><span data-stu-id="9e701-119">A mortgage broker requests financial information from a customer for a loan application</span></span>
    
- <span data-ttu-id="9e701-120">醫療服務提供者將醫療資訊傳送給病患</span><span class="sxs-lookup"><span data-stu-id="9e701-120">A health care provider sends health care information to patients</span></span>
    
- <span data-ttu-id="9e701-121">律師將機密資訊傳送給客戶或其他律師</span><span class="sxs-lookup"><span data-stu-id="9e701-121">An attorney sends confidential information to a customer or another attorney</span></span>
    
## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a><span data-ttu-id="9e701-122">Office 365 郵件加密而的新功能的運作方式</span><span class="sxs-lookup"><span data-stu-id="9e701-122">How Office 365 Message Encryption works without the new capabilities</span></span>

<span data-ttu-id="9e701-p104">Office 365 郵件加密是一種線上服務的內建 Microsoft Azure 版權管理 (Azure RMS)。以 Azure RMS 系統管理員可以定義郵件流程規則來決定加密的條件。例如，規則可能需要所有寄給特定收件者的郵件的加密。</span><span class="sxs-lookup"><span data-stu-id="9e701-p104">Office 365 Message Encryption is an online service that's built on Microsoft Azure Rights Management (Azure RMS). With Azure RMS, administrators can define mail flow rules to determine the conditions for encryption. For example, a rule can require the encryption of all messages addressed to a specific recipient.</span></span>
  
<span data-ttu-id="9e701-126">觀看這段短片查看 Office 365 郵件加密而的新功能的運作方式。</span><span class="sxs-lookup"><span data-stu-id="9e701-126">Watch this short video to see how Office 365 Message Encryption works without the new capabilities.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
<span data-ttu-id="9e701-p105">當有人傳送電子郵件訊息在 Exchange Online 符合加密規則時，會傳送郵件具有 HTML 附件。收件者開啟 HTML 附件，並遵循指示來檢視加密的郵件上的 Office 365 郵件加密入口網站。收件者可以選擇檢視郵件登入 Microsoft 帳戶或工作或學校相關聯與 Office 365 或使用一次性複雜的程式碼。這兩個選項可協助確保只有預定的收件者可以檢視加密的郵件。此程序的新 OME 功能非常不同。</span><span class="sxs-lookup"><span data-stu-id="9e701-p105">When someone sends an email message in Exchange Online that matches an encryption rule, the message is sent with an HTML attachment. The recipient opens the HTML attachment and follows instructions to view the encrypted message on the Office 365 Message Encryption portal. The recipient can choose to view the message by signing in with a Microsoft account or a work or school associated with Office 365, or by using a one-time pass code. Both options help ensure that only the intended recipient can view the encrypted message. This process is very different for the new OME capabilities.</span></span>
  
<span data-ttu-id="9e701-132">下表摘要說明透過加密和解密程序傳送電子郵件的過程。</span><span class="sxs-lookup"><span data-stu-id="9e701-132">The following diagram summarizes the passage of an email message through the encryption and decryption process.</span></span>
  
![顯示加密電子郵件路徑的圖表](media/O365-Office365MessageEncryption-Concept.png)
  
<span data-ttu-id="9e701-134">如需詳細資訊，請參閱[服務舊版 Office 365 郵件加密之前版本的新 OME 功能](legacy-information-for-message-encryption.md#LegacyServiceInfo)。</span><span class="sxs-lookup"><span data-stu-id="9e701-134">For more information, see [Service information for legacy Office 365 Message Encryption prior to the release of the new OME capabilities](legacy-information-for-message-encryption.md#LegacyServiceInfo).</span></span>
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a><span data-ttu-id="9e701-135">定義不使用新的 OME 功能的 Office 365 郵件加密的郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="9e701-135">Defining mail flow rules for Office 365 Message Encryption that don't use the new OME capabilities</span></span>

<span data-ttu-id="9e701-p106">若要啟用 Office 365 郵件加密的新功能而，Exchange Online 和 Exchange Online Protection 系統管理員會定義 Exchange 郵件流程規則。這些規則決定下何種條件電子郵件訊息應加密，以及移除郵件加密的條件。當加密巨集指令設定規則時，任何符合的規則條件的郵件加密之前他們正在傳送。</span><span class="sxs-lookup"><span data-stu-id="9e701-p106">To enable Office 365 Message Encryption without the new capabilities, Exchange Online and Exchange Online Protection administrators define Exchange mail flow rules. These rules determine under what conditions email messages should be encrypted, as well as conditions for removing message encryption. When an encryption action is set for a rule, any messages that match the rule conditions are encrypted before they're sent.</span></span>
  
<span data-ttu-id="9e701-p107">郵件流程規則具有彈性，讓您可以讓您可以符合特定安全性需求中單一規則合併條件。例如，您可以建立加密包含指定的關鍵字和定址給外部收件者的所有郵件的規則。Office 365 郵件加密也會從加密的電子郵件的收件者的回覆，您可以建立規則以解密那些回覆的電子郵件使用者的方便。如此一來，您的組織中的使用者不會有登入加密入口網站檢視回覆。</span><span class="sxs-lookup"><span data-stu-id="9e701-p107">Mail flow rules are flexible, letting you combine conditions so you can meet specific security requirements in a single rule. For example, you can create a rule to encrypt all messages that contain specified keywords and are addressed to external recipients. Office 365 Message Encryption also encrypts replies from recipients of encrypted email, and you can create a rule that decrypts those replies as a convenience for your email users. That way, users in your organization won't have to sign in to the encryption portal to view replies.</span></span>
  
<span data-ttu-id="9e701-143">如需如何建立 Exchange 郵件流程規則的詳細資訊，請參閱[Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="9e701-143">For more information about how to create Exchange mail flow rules, see [Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a><span data-ttu-id="9e701-144">傳送、檢視和回覆加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="9e701-144">Sending, viewing, and replying to encrypted email messages</span></span>

<span data-ttu-id="9e701-p108">與 Office 365 郵件加密、 電子郵件訊息會經過加密自動根據管理員定義規則。收件者的收件匣會進入附加 HTML 檔案天堂加密的郵件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9e701-p108">With Office 365 Message Encryption, email messages are encrypted automatically, based on administrator-defined rules. An email that bears an encrypted message arrives in the recipient's Inbox with an attached HTML file.</span></span>
  
<span data-ttu-id="9e701-p109">收件者遵循在開啟附件，並使用 Microsoft 帳戶或工作或學校相關聯與 Office 365 進行驗證的訊息中的指示。如果收件者沒有其中一個帳戶，他們正在導向建立檢視加密的郵件讓它們的帳戶登入 Microsoft。或者，收件者可以選擇以取得檢視郵件單次複雜程式碼。登入或之後使用一次性複雜的程式碼，收件者可以檢視已解密的郵件和傳送加密的回覆。</span><span class="sxs-lookup"><span data-stu-id="9e701-p109">Recipients follow instructions in the message to open the attachment and authenticate by using a Microsoft account or a work or school associated with Office 365. If recipients don't have either account, they're directed to create a Microsoft account that will let them sign in to view the encrypted message. Alternatively, recipients can choose to get a one-time pass code to view the message. After signing in or using a one-time pass code, recipients can view the decrypted message and send an encrypted reply.</span></span>
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a><span data-ttu-id="9e701-151">自訂 Office 365 郵件加密的加密的郵件</span><span class="sxs-lookup"><span data-stu-id="9e701-151">Customize encrypted messages with Office 365 Message Encryption</span></span>

<span data-ttu-id="9e701-p110">身為 Exchange Online 與 Exchange Online Protection 的管理員，您可以自訂加密的郵件。例如，您可以新增公司的品牌和商標、 指定簡介，並新增免責聲明文字中加密的郵件和入口網站中的收件者所在檢視加密的郵件。使用 Windows PowerShell cmdlet，您可以自訂下列部分的加密的電子郵件的收件者的檢視經驗：</span><span class="sxs-lookup"><span data-stu-id="9e701-p110">As an Exchange Online and Exchange Online Protection administrator, you can customize your encrypted messages. For example, you can add your company's brand and logo, specify an introduction, and add disclaimer text in encrypted messages and in the portal where recipients view your encrypted messages. Using Windows PowerShell cmdlets, you can customize the following aspects of the viewing experience for recipients of encrypted email messages:</span></span>
  
- <span data-ttu-id="9e701-155">包含加密訊息的電子郵件簡介文字</span><span class="sxs-lookup"><span data-stu-id="9e701-155">Introductory text of the email that contains the encrypted message</span></span>
    
- <span data-ttu-id="9e701-156">包含加密訊息的電子郵件免責聲明文字</span><span class="sxs-lookup"><span data-stu-id="9e701-156">Disclaimer text of the email that contains the encrypted message</span></span>
    
- <span data-ttu-id="9e701-157">將會出現在訊息檢視入口網站的入口網站文字</span><span class="sxs-lookup"><span data-stu-id="9e701-157">Portal text that will appear in the message viewing portal</span></span>
    
- <span data-ttu-id="9e701-158">將會出現在電子郵件和檢視入口網站的標誌</span><span class="sxs-lookup"><span data-stu-id="9e701-158">Logo that will appear in the email message and viewing portal</span></span>
    
<span data-ttu-id="9e701-159">您也可以隨時回復為預設的外觀與風格。</span><span class="sxs-lookup"><span data-stu-id="9e701-159">You can also revert back to the default look and feel at any time.</span></span>
  
<span data-ttu-id="9e701-160">下列範例顯示 ContosoPharma 在電子郵件附件中的自訂標誌：</span><span class="sxs-lookup"><span data-stu-id="9e701-160">The following example shows a custom logo for ContosoPharma in the email attachment:</span></span>
  
![已加密郵件頁面的檢視範例](media/TA-OME-3attachment2.jpg)
  
 <span data-ttu-id="9e701-162">**來自訂加密電子郵件和加密入口網站使用您的組織的商標**</span><span class="sxs-lookup"><span data-stu-id="9e701-162">**To customize encryption email messages and the encryption portal with your organization's brand**</span></span>
  
1. <span data-ttu-id="9e701-163">連線至 Exchange Online 使用遠端 PowerShell[連線至 Exchange Online Using Remote PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated)中所述。</span><span class="sxs-lookup"><span data-stu-id="9e701-163">Connect to Exchange Online using Remote PowerShell, as described in [Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated).</span></span>
    
2. <span data-ttu-id="9e701-164">使用 Set-omeconfiguration 指令程式，如下所述這裡： [Set-omeconfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)或使用下表取得指引。</span><span class="sxs-lookup"><span data-stu-id="9e701-164">Use the Set-OMEConfiguration cmdlet as described here: [Set-OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b) or use the following table for guidance.</span></span> 
    
   <span data-ttu-id="9e701-165">**加密自訂選項**</span><span class="sxs-lookup"><span data-stu-id="9e701-165">**Encryption customization options**</span></span>

|<span data-ttu-id="9e701-166">**若要自訂此加密經驗功能**</span><span class="sxs-lookup"><span data-stu-id="9e701-166">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="9e701-167">**請使用這些 Windows PowerShell 命令**</span><span class="sxs-lookup"><span data-stu-id="9e701-167">**Use these Windows PowerShell commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9e701-168">加密電子郵件隨附的預設文字</span><span class="sxs-lookup"><span data-stu-id="9e701-168">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="9e701-169">預設文字會出現在檢視加密郵件的指示上方。</span><span class="sxs-lookup"><span data-stu-id="9e701-169">The default text appears above the instructions for viewing encrypted messages</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> <span data-ttu-id="9e701-170">**範例：**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"`</span><span class="sxs-lookup"><span data-stu-id="9e701-170">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"`</span></span> <br/> |
|<span data-ttu-id="9e701-171">包含加密訊息之電子郵件中的免責聲明</span><span class="sxs-lookup"><span data-stu-id="9e701-171">Disclaimer statement in the email that contains the encrypted message</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> <span data-ttu-id="9e701-172">**範例：**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"`</span><span class="sxs-lookup"><span data-stu-id="9e701-172">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"`</span></span> <br/> |
|<span data-ttu-id="9e701-173">出現在加密郵件檢視入口網站上方的文字</span><span class="sxs-lookup"><span data-stu-id="9e701-173">Text that appears at the top of the encrypted mail viewing portal</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> <span data-ttu-id="9e701-174">**範例：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"`</span><span class="sxs-lookup"><span data-stu-id="9e701-174">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"`</span></span> <br/> |
|<span data-ttu-id="9e701-175">標誌</span><span class="sxs-lookup"><span data-stu-id="9e701-175">Logo</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> <span data-ttu-id="9e701-176">**範例：**`Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)`</span><span class="sxs-lookup"><span data-stu-id="9e701-176">**Example:** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)`</span></span> <br/> <span data-ttu-id="9e701-177">支援的檔案格式：.png、.jpg、.bmp 或 .tiff</span><span class="sxs-lookup"><span data-stu-id="9e701-177">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="9e701-178">標誌檔案的最佳大小：小於 40 KB</span><span class="sxs-lookup"><span data-stu-id="9e701-178">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="9e701-179">標誌影像的最佳大小：170x70 像素</span><span class="sxs-lookup"><span data-stu-id="9e701-179">Optimal size of logo image: 170x70 pixels</span></span>  <br/> |
   
 <span data-ttu-id="9e701-180">**若要移除的商標自訂加密電子郵件和加密入口網站**</span><span class="sxs-lookup"><span data-stu-id="9e701-180">**To remove brand customizations from encryption email messages and the encryption portal**</span></span>
  
1. <span data-ttu-id="9e701-181">連線至 Exchange Online 使用遠端 PowerShell[連線至 Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="9e701-181">Connect to Exchange Online using Remote PowerShell, as described in [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="9e701-p111">使用 Set-omeconfiguration 指令程式，如下所述這裡： [Set-omeconfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)。若要移除您組織的加商標的自訂項目從 DisclaimerText、 EmailText、 和 PortalText 值將值設定為空字串， `""`。如所有圖像值，例如標誌，將值設定為`"$null"`。</span><span class="sxs-lookup"><span data-stu-id="9e701-p111">Use the Set-OMEConfiguration cmdlet as described here: [Set-OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b). To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string,  `""`. For all image values, such as Logo, set the value to  `"$null"`.</span></span>
    
   <span data-ttu-id="9e701-185">**加密自訂選項**</span><span class="sxs-lookup"><span data-stu-id="9e701-185">**Encryption customization options**</span></span>

|<span data-ttu-id="9e701-186">**將加密體驗的這項功能回復為預設文字和影像**</span><span class="sxs-lookup"><span data-stu-id="9e701-186">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="9e701-187">**請使用這些 Windows PowerShell 命令**</span><span class="sxs-lookup"><span data-stu-id="9e701-187">**Use these Windows PowerShell commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9e701-188">加密電子郵件隨附的預設文字</span><span class="sxs-lookup"><span data-stu-id="9e701-188">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="9e701-189">預設文字會出現在檢視加密郵件的指示上方。</span><span class="sxs-lookup"><span data-stu-id="9e701-189">The default text appears above the instructions for viewing encrypted messages</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> <span data-ttu-id="9e701-190">**範例：**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`</span><span class="sxs-lookup"><span data-stu-id="9e701-190">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`</span></span> <br/> |
|<span data-ttu-id="9e701-191">包含加密訊息之電子郵件中的免責聲明</span><span class="sxs-lookup"><span data-stu-id="9e701-191">Disclaimer statement in the email that contains the encrypted message</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> <span data-ttu-id="9e701-192">**範例：**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`</span><span class="sxs-lookup"><span data-stu-id="9e701-192">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`</span></span> <br/> |
|<span data-ttu-id="9e701-193">出現在加密郵件檢視入口網站上方的文字</span><span class="sxs-lookup"><span data-stu-id="9e701-193">Text that appears at the top of the encrypted mail viewing portal</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> <span data-ttu-id="9e701-194">**回復為預設的範例：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`</span><span class="sxs-lookup"><span data-stu-id="9e701-194">**Example reverting back to default:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`</span></span> <br/> |
|<span data-ttu-id="9e701-195">標誌</span><span class="sxs-lookup"><span data-stu-id="9e701-195">Logo</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> <span data-ttu-id="9e701-196">**回復為預設的範例：**`Set-OMEConfiguration -Identity "OME configuration" -Image $null`</span><span class="sxs-lookup"><span data-stu-id="9e701-196">**Example reverting back to default:** `Set-OMEConfiguration -Identity "OME configuration" -Image $null`</span></span> <br/> |
   
## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a><span data-ttu-id="9e701-197">舊版 Office 365 郵件加密之前版本的新 OME 功能的服務資訊</span><span class="sxs-lookup"><span data-stu-id="9e701-197">Service information for legacy Office 365 Message Encryption prior to the release of the new OME capabilities</span></span>
<span data-ttu-id="9e701-198"><a name="LegacyServiceInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="9e701-198"></span></span>

<span data-ttu-id="9e701-199">下表提供 Office 365 郵件加密服務之前版本的新 OME 功能的技術詳細資料。</span><span class="sxs-lookup"><span data-stu-id="9e701-199">The following table provides technical details for the Office 365 Message Encryption service prior to the release of the new OME capabilities.</span></span>
  
|<span data-ttu-id="9e701-200">**服務詳細資料**</span><span class="sxs-lookup"><span data-stu-id="9e701-200">**Service details**</span></span>|<span data-ttu-id="9e701-201">**描述**</span><span class="sxs-lookup"><span data-stu-id="9e701-201">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9e701-202">用戶端裝置需求</span><span class="sxs-lookup"><span data-stu-id="9e701-202">Client device requirements</span></span>  <br/> |<span data-ttu-id="9e701-203">只要可以在支援「表單張貼」的現代瀏覽器中開啟 HTML 附件，就可以在任何用戶端裝置上檢視加密郵件。</span><span class="sxs-lookup"><span data-stu-id="9e701-203">Encrypted messages can be viewed on any client device, as long as the HTML attachment can be opened in a modern browser that supports Form Post.</span></span>  <br/> |
|<span data-ttu-id="9e701-204">加密演算法和聯邦資訊處理標準 (FIPS) 相容性</span><span class="sxs-lookup"><span data-stu-id="9e701-204">Encryption algorithm and Federal Information Processing Standards (FIPS) compliance</span></span>  <br/> |<span data-ttu-id="9e701-p112">Office 365 郵件加密使用相同的加密金鑰以 Windows Azure 資訊版權管理 (IRM)，並支援密碼編譯模式 2 （2 K 金鑰 RSA） 和 256 位元金鑰 sha-1 系統。如需基礎的 IRM 密碼編譯模式的詳細資訊，請參閱[AD RMS 密碼編譯模式](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9e701-p112">Office 365 Message Encryption uses the same encryption keys as Windows Azure Information Rights Management (IRM) and supports Cryptographic Mode 2 (2K key for RSA and 256 bits key for SHA-1 systems). For more information about the underlying IRM cryptographic modes, see [AD RMS Cryptographic Modes](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx).  </span></span><br/> |
|<span data-ttu-id="9e701-207">支援的訊息類型</span><span class="sxs-lookup"><span data-stu-id="9e701-207">Supported message types</span></span>  <br/> |<span data-ttu-id="9e701-p113">Office 365 郵件加密僅支援包含**IPM 訊息類別識別碼的項目。請注意**。如需詳細資訊，請參閱[項目類型和郵件類別](https://msdn.microsoft.com/library/office/ff861573.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9e701-p113">Office 365 Message Encryption is only supported for items that have a message class ID of **IPM.Note**. For more information, see [Item types and message classes](https://msdn.microsoft.com/library/office/ff861573.aspx).  </span></span><br/> |
|<span data-ttu-id="9e701-210">郵件大小限制</span><span class="sxs-lookup"><span data-stu-id="9e701-210">Message size limits</span></span>  <br/> |<span data-ttu-id="9e701-p114">Office 365 郵件加密可以加密郵件的最多 25 mb。如需詳細資訊的郵件大小限制，請參閱[Exchange Online 限制](http://technet.microsoft.com/library/exchange-online-limits.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9e701-p114">Office 365 Message Encryption can encrypt messages of up to 25 megabytes. For more details about message size limits, see [Exchange Online Limits](http://technet.microsoft.com/library/exchange-online-limits.aspx).  </span></span><br/> |
|<span data-ttu-id="9e701-213">Exchange Online 電子郵件保留原則</span><span class="sxs-lookup"><span data-stu-id="9e701-213">Exchange Online email retention policies</span></span>  <br/> |<span data-ttu-id="9e701-214">Exchange Online 不會儲存加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="9e701-214">Exchange Online doesn't store the encrypted messages.</span></span>  <br/> |
|<span data-ttu-id="9e701-215">Office 365 郵件加密的語言支援</span><span class="sxs-lookup"><span data-stu-id="9e701-215">Language support for Office 365 Message Encryption</span></span>  <br/> | <span data-ttu-id="9e701-216">Office 365 郵件加密支援 Office 365 語言，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9e701-216">Office 365 Message encryption supports Office 365 languages, as follows:</span></span>  <br/>  <span data-ttu-id="9e701-217">內送電子郵件和附加的 HTML 檔案會進行當地語系化根據寄件者的語言設定。</span><span class="sxs-lookup"><span data-stu-id="9e701-217">Incoming email messages and attached HTML files are localized based on the sender's language settings.</span></span>  <br/>  <span data-ttu-id="9e701-218">檢視入口網站是根據收件者的瀏覽器設定進行當地語系化。</span><span class="sxs-lookup"><span data-stu-id="9e701-218">The viewing portal is localized based on the recipient's browser settings.</span></span>  <br/>  <span data-ttu-id="9e701-219">加密郵件的本文 (內容) 則不會進行當地語系化。</span><span class="sxs-lookup"><span data-stu-id="9e701-219">The body (content) of the encrypted message isn't localized.</span></span>  <br/> |
|<span data-ttu-id="9e701-220">OME 入口網站與 OME 檢視器應用程式的隱私權資訊</span><span class="sxs-lookup"><span data-stu-id="9e701-220">Privacy information for OME Portal and OME Viewer App</span></span>  <br/> |<span data-ttu-id="9e701-221">[Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md) 提供 Microsoft 如何處理您私人資訊的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9e701-221">The [Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md) provides detailed information about what Microsoft does and doesn't do with your private information.</span></span>  <br/> |
   
## <a name="frequently-asked-questions-about-legacy-ome"></a><span data-ttu-id="9e701-222">常見問題集舊版 OME 的相關</span><span class="sxs-lookup"><span data-stu-id="9e701-222">Frequently Asked Questions about legacy OME</span></span>
<span data-ttu-id="9e701-223"><a name="LegacyServiceInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="9e701-223"></span></span>

<span data-ttu-id="9e701-p115">取得 Office 365 郵件加密的相關問題嗎？以下是一些常見問題的解答。如果您找不到您的需要，檢查[Office 365 社群](http://community.office365.com/en-us/forums/default.aspx)在 Office 365 社群論壇。</span><span class="sxs-lookup"><span data-stu-id="9e701-p115">Got questions about Office 365 Message Encryption? Here are some answers. If you can't find what you need, check the Office 365 community forums at [Office 365 community](http://community.office365.com/en-us/forums/default.aspx).</span></span>
  
 <span data-ttu-id="9e701-227">**問我的使用者傳送加密的電子郵件給我們組織外部收件者。是否有任何外部收件者已執行動作以閱讀和回覆加密與 Office 365 郵件加密的電子郵件吗？**</span><span class="sxs-lookup"><span data-stu-id="9e701-227">**Q. My users send encrypted email messages to recipients outside our organization. Is there anything that external recipients have to do in order to read and reply to email messages that are encrypted with Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="9e701-228">組織外部的收件者收到以 Office 365 加密的電子郵件時，可以這兩種方式檢視郵件：</span><span class="sxs-lookup"><span data-stu-id="9e701-228">Recipients outside your organization who receive Office 365 encrypted messages can view them in one of two ways:</span></span>
  
- <span data-ttu-id="9e701-229">登入 Microsoft 帳戶或 Office 365 相關聯的工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="9e701-229">By signing in with a Microsoft account or a work or school account associated with Office 365.</span></span>
    
- <span data-ttu-id="9e701-230">使用 [一次性傳遞的程式碼。</span><span class="sxs-lookup"><span data-stu-id="9e701-230">By using a one-time pass code.</span></span>
    
 <span data-ttu-id="9e701-231">**問：Office 365 加密郵件是儲存於雲端或 Microsoft 伺服器上嗎？**</span><span class="sxs-lookup"><span data-stu-id="9e701-231">**Q. Are Office 365 encrypted messages stored in the cloud or on Microsoft servers?**</span></span>
  
<span data-ttu-id="9e701-p116">否，加密的郵件會在收件者的電子郵件系統，並當收件者開啟郵件時，會暫時張貼的 Office 365 的伺服器上的檢視。郵件未那里儲存。</span><span class="sxs-lookup"><span data-stu-id="9e701-p116">No, the encrypted messages are kept on the recipient's email system, and when the recipient opens the message, it is temporarily posted for viewing on Office 365 servers. The messages are not stored there.</span></span>
  
 <span data-ttu-id="9e701-234">**問：我可以使用自己的品牌自訂加密電子郵件嗎？**</span><span class="sxs-lookup"><span data-stu-id="9e701-234">**Q. Can I customize encrypted email messages with my brand?**</span></span>
  
<span data-ttu-id="9e701-p117">可以。您可以使用 Windows PowerShell Cmdlet 自訂加密電子郵件頂端顯示的預設文字、免責聲明文字，及要用於電子郵件和加密入口網站的標誌。如需詳細資訊，請參閱[Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="9e701-p117">Yes. You can use Windows PowerShell cmdlets to customize the default text that appears at the top of encrypted email messages, the disclaimer text, and the logo that you want to use for the email message and the encryption portal. For details, see [Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
 <span data-ttu-id="9e701-238">**問：我組織內每位使用者是否皆需備有服務授權？**</span><span class="sxs-lookup"><span data-stu-id="9e701-238">**Q. Does the service require a license for every user in my organization?**</span></span>
  
<span data-ttu-id="9e701-239">組織中傳送加密電子郵件的每位使用者皆需有授權。</span><span class="sxs-lookup"><span data-stu-id="9e701-239">A license is required for every user in the organization who sends encrypted email.</span></span>
  
 <span data-ttu-id="9e701-240">**問：外部收件者需要訂閱嗎？**</span><span class="sxs-lookup"><span data-stu-id="9e701-240">**Q. Do external recipients require subscriptions?**</span></span>
  
<span data-ttu-id="9e701-241">否，外部收件者不需要訂閱即可讀取或回覆加密郵件。</span><span class="sxs-lookup"><span data-stu-id="9e701-241">No, external recipients do not require a subscription to read or reply to encrypted messages.</span></span> 
  
 <span data-ttu-id="9e701-242">**問如何為 Office 365 郵件加密不同從 Rights Management Services (RMS)？**</span><span class="sxs-lookup"><span data-stu-id="9e701-242">**Q. How is Office 365 Message Encryption different from Rights Management Services (RMS)?**</span></span>
  
<span data-ttu-id="9e701-p118">RMS 提供組織內部電子郵件的資訊權限保護功能來提供內建的範本，例如： 不要轉寄和公司機密。Office 365 郵件加密支援電子郵件加密的郵件傳送至外部收件者為內部收件者。</span><span class="sxs-lookup"><span data-stu-id="9e701-p118">RMS provides Information Rights Protection capabilities for an organization's internal emails by providing built-in templates, such as: Do not forward and Company Confidential. Office 365 Message Encryption supports email message encryption for messages that are sent to external recipients as well as internal recipients.</span></span>
  
 <span data-ttu-id="9e701-245">**問如何為 Office 365 郵件加密 S/MIME 與不同？**</span><span class="sxs-lookup"><span data-stu-id="9e701-245">**Q. How is Office 365 Message Encryption different from S/MIME?**</span></span>
  
<span data-ttu-id="9e701-p119">S/MIME 基本上是一種用戶端加密技術，需要複雜的憑證管理與發佈基礎結構。Office 365 郵件加密使用傳輸規則，不需要憑證發佈。</span><span class="sxs-lookup"><span data-stu-id="9e701-p119">S/MIME is essentially a client-side encryption technology, and requires complicated certificate management and publishing infrastructure. Office 365 Message Encryption uses transport rules and does not depend on certificate publishing.</span></span>
  
 <span data-ttu-id="9e701-248">**問：我可以透過行動裝置閱讀加密郵件嗎？**</span><span class="sxs-lookup"><span data-stu-id="9e701-248">**Q. Can I read the encrypted messages over mobile devices?**</span></span>
  
<span data-ttu-id="9e701-p120">是，您可以在 Android 和 iOS 上檢視郵件可透過從[Google 播放儲存](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409)和[Apple 應用程式存放區](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409)下載 OME 檢視器應用程式。在 OME 檢視器應用程式中開啟 HTML 附件，然後遵循指示來開啟加密的郵件。其他行動裝置，您可以開啟 HTML 附件只要郵件用戶端支援 「 表單張貼。</span><span class="sxs-lookup"><span data-stu-id="9e701-p120">Yes, you can view messages on Android and iOS by downloading the OME Viewer apps from the [Google Play store](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409) and the [Apple App store](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409). Open the HTML attachment in the OME Viewer app and then follow the instructions to open your encrypted message. For other mobile devices, you can open the HTML attachment as long as your mail client supports Form Post.</span></span>
  
 <span data-ttu-id="9e701-252">**問：回覆和轉寄郵件皆會加密嗎？**</span><span class="sxs-lookup"><span data-stu-id="9e701-252">**Q. Are replies and forwarded messages encrypted?**</span></span>
  
<span data-ttu-id="9e701-p121">是的。在整個執行緒期間都會對回應持續加密。</span><span class="sxs-lookup"><span data-stu-id="9e701-p121">Yes. Responses continue to be encrypted throughout the duration of the thread.</span></span>
  
 <span data-ttu-id="9e701-255">**問：Office 365 郵件加密是否提供當地語系化？**</span><span class="sxs-lookup"><span data-stu-id="9e701-255">**Q. Does Office 365 Message Encryption provide localization?**</span></span>
  
<span data-ttu-id="9e701-p122">內送電子郵件和 HTML 內容均依據寄件者電子郵件設定進行當地語系化。檢視入口網站會依據收件者的瀏覽器設定進行當地語系化。不過，加密郵件的實際內文 (內容) 不會進行當地語系化。</span><span class="sxs-lookup"><span data-stu-id="9e701-p122">Incoming email and HTML content is localized based on sender email settings. The viewing portal is localized based on recipient's browser settings. However, the actual body (content) of encrypted message isn't localized.</span></span>
  
 <span data-ttu-id="9e701-259">**問：Office 365 郵件加密使用何種加密方法？**</span><span class="sxs-lookup"><span data-stu-id="9e701-259">**Q. What encryption method is used for Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="9e701-p123">Office 365 郵件加密使用 Rights Management Services (RMS) 做為其加密基礎結構。使用的加密方法取決於您在哪裡取得用來加密及解密郵件的 RMS 金鑰。</span><span class="sxs-lookup"><span data-stu-id="9e701-p123">Office 365 Message Encryption uses Rights Management Services (RMS) as its encryption infrastructure. The encryption method used depends on where you obtain the RMS keys used to encrypt and decrypt messages.</span></span>
  
- <span data-ttu-id="9e701-p124">如果您使用 Microsoft Azure RMS 取得金鑰，則會使用密碼編譯模式 2。密碼編譯模式 2 是更新及增強 AD RMS 密碼編譯實作。它支援 RSA 2048 簽章和加密，並支援 SHA-1 256 個簽章。</span><span class="sxs-lookup"><span data-stu-id="9e701-p124">If you use Microsoft Azure RMS to obtain the keys, Cryptographic Mode 2 is used. Cryptographic Mode 2 is an updated and enhanced AD RMS cryptographic implementation. It supports RSA 2048 for signature and encryption, and supports SHA-256 for signature.</span></span>
    
- <span data-ttu-id="9e701-p125">如果您使用 Active Directory (AD) RMS 來取得金鑰，則會使用密碼編譯模式 1 或密碼編譯模式 2。使用的方法取決於內部部署 AD RMS 部署。密碼編譯模式 1 是原始的 AD RMS 密碼編譯實作。它支援使用 RSA 1024 進行簽章和加密，也支援使用 SHA-1 進行簽章。這個模式會繼續受到 RMS 所有目前的版本支援。</span><span class="sxs-lookup"><span data-stu-id="9e701-p125">If you use Active Directory (AD) RMS to obtain the keys, either Cryptographic Mode 1 or Cryptographic Mode 2 is used. The method used depends on your on-premises AD RMS deployment. Cryptographic Mode 1 is the original AD RMS cryptographic implementation. It supports RSA 1024 for signature and encryption, and supports SHA-1 for signature. This mode continues to be supported by all current versions of RMS.</span></span>
    
<span data-ttu-id="9e701-270">如需詳細資訊，請參閱[AD RMS 密碼編譯模式](http://go.microsoft.com/fwlink/p/?LinkId=398616)。</span><span class="sxs-lookup"><span data-stu-id="9e701-270">For more information, see [AD RMS Cryptographic Modes](http://go.microsoft.com/fwlink/p/?LinkId=398616).</span></span>
  
 <span data-ttu-id="9e701-271">**問：為什麼某些加密的訊息指出其來自 Office365@messaging.microsoft.com？**</span><span class="sxs-lookup"><span data-stu-id="9e701-271">**Q. Why do some encrypted messages say they come from Office365@messaging.microsoft.com?**</span></span>
  
<span data-ttu-id="9e701-p126">從加密入口網站或透過 OME 檢視器應用程式傳送加密的回覆時，傳送方的電子郵件地址會設為 Office365@messaging.microsoft.com，因為加密的郵件是透過 Microsoft 端點傳送。這有助於避免加密的郵件被標示為垃圾郵件。因為有此標示，加密入口網站中顯示的電子郵件名稱和地址不會變更。此外，此標示只會套用到透過入口網站傳送的郵件，而不會套用到透過任何其他電子郵件用戶端傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="9e701-p126">When an encrypted reply is sent from the encryption portal or through the OME Viewer app, the sending email address is set to Office365@messaging.microsoft.com because the encrypted message is sent through a Microsoft endpoint. This helps to prevent encrypted messages from being marked as spam. The displayed name on the email and the address within the encryption portal aren't changed because of this labeling. Also, this labeling only applies to messages sent through the portal, not through any other email client.</span></span>
  
 <span data-ttu-id="9e701-276">**問 I am Exchange Hosted Encryption (EHE) 訂閱者。讓瞭解更多有關升級至 Office 365 郵件加密資訊？**</span><span class="sxs-lookup"><span data-stu-id="9e701-276">**Q. I am an Exchange Hosted Encryption (EHE) subscriber. Where can I learn more about the upgrade to Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="9e701-p127">所有的 EHE 客戶都已升級至 Office 365 郵件加密。如需詳細資訊，請造訪[Exchange 託管加密升級中心](http://go.microsoft.com/fwlink/p/?LinkID=511077)。</span><span class="sxs-lookup"><span data-stu-id="9e701-p127">All EHE customers have been upgraded to Office 365 Message Encryption. For more information, visit the [Exchange Hosted Encryption Upgrade Center](http://go.microsoft.com/fwlink/p/?LinkID=511077).</span></span>
  
 <span data-ttu-id="9e701-279">**問： 我需要的開啟任何 Url、 IP 位址，或在我的組織防火牆連接埠以支援 Office 365 郵件加密吗？**</span><span class="sxs-lookup"><span data-stu-id="9e701-279">**Q. Do I need to open any URLs, IP addresses, or ports in my organization's firewall to support Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="9e701-p128">是的。您必須將 Exchange Online 的 URL 新增到您組織的允許清單中，才能為 Office 365 郵件加密所加密的郵件啟用驗證。如需 Exchange Online URL 的清單，請參閱 [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9e701-p128">Yes. You have to add URLs for Exchange Online to the allow list for your organization to enable authentication for messages encrypted by Office 365 Message Encryption. For a list of Exchange Online URLs, see [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx).</span></span>
  
 <span data-ttu-id="9e701-283">**問：我可以將 Office 365 加密郵件傳送給多少位收件者？**</span><span class="sxs-lookup"><span data-stu-id="9e701-283">**Q. How many recipients can I send an Office 365 encrypted message to?**</span></span>
  
<span data-ttu-id="9e701-p129">加密郵件的收件者限制為基礎的**郵件] 欄位**中的字元數。當合併 （之後通訊群組清單延伸），在**欄位中**的收件者地址不應該超過 11,980 字元。因為的字元長度變化多端電子郵件地址，有不標準的收件者限制為單一加密郵件。</span><span class="sxs-lookup"><span data-stu-id="9e701-p129">The recipient limit for an encrypted message is based on the number of characters in the message's **To** field. When combined (after distribution list expansion), recipient addresses in the **To** field should not exceed 11,980 characters. Because email addresses can vary in character length, there isn't a standard recipient limit for a single encrypted message.</span></span> 
  
 <span data-ttu-id="9e701-287">**問：是否可以撤銷傳送給特定收件者的郵件？**</span><span class="sxs-lookup"><span data-stu-id="9e701-287">**Q. Is it possible to revoke a message sent to a particular recipient?**</span></span>
  
<span data-ttu-id="9e701-p130">[否]。您不能撤銷權限給特定人員訊息之後傳送中。</span><span class="sxs-lookup"><span data-stu-id="9e701-p130">No. You can't revoke a message to a particular person after it's sent.</span></span>
  
 <span data-ttu-id="9e701-290">**問：是否可以檢視已接收和讀取的加密郵件的報表？**</span><span class="sxs-lookup"><span data-stu-id="9e701-290">**Q. Can I view a report of encrypted messages that have been received and read?**</span></span>
  
<span data-ttu-id="9e701-291">沒有顯示報告，如果已經檢視加密的郵件，但有 Office 365 報告提供您可以運用來決定符合特定傳輸規則，例如的訊息數。</span><span class="sxs-lookup"><span data-stu-id="9e701-291">There isn't a report that shows if an encrypted message has been viewed, but there are Office 365 reports available that you can leverage to determine the number of messages that matched a specific transport rule, for instance.</span></span>
  
 <span data-ttu-id="9e701-292">**問：Microsoft 會如何利用透過 OME 入口網站和 OME 檢視器應用程式所取得我的資訊？**</span><span class="sxs-lookup"><span data-stu-id="9e701-292">**Q. What does Microsoft do with the information I provide through the OME Portal and the OME Viewer App?**</span></span>
  
<span data-ttu-id="9e701-293">[Office 365 郵件加密入口網站隱私權聲明](protected-message-viewer-portal-privacy-statement.md)提供 Microsoft 與目的沒有透過私人資訊的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="9e701-293">The [Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md) provides detailed information about what Microsoft does and doesn't do with your private information.</span></span> 
  

