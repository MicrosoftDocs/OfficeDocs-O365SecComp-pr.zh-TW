---
title: 將您的組織品牌新增至加密的郵件
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 作為 Office 365 全域系統管理員, 您可以將組織的署名套用至組織的加密電子郵件和加密入口網站的內容。
ms.openlocfilehash: 19f227971c522f9d92aec343f1865ab7f23c13aa
ms.sourcegitcommit: b0ea2d66bc4c7f2fc0a8abab28d2ae652b1c4b73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2019
ms.locfileid: "34721370"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>將貴組織的品牌新增至您的加密郵件

做為 Exchange Online 或 Exchange Online Protection 系統管理員, 您可以套用公司品牌, 以自訂群組織的 Office 365 郵件加密電子郵件和加密入口網站的內容。 使用 Set-omeconfiguration 和 Set-omeconfiguration 的 Windows PowerShell Cmdlet, 您可以為加密的電子郵件的收件者自訂下列觀看體驗的各個層面:
  
- 包含加密訊息的電子郵件簡介文字

- 包含加密訊息的電子郵件免責聲明文字

- 出現在 OME 入口網站中的文字

- 出現在電子郵件和 OME 入口網站中的標誌

- 電子郵件訊息和 OME 入口網站中的背景色彩

您也可以隨時回復為預設的外觀與風格。

 如果您想要進行更多控制, 您可以使用 Office 365 高級郵件加密, 並為來自您組織的加密電子郵件建立多個範本。 使用這些範本, 您可以控制不只是電子郵件的外觀和風格, 也能控制使用者的使用者經驗。 例如, 您可以指定是否已套用此範本的郵件收件者, 以及使用 Google、Yahoo 和 Microsoft 帳戶的使用者, 都可以使用這些帳戶登入 Office 365 郵件加密入口網站。 您可以使用範本來完成數個使用案例, 例如:

- 每個部門的範本, 例如 [財務]、[銷售] 等等。

- 不同產品的範本

- 不同地理區域或國家/地區的範本

- 您是否要允許撤銷電子郵件

- 您是否希望傳送給外部收件者的電子郵件在指定的天數後到期。

建立範本之後, 您可以使用 Exchange 郵件流程規則將它們套用至加密的電子郵件。 如果您有 Office 365 高級郵件加密, 您可以使用這些範本來撤銷您所署名的任何電子郵件。
  
||
|:-----|
|本文是更多有關 Office 365 郵件加密的文章系列的一部分。 本文適用于系統管理員和 ITPros。 如果您只是尋找傳送或接收加密郵件的相關資訊, 請參閱[Office 365 訊息加密 (OME)](ome.md)中的文章清單, 並找出最符合您需求的文章。|
||

## <a name="create-branding-templates"></a>建立品牌範本

您可以使用 Set-omeconfiguration Cmdlet, 在 Windows PowerShell 中建立組織的品牌範本。 建立範本之後, 您可以使用 Set-omeconfiguration 指令程式來定義範本的元件。 您可以建立多個範本。

![可自訂的電子郵件元件](media/ome-template-breakout.png)
  
1. 使用在 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 啟動 Windows PowerShell 會話, 並聯機至 Exchange Online。 如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 Set-omeconfiguration Cmdlet 來建立新的範本。

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```

   For example,

   ```powershell
   New-OMEConfiguration -Identity "Branding template 1"
   ```

3. 使用 set- [set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)中所述的 set-omeconfiguration 指令程式, 定義您剛定義之範本的自訂專案, 或使用下表以取得指導方針。

|**若要自訂此加密經驗功能**|**使用這些命令**|
|:-----|:-----|
|背景色彩|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|商標|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支援的檔案格式：.png、.jpg、.bmp 或 .tiff  <br/> 標誌檔案的最佳大小：小於 40 KB  <br/> 標誌影像的最佳大小：170x70 像素|
|寄件者的名稱和電子郵件地址旁的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|[讀取郵件] 按鈕上顯示的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|出現在 [讀取郵件] 按鈕下方的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|包含加密訊息之電子郵件中的免責聲明|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|出現在加密郵件檢視入口網站上方的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|若要啟用或停用此自訂範本的一次性程式碼驗證|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **範例：** <br/>若要啟用此自訂範本的一次性 passcodes <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> 若要停用這個自訂範本的一次性 passcodes <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|啟用或停用此自訂範本的 Microsoft、Google 或 Yahoo 身分識別的驗證|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **範例：** <br/>若要啟用此自訂範本的社交識別碼 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> 停用此自訂範本的社交識別碼 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a>從 OME 入口網站中移除品牌自訂, 以及由 OME 加密的電子郵件
  
1. [連線至 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用**set-omeconfiguration**指令程式, 如[set-set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)中所述。 若要從 DisclaimerText、EmailText 及 PortalText 值中移除組織的署名自訂, 請將值設定為空字串`""`。 針對所有圖像值 (例如 [標誌]), 將值`"$null"`設為。

**加密自訂選項**

**將加密體驗的這項功能回復為預設文字和影像**|**使用這些命令**|
|:-----|:-----|
|加密電子郵件隨附的預設文字  <br/> 預設文字會出現在檢視加密郵件的指示上方。|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|包含加密訊息之電子郵件中的免責聲明|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|出現在加密郵件檢視入口網站上方的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **範例回復為預設值:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
|商標|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **範例回復為預設值:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|背景色彩|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **範例回復為預設值:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a>建立將自訂品牌套用至加密電子郵件的 Exchange 郵件流程規則

建立品牌範本之後, 您可以建立 Exchange 郵件流程規則, 以根據特定條件套用該自訂品牌。 在下列案例中, 這類規則會套用自訂品牌:

- 如果最終使用者從 Outlook 或 Outlook 網頁版 (先前稱為 Outlook Web App) 用戶端手動加密電子郵件

- 如果電子郵件已由 Exchange 郵件流程規則或 Office 365 資料遺失防護原則自動加密

如需如何建立套用加密的 Exchange 郵件流程規則的詳細資訊, 請參閱[定義郵件流程規則, 以在 Office 365 中加密電子郵件](define-mail-flow-rules-to-encrypt-email.md)。

1. 在網頁瀏覽器中, 使用已被授與全域系統管理員許可權的公司或學校帳戶, 登[入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 選擇 [系統**管理**] 磚。

3. 在 Office 365 系統管理中心, 選擇 [系統**管理中心** \> ] [ **Exchange**]。

4. 在 EAC 中, 移至 [**郵件流程** \> **規則**], 然後選取](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> [**新增** ![新的圖示] [**建立新的規則**]。 如需使用 EAC 的詳細資訊, 請參閱 exchange [Online 中的 exchange 系統管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 [**名稱**] 中, 輸入規則的名稱, 例如 [銷售部門的商標]。

6. 在 [選取條件] 的 [套用**此規則**] 中, 選取**寄件者位於組織內部**的條件, 以及您在可用條件清單中所需的其他條件。 例如, 您可能會想要將特定的品牌範本套用至:

     - 從財務部門成員傳送的所有加密電子郵件
     - 以特定關鍵字 (例如 "External" 或 "Partner") 傳送的加密電子郵件
     - 傳送至特定網域的加密電子郵件

7. 從**執行下列**動作, 選取 **[修改郵件安全性** > 套用**自訂品牌以 OME 郵件**]。 接下來, 從下拉式清單中選取您建立的品牌範本。

8. 步驟如果您想要郵件流程規則除了自訂品牌之外也要套用加密, 請從**執行下列**動作, 選取 [**修改郵件安全性**], 然後選擇 [套用**Office 365 郵件加密和許可權保護**]。 從清單中選取 RMS 範本, 選擇 [**儲存**], 然後選擇 **[確定]**。
  
     範本清單包含所有預設範本及選項, 以及您建立供 Office 365 使用的任何自訂範本。 如果清單是空的, 請確定您已使用[設定新的 office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)中所述的新功能, 來設定 Office 365 郵件加密。 如需預設範本的詳細資訊, 請參閱設定[和管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。 如需 [**不要轉寄**] 選項的詳細資訊, 請參閱[電子郵件的 [不要轉寄] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 如需 [**僅加密**] 選項的詳細資訊, 請參閱[僅加密電子郵件選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

     如果您想要指定另一個動作, 您可以選擇 [**新增動作**]。
