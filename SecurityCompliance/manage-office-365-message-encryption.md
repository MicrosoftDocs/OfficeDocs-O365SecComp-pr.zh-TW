---
title: 管理 Office 365 郵件加密
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- M365-security-compliance
description: 一旦您已經完成設定 up Office 365 郵件加密 (OME)，您可以自訂您的部署數種方式的設定。 例如，您可以設定是否要啟用一次性複雜代碼，顯示在網頁伺服器和多個 outlook 的 [保護] 按鈕。 本文中的任務說明如何。
ms.openlocfilehash: 7b5297ae42d3efa071408540863c6ff7dbdee407
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259811"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="27a8a-105">管理 Office 365 郵件加密</span><span class="sxs-lookup"><span data-stu-id="27a8a-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="27a8a-106">一旦您已經完成設定 up Office 365 郵件加密 (OME)，您可以自訂您的部署數種方式的設定。</span><span class="sxs-lookup"><span data-stu-id="27a8a-106">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in a number of ways.</span></span> <span data-ttu-id="27a8a-107">例如，您可以設定是否要啟用一次性複雜代碼，顯示在網頁伺服器和多個 outlook 的 [**保護**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="27a8a-107">For example, you can configure whether to enable one-time pass codes, display the **Protect** button in Outlook on the web, and more.</span></span> <span data-ttu-id="27a8a-108">本文中的任務說明如何。</span><span class="sxs-lookup"><span data-stu-id="27a8a-108">The tasks in this article describe how.</span></span>
  
||
|:-----|
|<span data-ttu-id="27a8a-109">本文屬於較大的一連串的 Office 365 郵件加密的相關文章。</span><span class="sxs-lookup"><span data-stu-id="27a8a-109">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="27a8a-110">本文適用於系統管理員和 ITPros。</span><span class="sxs-lookup"><span data-stu-id="27a8a-110">This article is intended for administrators and ITPros.</span></span> <span data-ttu-id="27a8a-111">如果您只是正在尋找的資訊傳送或接收的加密的訊息，請參閱在[Office 365 郵件加密 (OME)](ome.md)中的文章的清單，並找出最適合您需求的文章。</span><span class="sxs-lookup"><span data-stu-id="27a8a-111">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="27a8a-112">管理是否 Google、 Yahoo，以及 Microsoft 帳戶的收件者可以使用這些帳戶來登入 Office 365 郵件加密入口網站</span><span class="sxs-lookup"><span data-stu-id="27a8a-112">Managing whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="27a8a-113">根據預設，當您設定新的 Office 365 郵件加密功能，貴組織中的使用者可以傳送郵件給您的 Office 365 組織外的收件者。</span><span class="sxs-lookup"><span data-stu-id="27a8a-113">By default, when you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization.</span></span> <span data-ttu-id="27a8a-114">收件者如果收件者使用*社交識別碼*，例如 Google 帳戶、 Yahoo 帳戶或 Microsoft 帳戶，可以登入使用社交 ID OME 入口網站</span><span class="sxs-lookup"><span data-stu-id="27a8a-114">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal using the social ID.</span></span> <span data-ttu-id="27a8a-115">如果您想，您可以選擇不允許使用社交識別碼來登入 OME 入口網站的收件者。</span><span class="sxs-lookup"><span data-stu-id="27a8a-115">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-to-allow-recipients-to-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="27a8a-116">若要管理，就不會允許收件者使用社交識別碼來登入 OME 入口網站</span><span class="sxs-lookup"><span data-stu-id="27a8a-116">To manage whether or not to allow recipients to use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="27a8a-117">[連線至 Exchange Online 使用遠端 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="27a8a-117">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="27a8a-118">執行 Set-omeconfiguration 指令程式搭配 SocialIdSignIn 參數如下所示：</span><span class="sxs-lookup"><span data-stu-id="27a8a-118">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true | $false>
   ```

   <span data-ttu-id="27a8a-119">例如，若要停用社交識別碼：</span><span class="sxs-lookup"><span data-stu-id="27a8a-119">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="27a8a-120">若要啟用社交識別碼：</span><span class="sxs-lookup"><span data-stu-id="27a8a-120">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="27a8a-121">管理次傳遞代碼用於登入 Office 365 郵件加密入口網站</span><span class="sxs-lookup"><span data-stu-id="27a8a-121">Managing the use of one-time pass codes for signing in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="27a8a-122">根據預設，如果 OME 加密郵件的收件者不會使用 Outlook，無論收件者，所使用的帳戶收件者會收到時間有限 web 檢視連結，讓他們在閱讀郵件。</span><span class="sxs-lookup"><span data-stu-id="27a8a-122">By default, if the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="27a8a-123">這包括一次性複雜的程式碼。</span><span class="sxs-lookup"><span data-stu-id="27a8a-123">This includes a one-time pass code.</span></span> <span data-ttu-id="27a8a-124">身為管理員，您可以管理次傳遞代碼可以用來登入 OME 入口網站。</span><span class="sxs-lookup"><span data-stu-id="27a8a-124">As an administrator, you can manage whether or not one-time pass codes can be used to sign-in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-one-time-pass-codes-are-generated-for-ome"></a><span data-ttu-id="27a8a-125">若要管理次傳遞代碼所產生的 OME</span><span class="sxs-lookup"><span data-stu-id="27a8a-125">To manage whether or not one-time pass codes are generated for OME</span></span>
  
1. <span data-ttu-id="27a8a-126">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="27a8a-126">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="27a8a-127">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="27a8a-127">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="27a8a-128">執行 Set-omeconfiguration 指令程式搭配 OTPEnabled 參數：</span><span class="sxs-lookup"><span data-stu-id="27a8a-128">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="27a8a-129">例如，若要停用一次性複雜代碼：</span><span class="sxs-lookup"><span data-stu-id="27a8a-129">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="27a8a-130">若要啟用一次性複雜代碼：</span><span class="sxs-lookup"><span data-stu-id="27a8a-130">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a><span data-ttu-id="27a8a-131">管理網頁型 Outlook 中的 [保護] 按鈕的顯示</span><span class="sxs-lookup"><span data-stu-id="27a8a-131">Managing the display of the Protect button in Outlook on the web</span></span>

<span data-ttu-id="27a8a-132">根據預設，您設定 OME 時，不會啟用網頁型 Outlook 中的 [**保護**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="27a8a-132">By default, the **Protect** button in Outlook on the web is not enabled when you set up OME.</span></span> <span data-ttu-id="27a8a-133">身為管理員，您可以管理，就不會向使用者顯示此按鈕。</span><span class="sxs-lookup"><span data-stu-id="27a8a-133">As an administrator, you can manage whether or not to display this button to end users.</span></span>
  
### <a name="to-manage-whether-or-not-the-protect-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="27a8a-134">若要管理 [保護] 按鈕會出現在 outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="27a8a-134">To manage whether or not the Protect button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="27a8a-135">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="27a8a-135">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="27a8a-136">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="27a8a-136">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="27a8a-137">執行 Set-irmconfiguration 指令程式搭配-SimplifiedClientAccessEnabled 參數：</span><span class="sxs-lookup"><span data-stu-id="27a8a-137">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="27a8a-138">例如，若要停用 [**保護**] 按鈕：</span><span class="sxs-lookup"><span data-stu-id="27a8a-138">For example, to disable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="27a8a-139">若要啟用 [**保護**] 按鈕：</span><span class="sxs-lookup"><span data-stu-id="27a8a-139">To enable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="27a8a-140">啟用服務端解密的郵件應用程式的 iOS 使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="27a8a-140">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="27a8a-141">Ios 電子郵件應用程式無法解密郵件以 Office 365 郵件加密來保護。</span><span class="sxs-lookup"><span data-stu-id="27a8a-141">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="27a8a-142">是 Office 365 系統管理員，您可以套用服務端解密的郵件傳遞至 ios 電子郵件應用程式。</span><span class="sxs-lookup"><span data-stu-id="27a8a-142">As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="27a8a-143">當您選擇要執行這項操作時，服務會將已解密的郵件複本傳送至 iOS 裝置。</span><span class="sxs-lookup"><span data-stu-id="27a8a-143">When you choose to do this, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="27a8a-144">郵件會儲存在用戶端裝置解密。</span><span class="sxs-lookup"><span data-stu-id="27a8a-144">The message is stored decrypted on the client device.</span></span> <span data-ttu-id="27a8a-145">郵件也會保留使用權限的相關資訊，即使 ios 電子郵件應用程式不會套用至使用者的用戶端使用權限。</span><span class="sxs-lookup"><span data-stu-id="27a8a-145">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="27a8a-146">這表示使用者可以複製或列印郵件，即使他們原本沒有要執行這項操作的權限。</span><span class="sxs-lookup"><span data-stu-id="27a8a-146">This means that the user can copy or print the message even if they did not originally have the rights to do so.</span></span> <span data-ttu-id="27a8a-147">不過，如果使用者嘗試完成需要 Office 365 的郵件伺服器，例如轉寄訊息，巨集指令，伺服器不如果使用者原本沒有這麼做的 usage 權限允許巨集指令。</span><span class="sxs-lookup"><span data-stu-id="27a8a-147">However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server will not permit the action if the user did not originally have the usage right to do so.</span></span> <span data-ttu-id="27a8a-148">不過，使用者可以解決不要轉寄流量限制郵件轉寄其 ios 電子郵件應用程式中的不同帳戶。</span><span class="sxs-lookup"><span data-stu-id="27a8a-148">However, end-users can work around Do Not Forward usage restriction by forwarding the message from a different account in their iOS mail app.</span></span> <span data-ttu-id="27a8a-149">不論是否您設定服務端解密的郵件，任何附件加密，而且無法在 ios 電子郵件應用程式中檢視權限受保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="27a8a-149">Regardless of whether you set up service-side decryption of mail, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="27a8a-150">如果您選擇不要讓解密的郵件傳送至 iOS 郵件應用程式的使用者，使用者會收到訊息，指出他們沒有檢視郵件的權限。</span><span class="sxs-lookup"><span data-stu-id="27a8a-150">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="27a8a-151">根據預設，未啟用服務端解密的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="27a8a-151">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="27a8a-152">如需詳細資訊，以及用戶端體驗的檢視，請參閱[檢視加密的郵件在 iPhone 或 iPad 上](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)。</span><span class="sxs-lookup"><span data-stu-id="27a8a-152">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-or-not-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="27a8a-153">若要管理 iOS 郵件應用程式的使用者可以檢視受保護的 Office 365 郵件加密的郵件</span><span class="sxs-lookup"><span data-stu-id="27a8a-153">To manage whether or not iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="27a8a-154">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="27a8a-154">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="27a8a-155">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="27a8a-155">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="27a8a-156">使用 AllowRMSSupportForUnenlightenedApps 參數執行設定 ActiveSyncOrganizations 指令程式：</span><span class="sxs-lookup"><span data-stu-id="27a8a-156">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="27a8a-157">例如，若要設定服務，以解密訊息之前傳送至 unenlightened 應用程式例如 iOS 郵件應用程式：</span><span class="sxs-lookup"><span data-stu-id="27a8a-157">For example, to configure the service to decrypt messages before they are sent to unenlightened apps such as the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="27a8a-158">或者，若要設定服務未以解密的郵件傳送至 unenlightened 應用程式：</span><span class="sxs-lookup"><span data-stu-id="27a8a-158">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="27a8a-159">啟用服務端解密的網頁瀏覽器郵件用戶端的電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="27a8a-159">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="27a8a-160">一般而言，當您使用 Office 365 郵件加密時，會自動加密附件。</span><span class="sxs-lookup"><span data-stu-id="27a8a-160">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="27a8a-161">是 Office 365 系統管理員，您可以套用使用者從網頁瀏覽器下載的電子郵件附件的服務端的解密。</span><span class="sxs-lookup"><span data-stu-id="27a8a-161">As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="27a8a-162">當您選擇要執行這項操作時，服務會傳送解密該檔案的複本至裝置。</span><span class="sxs-lookup"><span data-stu-id="27a8a-162">When you choose to do this, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="27a8a-163">仍處於加密郵件。</span><span class="sxs-lookup"><span data-stu-id="27a8a-163">The message is still encrypted.</span></span> <span data-ttu-id="27a8a-164">電子郵件附件也會保留使用權限的相關資訊，即使在瀏覽器不會套用至使用者的用戶端使用權限。</span><span class="sxs-lookup"><span data-stu-id="27a8a-164">The email attachment also retains information about usage rights even though the browser does not apply client-side usage rights to the user.</span></span> <span data-ttu-id="27a8a-165">這表示使用者可以複製或列印的電子郵件附件，即使他們原本沒有要執行這項操作的權限。</span><span class="sxs-lookup"><span data-stu-id="27a8a-165">This means that the user can copy or print the email attachment even if they did not originally have the rights to do so.</span></span> <span data-ttu-id="27a8a-166">不過，如果使用者嘗試完成需要 Office 365 的郵件伺服器，例如轉寄附件，巨集指令，伺服器不如果使用者原本沒有這麼做的 usage 權限允許巨集指令。</span><span class="sxs-lookup"><span data-stu-id="27a8a-166">However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server will not permit the action if the user did not originally have the usage right to do so.</span></span>
  
<span data-ttu-id="27a8a-167">不論是否您設定服務端解密的附件，任何附件加密，而且無法在 ios 電子郵件應用程式中檢視權限受保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="27a8a-167">Regardless of whether you set up service-side decryption of attachments, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="27a8a-168">如果您選擇不要允許解密電子郵件附件，也就是預設值，使用者會收到訊息，指出他們沒有檢視附件的權限。</span><span class="sxs-lookup"><span data-stu-id="27a8a-168">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="27a8a-169">如需有關 Office 365 如何實作加密的電子郵件和電子郵件附件的加密唯讀] 選項的詳細資訊，請參閱[僅限加密的電子郵件選項。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="27a8a-169">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-or-not-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="27a8a-170">若要管理電子郵件附件進行解密上從網頁瀏覽器下載</span><span class="sxs-lookup"><span data-stu-id="27a8a-170">To manage whether or not email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="27a8a-171">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="27a8a-171">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="27a8a-172">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="27a8a-172">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="27a8a-173">執行 Set-irmconfiguration 指令程式搭配 DecryptAttachmentFromPortal 參數：</span><span class="sxs-lookup"><span data-stu-id="27a8a-173">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="27a8a-174">例如，若要設定服務，以解密電子郵件附件當使用者下載其從網頁瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="27a8a-174">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="27a8a-175">若要設定要保留加密的電子郵件附件，因為它們是在下載時的服務：</span><span class="sxs-lookup"><span data-stu-id="27a8a-175">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="27a8a-176">自訂電子郵件訊息和 OME 入口網站的外觀</span><span class="sxs-lookup"><span data-stu-id="27a8a-176">Customizing the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="27a8a-177">如需如何自訂 OME 組織的詳細資訊，請參閱[新增至加密郵件的貴組織的品牌](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="27a8a-177">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disabling-the-new-capabilities-for-ome"></a><span data-ttu-id="27a8a-178">停用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="27a8a-178">Disabling the new capabilities for OME</span></span>

<span data-ttu-id="27a8a-179">我們希望它不會來自，但如果您需要 OME 非常簡單，停用的新功能。</span><span class="sxs-lookup"><span data-stu-id="27a8a-179">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="27a8a-180">首先，您需要移除任何郵件流程規則已建立使用全新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="27a8a-180">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="27a8a-181">如需移除郵件流程規則的相關資訊，請參閱 <<c0>管理郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="27a8a-181">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="27a8a-182">然後，完成下列步驟在 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="27a8a-182">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="27a8a-183">若要停用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="27a8a-183">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="27a8a-184">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="27a8a-184">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="27a8a-185">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="27a8a-185">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="27a8a-186">如果您啟用網頁型 Outlook 中的 [**保護**] 按鈕，請執行 Set-irmconfiguration 指令程式搭配 SimplifiedClientAccessEnabled 參數來將它停用。</span><span class="sxs-lookup"><span data-stu-id="27a8a-186">If you enabled the **Protect** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="27a8a-187">否則請跳過此步驟。</span><span class="sxs-lookup"><span data-stu-id="27a8a-187">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="27a8a-188">停用 OME 的新功能，藉由將 AzureRMSLicensingEnabled 參數設為 false 以執行 Set-irmconfiguration 指令程式：</span><span class="sxs-lookup"><span data-stu-id="27a8a-188">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
