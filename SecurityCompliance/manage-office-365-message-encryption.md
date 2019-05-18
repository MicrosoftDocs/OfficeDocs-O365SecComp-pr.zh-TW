---
title: 管理 Office 365 郵件加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 一旦您已經完成設定 up Office 365 郵件加密 (OME)，您可以自訂您的部署，以數種方式的設定。 例如，您可以設定是否要啟用一次性複雜代碼，顯示在網頁伺服器和多個 outlook 的 [保護] 按鈕。 本文中的任務說明如何。
ms.openlocfilehash: 5c498c648fb28e6538bfc2fde8bdf50e8e02cbfc
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155745"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="c19c4-105">管理 Office 365 郵件加密</span><span class="sxs-lookup"><span data-stu-id="c19c4-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="c19c4-106">一旦您已經完成設定 up Office 365 郵件加密 (OME)，您可以自訂您的部署，以數種方式的設定。</span><span class="sxs-lookup"><span data-stu-id="c19c4-106">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="c19c4-107">例如，您可以設定是否要啟用一次性複雜代碼，顯示在網頁伺服器和多個 outlook 的 [**保護**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c19c4-107">For example, you can configure whether to enable one-time pass codes, display the **Protect** button in Outlook on the web, and more.</span></span> <span data-ttu-id="c19c4-108">本文中的任務說明如何。</span><span class="sxs-lookup"><span data-stu-id="c19c4-108">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="c19c4-109">管理是否 Google、 Yahoo，以及 Microsoft 帳戶的收件者可以使用這些帳戶來登入 Office 365 郵件加密入口網站</span><span class="sxs-lookup"><span data-stu-id="c19c4-109">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="c19c4-110">當您設定新的 Office 365 郵件加密功能時，您組織中的使用者可以傳送郵件給您的 Office 365 組織外的收件者。</span><span class="sxs-lookup"><span data-stu-id="c19c4-110">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization.</span></span> <span data-ttu-id="c19c4-111">收件者如果收件者使用*社交識別碼*，例如 Google 帳戶、 Yahoo 帳戶或 Microsoft 帳戶，可以登入到具有社交識別碼 OME 入口網站</span><span class="sxs-lookup"><span data-stu-id="c19c4-111">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="c19c4-112">如果您想，您可以選擇不允許使用社交識別碼來登入 OME 入口網站的收件者。</span><span class="sxs-lookup"><span data-stu-id="c19c4-112">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="c19c4-113">若要管理是否收件者可以使用社交識別碼登入 OME 入口網站</span><span class="sxs-lookup"><span data-stu-id="c19c4-113">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="c19c4-114">[連線至 Exchange Online 使用遠端 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c19c4-114">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="c19c4-115">執行 Set-omeconfiguration 指令程式搭配 SocialIdSignIn 參數如下所示：</span><span class="sxs-lookup"><span data-stu-id="c19c4-115">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="c19c4-116">例如，若要停用社交識別碼：</span><span class="sxs-lookup"><span data-stu-id="c19c4-116">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="c19c4-117">若要啟用社交識別碼：</span><span class="sxs-lookup"><span data-stu-id="c19c4-117">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="c19c4-118">管理次傳遞代碼用於 Office 365 郵件加密入口網站</span><span class="sxs-lookup"><span data-stu-id="c19c4-118">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="c19c4-119">如果由 OME 加密郵件的收件者不會使用 Outlook，無論收件者所使用的帳戶，收件者會收到一個時間有限 web 檢視連結，讓他們在閱讀郵件。</span><span class="sxs-lookup"><span data-stu-id="c19c4-119">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="c19c4-120">此連結，包括一次性複雜的程式碼。</span><span class="sxs-lookup"><span data-stu-id="c19c4-120">This link includes a one-time pass code.</span></span> <span data-ttu-id="c19c4-121">身為管理員，您可以決定收件者是否可以使用次傳遞代碼來登入 OME 入口網站。</span><span class="sxs-lookup"><span data-stu-id="c19c4-121">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="c19c4-122">若要管理是否 OME 產生次傳遞代碼</span><span class="sxs-lookup"><span data-stu-id="c19c4-122">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="c19c4-123">使用公司或學校帳戶具有您 Office 365 組織中的全域系統管理員權限啟動 Windows PowerShell 工作階段並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c19c4-123">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c19c4-124">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="c19c4-124">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="c19c4-125">執行 Set-omeconfiguration 指令程式搭配 OTPEnabled 參數：</span><span class="sxs-lookup"><span data-stu-id="c19c4-125">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="c19c4-126">例如，若要停用一次性複雜代碼：</span><span class="sxs-lookup"><span data-stu-id="c19c4-126">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="c19c4-127">若要啟用一次性複雜代碼：</span><span class="sxs-lookup"><span data-stu-id="c19c4-127">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-protect-button-in-outlook-on-the-web"></a><span data-ttu-id="c19c4-128">管理網頁型 Outlook 中的 [保護] 按鈕的顯示</span><span class="sxs-lookup"><span data-stu-id="c19c4-128">Manage the display of the Protect button in Outlook on the web</span></span>

<span data-ttu-id="c19c4-129">當您設定 OME 時，會停用網頁型 Outlook 中的 [**保護**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c19c4-129">The **Protect** button in Outlook on the web is disabled when you set up OME.</span></span> <span data-ttu-id="c19c4-130">身為管理員，您可以管理是否要對使用者顯示此按鈕。</span><span class="sxs-lookup"><span data-stu-id="c19c4-130">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-protect-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="c19c4-131">若要管理是否 [保護] 按鈕會出現在 outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="c19c4-131">To manage whether the Protect button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="c19c4-132">使用公司或學校帳戶具有您 Office 365 組織中的全域系統管理員權限啟動 Windows PowerShell 工作階段並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c19c4-132">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c19c4-133">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="c19c4-133">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="c19c4-134">執行 Set-irmconfiguration 指令程式搭配-SimplifiedClientAccessEnabled 參數：</span><span class="sxs-lookup"><span data-stu-id="c19c4-134">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="c19c4-135">例如，若要停用 [**保護**] 按鈕：</span><span class="sxs-lookup"><span data-stu-id="c19c4-135">For example, to disable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="c19c4-136">若要啟用 [**保護**] 按鈕：</span><span class="sxs-lookup"><span data-stu-id="c19c4-136">To enable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="c19c4-137">啟用服務端解密的郵件應用程式的 iOS 使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="c19c4-137">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="c19c4-138">Ios 電子郵件應用程式無法解密郵件以 Office 365 郵件加密來保護。</span><span class="sxs-lookup"><span data-stu-id="c19c4-138">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="c19c4-139">是 Office 365 系統管理員，您可以套用服務端解密的郵件傳遞至 ios 電子郵件應用程式。</span><span class="sxs-lookup"><span data-stu-id="c19c4-139">As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="c19c4-140">當您選擇不要使用服務端解密時，服務會將已解密的郵件複本傳送至 iOS 裝置。</span><span class="sxs-lookup"><span data-stu-id="c19c4-140">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="c19c4-141">用戶端裝置儲存解密郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="c19c4-141">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="c19c4-142">郵件也會保留使用權限的相關資訊，即使 ios 電子郵件應用程式不會套用至使用者的用戶端使用權限。</span><span class="sxs-lookup"><span data-stu-id="c19c4-142">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="c19c4-143">使用者可以複製或列印郵件，即使他們原本沒有要執行這項操作的權限。</span><span class="sxs-lookup"><span data-stu-id="c19c4-143">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="c19c4-144">然而，如果使用者嘗試完成的動作需要 Office 365 的郵件伺服器，例如轉寄郵件，伺服器不會允許動作如果使用者原本沒有使用權若要這麼做。</span><span class="sxs-lookup"><span data-stu-id="c19c4-144">However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="c19c4-145">不過，使用者可以解決 「 不要轉寄 」 流量限制郵件轉寄 ios 電子郵件應用程式內的不同帳戶。</span><span class="sxs-lookup"><span data-stu-id="c19c4-145">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="c19c4-146">不論是否您設定服務端解密的郵件，附件加密，而且無法在 ios 電子郵件應用程式中檢視權限受保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="c19c4-146">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="c19c4-147">如果您選擇不要讓解密的郵件傳送至 iOS 郵件應用程式的使用者，使用者會收到訊息，指出他們沒有檢視郵件的權限。</span><span class="sxs-lookup"><span data-stu-id="c19c4-147">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="c19c4-148">根據預設，未啟用服務端解密的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="c19c4-148">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="c19c4-149">如需詳細資訊，以及用戶端體驗的檢視，請參閱[檢視加密的郵件在 iPhone 或 iPad 上](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)。</span><span class="sxs-lookup"><span data-stu-id="c19c4-149">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="c19c4-150">若要管理 iOS 郵件應用程式的使用者是否可以檢視受保護的 Office 365 郵件加密的郵件</span><span class="sxs-lookup"><span data-stu-id="c19c4-150">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="c19c4-151">使用公司或學校帳戶具有您 Office 365 組織中的全域系統管理員權限啟動 Windows PowerShell 工作階段並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c19c4-151">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c19c4-152">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="c19c4-152">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="c19c4-153">使用 AllowRMSSupportForUnenlightenedApps 參數執行設定 ActiveSyncOrganizations 指令程式：</span><span class="sxs-lookup"><span data-stu-id="c19c4-153">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="c19c4-154">例如，若要設定服務，以解密郵件之前，傳送給 unenlightened 應用程式如 iOS 郵件應用程式：</span><span class="sxs-lookup"><span data-stu-id="c19c4-154">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="c19c4-155">或者，若要設定服務未以解密的郵件傳送至 unenlightened 應用程式：</span><span class="sxs-lookup"><span data-stu-id="c19c4-155">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="c19c4-156">啟用服務端解密的網頁瀏覽器郵件用戶端的電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="c19c4-156">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="c19c4-157">一般而言，當您使用 Office 365 郵件加密時，會自動加密附件。</span><span class="sxs-lookup"><span data-stu-id="c19c4-157">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="c19c4-158">是 Office 365 系統管理員，您可以套用使用者從網頁瀏覽器下載的電子郵件附件的服務端的解密。</span><span class="sxs-lookup"><span data-stu-id="c19c4-158">As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="c19c4-159">當您使用服務端解密時，服務會將解密該檔案的複本傳送到裝置。</span><span class="sxs-lookup"><span data-stu-id="c19c4-159">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="c19c4-160">仍處於加密郵件。</span><span class="sxs-lookup"><span data-stu-id="c19c4-160">The message is still encrypted.</span></span> <span data-ttu-id="c19c4-161">電子郵件附件也會保留使用權限的相關資訊，即使在瀏覽器不會套用至使用者的用戶端使用權限。</span><span class="sxs-lookup"><span data-stu-id="c19c4-161">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="c19c4-162">使用者可以複製或列印的電子郵件附件，即使他們原本沒有要執行這項操作的權限。</span><span class="sxs-lookup"><span data-stu-id="c19c4-162">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="c19c4-163">然而，如果使用者嘗試完成的動作需要 Office 365 的郵件伺服器，例如轉寄附件，伺服器不會允許動作如果使用者原本沒有使用權若要這麼做。</span><span class="sxs-lookup"><span data-stu-id="c19c4-163">However, if the user tries to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="c19c4-164">不論是否您設定服務端解密的附件，使用者無法檢視加密的任何附件和權限保護郵件中 iOS 郵件應用程式。</span><span class="sxs-lookup"><span data-stu-id="c19c4-164">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="c19c4-165">如果您選擇不要允許解密電子郵件附件，也就是預設值，使用者會收到訊息，指出他們沒有檢視附件的權限。</span><span class="sxs-lookup"><span data-stu-id="c19c4-165">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="c19c4-166">如需有關 Office 365 如何實作加密的電子郵件和電子郵件附件的加密唯讀] 選項的詳細資訊，請參閱[僅限加密的電子郵件選項。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="c19c4-166">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="c19c4-167">若要管理是否電子郵件附件進行解密上從網頁瀏覽器下載</span><span class="sxs-lookup"><span data-stu-id="c19c4-167">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="c19c4-168">使用公司或學校帳戶具有您 Office 365 組織中的全域系統管理員權限啟動 Windows PowerShell 工作階段並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c19c4-168">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c19c4-169">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="c19c4-169">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="c19c4-170">執行 Set-irmconfiguration 指令程式搭配 DecryptAttachmentFromPortal 參數：</span><span class="sxs-lookup"><span data-stu-id="c19c4-170">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="c19c4-171">例如，若要設定服務，以解密電子郵件附件當使用者下載其從網頁瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="c19c4-171">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="c19c4-172">若要設定要保留加密的電子郵件附件，因為它們是在下載時的服務：</span><span class="sxs-lookup"><span data-stu-id="c19c4-172">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only"></a><span data-ttu-id="c19c4-173">請確定所有外部收件者讀取加密的郵件使用 OME 入口網站-Office 365 進階郵件加密僅</span><span class="sxs-lookup"><span data-stu-id="c19c4-173">Ensure all external recipients use the OME Portal to read encrypted mail — Office 365 Advanced Message Encryption only</span></span>

<span data-ttu-id="c19c4-174">如果您有 Office 365 進階郵件加密，您可以使用自訂品牌的範本，若要強制接收指示它們讀取加密的電子郵件，而不是使用 Outlook 或網頁型 Outlook OME 入口網站中的包裝函式郵件的收件者。</span><span class="sxs-lookup"><span data-stu-id="c19c4-174">If you have Office 365 Advanced Message Encryption, you can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="c19c4-175">您可能想要這麼做，如果您使用想接收更能掌控收件者如何使用郵件。</span><span class="sxs-lookup"><span data-stu-id="c19c4-175">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="c19c4-176">例如，如果外部收件者在入口網站中檢視電子郵件，您可以設定到期日的電子郵件，而您可以撤銷電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c19c4-176">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="c19c4-177">透過 OME 入口網站僅支援這些功能。</span><span class="sxs-lookup"><span data-stu-id="c19c4-177">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="c19c4-178">建立郵件流程規則時，您可以使用加密選項和 [不要轉寄] 選項。</span><span class="sxs-lookup"><span data-stu-id="c19c4-178">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="create-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email-to-be-revocable-and-expire-in-7-days"></a><span data-ttu-id="c19c4-179">建立自訂的範本，以便強制所有外部的收件者使用 OME 入口網站及加密的電子郵件可撤銷之和 7 天內到期</span><span class="sxs-lookup"><span data-stu-id="c19c4-179">Create a custom template to force all external recipients to use the OME Portal and for encrypted email to be revocable and expire in 7 days</span></span>

1. <span data-ttu-id="c19c4-180">使用公司或學校帳戶具有您 Office 365 組織中的全域系統管理員權限啟動 Windows PowerShell 工作階段並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c19c4-180">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c19c4-181">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="c19c4-181">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="c19c4-182">執行新增 Set-omeconfiguration cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c19c4-182">Run the New-OMEConfiguration cmdlet:</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<template name>" -ExternalMailExpiryInDays 7
   ```

   <span data-ttu-id="c19c4-183">其中`template name`是您想要用於 Office 365 郵件加密的自訂品牌範本的名稱。</span><span class="sxs-lookup"><span data-stu-id="c19c4-183">where `template name` is the name you want to use for the Office 365 Message Encryption custom branding template.</span></span> <span data-ttu-id="c19c4-184">For example,</span><span class="sxs-lookup"><span data-stu-id="c19c4-184">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<One week expiration>" -ExternalMailExpiryInDays 7
   ```

3. <span data-ttu-id="c19c4-185">執行 New-transportrule 指令程式：</span><span class="sxs-lookup"><span data-stu-id="c19c4-185">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="c19c4-186">其中：</span><span class="sxs-lookup"><span data-stu-id="c19c4-186">where:</span></span>

   - <span data-ttu-id="c19c4-187">`mail flow rule name`是您想要用於新的郵件流程規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="c19c4-187">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="c19c4-188">`option name`是`Encrypt`或`Do Not Forward`。</span><span class="sxs-lookup"><span data-stu-id="c19c4-188">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="c19c4-189">`template name`是您命名的自訂品牌的範本，例如`One week expiration`。</span><span class="sxs-lookup"><span data-stu-id="c19c4-189">`template name` is the name you gave the custom branding template, for example `One week expiration`.</span></span>

   <span data-ttu-id="c19c4-190">若要加密與 「 一週到期 」 範本的所有外部電子郵件並套用加密唯讀選項：</span><span class="sxs-lookup"><span data-stu-id="c19c4-190">To encrypt all external email with the "One week expiration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

   <span data-ttu-id="c19c4-191">若要加密與 「 一週到期 」 範本的所有外部電子郵件，並套用 [不要轉寄] 選項：</span><span class="sxs-lookup"><span data-stu-id="c19c4-191">To encrypt all external email with the "One week expiration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="c19c4-192">自訂電子郵件訊息和 OME 入口網站的外觀</span><span class="sxs-lookup"><span data-stu-id="c19c4-192">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="c19c4-193">如需如何自訂 OME 組織的詳細資訊，請參閱[新增至加密郵件的貴組織的品牌](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="c19c4-193">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="c19c4-194">停用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="c19c4-194">Disable the new capabilities for OME</span></span>

<span data-ttu-id="c19c4-195">我們希望它不會來自，但如果您需要 OME 非常簡單，停用的新功能。</span><span class="sxs-lookup"><span data-stu-id="c19c4-195">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="c19c4-196">首先，您需要移除任何郵件流程規則已建立使用全新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="c19c4-196">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="c19c4-197">如需移除郵件流程規則的相關資訊，請參閱 <<c0>管理郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="c19c4-197">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="c19c4-198">然後，完成下列步驟在 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c19c4-198">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="c19c4-199">若要停用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="c19c4-199">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="c19c4-200">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c19c4-200">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c19c4-201">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="c19c4-201">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="c19c4-202">如果您啟用網頁型 Outlook 中的 [**保護**] 按鈕，請執行 Set-irmconfiguration 指令程式搭配 SimplifiedClientAccessEnabled 參數來將它停用。</span><span class="sxs-lookup"><span data-stu-id="c19c4-202">If you enabled the **Protect** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="c19c4-203">否則請跳過此步驟。</span><span class="sxs-lookup"><span data-stu-id="c19c4-203">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="c19c4-204">停用 OME 的新功能，藉由將 AzureRMSLicensingEnabled 參數設為 false 以執行 Set-irmconfiguration 指令程式：</span><span class="sxs-lookup"><span data-stu-id="c19c4-204">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
