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
# <a name="manage-office-365-message-encryption"></a>管理 Office 365 郵件加密

一旦您已經完成設定 up Office 365 郵件加密 (OME)，您可以自訂您的部署數種方式的設定。 例如，您可以設定是否要啟用一次性複雜代碼，顯示在網頁伺服器和多個 outlook 的 [**保護**] 按鈕。 本文中的任務說明如何。
  
||
|:-----|
|本文屬於較大的一連串的 Office 365 郵件加密的相關文章。 本文適用於系統管理員和 ITPros。 如果您只是正在尋找的資訊傳送或接收的加密的訊息，請參閱在[Office 365 郵件加密 (OME)](ome.md)中的文章的清單，並找出最適合您需求的文章。 |
||

## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>管理是否 Google、 Yahoo，以及 Microsoft 帳戶的收件者可以使用這些帳戶來登入 Office 365 郵件加密入口網站

根據預設，當您設定新的 Office 365 郵件加密功能，貴組織中的使用者可以傳送郵件給您的 Office 365 組織外的收件者。 收件者如果收件者使用*社交識別碼*，例如 Google 帳戶、 Yahoo 帳戶或 Microsoft 帳戶，可以登入使用社交 ID OME 入口網站 如果您想，您可以選擇不允許使用社交識別碼來登入 OME 入口網站的收件者。
  
### <a name="to-manage-whether-or-not-to-allow-recipients-to-use-social-ids-to-sign-in-to-the-ome-portal"></a>若要管理，就不會允許收件者使用社交識別碼來登入 OME 入口網站
  
1. [連線至 Exchange Online 使用遠端 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。

2. 執行 Set-omeconfiguration 指令程式搭配 SocialIdSignIn 參數如下所示：

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true | $false>
   ```

   例如，若要停用社交識別碼：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   若要啟用社交識別碼：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a>管理次傳遞代碼用於登入 Office 365 郵件加密入口網站

根據預設，如果 OME 加密郵件的收件者不會使用 Outlook，無論收件者，所使用的帳戶收件者會收到時間有限 web 檢視連結，讓他們在閱讀郵件。 這包括一次性複雜的程式碼。 身為管理員，您可以管理次傳遞代碼可以用來登入 OME 入口網站。
  
### <a name="to-manage-whether-or-not-one-time-pass-codes-are-generated-for-ome"></a>若要管理次傳遞代碼所產生的 OME
  
1. 使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。 如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。

2. 執行 Set-omeconfiguration 指令程式搭配 OTPEnabled 參數：

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   例如，若要停用一次性複雜代碼：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   若要啟用一次性複雜代碼：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a>管理網頁型 Outlook 中的 [保護] 按鈕的顯示

根據預設，您設定 OME 時，不會啟用網頁型 Outlook 中的 [**保護**] 按鈕。 身為管理員，您可以管理，就不會向使用者顯示此按鈕。
  
### <a name="to-manage-whether-or-not-the-protect-button-appears-in-outlook-on-the-web"></a>若要管理 [保護] 按鈕會出現在 outlook 網頁版
  
1. 使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。 如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。

2. 執行 Set-irmconfiguration 指令程式搭配-SimplifiedClientAccessEnabled 參數：

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   例如，若要停用 [**保護**] 按鈕：

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   若要啟用 [**保護**] 按鈕：

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>啟用服務端解密的郵件應用程式的 iOS 使用者的電子郵件

Ios 電子郵件應用程式無法解密郵件以 Office 365 郵件加密來保護。 是 Office 365 系統管理員，您可以套用服務端解密的郵件傳遞至 ios 電子郵件應用程式。 當您選擇要執行這項操作時，服務會將已解密的郵件複本傳送至 iOS 裝置。 郵件會儲存在用戶端裝置解密。 郵件也會保留使用權限的相關資訊，即使 ios 電子郵件應用程式不會套用至使用者的用戶端使用權限。 這表示使用者可以複製或列印郵件，即使他們原本沒有要執行這項操作的權限。 不過，如果使用者嘗試完成需要 Office 365 的郵件伺服器，例如轉寄訊息，巨集指令，伺服器不如果使用者原本沒有這麼做的 usage 權限允許巨集指令。 不過，使用者可以解決不要轉寄流量限制郵件轉寄其 ios 電子郵件應用程式中的不同帳戶。 不論是否您設定服務端解密的郵件，任何附件加密，而且無法在 ios 電子郵件應用程式中檢視權限受保護的郵件。
  
如果您選擇不要讓解密的郵件傳送至 iOS 郵件應用程式的使用者，使用者會收到訊息，指出他們沒有檢視郵件的權限。 根據預設，未啟用服務端解密的電子郵件訊息。
  
如需詳細資訊，以及用戶端體驗的檢視，請參閱[檢視加密的郵件在 iPhone 或 iPad 上](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)。
  
### <a name="to-manage-whether-or-not-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>若要管理 iOS 郵件應用程式的使用者可以檢視受保護的 Office 365 郵件加密的郵件
  
1. 使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。 如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。

2. 使用 AllowRMSSupportForUnenlightenedApps 參數執行設定 ActiveSyncOrganizations 指令程式：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   例如，若要設定服務，以解密訊息之前傳送至 unenlightened 應用程式例如 iOS 郵件應用程式：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   或者，若要設定服務未以解密的郵件傳送至 unenlightened 應用程式：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>啟用服務端解密的網頁瀏覽器郵件用戶端的電子郵件附件

一般而言，當您使用 Office 365 郵件加密時，會自動加密附件。 是 Office 365 系統管理員，您可以套用使用者從網頁瀏覽器下載的電子郵件附件的服務端的解密。
  
當您選擇要執行這項操作時，服務會傳送解密該檔案的複本至裝置。 仍處於加密郵件。 電子郵件附件也會保留使用權限的相關資訊，即使在瀏覽器不會套用至使用者的用戶端使用權限。 這表示使用者可以複製或列印的電子郵件附件，即使他們原本沒有要執行這項操作的權限。 不過，如果使用者嘗試完成需要 Office 365 的郵件伺服器，例如轉寄附件，巨集指令，伺服器不如果使用者原本沒有這麼做的 usage 權限允許巨集指令。
  
不論是否您設定服務端解密的附件，任何附件加密，而且無法在 ios 電子郵件應用程式中檢視權限受保護的郵件。
  
如果您選擇不要允許解密電子郵件附件，也就是預設值，使用者會收到訊息，指出他們沒有檢視附件的權限。
  
如需有關 Office 365 如何實作加密的電子郵件和電子郵件附件的加密唯讀] 選項的詳細資訊，請參閱[僅限加密的電子郵件選項。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-or-not-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>若要管理電子郵件附件進行解密上從網頁瀏覽器下載
  
1. 使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。 如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。

2. 執行 Set-irmconfiguration 指令程式搭配 DecryptAttachmentFromPortal 參數：

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   例如，若要設定服務，以解密電子郵件附件當使用者下載其從網頁瀏覽器：

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   若要設定要保留加密的電子郵件附件，因為它們是在下載時的服務：

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a>自訂電子郵件訊息和 OME 入口網站的外觀

如需如何自訂 OME 組織的詳細資訊，請參閱[新增至加密郵件的貴組織的品牌](add-your-organization-brand-to-encrypted-messages.md)。
  
## <a name="disabling-the-new-capabilities-for-ome"></a>停用 OME 的新功能

我們希望它不會來自，但如果您需要 OME 非常簡單，停用的新功能。 首先，您需要移除任何郵件流程規則已建立使用全新的 OME 功能。 如需移除郵件流程規則的相關資訊，請參閱 <<c0>管理郵件流程規則。 然後，完成下列步驟在 Exchange Online PowerShell。
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>若要停用 OME 的新功能
  
1. 使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。 如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。

2. 如果您啟用網頁型 Outlook 中的 [**保護**] 按鈕，請執行 Set-irmconfiguration 指令程式搭配 SimplifiedClientAccessEnabled 參數來將它停用。 否則請跳過此步驟。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. 停用 OME 的新功能，藉由將 AzureRMSLicensingEnabled 參數設為 false 以執行 Set-irmconfiguration 指令程式：

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
