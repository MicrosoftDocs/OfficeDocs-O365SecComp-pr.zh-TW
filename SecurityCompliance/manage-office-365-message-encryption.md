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
# <a name="manage-office-365-message-encryption"></a>管理 Office 365 郵件加密

您已完成設定 up Office 365 郵件加密 (OME)，您可以自訂在數種方式部署的設定。例如，您可以設定是否要啟用一次性複雜代碼、 網頁伺服器與多上的 Outlook 中顯示 [**保護**] 按鈕。本文中的工作說明如何。 
  
||
|:-----|
|本文屬於較大的一系列有關 Office 365 郵件加密的文章。本文適用於系統管理員及 IT 專業人員的。如果您只尋找的資訊在傳送或接收加密的郵件，請參閱[Office 365 郵件加密 (OME)](ome.md)中的文章的清單並找出最適合您需求的文章。 |
   
## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>管理是否 Google、 Yahoo、 及 Microsoft 帳戶的收件者可以使用這些帳戶來登入 Office 365 郵件加密入口網站
<a name="PermitSocialID"> </a>

根據預設，當您設定新的 Office 365 郵件加密功能，您組織中的使用者可以傳送郵件給 Office 365 組織外收件者。收件者若收件者使用*社交識別碼*例如 Google 帳戶、 Yahoo 帳戶或 Microsoft 帳戶，則可以登入 OME 入口網站使用社交 id。如果您想您可以選擇不允許使用社交識別碼來登入 OME 入口網站的收件者。 
  
 **若要管理要允許使用社交識別碼來登入 OME 入口網站的收件者**
  
1. [連線至 Exchange Online 使用遠端 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。
    
2. 執行 Set-omeconfiguration 指令程式搭配 SocialIdSignIn 參數如下所示：
    
  ```
  Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true |$false >
  ```

    例如，若要停用社交 Id：
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
  ```

    若要啟用社交 Id：
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
  ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a>管理一次性複雜代碼用於登入 Office 365 郵件加密入口網站
<a name="GenerateOTPC"> </a>

根據預設，如果依 OME 加密郵件的收件者不使用 Outlook，不論收件者，所使用的帳戶收件者會收到讓讀取郵件的時間限制 web 檢視連結。這包括一次性複雜的程式碼。以系統管理員可以管理一次性複雜碼可用來登入 OME 入口網站。
  
 **若要管理一次性複雜的程式碼產生的 OME**
  
1. [連線至 Exchange Online 使用遠端 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。
    
2. 執行 Set-omeconfiguration 指令程式搭配 OTPEnabled 參數如下所示：
    
  ```
  Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true |$false >
  ```

    例如，若要停用一次性複雜的程式碼：
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
  ```

    若要啟用一次性複雜的程式碼：
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
  ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a>管理 Outlook web 上的 [保護] 按鈕的顯示
<a name="DisplayProtectButton"> </a>

根據預設，在網路上的 Outlook [**保護**] 按鈕未啟用設定 OME 時。以系統管理員可以管理要對使用者顯示此按鈕。 
  
 **若要管理 [保護] 按鈕會出現在網路上的 Outlook**
  
1. [連線至 Exchange Online 使用遠端 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。
    
2. 執行 Set-irmconfiguration 指令程式搭配-SimplifiedClientAccessEnabled 參數如下所示：
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true |$false >
  ```

    例如，若要停用 [**保護**] 按鈕： 
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
  ```

    若要啟用 [**保護**] 按鈕： 
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
  ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>啟用服務端解密的 iOS 郵件應用程式使用者的電子郵件
<a name="EnableServiceSideDecrypt"> </a>

IOS 郵件應用程式無法解密受保護與 Office 365 郵件加密的郵件。身為 Office 365 管理員，您可以套用服務端解密的郵件傳遞至 iOS 郵件應用程式。當您選擇這樣做時，服務會將已解密的郵件複本傳送至 iOS 裝置。郵件會儲存在用戶端裝置上解密。即使 iOS 郵件應用程式不會套用至使用者的用戶端使用權限訊息也會保留 usage 權限的相關資訊。這表示使用者可以複製或列印郵件即使因原本沒有要執行這項操作的權限。不過，如果使用者嘗試完成需要 Office 365 的郵件伺服器，例如轉寄郵件的動作，伺服器不如果使用者原本沒有這樣的 usage 權限允許巨集指令。不過，使用者可以藉由轉寄的郵件不論是否設定服務端解密的郵件其 iOS 郵件 app 中的不同帳戶時解決不要轉寄流量限制、 任何附件加密和權限受保護的郵件無法檢視 iOS 郵件應用程式中。
  
如果您選擇不要允許解密的郵件傳送至 iOS 郵件應用程式的使用者，使用者會收到訊息表示它們不需要檢視郵件的權限。根據預設，未啟用服務端解密的電子郵件訊息。
  
如需詳細資訊及用戶端體驗的檢視，請參閱] 區段中，在[檢視加密的郵件 iPhone 或 iPad 上](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)的 「[檢視加密的郵件 iPhone 或 iPad 上](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf#iOSEncryptedMail)」。
  
 **若要管理 iOS 郵件應用程式的使用者可以檢視受保護之 Office 365 郵件加密的郵件**
  
1. [連線至 Exchange Online 使用遠端 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。
    
2. 執行設定 ActiveSyncOrganizations 指令程式搭配 AllowRMSSupportForUnenlightenedApps 參數如下所示：
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true |$false >
  ```

    例如，若要設定解密的郵件前它們傳送到 unenlightened 應用程式的服務例如 iOS 郵件應用程式：
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
  ```

    例如，若要設定服務未將解密的郵件傳送至 unenlightened 應用程式：
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
  ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>啟用服務端解密的網頁瀏覽器郵件用戶端的電子郵件附件
<a name="EnableServiceSideDecrypt"> </a>

一般而言，當您使用 Office 365 郵件加密時，會自動加密附件。Office 365 系統管理員身分您可以套用服務端解密使用者下載從網頁瀏覽器中的電子郵件附件。 
  
當您選擇這樣做時，服務會將解密檔案的複本傳送至裝置。仍處於加密郵件。即使在瀏覽器不會套用至使用者的用戶端使用權限電子郵件附件也會保留 usage 權限的相關資訊。這表示使用者可以複製或列印電子郵件附件即使因原本沒有要執行這項操作的權限。但如果使用者嘗試完成動作所需的 Office 365 郵件伺服器，例如轉寄附件，伺服器不如果使用者原本沒有這樣的 usage 權限允許巨集指令。
  
不論是否您設定服務端解密的附件，任何附件的加密和權限受保護的郵件無法 iOS 郵件應用程式中檢視。
  
如果您選擇不要允許解密電子郵件附件，這是預設值，使用者會收到訊息表示它們不需要檢視附件的權限。\* \* \*插入圖片吗？
  
如需 Office 365 如何實作加密電子郵件及電子郵件附件的加密唯讀] 選項的詳細資訊，請參閱[僅限加密的電子郵件選項。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
 **若要管理電子郵件附件進行解密上從網頁瀏覽器的下載 （英文）**
  
1. [連線至 Exchange Online 使用遠端 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。
    
2. 執行 Set-irmconfiguration 指令程式搭配 DecryptAttachmentFromPortal 參數如下所示：
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal <$true |$false >
  ```

    例如，服務設定為解密電子郵件附件時使用者下載這些從網頁瀏覽器：
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal $true
  ```

    若要設定為它們在下載時保留加密的電子郵件附件服務：
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal $false
  ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a>自訂電子郵件和 OME 入口網站的外觀
<a name="CustomizeAppearance"> </a>

如需如何自訂 OME 組織的詳細資訊，請參閱[新增至您已加密郵件的貴組織的商標](add-your-organization-brand-to-encrypted-messages.md)。
  
## <a name="disabling-the-new-capabilities-for-ome"></a>停用的新功能以進行 OME
<a name="CustomizeAppearance"> </a>

我們希望它不會跳到其中，但如果您需要、 OME 非常簡單停用的新功能。首先，您需要移除任何郵件流程而建立的規則已使用新的 OME 功能。如需移除郵件流程規則的資訊，請參閱[管理郵件流程規則](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)。然後，完成這些步驟在 Exchange Online PowerShell。
  
 **針對 OME 停用的新功能**
  
1. [連線至 Exchange Online 使用遠端 PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)。
    
2. 如果您啟用的網路上的 Outlook [保護] 按鈕，停用它使用來執行 Set-irmconfiguration 指令程式 SimplifiedClientAccessEnabled 參數，如下所示：
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
  ```

3. 執行 Set-irmconfiguration 指令程式搭配 AzureRMSLicensingEnabled 參數如下所示：
    
  ```
  Set-IRMConfiguration -AzureRMSLicensingEnabled $false
  ```


