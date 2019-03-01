---
title: 將您組織的品牌新增至您的加密郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- M365-security-compliance
description: 為 Exchange 系統管理員，您可以套用貴組織的品牌貴組織的加密的電子郵件和加密入口網站的內容。
ms.openlocfilehash: b15bb058d68d0f1783d2a689fff180a2bf48023e
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341704"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>將貴組織的品牌新增至您的加密郵件

以 Exchange Online 或 Exchange Online Protection 系統管理員身分，您可以套用貴公司商標新增至自訂貴組織的 Office 365 郵件加密電子郵件的外觀和加密入口網站的內容。使用 Get-omeconfiguration 和 Set-omeconfiguration Windows PowerShell cmdlet，您可以自訂加密的電子郵件的收件者的檢視體驗的下列層面：
  
- 包含加密訊息的電子郵件簡介文字
- 包含加密訊息的電子郵件免責聲明文字
- OME 入口網站中出現的文字
- 會出現在電子郵件訊息和 OME 入口網站的標誌
- 在電子郵件訊息和 OME 入口網站的背景色彩

您也可以隨時回復為預設的外觀與風格。

如果您想要更多控制，您可以建立多個範本來自您組織的加密電子郵件。使用這些範本，您可以控制不只是電子郵件、 外觀與風格，但也可以控制使用者經驗的部分。例如，您可以指定收件者的郵件套用此範本，而且誰使用 Google、 Yahoo，以及 Microsoft 帳戶可以使用這些帳戶來登入 Office 365 郵件加密入口網站。您可以使用範本來滿足幾個使用情況下，例如：

- 每個部門，例如財務、 銷售等的範本。
- 不同產品的範本
- 不同地理區域或國家/地區的範本

一旦您已經建立範本，您可以套用至已加密的電子郵件使用 Exchange 郵件流程規則。可以撤銷品牌使用這些範本的所有郵件。
  
||
|:-----|
|本文屬於較大的一連串的 Office 365 郵件加密的相關文章。本文適用於系統管理員和 ITPros。如果您只是正在尋找的資訊傳送或接收的加密的訊息，請參閱在[Office 365 郵件加密 (OME)](ome.md)中的文章的清單，並找出最適合您需求的文章。|
||

## <a name="create-branding-templates"></a>建立品牌的範本

您為組織中使用 Windows PowerShell 新增 Set-omeconfiguration 指令程式建立品牌的範本。一旦您已經建立該範本，您可以使用 Set-omeconfiguration 指令程式定義之範本的部分。您可以建立多個範本。

![可自訂電子郵件組件](media/ome-template-breakout.png)
  
1. 使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。

2. 使用新增 Set-omeconfiguration 指令程式來建立新的範本。

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```
   例如，

   ```powershell
   New-OMEConfiguration -Identity <Branding template 1>
   ```
3. 定義您定義使用 Set-omeconfiguration 指令程式[Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)所述之範本所做的自訂或使用下表取得指引。

|**若要自訂此加密經驗功能**|**使用這些命令**|
|:-----|:-----|
|背景色彩|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|標誌|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支援的檔案格式：.png、.jpg、.bmp 或 .tiff  <br/> 標誌檔案的最佳大小：小於 40 KB  <br/> 標誌影像的最佳大小：170x70 像素|
|寄件者的名稱和電子郵件地址] 旁的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|「 讀取的郵件 」 按鈕顯示的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|欄上方會出現在 「 讀取的郵件 」 按鈕下方的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|包含加密訊息之電子郵件中的免責聲明|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|出現在加密郵件檢視入口網站上方的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|若要啟用或停用驗證，使用此自訂範本次傳遞程式碼|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **範例：** <br/>若要啟用一次性密碼此自訂範本 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> 若要停用一次性密碼此自訂範本 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|若要啟用或停用此自訂範本的 Microsoft、 Google 或 Yahoo 身分識別與驗證|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **範例：** <br/>若要啟用此自訂範本的社交識別碼 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> 若要停用社交此自訂的範本識別碼 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a>若要移除依 OME 加密 OME 入口網站和電子郵件訊息的品牌自訂內容
  
1. [連線至 Exchange Online PowerShell](https://aka.ms/exopowershell) (機器翻譯)。

2. [Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)所述，請使用**Set-omeconfiguration**指令程式。若要移除您組織的品牌自訂項目從 DisclaimerText，EmailText，和 PortalText 值，將值設定為空字串， `""`。針對所有影像值，例如標誌，將值設為`"$null"`。

**加密自訂選項**

**將加密體驗的這項功能回復為預設文字和影像**|**使用這些命令**|
|:-----|:-----|
|加密電子郵件隨附的預設文字  <br/> 預設文字會出現在檢視加密郵件的指示上方。|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|包含加密訊息之電子郵件中的免責聲明|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|出現在加密郵件檢視入口網站上方的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **範例回還原預設值：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
|標誌|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **範例回還原預設值：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|背景色彩|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **範例回還原預設值：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a>建立適用於 Exchange 郵件流程規則將自訂品牌對加密的電子郵件

您已建立的品牌的範本後，您可以建立 Exchange 郵件流程規則來套用該自訂品牌根據特定條件。在下列案例中的自訂品牌套用這類規則：

- 如果電子郵件以手動方式加密的使用者從 Outlook 或網頁 （原先稱為 Outlook Web App） 用戶端
- 如果電子郵件會自動加密的 Exchange 郵件流程規則] 或 [Office 365 資料外洩防護原則

如需如何建立適用於加密 Exchange 郵件流程規則的詳細資訊，請參閱 <<c0>定義郵件流規則以加密 Office 365 中的電子郵件。

1. 在網頁瀏覽器中使用已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)工作或學校帳戶。

2. 選擇 [**管理**] 磚。

3. 在 Office 365 系統管理中心中，選擇 [**系統管理中心** \> **Exchange**。

4. 在 EAC 中，移至 [**郵件流程** \> **規則**，然後選擇 [**新增** ![[新增] 圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。如需使用 EAC 的詳細資訊，請參閱[Exchange 系統管理中心在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 [**名稱**] 中，輸入規則名稱，例如銷售部門的品牌。

6. 在 [**套用此規則，如果**選擇一個條件，從可用的條件清單中選取 [**寄件者位於在組織內**的條件，以及其他您想要的條件。例如，您可能想要套用特定的品牌範本，以：

     - 所有加密的電子郵件寄件者的財務部門成員
     - 與特定關鍵字例如 「 外部 」 或 「 夥伴 」 傳送加密的電子郵件
     - 加密的電子郵件傳送至特定網域

7. 從**執行下列動作**，選取 [**修改郵件安全性** > **套用自訂商標至 OME 郵件**。接下來，從下拉式清單中，選取與您所建立的品牌範本。
8. （選用）如果您想郵件流程規則，以也適用於加密除了自訂品牌，從**執行下列動作**，選取 [**修改郵件安全性**，然後選擇 [**適用於 Office 365 郵件加密和權限保護**。從清單中選取的 RMS 範本，選擇 [**儲存**]，然後選擇 [**確定]**。
  
     範本的清單包含所有的預設範本及 Office 365 所使用的選項，以及您已建立的任何自訂範本。如果清單是空的請確定您已設定 Office 365 郵件加密與新功能[設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。如需預設範本的資訊，請參閱[設定與管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。[**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。[**僅限加密**] 選項的相關資訊，請參閱[僅加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

     如果您想要指定另一個動作，您可以選擇**新增巨集指令**。
