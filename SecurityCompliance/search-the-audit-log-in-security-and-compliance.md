---
title: 在 Office 365 安全與規範中心搜尋稽核記錄
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365AC_AlternativeEmailAddress
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: '使用 Office 365 安全性&amp;規範中心來搜尋整合的稽核記錄，以檢視您的 Office 365 組織中的使用者與管理員的活動。 '
ms.openlocfilehash: 4c56f6f0c5f5a1ace7b94fab63d839760045c66f
ms.sourcegitcommit: 6562a0d171dacdcdb945d192f45ea1a4c0c1c0c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/24/2018
ms.locfileid: "24974683"
---
# <a name="search-the-audit-log-in-the-office-365-security-amp-compliance-center"></a>在 Office 365 安全與規範中心搜尋稽核記錄

需要尋找是否使用者檢視特定文件或清除 [從他們的信箱項目吗？若如此，您可以使用 Office 365 安全性&amp;規範中心來搜尋整合的稽核記錄，以檢視您的 Office 365 組織中的使用者與管理員的活動。整合的稽核記錄的為何？因為您可以搜尋下列類型的使用者與系統管理 Office 365 中的活動：
  
- SharePoint Online 和 OneDrive for Business 的使用者活動
    
- Exchange Online 中的使用者活動 （Exchange 信箱稽核記錄）
    
    > [!IMPORTANT]
    > 信箱稽核記錄必須開啟每個使用者信箱之前會記錄在 Exchange Online 中的使用者活動。如需詳細資訊，請參閱[啟用信箱稽核 Office 365 中](enable-mailbox-auditing.md)。
  
- 在 SharePoint Online 中管理活動
    
- 管理 Azure Active Directory （Office 365 的目錄服務） 中的活動
    
- Exchange Online 中的管理活動 （Exchange 管理員稽核記錄）
    
- Sway 中的使用者和系統活動
    
- Office 365 安全性 eDiscovery 活動&amp;規範中心
    
- Power bi for Office 365 的使用者和系統活動
    
- 使用者和系統中的 Microsoft 小組的活動

- Dynamics 365 中的使用者和系統活動
    
- Microsoft 流程中的使用者和系統活動

- Yammer 中的使用者和系統活動
    
- Microsoft Stream 中的使用者和系統活動
    
   
## <a name="before-you-begin"></a>開始之前

請務必先閱讀下列項目之前您啟動搜尋 Office 365 稽核記錄。
  
- 您 （或另一個系統管理員） 必須先開啟稽核記錄才能開始搜尋的 Office 365 稽核記錄。若要將它開啟，剛**開始錄製使用者和系統活動**頁面上按一下 [**稽核記錄搜尋**安全性&amp;規範中心。（如果您沒有看到此連結，稽核已經已開啟您的組織。）您開啟之後，會顯示訊息指出做準備的稽核記錄及您可在幾小時準備完成後執行搜尋。您只能有一次執行這項作業。 
    
    > [!NOTE]
    > 我們已經程序開啟預設稽核。加上 then，直到您可以加以開啟為先前所述。 
  
- 您必須指派 「 僅檢視稽核記錄 」 或 「 稽核記錄角色在 Exchange Online 搜尋 Office 365 稽核記錄。根據預設，這些角色被指派給 Exchange 系統管理中心的 [**權限**] 頁面上相符性管理] 和 [組織管理角色群組。若要讓使用者能夠搜尋 Office 365 稽核記錄的最低權限，您可以自訂角色群組 Exchange Online 中建立、 新增 「 僅檢視稽核記錄或稽核記錄 」 角色並再將使用者新增為新的角色群組的成員。如需詳細資訊，請參閱[管理角色群組在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688)。
    
    > [!IMPORTANT]
    > 如果您在 [安全性]**權限**] 頁面上的僅檢視稽核記錄或稽核記錄角色指派使用者&amp;規範中心他們不能搜尋 Office 365 稽核記錄。您必須指派 Exchange Online 中的權限。這是因為基礎指令程式來搜尋稽核記錄是 Exchange Online 指令程式。 
  
- 如果您想要關閉的 Office 365 組織的稽核記錄搜尋，您可以連線至 Exchange Online 組織的遠端 PowerShell 中執行下列命令：
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    若要一次開啟稽核搜尋，您可以在 Exchange Online PowerShell 中執行下列命令：
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

    如需詳細資訊，請參閱[關閉 Office 365 中的稽核記錄搜尋](turn-audit-log-search-on-or-off.md)。
    
- 先前所述，基礎指令程式來搜尋稽核記錄檔會是 Exchange Online 指令程式，這是**搜尋 UnifiedAuditLog**。這表示您可以使用此指令程式來搜尋而非使用中 [安全性] 的 [**稽核記錄檔**] 頁面上的 Office 365 稽核記錄&amp;規範中心。您必須在連線至 Exchange Online 組織的遠端 PowerShell 執行這個指令程式。如需詳細資訊，請參閱 ＜[搜尋 UnifiedAuditLog](https://go.microsoft.com/fwlink/p/?linkid=834776)。
    
- 如果您想要以程式設計方式從 Office 365 稽核記錄下載資料，我們建議您使用 Office 365 管理活動 API 而不是使用 PowerShell 指令碼。Office 365 管理活動 API 是您可以使用擬定作業、 安全性及規範的組織的監控解決方案的 REST web 服務。如需詳細資訊，請參閱[Office 365 管理活動 API 參考 （英文）](https://go.microsoft.com/fwlink/?linkid=852309)。
    
- 您可搜尋過去 90 天內所執行的活動的 Office 365 稽核記錄。
    
- 它可以需要長達 30 分鐘或向上事件之後的 24 小時的週期定期發生相對應的稽核記錄項目顯示在搜尋結果中。下表顯示 Office 365 中的不同服務所花費的時間。
    
|**Office 365 服務**|**30 分鐘**|**24 小時**|
|:-----|:-----|:-----|
|進階的威脅保護和威脅智慧  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| |
|Azure Active Directory （使用者登入事件）  <br/> ||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|Azure Active Directory （系統事件）  <br/> ||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) |
|Azure Active Directory （使用者登入事件）  <br/> ||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|資料遺失防護  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|Dynamics 365 CRM <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|eDiscovery  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|Exchange Online  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
|Microsoft Flow  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|Microsoft 表單  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|Microsoft Project  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|Microsoft Stream  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|Microsoft Teams  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
|Power BI  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|安全性&amp;規範中心  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
|SharePoint Online 和商務用 OneDrive  <br/> |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
|Sway  <br/> ||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|Yammer  <br/> ||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
   
- Azure Active Directory (Azure AD) 是 Office 365 的目錄服務。整合的稽核記錄檔包含使用者、 群組、 應用程式、 網域和執行 Office 365 系統管理中心或在 Azure 中的目錄活動管理入口網站。Azure AD 事件的完整清單，請參閱[Azure Active Directory 稽核報告事件](https://go.microsoft.com/fwlink/p/?LinkID=616549)。
    
- Exchange Online 稽核記錄檔包含兩種類型的事件： Exchange admin 事件 （系統管理員所採取的動作） 和信箱事件 （上信箱的使用者所採取的動作）。請注意預設未啟用信箱稽核。其必須之前信箱事件可以搜尋的 Office 365 稽核記錄中的每個使用者信箱啟用。如需信箱稽核及信箱稽核記錄的動作的詳細資訊，請參閱[啟用信箱稽核 Office 365 中](enable-mailbox-auditing.md)。
    
- 預設未啟用的 Power BI 稽核記錄。若要搜尋的 Office 365 稽核記錄中的 Power BI 活動，您必須啟用 [Power BI 系統入口網站中的稽核。指示，請參閱[稽核 Power BI](https://docs.microsoft.com/power-bi/service-admin-auditing#enabling-auditing-functionality-in-the-power-bi-admin-portal)。
    
    
## <a name="search-the-audit-log"></a>搜尋稽核記錄

以下是在 Office 365 中搜尋稽核記錄的程序。
  
[步驟 1： 執行稽核記錄搜尋](#step-1-run-an-audit-log-search)
  
[步驟 2： 檢視搜尋結果](#step-2-view-the-search-results)

[步驟 3： 篩選搜尋結果](#step-3-filter-the-search-results)

[步驟 4： 將搜尋結果匯出至檔案](#step-4-export-the-search-results-to-a-file)
  
### <a name="step-1-run-an-audit-log-search"></a>步驟 1： 執行稽核記錄搜尋

1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
    > [!TIP]
    > 使用私用的瀏覽工作階段 （不正常工作階段） 來存取 Office 365 安全性&amp;規範中心因為如此將會防止您目前登入與從正在使用的認證。若要開啟 [InPrivate 瀏覽工作階段在 Internet Explorer 或 Microsoft Edge，只是按 CTRL + SHIFT + P。若要開啟私用的瀏覽工作階段中 Google Chrome （稱為 incognito 視窗），請按 CTRL + SHIFT + N。 
  
2. 登入 Office 365 中，使用您工作或學校的帳戶。
    
3. 在 [安全性] 的左窗格中&amp;規範中心按一下**搜尋&amp;調查**，然後按一下 [**稽核記錄搜尋**。
    
    會顯示 [**稽核記錄搜尋**] 頁面。 
    
    ![設定準則，然後按一下 [搜尋] 執行報告](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
    > [!NOTE]
    > 您必須在稽核記錄，才可執行的稽核記錄搜尋的第一個開啟。如果顯示 [**開始錄製使用者和系統活動**] 連結時，請按一下它便開啟稽核功能。如果您沒有看到此連結，稽核已經已開啟您的組織。 
  
4. 設定下列搜尋準則：
    
1. **活動**按一下下拉式清單以顯示您可以搜尋的活動。使用者和系統活動編組成群組相關的活動。您可以選取特定的活動或您可以按一下 [選取群組中的所有活動的活動群組名稱。您也可以按一下 [清除選取項目所選的活動。執行搜尋之後，會顯示只選取活動的稽核記錄項目。選取 [**顯示所有的活動的結果**會顯示所選的使用者或使用者群組所執行的所有活動的結果。 
    
    超過 100 的使用者和系統活動會記錄在 Office 365 稽核記錄檔。按一下 [在本篇文章以查看每個不同的 Office 365 服務中的每個活動的說明主題**Audited 活動**] 索引標籤。 
    
2. 預設會選取**開始日期**和**結束日期**過去 7 天。選取以顯示該期間內發生之事件的日期和時間範圍。以國際標準時間 (UTC) 格式所呈現的日期和時間。您可以指定的最大的日期範圍為 90 天。如果選取的日期範圍大於 90 天會顯示錯誤。 
    
    > [!TIP]
    > 如果您使用 90 天的最大的日期範圍、 選取目前時間的**開始日期**。否則，您會收到的錯誤說明的開始日期早於結束日期。如果您已開啟稽核過去 90 天內，最大的日期範圍無法啟動之前已開啟稽核的日期。 
  
3. **使用者**在此方塊中按一下，然後選取 [顯示搜尋結果的一或多個使用者。選取您在此方塊中選取的使用者所執行的活動的稽核記錄項目所顯示的結果清單中。保留此方塊空白以傳回組織中的所有使用者 （及服務帳戶） 的項目。 
    
4. **檔案或資料夾**輸入某些或所有搜尋資料夾包含指定之的關鍵字的檔案相關的活動的檔案或資料夾名稱。您也可以指定的檔案或資料夾的 URL。如果您使用的 URL，請確定此類型的完整的 URL 路徑或如果您只需要輸入 URL 部分不會包含任何特殊字元或空格。 
    
    保留此方塊空白以傳回組織中的所有檔案及資料夾的項目。
    
5. 按一下 [**搜尋**來執行使用搜尋準則的 [搜尋]。 
    
    會載入搜尋結果，並在幾分鐘之後他們的顯示在 [**結果**。搜尋完成時，會顯示找到的結果數目。請注意將會以遞增 150 事件 ； 中的 [**結果**] 窗格中顯示最大值為 5000 個事件如果超過 5000 筆事件符合搜尋準則，則會顯示最近的 5000 個事件。 
    
    ![顯示搜尋完畢後的結果數](media/986216f1-ca2f-4747-9480-e232b5bf094c.png)
  
  
#### <a name="tips-for-searching-the-audit-log"></a>搜尋稽核記錄的秘訣

- 您可以選取活動名稱上按一下 [搜尋特定的活動。或您可搜尋的所有活動 （如**檔案及資料夾的活動**） 群組中按一下群組名稱。如果已選取 [活動，您可以按一下它取消選取項目。您也可以使用 [搜尋] 方塊中顯示含有您所輸入關鍵字的活動。
    
    ![按一下以選取所有的活動的活動群組名稱](media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)
  
- 您必須以顯示從 Exchange 管理員稽核記錄的事件**活動**清單中選取 [**顯示所有的活動的結果**。從這個稽核記錄的事件結果中的 [**活動**] 欄中顯示的指令程式名稱 （例如**Set-mailbox** ）。如需詳細資訊，本主題中的 [ **Audited 活動**] 索引標籤和 [ **Exchange 系統活動**。
    
    同樣地，有一些稽核活動**活動**清單中沒有對應的項目。如果您知道這些活動的作業的名稱，您可以搜尋所有的活動，然後輸入作業的名稱] 方塊中的 [**活動**] 欄來篩選結果。請參閱[步驟 3： 篩選搜尋結果](#step-3-filter-the-search-results)的篩選結果的詳細資訊。 
    
- 按一下 [**清除**來清除目前的搜尋準則。日期範圍會傳回預設的過去 7 天。您也可以按一下 [取消所有選取的活動**清除所有以顯示所有的活動的結果**。 
    
- 如果找到 5000 筆結果可能可以假設有超過 5000 筆符合搜尋準則的事件。您可以調整的搜尋準則並重新執行搜尋以返回較少的結果，或將所有的搜尋結果匯出選取 [**匯出結果** \> **下載所有結果**。

  
### <a name="step-2-view-the-search-results"></a>步驟 2： 檢視搜尋結果

稽核記錄搜尋結果會顯示 [**結果**在**稽核記錄檔**] 頁面上。如先前所述以遞增 150 事件中顯示最大值為 5000 個 （最新） 的事件。若要顯示多個事件您可以使用捲軸列在 [**結果**] 窗格中或您可以按**Shift + End**顯示下一步] 150 事件。 
  
結果包含下列搜尋傳回的每個事件的相關資訊。
  
- **日期：** 日期和時間 （UTC 格式） 事件發生的時間。 
    
- **IP 位址：** 活動已記錄時使用的裝置 IP 位址。IP 位址是 IPv4 或 IPv6 地址格式顯示。 
    
- **使用者：** 使用者 （或服務帳戶） 誰執行觸發事件的動作。 
    
- **活動：** 使用者執行活動。此值會對應至您在 [**活動**] 下拉式清單中選取的活動。從 Exchange 管理員稽核記錄的事件，此資料行中的值會是 Exchange cmdlet。 
    
- **項目：** 已建立或修改因為相對應的活動的物件。例如，已檢視或修改的檔案或已更新的使用者帳戶。並非所有的活動具有此欄中的值。 
    
- **詳細資料：** 其他活動的詳細資訊。同樣地，不是所有的活動都有值。 
    
> [!TIP]
> 按一下欄標題底下來排序結果的**結果**。您可以排序結果從 A 到 Z 或 Z A 按一下**日期**欄位名稱來排序結果的最早為最新或最新到最舊。 
  
#### <a name="view-the-details-for-a-specific-event"></a>檢視特定事件的詳細資料

您可以依序按一下 [搜尋結果的清單中的事件記錄檢視某個事件有關的詳細資訊。**詳細資料**] 頁面會顯示包含從事件記錄的詳細的屬性。顯示的內容取決於 Office 365 服務中發生此事件。若要顯示這些詳細資訊，請按一下 [**詳細資訊**。如需說明，請參閱[Office 365 中的詳細的內容稽核記錄](detailed-properties-in-the-office-365-audit-log.md)。
  
![按一下 [檢視稽核記錄的事件記錄的詳細的屬性的詳細資訊](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

  
### <a name="step-3-filter-the-search-results"></a>步驟 3： 篩選搜尋結果

除了排序，您也可以篩選的稽核記錄搜尋的結果。這是更好的功能可協助您快速篩選特定使用者或活動的結果。您可以開始建立寬搜尋和快速篩選結果，以查看特定的事件。然後您可縮小範圍的搜尋準則並重新執行搜尋以返回較小、 比較簡明結果集。
  
若要篩選結果：
  
1. 執行稽核記錄搜尋。
    
2. 時所顯示的結果，按一下 [**篩選結果**。
    
    關鍵字] 方塊會顯示每個資料行標題底下。
    
3. 按一下欄標題下的其中一個方塊，輸入的單字或片語，視您要篩選的資料行。結果會以動態方式重新調整以顯示符合您的篩選器的事件。
    
    ![顯示符合篩選事件的篩選器中輸入一個字](media/542dc323-a997-402c-934b-cc5e218e50bc.png)
  
4. 若要清除篩選，請按一下 [篩選] 方塊中的**X**或只要按一下 [**隱藏篩選**。
    
> [!TIP]
> 若要顯示從 Exchange 管理員稽核記錄的事件，請輸入**-**（虛線）**活動**篩選] 方塊中。這會顯示的 Exchange 系統事件的 [**活動**] 欄中顯示的指令程式名稱。然後您可以排序依字母順序排列的 cmdlet 名稱。 

### <a name="step-4-export-the-search-results-to-a-file"></a>步驟 4： 將搜尋結果匯出至檔案

您可以將稽核記錄搜尋結果匯出至本機電腦上逗點分隔的值 (CSV) 檔案。您可以在 Microsoft Excel 中開啟此檔案並使用功能，例如搜尋、 排序、 篩選和分割單一欄 （其中包含多重值的儲存格） 到多個資料欄。
  
1. 執行稽核記錄搜尋，並再修改搜尋準則直到您有想要的結果。
    
2. 按一下 [**匯出結果**並選取下列選項之一： 
    
  - **儲存載入結果**選擇此選項可匯出的 [**結果**顯示的項目 * * 稽核記錄搜尋 * *] 頁面。已下載的 CSV 檔案包含相同資料行 （和資料） 顯示在頁面 （日期、 使用者、 活動、 項目及詳細資料）。額外一欄 （名為**多個**） 隨附於包含稽核記錄項目中的詳細資訊的 CSV 檔案。因為您要匯出相同的結果所載入 （及檢視） 的**稽核記錄搜尋**頁面上，都要匯出的最大值為 5000 項目。 
    
  - **下載所有結果**選擇此選項可從符合搜尋準則的 Office 365 稽核記錄中匯出所有的項目。搜尋結果的一大組，選擇此選項除了可以**稽核記錄搜尋**頁顯示 5000 筆結果的稽核記錄檔從下載所有項目。這個選項會下載從稽核記錄的原始資料至 CSV 檔案，並包含名為**AuditData**] 欄中的稽核記錄項目中的其他資訊。可能需要更久，如果您選擇這個匯出選項因為檔案可能會更加大於會下載如果您選擇其他選項的下載檔案。
    
    > [!IMPORTANT]
    > 您可以下載到 CSV 檔案的最大值為 50000 項目從單一的稽核記錄搜尋。如果 50000 項目會下載到 CSV 檔案，您可能可以假設有超過 50000 個符合搜尋準則的事件。若要匯出超過此限制，嘗試使用日期範圍減少的稽核記錄項目數目。您可能必須執行多個搜尋與較小的日期範圍中匯出 50000 個以上的項目。 
  
3. 選取 [匯出] 選項後，會提示您 CSV 檔案開啟、 將其儲存至 [下載項目] 資料夾中，或將其儲存至特定資料夾視窗底部顯示訊息。

  
#### <a name="more-information-about-exporting-audit-log-search-results"></a>匯出稽核記錄搜尋結果的詳細資訊

- **下載所有結果**] 選項會下載到 CSV 檔案從 Office 365 稽核記錄的原始資料。這個檔案包含不同的資料行名稱 （CreationDate、 UserIds、 作業、 AuditData） 比如果您選取 [**儲存] 載入結果**] 選項已下載的檔案。在相同的活動的兩個不同 CSV 檔案中的值也可能不同。例如，csv 檔案中的 [**動作**] 欄中的活動檔案且可能會有不同的值大於**稽核記錄搜尋**頁面 ； 上的 [**活動**] 欄中會顯示"易記"版本例如，MailboxLogin 相對於使用者登入至信箱。
    
- 如果您下載所有結果、 CSV 檔案會包含名為**AuditData**，其中包含每個事件的其他資訊的欄。先前所述，此資料行包含多個屬性的稽核記錄的記錄從多重值屬性。每個成對此多重值屬性中的**屬性： 值**是以逗號分隔。您可以使用 Excel 中的 Power 查詢此資料行分割成多個資料欄，，讓每個屬性將有其專屬資料行。這可讓您排序及篩選一或多個這些屬性。了解如何執行這項作業，請參閱"分割資料行來分隔字元"一節中[分割資料行的文字 （進階查詢）](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662)。
    
    分割**AuditData**欄之後，您可以當做篩選依據以顯示特定類型的活動的詳細的內容的 [**作業**] 欄。 
    
- 沒有 3,060 字元的限制的稽核記錄的**AuditData**欄位中所顯示的資料。如果超過 3,060 字元限制，此欄位中的資料會無條件捨去。 
    
- 當您從包含事件從不同 Office 365 服務搜尋查詢下載所有結果時、 **AuditData**欄 CSV 檔案中的包含根據服務動作所執行的不同屬性。例如，從 Exchange 和 Azure AD 的稽核記錄項目包含名為**ResultStatus**指出動作如果已成功屬性。此屬性不包含在 SharePoint 中的事件。同樣地，SharePoint 事件沒有屬性識別的網站 URL 的檔案與資料夾相關的活動。若要降低此表現方式，請考慮使用不同的搜尋活動的結果匯出單一服務。 
    
    當您下載所有結果，以及服務每一個 CSV 檔案中的 [ **AuditData** ] 欄中所列的屬性描述一套用於，請參閱[Office 365 中的詳細的內容稽核記錄](detailed-properties-in-the-office-365-audit-log.md)。

  
## <a name="audited-activities"></a>稽核的活動

本節中的表格說明 Office 365 中您可以稽核的活動。您可以搜尋的安全性將這些事件來搜尋稽核記錄&amp;規範中心。按一下 [**搜尋稽核記錄**] 索引標籤的逐步指示。 
  
這些表格群組相關的活動] 或 [從特定的 Office 365 服務活動。表格包含顯示在 [**活動**] 下拉式清單中的易記名稱和對應作業時匯出搜尋結果出現在稽核記錄的詳細資訊及 CSV 檔案的名稱。如需詳細資訊的說明，請參閱[Office 365 中的詳細的內容稽核記錄](detailed-properties-in-the-office-365-audit-log.md)。
  
按一下下列連結，即可移至特定資料表的其中一個。
  
||||
|:-----|:-----|:-----|
|[檔案及] 頁面上的活動](#file-and-page-activities)<br/> |[資料夾的活動](#folder-activities)<br/> |[共用和存取要求活動](#sharing-and-access-request-activities)<br/> |
|[同步處理活動](#synchronization-activities)<br/> |[網站管理活動](#site-administration-activities)<br/> |[Exchange 信箱的活動](#exchange-mailbox-activities)<br/> |
|[Sway 活動](#sway-activities) <br/> |[使用者管理活動](#user-administration-activities) <br/> |[Azure AD 群組管理活動](#azure-ad-group-administration-activities) <br/> |
|[應用程式管理活動](#application-administration-activities) <br/> |[角色管理活動](#role-administration-activities) <br/> |[目錄管理活動](#directory-administration-activities) <br/> |
|[eDiscovery 活動](#ediscovery-activities) <br/> |[Power BI 活動](#power-bi-activities) <br/> |[Microsoft 小組活動](#microsoft-teams-activities) <br/> |
|[Yammer 活動](#yammer-activities) <br/> |[Microsoft Stream](#microsoft-stream) <br/> |[Exchange 管理員稽核記錄](#exchange-admin-audit-log) <br/> |
   
  
### <a name="file-and-page-activities"></a>檔案及] 頁面上的活動
  
下表說明 SharePoint Online 和 OneDrive for Business 檔案和] 頁面上的活動。
  
|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|存取過之檔案  <br/> |FileAccessed  <br/> |使用者或系統帳戶存取檔案。  <br/> |
|（無）  <br/> |FileAccessedExtended  <br/> |這與相關"存取檔案"(FileAccessed) 活動。FileAccessedExtended 事件會記錄時的相同的人員需要經常存取檔案的一段時間 （最多 3 小時）。記錄 FileAccessedExtended 事件的目的是以減少需要經常存取檔案時所登入 FileAccessed 事件的次數。這有助於減少雜訊的什麼基本上是相同的多個 FileAccessed 記錄的使用者活動與可讓您焦點放在初始 （及更重要） FileAccessed 事件。  <br/> |
|存回檔案  <br/> |FileCheckedIn  <br/> |使用者存回其文件庫中取出的文件。  <br/> |
|取出的檔案  <br/> |FileCheckedOut  <br/> |使用者取出的文件庫中的文件。使用者可以取出並對它們與已共用的文件進行變更。  <br/> |
|複製的檔案  <br/> |FileCopied  <br/> |使用者會複製網站中的文件。複製之檔案可以儲存在網站上的另一個資料夾。  <br/> |
|已刪除的檔案  <br/> |FileDeleted  <br/> |使用者從網站刪除文件。  <br/> |
|資源回收筒中已刪除的檔案  <br/> |FileDeletedFirstStageRecycleBin  <br/> |使用者會從網站資源回收筒中刪除檔案。  <br/> |
|第二階段資源回收筒中已刪除的檔案  <br/> |FileDeletedSecondStageRecycleBin  <br/> |使用者網站的第二階段資源回收筒中刪除檔案。  <br/> |
|在檔案中偵測到惡意程式碼  <br/> |FileMalwareDetected  <br/> |SharePoint 的防毒引擎偵測惡意程式碼檔案中。  <br/> |
|捨棄的檔案取出  <br/> |FileCheckOutDiscarded  <br/> |使用者捨棄 (或復原) 取出的檔案。這表示對取出的文件所做的任何變更會被捨棄，不儲存到文件庫中的文件版本。  <br/> |
|下載的檔案  <br/> |FileDownloaded  <br/> |使用者從網站下載文件。  <br/> |
|修改的檔案  <br/> |FileModified  <br/> |使用者或系統帳戶修改內容或網站上的文件的屬性。  <br/> |
|（無）  <br/> |FileModifiedExtended  <br/> |這相關的"Modified 檔案 」 (FileModified) 活動。FileModifiedExtended 事件會記錄時同一人士持續修改檔案的一段時間 （最多 3 小時）。記錄 FileModifiedExtended 事件的目的是以減少持續修改檔案時所登入 FileModified 事件的次數。這有助於減少雜訊的什麼基本上是相同的多個 FileModified 記錄的使用者活動與可讓您焦點放在初始 （及更重要） FileModified 事件。  <br/> |
|移動的檔案  <br/> |FileMoved  <br/> |使用者會在網站上從其目前的位置在文件移至新位置。  <br/> |
|回收所有的次要版本的檔案  <br/> |FileVersionsAllMinorsRecycled  <br/> |使用者會從檔案之版本歷程記錄刪除所有的次要版本。刪除的版本會移至網站資源回收筒。  <br/> |
|回收所有版本的檔案  <br/> |FileVersionsAllRecycled  <br/> |使用者會刪除檔案之版本歷程記錄中的所有版本。刪除的版本會移至網站資源回收筒。  <br/> |
|回收的版本的檔案  <br/> |FileVersionRecycled  <br/> |使用者會刪除檔案之版本歷程記錄中的版本。刪除的版本移至網站資源回收筒。  <br/> |
|重新命名的檔案  <br/> |FileRenamed  <br/> |使用者會重新命名網站上的文件。  <br/> |
|還原的檔案  <br/> |FileRestored  <br/> |使用者從網站資源回收筒還原文件。  <br/> |
|上傳的檔案  <br/> |FileUploaded  <br/> |使用者將文件上傳至網站上的資料夾。  <br/> |
|檢視的頁面  <br/> |PageViewed  <br/> |使用者檢視網站頁面。這不包括使用網頁瀏覽器中檢視中的文件庫的檔案。  <br/> |
|（無）  <br/> |PageViewedExtended  <br/> |這與相關"Viewed 頁面 」 (PageViewed) 活動。PageViewedExtended 事件會記錄時同一人士持續檢視網頁的一段時間 （最多 3 小時）。記錄 PageViewedExtended 事件的目的是以減少需要經常檢視頁面時所登入 PageViewed 事件的次數。這有助於減少雜訊的什麼基本上是相同的多個 PageViewed 記錄的使用者活動與可讓您焦點放在初始 （及更重要） PageViewed 事件。  <br/> |
  
### <a name="folder-activities"></a>資料夾的活動
  
下表說明在 SharePoint Online 和 OneDrive for Business 的資料夾活動。
  
|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|複製的資料夾  <br/> |FolderCopied  <br/> |使用者會從網站中資料夾複製到 SharePoint 或 OneDrive for Business 的另一個位置。  <br/> |
|建立的資料夾  <br/> |FolderCreated  <br/> |使用者會在網站上建立資料夾。  <br/> |
|刪除的郵件] 資料夾  <br/> |FolderDeleted  <br/> |使用者會從網站刪除資料夾。  <br/> |
|資源回收筒中刪除的郵件資料夾  <br/> |FolderDeletedFirstStageRecycleBin  <br/> |使用者會刪除在網站上的資源回收筒中的資料夾。  <br/> |
|第二階段資源回收筒中刪除的郵件資料夾  <br/> |FolderDeletedSecondStageRecycleBin  <br/> |使用者會刪除在網站上的第二階段資源回收筒中的資料夾。  <br/> |
|已修改的資料夾  <br/> |FolderModified  <br/> |使用者會修改站台上的資料夾。這包含變更資料夾中繼資料，例如變更標記和屬性。  <br/> |
|移動的資料夾  <br/> |FolderMoved  <br/> |使用者在網站上將資料夾移至不同的位置。  <br/> |
|重新命名的資料夾  <br/> |FolderRenamed  <br/> |使用者會重新命名網站上的資料夾。  <br/> |
|還原的資料夾  <br/> |FolderRestored  <br/> |使用者從網站上的資源回收筒還原刪除的郵件] 資料夾。  <br/> |
  
### <a name="sharing-and-access-request-activities"></a>共用和存取要求活動
  
下表說明在 SharePoint Online 和 OneDrive for Business 的使用者共用和存取要求活動。共用事件，在**結果**] 下的 [**詳細資料**] 欄會識別的使用者或群組與已共用的項目名稱且是否使用者或群組的成員或組織中的來賓。如需詳細資訊，請參閱[使用共用的 Office 365 稽核記錄中的稽核](use-sharing-auditing.md)。
  
> [!NOTE]
> 使用者可以是 [*成員*] 或 [ *guests*根據使用者物件的 UserType 屬性。成員通常是員工、 和來賓通常是組織外的 collaborator。當使用者接受共用邀請 （和並非在貴組織的一部分） 時，就會為這些 guest 帳戶建立您的組織目錄中。一旦來賓使用者您的目錄中有帳戶，資源可能會直接與共用 （而不需要邀請）。 
  
|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|接受存取要求  <br/> |AccessRequestAccepted  <br/> |網站、 資料夾或文件存取要求被接受並要求使用者授與存取權。  <br/> |
|接受共用邀請  <br/> |SharingInvitationAccepted  <br/> |使用者 （成員或來賓） 接受共用邀請並已授與存取資源。此事件會包含 （它們可能會不同） 獲邀使用者與用來接受邀請電子郵件地址的相關資訊。此活動通常被伴隨著說明如何已授與使用者存取的資源，例如將使用者新增至群組有權存取資源在第二個事件。  <br/> |
|網站集合已新增的權限層級  <br/> |PermissionLevelAdded  <br/> |權限等級已新增至網站集合。  <br/> |
|使用者新增至安全連結  <br/> |AddedToSecureLink  <br/> |使用者已新增到實體可以使用此安全的共用連結清單。  <br/> |
|封鎖的共用邀請  <br/> |SharingInvitationBlocked  <br/> | 在組織中使用者所傳送的共用邀請因外部的共用原則的 [允許] 或 [拒絕外部共用之目標使用者的網域為基礎而封鎖。在此例中共用邀請，所以封鎖：<br/>  目標使用者的網域不包含在允許網域清單中。  <br/>  或  <br/>  目標使用者的網域已包含在封鎖網域清單中。  <br/>  如需允許或封鎖外部共用網域為基礎的詳細資訊，請參閱[限制在 SharePoint Online 和 OneDrive for Business 中共用的網域](https://support.office.com/article/5d7589cd-0997-4a00-a2ba-2320ec49c4e9)。  <br/> |
|中斷權限層級繼承  <br/> |PermissionLevelsInheritanceBroken  <br/> |使其不再是繼承的權限層級與其父系，已變更的項目。  <br/> |
|中斷共用繼承  <br/> |SharingInheritanceBroken  <br/> |使其不再從其父代繼承共用權限已變更的項目。  <br/> |
|建立公司可共用連結  <br/> |CompanyLinkCreated  <br/> |使用者建立的資源的全公司的連結。在組織中的成員僅可使用全公司的連結。他們無法使用來賓。  <br/> |
|建立存取要求  <br/> |AccessRequestCreated  <br/> |使用者要求存取網站、 資料夾或文件沒有存取權限。  <br/> |
|建立匿名的連結  <br/> |AnonymousLinkCreated  <br/> |使用者建立的資源匿名連結。使用此連結的任何人都可以存取資源而不需要進行驗證。  <br/> |
|建立安全連結  <br/> |SecureLinkCreated  <br/> |建立安全的共用連結到這個項目。  <br/> |
|建立共用邀請  <br/> |SharingInvitationCreated  <br/> |不在貴組織的目錄中的使用者與使用者共用的 SharePoint Online 或 OneDrive for Business 中的資源。  <br/> |
|已刪除的安全連結  <br/> |SecureLinkDeleted  <br/> |已刪除的安全共用的連結。  <br/> |
|拒絕存取要求  <br/> |AccessRequestDenied  <br/> |拒絕網站、 資料夾或文件存取要求。  <br/> |
|網站集合上的修改後的權限層級  <br/> |PermissionLevelModified  <br/> |權限等級已變更網站集合上。  <br/> |
|移除公司可共用連結  <br/> |CompanyLinkRemoved  <br/> |使用者移除資源的全公司的連結。連結不再可用來存取資源。  <br/> |
|移除匿名的連結  <br/> |AnonymousLinkRemoved  <br/> |使用者移除資源匿名連結。連結不再可用來存取資源。  <br/> |
|從網站集合中移除權限層級  <br/> |PermissionLevelRemoved  <br/> |從網站集合移除電腦權限等級。  <br/> |
|還原共用繼承  <br/> |SharingInheritanceReset  <br/> |使項目是共用的權限繼承其父項進行變更。  <br/> |
|共用的檔案、 資料夾或網站  <br/> |SharingSet  <br/> |使用者 （成員或來賓） 共用檔案、 資料夾或 SharePoint 或 OneDrive for Business 中的網站與您的組織目錄中的使用者。此活動的 [**詳細資料**] 欄中的值會識別與已共用資源的使用者和這位使用者為成員或來賓的名稱。此活動通常被伴隨著說明如何已授與使用者存取的資源，在第二個事件例如，將使用者新增至群組有權存取資源。<br/> |
|更新的存取要求  <br/> |AccessRequestUpdated  <br/> |已更新的項目存取要求。  <br/> |
|更新匿名的連結  <br/> |AnonymousLinkUpdated  <br/> |使用者更新資源匿名的連結。更新的欄位隨附 EventData 屬性中匯出搜尋結果。  <br/> |
|更新共用邀請  <br/> |SharingInvitationUpdated  <br/> |已更新外部的共用邀請。  <br/> |
|使用匿名的連結  <br/> |AnonymousLinkUsed  <br/> |匿名使用者存取的資源使用匿名] 連結。使用者身分識別可能是未知的但是您可以取得使用者的 IP 位址等其他詳細資料。  <br/> |
|取消共用的檔案、 資料夾或網站  <br/> |SharingRevoked  <br/> |使用者 （成員或來賓） 不共用檔案、 資料夾或先前已與另一位使用者共用的網站。  <br/> |
|使用公司可共用連結  <br/> |CompanyLinkUsed  <br/> |使用者使用全公司的連結存取資源。  <br/> |
|使用安全連結  <br/> |SecureLinkUsed  <br/> |使用者所使用的安全連結。  <br/> |
|使用者新增至安全連結  <br/> |AddedToSecureLink  <br/> |使用者已新增到實體可以使用共用的安全連結清單。  <br/> |
|從安全連結中移除的使用者  <br/> |RemovedFromSecureLink  <br/> |使用者已從實體可以使用共用的安全連結清單移除。  <br/> |
|拖共用邀請  <br/> |SharingInvitationRevoked  <br/> |使用者拖至資源共用邀請。  <br/> |
  
### <a name="synchronization-activities"></a>同步處理活動
  
下表列出 SharePoint Online 和 OneDrive for Business 檔案同步處理活動。
  
|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|允許同步處理檔案的電腦  <br/> |ManagedSyncClientAllowed  <br/> |使用者已成功建立與站台的同步處理關係。因為使用者的電腦已新增至網域 （稱為 「*安全的收件者清單*） 可以存取您組織中的文件庫清單中的網域的成員，已成功的同步處理關係。<br/> 如需此功能的詳細資訊，請參閱 ＜ [Use Windows PowerShell cmdlet 來啟用 OneDrive 同步處理會在 [安全的收件者] 清單上的網域](https://go.microsoft.com/fwlink/p/?LinkID=534609)。  <br/> |
|封鎖從次檔案的電腦  <br/> |UnmanagedSyncClientBlocked  <br/> |使用者嘗試建立的網站不是組織的網域的成員電腦同步處理關係或是尚未新增至網域清單中的某個網域的成員 (稱為*安全的收件者清單)* 的可存取文件在組織中的文件庫。不允許同步處理關係、 及使用者的電腦會封鎖從次、 下載、 或上傳文件庫上的檔案。<br/> 這項功能的相關資訊，請參閱[Use Windows PowerShell cmdlet 來啟用 OneDrive 同步處理會在 [安全的收件者] 清單上的網域](https://go.microsoft.com/fwlink/p/?LinkID=534609)。  <br/> |
|下載的檔案的電腦  <br/> |FileSyncDownloadedFull  <br/> |使用者會建立的同步處理關係與成功文件庫中下載第一次至其電腦的檔案。  <br/> |
|下載的檔案變更電腦  <br/> |FileSyncDownloadedPartial  <br/> |使用者已順利會下載至檔案的任何變更文件庫中。這項活動會指出文件庫中的檔案所做的任何變更已下載到使用者的電腦。只有變更已下載因為 （如以**下載到電腦檔案**活動） 先前的文件庫下載使用者。<br/> |
|上傳的檔案至文件庫  <br/> |FileSyncUploadedFull  <br/> |使用者會建立的同步處理關係，並已順利將檔案上傳至文件庫第一次從其電腦。  <br/> |
|將變更上傳的檔案至文件庫  <br/> |FileSyncUploadedPartial  <br/> |使用者已順利將變更上載的文件庫上的檔案。此事件會指出文件庫中做為檔案的本機版本的任何變更會成功上傳至文件庫。僅卸載變更是因為這些檔案先前由使用者上傳 (所指示 * * 上傳檔案至文件庫 * * 活動)。  <br/> |
  
### <a name="site-administration-activities"></a>網站管理活動
  
下表列出的事件所產生的 SharePoint Online 中的網站管理工作。
  
|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|新增免除使用者代理程式  <br/> |ExemptUserAgentSet  <br/> |為 SharePoint 或全域管理員新增的使用者代理程式在 SharePoint 系統管理中心免除使用者代理程式的清單。  <br/> |
|新增的網站集合管理員  <br/> |SiteCollectionAdminAdded  <br/> |網站集合管理員或擁有者會新增個人網站之網站集合管理員。網站集合管理員擁有網站集合及所有子網站的完全控制權限。  <br/> |
|新增的使用者或群組至 SharePoint 群組  <br/> |AddedToGroup  <br/> |使用者會新增至 SharePoint 群組的成員或來賓。這可能已刻意的動作或另一項活動，如共用的事件的結果。  <br/> |
|允許使用者建立群組  <br/> |AllowGroupCreationSet  <br/> |網站管理員或擁有者會新增至網站，可讓使用者權限等級指派該權限來建立該網站群組。  <br/> |
|取消的網站地理位置移動  <br/> |SiteGeoMoveCancelled  <br/> |為 SharePoint 或全域管理員成功會取消 SharePoint 或 OneDrive 網站地理位置移動。多個地理位置功能可讓跨越多個 Office 365 datacenter 地理位置，稱為 geos Office 365 組織。如需詳細資訊，請參閱[OneDrive 和 SharePoint Online 中的 Office 365 的多重地理位置功能](https://go.microsoft.com/fwlink/?linkid=860840)。<br/> |
|變更共用原則  <br/> |SharingPolicyChanged  <br/> |為 SharePoint 或全域管理員變更 SharePoint 使用的 Office 365 系統管理入口網站、 SharePoint 管理入口網站或 SharePoint Online 管理命令介面來共用原則。在組織中的共用原則中設定的任何變更都會記錄。在事件記錄的詳細內容**ModifiedProperties** ] 欄位中所識別已變更的原則。<br/> |
|變更裝置存取原則  <br/> |DeviceAccessPolicyChanged  <br/> |在 SharePoint 或全域管理員變更您的組織未受管理的裝置原則。此原則會控制存取 SharePoint、 OneDrive 及 Office 365 中的未加入至您的組織的裝置。設定此原則需要企業行動性 + 安全性訂閱。如需詳細資訊，請參閱[控制存取來自未受管理的裝置](https://support.office.com/article/5ae550c4-bd20-4257-847b-5c20fb053622)。<br/> |
|變更免除使用者代理程式  <br/> |CustomizeExemptUsers  <br/> |為 SharePoint 或全域管理員自訂免除使用者代理程式在 SharePoint 管理中心內的清單。您可以指定哪些使用者代理程式免除接收到索引將整個網頁。這表示您已指定為免除遇到 InfoPath 表單的使用者代理程式時，表單將會傳回為 XML 檔案，而不是將整個網頁。這會使索引的 InfoPath 表單得更快。  <br/> |
|變更網路存取原則  <br/> |NetworkAccessPolicyChanged  <br/> |在 SharePoint 或全域管理員變更 （也稱為 「 信任的網路界限） [SharePoint 系統管理中心或使用 SharePoint Online PowerShell 以位置為主的存取原則。此類型的成員可存取組織根據您指定的授權 IP 位址範圍中的 SharePoint 和 OneDrive 資源原則控制項。如需詳細資訊，請參閱[控制存取 SharePoint Online 和 OneDrive 資料根據網路位置](https://support.office.com/article/b5a5f1f1-1174-4c6b-91d0-9273a6b6971f)。<br/> |
|已完成的站台地理位置移動  <br/> |SiteGeoMoveCompleted  <br/> |使用您的組織中的全域管理員已排定的網站地理位置移動已順利完成。多個地理位置功能可讓跨越多個 Office 365 datacenter 地理位置，稱為 geos Office 365 組織。如需詳細資訊，請參閱[OneDrive 和 SharePoint Online 中的 Office 365 的多重地理位置功能](https://go.microsoft.com/fwlink/?linkid=860840)。<br/> |
|建立的群組  <br/> |GroupAdded  <br/> |網站管理員或擁有者建立網站、 群組或執行工作的結果中所建立的群組。例如，第一次使用者建立共用檔案的連結，系統群組新增至使用者的 OneDrive for Business 網站。此事件也可以建立與連結的使用者結果編輯共用檔案的權限。  <br/> |
|建立的傳送至連線  <br/> |SendToConnectionAdded  <br/> |SharePoint 或全域管理員會在 SharePoint 管理中心的記錄管理] 頁面上建立新的傳送至連線。傳送至連線指定文件存放庫或記錄中心的設定。當您建立的傳送至連線時、 內容組合管理可以送出至指定的位置的文件。  <br/> |
|建立的網站集合  <br/> |SiteCollectionCreated  <br/> |SharePoint 或全域管理員會在您的 SharePoint Online 組織中建立新的網站集合或使用者佈建其 OneDrive for Business 網站。  <br/> |
|已刪除的群組  <br/> |GroupRemoved  <br/> |使用者從網站刪除的群組。  <br/> |
|刪除的郵件傳送至連線  <br/> |SendToConnectionRemoved  <br/> |為 SharePoint 或全域管理員刪除傳送至連線在 SharePoint 管理中心的記錄管理] 頁面上。  <br/> |
|已刪除的網站  <br/> |SiteDeleted  <br/> |網站管理員刪除網站。  <br/> |
|啟用文件預覽  <br/> |PreviewModeEnabledSet  <br/> |網站管理員可讓網站的文件預覽。  <br/> |
|啟用舊版的工作流程  <br/> |LegacyWorkflowEnabledSet  <br/> |網站管理員或擁有者將 SharePoint 2013 工作流程工作內容類型新增至網站。全域管理員也可以在 SharePoint 系統管理中心啟用整個組織的工作流程。  <br/> |
|啟用的 Office on Demand  <br/> |OfficeOnDemandSet  <br/> |網站管理員可讓 Office on Demand，讓使用者可以存取最新版的 Office 桌面應用程式。Office on Demand 在 SharePoint 管理中心已啟用，且需要包含完整、 已安裝的 Office 應用程式的 Office 365 訂閱。  <br/> |
|已啟用的 RSS 摘要  <br/> |NewsFeedEnabledSet  <br/> |網站管理員或擁有者可讓網站的 RSS 摘要。全域管理員可以啟用整個組織在 SharePoint 管理中心的 RSS 摘要。  <br/> |
|已修改的存取權要求設定  <br/> |WebRequestAccessModified  <br/> |存取要求設定已修改在網站上。  <br/> |
|已修改的成員可以共用設定  <br/> |WebMembersCanShareModified  <br/> |**成員可以共用**設定已修改在網站上。  <br/> |
|修改的網站權限  <br/> |SitePermissionsModified  <br/> |網站管理員或擁有者 （或系統帳戶） 變更指派給網站上群組的權限層級。如果所有的權限會從群組移除，也會記錄此活動。<br/> > [!NOTE]> 在 SharePoint Online 中已被取代這項作業。若要尋找相關的事件，您可搜尋的其他權限相關活動等**已新增網站集合管理員**、**已新增使用者或群組至 SharePoint 群組**、**允許使用者建立群組**、**建立日期群組**及**Deleted群組。**         |
|從 SharePoint 群組移除使用者或群組  <br/> |RemovedFromGroup  <br/> |使用者會移除 SharePoint 群組的成員或來賓。這可能已刻意的動作或另一項活動，如取消事件的結果。  <br/> |
|重新命名的網站  <br/> |SiteRenamed  <br/> |網站管理員或擁有者重新命名網站  <br/> |
|要求的網站管理員權限  <br/> |SiteAdminChangeRequest  <br/> |若要新增為網站集合的網站集合管理員的使用者要求。網站集合管理員擁有網站集合及所有子網站的完全控制權限。  <br/> |
|已排程的站台地理位置移動  <br/> |SiteGeoMoveScheduled  <br/> |為 SharePoint 或全域管理員成功排程 SharePoint 或 OneDrive 網站地理位置移動。多個地理位置功能可讓跨越多個 Office 365 datacenter 地理位置，稱為 geos Office 365 組織。如需詳細資訊，請參閱[OneDrive 和 SharePoint Online 中的 Office 365 的多重地理位置功能](https://go.microsoft.com/fwlink/?linkid=860840)。<br/> |
|設定主機網站  <br/> |HostSiteSet  <br/> |SharePoint 或全域管理員變更指定架設個人網站或 OneDrive for Business 的網站。  <br/> |
|更新的群組  <br/> |GroupUpdated  <br/> |網站管理員或擁有者變更網站群組的設定。它可以包含變更群組的名稱、 可檢視或編輯群組成員資格及如何處理成員資格要求。  <br/> |
  
### <a name="exchange-mailbox-activities"></a>Exchange 信箱的活動
  
下表列出可以信箱所記錄的活動稽核記錄。信箱擁有者、 委派的使用者或系統管理員所執行的信箱活動的記錄。根據預設，Office 365 中的信箱稽核無法開啟。信箱稽核記錄必須開啟每一個信箱之前將記錄信箱活動。如需詳細資訊，請參閱[啟用信箱稽核 Office 365 中](https://go.microsoft.com/fwlink/p/?LinkID=626109)。
  
|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|新增的委派信箱權限  <br/> |新增 MailboxPermission  <br/> |系統管理員指派至另一個人信箱的 FullAccess 信箱權限給使用者 （又稱為代理人）。FullAccess 權限可讓代理人開啟其他人的信箱與讀取和管理信箱的內容。  <br/> |
|複製到另一個資料夾的郵件  <br/> |複製  <br/> |郵件已複製到另一個資料夾。  <br/> |
|建立的信箱項目  <br/> |建立  <br/> |在信箱 ； 中的 [行事曆、 連絡人、 備忘稿或工作] 資料夾中建立項目例如，會建立新的會議邀請。請注意不稽核建立、 傳送或接收郵件。此外，不稽核建立信箱資料夾。  <br/> |
|從 [刪除的郵件] 資料夾刪除的郵件  <br/> |SoftDelete  <br/> |已永久刪除或從 [刪除的郵件] 資料夾刪除郵件。這些項目會移至 [可復原的項目] 資料夾。當使用者選取它，並按下**Shift + Delete**，訊息也會移至 [可復原的項目] 資料夾。<br/> |
|移至另一個資料夾的郵件  <br/> |Move  <br/> |郵件已移到另一個資料夾。  <br/> |
|移至刪除的郵件] 資料夾的郵件  <br/> |MoveToDeletedItems  <br/> |郵件已遭刪除並移至 [刪除的郵件] 資料夾。  <br/> |
|已修改的資料夾權限  <br/> |UpdateFolderPermissions  <br/> |已變更的資料夾權限。在組織中的哪些使用者可存取信箱資料夾和資料夾中的郵件] 資料夾的權限控制項。  <br/> |
|從信箱清除的郵件  <br/> |HardDelete  <br/> |郵件已清除從 （永久刪除信箱） 的 [可復原的項目] 資料夾。  <br/> |
|已移除的委派信箱權限  <br/> |Remove-mailboxpermission  <br/> |系統管理員移除人員信箱的 FullAccess 權限 （也就指派給代理人）。移除的 FullAccess 權限後，代理人將無法開啟其他人的信箱或存取任何內容。  <br/> |
|傳送郵件使用下列傳送] 權限  <br/> |SendAs  <br/> |已使用 SendAs 權限傳送郵件。這表示，另一個使用者已傳送郵件，就像此郵件是來自信箱擁有者一樣。  <br/> |
|傳送郵件使用傳送代理者權限  <br/> |SendOnBehalf  <br/> |已使用 SendOnBehalf 權限傳送郵件。這表示，另一個使用者已代表信箱擁有者傳送郵件。此郵件會向收件者指示，此郵件是代表誰傳送，以及實際傳送郵件的人是誰。  <br/> |
|更新的代理人存取行事曆] 資料夾  <br/> |UpdateCalendarDelegation  <br/> |行事曆委派已指派給信箱。行事曆委派可讓其他人在相同的組織權限管理信箱擁有者的行事曆。  <br/> |
|更新的郵件  <br/> |更新  <br/> |郵件或其屬性已變更。  <br/> |
|使用者登入信箱  <br/> |MailboxLogin  <br/> |使用者已登入其信箱。  <br/> |
|（無）  <br/> |UpdateInboxRules  <br/> |收件匣規則已新增、 移除或變更。收件匣規則可用來處理郵件的收件匣根據指定的條件和符合規則的條件，例如將郵件移至指定的資料夾或刪除郵件時採取的動作。<br/> 若要傳回的收件匣規則活動項目，您必須選取 [**活動**] 清單中的 [**顯示所有的活動的結果**。使用 [日期範圍] 方塊和 [**使用者**] 清單來縮小搜尋結果。<br/> |
  
### <a name="sway-activities"></a>Sway 活動
  
下表列出 Sway 中的使用者和系統活動。Sway 是可協助使用者收集、 格式化及分享構思、 stories、 與簡報互動式、 web 式畫布上的 Office 365 應用程式。如需詳細資訊，請參閱 ＜[常見問題集相關 Sway-Admin 說明](https://support.office.com/article/446380fa-25bf-47b2-996c-e12cb2f9d075)。
  
|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|已變更的 Sway 共用層級  <br/> |SwayChangeShareLevel  <br/> |使用者變更 Sway 共用層級。此事件會擷取使用者變更共用 Sway; 相關聯的範圍例如，與組織內部的公開金鑰。  <br/> |
|建立的 Sway  <br/> |SwayCreate  <br/> |使用者建立 Sway。  <br/> |
|刪除的 Sway  <br/> |SwayDelete  <br/> |使用者會刪除 Sway。  <br/> |
|已停用的 Sway 重複  <br/> |SwayDisableDuplication  <br/> |使用者會停用重複的 Sway。  <br/> |
|重複的 Sway  <br/> |SwayDuplicate  <br/> |使用者會複製 Sway。  <br/> |
|編輯的 Sway  <br/> |SwayEdit  <br/> |使用者編輯 Sway。  <br/> |
|啟用的 Sway 重複  <br/> |EnableDuplication  <br/> |使用者可讓重複的 Sway;預設會啟用以啟用重複的 Sway 使用者的能力。  <br/> |
|撤銷 Sway 共用  <br/> |SwayRevokeShare  <br/> |使用者會停止共用 Sway 由撤銷其存取權。撤銷存取變更 Sway 相關聯的連結。  <br/> |
|共用的 Sway  <br/> |SwayShare  <br/> |使用者要共用 Sway。此事件會擷取按一下 Sway 共用功能表內的特定共用目的地的使用者動作。此事件不會指出使用者是否已完成的共用巨集指令。  <br/> |
|關閉 Sway 外部共用  <br/> |SwayExternalSharingOff  <br/> |系統管理員停用整個組織的使用在 Office 365 系統管理中心外部 Sway 的共用。  <br/> |
|開啟的 Sway 外部共用  <br/> |SwayExternalSharingOn  <br/> |管理員啟用整個組織的使用在 Office 365 系統管理中心外部 Sway 的共用。  <br/> |
|關閉 Sway 服務  <br/> |SwayServiceOff  <br/> |系統管理員停用 Sway 整個組織的使用在 Office 365 系統管理中心。  <br/> |
|開啟 Sway 服務  <br/> |SwayServiceOn  <br/> |系統管理員為整個組織啟用 Sway 使用 Office 365 系統管理中心 (預設會啟用服務 Sway)。  <br/> |
|檢視的 Sway  <br/> |SwayView  <br/> |使用者檢視 Sway。  <br/> |

  
### <a name="user-administration-activities"></a>使用者管理活動
  
下表列出會記錄系統管理員新增或變更的使用者帳戶使用 Office 365 系統管理中心或 Azure 管理入口網站時的使用者管理活動。
  
|**活動**|**作業**|**描述**|
|:-----|:-----|:-----|
|新增的使用者  <br/> |新增使用者  <br/> |建立 Office 365 使用者帳戶。  <br/> |
|已變更的使用者授權  <br/> |變更使用者授權  <br/> |指派授權給使用者有哪些變更。若要查看哪些授權已變更，請參閱對應的**更新使用者**活動。<br/> |
|變更的使用者密碼  <br/> |變更使用者密碼  <br/> |系統管理員已變更使用者密碼的密碼。  <br/> |
|已刪除的使用者  <br/> |刪除使用者  <br/> |Office 365 使用者帳戶已刪除。  <br/> |
|重設使用者密碼  <br/> |重設使用者密碼  <br/> |系統管理員重設使用者密碼。  <br/> |
|設定強制使用者變更密碼的屬性  <br/> |設定強制變更使用者密碼  <br/> |系統管理員設定強制使用者變更其密碼。 在下一次使用者登入 Office 365 的屬性。  <br/> |
|設定授權屬性  <br/> |設定授權屬性  <br/> |系統管理員修改指派給使用者的授權的屬性。  <br/> |
|更新的使用者  <br/> |更新使用者  <br/> |系統管理員變更使用者帳戶的一或多個的屬性。如需可更新的使用者屬性的清單，請參閱[Azure Active Directory 稽核報告事件](https://go.microsoft.com/fwlink/p/?LinkID=616549)的"更新使用者屬性 」 一節。<br/> |
  
### <a name="azure-ad-group-administration-activities"></a>Azure AD 群組管理活動
  
下表列出會記錄系統管理員或使用者建立或變更的 Office 365 群組或系統管理員會使用 Office 365 系統管理中心或 Azure 管理入口網站建立安全性群組的群組管理活動。如需 Office 365 中的群組的詳細資訊，請參閱[檢視、 建立以及刪除 Office 365 系統管理中心中的群組](https://support.office.com/article/a6360120-2fc4-46af-b105-6a04dc5461c7)。
  
|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|新增的群組  <br/> |新增群組  <br/> |建立群組時。  <br/> |
|已新增至群組的成員  <br/> |將成員新增至群組  <br/> |成員已新增至群組。  <br/> |
|已刪除的群組  <br/> |刪除群組  <br/> |已刪除的群組。  <br/> |
|從群組移除的成員  <br/> |從群組中移除成員  <br/> |已將成員從群組中移除。  <br/> |
|更新的群組  <br/> |更新群組  <br/> |已變更群組的屬性。  <br/> |
   
### <a name="application-administration-activities"></a>應用程式管理活動
  
下表列出會記錄系統管理員新增或變更 Azure AD 中註冊的應用程式時的應用程式管理活動。依賴 Azure AD 驗證的任何應用程式必須在目錄中註冊。
  
|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|新增的委派項目  <br/> |新增委派項目  <br/> |驗證權限已建立/授與 Azure AD 應用程式。  <br/> |
|新增的服務主要名稱  <br/> |新增服務主要名稱  <br/> |應用程式已登錄於 Azure AD。在目錄服務主要名稱代表應用程式。  <br/> |
|新增的認證的服務主要名稱  <br/> |新增服務主體認證  <br/> |認證新增至主體的 Azure AD 的服務。服務當中代表的目錄中應用程式。  <br/> |
|已移除的委派項目  <br/> |移除委派項目  <br/> |驗證權限已移除從 Azure AD 應用程式。  <br/> |
|移除從目錄服務主要名稱  <br/> |移除服務主要名稱  <br/> |應用程式已刪除/取消註冊從 Azure AD。在目錄服務主要名稱代表應用程式。  <br/> |
|已移除從主體服務的認證  <br/> |移除服務主體認證  <br/> |認證已移除從主體 Azure AD 的服務。服務當中代表的目錄中應用程式。  <br/> |
|設定委派項目  <br/> |設定委派項目  <br/> |驗證權限已更新在 Azure AD 應用程式。  <br/> |

### <a name="role-administration-activities"></a>角色管理活動
  
下表列出當系統管理員管理管理員角色在 Office 365 系統管理中心或 Azure management portal 中所記錄的 Azure AD 角色管理活動。
  
|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|將成員新增至角色  <br/> |將角色成員新增至角色  <br/> |新增使用者至 Office 365 系統管理員角色。  <br/> |
|從目錄角色移除使用者  <br/> |從角色移除角色成員  <br/> |Office 365 中移除使用者從系統管理員角色。  <br/> |
|設定公司連絡人資訊  <br/> |設定公司連絡人資訊  <br/> |更新 Office 365 組織層級的公司連絡人喜好設定。這包括訂閱相關的電子郵件傳送的 Office 365 中，為 Office 365 服務相關的技術通知的電子郵件地址。  <br/> |
   
### <a name="directory-administration-activities"></a>目錄管理活動
  
下表列出 Azure AD directory 及網域相關的系統管理員管理 Office 365 組織中 Office 365 系統管理中心或 Azure management portal 中會記錄的活動。
  
|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|新增為公司的網域  <br/> |將網域新增至公司  <br/> |新增網域至 Office 365 組織。  <br/> |
|新增合作夥伴到目錄  <br/> |將協力廠商新增至公司  <br/> |新增至 Office 365 組織的夥伴 （委派的管理員）。  <br/> |
|已移除從公司的網域  <br/> |移除公司的網域  <br/> |從 Office 365 組織中移除網域。  <br/> |
|從目錄上移除協力廠商  <br/> |移除公司的協力廠商  <br/> |從 Office 365 組織移除夥伴 （委派的管理員）。  <br/> |
|設定公司資訊  <br/> |設定公司資訊  <br/> |更新 Office 365 組織的公司資訊。這包括訂閱相關的電子郵件傳送的 Office 365 中，為 Office 365 服務相關的技術通知的電子郵件地址。  <br/> |
|設定網域驗證  <br/> |設定網域驗證  <br/> |變更您的 Office 365 組織的網域驗證設定。  <br/> |
|更新網域同盟設定  <br/> |設定網域同盟設定  <br/> |變更您的 Office 365 組織的同盟 （外部共用） 設定。  <br/> |
|設定密碼原則  <br/> |設定密碼原則  <br/> |已變更的 Office 365 組織中的使用者密碼長度及字元限制。  <br/> |
|開啟 Azure AD 同步處理  <br/> |在公司上設定 DirSyncEnabled 標幟  <br/> |設定啟用 Azure AD 同步處理目錄的屬性。  <br/> |
|更新的網域  <br/> |更新網域  <br/> |更新 Office 365 組織中的網域的設定。  <br/> |
|已驗證的網域  <br/> |確認網域  <br/> |確認您的組織已將網域的擁有者。  <br/> |
|已驗證的電子郵件已驗證的網域  <br/> |確認電子郵件已驗證的網域  <br/> |用來確認貴組織的網域擁有者的電子郵件的驗證。  <br/> |
   
### <a name="ediscovery-activities"></a>eDiscovery 活動
  
內容搜尋及執行 Office 365 安全性的 eDiscovery 與相關活動&amp;規範中心或執行相對應的 Windows PowerShell 指令程式會記錄在 Office 365 稽核記錄檔。這包括下列活動：
  
- 建立及管理 eDiscovery 案例
    
- 建立、 啟動和編輯內容的搜尋
    
- 執行內容搜尋動作，例如預覽，匯出，以及刪除搜尋結果
    
- 設定內容搜尋篩選的權限
    
- 管理 eDiscovery 系統管理員角色
    
清單及詳細的說明會記錄的 eDiscovery 活動，請參閱 ＜[搜尋 Office 365 中的 eDiscovery 活動的稽核記錄](search-for-ediscovery-activities-in-the-audit-log.md)。
  
> [!NOTE]
> 延長 30 分鐘的事件所產生的列下方顯示搜尋結果中的**活動**下拉式清單中的**eDiscovery 活動**的活動。相反地，採用 24 小時的時間從 eDiscovery 對應事件會出現在搜尋結果中的指令程式活動。 
  
### <a name="power-bi-activities"></a>Power BI 活動
  
下表列出使用者與 Power bi 系統活動的 Office 365 稽核記錄檔中。
  
 **重要：** 預設未啟用的 Power BI 稽核記錄。若要搜尋的 [Office 365 稽核記錄中的 Power BI 活動，您必須啟用 [Power BI 系統入口網站中的稽核。指示，請參閱[稽核 Power BI](https://docs.microsoft.com/power-bi/service-admin-auditing#enabling-auditing-functionality-in-the-power-bi-admin-portal)。
  
|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|已新增的 Power BI 群組成員  <br/> |AddGroupMembers  <br/> |成員會新增至 Power BI 群組工作區。  <br/> |
|分析的 Power BI 資料集  <br/> |AnalyzedByExternalApplication  <br/> |資料集是由外部應用程式分析。  <br/> |
|建立的 Power BI 儀表板  <br/> |CreateDashboard  <br/> |會建立新的儀表板。  <br/> |
|建立的 Power BI 群組  <br/> |CreateGroup  <br/> |建立群組。  <br/> |
|建立組織的 Power BI 內容的套件  <br/> |CreateOrgApp  <br/> |建立組織內容的套件。  <br/> |
|已刪除的 Power BI 儀表板  <br/> |DeleteDashboard  <br/> |會刪除在儀表板。  <br/> |
|已刪除的 Power BI 資料集  <br/> |DeleteDataset  <br/> |會刪除資料集。  <br/> |
|已刪除的 Power BI 報表  <br/> |DeleteReport  <br/> |報表會在刪除。  <br/> |
|下載的 Power BI 報表  <br/> |DownloadReport  <br/> |使用者會從服務 Power BI 報表下載到電腦。  <br/> |
|已編輯的 Power BI 儀表板  <br/> |EditDashboard  <br/> |在重新命名儀表板。  <br/> |
|匯出的 Power BI 報告視覺資料  <br/> |ExportReport  <br/> |從報表磚匯出資料。  <br/> |
|匯出的 Power BI 並排顯示資料  <br/> |ExportTile  <br/> |從儀表板磚匯出資料。  <br/> |
|列印的 Power BI 儀表板  <br/> |PrintDashboard  <br/> |列印儀表板。  <br/> |
|Power BI 報表的列印的頁面  <br/> |PrintReport  <br/> |列印報表。  <br/> |
|Power BI 報表發佈至網頁  <br/> |PublishToWebReport  <br/> |報表發佈至網頁。  <br/> |
|共用的 Power BI 儀表板  <br/> |ShareDashboard  <br/> |共用儀表板。  <br/> |
|啟動的 Power BI 試用版  <br/> |OptInForProTrial  <br/> |使用者啟動 Power BI 專業人員的試用版訂閱。  <br/> |
|更新的組織的 Power BI 設定  <br/> |UpdatedAdminFeatureSwitch  <br/> |系統管理員已變更的 Power BI 系統入口網站中的組織] 設定。  <br/> |
|檢視的 Power BI 儀表板  <br/> |ViewDashboard  <br/> |在儀表板來檢視。  <br/> |
|檢視的 Power BI 報表  <br/> |ViewReport  <br/> |會檢視報表。  <br/> |
  
### <a name="microsoft-teams-activities"></a>Microsoft 小組活動
  
下表列出使用者與在登入 Office 365 的 Microsoft 小組管理活動的稽核記錄。Microsoft 小組是 Office 365 中的聊天室置中對齊工作區。它結合團隊的交談、 會議、 檔案及備忘稿至單一的位置。如需詳細資訊以及的說明主題的連結，請參閱：
  
- [常見問題集的 Microsoft 小組管理說明](https://support.office.com/article/05cbe533-2181-4e95-a4b0-52cd7695fafc)
    
- [Microsoft 小組說明](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|新增的 bot 小組  <br/> |BotAddedToTeam  <br/> |使用者新增至小組 bot。  <br/> |
|新增的通道  <br/> |ChannelAdded  <br/> |使用者新增到小組的通道。  <br/> |
|已新增的連接器  <br/> |ConnectorAdded  <br/> |使用者會連接線的通道。  <br/> |
|已新增到小組成員  <br/> |MemberAdded  <br/> |小組擁有者新增到小組成員。  <br/> |
|新增索引標籤  <br/> |TabAdded  <br/> |使用者將 tab 新增的通道。  <br/> |
|變更通道設定  <br/> |ChannelSettingChanged  <br/> | 當小組成員會執行下列活動會記錄 ChannelSettingChanged 作業。每個這些活動，設定已變更 （如括弧以下所示） 的描述會顯示在稽核記錄搜尋結果中的**項目**] 欄中。<br/> <br/>-變更小組通道 （**通道名稱**） 的名稱。  <br/>  <br/>-變更小組通道 （**通道描述**） 的描述。  <br/> |
|變更組織設定  <br/> |TeamsTenantSettingChanged  <br/> | TeamsTenantSettingChanged 作業會記錄時所 （使用 Office 365 系統管理中心）; 全域管理員會執行下列活動請注意這些活動影響整個組織的 Microsoft 小組設定。如需詳細資訊，請參閱[Microsoft 小組的系統管理員設定](https://support.office.com/article/3966a3f5-7e0f-4ea9-a402-41888f455ba2)。<br/>  每個這些活動，設定已變更 （如括弧以下所示） 的描述會顯示在稽核記錄搜尋結果中的**項目**] 欄中。  <br/><br/>-啟用或停用組織 (**的 Microsoft 小組**) 的 Microsoft 小組。  <br/><br/>-啟用或停用組織 ( **Business 交互操作必須使用 Skype**) 之間的 Microsoft 小組和 Skype for Business 的互通性。<br/><br/>-啟用或停用的 Microsoft 小組用戶端 （ **Org 圖表] 檢視**） 中的 [組織圖] 檢視。  <br/><br/>-啟用或停用讓小組成員進行排程私人會議 （**私人會議排程**） 的能力。  <br/><br/>-啟用或停用的排程 （**通道會議排程**） 的通道會議的小組成員的能力。  <br/><br/>-啟用或停用視訊在呼叫小組會議 （ **Skype 會議視訊**）。  <br/><br/>-啟用或停用螢幕共用中的 Microsoft 小組 meetups 組織 （**螢幕共用 Skype 會議**）。  <br/><br/>-啟用或停該能夠加入動畫效果的圖像 （稱為 Giphys） 至小組交談 （**動畫效果的圖像**）。  <br/><br/>-變更分級組織 （**內容分級**） 設定的內容。內容分級限制可顯示交談中的動畫影像的類型。<br/><br/>-啟用或會停用功能讓小組成員進行新增可自訂的圖像 （稱為 「 自訂 memes） 從網際網路對小組交談 （**從網際網路可自訂的圖像**）。  <br/><br/>-啟用或停對小組交談 （**可編輯的影像**） 的小組成員新增可編輯的圖像 （稱為貼紙） 的能力。<br/><br/>-啟用或停用使用中的 Microsoft 小組聊天室和通道 (**全組織的 bot**) bot 的小組成員的能力。<br/><br/>-啟用特定 bot 的 Microsoft 小組;這不包括 T-Bot，這是當組織 (**個別 bot**) 啟用 bot 的小組說明 bot。  <br/><br/>-啟用或停用讓小組成員新增副檔名或索引標籤 （**延伸或] 索引標籤**）。  <br/><br/>-啟用或停用戶端載入的專屬 Bot 的 Microsoft 小組 (**端載入 Bot 的**)。  <br/><br/>-啟用或停用使用者的 Microsoft 小組通道 (**通道電子郵件**) 傳送電子郵件的功能。  <br/> |
|已變更的小組成員的角色  <br/> |MemberRoleChanged  <br/> |小組擁有者變更小組成員的角色。下列的值表示已指派給使用者的角色類型。<br/><br/><br/> **1** -會指出擁有者 」 角色。<br/>**2** -會指出成員角色。 <br/>**3** -會指出來賓角色。 <br/>Members 屬性也會包含您的組織和成員的電子郵件地址的名稱。  <br/> |
|變更小組設定  <br/> |TeamSettingChanged  <br/> | TeamSettingChanged 作業會記錄下列活動會執行小組擁有者時。每個這些活動，設定已變更 （如括弧以下所示） 的描述會顯示在稽核記錄搜尋結果中的**項目**] 欄中。<br/><br/>-變更小組的存取類型。小組可以設為私人或公開 （**小組存取類型**）。當小組在私人 （預設設定），使用者可以存取小組只能邀請。公用小組時，它是可供搜尋的任何人。<br/><br/>-變更資訊分類保護資訊之小組 （**小組分類**）。  <br/>  例如，小組資料可分類為高的業務影響、 中型業務影響或低的業務影響。<br/><br/>-變更小組 （**小組名稱**） 的名稱。  <br/><br/>-變更小組描述 （**小組描述**）。 <br/><br/>-任何小組設定所做的變更。小組擁有者可以存取這些設定小組用戶端中的依以滑鼠右鍵按一下 [小組] 和 [**管理小組**，然後按一下 [**設定**] 索引標籤。這些活動，已變更的設定的名稱會顯示在稽核記錄搜尋結果中的**項目**] 欄中。<br/> |
|建立的小組  <br/> |TeamCreated  <br/> |使用者會建立新的小組。  <br/> |
|已刪除的通道  <br/> |ChannelDeleted  <br/> |使用者會從小組刪除通道。  <br/> |
|已刪除的小組  <br/> |TeamDeleted  <br/> |小組擁有者中刪除小組。  <br/> |
|已移除的 bot 小組  <br/> |BotRemovedFromTeam  <br/> |使用者會移除小組 bot。  <br/> |
|已移除的連接器  <br/> |ConnectorRemoved  <br/> |使用者會移除通道的連接器。  <br/> |
|移除小組的成員  <br/> |MemberRemoved  <br/> |小組擁有者移除小組的成員。  <br/> |
|已移除] 索引標籤  <br/> |TabRemoved  <br/> |使用者會移除通道] 索引標籤。  <br/> |
|更新的連接器  <br/> |ConnectorUpdated  <br/> |使用者修改通道中的連接器。  <br/> |
|更新] 索引標籤  <br/> |TabUpdated  <br/> |使用者修改日期] 索引標籤中使用的通道。  <br/> |
|使用者登入小組  <br/> |TeamsSessionStarted  <br/> |使用者的 Microsoft 小組用戶端登入。  <br/> |

### <a name="yammer-activities"></a>Yammer 活動
  
下表列出使用者並登入 Office 365 的管理活動 Yammer 中的稽核記錄。若要傳回來自 Office 365 Yammer 與相關活動的稽核記錄，您必須**活動**清單中選取 [**顯示所有的活動的結果**。使用 [日期範圍] 方塊和 [**使用者**] 清單來縮小搜尋結果。 
  
|**易記名稱**|**作業**|**描述**|
|:-----|:-----|:-----|
|已變更的資料保留原則  <br/> |SoftDeleteSettingsUpdated  <br/> |已驗證的系統管理更新為固定刪除或柔刪除網路資料保留原則的設定。僅限已驗證的系統管理員可以執行此作業。  <br/> |
|已變更的網路設定  <br/> |NetworkConfigurationUpdated  <br/> |由於網路或已驗證的系統管理變更 Yammer 網路的設定。這包括設定匯出資料並啟用聊天的間隔。  <br/> |
|已變更的網路設定檔設定  <br/> |ProcessProfileFields  <br/> |由於網路或已驗證的系統管理變更出現成員設定檔的網路使用者網路上的資訊。  <br/> |
|已變更的私人內容模式  <br/> |SupervisorAdminToggled  <br/> |已驗證的系統開關*私人內容模式*。此模式屬性可讓管理員檢視文章私人群組和檢視個別的使用者 （或使用者群組） 之間的私人郵件中。僅限只有已驗證的系統管理員可以執行此作業。<br/> |
|已變更的安全性設定  <br/> |NetworkSecurityConfigurationUpdated  <br/> |已驗證的系統管理更新 Yammer 網路的安全性設定。這包括設定密碼到期原則和 IP 位址的限制。僅限已驗證的系統管理員可以執行此作業。  <br/> |
|建立的檔案  <br/> |FileCreated  <br/> |使用者上傳檔案。  <br/> |
|建立的群組  <br/> |GroupCreation  <br/> |使用者會建立新的群組。  <br/> |
|已刪除的群組  <br/> |GroupDeletion  <br/> |從 Yammer 刪除群組。  <br/> |
|已刪除的郵件  <br/> |MessageDeleted  <br/> |使用者會刪除郵件。  <br/> |
|下載的檔案  <br/> |FileDownloaded  <br/> |使用者下載檔案。  <br/> |
|匯出的資料  <br/> |DataExport  <br/> |已驗證的系統會將 Yammer 網路資料匯出。僅限已驗證的系統管理員可以執行此作業。  <br/> |
|共用的檔案  <br/> |FileShared  <br/> |使用者與其他使用者共用檔案。  <br/> |
|暫停的網路使用者  <br/> |NetworkUserSuspended  <br/> |網路或已驗證的系統管理員擱置 （停用） Yammer 中的使用者。  <br/> |
|暫停的使用者  <br/> |UserSuspension  <br/> |暫停使用者帳戶 （已停用）。  <br/> |
|更新的檔案描述  <br/> |FileUpdateDescription  <br/> |使用者變更檔案的描述。  <br/> |
|更新的檔案名稱  <br/> |FileUpdateName  <br/> |使用者變更檔案的名稱。  <br/> |
|檢視的檔案  <br/> |FileVisited  <br/> |使用者檢視檔案。  <br/> |
   
### <a name="microsoft-stream"></a>Microsoft Stream
  
您可搜尋 Microsoft 資料流活動的稽核記錄。這些活動包括使用者、 群組通道活動，以及管理活動等管理使用者、 管理組織設定並匯出報告所執行的視訊活動。這些活動的說明，請參閱[Microsoft Stream 中的稽核記錄](https://docs.microsoft.com/stream/audit-logs)"活動登入 Microsoft 資料流 」 一節。
  
### <a name="exchange-admin-audit-log"></a>Exchange 管理員稽核記錄
  
Exchange 系統管理員稽核記錄-Office 365 中的預設會啟用其 — 當系統管理員 （或已指派系統管理權限的使用者） 進行變更 Exchange Online 組織中將事件記錄中的 Office 365 稽核記錄。使用 Exchange 系統管理中心或 Windows PowerShell 中執行指令程式來進行的變更都會記錄在 Exchange 管理員稽核記錄。如需詳細資訊管理稽核記錄功能在 Exchange，請參閱[系統管理員稽核記錄](https://go.microsoft.com/fwlink/p/?LinkID=619225)。
  
以下是搜尋 Exchange 管理員稽核記錄中的活動的一些秘訣：
  
- 若要傳回項目從 Exchange 管理員稽核記錄，您必須**活動**清單中選取 [**顯示所有的活動的結果**。使用 [日期範圍] 方塊和 [**使用者**] 清單來縮小搜尋結果的特定日期範圍內的特定 Exchange 系統管理員所執行的指令程式。 
    
- 若要顯示從 Exchange 管理員稽核記錄的事件，篩選搜尋結果和類型**-**（虛線）**活動**篩選] 方塊中。這會顯示的 Exchange 系統事件的 [**活動**] 欄中顯示的指令程式名稱。然後您可以排序依字母順序排列的 cmdlet 名稱。 
    
    ![一條虛線後的活動在方塊中輸入篩選 Exchange admin 事件](media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)
  
- 若要取得何種 cmdlet 所執行、 所使用的參數和參數值，以及哪些物件所影響的詳細資訊，您必須將搜尋結果匯出並選取 [**下載所有結果**] 選項。 
    
- 您也可以檢視 Exchange 管理員稽核記錄中的事件使用 Exchange 系統管理中心。指示，請參閱[檢視系統管理員稽核記錄](https://technet.microsoft.com/library/dn342832%28v=exchg.150%29.aspx)。
  
## <a name="frequently-asked-questions"></a>常見問題集

**何處可找到有關 Office 365 中的稽核服務所提供的功能？**

如需 Office 365 中可用的稽核與報告功能的詳細資訊，請參閱[稽核與 Office 365 中的報告](office-365-auditing-and-reporting-overview.md)。 

**不同 Office 365 服務目前稽核有哪些？**

最常使用的 Office 365 服務 like Exchange Online、 SharePoint、 OneDrive、 Azure Active Directory、 的 Microsoft 小組、 CRM、 進階威脅保護及資料外洩防護稽核。請參閱本文的完整清單中的 [[簡介](#search-the-audit-log-in-the-office-365-security-amp-compliance-center)] 區段。

**哪些活動的稽核 Office 365 服務稽核？**

請參閱本文章的清單及稽核 Office 365 中的活動的描述[Audited 活動](#audited-activities)一節。

**沒有多少時間針對稽核記錄的事件之後發生可供使用？**

大部分的稽核資料有 30 分鐘內，但可能需要最多 24 小時之後事件發生於對應的稽核記錄項目顯示搜尋結果中。請參閱本文顯示所花費的不同 Office 365 服務中的事件可供使用的時間[開始之前](#before-you-begin)] 區段中的表格。

**多久要保留稽核記錄吗？**

目前的稽核的記錄的保留期為 90 天。若要增加此限制的計劃主動正在處理 Microsoft。 

**我可以程式設計方式存取稽核資料吗？**

[是]。Office 365 管理活動 API 用來以程式設計方式擷取稽核記錄。 若要開始，請參閱[開始使用 Office 365 管理 api （英文）](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。

**是否有其他方法可以取得稽核記錄檔之外 suing Office 365 安全性 & 規範中心或 Office 365 管理活動 API 吗？**

[否]。這些是只有兩種方式從 Office 365 稽核服務取得資料。 

**是否需要個別啟用 [我想要擷取稽核記錄中的每個服務中的稽核吗？**

在大多數的 Office 365 服務稽核預設會啟用後您一開始開啟稽核功能的 Office 365 組織 （如本文中的 [[開始之前](#before-you-begin)] 區段中所述）。不過，您必須啟用信箱稽核針對您想要稽核的信箱在 Exchange Online。  我們正在工作的啟用信箱稽核由 Office 365 組織中所有信箱的預設值。如需詳細資訊，請參閱 「 Exchange 信箱稽核將會預設啟用" [Microsoft 安全性、 隱私權和規範部落](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Exchange-Mailbox-Auditing-will-be-enabled-by-default/ba-p/215171)格中。

**沒有 Office 365 稽核服務支援重複資料刪除的記錄吗？**

[否]。稽核服務管線接近，即時與因此無法支援重複資料刪除。
 
**Office 365 稽核資料是否流程不同地理位置中吗？**

[否]。我們目前有稽核 NA （北美洲）、 （歐洲、 中東及非洲） EMEA 和 APAC （亞太地區） 區域中的管線部署。不過，我們可能 flow 資料跨這些區域的負載平衡與僅在 live 網站問題。當我們執行執行這些活動時，已加密傳送過程中的資料。   
 
**稽核加密資料吗？**

稽核資料會儲存在其中部署稽核管線的相同區域中的 Exchange 信箱 （靜態資料）。此資料不會加密。但是，一律加密傳送過程中的資料。 












