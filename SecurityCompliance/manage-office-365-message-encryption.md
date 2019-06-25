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
# <a name="manage-office-365-message-encryption"></a>管理 Office 365 郵件加密

完成設定 Office 365 郵件加密 (OME) 後, 您可以透過多種方式自訂部署的設定。 例如, 您可以設定是否要啟用一次性傳送碼、在 Outlook 網頁版中顯示 [**加密**] 按鈕, 等等。 本文中的工作會說明。

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>管理 Google、Yahoo 和 Microsoft 帳戶收件者是否可以使用這些帳戶登入 Office 365 郵件加密入口網站

當您設定新的 Office 365 郵件加密功能時, 您組織中的使用者可以傳送郵件給您的 Office 365 組織之外的收件者。 如果收件者使用的是 Google 帳戶、Yahoo 帳戶或 Microsoft 帳戶之類的*社交識別碼*, 則收件者可以使用社交識別碼登入 OME 入口網站。 如果您想要, 您可以選擇不要讓收件者使用社交識別碼來登入 OME 入口網站。
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>管理收件者是否可以使用社交識別碼登入 OME 入口網站
  
1. [使用遠端 PowerShell 連線到 Exchange Online](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。

2. 使用 SocialIdSignIn 參數執行 Set-omeconfiguration 指令程式, 如下所示:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   例如, 若要停用社交識別碼:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   若要啟用社交識別碼:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>管理 Office 365 郵件加密入口網站的一次性處理碼使用

如果 OME 加密的郵件收件者不會使用 Outlook, 不論收件者使用的帳戶為何, 收件者都會收到限制的網頁查看連結, 讓他們能夠讀取郵件。 此連結包含一次性處理常式代碼。 作為系統管理員, 您可以決定收件者是否可以使用一次性傳遞碼來登入 OME 入口網站。
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>若要管理 OME 是否會產生一次性的處理常式代碼
  
1. 使用在您的 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 並啟動 Windows PowerShell 會話並聯機至 Exchange Online。 如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 OTPEnabled 參數執行 Set-omeconfiguration 指令程式:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   例如, 若要停用一次性處理常式代碼:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   若要啟用一次性處理常式代碼:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>在 web 上的 Outlook 中管理 [加密] 按鈕的顯示

作為系統管理員, 您可以管理是否要將此按鈕顯示給使用者。
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>管理 [加密] 按鈕是否顯示在 web 上的 Outlook 中
  
1. 使用在您的 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 並啟動 Windows PowerShell 會話並聯機至 Exchange Online。 如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用-SimplifiedClientAccessEnabled 參數執行 Get-irmconfiguration 程式指令程式:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   例如, 若要停用 [**加密**] 按鈕:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   若要啟用 [**加密**] 按鈕:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>啟用 iOS 郵件應用程式使用者之電子郵件的服務端解密

IOS 郵件應用程式無法解密受 Office 365 郵件加密保護的郵件。 作為 Office 365 系統管理員, 您可以對傳送至 iOS 郵件應用程式的郵件套用服務端解密。 當您選擇使用服務端解密時, 服務會將解密的郵件副本傳送至 iOS 裝置。 用戶端裝置會儲存解密的郵件副本。 即使 iOS 郵件應用程式不會對使用者套用用戶端使用許可權, 郵件也會保留使用許可權的相關資訊。 使用者也可以複製或列印郵件, 即使他們原本沒有這麼做也一樣。 不過, 如果使用者嘗試完成需要 Office 365 郵件伺服器的動作 (例如轉寄郵件), 則伺服器不會允許該動作 (如果使用者原本未使用此方法)。 不過, 使用者可以從 iOS 郵件應用程式內的不同帳戶轉寄郵件, 以解決「不要轉寄」使用限制。 不論您是否設定郵件的服務端解密, 您都無法在 iOS 郵件應用程式中查看加密和受版權保護之郵件的附件。
  
如果您選擇 [不允許將解密的郵件傳送至 iOS 郵件應用程式使用者], 使用者會收到一則訊息, 指出他們沒有查看郵件的許可權。 根據預設, 不會啟用電子郵件的服務端解密。
  
如需詳細資訊, 以及用戶端體驗的觀點, 請參閱[在 iPhone 或 iPad 上查看加密的郵件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)。
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>管理 iOS 郵件應用程式使用者是否可以查看 Office 365 郵件加密所保護的郵件
  
1. 使用在您的 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 並啟動 Windows PowerShell 會話並聯機至 Exchange Online。 如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 AllowRMSSupportForUnenlightenedApps 參數執行 ActiveSyncOrganizations 指令程式:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   例如, 若要設定服務, 在將郵件傳送至 unenlightened 應用程式 (如 iOS 郵件應用程式) 之前, 將郵件解密:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   或者, 若要將服務設定為不傳送解密的郵件至 unenlightened 應用程式, 請執行下列動作:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>啟用 web 瀏覽器郵件用戶端之電子郵件附件的服務端解密

通常, 當您使用 Office 365 郵件加密時, 會自動加密附件。 作為 Office 365 系統管理員, 您可以對使用者從網頁瀏覽器下載的電子郵件附件套用服務端解密。
  
當您使用服務端解密時, 服務會將檔案的解密複本傳送至裝置。 郵件仍然加密。 即使瀏覽器不會對使用者套用用戶端使用許可權, 電子郵件附件也會保留有關使用許可權的資訊。 使用者可以複製或列印電子郵件附件, 即使他們原來並未擁有這麼做的權利。 不過, 如果使用者嘗試完成需要 Office 365 郵件伺服器的動作 (例如轉寄附件), 則伺服器不會允許該動作 (如果使用者原本未使用此方法)。
  
不論您是否設定附件的服務端解密, 使用者都無法在 iOS 郵件應用程式中查看加密和受版權保護郵件的任何附件。
  
如果您選擇不允許解密的電子郵件附件 (預設值), 則使用者會收到一則訊息, 指出他們沒有查看附件的許可權。
  
如需有關 Office 365 如何使用 [僅供加密] 選項來為電子郵件和電子郵件附件進行加密的詳細資訊, 請參閱[電子郵件的 [僅加密] 選項。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>管理電子郵件附件是否會在從網頁瀏覽器下載時解密
  
1. 使用在您的 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 並啟動 Windows PowerShell 會話並聯機至 Exchange Online。 如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 DecryptAttachmentFromPortal 參數執行 Get-irmconfiguration 程式指令程式:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   例如, 若要設定服務以在使用者從網頁瀏覽器下載時解密電子郵件附件, 請執行下列動作:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   若要將服務設定為在下載時保留加密的電子郵件附件:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only"></a>確定所有外部收件者都使用 OME 入口網站來讀取加密的郵件 (僅限 Office 365 高級郵件加密)

如果您有 Office 365 高級郵件加密, 您可以使用自訂品牌範本, 強制收件者收到包裝者郵件, 讓他們在 OME 入口網站中讀取加密的電子郵件, 而不是使用 Outlook 或 web 上的 Outlook。 如果您想要更進一步控制收件者如何使用他們收到的郵件, 您可能會想要這麼做。 例如, 如果外部收件者在 web 入口網站中查看電子郵件, 您可以設定電子郵件的到期日, 您也可以撤銷電子郵件。 這些功能只支援透過 OME 入口網站。 您可以在建立郵件流程規則時, 使用 [加密] 選項和 [不要轉寄] 選項。

### <a name="create-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email-to-be-revocable-and-expire-in-7-days"></a>建立自訂範本, 以強制所有外部收件者都使用 OME 入口網站, 以及將加密的電子郵件設為可撤銷且7天后到期

1. 使用在您的 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 並啟動 Windows PowerShell 會話並聯機至 Exchange Online。 如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 執行 Set-omeconfiguration Cmdlet:

   ```powershell
   New-OMEConfiguration -Identity "<template name>" -ExternalMailExpiryInDays 7
   ```

   其中`template name`是您想要用於 Office 365 郵件加密自訂品牌範本的名稱。 For example,

   ```powershell
   New-OMEConfiguration -Identity "<One week expiration>" -ExternalMailExpiryInDays 7
   ```

3. 執行 Get-transportrule 程式 Cmdlet:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    其中：

   - `mail flow rule name`是您要用於新郵件流程規則的名稱。

   - `option name`是`Encrypt`或`Do Not Forward`。

   - `template name`是您提供自訂品牌範本的名稱, 例如`One week expiration`。

   若要將所有的外部電子郵件加密為「一周到期」範本, 並套用 [僅供加密] 選項:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

   若要使用「一周到期」範本來加密所有外部電子郵件, 並套用 [不要轉寄] 選項:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>自訂電子郵件的外觀和 OME 入口網站

如需如何為組織自訂 OME 的詳細資訊, 請參閱[將貴組織的品牌新增至您的加密郵件](add-your-organization-brand-to-encrypted-messages.md)。
  
## <a name="disable-the-new-capabilities-for-ome"></a>停用 OME 的新功能

我們希望它不會進入它, 但如果您需要, 停用 OME 的新功能就非常簡單。 首先, 您必須移除您建立的任何使用新 OME 功能的郵件流程規則。 如需移除郵件流程規則的詳細資訊, 請參閱[管理郵件流程規則](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)。 然後, 請在 Exchange Online PowerShell 中完成下列步驟。
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>停用 OME 的新功能
  
1. 使用在 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 啟動 Windows PowerShell 會話, 並聯機至 Exchange Online。 如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 如果您已在網頁版 Outlook 中啟用 [**加密**] 按鈕, 請使用 SimplifiedClientAccessEnabled 參數執行 get-irmconfiguration 程式指令程式以將其停用。 否則, 請略過此步驟。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. 使用 AzureRMSLicensingEnabled 參數設定為 false 來執行 Get-irmconfiguration 程式指令程式, 以停用 OME 的新功能:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
