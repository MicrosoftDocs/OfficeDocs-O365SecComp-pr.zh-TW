---
title: 為您的組織設定監督原則
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: 設定監督檢閱原則以擷取員工通訊供檢閱。
ms.openlocfilehash: af317194fcf551acde8c53cdf6aa38bfb040dc84
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216733"
---
# <a name="configure-supervision-policies-for-your-organization"></a>為您的組織設定監督原則

使用監督原則來擷取由內部或外部檢閱者檢查 「 員工通訊。如需監督原則可幫助您監視組織中的通訊的詳細資訊，請參閱[Office 365 中的監督原則](supervision-policies.md)。

> [!NOTE]
> 監督原則受監控的使用者必須具有進階規範附加元件可以是 Office 365 企業版 E3 授權或包含在 Office 365 企業版 E5 訂閱。如果您未有現有的企業 E5 計劃以及要嘗試監督，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。
  
請遵循下列步驟來設定和 Office 365 組織中使用監督：
  
- **步驟 1 （選用）** - [設定的監督群組](configure-supervision-policies.md#exampledist)

    在您開始使用監督之前，請決定誰將其通訊檢閱和誰可以執行這些檢閱 （英文）。如果您想要開始使用少數使用者看到監督的運作方式，您可以略過現在群組設定。

- **步驟 2 （必要）** - [讓組織中可用的監督](configure-supervision-policies.md#MakeAvailable)

    新增您自己監督檢閱角色群組讓您可以設定原則。已指派給此角色的任何人可以存取**資料控管**下 [**監督**頁面的安全性 & 規範中心。若要檢閱的電子郵件裝載於 Exchange Online，每一個檢閱者也必須具有[遠端 PowerShell 存取至 Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。

- **步驟 3 （選用）** - [設定自訂的敏感資訊類型或自訂的關鍵字字典/lexicons](configure-supervision-policies.md#sensitiveinfo)

    如果您需要使用自訂的敏感資訊類型或自訂的關鍵字字典監督原則，您需要建立開始監督精靈之前。

- **步驟 4 （必要）** - [設定的監督原則](configure-supervision-policies.md#setupsuper)

    您將建立監督原則中安全性 & 規範中心。這些原則定義的通訊會受到組織中的檢閱和指定誰應該執行檢閱 （英文）。通訊包含電子郵件和 Microsoft 小組通訊，以及第 3 廠商平台通訊 （例如 Facebook、 Twitter、 等）

- **步驟 5-（選用）**[測試您的新監督原則](configure-supervision-policies.md#TestPolicy)

    測試以確保能運作視您監督原則是確保合規策略會議您標準重要的一部分。

- **步驟 6-（選用）**[Outlook 增益集不想要使用 Office 365 監督儀表板或 （前身為 Outlook Web App） 在 web 上的 Outlook 檢閱監督的通訊的檢閱者的設定](configure-supervision-policies.md#UseOutlook)

    監督的增益集 Outlook 可以讓檢閱者存取 Outlook 用戶端內的監督的功能權限，讓他們可以評估並將每個項目。

<a name="exampledist"> </a>

## <a name="step-1---set-up-groups-for-supervision-optional"></a>步驟 1-設定群組的監督 （選用）

 當您建立監督原則時，您將決定誰會有檢閱其通訊及誰可以執行這些檢閱 （英文）。在原則中，您將使用電子郵件地址來識別的個人或群組的人員。若要簡化您的安裝程式，建立人員有其檢閱的通訊群組和人員將檢閱這些通訊群組。如果您使用的群組，您可能需要數個 — 例如，如果您想要監視的人員、 兩個不同的群組之間的通訊，或者您想要指定無法移至要指導的群組。如需此的運作方式的詳細資訊，請參閱[範例通訊群組](configure-supervision-policies.md#GroupExample)。
  
若要管理組織中的群組內或之間的通訊、 設定通訊群組在 Exchange 系統管理中心 (移至 [**收件者** \> **群組**)。如需設定通訊群組的詳細資訊，請參閱[管理通訊群組](http://go.microsoft.com/fwlink/?LinkId=613635)
  
> [!NOTE]
> 您也可以使用動態通訊群組或安全性群組的監督若您偏好。若要協助您決定是否這些更適合您組織需求，請參閱[管理擁有郵件功能的安全性群組](http://go.microsoft.com/fwlink/?LinkId=627033)及[管理動態通訊群組](http://go.microsoft.com/fwlink/?LinkId=627058)。
  
<a name="GroupExample"> </a>

### <a name="example-distribution-groups"></a>通訊群組範例

此範例會包含已針對名為 Contoso 財務國際財務組織設定的通訊群組。
  
在 Contoso Financial International 中，必須抽樣監管美國境內各代理人間的通訊。不過，不需要監管該群組內的法務人員。在此範例中，我們可以建立下列群組：
  
|**設定此通訊群組**|**群組地址 (別名)**|**描述**|
|:-----|:-----|:-----|
|所有美國代理人 | US_Brokers@Contoso.com | 此群組包含於 Contoso 任職，所有位於美國的代理人的電子郵件地址。 |
| 所有美國法務人員 | US_Compliance@Contoso.com  | 此群組包含所有的美國型法務人員合作 Contoso 的電子郵件地址。因為此群組的所有美國型經紀人子集，您可用於此別名免除法務人員從監督原則。 |
  
<a name="MakeAvailable"> </a>

## <a name="step-2---make-supervision-available-in-your-organization-required"></a>步驟 2-產生監督提供組織 （必要）

在安全性 & 規範中心進行**監督**可作為功能表選項，您必須指派監督檢閱系統管理員角色。
  
為達成此目的，您也可以新增您自己做監督檢閱角色群組的成員，或您可以建立新的角色群組。
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>新增成員至監督檢閱角色群組

1. 登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中的管理帳戶的認證。

2. 在安全性 & 規範中心中，移至 [**權限**。

3. 選取 [**監督檢閱**角色群組，然後按一下 [編輯] 圖示。

4. 在 [**成員**] 區段中，新增您想要管理您的組織的監督的人員。

### <a name="create-a-new-role-group"></a>建立新的角色群組

1. 登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中的管理帳戶的認證。

2. 在安全性 & 規範中心中，移至 [**權限**和 [新增 (**+**)。

3. 在 [**角色**] 區段中，按一下 [新增] (**+**) 和**監督檢閱管理員**下的捲軸。將此角色新增至角色群組。

4. 在 [**成員**] 區段中，新增您想要管理您的組織的監督的人員。

如需有關角色群組和權限的詳細資訊，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>啟用遠端 PowerShell 存取檢閱者 （若電子郵件會被託管在 Exchange Online）

1. 請遵循[啟用或停用 access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)中的指引。

<a name="sensitiveinfo"> </a>
  
## <a name="step-3---create-custom-sensitive-information-types-or-custom-keyword-dictionaries-optional"></a>步驟 3-建立自訂的敏感資訊類型或自訂的關鍵字字典 （選用）

若要挑選的現有自訂的敏感資訊類型或自訂的關鍵字字典監督原則] 精靈中，您需要視建立這些項目。

### <a name="create-custom-sensitive-information-types"></a>建立自訂的敏感資訊類型

1. 在 Office 365 安全性 & 規範中心中建立新的敏感資訊類型。瀏覽至 [**分類** \> **敏感資訊類型**並遵循**新增敏感資訊類型] 精靈**中的步驟。將以下：

    - 定義的名稱和描述的敏感資訊類型
    - 定義鄰近、 信賴等級和主要圖樣元素
    - 檢閱您的選項，並建立的敏感資訊類型

    如需詳細資訊，請參閱[建立自訂的敏感資訊類型](create-a-custom-sensitive-information-type.md)。

### <a name="create-custom-keyword-dictionarylexicon"></a>建立自訂的關鍵字字典/lexicon

1. 使用文字編輯器 （例如 [記事本])，建立新的檔案包含您想要監視監督原則中的關鍵字詞組。確定每個字詞是以一行和**Unicode/utf-16 (一點 Endian)** 格式儲存檔案。
2. 關鍵字檔案匯入您的 Office 365 租用戶使用 PowerShell。若要連線至 Office 365 powershell，請參閱[Connect to Office 365 安全性 & 規範中心 PowerShell。](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)

    您已連線至 Office 365 with PowerShell 之後，請執行下列命令以匯入關鍵字字典：

    ```
    $fileData = Get-Content "your keyword path and file name" -Encoding Byte -ReadCount 0

    New-DlpKeywordDictionary -Name "Name for your keyword dictionary" -Description "optional description for your keyword dictionary" -FileData $fileData
    ```
    如需詳細資訊，請參閱 ＜ [Create 關鍵字字典](create-a-keyword-dictionary.md)。

3. 在 Office 365 安全性 & 規範中心中建立新的敏感資訊類型。瀏覽至 [**分類** \> **敏感資訊類型**並遵循**新增敏感資訊類型] 精靈**中的步驟。將以下：

    - 定義的名稱和描述的敏感資訊類型
    - 將您的自訂字典新增為必要項目相符的項目
    - 檢閱您的選項，並建立的敏感資訊類型

    建立自訂字典/lexicon 之後，您可以檢視已設定使用[Get DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary)指令程式的關鍵字或新增和移除字詞[組 DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary)指令程式。

    如需詳細資訊，請參閱[建立自訂的敏感資訊類型](create-a-custom-sensitive-information-type.md)。

<a name="setupsuper"> </a>

## <a name="step-4---set-up-a-supervision-policy-required"></a>步驟 4-設定 （必要） 的監督原則
  
1. 登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中的管理帳戶的認證。

2. 在 [安全性 & 規範中心中，選取**監督**。
  
3. 選取 [**建立**，然後遵循精靈來設定下列原則的頁面。您使用精靈，將會：

    - 提供該原則的名稱和描述。
    - 選擇 [使用者或群組管理，包括 [選擇使用者或您想要排除的群組。
    - 定義監督原則條件。
    - 選擇 [是否您想要包含敏感資訊類型。這是您可以在其中選取預設和自訂的敏感資訊類型。
    - 定義可供檢閱的通訊的百分比。
    - 選擇 [原則檢閱者。檢閱者可以是個別使用者或[擁有郵件功能的安全性群組](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。
    - 檢閱您的原則選項並建立原則。

<a name="TestPolicy"> </a>

## <a name="step-5---test-your-supervision-policy-optional"></a>步驟 5-測試您的監督原則 （選用）

建立監督原則之後，它會是不錯的選項進行測試以確定您定義的條件會被正確強制原則。如果您監督原則包含敏感資訊類型也可能會想要[測試您的資料外洩防護 (DLP) 原則](create-test-tune-dlp-policy.md)。請遵循下列步驟來測試您的監督原則：

1. 開啟的電子郵件用戶端或 Microsoft 小組以登入您想要測試該的原則所定義的監督使用者。
2. 傳送電子郵件或符合您已定義的監督原則中之準則的 Microsoft 小組聊天室。這可以是關鍵字附件大小、 網域、 等。請確定您決定是否太嚴格或太寬鬆原則中設定格式化的條件組態的設定。

    > [!Note]
    > 電子郵件受限於定義的原則會以幾近即時地處理及之後設定的原則就可以測試。聊天室中的 Microsoft 小組可能需要 24 小時的時間來完全處理原則中。 

3. 登入您的 Office 365 租用戶為監督原則中指定檢閱者。瀏覽至 [**監督** > *您的自訂原則* > **開啟**以檢視該原則的報告。

<a name="UseOutlook"> </a>

## <a name="step-6---set-up-outlook-add-in-for-reviewers-optional"></a>步驟 6-設定 Outlook 增益集的檢閱者 （選用）

想要使用 Outlook，而非使用 Office 365 或網路上的 Outlook 中的監督儀表板檢閱通訊的檢閱者必須安裝的監督增益集其 Outlook 用戶端。

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>步驟 1： 將複製的監督信箱的地址

若要安裝的 Outlook 桌面增益集，您將需要位址監督信箱建立為監督原則安裝程式的一部分。
  
> [!NOTE]
> 如果別人建立原則，您需要從其安裝增益集取得此位址。

 **若要尋找的監督信箱地址**
  
1. 登入[安全性&amp;規範中心](https://protection.office.com)使用 Office 365 組織中的管理帳戶的認證。

2. 移至**監督**。

3. 按一下 [收集您想要檢閱的通訊的監督原則。

4. 原則的詳細資訊彈出式、 下**監督信箱**中複製的位址。<br/>!['監督信箱'] 區段中的監督原則的詳細資訊彈出式顯示醒目提示的監督信箱地址](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a>步驟 2： 設定 Outlook 桌面 access 監督信箱

接下來，檢閱者需要讓他們可以將 Outlook 連接到監督信箱執行幾個的 Exchange Online PowerShell 命令。
  
1. 連線到 Exchange Online PowerShell。[如何執行這？](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. 執行下列命令，其中*SupervisoryReview{GUID}@domain.onmicrosoft.com*是您在上述步驟 1 中複製的地址和*使用者*是檢閱者都要連線至步驟 3 中的監督信箱的名稱。

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. 等待至少一小時前將移至下的步驟 3。

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>步驟 3： 建立 Outlook 設定檔連線至監督信箱

最後一個步驟中，檢閱者必須建立 Outlook 設定檔連線至監督信箱。

> [!NOTE]
> 若要建立新的 Outlook 設定檔，您將在 Windows 控制台中使用 [郵件設定。您需要以取得這些設定的路徑可能會取決於您使用的 Windows 作業系統 （Windows 7、 Windows 8 或 Windows 10），並且已安裝的 Outlook 版本。
  
1. 開啟 [控制台] 中，並在視窗頂端的 [**搜尋**] 方塊中輸入**郵件**。<br/>(不確定如何取得 Control panel？請參閱[所在控制台吗？](https://support.microsoft.com/help/13764/windows-where-is-control-panel))
  
2. 開啟**郵件**應用程式。

3. 在 [**郵件設定-Outlook**中，按一下 [**顯示設定檔**]。<br/>!['郵件安裝-Outlook'' 顯示設定檔 」 按鈕醒目提示] 對話方塊](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. 在 [**郵件**] 按一下 [**新增**]。然後，在**新的設定檔**、 輸入的名稱 （例如**監督**） 監督信箱。<br/>![在 [設定檔名稱] 方塊中顯示名稱 '監督' ' 新設定檔 」 對話方塊](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. 在 [**連線至 Office 365 的 Outlook**中，按一下 [**連接到不同的帳戶**。<br/>![' 連線至 Office 365 Outlook' 郵件與反白顯示 「 連接至不同的帳戶' 連結](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. 在 [**自動帳戶設定**] 選擇**手動安裝程式] 或 [其他伺服器類型**，並再按 [**下一步**。

7. 在 [**選擇您的帳戶類型**，選擇 [ **Office 365**]。然後，在 [**電子郵件地址**] 方塊中輸入您在先前複製監督信箱的地址。<br/>![Outlook 顯示醒目提示 [' 電子郵件地址 」] 方塊中的 [新增帳戶] 對話方塊的 「 選擇您的帳戶類型 」 頁面。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. 出現提示時，輸入您的 Office 365 認證。

9. 如果成功，您會看見**監督-\<原則名稱\>** 在 Outlook 中的資料夾清單檢視中列出的資料夾。

## <a name="powershell-reference"></a>PowerShell 參考 （英文)

必要時，您可建立並管理使用下列 PowerShell cmdlet 的監督原則：

- [新 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [取得 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [設定 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [移除 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [新 SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [設定 SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [取得 SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [取得 SupervisoryReviewOverallProgressReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [取得 SupervisoryReviewTopCasesReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)