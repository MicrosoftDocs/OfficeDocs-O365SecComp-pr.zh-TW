---
title: 在 Office 365 安全與規範中心搜尋稽核記錄
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: '使用 Office 365 安全性 & 合規性中心來搜尋整合的稽核記錄] 來檢視您的 Office 365 組織中的使用者和系統管理員活動。 '
ms.openlocfilehash: 8cb8650315c19714960aba7551902780e38a554b
ms.sourcegitcommit: 54a2cbe5d13f448e0c28655bdf88deb9e5434cac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/27/2019
ms.locfileid: "30935348"
---
# <a name="search-the-audit-log-in-the-office-365-security--compliance-center"></a>在 Office 365 安全性 & 規範中心搜尋稽核記錄

## <a name="introduction"></a>簡介

要尋找是否使用者檢視特定的文件，或清除其信箱中的項目？ 如果這樣，您可以使用 Office 365 安全性&amp;若要檢視 Office 365 組織中的使用者和系統管理員活動整合的稽核記錄中搜尋的合規性中心。 為什麼使用整合的稽核記錄？ 因為您可以搜尋下列類型的 Office 365 中的使用者和系統管理員活動：
  
- 在 SharePoint Online 和商務用 OneDrive 中的使用者活動
    
- Exchange Online 中的使用者活動 （Exchange 信箱稽核記錄）
    
    > [!IMPORTANT]
    > 信箱稽核記錄必須開啟每個使用者信箱將會記錄在 Exchange Online 中的使用者活動之前。 如需詳細資訊，請參閱 <<c0>啟用 Office 365 中的稽核的信箱。
  
- 在 SharePoint Online 中的系統管理員活動
    
- 在 Azure Active Directory （Office 365 的目錄服務） 的系統管理員活動
    
- Exchange Online 中的系統管理員活動 （Exchange 系統管理員稽核記錄）
    
- 在 Sway 中的使用者和系統管理員活動
    
- 在 Office 365 安全性 & 合規性中心中的 eDiscovery 活動
    
- Power BI 中的使用者和系統管理員活動
    
- Microsoft Teams 中的使用者和系統管理員活動

- 在 Dynamics 365 中的使用者和系統管理員活動
    
- Yammer 中的使用者和系統管理員活動
 
- Microsoft Flow 中的使用者和系統管理員活動
    
- Microsoft Stream 中的使用者和系統管理員活動

- 在 Microsoft 工作場所分析中的分析師和系統管理員活動

- Microsoft PowerApps 中的使用者和系統管理員活動
    
   
## <a name="before-you-begin"></a>開始之前

請務必先閱讀下列項目之前開始搜尋 Office 365 稽核記錄。
  
- 您 （或另一個系統管理員） 必須先開啟稽核記錄，才能開始搜尋 Office 365 稽核記錄檔。 若要將它開啟，只是按一下 [**開始錄製使用者和系統管理員活動**安全性**稽核記錄搜尋**] 頁面上&amp;合規性中心。 （如果您沒有看到此連結，稽核已開啟為您的組織。）您開啟之後，會顯示訊息，指出準備稽核記錄檔以及您可以在幾個小時後準備已完成執行搜尋。 您只需要執行這項操作一次。 
    
    > [!NOTE]
    > 我們正在開啟依預設稽核。 在那之前，您可以將其開啟為先前所述。 
  
- 您必須獲指派 「 僅檢視稽核記錄檔] 或 [稽核記錄檔角色在 Exchange Online 來搜尋 Office 365 稽核記錄。 根據預設，這些角色被指派給在 Exchange 系統管理中心中的**權限**] 頁面上相符性管理] 和 [組織管理角色群組。 若要讓使用者能夠搜尋 Office 365 稽核記錄的最低權限，您可以自訂角色群組 Exchange Online 中建立、 新增 「 僅檢視稽核記錄檔] 或 [稽核記錄 」 角色，並再將使用者新增為新的角色群組的成員。 如需詳細資訊，請參閱[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688)。
    
    > [!IMPORTANT]
    > 如果將使用者指派安全性**權限**] 頁面上的 「 僅檢視稽核記錄 」 或 「 稽核記錄檔角色&amp;合規性中心，他們將無法搜尋的 Office 365 稽核記錄檔。 您必須指派 Exchange Online 中的權限。 這是因為基礎指令程式用來搜尋稽核記錄是 Exchange Online cmdlet。 
  
- 由使用者或系統管理員執行稽核的活動時，會產生稽核記錄，並且儲存在貴組織的 Office 365 稽核記錄檔中。 稽核記錄會保留 （而且可搜尋稽核記錄中） 的時間長度，取決於您的 Office 365 訂閱，並特別指定給特定使用者的授權類型。

     - **Office 365 E3** -稽核記錄會保留 90 天。 這表示您可以搜尋過去 90 天內執行活動的稽核記錄檔。

     - **Office 365 E5** -稽核記錄保留為 365 天 （一年）。 這表示您可以搜尋在過去一年內所執行的活動的稽核記錄檔。 稽核記錄保留一年的也是可用的使用者，會指派 E3/Exchange Online Plan 1 授權，而且具有 Office 365 進階合規性的附加元件授權。

        > [!NOTE]
        > 稽核記錄的一年保留期間的 E5 組織 （或 E3 有進階合規性的附加元件授權） 是目前無法使用僅做為私人預覽計畫的一部分。 若要在此預覽計畫中註冊，請與[Microsoft 支援服務](https://docs.microsoft.com/en-us/office365/admin/contact-support-for-business-products?redirectSourcePath=%252fen-us%252farticle%252fcontact-support-for-business-products-admin-help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online)歸檔，並包括下列項目為您需要協助的描述: 「 長期 Office 365 稽核記錄檔私人預覽 」。

- 如果您想要關閉 Office 365 中為您的組織的稽核記錄搜尋，您可以在遠端 PowerShell 連線至 Exchange Online 組織中執行下列命令：
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    若要一次開啟稽核搜尋，您可以在 Exchange Online PowerShell 中執行下列命令：
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

    如需詳細資訊，請參閱[關閉 Office 365 中的稽核記錄搜尋](turn-audit-log-search-on-or-off.md)。
    
- 如先前所述，基礎指令程式用來搜尋稽核記錄會是 Exchange Online 指令程式，也就是**Search-unifiedauditlog**。 這表示您可以使用此指令程式來搜尋 Office 365 稽核記錄，而不是使用 [**稽核記錄搜尋**] 頁面上，安全性&amp;合規性中心。 您必須在遠端 PowerShell 連線至 Exchange Online 組織中執行此 cmdlet。 如需詳細資訊，請參閱 < <b0>Search-unifiedauditlog</b0>。
    
- 如果您想要以程式設計方式從 Office 365 稽核記錄檔下載資料，我們建議您使用 Office 365 管理活動 API，而不是使用 PowerShell 指令碼。 Office 365 管理活動 API 為 REST web 服務可供您開發作業、 安全性和規範監視解決方案的組織。 如需詳細資訊，請參閱[Office 365 管理活動 API 參考資料](https://go.microsoft.com/fwlink/?linkid=852309)。
    
- 它可以最多需要 30 分鐘或向上事件之後的 24 小時就會發生的相對應的稽核記錄項目顯示在搜尋結果中。 下表顯示 Office 365 中的不同服務所花費的時間。
    
    |**Office 365 服務**|**30 分鐘**|**24 小時**|
    |:-----|:-----|:-----|
    |進階的威脅防護和威脅情報  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| |
    |Azure Active Directory （使用者登入事件）  <br/> ||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
    |Azure Active Directory （系統事件）  <br/> ||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) |
    |資料遺失防護  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)       <br/>| |
    |Dynamics 365 CRM <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |eDiscovery  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Exchange Online  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Microsoft Flow  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft 表單  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Project  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Stream  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Teams  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Power BI  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |安全性&amp;合規性中心  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |SharePoint Online 和商務用 OneDrive  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Sway  <br/> ||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
    |工作場所分析<br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> || 
    |Yammer  <br/> ||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
   
- Azure Active Directory (Azure AD) 是 Office 365 的目錄服務。 整合的稽核記錄檔包含使用者、 群組、 應用程式、 網域及 Office 365 系統管理中心中，或在 Azure 中執行的目錄活動管理入口網站。 Azure AD 事件的完整清單，請參閱[Azure Active Directory 稽核報告事件](https://go.microsoft.com/fwlink/p/?LinkID=616549)。
    
- Exchange Online 的稽核記錄檔包含兩種類型的事件： 在 Exchange 系統管理事件 （系統管理員所採取的動作） 與信箱事件 （在信箱上的使用者所採取的動作）。 請注意預設未啟用信箱稽核。 它必須啟用每個使用者信箱，才能信箱事件可以在 Office 365 稽核記錄搜尋。 如需信箱稽核和信箱稽核記錄的動作的詳細資訊，請參閱 <<c0>啟用 Office 365 中的稽核的信箱。
    
- 根據預設，不啟用 Power bi 的稽核記錄。 若要搜尋的 Office 365 稽核記錄中的 Power BI 活動，您必須啟用 Power BI 系統管理入口網站中的稽核。 如需相關指示，請參閱 < <b0>Power BI 系統管理入口網站</b0>的 「 稽核記錄 」 一節。
    
    
## <a name="search-the-audit-log"></a>搜尋稽核記錄

以下是在 Office 365 中搜尋稽核記錄檔的程序。
  
[步驟 1： 執行稽核記錄搜尋](#step-1-run-an-audit-log-search)
  
[步驟 2： 檢視搜尋結果](#step-2-view-the-search-results)

[步驟 3： 篩選搜尋結果](#step-3-filter-the-search-results)

[步驟 4： 將搜尋結果匯出至檔案](#step-4-export-the-search-results-to-a-file)
  
### <a name="step-1-run-an-audit-log-search"></a>步驟 1： 執行稽核記錄搜尋

1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
    > [!TIP]
    > 使用私人的瀏覽工作階段 （不在一般工作階段） 來存取 Office 365 安全性&amp;合規性中心，因為這會防止您目前登入與所用的認證。 若要開啟 [InPrivate 瀏覽工作階段在 Internet Explorer 或 Microsoft Edge 中，只需按 CTRL + SHIFT + P。 若要在 Google Chrome （稱為 incognito 視窗） 中開啟私人瀏覽工作階段，請按 CTRL + SHIFT + N。 
  
2. 使用公司或學校帳戶登入 Office 365。
    
3. 安全性的左窗格中&amp;合規性中心，按一下 [**搜尋&amp;調查**，然後按一下 [**稽核記錄搜尋**。
    
    會顯示 [**稽核記錄搜尋**] 頁面。 
    
    ![設定準則，然後按一下 [搜尋] 以執行報告](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
    > [!NOTE]
    > 您必須先開啟稽核記錄，才能執行稽核記錄搜尋。 如果顯示 [**開始錄製使用者和系統管理員活動**] 連結，請按一下它便開啟稽核功能。 如果您沒有看到此連結，稽核已開啟為您的組織。 
  
4. 設定下列搜尋準則：
    
    a. **活動**按一下 [下拉式清單，以顯示您可以搜尋的活動。 使用者和系統管理員活動會組織的相關活動的群組。 您可以選取特定活動，或您可以按一下 [活動群組名稱來選取] 群組中的所有活動。 您也可以按一下選取的活動，以清除選取範圍。 執行搜尋之後，會顯示僅針對所選活動的稽核記錄項目。 選取 [**顯示所有活動的結果**會顯示所選取的使用者或使用者群組執行的所有活動的結果。 
    
    超過 100 個使用者和系統管理員活動登入 Office 365 稽核記錄檔。 按一下 [**稽核活動**] 索引標籤，在主題的本文，查看每個不同的 Office 365 服務中每個活動的描述。 
    
    b. 預設會選取**開始日期**和**結束日期**過去 7 天。 選取要顯示在該期間內發生的事件的日期和時間範圍。 日期和時間會以 Coordinated Universal Time (UTC) 格式呈現。 您可以指定的最大的日期範圍為 90 天。 如果選取的日期範圍大於 90 天內，會顯示錯誤。 
    
    > [!TIP]
    > 如果您正在使用的 90 天的最大的日期範圍，選取目前時間的**開始日期**。 否則，您會收到錯誤訊息說明的開始日期是早於結束日期。 如果您已開啟稽核在過去 90 天內，最大的日期範圍無法啟動之前已開啟稽核的日期。 
  
    c. **使用者**在此方塊中按一下，然後選取 [顯示搜尋結果的一或多個使用者。 選取您在此方塊中選取的使用者所執行的活動的稽核記錄項目會顯示在結果清單中。 保留此方塊留白，以傳回組織中的所有使用者 （與服務帳戶） 的項目。 
    
    d. **檔案、 資料夾或網站**輸入部分或全部要搜尋的檔案的資料夾，其中包含指定的關鍵字的相關活動的檔案或資料夾名稱。 您也可以指定的檔案或資料夾的 URL。 如果您使用的 URL，務必類型的完整的 URL 路徑，或如果您只需要輸入 URL，部分不會包含任何特殊字元或空格。 
    
    保留此方塊留白，以傳回組織中的所有檔案及資料夾的項目。
    
    > [!TIP]
    > 如果您要尋找與**網站**相關的所有活動，新增萬用字元符號 (\*) 之後的 URL，可傳回該網站; 的所有項目例如， **"https://contoso-my.sharepoint.com/personal/* 」**。
    
5. 按一下 [**搜尋**] 以執行使用您的搜尋準則的 [搜尋]。 
    
    搜尋結果會載入，且在幾分鐘之後被顯示在 [**結果**] 下。 搜尋完成時，會顯示找到的結果數目。 請注意，將會以遞增 150 事件; 在**結果**窗格中顯示最大值為 5000 個事件如果超過 5000 筆事件符合搜尋準則，會顯示最近的 5000 個事件。 
    
    ![搜尋完成之後，會顯示的結果數](media/986216f1-ca2f-4747-9480-e232b5bf094c.png)
  
  
#### <a name="tips-for-searching-the-audit-log"></a>搜尋稽核記錄檔的秘訣

- 您可以選取特定活動的活動名稱上按一下來進行搜尋。 或者您可以在群組名稱上按一下 [搜尋群組 （例如**檔案和資料夾的活動**） 中的所有活動。 如果選取的活動，則您可以按一下它，取消選取項目。 您也可以使用 [搜尋] 方塊中顯示含有您所輸入的關鍵字的活動。
    
    ![按一下以選取所有活動的活動群組名稱](media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)
  
- 您必須以顯示從 Exchange 系統管理員稽核記錄的事件**活動**清單中選取 [**顯示所有活動的結果**。 從這個稽核記錄的事件結果中的 [**活動**] 欄中顯示的指令程式名稱 （例如， **Set-mailbox** ）。 如需詳細資訊，本主題中的 [**稽核活動**] 索引標籤，然後按一下 [ **Exchange 系統管理員活動**。
    
    同樣地，有某些稽核活動在**活動**清單中沒有對應的項目。 如果您知道這些活動的作業的名稱，您可以搜尋所有活動，然後在 [**活動**] 欄中的方塊中輸入作業的名稱來篩選結果。 請參閱[步驟 3： 篩選搜尋結果](#step-3-filter-the-search-results)如需有關篩選結果。 
    
- 按一下 [若要清除目前的搜尋準則的 [**清除**]。 日期範圍會傳回為預設的過去 7 天。 您也可以按一下 [取消選取的所有活動 [**清除 [全部]，以顯示結果的所有活動**。 
    
- 如果找不到 5000 筆結果，您可能可以假設有超過 5000 筆符合搜尋準則的事件。 您可以精簡搜尋準則，並重新執行搜尋以返回較少的結果，或是您可以藉由選取 [**匯出結果**匯出所有的搜尋結果\>**下載所有結果**。

  
### <a name="step-2-view-the-search-results"></a>步驟 2： 檢視搜尋結果

稽核記錄搜尋結果] 底下會顯示**結果**[**稽核記錄搜尋**] 頁面。 如先前所述的遞增量 150 事件會顯示最大值為 5000 個 （最新） 的事件。 若要顯示更多事件您可以使用捲軸列在 [**結果**] 窗格中，或您可以按**Shift + End**以顯示下一步] 150 事件。 
  
結果包含下列搜尋傳回的每個事件的相關資訊。
  
- **日期：** 日期和時間 （UTC 格式） 事件發生時。 
    
- **IP 位址：** 活動已記錄時使用的裝置 IP 位址。 IP 位址會顯示在 IPv4 或 IPv6 地址格式。 
    
- **使用者：** 使用者 （或服務帳戶） 誰執行觸發事件的動作。 
    
- **活動：** 執行活動的使用者。 此值會對應至您在 [**活動**] 下拉式清單中選取的活動。 從 Exchange 系統管理員稽核記錄的事件，此欄中的值會是 Exchange 指令程式。 
    
- **項目：** 物件已建立或修改由於相對應的活動。 例如，檢視或修改的檔案或已更新的使用者帳戶。 並非所有活動中此欄都有值。 
    
- **詳細資料：** 關於活動的額外詳細資料。 同樣地，並非所有活動會都有一個值。 
    
> [!TIP]
> 按一下欄標題來排序結果的**結果**下。 您可以排序結果從 A 到 Z 或 Z A 按一下 「**日期**」 標題來排序結果的最舊到最新或最新到最舊。 
  
#### <a name="view-the-details-for-a-specific-event"></a>檢視特定事件的詳細資料

您可以檢視事件有關的更多詳細資料]，即可在搜尋結果清單中的事件記錄。 **詳細資料**] 頁面會顯示包含從事件記錄的詳細的屬性。 會顯示的內容取決於 Office 365 服務發生事件。 若要顯示這些詳細資料，請按一下 [**更多的資訊**。 如需說明，請參閱[在 Office 365 的詳細的內容稽核記錄](detailed-properties-in-the-office-365-audit-log.md)。
  
![按一下 [檢視稽核記錄的事件記錄的詳細的內容的詳細資訊](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

  
### <a name="step-3-filter-the-search-results"></a>步驟 3： 篩選搜尋結果

除了排序，您也可以篩選稽核記錄搜尋的結果。 這是個不錯的功能，可協助您快速篩選特定使用者或活動的結果。 您可以一開始建立整體搜尋，並快速篩選結果，以查看特定的事件。 然後您可以縮小搜尋準則，並重新執行搜尋以返回較小，更簡潔的結果集。
  
若要篩選的結果：
  
1. 執行稽核記錄搜尋。
    
2. 結果會顯示，按一下 [**篩選結果**。
    
    關鍵字方塊會顯示在每個資料行標題之下。
    
3. 按一下其中一個方塊下欄標題，然後輸入單字或片語，視您正在篩選的資料行。 結果會以動態方式重新調整以顯示符合篩選的事件。
    
    ![輸入字詞的篩選，以顯示符合篩選的事件](media/542dc323-a997-402c-934b-cc5e218e50bc.png)
  
4. 若要清除篩選，請按一下 [篩選] 方塊中的**X**或只要按一下 [**隱藏篩選**。
    
> [!TIP]
> 若要顯示來自 Exchange 系統管理員稽核記錄的事件，請輸入**-**（虛線） 在 [**活動**篩選] 方塊中。 這會顯示指令程式名稱，會顯示在 Exchange 系統事件的 [**活動**] 欄位。 然後您可以排序依字母順序排列的指令程式名稱。 

### <a name="step-4-export-the-search-results-to-a-file"></a>步驟 4： 將搜尋結果匯出至檔案

您可以將稽核記錄搜尋結果匯出至本機電腦上的逗點分隔的值 (CSV) 檔案。 您可以在 Microsoft Excel 中開啟此檔案，並使用多個資料行到功能，例如搜尋，排序、 篩選及分割的單一資料行 （包含多重值的儲存格）。
  
1. 執行稽核記錄搜尋]，然後再修訂的搜尋準則，直到您有想要的結果。
    
2. 按一下 [**匯出結果**，選取下列選項之一： 
    
  - **儲存載入結果**選擇此選項可匯出] 底下**的結果**會顯示的項目 * * 稽核記錄搜尋 * *] 頁面。 下載的 CSV 檔案包含 （日期、 使用者、 活動、 項目，以及詳細資料） 頁面上顯示的相同資料行 （和資料）。 （名為**多個**） 額外一欄包含在 CSV 檔案包含稽核記錄項目從的詳細資訊。 因為您要匯出相同的結果載入 （與檢視） 的最大值為 5000 的項目會匯出在 [**稽核記錄搜尋**] 頁面。 
    
  - **下載所有結果**選擇此選項以從符合搜尋準則的 Office 365 稽核記錄檔匯出所有的項目。 一組大型的搜尋結果，選擇此選項以從除了 5000 筆結果，可以顯示在 [**稽核記錄搜尋**] 頁面上的稽核記錄檔下載所有項目。 此選項將稽核記錄檔從下載的未經處理資料至 CSV 檔案，並包含名為**AuditData**] 欄中的稽核記錄項目中的其他資訊。 可能需要較長的時間下載檔案，如果您選擇此匯出選項，因為可能遠大於一如果您選擇其他選項下載的檔案。
    
    > [!IMPORTANT]
    > 您可以下載至 CSV 檔案的最大值為 50000 的項目從單一的稽核記錄搜尋。 如果 50000 的項目會下載到 CSV 檔案，您可能可以假設有超過 50000 個符合搜尋準則的事件。 若要匯出超過此限制，請嘗試使用日期範圍，以減少稽核記錄項目的數目。 您可能使用較小的日期範圍，若要匯出超過 50000 個項目執行多個搜尋。 
  
3. 選取 [匯出] 選項後，會提示您開啟 CSV 檔案，將它儲存到 [下載項目] 資料夾中，或將其儲存至特定資料夾視窗的底部會顯示訊息。

  
#### <a name="more-information-about-exporting-audit-log-search-results"></a>匯出稽核記錄搜尋結果的詳細資訊

- **下載所有結果**] 選項會下載到 CSV 檔案從 Office 365 稽核記錄檔的未經處理資料。 此檔案包含不同的資料行名稱 （CreationDate、 UserIds、 作業、 AuditData） 比如果您選取 [**儲存載入結果**] 選項已下載的檔案。 兩個不同的 CSV 檔案的相同活動中的值也可能會不同。 例如，在 csv 檔案中的 [**動作**] 欄中的活動檔案，且可能會有不同的值會顯示在 [**稽核記錄搜尋**] 頁面上; 中的 [**活動**] 欄中的 「 好記易懂 「 版本例如，MailboxLogin 相對於使用者登入至信箱。
    
- 如果您要下載所有結果，CSV 檔案中包含名為**AuditData**，其中包含每個事件相關的其他資訊的資料行。 如先前所述，此欄會包含多個屬性的稽核記錄檔記錄的多重值屬性。 此多重值屬性中的**屬性： 值**組的每個都以逗號分隔。 您可以使用 Excel 中的 Power Query 此資料行分割成多個資料行，使每個屬性將有它自己的資料行。 這可讓您排序及篩選一或多個這些屬性。 若要了解如何執行這項操作，請參閱[分割資料行的文字 (Power Query)](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662)的 「 分割資料行分隔符號 」 一節。
    
    分割**AuditData**欄之後，您可以篩選以顯示特定類型的活動的詳細的內容的 [**作業**] 欄。 
    
- 沒有 3,060 字元會顯示在稽核記錄的**AuditData**欄位的資料的長度限制。 如果超出 3,060 字元限制，則此欄位中的資料會捨去成整數。 
    
- 當您下載所有結果包含的事件來自不同 Office 365 服務的搜尋查詢時，CSV 檔案中的 [ **AuditData** ] 欄會包含不同根據服務巨集指令執行中的屬性。 例如，從 Exchange 和 Azure AD 的稽核記錄項目包含名為**ResultStatus**表示動作是否成功與否屬性。 此屬性不包含在 SharePoint 中的事件。 同樣地，SharePoint 事件有屬性，識別的網站 URL 的檔案和資料夾相關的活動。 若要降低此行為，請考慮使用不同的搜尋從單一服務匯出活動的結果。 
    
    當您下載所有的結果，以及服務每一個 CSV 檔案中的 [ **AuditData** ] 欄中所列的屬性描述一套用於，請參閱[在 Office 365 的詳細的內容稽核記錄](detailed-properties-in-the-office-365-audit-log.md)。

## <a name="audited-activities"></a>稽核的活動

本節中的表格說明稽核 Office 365 中的活動。 您可以藉由中安全性 & 規範中心搜尋稽核記錄搜尋這些事件。
  
這些表格群組相關的活動或從特定的 Office 365 服務的活動。 表格包含 [**活動**] 下拉式清單中顯示的易記名稱及對應的作業，當您匯出搜尋結果出現在稽核記錄的詳細資訊和 CSV 檔案的名稱。 如需詳細資訊的說明，請參閱[在 Office 365 的詳細的內容稽核記錄](detailed-properties-in-the-office-365-audit-log.md)。
  
按一下下列其中一個下列連結，即可移至指定的表格。
  
||||
|:-----|:-----|:-----|
|[檔案和] 頁面上的活動](#file-and-page-activities)<br/> |[資料夾活動](#folder-activities)<br/> |[共用和存取要求活動](#sharing-and-access-request-activities)<br/> |
|[同步處理活動](#synchronization-activities)<br/> |[網站管理活動](#site-administration-activities)<br/> |[Exchange 信箱活動](#exchange-mailbox-activities)<br/> |
|[Sway 活動](#sway-activities) <br/> |[使用者管理活動](#user-administration-activities) <br/> |[Azure AD 群組管理活動](#azure-ad-group-administration-activities) <br/> 
|[應用程式管理活動](#application-administration-activities) <br/> |[角色管理活動](#role-administration-activities) <br/> |[目錄管理活動](#directory-administration-activities) <br/>| 
|[電子文件探索活動](#ediscovery-activities) <br/> |[Power BI 活動](#power-bi-activities) <br/> |[Microsoft 工作場所分析](#microsoft-workplace-analytics-activities)<br/>|
|[Microsoft Teams 活動](#microsoft-teams-activities) <br/> |[Yammer 活動](#yammer-activities) <br/> |[Microsoft Flow 活動](#microsoft-flow-activities) <br/>|
|[Microsoft PowerApps 活動](#microsoft-powerapps)<br/>|[Microsoft 資料流活動](#microsoft-stream-activities) <br/>|[Exchange 系統管理員活動](#exchange-admin-audit-log)<br/>|
||||
   
  
### <a name="file-and-page-activities"></a>檔案和] 頁面上的活動
  
下表說明 SharePoint Online 和商務用 OneDrive 中的檔案和頁面活動。
  
|**易記名稱**|**Operation**|**描述**|
|:-----|:-----|:-----|
|存取的檔案  <br/> |FileAccessed  <br/> |使用者或系統帳戶存取檔案。  <br/> |
|(無)  <br/> |FileAccessedExtended  <br/> |這與 「 存取檔案 」 (FileAccessed) 活動。 相同的人持續存取檔案的一段時間 （最多 3 小時） 時，會記錄 FileAccessedExtended 事件。 記錄 FileAccessedExtended 事件的目的是要減少 FileAccessed 事件持續存取檔案時所記錄的數目。 這可協助降低的多個 FileAccessed 記錄功能基本上是相同的雜訊使用者活動，並可讓您專注於初始 （和更重要） FileAccessed 事件。  <br/> |
|存回檔案  <br/> |FileCheckedIn  <br/> |使用者存回他們從文件庫取出的文件。  <br/> |
|取出檔案  <br/> |FileCheckedOut  <br/> |使用者取出的文件庫中的文件。 使用者可以簽出，並與他們共用的文件進行變更。  <br/> |
|複製的檔案  <br/> |FileCopied  <br/> |使用者會複製網站中的文件。 複製的檔案可以儲存到網站上的另一個資料夾。  <br/> |
|已刪除的檔案  <br/> |FileDeleted  <br/> |使用者從網站刪除文件。  <br/> |
|資源回收筒中已刪除的檔案  <br/> |FileDeletedFirstStageRecycleBin  <br/> |使用者從網站的資源回收筒刪除檔案。  <br/> |
|第二階段資源回收筒中已刪除的檔案  <br/> |FileDeletedSecondStageRecycleBin  <br/> |使用者從網站的第二階段資源回收筒刪除檔案。  <br/> |
|在檔案中偵測到惡意程式碼  <br/> |FileMalwareDetected  <br/> |SharePoint 防毒引擎偵測惡意程式碼檔案中。  <br/> |
|已捨棄的檔案簽出  <br/> |FileCheckOutDiscarded  <br/> |使用者捨棄 (或復原) 取出的檔案。這表示對取出的文件所做的任何變更會被捨棄，不儲存到文件庫中的文件版本。  <br/> |
|下載的檔案  <br/> |FileDownloaded  <br/> |使用者從網站下載的文件。  <br/> |
|修改的檔案  <br/> |FileModified  <br/> |使用者或系統帳戶修改的內容或位在網站上的文件的屬性。  <br/> |
|(無)  <br/> |FileModifiedExtended  <br/> |這與 「 最後修改檔案 」 (FileModified) 活動。 同一人士不斷修改檔案的一段時間 （最多 3 小時） 時，會記錄 FileModifiedExtended 事件。 記錄 FileModifiedExtended 事件的目的是減少不斷修改檔案時，會記錄的 FileModified 事件的次數。 這可協助降低的多個 FileModified 記錄功能基本上是相同的雜訊使用者活動，並可讓您專注於初始 （和更重要） FileModified 事件。  <br/> |
|移動的檔案  <br/> |FileMoved  <br/> |使用者從其目前的位置，網站上的新位置，移動文件。  <br/> |
|Recycled 檔案的所有次要版本  <br/> |FileVersionsAllMinorsRecycled  <br/> |使用者從檔案的版本歷程記錄刪除所有的次要版本。 已刪除的版本會移至網站資源回收筒。  <br/> |
|Recycled 檔案的所有版本  <br/> |FileVersionsAllRecycled  <br/> |使用者從檔案的版本歷程記錄刪除所有版本。 已刪除的版本會移至網站資源回收筒。  <br/> |
|回收的檔案版本  <br/> |FileVersionRecycled  <br/> |使用者從檔案的版本歷程記錄刪除版本。 已刪除的版本會移至網站資源回收筒。  <br/> |
|重新命名的檔案  <br/> |FileRenamed  <br/> |使用者重新命名的網站上的文件。  <br/> |
|還原的檔案  <br/> |FileRestored  <br/> |使用者從網站的資源回收筒還原文件。  <br/> |
|上傳的檔案  <br/> |FileUploaded  <br/> |使用者將文件上傳到網站上的資料夾。  <br/> |
|檢視的頁面  <br/> |PageViewed  <br/> |使用者檢視網站頁面。 這不包含使用網頁瀏覽器檢視中的文件庫檔案。  <br/> |
|(無)  <br/> |PageViewedExtended  <br/> |這與 「 檢視畫面 」 相關 (PageViewed) 活動。 同一人士不斷檢視網頁的一段時間 （最多 3 小時） 時，會記錄 PageViewedExtended 事件。 記錄 PageViewedExtended 事件的目的是減少 PageViewed 事件不斷檢視頁面時所記錄的數目。 這可協助降低的多個 PageViewed 記錄功能基本上是相同的雜訊使用者活動，並可讓您專注於初始 （和更重要） PageViewed 事件。  <br/> |
||||
  
### <a name="folder-activities"></a>資料夾活動
  
下表說明 SharePoint Online 和商務用 OneDrive 中的資料夾活動。
  
|**易記名稱**|**Operation**|**描述**|
|:-----|:-----|:-----|
|複製的資料夾  <br/> |FolderCopied  <br/> |使用者會從網站中資料夾複製到 SharePoint 或商務用 OneDrive 中的另一個位置。  <br/> |
|建立的資料夾  <br/> |FolderCreated  <br/> |使用者在網站上建立資料夾。  <br/> |
|已刪除的資料夾  <br/> |FolderDeleted  <br/> |使用者從網站刪除資料夾。  <br/> |
|資源回收筒中已刪除的資料夾  <br/> |FolderDeletedFirstStageRecycleBin  <br/> |使用者從網站上的資源回收筒刪除資料夾。  <br/> |
|第二階段資源回收筒中已刪除的資料夾  <br/> |FolderDeletedSecondStageRecycleBin  <br/> |使用者從網站上的第二階段資源回收筒刪除資料夾。  <br/> |
|已修改的資料夾  <br/> |FolderModified  <br/> |使用者可修改在網站上的資料夾。 這包括變更資料夾的中繼資料，例如變更標記和屬性。  <br/> |
|移動的資料夾  <br/> |FolderMoved  <br/> |使用者會在網站上，將資料夾移至不同的位置。  <br/> |
|重新命名的資料夾  <br/> |FolderRenamed  <br/> |使用者重新命名的網站上的資料夾。  <br/> |
|還原的資料夾  <br/> |FolderRestored  <br/> |使用者從網站上的資源回收筒還原已刪除的資料夾。  <br/> |
||||
  
### <a name="sharing-and-access-request-activities"></a>共用和存取要求活動
  
下表說明 SharePoint Online 和商務用 OneDrive 中的使用者共用及存取要求活動。 共用事件，在 [**結果**] 下的 [**詳細資料**] 欄會識別的使用者或群組共用的項目名稱，以及是否該使用者或群組為成員或組織中的來賓。 如需詳細資訊，請參閱 <<c0>使用 Office 365 稽核記錄檔中的共用稽核。
  
> [!NOTE]
> 使用者可以成為 [*成員*] 或 [*訪客*的使用者物件的 UserType 屬性為基礎。 成員通常員工，而來賓通常是組織外的一目了然。 當使用者可接受的共用邀請 （且已不是您組織的一部分） 時，就會為他們來賓帳戶建立貴組織的目錄中。 一旦來賓使用者帳戶目錄中，可能會直接與他們共用資源，（而不需要邀請）。 
  
|**易記名稱**|**Operation**|**描述**|
|:-----|:-----|:-----|
|接受存取要求  <br/> |AccessRequestAccepted  <br/> |存取網站、 資料夾或文件已接受邀請，並要求使用者授與存取權。  <br/> |
|公認的共用邀請  <br/> |SharingInvitationAccepted  <br/> |使用者 （成員或來賓） 接受的共用邀請，並已授與給資源的存取權。 此事件資訊包含獲邀使用者與用來接受邀請的電子郵件地址 （它們可能會不同）。 這項活動通常伴隨告訴您，如何已授與使用者存取的資源，例如，將使用者新增至具有存取的資源群組的第二個事件。  <br/> |
|網站集合已新增權限等級  <br/> |PermissionLevelAdded  <br/> |權限等級已新增至網站集合。  <br/> |
|使用者新增至安全連結  <br/> |AddedToSecureLink  <br/> |使用者已新增至實體可以使用這個安全的共用連結的清單。  <br/> |
|封鎖的共用邀請  <br/> |SharingInvitationBlocked  <br/> | 因為 [允許] 或 [拒絕外部共用的目標使用者的網域為基礎的外部共用原則封鎖您組織中的使用者所傳送的共用邀請。 在此情況下，共用邀請，所以封鎖郵件：  <br/>  允許的網域清單不包含目標使用者的網域。  <br/>  或  <br/>  目標使用者的網域包含在封鎖網域清單中。  <br/>  如需允許或封鎖的網域為基礎的外部共用的詳細資訊，請參閱 < <b0>SharePoint Online 和商務用 OneDrive 中共用的受限的網域</b0>。  <br/> |
|中斷權限層級繼承  <br/> |PermissionLevelsInheritanceBroken  <br/> |項目已變更，使它不再繼承其父系的權限等級。  <br/> |
|中斷共用繼承  <br/> |SharingInheritanceBroken  <br/> |項目已變更，使它不再繼承其父共用權限。  <br/> |
|建立公司可共用連結  <br/> |CompanyLinkCreated  <br/> |使用者建立資源的全公司的連結。 全公司的連結只可供您組織中的成員。 他們無法使用來賓。  <br/> |
|建立存取要求  <br/> |AccessRequestCreated  <br/> |使用者要求存取他們沒有存取權限的網站、 資料夾或文件。  <br/> |
|建立匿名的連結  <br/> |AnonymousLinkCreated  <br/> |建立資源匿名連結的使用者。 使用此連結的任何人都可以存取資源而不必經過驗證。  <br/> |
|建立安全連結  <br/> |SecureLinkCreated  <br/> |安全的共用連結被建立此項目。  <br/> |
|建立共用邀請  <br/> |SharingInvitationCreated  <br/> |不在貴組織的目錄中的使用者與使用者共用的 SharePoint Online 或商務用 OneDrive 中的資源。  <br/> |
|已刪除的安全連結  <br/> |SecureLinkDeleted  <br/> |已刪除的安全共用連結。  <br/> |
|拒絕存取要求  <br/> |AccessRequestDenied  <br/> |拒絕存取要求網站、 資料夾或文件。  <br/> |
|在 [網站集合上的修改權限等級  <br/> |PermissionLevelModified  <br/> |在網站集合上，已變更權限等級。  <br/> |
|移除公司可共用連結  <br/> |CompanyLinkRemoved  <br/> |使用者中移除資源的全公司的連結。 連結不再可以用來存取資源。  <br/> |
|移除匿名的連結  <br/> |AnonymousLinkRemoved  <br/> |移除資源匿名連結的使用者。 連結不再可以用來存取資源。  <br/> |
|從網站集合中移除權限等級  <br/> |PermissionLevelRemoved  <br/> |從網站集合已移除權限等級。  <br/> |
|還原共用繼承  <br/> |SharingInheritanceReset  <br/> |變更的原因，讓項目會繼承其父代中的共用權限。  <br/> |
|共用的檔案、 資料夾或網站  <br/> |SharingSet  <br/> |使用者 （成員或來賓） 與您的組織目錄中的使用者共用檔案、 資料夾或 SharePoint 或商務用 OneDrive 中的網站。 執行活動的 [**詳細資料**] 欄中的值會識別資源共用的使用者，以及此使用者是否為成員或來賓的名稱。 這項活動通常伴隨著將告訴您如何已授與使用者存取的資源; 第二個事件例如，將使用者新增至群組有權存取資源。  <br/> |
|更新的存取要求  <br/> |AccessRequestUpdated  <br/> |已更新的項目存取要求。  <br/> |
|更新匿名的連結  <br/> |AnonymousLinkUpdated  <br/> |使用者更新資源匿名的連結。 當您匯出搜尋結果時，更新的欄位隨附於 EventData 屬性。  <br/> |
|更新共用邀請  <br/> |SharingInvitationUpdated  <br/> |已更新的外部共用邀請。  <br/> |
|使用匿名的連結  <br/> |AnonymousLinkUsed  <br/> |匿名使用者會使用匿名的連結，以存取資源。 使用者的身分識別可能是未知的但您可以取得其他詳細資料，例如使用者的 IP 位址。  <br/> |
|取消共用的檔案、 資料夾或網站  <br/> |SharingRevoked  <br/> |使用者 （成員或來賓） 取消共用檔案、 資料夾或先前已與另一位使用者共用的網站。  <br/> |
|使用公司可共用連結  <br/> |CompanyLinkUsed  <br/> |使用者使用全公司的連結，以存取資源。  <br/> |
|使用安全連結  <br/> |SecureLinkUsed  <br/> |使用者使用的安全連結。  <br/> |
|使用者新增至安全連結  <br/> |AddedToSecureLink  <br/> |使用者已新增至實體可以使用的安全共用連結的清單。  <br/> |
|移除安全連結的使用者  <br/> |RemovedFromSecureLink  <br/> |使用者已移除的實體可以使用的安全共用連結清單。  <br/> |
|拖共用邀請  <br/> |SharingInvitationRevoked  <br/> |使用者拖到資源的共用邀請。  <br/> |
||||
  
### <a name="synchronization-activities"></a>同步處理活動
  
下表列出 SharePoint Online 和商務用 OneDrive 中的檔案同步處理活動。
  
|**易記名稱**|**Operation**|**描述**|
|:-----|:-----|:-----|
|允許電腦同步處理檔案  <br/> |ManagedSyncClientAllowed  <br/> |使用者成功建立與網站的同步處理關係。 同步處理關係是成功，因為使用者的電腦所新增的網域 （稱為 「*安全的收件者清單*） 可以存取您組織中的文件庫清單到網域的成員。  <br/> 如需此功能的詳細資訊，請參閱 <<c0>使用 Windows PowerShell cmdlet 來啟用的網域已在安全收件者清單中的 OneDrive 同步處理。  <br/> |
|封鎖電腦進行同步處理檔案  <br/> |UnmanagedSyncClientBlocked  <br/> |使用者嘗試建立的網站不是貴組織的網域的成員電腦同步處理關係或是尚未新增至清單中網域的網域的成員 (稱為 「*安全收件者清單)* ，可以存取文件在您的組織中的文件庫。 不允許同步處理關係，以及使用者的電腦會封鎖同步處理、 下載，或上傳的文件庫的檔案。  <br/> 如需此功能的資訊，請參閱 <<c0>使用 Windows PowerShell cmdlet 來啟用的網域已在安全收件者清單中的 OneDrive 同步處理。  <br/> |
|下載至電腦的檔案  <br/> |FileSyncDownloadedFull  <br/> |使用者建立同步處理關係並且成功下載檔案第一次至其電腦從文件庫。  <br/> |
|下載的檔案，變更至電腦  <br/> |FileSyncDownloadedPartial  <br/> |使用者成功的任何變更檔案從下載的文件庫。 這項活動會指出文件庫中的檔案所做的任何變更已下載至使用者的電腦。 因為 （如**下載至電腦的檔案**活動所指示） 先前的文件庫下載的使用者，已下載只變更。  <br/> |
|上傳的檔案至文件庫  <br/> |FileSyncUploadedFull  <br/> |使用者建立同步處理關係並且成功將檔案上傳至文件庫第一次從其電腦。  <br/> |
|將變更上傳的檔案至文件庫  <br/> |FileSyncUploadedPartial  <br/> |使用者成功地將變更上載至文件庫上的檔案。 此事件表示對文件庫檔案的本機版本所做的任何變更都已成功上傳至文件庫。 只變更會卸載，因為這些檔案先前上傳的使用者 (所指示 * * 檔案上傳至文件庫 * * 活動)。  <br/> |
||||
  
### <a name="site-administration-activities"></a>網站管理活動
  
下表列出所得網站管理工作，在 SharePoint Online 中的事件。
  
|**易記名稱**|**Operation**|**描述**|
|:-----|:-----|:-----|
|新增免除使用者代理程式  <br/> |ExemptUserAgentSet  <br/> |在 SharePoint 或全域系統管理員將使用者代理程式新增至 SharePoint 系統管理中心的免除使用者代理程式的清單。  <br/> |
|新增的網站集合管理員  <br/> |SiteCollectionAdminAdded  <br/> |網站集合管理員或擁有者將人員新增為網站的網站集合管理員。 網站集合管理員擁有網站集合及其所有子網站的完整控制權限。 當系統管理員可讓自己存取使用者的 OneDrive 帳戶中 （藉由編輯 SharePoint 系統管理中心或[使用 Office 365 系統管理中心](https://docs.microsoft.com/office365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data#part-1---get-access-to-the-former-employees-onedrive-for-business-documents)中的使用者設定檔），也會記錄此活動。 <br/> |
|(無)  <br/> |SiteCollectionAdminRemoved <br/> |網站集合管理員或擁有者會移除為網站的網站集合管理員的人員。 當系統管理員自行從清單中移除的網站集合管理員使用者的 OneDrive 帳戶 （藉由編輯 SharePoint 系統管理中心中的使用者設定檔），也會記錄此活動。  請注意，若要傳回此活動的稽核記錄搜尋結果中，您要搜尋的所有活動。 <br/> |
|新增的使用者或群組至 SharePoint 群組  <br/> |AddedToGroup  <br/> |使用者新增至 SharePoint 群組的成員或來賓。 這可能已經故意巨集指令或另一個活動，例如共用事件的結果。  <br/> |
|允許使用者建立群組  <br/> |AllowGroupCreationSet  <br/> |網站管理員或擁有者會新增至網站，可讓使用者權限等級指派該權限建立該網站的群組。  <br/> |
|已取消的網站異地移動  <br/> |SiteGeoMoveCancelled  <br/> |在 SharePoint 或全域系統管理員已成功取消 SharePoint 或 OneDrive 網站異地移動。 多地理位置功能可讓橫跨多個 Office 365 資料中心地區，稱為 geos Office 365 組織。 如需詳細資訊，請參閱 < <b0>OneDrive 中和 Office 365 中 SharePoint Online 的多地理位置功能</b0>。  <br/> |
|變更共用原則  <br/> |SharingPolicyChanged  <br/> |在 SharePoint 或全域系統管理員變更 SharePoint 共用原則使用 Office 365 系統管理入口網站，SharePoint 系統管理入口網站或 SharePoint Online 管理命令介面。 在您組織中的共用原則中設定的任何變更會被記錄。 **ModifiedProperties**欄位中的事件記錄的詳細屬性被識別已變更的原則。  <br/> |
|變更裝置存取原則  <br/> |DeviceAccessPolicyChanged  <br/> |在 SharePoint 或全域系統管理員變更貴組織的受管理的裝置原則。 此原則可控制存取未加入您的組織的裝置從 SharePoint、 OneDrive 和 Office 365。 若要設定此原則需要企業行動力 + 安全性訂閱。 如需詳細資訊，請參閱[控制未受管理裝置的存取權](https://support.office.com/article/5ae550c4-bd20-4257-847b-5c20fb053622)。  <br/> |
|變更免除使用者代理程式  <br/> |CustomizeExemptUsers  <br/> |在 SharePoint 或全域系統管理員自訂 SharePoint 系統管理中心的免除使用者代理程式的清單。 您可以指定要免除哪些使用者代理程式接收要編製索引的整個網頁。 這表示當您已指定為不受遇到 InfoPath 表單的使用者代理程式時，表單將會傳回為 XML 檔案，而不是整個網頁。 這樣可以讓編製索引 InfoPath 表單更快速。  <br/> |
|變更網路存取原則  <br/> |NetworkAccessPolicyChanged  <br/> |在 SharePoint 或全域系統管理員變更 （也稱為信任的網路界限） [SharePoint 系統管理中心或使用 SharePoint Online PowerShell 的位置式存取原則。 此類型的原則控制可以存取 SharePoint 和 OneDrive 根據授權的 IP 位址範圍，您指定貴組織中的資源。 如需詳細資訊，請參閱 < <b0>SharePoint Online 和 OneDrive 資料是根據網路位置控制存取</b0>。  <br/> |
|已完成的站台異地移動  <br/> |SiteGeoMoveCompleted  <br/> |使用您的組織中的全域系統管理員已排定網站異地移動已順利完成。 多地理位置功能可讓橫跨多個 Office 365 資料中心地區，稱為 geos Office 365 組織。 如需詳細資訊，請參閱 < <b0>OneDrive 中和 Office 365 中 SharePoint Online 的多地理位置功能</b0>。  <br/> |
|建立的群組  <br/> |GroupAdded  <br/> |網站管理員或擁有者會建立一組網站，或執行所建立的群組會導致工作。 例如，第一次使用者建立共用檔案的連結，系統群組新增至使用者的 OneDrive for Business 網站。 此事件也可以透過使用者建立具有共用檔案編輯權限的連結而產生。  <br/> |
|建立傳送至連線  <br/> |SendToConnectionAdded  <br/> |SharePoint 或全域系統管理員會在 SharePoint 系統管理中心的 [記錄管理] 頁面上建立新的傳送至連線。 「傳送至」連線指定文件存放庫或記錄中心的設定。 「傳送至」連線建立時，[內容組合管理] 可以將文件提交至指定位置。  <br/> |
|建立的網站集合  <br/> |SiteCollectionCreated  <br/> |SharePoint 或全域系統管理員會在您的 SharePoint Online 組織中建立新的網站集合或使用者佈建 OneDrive for Business 網站。  <br/> |
|已刪除的群組  <br/> |GroupRemoved  <br/> |使用者從網站刪除群組。  <br/> |
|刪除傳送至連線  <br/> |SendToConnectionRemoved  <br/> |在 SharePoint 或全域系統管理員刪除傳送至連線在記錄管理] 頁面上，在 SharePoint 系統管理中心。  <br/> |
|已刪除的網站  <br/> |SiteDeleted  <br/> |網站管理員刪除網站。  <br/> |
|啟用文件預覽  <br/> |PreviewModeEnabledSet  <br/> |網站管理員可讓網站的文件預覽。  <br/> |
|啟用舊版的工作流程  <br/> |LegacyWorkflowEnabledSet  <br/> |網站管理員或擁有者將 SharePoint 2013 工作流程工作內容類型新增至網站。 全域管理員也可以在 SharePoint 系統管理中心啟用整個組織的工作流程。  <br/> |
|啟用的 Office on Demand  <br/> |OfficeOnDemandSet  <br/> |網站管理員啟用 Office on Demand，讓使用者存取最新版本的 Office 桌面應用程式。 Office on Demand SharePoint 系統管理中心中已啟用，且需要 Office 365 訂用帳戶包含完整的安裝 Office 應用程式。  <br/> |
|啟用的 RSS 摘要  <br/> |NewsFeedEnabledSet  <br/> |網站管理員或擁有者可讓網站的 RSS 摘要。 全域管理員可以在 SharePoint 系統管理中心啟用整個組織的 RSS 摘要。  <br/> |
|已修改的存取要求設定  <br/> |WebRequestAccessModified  <br/> |在網站上進行修改的存取要求設定。  <br/> |
|已修改的成員可以共用設定  <br/> |WebMembersCanShareModified  <br/> |在網站上修改**成員可以共用**設定。  <br/> |
|修改的網站權限  <br/> |SitePermissionsModified  <br/> |網站管理員或擁有者 （或系統帳戶） 變更指派給站台的群組的權限等級。 如果從群組中移除所有的權限，也會記錄此活動。  <br/> > [!NOTE]這項作業已被取代的 SharePoint Online 的 >。 若要尋找相關的事件，您可以搜尋其他權限相關的活動，例如**新增網站集合系統管理員**、**新增使用者或群組至 SharePoint 群組**、**允許使用者建立群組**，**建立群組**，以及**已刪除群組。**         |
|從 SharePoint 群組中移除使用者或群組  <br/> |RemovedFromGroup  <br/> |使用者會移除 SharePoint 群組的成員或來賓。 這可能已經故意巨集指令或另一個活動，例如取消事件的結果。  <br/> |
|重新命名的網站  <br/> |SiteRenamed  <br/> |網站管理員或擁有者重新命名網站  <br/> |
|要求的網站系統管理員權限  <br/> |SiteAdminChangeRequest  <br/> |若要新增為網站集合的網站集合管理員的使用者要求。 網站集合管理員擁有網站集合及其所有子網站的完整控制權限。  <br/> |
|排程的網站異地移動  <br/> |SiteGeoMoveScheduled  <br/> |在 SharePoint 或全域系統管理員已成功排程 SharePoint 或 OneDrive 網站異地移動。 多地理位置功能可讓橫跨多個 Office 365 資料中心地區，稱為 geos Office 365 組織。 如需詳細資訊，請參閱 < <b0>OneDrive 中和 Office 365 中 SharePoint Online 的多地理位置功能</b0>。  <br/> |
|設定主機網站  <br/> |HostSiteSet  <br/> |SharePoint 或全域系統管理員變更指定的網站來主控個人或 OneDrive for Business 網站。  <br/> |
|更新的群組  <br/> |GroupUpdated  <br/> |網站管理員或擁有者變更設定的網站群組。 這可以包括變更群組的名稱、可以檢視或編輯群組成員資格的人員，以及成員資格要求的處理方式。  <br/> |
||||
  
### <a name="exchange-mailbox-activities"></a>Exchange 信箱活動
  
下表列出的活動，可記錄信箱稽核記錄。 會記錄信箱擁有者、 委派的使用者或系統管理員所執行的信箱活動。 根據預設，Office 365 中的信箱稽核無法開啟。 信箱稽核記錄必須開啟每一個信箱將會記錄信箱活動之前。 如需詳細資訊，請參閱 <<c0>啟用 Office 365 中的稽核的信箱。
  
|**易記名稱**|**Operation**|**描述**|
|:-----|:-----|:-----|
|新增的委派信箱權限  <br/> |Add-mailboxpermission  <br/> |系統管理員指派給使用者 （稱為 「 代理人 」） 的 FullAccess 信箱權限給其他人的信箱。 FullAccess 權限可讓代理人開啟另一個使用者的信箱，並讀取和管理信箱的內容。  <br/> |
|分類為記錄的郵件  <br/> |ApplyRecordLabel<br/> |郵件被分類為記錄。 分類為記錄的內容保留標籤手動或自動套用至郵件會發生此錯誤。<br/> |
|複製到另一個資料夾的郵件  <br/> |複製  <br/> |郵件已複製到另一個資料夾。  <br/> |
|建立的信箱項目  <br/> |Create  <br/> |在信箱; 中的 [行事曆、 連絡人、 備忘稿或工作] 資料夾中建立項目例如，會建立新的會議邀請。 請注意不稽核建立、 傳送或接收郵件。 此外，不稽核建立一個信箱資料夾。  <br/> |
|在 Outlook web app 中建立新的收件匣規則  <br/> |NewInboxRule<br/> |<br/> |
|從 [刪除的項目] 資料夾的已刪除郵件  <br/> |SoftDelete  <br/> |郵件已永久刪除，或從 [刪除的項目] 資料夾中刪除。 這些項目會移至 [可復原的項目] 資料夾。 當使用者選取它，並按下**Shift + Delete**，郵件也會移至 [可復原的項目] 資料夾。  <br/> |
|移至另一個資料夾的郵件  <br/> |移動  <br/> |郵件已移到另一個資料夾。  <br/> |
|移至刪除的項目] 資料夾的郵件  <br/> |MoveToDeletedItems  <br/> |已刪除的郵件，並將它移至 [刪除的項目] 資料夾。  <br/> |
|修改的資料夾權限  <br/> |UpdateFolderPermissions  <br/> |已變更資料夾的權限。 資料夾的權限控制您組織中的哪些使用者可以存取信箱資料夾和資料夾中的郵件。  <br/> |
|從信箱清除的郵件  <br/> |HardDelete  <br/> |郵件已清除從 [可復原的項目] 資料夾 （從信箱中永久刪除）。  <br/> |
|已移除的委派信箱權限  <br/> |Remove-mailboxpermission  <br/> |系統管理員移除某個人的信箱的 FullAccess 權限 （也就指派給代理人）。 移除的 FullAccess 權限後，代理人無法開啟另一個使用者的信箱，或存取任何內容。  <br/> |
|傳送訊息使用傳送為 」 權限  <br/> |SendAs  <br/> |郵件已傳送使用 SendAs 權限。 這表示另一位使用者傳送的郵件，就好像它來自信箱擁有者。  <br/> |
|傳送訊息使用傳送代理者權限  <br/> |SendOnBehalf  <br/> |郵件已傳送使用 SendOnBehalf 權限。 這表示另一位使用者傳送代表信箱擁有者的郵件。 郵件已傳送代理者誰以及實際寄件者郵件的訊息會指出收件者。  <br/> |
|更新的委派存取權的行事曆資料夾  <br/> |UpdateCalendarDelegation  <br/> |行事曆委派已指派給信箱。 行事曆委派可讓其他人在相同的組織權限來管理信箱擁有者的行事曆。  <br/> |
|更新的訊息  <br/> |Update  <br/> |郵件或其屬性已變更。  <br/> |
|登入信箱的使用者  <br/> |MailboxLogin  <br/> |使用者登入其信箱。  <br/> |
|(無)  <br/> |UpdateInboxRules  <br/> |已新增、 移除或變更收件匣規則。 收件匣規則用來處理郵件使用者的收件匣根據指定的條件，並符合規則的條件，例如將郵件移至指定資料夾或刪除郵件時採取的動作。  <br/> 若要傳回的收件匣規則活動的項目，您必須在**活動**清單中選取 [**顯示所有活動的結果**。 使用日期範圍] 方塊和 [**使用者**] 清單來縮小搜尋結果。  <br/> |
||||

### <a name="sway-activities"></a>Sway 活動
  
下表列出在 Sway 中的使用者和系統管理員活動。 Sway 是 Office 365 應用程式，可協助使用者收集、 格式化及分享想法、 故事，並在互動式、 web 式畫布上的簡報。 如需詳細資訊，請參閱[常見問題集關於 Sway-系統管理說明](https://support.office.com/article/446380fa-25bf-47b2-996c-e12cb2f9d075)。
  
|**易記名稱**|**Operation**|**描述**|
|:-----|:-----|:-----|
|已變更的 Sway 共用層級  <br/> |SwayChangeShareLevel  <br/> |會在使用者變更 Sway 的共用層級。 此事件會擷取使用者變更共用 Sway; 相關聯的範圍例如，與組織內公用。  <br/> |
|建立的 Sway  <br/> |SwayCreate  <br/> |使用者建立 Sway。  <br/> |
|刪除的 Sway  <br/> |SwayDelete  <br/> |在使用者刪除 Sway。  <br/> |
|已停用的 Sway 重複  <br/> |SwayDisableDuplication  <br/> |使用者會停用 Sway 重複。  <br/> |
|重複的 Sway  <br/> |SwayDuplicate  <br/> |使用者會複製 Sway。  <br/> |
|編輯的 Sway  <br/> |SwayEdit  <br/> |使用者編輯 Sway。  <br/> |
|啟用的 Sway 重複  <br/> |EnableDuplication  <br/> |使用者啟用重複的 Sway;預設會啟用使用者啟用重複的 Sway 的能力。  <br/> |
|撤銷 Sway 共用  <br/> |SwayRevokeShare  <br/> |使用者會停止共用 Sway 利用撤銷存取權限。 撤銷存取變更 Sway 相關聯的連結。  <br/> |
|共用的 Sway  <br/> |SwayShare  <br/> |使用者要共用的 Sway。 此事件會擷取按一下特定共用的目的地 Sway 的 [共用] 功能表內的使用者動作。 此事件不會指出使用者是否已完成的共用巨集指令。  <br/> |
|關閉外部共用的 Sway  <br/> |SwayExternalSharingOff  <br/> |系統管理員會停用整個組織使用 Office 365 系統管理中心外部 Sway 的共用。  <br/> |
|開啟外部共用的 Sway  <br/> |SwayExternalSharingOn  <br/> |管理員啟用整個組織使用 Office 365 系統管理中心外部 Sway 的共用。  <br/> |
|關閉 Sway 服務  <br/> |SwayServiceOff  <br/> |系統管理員停用 Sway 為整個組織使用 Office 365 系統管理中心。  <br/> |
|開啟 Sway 服務  <br/> |SwayServiceOn  <br/> |管理員為整個組織啟用 Sway，藉由使用 Office 365 系統管理中心 (預設為啟用服務的 Sway)。  <br/> |
|檢視的 Sway  <br/> |SwayView  <br/> |使用者檢視 Sway。  <br/> |
||||

  
### <a name="user-administration-activities"></a>使用者管理活動
  
下表列出會記錄系統管理員新增或變更的使用者帳戶使用 Office 365 系統管理中心或 Azure 管理入口網站時的使用者管理活動。
  
|**活動**|**Operation**|**描述**|
|:-----|:-----|:-----|
|新增的使用者  <br/> |新增使用者  <br/> |建立 Office 365 使用者帳戶。  <br/> |
|已變更的使用者授權  <br/> |變更使用者授權  <br/> |指派授權給使用者變更的項目。 若要查看哪些授權已變更，請參閱 < 的相對應的<b0>更新使用者</b0>活動。  <br/> |
|變更的使用者密碼  <br/> |變更使用者密碼  <br/> |系統管理員變更密碼的使用者的密碼。  <br/> |
|已刪除的使用者  <br/> |Delete user  <br/> |Office 365 使用者帳戶被刪除。  <br/> |
|重設使用者密碼  <br/> |重設使用者密碼  <br/> |系統管理員重設使用者的密碼。  <br/> |
|設定會強制使用者變更密碼的屬性  <br/> |設定強制變更使用者密碼  <br/> |系統管理員設定會強制使用者變更其密碼。 在下一次使用者登入 Office 365 的屬性。  <br/> |
|設定授權屬性  <br/> |設定授權屬性  <br/> |系統管理員修改的授權，指派給使用者的屬性。  <br/> |
|更新的使用者  <br/> |更新使用者  <br/> |系統管理員變更使用者帳戶的一或多個的屬性。 如需可更新的使用者屬性的清單，請參閱[Azure Active Directory 稽核報告事件](https://go.microsoft.com/fwlink/p/?LinkID=616549)」 更新使用者屬性 」 一節。  <br/> |
||||
  
### <a name="azure-ad-group-administration-activities"></a>Azure AD 群組管理活動
  
下表列出會記錄系統管理員或使用者建立或變更 Office 365 群組時，或當系統管理員會使用在 Office 365 系統管理中心或 Azure 管理入口網站建立安全性群組的群組管理活動。 如需 Office 365 中群組的詳細資訊，請參閱[檢視、 建立及刪除 Office 365 系統管理中心中的群組](https://support.office.com/article/a6360120-2fc4-46af-b105-6a04dc5461c7)。
  
|**易記名稱**|**Operation**|**描述**|
|:-----|:-----|:-----|
|新增的群組  <br/> |新增群組  <br/> |已建立的群組。  <br/> |
|新增的成員至群組  <br/> |將成員新增至群組  <br/> |成員已新增至群組。  <br/> |
|已刪除的群組  <br/> |刪除群組  <br/> |已刪除的群組。  <br/> |
|從群組移除的成員  <br/> |從群組移除成員  <br/> |已將成員從群組中移除。  <br/> |
|更新的群組  <br/> |更新群組  <br/> |已變更群組的屬性。  <br/> |
||||
   
### <a name="application-administration-activities"></a>應用程式管理活動
  
下表列出會記錄系統管理員新增或變更在 Azure AD 中註冊應用程式時的應用程式系統管理員活動。 任何依賴進行驗證的 Azure AD 的應用程式必須在目錄中註冊。
  
|**易記名稱**|**Operation**|**描述**|
|:-----|:-----|:-----|
|新增的委派項目  <br/> |新增委派項目  <br/> |驗證權限已建立/授與 Azure AD 中的應用程式。  <br/> |
|已新增的服務主要名稱  <br/> |新增服務主要名稱  <br/> |在 Azure AD 中已註冊應用程式。 在目錄中的服務主體代表應用程式。  <br/> |
|已新增的認證以服務主要名稱  <br/> |將服務主體認證新增  <br/> |憑證已新增至主體 Azure AD 中的服務。 服務原則代表目錄中的應用程式。  <br/> |
|已移除的委派項目  <br/> |移除委派項目  <br/> |驗證權限已從在 Azure AD 中的應用程式中移除。  <br/> |
|從目錄中移除的服務主要名稱  <br/> |移除服務主要名稱  <br/> |應用程式已刪除/取消註冊從 Azure AD。 在目錄中的服務主體代表應用程式。  <br/> |
|已移除從主要服務的認證  <br/> |移除服務主體認證  <br/> |認證已移除主要在 Azure AD 中的服務。 服務原則代表目錄中的應用程式。  <br/> |
|設定委派項目  <br/> |設定委派項目  <br/> |驗證權限已更新的 Azure AD 中的應用程式。  <br/> |
||||

### <a name="role-administration-activities"></a>角色管理活動
  
下表列出當系統管理員管理 Office 365 系統管理中心或 Azure 管理入口網站中的系統管理員角色時，會記錄的 Azure AD 角色管理活動。
  
|**易記名稱**|**Operation**|**描述**|
|:-----|:-----|:-----|
|將成員新增至角色  <br/> |將角色成員新增至角色  <br/> |新增使用者至 Office 365 中系統管理員角色。  <br/> |
|從目錄角色移除使用者  <br/> |從角色移除角色成員  <br/> |在 Office 365 中移除使用者從系統管理員角色。  <br/> |
|設定公司連絡人資訊  <br/> |設定公司連絡人資訊  <br/> |更新您的 Office 365 組織的公司層級連絡人喜好設定。 這包括訂閱相關的電子郵件由 Office 365，以及 Office 365 服務相關的技術通知傳送的電子郵件地址。  <br/> |
||||
   
### <a name="directory-administration-activities"></a>目錄管理活動
  
下表列出 Azure AD 目錄及網域相關的系統管理員管理 Office 365 組織中的 Office 365 系統管理中心，或在 Azure 管理入口網站會記錄的活動。
  
|**易記名稱**|**Operation**|**描述**|
|:-----|:-----|:-----|
|新增的網域至公司  <br/> |將網域新增至公司  <br/> |新增網域至 Office 365 組織。  <br/> |
|新增合作夥伴到目錄  <br/> |將合作夥伴新增至公司  <br/> |新增合作夥伴 （委派的系統管理員） 至 Office 365 組織。  <br/> |
|公司中移除的網域  <br/> |移除公司的網域  <br/> |從 Office 365 組織中移除網域。  <br/> |
|從目錄上移除合作夥伴  <br/> |移除公司的協力廠商  <br/> |從 Office 365 組織中移除合作夥伴 （委派的系統管理員）。  <br/> |
|設定公司資訊  <br/> |設定公司資訊  <br/> |更新您的 Office 365 組織的公司資訊。 這包括訂閱相關的電子郵件由 Office 365，以及 Office 365 服務相關的技術通知傳送的電子郵件地址。  <br/> |
|設定網域驗證  <br/> |設定網域驗證  <br/> |變更您的 Office 365 組織的網域驗證設定。  <br/> |
|更新網域的同盟設定  <br/> |在網域上設定同盟設定  <br/> |變更您的 Office 365 組織的同盟 （外部共用） 設定。  <br/> |
|設定密碼原則  <br/> |設定密碼原則  <br/> |變更 Office 365 組織中的使用者密碼的長度及字元限制。  <br/> |
|開啟 Azure AD 同步處理  <br/> |在 [公司設定 DirSyncEnabled 旗標  <br/> |設定啟用 Azure AD 同步處理目錄的屬性。  <br/> |
|更新的網域  <br/> |更新的網域  <br/> |更新您的 Office 365 組織中的網域的設定。  <br/> |
|已驗證的網域  <br/> |驗證網域  <br/> |驗證您的組織已加入網域的擁有者。  <br/> |
|已驗證的電子郵件已驗證的網域  <br/> |確認電子郵件已驗證的網域  <br/> |若要確認您的組織已加入網域的擁有者使用的電子郵件驗證。  <br/> |
||||
   
### <a name="ediscovery-activities"></a>電子文件探索活動
  
在 Office 365 稽核記錄檔中記錄內容搜尋和 eDiscovery 相關的活動在 Office 365 安全性 & 合規性中心中，或藉由執行對應的 Windows PowerShell cmdlet 所執行。 這包括下列活動：
  
- 建立及管理 eDiscovery 案例
    
- 建立、 啟動和編輯內容搜尋
    
- 執行內容搜尋動作，例如預覽，匯出，以及刪除搜尋結果
    
- 設定內容搜尋的權限篩選
    
- 管理 eDiscovery 系統管理員角色
    
清單與電子文件探索活動所記錄的詳細的說明，請參閱[搜尋 eDiscovery 活動在 Office 365 稽核記錄](search-for-ediscovery-activities-in-the-audit-log.md)。
  
> [!NOTE]
> 花費最多 30 分鐘所得列在 [**活動**下拉式清單中要顯示在搜尋結果中的**eDiscovery 活動**之下的活動的事件。 相反地，採用 24 小時的時間從 eDiscovery 對應事件的指令程式的活動，以顯示在搜尋結果。 
  
### <a name="power-bi-activities"></a>Power BI 活動
  
您可以在 Power BI 中搜尋活動的稽核記錄檔。 Power BI 活動的相關資訊，請參閱[稽核組織內使用](https://docs.microsoft.com/power-bi/service-admin-auditing#activities-audited-by-power-bi)的 「 活動的稽核依 Power Power BI 」 一節。
  
請注意，預設為未啟用 Power bi 的稽核記錄。 若要搜尋的 Office 365 稽核記錄中的 Power BI 活動，您必須啟用 Power BI 系統管理入口網站中的稽核。 如需相關指示，請參閱 < <b0>Power BI 系統管理入口網站</b0>的 「 稽核記錄 」 一節。
  
### <a name="microsoft-workplace-analytics-activities"></a>Microsoft 工作場所分析活動

工作場所分析提供深入群組跨 Office 365 組織的共同作業。 下表列出 「 管理員 」 角色或 「 工作場所分析中的分析師角色指派的使用者所執行的活動。 指派分析師角色的使用者擁有完整存取權的所有服務功能，以及使用產品進行分析。 指派系統管理員角色的使用者可以設定隱私權設定與系統的預設值，可以準備、 上傳，並確認工作場所分析中的組織資料。 如需詳細資訊，請參閱 <<c0>工作場所分析。

|**易記名稱**|**Operation**|**描述**|
|:-----|:-----|:-----|
|存取的 OData 連結 <br/> |AccessedOdataLink <br/> |分析師存取查詢的 OData 連結。|
|已取消的查詢 <br/> |CanceledQuery <br/> |分析師取消執行查詢。|
|建立的會議排除項目 <br/> |MeetingExclusionCreated <br/> |建立新的分析師會議排除規則。|
|已刪除的結果 <br/> |DeletedResult <br/> |分析師刪除查詢結果。|
|下載的報告 <br/> |DownloadedReport <br/> |分析師下載查詢結果檔案。|
|執行的查詢 <br/> |ExecutedQuery <br/> |分析師執行查詢。|
|更新的資料存取設定 <br/> |UpdatedDataAccessSetting <br/> |系統管理員更新資料存取設定。|
|更新的隱私權設定 <br/> |UpdatedPrivacySetting <br/> |系統管理員更新隱私權設定;例如，最小的群組大小。|
|上傳的組織資料 <br/> |UploadedOrgData <br/> |系統管理員上傳組織資料檔案。|
|檢視瀏覽 <br/> |ViewedExplore <br/> |分析師在一或多個瀏覽頁面索引標籤中檢視的視覺效果。|
||||

### <a name="microsoft-teams-activities"></a>Microsoft Teams 活動
  
下表列出使用者並登入 Office 365 的 Microsoft Teams 中的系統管理員活動的稽核記錄。 Microsoft Teams 是 Office 365 中的聊天置中對齊工作區。 它小組的交談、 會議、 檔案及備忘稿聚集所有同等級到單一位置。 如需詳細資訊與連結的說明主題，請參閱：
  
- [常見問題集有關 Microsoft Teams-系統管理說明](https://support.office.com/article/05cbe533-2181-4e95-a4b0-52cd7695fafc)
    
- [Microsoft Teams 說明](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
|**易記名稱**|**Operation**|**描述**|
|:-----|:-----|:-----|
|已新增到小組 bot  <br/> |BotAddedToTeam  <br/> |使用者新增到小組 bot。  <br/> |
|新增的通道  <br/> |ChannelAdded  <br/> |使用者會新增至小組的通道。  <br/> |
|新增的連接器  <br/> |ConnectorAdded  <br/> |使用者將連接器新增至通道。  <br/> |
|已新增到小組成員  <br/> |MemberAdded  <br/> |小組擁有者會將成員新增到小組。  <br/> |
|新增索引標籤  <br/> |TabAdded  <br/> |使用者將 tab 新增至通道。  <br/> |
|變更通道設定  <br/> |ChannelSettingChanged  <br/> | 小組成員中執行下列活動時，會記錄 ChannelSettingChanged 作業。 針對每個這些活動，設定已變更 （如括弧以下所示） 的描述會顯示在稽核記錄搜尋結果中的**項目**] 欄中。  <br/> <br/>-變更的小組通道 （**通道名稱**） 的名稱。  <br/>  <br/>-變更的小組通道 （**通道描述**） 的描述。  <br/> |
|變更組織設定  <br/> |TeamsTenantSettingChanged  <br/> | TeamsTenantSettingChanged 作業會記錄時 （使用在 Office 365 系統管理中心）; 全域系統管理員會執行下列活動請注意，這些活動會影響整個組織的 Microsoft Teams 設定。 如需詳細資訊，請參閱[Microsoft Teams 的系統管理員設定](https://support.office.com/article/3966a3f5-7e0f-4ea9-a402-41888f455ba2)。  <br/>  針對每個這些活動，設定已變更 （如括弧以下所示） 的描述會顯示在稽核記錄搜尋結果中的**項目**] 欄中。  <br/><br/>-啟用或停用組織 ( **Microsoft Teams**) 的 Microsoft Teams。  <br/><br/>-啟用或停用 Microsoft Teams 和商務用 Skype 之間的交互操作性，為組織 ( **Skype for Business 的互通性**)。<br/><br/>-啟用或停用 Microsoft Teams 用戶端 （ **Org 圖表] 檢視**） 中的 [組織圖] 檢視。  <br/><br/>-啟用或停用的排程 （**私人會議排程功能**） 的私用會議的小組成員的能力。  <br/><br/>-啟用或停用的排程 （**通道會議排程功能**） 的通道會議的小組成員的能力。  <br/><br/>-啟用或停用視訊通話中 Teams 會議 （ **Skype 會議視訊**）。  <br/><br/>-啟用或停用螢幕共用 Microsoft Teams meetups 組織 （**畫面共享 Skype 會議**]） 中。  <br/><br/>-啟用或停該能夠將動畫效果的影像 （稱為 Giphys） 加入至 Teams 交談 （**動畫效果的影像**）。  <br/><br/>-變更分級組織 （**內容分級**） 設定的內容。 內容分級限制可以顯示在對話中的動畫影像的類型。  <br/><br/>-啟用或會停用功能適用於小組成員新增自訂的圖像 （稱為 「 自訂 memes） 從網際網路到小組交談 （**從網際網路的可自訂映像**）。  <br/><br/>-啟用或停小組交談 （**可編輯的影像**） 適用於小組成員新增 （稱為貼紙） 的可編輯影像的能力。<br/><br/>-啟用或停用該功能適用於使用 Microsoft Teams 聊天和通道 (**全組織 bot**) 中的 bot 的小組成員。<br/><br/>-啟用 Microsoft Teams; 特定 bot這不包含 T-Bot，也就是當組織 (**個別 bot**) 啟用 bot 是可用的 Teams 說明 bot。  <br/><br/>-啟用或停用若要新增分機或索引標籤 （**分機或索引標籤**） 的小組成員的功能。  <br/><br/>-啟用或停用的 Microsoft Teams ( **Bot 端載入**) 的專屬 Bot 端載入。  <br/><br/>-啟用或停用使用者的 Microsoft Teams 通道 (**通道電子郵件**) 傳送電子郵件訊息的能力。  <br/> |
|變更的角色中小組的成員  <br/> |MemberRoleChanged  <br/> |在 [小組成員的角色變更小組擁有者。 下列的值表示指派給使用者的角色類型。  <br/><br/><br/> **1** -表示擁有者 」 角色。<br/>**2** -會指出 「 成員 」 角色。 <br/>**3** -會指出 「 來賓 」 角色。 <br/>Members 屬性也會包含您的組織和成員的電子郵件地址的名稱。  <br/> |
|變更小組設定  <br/> |TeamSettingChanged  <br/> | 下列活動小組擁有者執行時，會記錄 TeamSettingChanged 作業。 針對每個這些活動，設定已變更 （如括弧以下所示） 的描述會顯示在稽核記錄搜尋結果中的**項目**] 欄中。  <br/><br/>-變更小組的存取類型。 小組可以設為私人或公開 （**小組存取類型**）。 當小組為私用 （預設設定），使用者可以存取小組僅邀請。 公用小組時，就可被探索到的任何人。  <br/><br/>-變更之小組 （**小組分類**） 的資訊分類。  <br/>  例如，小組資料可分類為高業務影響、 中等的商業影響或低業務影響。<br/><br/>-變更之小組 （**小組名稱**） 的名稱。  <br/><br/>-變更小組描述 （**小組描述**）。 <br/><br/>-任何小組設定所做的變更。 小組擁有者可以存取這些設定 microsoft Teams 用戶端中的小組滑鼠右鍵按一下，按一下 [**管理小組**，然後按一下 [**設定**] 索引標籤。對這些活動，設定已變更的名稱會顯示在稽核記錄搜尋結果中的**項目**資料行。  <br/> |
|建立的小組  <br/> |TeamCreated  <br/> |在使用者建立新的小組。  <br/> |
|已刪除的通道  <br/> |ChannelDeleted  <br/> |使用者從小組刪除通道。  <br/> |
|已刪除的小組  <br/> |TeamDeleted  <br/> |小組擁有者會刪除小組。  <br/> |
|已移除的 bot 小組  <br/> |BotRemovedFromTeam  <br/> |使用者會將 bot 移除小組。  <br/> |
|已移除的連接器  <br/> |ConnectorRemoved  <br/> |使用者會移除通道中的連接器。  <br/> |
|移除小組的成員  <br/> |MemberRemoved  <br/> |小組擁有者會移除小組的成員。  <br/> |
|移除索引標籤  <br/> |TabRemoved  <br/> |使用者移除通道] 索引標籤。  <br/> |
|更新的連接器  <br/> |ConnectorUpdated  <br/> |使用者修改某個通道中的連接器。  <br/> |
|更新] 索引標籤  <br/> |TabUpdated  <br/> |使用者修改某個通道中的索引標籤。  <br/> |
|使用者登入 microsoft Teams  <br/> |TeamsSessionStarted  <br/> |使用者登入 Microsoft Teams 用戶端。  <br/> |
||||

### <a name="yammer-activities"></a>Yammer 活動
  
下表列出使用者並登入 Office 365 的系統管理員活動 Yammer 中的稽核記錄。 若要傳回 Yammer 相關的活動，從 Office 365 稽核記錄，您必須在**活動**清單中選取 [**顯示所有活動的結果**。 使用日期範圍] 方塊和 [**使用者**] 清單來縮小搜尋結果。 
  
|**易記名稱**|**Operation**|**描述**|
|:-----|:-----|:-----|
|變更的資料保留原則  <br/> |SoftDeleteSettingsUpdated  <br/> |已驗證的系統管理員更新實刪除] 或 [虛刪除的網路資料保留原則的設定。 只有已驗證的系統管理員才能執行這項作業。  <br/> |
|變更的網路組態  <br/> |NetworkConfigurationUpdated  <br/> |網路或已驗證的系統管理員變更在 Yammer 網路的組態。 這包括設定匯出資料並啟用聊天室的間隔。  <br/> |
|變更的網路設定檔設定  <br/> |ProcessProfileFields  <br/> |網路或已驗證的系統管理員變更在成員設定檔的網路使用者網路上所顯示的資訊。  <br/> |
|已變更的私人內容模式  <br/> |SupervisorAdminToggled  <br/> |開啟或關閉，驗證的系統就會開啟*私人內容模式*。 此模式屬性可讓系統管理員檢視張貼在私人群組及檢視個別的使用者 （或使用者群組） 之間的私人郵件。 只有已驗證的管理員可以執行這項作業。  <br/> |
|已變更的安全性設定  <br/> |NetworkSecurityConfigurationUpdated  <br/> |已驗證的系統管理員更新 Yammer 網路的安全性設定。 這包括設定密碼到期原則和 IP 位址的限制。 只有已驗證的系統管理員才能執行這項作業。  <br/> |
|建立的檔案  <br/> |FileCreated  <br/> |使用者上傳檔案。  <br/> |
|建立的群組  <br/> |GroupCreation  <br/> |使用者建立新的群組。  <br/> |
|已刪除的群組  <br/> |GroupDeletion  <br/> |從 Yammer 刪除群組。  <br/> |
|已刪除的郵件  <br/> |MessageDeleted  <br/> |使用者會刪除郵件。  <br/> |
|下載的檔案  <br/> |FileDownloaded  <br/> |使用者下載檔案。  <br/> |
|匯出的資料  <br/> |DataExport  <br/> |已驗證的系統管理員將 Yammer 網路資料匯出。 只有已驗證的系統管理員才能執行這項作業。  <br/> |
|共用的檔案  <br/> |FileShared  <br/> |使用者與其他使用者共用檔案。  <br/> |
|擱置的網路使用者  <br/> |NetworkUserSuspended  <br/> |網路或已驗證的系統管理員擱置 （停用） Yammer 中的使用者。  <br/> |
|暫停的使用者  <br/> |UserSuspension  <br/> |暫停使用者帳戶 （停用）。  <br/> |
|更新的檔案的描述  <br/> |FileUpdateDescription  <br/> |會在使用者變更檔案的描述。  <br/> |
|更新過的檔案名稱  <br/> |FileUpdateName  <br/> |在使用者變更檔案的名稱。  <br/> |
|檢視的檔案  <br/> |FileVisited  <br/> |使用者檢視檔案。  <br/> |
||||
   
### <a name="microsoft-flow-activities"></a>Microsoft Flow 活動

您可以在 Microsoft Flow 中搜尋活動的稽核記錄檔。 這些活動包括建立、 編輯和刪除流程，以及變更流程權限。 如需流程活動的稽核資訊，請參閱 < 部落格<b0>稽核事件目前可用的 Office 365 安全性 &amp; 合規性中心的 Microsoft Flow</b0>。

### <a name="microsoft-powerapps"></a>Microsoft PowerApps

您可以在 PowerApps 中搜尋應用程式相關的活動的稽核記錄檔。 這些活動包括建立、 啟動和發佈應用程式。 也稽核指派權限給應用程式。 所有 PowerApps 活動的說明，請參閱[PowerApps 記錄活動](https://docs.microsoft.com/en-us/power-platform/admin/logging-powerapps#what-events-are-audited)。

### <a name="microsoft-stream-activities"></a>Microsoft 資料流活動
  
您可以在 Microsoft 資料流中搜尋活動的稽核記錄檔。 這些活動包括使用者、 群組通道活動及系統管理員活動，例如管理使用者、 管理組織的設定，以及匯出報告所執行的視訊活動。 如需這些活動的說明，請參閱 < <b0>Microsoft Stream 中的稽核記錄</b0>的 「 登入 Microsoft Stream 的活動 」 一節。

### <a name="exchange-admin-audit-log"></a>Exchange 系統管理員稽核記錄
  
Exchange 系統管理員稽核記錄 — 這會啟用 Office 365 中的預設 — 當系統管理員身分 （或已被指派系統管理權限的使用者） 中 Exchange Online 組織進行變更時，在 Office 365 稽核記錄檔中記錄事件。 使用 Exchange 系統管理中心或 Windows PowerShell 中執行指令程式來進行的變更都會記錄在 Exchange 系統管理員稽核記錄檔。 如需詳細資訊的相關系統管理員稽核記錄功能在 Exchange，請參閱[系統管理員稽核記錄](https://go.microsoft.com/fwlink/p/?LinkID=619225)。
  
以下是搜尋 Exchange 系統管理員稽核記錄中的活動的一些秘訣：
  
- 若要從 Exchange 系統管理員稽核記錄中傳回項目，您必須在**活動**清單中選取 [**顯示所有活動的結果**。 使用日期範圍] 方塊和 [**使用者**] 清單來縮小搜尋結果在特定日期範圍內的特定 Exchange 系統管理員所執行的指令程式。 
    
- 若要顯示來自 Exchange 系統管理員稽核記錄的事件，篩選搜尋結果，並類型**-**（虛線） 在 [**活動**篩選] 方塊中。 這會顯示指令程式名稱，會顯示在 Exchange 系統事件的 [**活動**] 欄位。 然後您可以排序依字母順序排列的指令程式名稱。 
    
    ![若要篩選 Exchange 系統管理事件的活動] 方塊中輸入一條虛線](media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)
  
- 若要取得哪些 cmdlet 所執行、 已使用的參數和參數值，以及哪些物件受到影響的相關資訊，您必須匯出搜尋結果，並選取 [**下載所有結果**] 選項。 
    
- 您也可以使用 Exchange 系統管理中心，來檢視 Exchange 系統管理員稽核記錄中的事件。 如需相關指示，請參閱 <<c0>檢視系統管理員稽核記錄。
  
## <a name="frequently-asked-questions"></a>常見問題集

**哪裡可以找到關於 Office 365 中的稽核服務所提供的功能？**

如需 Office 365 中可用的稽核和報告功能的詳細資訊，請參閱[稽核與 Office 365 中的報告](office-365-auditing-and-reporting-overview.md)。 

**什麼是目前稽核的不同 Office 365 服務？**

最常使用的 Office 365 服務 like Exchange Online、 SharePoint Online、 OneDrive for Business、 Azure Active Directory、 Microsoft Teams、 Dynamics 365、 進階威脅防護，和 Power BI 受到稽核。 請參閱[本文開頭](search-the-audit-log-in-security-and-compliance.md)的稽核的服務清單。

**查看活動稽核稽核 Office 365 中的服務？**

請參閱本文章的清單和說明稽核 Office 365 中的活動的[稽核活動](#audited-activities)一節。

**多久需要事件發生之後才能使用稽核記錄？**

大部分的稽核資料有 30 分鐘內，但可能需要最多 24 小時之後事件發生於對應的稽核記錄項目顯示在搜尋結果中。 請參閱本文顯示的時間不同 Office 365 服務中的事件，可供[您開始之前](#before-you-begin)] 區段中的表格。

**多久會稽核記錄保留？**

如先前所述，稽核記錄的保留期間，取決於貴組織的 Office 365 訂用帳戶。  

- **Office 365 E3** -稽核記錄會保留 90 天。

- **Office 365 E5** -稽核記錄保留為 365 天 （一年）。 適用於具有 E3 訂閱和 Office 365 進階合規性附加元件訂閱的組織，也是一年保留稽核記錄。

     > [!NOTE]
     > 如同先前的說明，E5 組織 （或具有進階合規性的附加元件授權的 E3 組織） 的稽核記錄的一年保留期間是目前無法使用僅做為私人預覽計畫的一部分。 若要在此預覽計畫中註冊，請與[Microsoft 支援服務](https://docs.microsoft.com/en-us/office365/admin/contact-support-for-business-products?redirectSourcePath=%252fen-us%252farticle%252fcontact-support-for-business-products-admin-help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online)歸檔，並包括下列項目為您需要協助的描述: 「 長期 Office 365 稽核記錄檔私人預覽 」。

也請注意的稽核記錄的保留期間的持續時間根據每位使用者授權。 例如，如果您組織中的使用者指派 Office 365 版 E3 授權，該使用者所執行的活動的稽核記錄會保留 90 天。 如果 Office 365 E5 授權指派給不同的使用者，其稽核記錄會保留一年。 

**我可以透過程式設計方式存取稽核資料？**

可以。 Office 365 管理活動 API 用來以程式設計方式擷取稽核記錄。  若要開始，請參閱 <<c0>開始使用 Office 365 管理 Api。

**是否有其他方法來取得稽核記錄檔不是使用 Office 365 安全性 & 合規性中心] 或 [Office 365 管理活動 API？**

否。 以下是從 Office 365 稽核服務取得資料的只有兩種方式。 

**是否需要個別啟用 [每項服務，我想要擷取稽核記錄中的稽核？**

在大多數的 Office 365 服務中，會啟用稽核預設之後您最初開啟稽核 Office 365 組織 （如本文[開始前](#before-you-begin)一節所述）。 不過，您必須啟用稽核的每個您想要稽核的信箱在 Exchange Online 信箱。   我們正在啟用信箱稽核根據預設會針對 Office 365 組織中所有信箱。 如需詳細資訊，請參閱 「 Exchange 信箱稽核會預設為啟用 「 [Microsoft 安全性、 隱私權和規範部落](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Exchange-Mailbox-Auditing-will-be-enabled-by-default/ba-p/215171)格中。

**沒有 Office 365 稽核服務支援重複資料刪除的記錄？**

否。 稽核服務管線接近即時，，，因此無法支援重複資料刪除。
 
**沒有 Office 365 稽核資料流程跨地區嗎？**

否。 我們目前沒有稽核 NA （北美洲）、 （歐洲、 中東和非洲） EMEA 和 APAC （亞太地區） 區域中的管線部署。 不過，我們可能會將資料流經這些區域的負載平衡和只期間 live 網站問題。 當我們執行動作執行這些活動時，傳輸中的資料會加密。   
 
**稽核加密的資料嗎？**

稽核資料會儲存在其中部署稽核管線的相同區域中的 Exchange 信箱 （靜態資料）。 此資料不會加密。 不過，永遠加密傳輸中的資料。 
