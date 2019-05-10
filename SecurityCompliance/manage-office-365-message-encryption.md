---
title: 管理 Office 365 郵件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
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
ms.openlocfilehash: 1afaaea3cd744878630598acd3f02dc7dc70e9cb
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834922"
---
# <a name="manage-office-365-message-encryption"></a>管理 Office 365 郵件加密

一旦您已經完成設定 up Office 365 郵件加密 (OME)，您可以自訂您的部署，以數種方式的設定。 例如，您可以設定是否要啟用一次性複雜代碼，顯示在網頁伺服器和多個 outlook 的 [**保護**] 按鈕。 本文中的任務說明如何。

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>管理是否 Google、 Yahoo，以及 Microsoft 帳戶的收件者可以使用這些帳戶來登入 Office 365 郵件加密入口網站

當您設定新的 Office 365 郵件加密功能時，您組織中的使用者可以傳送郵件給您的 Office 365 組織外的收件者。 收件者如果收件者使用*社交識別碼*，例如 Google 帳戶、 Yahoo 帳戶或 Microsoft 帳戶，可以登入到具有社交識別碼 OME 入口網站 如果您想，您可以選擇不允許使用社交識別碼來登入 OME 入口網站的收件者。
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>若要管理是否收件者可以使用社交識別碼登入 OME 入口網站
  
1. [連線至 Exchange Online 使用遠端 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。

2. 執行 Set-omeconfiguration 指令程式搭配 SocialIdSignIn 參數如下所示：

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   例如，若要停用社交識別碼：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   若要啟用社交識別碼：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>管理次傳遞代碼用於 Office 365 郵件加密入口網站

如果由 OME 加密郵件的收件者不會使用 Outlook，無論收件者所使用的帳戶，收件者會收到一個時間有限 web 檢視連結，讓他們在閱讀郵件。 此連結，包括一次性複雜的程式碼。 身為管理員，您可以決定收件者是否可以使用次傳遞代碼來登入 OME 入口網站。
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>若要管理是否 OME 產生次傳遞代碼
  
1. 使用公司或學校帳戶具有您 Office 365 組織中的全域系統管理員權限啟動 Windows PowerShell 工作階段並連線至 Exchange Online。 如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。

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

## <a name="manage-the-display-of-the-protect-button-in-outlook-on-the-web"></a>管理網頁型 Outlook 中的 [保護] 按鈕的顯示

當您設定 OME 時，會停用網頁型 Outlook 中的 [**保護**] 按鈕。 身為管理員，您可以管理是否要對使用者顯示此按鈕。
  
### <a name="to-manage-whether-the-protect-button-appears-in-outlook-on-the-web"></a>若要管理是否 [保護] 按鈕會出現在 outlook 網頁版
  
1. 使用公司或學校帳戶具有您 Office 365 組織中的全域系統管理員權限啟動 Windows PowerShell 工作階段並連線至 Exchange Online。 如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。

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

Ios 電子郵件應用程式無法解密郵件以 Office 365 郵件加密來保護。 是 Office 365 系統管理員，您可以套用服務端解密的郵件傳遞至 ios 電子郵件應用程式。 當您選擇不要使用服務端解密時，服務會將已解密的郵件複本傳送至 iOS 裝置。 用戶端裝置儲存解密郵件的副本。 郵件也會保留使用權限的相關資訊，即使 ios 電子郵件應用程式不會套用至使用者的用戶端使用權限。 使用者可以複製或列印郵件，即使他們原本沒有要執行這項操作的權限。 然而，如果使用者嘗試完成的動作需要 Office 365 的郵件伺服器，例如轉寄郵件，伺服器不會允許動作如果使用者原本沒有使用權若要這麼做。 不過，使用者可以解決 「 不要轉寄 」 流量限制郵件轉寄 ios 電子郵件應用程式內的不同帳戶。 不論是否您設定服務端解密的郵件，附件加密，而且無法在 ios 電子郵件應用程式中檢視權限受保護的郵件。
  
如果您選擇不要讓解密的郵件傳送至 iOS 郵件應用程式的使用者，使用者會收到訊息，指出他們沒有檢視郵件的權限。 根據預設，未啟用服務端解密的電子郵件訊息。
  
如需詳細資訊，以及用戶端體驗的檢視，請參閱[檢視加密的郵件在 iPhone 或 iPad 上](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)。
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>若要管理 iOS 郵件應用程式的使用者是否可以檢視受保護的 Office 365 郵件加密的郵件
  
1. 使用公司或學校帳戶具有您 Office 365 組織中的全域系統管理員權限啟動 Windows PowerShell 工作階段並連線至 Exchange Online。 如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。

2. 使用 AllowRMSSupportForUnenlightenedApps 參數執行設定 ActiveSyncOrganizations 指令程式：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   例如，若要設定服務，以解密郵件之前，傳送給 unenlightened 應用程式如 iOS 郵件應用程式：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   或者，若要設定服務未以解密的郵件傳送至 unenlightened 應用程式：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>啟用服務端解密的網頁瀏覽器郵件用戶端的電子郵件附件

一般而言，當您使用 Office 365 郵件加密時，會自動加密附件。 是 Office 365 系統管理員，您可以套用使用者從網頁瀏覽器下載的電子郵件附件的服務端的解密。
  
當您使用服務端解密時，服務會將解密該檔案的複本傳送到裝置。 仍處於加密郵件。 電子郵件附件也會保留使用權限的相關資訊，即使在瀏覽器不會套用至使用者的用戶端使用權限。 使用者可以複製或列印的電子郵件附件，即使他們原本沒有要執行這項操作的權限。 然而，如果使用者嘗試完成的動作需要 Office 365 的郵件伺服器，例如轉寄附件，伺服器不會允許動作如果使用者原本沒有使用權若要這麼做。
  
不論是否您設定服務端解密的附件，使用者無法檢視加密的任何附件和權限保護郵件中 iOS 郵件應用程式。
  
如果您選擇不要允許解密電子郵件附件，也就是預設值，使用者會收到訊息，指出他們沒有檢視附件的權限。
  
如需有關 Office 365 如何實作加密的電子郵件和電子郵件附件的加密唯讀] 選項的詳細資訊，請參閱[僅限加密的電子郵件選項。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>若要管理是否電子郵件附件進行解密上從網頁瀏覽器下載
  
1. 使用公司或學校帳戶具有您 Office 365 組織中的全域系統管理員權限啟動 Windows PowerShell 工作階段並連線至 Exchange Online。 如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。

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

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only"></a>請確定所有外部收件者讀取加密的郵件使用 OME 入口網站-Office 365 進階郵件加密僅

如果您有 Office 365 進階郵件加密，您可以使用自訂品牌的範本，若要強制接收指示它們讀取加密的電子郵件，而不是使用 Outlook 或網頁型 Outlook OME 入口網站中的包裝函式郵件的收件者。 您可能想要這麼做，如果您使用想接收更能掌控收件者如何使用郵件。 例如，如果外部收件者在入口網站中檢視電子郵件，您可以設定到期日的電子郵件，而您可以撤銷電子郵件。 透過 OME 入口網站僅支援這些功能。 建立郵件流程規則時，您可以使用加密選項和 [不要轉寄] 選項。

### <a name="create-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email-to-be-revocable-and-expire-in-7-days"></a>建立自訂的範本，以便強制所有外部的收件者使用 OME 入口網站及加密的電子郵件可撤銷之和 7 天內到期

1. 使用公司或學校帳戶具有您 Office 365 組織中的全域系統管理員權限啟動 Windows PowerShell 工作階段並連線至 Exchange Online。 如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。

2. 執行新增 Set-omeconfiguration cmdlet:

   ```powershell
   New-OMEConfiguration -Identity "<template name>" -ExternalMailExpiryInDays 7
   ```

   其中`template name`是您想要用於 Office 365 郵件加密的自訂品牌範本的名稱。 For example,

   ```powershell
   New-OMEConfiguration -Identity "<One week expiration>" -ExternalMailExpiryInDays 7
   ```

3. 執行 New-transportrule 指令程式：

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    其中：

   - `mail flow rule name`是您想要用於新的郵件流程規則的名稱。

   - `option name`是`Encrypt`或`Do Not Forward`。

   - `template name`是您命名的自訂品牌的範本，例如`One week expiration`。

   若要加密與 「 一週到期 」 範本的所有外部電子郵件並套用加密唯讀選項：

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

   若要加密與 「 一週到期 」 範本的所有外部電子郵件，並套用 [不要轉寄] 選項：

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>自訂電子郵件訊息和 OME 入口網站的外觀

如需如何自訂 OME 組織的詳細資訊，請參閱[新增至加密郵件的貴組織的品牌](add-your-organization-brand-to-encrypted-messages.md)。
  
## <a name="disable-the-new-capabilities-for-ome"></a>停用 OME 的新功能

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
