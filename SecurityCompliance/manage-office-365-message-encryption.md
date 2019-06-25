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
description: 完成設定 Office 365 郵件加密 (OME) 後, 您可以透過多種方式自訂部署的設定。 例如, 您可以設定是否要啟用一次性程式碼、在 Outlook 網頁版中顯示 [保護] 按鈕, 等等。 本文中的工作會說明。
ms.openlocfilehash: f19556f88783eed86bd33a7fdcbd1efae18c3ef3
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852527"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="ba18a-105">管理 Office 365 郵件加密</span><span class="sxs-lookup"><span data-stu-id="ba18a-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="ba18a-106">完成設定 Office 365 郵件加密 (OME) 後, 您可以透過多種方式自訂部署的設定。</span><span class="sxs-lookup"><span data-stu-id="ba18a-106">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="ba18a-107">例如, 您可以設定是否要啟用一次性傳送碼、在 Outlook 網頁版中顯示 [**加密**] 按鈕, 等等。</span><span class="sxs-lookup"><span data-stu-id="ba18a-107">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="ba18a-108">本文中的工作會說明。</span><span class="sxs-lookup"><span data-stu-id="ba18a-108">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="ba18a-109">管理 Google、Yahoo 和 Microsoft 帳戶收件者是否可以使用這些帳戶登入 Office 365 郵件加密入口網站</span><span class="sxs-lookup"><span data-stu-id="ba18a-109">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="ba18a-110">當您設定新的 Office 365 郵件加密功能時, 您組織中的使用者可以傳送郵件給您的 Office 365 組織之外的收件者。</span><span class="sxs-lookup"><span data-stu-id="ba18a-110">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization.</span></span> <span data-ttu-id="ba18a-111">如果收件者使用的是 Google 帳戶、Yahoo 帳戶或 Microsoft 帳戶之類的*社交識別碼*, 則收件者可以使用社交識別碼登入 OME 入口網站。</span><span class="sxs-lookup"><span data-stu-id="ba18a-111">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="ba18a-112">如果您想要, 您可以選擇不要讓收件者使用社交識別碼來登入 OME 入口網站。</span><span class="sxs-lookup"><span data-stu-id="ba18a-112">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="ba18a-113">管理收件者是否可以使用社交識別碼登入 OME 入口網站</span><span class="sxs-lookup"><span data-stu-id="ba18a-113">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="ba18a-114">[使用遠端 PowerShell 連線到 Exchange Online](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ba18a-114">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="ba18a-115">使用 SocialIdSignIn 參數執行 Set-omeconfiguration 指令程式, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="ba18a-115">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="ba18a-116">例如, 若要停用社交識別碼:</span><span class="sxs-lookup"><span data-stu-id="ba18a-116">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="ba18a-117">若要啟用社交識別碼:</span><span class="sxs-lookup"><span data-stu-id="ba18a-117">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="ba18a-118">管理 Office 365 郵件加密入口網站的一次性處理碼使用</span><span class="sxs-lookup"><span data-stu-id="ba18a-118">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="ba18a-119">如果 OME 加密的郵件收件者不會使用 Outlook, 不論收件者使用的帳戶為何, 收件者都會收到限制的網頁查看連結, 讓他們能夠讀取郵件。</span><span class="sxs-lookup"><span data-stu-id="ba18a-119">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="ba18a-120">此連結包含一次性處理常式代碼。</span><span class="sxs-lookup"><span data-stu-id="ba18a-120">This link includes a one-time pass code.</span></span> <span data-ttu-id="ba18a-121">作為系統管理員, 您可以決定收件者是否可以使用一次性傳遞碼來登入 OME 入口網站。</span><span class="sxs-lookup"><span data-stu-id="ba18a-121">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="ba18a-122">若要管理 OME 是否會產生一次性的處理常式代碼</span><span class="sxs-lookup"><span data-stu-id="ba18a-122">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="ba18a-123">使用在您的 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 並啟動 Windows PowerShell 會話並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ba18a-123">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="ba18a-124">如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="ba18a-124">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="ba18a-125">使用 OTPEnabled 參數執行 Set-omeconfiguration 指令程式:</span><span class="sxs-lookup"><span data-stu-id="ba18a-125">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="ba18a-126">例如, 若要停用一次性處理常式代碼:</span><span class="sxs-lookup"><span data-stu-id="ba18a-126">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="ba18a-127">若要啟用一次性處理常式代碼:</span><span class="sxs-lookup"><span data-stu-id="ba18a-127">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="ba18a-128">在 web 上的 Outlook 中管理 [加密] 按鈕的顯示</span><span class="sxs-lookup"><span data-stu-id="ba18a-128">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="ba18a-129">作為系統管理員, 您可以管理是否要將此按鈕顯示給使用者。</span><span class="sxs-lookup"><span data-stu-id="ba18a-129">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="ba18a-130">管理 [加密] 按鈕是否顯示在 web 上的 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="ba18a-130">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="ba18a-131">使用在您的 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 並啟動 Windows PowerShell 會話並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ba18a-131">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="ba18a-132">如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="ba18a-132">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="ba18a-133">使用-SimplifiedClientAccessEnabled 參數執行 Get-irmconfiguration 程式指令程式:</span><span class="sxs-lookup"><span data-stu-id="ba18a-133">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="ba18a-134">例如, 若要停用 [**加密**] 按鈕:</span><span class="sxs-lookup"><span data-stu-id="ba18a-134">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="ba18a-135">若要啟用 [**加密**] 按鈕:</span><span class="sxs-lookup"><span data-stu-id="ba18a-135">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="ba18a-136">啟用 iOS 郵件應用程式使用者之電子郵件的服務端解密</span><span class="sxs-lookup"><span data-stu-id="ba18a-136">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="ba18a-137">IOS 郵件應用程式無法解密受 Office 365 郵件加密保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="ba18a-137">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="ba18a-138">作為 Office 365 系統管理員, 您可以對傳送至 iOS 郵件應用程式的郵件套用服務端解密。</span><span class="sxs-lookup"><span data-stu-id="ba18a-138">As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="ba18a-139">當您選擇使用服務端解密時, 服務會將解密的郵件副本傳送至 iOS 裝置。</span><span class="sxs-lookup"><span data-stu-id="ba18a-139">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="ba18a-140">用戶端裝置會儲存解密的郵件副本。</span><span class="sxs-lookup"><span data-stu-id="ba18a-140">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="ba18a-141">即使 iOS 郵件應用程式不會對使用者套用用戶端使用許可權, 郵件也會保留使用許可權的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ba18a-141">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="ba18a-142">使用者也可以複製或列印郵件, 即使他們原本沒有這麼做也一樣。</span><span class="sxs-lookup"><span data-stu-id="ba18a-142">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="ba18a-143">不過, 如果使用者嘗試完成需要 Office 365 郵件伺服器的動作 (例如轉寄郵件), 則伺服器不會允許該動作 (如果使用者原本未使用此方法)。</span><span class="sxs-lookup"><span data-stu-id="ba18a-143">However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="ba18a-144">不過, 使用者可以從 iOS 郵件應用程式內的不同帳戶轉寄郵件, 以解決「不要轉寄」使用限制。</span><span class="sxs-lookup"><span data-stu-id="ba18a-144">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="ba18a-145">不論您是否設定郵件的服務端解密, 您都無法在 iOS 郵件應用程式中查看加密和受版權保護之郵件的附件。</span><span class="sxs-lookup"><span data-stu-id="ba18a-145">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="ba18a-146">如果您選擇 [不允許將解密的郵件傳送至 iOS 郵件應用程式使用者], 使用者會收到一則訊息, 指出他們沒有查看郵件的許可權。</span><span class="sxs-lookup"><span data-stu-id="ba18a-146">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="ba18a-147">根據預設, 不會啟用電子郵件的服務端解密。</span><span class="sxs-lookup"><span data-stu-id="ba18a-147">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="ba18a-148">如需詳細資訊, 以及用戶端體驗的觀點, 請參閱[在 iPhone 或 iPad 上查看加密的郵件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)。</span><span class="sxs-lookup"><span data-stu-id="ba18a-148">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="ba18a-149">管理 iOS 郵件應用程式使用者是否可以查看 Office 365 郵件加密所保護的郵件</span><span class="sxs-lookup"><span data-stu-id="ba18a-149">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="ba18a-150">使用在您的 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 並啟動 Windows PowerShell 會話並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ba18a-150">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="ba18a-151">如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="ba18a-151">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="ba18a-152">使用 AllowRMSSupportForUnenlightenedApps 參數執行 ActiveSyncOrganizations 指令程式:</span><span class="sxs-lookup"><span data-stu-id="ba18a-152">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="ba18a-153">例如, 若要設定服務, 在將郵件傳送至 unenlightened 應用程式 (如 iOS 郵件應用程式) 之前, 將郵件解密:</span><span class="sxs-lookup"><span data-stu-id="ba18a-153">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="ba18a-154">或者, 若要將服務設定為不傳送解密的郵件至 unenlightened 應用程式, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="ba18a-154">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="ba18a-155">啟用 web 瀏覽器郵件用戶端之電子郵件附件的服務端解密</span><span class="sxs-lookup"><span data-stu-id="ba18a-155">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="ba18a-156">通常, 當您使用 Office 365 郵件加密時, 會自動加密附件。</span><span class="sxs-lookup"><span data-stu-id="ba18a-156">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="ba18a-157">作為 Office 365 系統管理員, 您可以對使用者從網頁瀏覽器下載的電子郵件附件套用服務端解密。</span><span class="sxs-lookup"><span data-stu-id="ba18a-157">As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="ba18a-158">當您使用服務端解密時, 服務會將檔案的解密複本傳送至裝置。</span><span class="sxs-lookup"><span data-stu-id="ba18a-158">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="ba18a-159">郵件仍然加密。</span><span class="sxs-lookup"><span data-stu-id="ba18a-159">The message is still encrypted.</span></span> <span data-ttu-id="ba18a-160">即使瀏覽器不會對使用者套用用戶端使用許可權, 電子郵件附件也會保留有關使用許可權的資訊。</span><span class="sxs-lookup"><span data-stu-id="ba18a-160">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="ba18a-161">使用者可以複製或列印電子郵件附件, 即使他們原來並未擁有這麼做的權利。</span><span class="sxs-lookup"><span data-stu-id="ba18a-161">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="ba18a-162">不過, 如果使用者嘗試完成需要 Office 365 郵件伺服器的動作 (例如轉寄附件), 則伺服器不會允許該動作 (如果使用者原本未使用此方法)。</span><span class="sxs-lookup"><span data-stu-id="ba18a-162">However, if the user tries to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="ba18a-163">不論您是否設定附件的服務端解密, 使用者都無法在 iOS 郵件應用程式中查看加密和受版權保護郵件的任何附件。</span><span class="sxs-lookup"><span data-stu-id="ba18a-163">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="ba18a-164">如果您選擇不允許解密的電子郵件附件 (預設值), 則使用者會收到一則訊息, 指出他們沒有查看附件的許可權。</span><span class="sxs-lookup"><span data-stu-id="ba18a-164">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="ba18a-165">如需有關 Office 365 如何使用 [僅供加密] 選項來為電子郵件和電子郵件附件進行加密的詳細資訊, 請參閱[電子郵件的 [僅加密] 選項。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="ba18a-165">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="ba18a-166">管理電子郵件附件是否會在從網頁瀏覽器下載時解密</span><span class="sxs-lookup"><span data-stu-id="ba18a-166">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="ba18a-167">使用在您的 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 並啟動 Windows PowerShell 會話並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ba18a-167">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="ba18a-168">如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="ba18a-168">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="ba18a-169">使用 DecryptAttachmentFromPortal 參數執行 Get-irmconfiguration 程式指令程式:</span><span class="sxs-lookup"><span data-stu-id="ba18a-169">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="ba18a-170">例如, 若要設定服務以在使用者從網頁瀏覽器下載時解密電子郵件附件, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="ba18a-170">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="ba18a-171">若要將服務設定為在下載時保留加密的電子郵件附件:</span><span class="sxs-lookup"><span data-stu-id="ba18a-171">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only"></a><span data-ttu-id="ba18a-172">確定所有外部收件者都使用 OME 入口網站來讀取加密的郵件 (僅限 Office 365 高級郵件加密)</span><span class="sxs-lookup"><span data-stu-id="ba18a-172">Ensure all external recipients use the OME Portal to read encrypted mail — Office 365 Advanced Message Encryption only</span></span>

<span data-ttu-id="ba18a-173">如果您有 Office 365 高級郵件加密, 您可以使用自訂品牌範本, 強制收件者收到包裝者郵件, 讓他們在 OME 入口網站中讀取加密的電子郵件, 而不是使用 Outlook 或 web 上的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="ba18a-173">If you have Office 365 Advanced Message Encryption, you can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="ba18a-174">如果您想要更進一步控制收件者如何使用他們收到的郵件, 您可能會想要這麼做。</span><span class="sxs-lookup"><span data-stu-id="ba18a-174">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="ba18a-175">例如, 如果外部收件者在 web 入口網站中查看電子郵件, 您可以設定電子郵件的到期日, 您也可以撤銷電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ba18a-175">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="ba18a-176">這些功能只支援透過 OME 入口網站。</span><span class="sxs-lookup"><span data-stu-id="ba18a-176">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="ba18a-177">您可以在建立郵件流程規則時, 使用 [加密] 選項和 [不要轉寄] 選項。</span><span class="sxs-lookup"><span data-stu-id="ba18a-177">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="create-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email-to-be-revocable-and-expire-in-7-days"></a><span data-ttu-id="ba18a-178">建立自訂範本, 以強制所有外部收件者都使用 OME 入口網站, 以及將加密的電子郵件設為可撤銷且7天后到期</span><span class="sxs-lookup"><span data-stu-id="ba18a-178">Create a custom template to force all external recipients to use the OME Portal and for encrypted email to be revocable and expire in 7 days</span></span>

1. <span data-ttu-id="ba18a-179">使用在您的 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 並啟動 Windows PowerShell 會話並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ba18a-179">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="ba18a-180">如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="ba18a-180">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="ba18a-181">執行 Set-omeconfiguration Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ba18a-181">Run the New-OMEConfiguration cmdlet:</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<template name>" -ExternalMailExpiryInDays 7
   ```

   <span data-ttu-id="ba18a-182">其中`template name`是您想要用於 Office 365 郵件加密自訂品牌範本的名稱。</span><span class="sxs-lookup"><span data-stu-id="ba18a-182">where `template name` is the name you want to use for the Office 365 Message Encryption custom branding template.</span></span> <span data-ttu-id="ba18a-183">For example,</span><span class="sxs-lookup"><span data-stu-id="ba18a-183">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<One week expiration>" -ExternalMailExpiryInDays 7
   ```

3. <span data-ttu-id="ba18a-184">執行 Get-transportrule 程式 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ba18a-184">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="ba18a-185">其中：</span><span class="sxs-lookup"><span data-stu-id="ba18a-185">where:</span></span>

   - <span data-ttu-id="ba18a-186">`mail flow rule name`是您要用於新郵件流程規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="ba18a-186">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="ba18a-187">`option name`是`Encrypt`或`Do Not Forward`。</span><span class="sxs-lookup"><span data-stu-id="ba18a-187">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="ba18a-188">`template name`是您提供自訂品牌範本的名稱, 例如`One week expiration`。</span><span class="sxs-lookup"><span data-stu-id="ba18a-188">`template name` is the name you gave the custom branding template, for example `One week expiration`.</span></span>

   <span data-ttu-id="ba18a-189">若要將所有的外部電子郵件加密為「一周到期」範本, 並套用 [僅供加密] 選項:</span><span class="sxs-lookup"><span data-stu-id="ba18a-189">To encrypt all external email with the "One week expiration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

   <span data-ttu-id="ba18a-190">若要使用「一周到期」範本來加密所有外部電子郵件, 並套用 [不要轉寄] 選項:</span><span class="sxs-lookup"><span data-stu-id="ba18a-190">To encrypt all external email with the "One week expiration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="ba18a-191">自訂電子郵件的外觀和 OME 入口網站</span><span class="sxs-lookup"><span data-stu-id="ba18a-191">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="ba18a-192">如需如何為組織自訂 OME 的詳細資訊, 請參閱[將貴組織的品牌新增至您的加密郵件](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="ba18a-192">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="ba18a-193">停用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="ba18a-193">Disable the new capabilities for OME</span></span>

<span data-ttu-id="ba18a-194">我們希望它不會進入它, 但如果您需要, 停用 OME 的新功能就非常簡單。</span><span class="sxs-lookup"><span data-stu-id="ba18a-194">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="ba18a-195">首先, 您必須移除您建立的任何使用新 OME 功能的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="ba18a-195">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="ba18a-196">如需移除郵件流程規則的詳細資訊, 請參閱[管理郵件流程規則](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ba18a-196">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="ba18a-197">然後, 請在 Exchange Online PowerShell 中完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="ba18a-197">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="ba18a-198">停用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="ba18a-198">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="ba18a-199">使用在 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 啟動 Windows PowerShell 會話, 並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ba18a-199">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="ba18a-200">如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="ba18a-200">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="ba18a-201">如果您已在網頁版 Outlook 中啟用 [**加密**] 按鈕, 請使用 SimplifiedClientAccessEnabled 參數執行 get-irmconfiguration 程式指令程式以將其停用。</span><span class="sxs-lookup"><span data-stu-id="ba18a-201">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="ba18a-202">否則, 請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="ba18a-202">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="ba18a-203">使用 AzureRMSLicensingEnabled 參數設定為 false 來執行 Get-irmconfiguration 程式指令程式, 以停用 OME 的新功能:</span><span class="sxs-lookup"><span data-stu-id="ba18a-203">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
