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
description: 若要擷取員工通訊，檢閱設定主管檢閱原則。
ms.openlocfilehash: 1e381f5f435c7edb9f59afb07c22905f12d35513
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001026"
---
# <a name="configure-supervision-policies-for-your-organization"></a>為您的組織設定監督原則

使用監督原則來擷取員工通訊，由內部或外部的檢閱者檢查。 如需監督原則可幫助您監視組織中的通訊的詳細資訊，請參閱 < <b0>Office 365 中的監督原則</b0>。

> [!NOTE]
> 受到監督原則的使用者必須擁有可以是 Microsoft 365 E5 合規性授權 Office 365 企業版 E3 授權來搭配進階合規性的附加元件，或包含在 Office 365 企業版 E5 訂閱。
如果您未擁有現有的企業版 E5 方案，以及要嘗試監督，您可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。
  
請遵循下列步驟來設定和使用 Office 365 組織中監督：
  
- **步驟 1 （選用）** - [設定群組的監督 （選用）](#step-1---set-up-groups-for-supervision-optional)

    開始使用監督之前，請決定誰將其通訊檢閱，以及誰可以執行這些檢閱。 如果您想要開始使用少數使用者查看監督的運作方式，您可以略過現在群組設定。

- **步驟 2 （必要）** - [進行 （必要） 組織中可用的監督](#step-2---make-supervision-available-in-your-organization-required)

    將自己新增至主管檢閱角色群組，以便讓您可以設定原則。 擁有此角色指派給任何人可以存取合規性中心中的 [**監督**] 頁面。 若要檢閱的電子郵件裝載於 Exchange Online，每一位檢閱還必須[至 Exchange Online 的遠端 PowerShell 存取](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。

- **步驟 3 （選用）** - [建立自訂機密資訊類型和自訂的關鍵字字典](#step-3---create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)

    如果您需要使用的自訂機密資訊類型或自訂的關鍵字字典監督原則，您需要建立啟動監督精靈之前。

- **步驟 4 （必要）** - [設定的監督原則](#step-4---set-up-a-supervision-policy-required)

    您將建立監督原則與合規性中心。 這些原則定義哪些通訊會受到檢閱您組織中，並指定誰應該執行的檢閱。 通訊包括電子郵件和 Microsoft Teams 的通訊，以及第 3 廠商平台 （例如 Facebook、 Twitter 等等） 的通訊

- **步驟 5-（選用）**[測試您的監督原則](#step-5---test-your-supervision-policy-optional)

    測試您的監督原則，以確保其運作視是確保您的合規性策略會議標準的重要部分。

- **步驟 6-（選用）**[設定 Outlook 的檢閱者不想要使用 Office 365 監督儀表板或 （先前稱為 Outlook Web App） 網頁型 Outlook 來檢閱監督的通訊](#step-6---configure-outlook-for-reviewers-optional)

    Outlook 可以設定讓檢閱者存取 Outlook 用戶端內的監督功能讓他們可以評估並加以分類每個項目。

## <a name="step-1---set-up-groups-for-supervision-optional"></a>步驟 1-設定群組的監督 （選用）

 當您建立的監督原則時，您將決定誰會有檢閱其通訊，以及誰可以執行這些檢閱。 在原則中，您將使用電子郵件地址來識別的個人或群組的人員。 為了簡化您的設定，您可以建立的人必須檢閱其通訊群組和的人會檢閱這些通訊群組。 如果您使用的群組，您可能需要數個 — 例如，如果您想要監視的人員，或如果您想要指定群組不是要為指導的兩個不同的群組之間的通訊。

使用下表來協助您在您的組織監督原則中設定群組：

| **原則成員** | **支援的群組** | **不支援的群組** |
|:-----|:-----|:-----|
|監督的使用者 | 通訊群組 <br> Office 365 群組 | 動態通訊群組 |
| Reviewers | 擁有郵件功能的安全性群組  | 通訊群組 <br> 動態通訊群組 |
  
若要管理大型企業組織中監督的使用者，您可能需要非常大型的群組之間監視所有使用者。 您可以使用 PowerShell 來設定全域監督原則中的 [指派] 群組的通訊群組。 這可協助您使用單一原則，以監視千分位的使用者，並保留更新為新員工加入您的組織在監督原則。

1. 具有下列內容建立適用於您的全域監督原則的專用的[通訊群組](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps)。 請確定此通訊群組未用於其他目的或其他 Office 365 服務。

    - **MemberDepartRestriction = 關閉**。 這可確保使用者不能移除自行從通訊群組。
    - **MemberJoinRestriction = 關閉**。 這可確保使用者無法將自己新增至通訊群組。
    - **ModerationEnabled = True**。 這可確保所有郵件傳送給此群組都需要核准及不會群組用來傳達外監督原則設定。

    ```
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```
2. 選取 [未使用[Exchange 的自訂屬性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww)用於追蹤哪些使用者已新增至您組織中監督原則]。

3. 若要將使用者新增至監督原則的週期性排程上執行下列 PowerShell 指令碼：

    ```
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

如需設定群組的詳細資訊，請參閱：
- [建立並管理通訊群組](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [管理啟用郵件功能的安全性群組](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Office 365 群組概觀](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2---make-supervision-available-in-your-organization-required"></a>步驟 2-進行監督 （必要） 組織中可用

若要讓**監督**在規範中心中可用的功能表選項，您必須獲指派的主管檢閱管理員角色。
  
若要這麼做，您可以也將自己新增為主管檢閱角色群組的成員，或您可以建立新的角色群組。
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>將成員新增至 [主管檢閱] 角色群組

1. 登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中系統管理員帳戶認證。

2. 在合規性中心] 中，前往 [**權限**。

3. 選取 [**主管檢閱**] 角色群組，然後按一下 [編輯] 圖示。

4. 在 [**成員**] 區段中，新增您想要管理貴組織的監督的人員。

### <a name="create-a-new-role-group"></a>建立新的角色群組

1. 登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中系統管理員帳戶認證。

2. 在合規性中心] 中，移至**權限**，然後按一下 [新增 (**+**)。

3. 在 [**角色**] 區段中，按一下 [新增 (**+**) 和向下**主管檢閱管理員**捲動。 將此角色新增至角色群組。

4. 在 [**成員**] 區段中，新增您想要管理貴組織的監督的人員。

如需有關角色群組和權限的詳細資訊，請參閱 <<c0>合規性中心的權限。

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>啟用遠端 PowerShell 存取的檢閱者 （如果電子郵件裝載於 Exchange Online）

1. 請遵循[啟用或停用存取 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)中的指引。

## <a name="step-3---create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>步驟 3： 建立自訂機密資訊類型，以及自訂的關鍵字字典 （選用）

若要從現有的自訂機密資訊類型或自訂的關鍵字字典中監督原則] 精靈中挑選，必須先建立這些項目，如有需要。

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>建立自訂的關鍵字字典/lexicon （選用）

使用文字編輯器 （例如記事本），建立新的檔案，其中包含您想要監視的監督原則的關鍵字字詞。 請確定每個字詞是位於個別一行，並以**Unicode/utf-16 (一點 Endian)** 格式儲存檔案。

### <a name="create-custom-sensitive-information-types"></a>建立自訂機密資訊類型

1. 建立新的敏感資訊類型，並在 Office 365 安全性 & 合規性中心中新增您的自訂字典。 瀏覽至 **[分類]** \> **敏感資訊類型]，** 然後依照中**新的敏感資訊類型精靈**的步驟。 在這裡您將會：

    - 定義的名稱和描述的敏感資訊類型
    - 定義接近度信賴等級，主要模式元素
    - 匯入您的自訂字典比對元素的需求
    - 檢閱您的選項，並建立敏感資訊類型

    如需詳細資訊，請參閱[建立自訂機密資訊類型](create-a-custom-sensitive-information-type.md)和[建立關鍵字字典](create-a-keyword-dictionary.md)

    建立自訂字典/lexicon 之後，您可以檢視使用[Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary)指令程式的設定的關鍵字或新增和移除使用[組 DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary)指令程式的字詞。

## <a name="step-4---set-up-a-supervision-policy-required"></a>步驟 4-設定 （必要） 的監督原則
  
1. 登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中系統管理員帳戶認證。

2. 在合規性中心] 中，選取 [**監督**]。
  
3. 選取 [**建立**，然後遵循精靈來設定下列頁面的原則。 使用這個精靈，您會：

    - 授與此原則的名稱和描述。
    - 選擇使用者或群組来監管，包括 [選擇使用者] 或 [您想要排除的群組。
    - 定義監督原則條件。
    - 選擇您想要包含敏感資訊類型。 這是您可以在其中選取預設及自訂機密資訊類型。
    - 定義要檢閱的通訊的百分比。
    - 選擇 [原則的檢閱者]。 檢閱者可以是個別使用者或[擁有郵件功能的安全性群組](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。
    - 檢閱您的原則選項，並建立原則。

## <a name="step-5---test-your-supervision-policy-optional"></a>步驟 5-測試 （選擇性） 您監督原則

建立監督原則之後，它是不錯的選項進行測試以確定您定義的條件都要正確地強制執行該原則所。 如果您的監督原則包含敏感資訊類型，您也可能會想要[測試您的資料遺失防護 (DLP) 原則](create-test-tune-dlp-policy.md)。 請遵循下列步驟來測試您的監督原則：

1. 開啟電子郵件用戶端或 Microsoft Teams 以登入您想要測試該的原則所定義的監督使用者。
2. 傳送電子郵件或符合您已定義的監督原則中之準則的 Microsoft Teams 聊天室。 這可以是關鍵字附件大小、 網域、 等等。請確定您判斷您在原則中的現有條件化設定為太嚴格或太廣義。

    > [!Note]
    > 受到定義原則的電子郵件中處理幾近即時和可以用來測試後的原則設定。 Microsoft Teams 中的聊天室 」 可能需要最多 24 小時才完全處理程序中的原則。 

3. 登入您的 Office 365 租用戶為監督原則中指定檢閱者。 瀏覽至**監督** > *您的自訂原則* > **開啟**檢視該原則的報告。

## <a name="step-6---configure-outlook-for-reviewers-optional"></a>步驟 6-設定 Outlook 的檢閱者 （選用）

想要使用 Outlook，而不是使用 Office 365 中的監督儀表板，以檢閱通訊的檢閱者必須設定他們的 Outlook 用戶端。

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>步驟 1： 複製監督信箱的地址

若要設定的 Outlook 桌面檢閱或 outlook 網頁版，您需要的地址監督信箱監督原則安裝過程所建立。
  
> [!NOTE]
> 如果別人建立原則，您需要取得這個地址，才能安裝增益集。

 **若要尋找的監督信箱地址**
  
1. 登入[合規性中心](https://compliance.microsoft.com)使用您組織中系統管理員帳戶認證。

2. 移至**監督**。

3. 按一下會收集您想要檢閱的通訊的監督原則。

4. 在 [原則的詳細資訊彈出式視窗中，[**監督信箱**，複製地址。<br/>![['監督信箱'] 區段中的監督原則的詳細資料彈出式視窗顯示反白顯示的監督信箱地址](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-access"></a>步驟 2： 設定 Outlook 存取的監督信箱

下一步]，檢閱者將必須重新執行幾位 Exchange Online PowerShell 命令，讓他們可以將 Outlook 連線至監督的信箱。
  
1. 連線至 Exchange Online PowerShell。 [該怎麼做？](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. 執行下列命令，其中*SupervisoryReview{GUID}@domain.onmicrosoft.com*是您在上述步驟 1 中複製的地址，且*使用者*的檢閱者會連線至步驟 3 中的監督信箱的名稱。

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. 等候至少一個小時再移至步驟 3 下方。

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>步驟 3： 建立的 Outlook 設定檔，以連線至監督信箱

最後一個步驟中，檢閱者將會需要建立的 Outlook 設定檔，以連線至監督信箱。

> [!NOTE]
> 若要建立新的 Outlook 設定檔，您將使用在 Windows [控制台] 中的 「 信箱 」 設定。 若要取得這些設定您所採取的路徑可能需取決於您使用的 Windows 作業系統 （Windows 7、 Windows 8 或 Windows 10），以及安裝的 Outlook 版本。
  
1. 開啟 [控制台] 中，並在視窗頂端的 [**搜尋**] 方塊中，輸入**郵件**。<br/>(不確定如何取得 Control Panel 嗎？ 請參閱[所在控制台？](https://support.microsoft.com/help/13764/windows-where-is-control-panel))
  
2. 開啟 [**郵件**應用程式]。

3. 在 [**郵件設定的 Outlook**，按一下 [**顯示設定檔**]。<br/>!['郵件安裝程式-Outlook' 與' 顯示設定檔] 按鈕以反白顯示的對話方塊](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. 在 [**郵件**] 按一下 [**新增**]。 然後，在**新的設定檔**，輸入監督信箱 （例如**監督**） 的名稱。<br/>![在 [設定檔名稱] 方塊中顯示的名稱 '監督' ['新設定檔'] 對話方塊](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. 在 [**連線至 Office 365 的 Outlook**中，按一下 [**連線到不同的帳戶。**<br/>![具有反白顯示的 [連線到不同的帳戶] 連結的 ' 連線到 Office 365 的 Outlook' 訊息](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. 在 [**自動帳戶設定**] 中，選擇 [**手動安裝程式或其他伺服器類型**，，然後按 [**下一步**。

7. 在 [**選擇您的帳戶類型**] 中，選擇 [ **Office 365**]。 然後，在 [**電子郵件地址**] 方塊中，輸入您先前複製的監督信箱地址。<br/>![顯示 '電子郵件地址] 方塊中反白顯示在 Outlook 中的 [新增帳戶] 對話方塊的' 選擇您的帳戶類型] 頁面。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. 出現提示時，輸入您的 Office 365 認證。

9. 如果成功，您會看到**監督-\<原則名稱\>** 資料夾列在 Outlook 中的 [資料夾清單] 檢視中。

## <a name="powershell-reference"></a>PowerShell 參考

如有需要您可以建立及管理監督原則使用下列 PowerShell cmdlet:

- [新 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [取得 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [Set-supervisoryreviewpolicyv2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [Remove-supervisoryreviewpolicyv2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [新 SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [Set-supervisoryreviewrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [取得 SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [取得 SupervisoryReviewOverallProgressReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [取得 SupervisoryReviewTopCasesReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)