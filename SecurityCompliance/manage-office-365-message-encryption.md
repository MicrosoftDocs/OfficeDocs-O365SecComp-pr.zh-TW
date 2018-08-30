---
title: 管理 Office 365 郵件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
description: 您已完成設定 up Office 365 郵件加密 (OME)，您可以自訂在數種方式部署的設定。例如，您可以設定是否要啟用一次性複雜代碼、 網頁伺服器與多上的 Outlook 中顯示 [保護] 按鈕。本文中的工作說明如何。
ms.openlocfilehash: ddc86bdf0d0ce5480587862a4ed438b6c138987f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526491"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="34386-105">管理 Office 365 郵件加密</span><span class="sxs-lookup"><span data-stu-id="34386-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="34386-p102">您已完成設定 up Office 365 郵件加密 (OME)，您可以自訂在數種方式部署的設定。例如，您可以設定是否要啟用一次性複雜代碼、 網頁伺服器與多上的 Outlook 中顯示 [**保護**] 按鈕。本文中的工作說明如何。</span><span class="sxs-lookup"><span data-stu-id="34386-p102">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in a number of ways. For example, you can configure whether to enable one-time pass codes, display the **Protect** button in Outlook on the web, and more. The tasks in this article describe how.</span></span> 
  
||
|:-----|
|<span data-ttu-id="34386-p103">本文屬於較大的一系列有關 Office 365 郵件加密的文章。本文適用於系統管理員及 IT 專業人員的。如果您只尋找的資訊在傳送或接收加密的郵件，請參閱[Office 365 郵件加密 (OME)](ome.md)中的文章的清單並找出最適合您需求的文章。</span><span class="sxs-lookup"><span data-stu-id="34386-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and IT Pros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
   
## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="34386-112">管理是否 Google、 Yahoo、 及 Microsoft 帳戶的收件者可以使用這些帳戶來登入 Office 365 郵件加密入口網站</span><span class="sxs-lookup"><span data-stu-id="34386-112">Managing whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>
<span data-ttu-id="34386-113"><a name="PermitSocialID"> </a></span><span class="sxs-lookup"><span data-stu-id="34386-113"></span></span>

<span data-ttu-id="34386-p104">根據預設，當您設定新的 Office 365 郵件加密功能，您組織中的使用者可以傳送郵件給 Office 365 組織外收件者。收件者若收件者使用*社交識別碼*例如 Google 帳戶、 Yahoo 帳戶或 Microsoft 帳戶，則可以登入 OME 入口網站使用社交 id。如果您想您可以選擇不允許使用社交識別碼來登入 OME 入口網站的收件者。</span><span class="sxs-lookup"><span data-stu-id="34386-p104">By default, when you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization. If the recipient uses a  *social ID*  such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal using the social ID. If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span> 
  
 <span data-ttu-id="34386-117">**若要管理要允許使用社交識別碼來登入 OME 入口網站的收件者**</span><span class="sxs-lookup"><span data-stu-id="34386-117">**To manage whether or not to allow recipients to use social IDs to sign in to the OME portal**</span></span>
  
1. <span data-ttu-id="34386-118">[連線至 Exchange Online 使用遠端 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="34386-118">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="34386-119">執行 Set-omeconfiguration 指令程式搭配 SocialIdSignIn 參數如下所示：</span><span class="sxs-lookup"><span data-stu-id="34386-119">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>
    
  ```
  Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true |$false >
  ```

    <span data-ttu-id="34386-120">例如，若要停用社交 Id：</span><span class="sxs-lookup"><span data-stu-id="34386-120">For example, to disable social IDs:</span></span>
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
  ```

    <span data-ttu-id="34386-121">若要啟用社交 Id：</span><span class="sxs-lookup"><span data-stu-id="34386-121">To enable social IDs:</span></span>
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
  ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="34386-122">管理一次性複雜代碼用於登入 Office 365 郵件加密入口網站</span><span class="sxs-lookup"><span data-stu-id="34386-122">Managing the use of one-time pass codes for signing in to the Office 365 Message Encryption portal</span></span>
<span data-ttu-id="34386-123"><a name="GenerateOTPC"> </a></span><span class="sxs-lookup"><span data-stu-id="34386-123"></span></span>

<span data-ttu-id="34386-p105">根據預設，如果依 OME 加密郵件的收件者不使用 Outlook，不論收件者，所使用的帳戶收件者會收到讓讀取郵件的時間限制 web 檢視連結。這包括一次性複雜的程式碼。以系統管理員可以管理一次性複雜碼可用來登入 OME 入口網站。</span><span class="sxs-lookup"><span data-stu-id="34386-p105">By default, if the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message. This includes a one-time pass code. As an administrator, you can manage whether or not one-time pass codes can be used to sign-in to the OME portal.</span></span>
  
 <span data-ttu-id="34386-127">**若要管理一次性複雜的程式碼產生的 OME**</span><span class="sxs-lookup"><span data-stu-id="34386-127">**To manage whether or not one-time pass codes are generated for OME**</span></span>
  
1. <span data-ttu-id="34386-128">[連線至 Exchange Online 使用遠端 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="34386-128">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="34386-129">執行 Set-omeconfiguration 指令程式搭配 OTPEnabled 參數如下所示：</span><span class="sxs-lookup"><span data-stu-id="34386-129">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter as follows:</span></span>
    
  ```
  Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true |$false >
  ```

    <span data-ttu-id="34386-130">例如，若要停用一次性複雜的程式碼：</span><span class="sxs-lookup"><span data-stu-id="34386-130">For example, to disable one-time pass codes:</span></span>
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
  ```

    <span data-ttu-id="34386-131">若要啟用一次性複雜的程式碼：</span><span class="sxs-lookup"><span data-stu-id="34386-131">To enable one-time pass codes:</span></span>
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
  ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a><span data-ttu-id="34386-132">管理 Outlook web 上的 [保護] 按鈕的顯示</span><span class="sxs-lookup"><span data-stu-id="34386-132">Managing the display of the Protect button in Outlook on the web</span></span>
<span data-ttu-id="34386-133"><a name="DisplayProtectButton"> </a></span><span class="sxs-lookup"><span data-stu-id="34386-133"></span></span>

<span data-ttu-id="34386-p106">根據預設，在網路上的 Outlook [**保護**] 按鈕未啟用設定 OME 時。以系統管理員可以管理要對使用者顯示此按鈕。</span><span class="sxs-lookup"><span data-stu-id="34386-p106">By default, the **Protect** button in Outlook on the web is not enabled when you set up OME. As an administrator, you can manage whether or not to display this button to end users.</span></span> 
  
 <span data-ttu-id="34386-136">**若要管理 [保護] 按鈕會出現在網路上的 Outlook**</span><span class="sxs-lookup"><span data-stu-id="34386-136">**To manage whether or not the Protect button appears in Outlook on the web**</span></span>
  
1. <span data-ttu-id="34386-137">[連線至 Exchange Online 使用遠端 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="34386-137">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="34386-138">執行 Set-irmconfiguration 指令程式搭配-SimplifiedClientAccessEnabled 參數如下所示：</span><span class="sxs-lookup"><span data-stu-id="34386-138">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter as follows:</span></span>
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true |$false >
  ```

    <span data-ttu-id="34386-139">例如，若要停用 [**保護**] 按鈕：</span><span class="sxs-lookup"><span data-stu-id="34386-139">For example, to disable the **Protect** button:</span></span> 
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
  ```

    <span data-ttu-id="34386-140">若要啟用 [**保護**] 按鈕：</span><span class="sxs-lookup"><span data-stu-id="34386-140">To enable the **Protect** button:</span></span> 
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
  ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="34386-141">啟用服務端解密的 iOS 郵件應用程式使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="34386-141">Enable service-side decryption of email messages for iOS mail app users</span></span>
<span data-ttu-id="34386-142"><a name="EnableServiceSideDecrypt"> </a></span><span class="sxs-lookup"><span data-stu-id="34386-142"></span></span>

<span data-ttu-id="34386-p107">IOS 郵件應用程式無法解密受保護與 Office 365 郵件加密的郵件。身為 Office 365 管理員，您可以套用服務端解密的郵件傳遞至 iOS 郵件應用程式。當您選擇這樣做時，服務會將已解密的郵件複本傳送至 iOS 裝置。郵件會儲存在用戶端裝置上解密。即使 iOS 郵件應用程式不會套用至使用者的用戶端使用權限訊息也會保留 usage 權限的相關資訊。這表示使用者可以複製或列印郵件即使因原本沒有要執行這項操作的權限。不過，如果使用者嘗試完成需要 Office 365 的郵件伺服器，例如轉寄郵件的動作，伺服器不如果使用者原本沒有這樣的 usage 權限允許巨集指令。不過，使用者可以藉由轉寄的郵件不論是否設定服務端解密的郵件其 iOS 郵件 app 中的不同帳戶時解決不要轉寄流量限制、 任何附件加密和權限受保護的郵件無法檢視 iOS 郵件應用程式中。</span><span class="sxs-lookup"><span data-stu-id="34386-p107">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption. As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app. When you choose to do this, the service sends a decrypted copy of the message to the iOS device. The message is stored decrypted on the client device. The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user. This means that the user can copy or print the message even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server will not permit the action if the user did not originally have the usage right to do so. However, end-users can work around Do Not Forward usage restriction by forwarding the message from a different account in their iOS mail app. Regardless of whether you set up service-side decryption of mail, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="34386-p108">如果您選擇不要允許解密的郵件傳送至 iOS 郵件應用程式的使用者，使用者會收到訊息表示它們不需要檢視郵件的權限。根據預設，未啟用服務端解密的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="34386-p108">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message. By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="34386-154">如需詳細資訊及用戶端體驗的檢視，請參閱] 區段中，在[檢視加密的郵件 iPhone 或 iPad 上](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)的 「[檢視加密的郵件 iPhone 或 iPad 上](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf#iOSEncryptedMail)」。</span><span class="sxs-lookup"><span data-stu-id="34386-154">For more information, and for a view of the client experience, see the section, "[View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf#iOSEncryptedMail)" in [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
 <span data-ttu-id="34386-155">**若要管理 iOS 郵件應用程式的使用者可以檢視受保護之 Office 365 郵件加密的郵件**</span><span class="sxs-lookup"><span data-stu-id="34386-155">**To manage whether or not iOS mail app users can view messages protected by Office 365 Message Encryption**</span></span>
  
1. <span data-ttu-id="34386-156">[連線至 Exchange Online 使用遠端 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="34386-156">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="34386-157">執行設定 ActiveSyncOrganizations 指令程式搭配 AllowRMSSupportForUnenlightenedApps 參數如下所示：</span><span class="sxs-lookup"><span data-stu-id="34386-157">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter as follows:</span></span>
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true |$false >
  ```

    <span data-ttu-id="34386-158">例如，若要設定解密的郵件前它們傳送到 unenlightened 應用程式的服務例如 iOS 郵件應用程式：</span><span class="sxs-lookup"><span data-stu-id="34386-158">For example, to configure the service to decrypt messages before they are sent to unenlightened apps such as the iOS mail app:</span></span>
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
  ```

    <span data-ttu-id="34386-159">例如，若要設定服務未將解密的郵件傳送至 unenlightened 應用程式：</span><span class="sxs-lookup"><span data-stu-id="34386-159">For example, to configure the service not to send decrypted messages to unenlightened apps:</span></span>
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
  ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="34386-160">啟用服務端解密的網頁瀏覽器郵件用戶端的電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="34386-160">Enable service-side decryption of email attachments for web browser mail clients</span></span>
<span data-ttu-id="34386-161"><a name="EnableServiceSideDecrypt"> </a></span><span class="sxs-lookup"><span data-stu-id="34386-161"></span></span>

<span data-ttu-id="34386-p109">一般而言，當您使用 Office 365 郵件加密時，會自動加密附件。Office 365 系統管理員身分您可以套用服務端解密使用者下載從網頁瀏覽器中的電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="34386-p109">Normally, when you use Office 365 message encryption, attachments are automatically encrypted. As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span> 
  
<span data-ttu-id="34386-p110">當您選擇這樣做時，服務會將解密檔案的複本傳送至裝置。仍處於加密郵件。即使在瀏覽器不會套用至使用者的用戶端使用權限電子郵件附件也會保留 usage 權限的相關資訊。這表示使用者可以複製或列印電子郵件附件即使因原本沒有要執行這項操作的權限。但如果使用者嘗試完成動作所需的 Office 365 郵件伺服器，例如轉寄附件，伺服器不如果使用者原本沒有這樣的 usage 權限允許巨集指令。</span><span class="sxs-lookup"><span data-stu-id="34386-p110">When you choose to do this, the service sends a decrypted copy of the file to the device. The message is still encrypted. The email attachment also retains information about usage rights even though the browser does not apply client-side usage rights to the user. This means that the user can copy or print the email attachment even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server will not permit the action if the user did not originally have the usage right to do so.</span></span>
  
<span data-ttu-id="34386-169">不論是否您設定服務端解密的附件，任何附件的加密和權限受保護的郵件無法 iOS 郵件應用程式中檢視。</span><span class="sxs-lookup"><span data-stu-id="34386-169">Regardless of whether you set up service-side decryption of attachments, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="34386-p111">如果您選擇不要允許解密電子郵件附件，這是預設值，使用者會收到訊息表示它們不需要檢視附件的權限。\* \* \*插入圖片吗？</span><span class="sxs-lookup"><span data-stu-id="34386-p111">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment. \*\*\* insert picture?</span></span>
  
<span data-ttu-id="34386-172">如需 Office 365 如何實作加密電子郵件及電子郵件附件的加密唯讀] 選項的詳細資訊，請參閱[僅限加密的電子郵件選項。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="34386-172">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
 <span data-ttu-id="34386-173">**若要管理電子郵件附件進行解密上從網頁瀏覽器的下載 （英文）**</span><span class="sxs-lookup"><span data-stu-id="34386-173">**To manage whether or not email attachments are decrypted on download from a web browser**</span></span>
  
1. <span data-ttu-id="34386-174">[連線至 Exchange Online 使用遠端 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="34386-174">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="34386-175">執行 Set-irmconfiguration 指令程式搭配 DecryptAttachmentFromPortal 參數如下所示：</span><span class="sxs-lookup"><span data-stu-id="34386-175">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter as follows:</span></span>
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal <$true |$false >
  ```

    <span data-ttu-id="34386-176">例如，服務設定為解密電子郵件附件時使用者下載這些從網頁瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="34386-176">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal $true
  ```

    <span data-ttu-id="34386-177">若要設定為它們在下載時保留加密的電子郵件附件服務：</span><span class="sxs-lookup"><span data-stu-id="34386-177">To configure the service to leave encrypted email attachments as they are upon download:</span></span>
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal $false
  ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="34386-178">自訂電子郵件和 OME 入口網站的外觀</span><span class="sxs-lookup"><span data-stu-id="34386-178">Customizing the appearance of email messages and the OME portal</span></span>
<span data-ttu-id="34386-179"><a name="CustomizeAppearance"> </a></span><span class="sxs-lookup"><span data-stu-id="34386-179"></span></span>

<span data-ttu-id="34386-180">如需如何自訂 OME 組織的詳細資訊，請參閱[新增至您已加密郵件的貴組織的商標](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="34386-180">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disabling-the-new-capabilities-for-ome"></a><span data-ttu-id="34386-181">停用的新功能以進行 OME</span><span class="sxs-lookup"><span data-stu-id="34386-181">Disabling the new capabilities for OME</span></span>
<span data-ttu-id="34386-182"><a name="CustomizeAppearance"> </a></span><span class="sxs-lookup"><span data-stu-id="34386-182"></span></span>

<span data-ttu-id="34386-p112">我們希望它不會跳到其中，但如果您需要、 OME 非常簡單停用的新功能。首先，您需要移除任何郵件流程而建立的規則已使用新的 OME 功能。如需移除郵件流程規則的資訊，請參閱[管理郵件流程規則](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)。然後，完成這些步驟在 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="34386-p112">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward. First, you'll need to remove any mail flow rules you've created that use the new OME capabilities. For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Then, complete these steps in Exchange Online PowerShell.</span></span>
  
 <span data-ttu-id="34386-187">**針對 OME 停用的新功能**</span><span class="sxs-lookup"><span data-stu-id="34386-187">**To disable the new capabilities for OME**</span></span>
  
1. <span data-ttu-id="34386-188">[連線至 Exchange Online 使用遠端 PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="34386-188">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).</span></span>
    
2. <span data-ttu-id="34386-189">如果您啟用的網路上的 Outlook [保護] 按鈕，停用它使用來執行 Set-irmconfiguration 指令程式 SimplifiedClientAccessEnabled 參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="34386-189">If you enabled the Protect button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter as follows:</span></span>
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
  ```

3. <span data-ttu-id="34386-190">執行 Set-irmconfiguration 指令程式搭配 AzureRMSLicensingEnabled 參數如下所示：</span><span class="sxs-lookup"><span data-stu-id="34386-190">Run the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter as follows:</span></span>
    
  ```
  Set-IRMConfiguration -AzureRMSLicensingEnabled $false
  ```


