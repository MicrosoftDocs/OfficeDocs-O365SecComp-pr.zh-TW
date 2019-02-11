---
title: Office 365 中的內容搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: 使用 Office 365 安全性內容搜尋&amp;規範中心搜尋的內容信箱、 SharePoint Online 網站、 OneDrive 帳戶、 的 Microsoft 小組、 Office 365 群組和 Skype 商務交談。您可以使用關鍵字搜尋查詢和搜尋條件來縮小搜尋結果。然後您可預覽及匯出搜尋結果。內容搜尋也是有效的工具來搜尋 GDPR 資料主體要求可能相關的內容。
ms.openlocfilehash: befd2060e65cea73d3c8432b77727e27dd91b82a
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29686114"
---
# <a name="content-search-in-office-365"></a>Office 365 中的內容搜尋

您可以使用 「 內容搜尋 eDiscovery 工具在 Office 365 安全性&amp;規範中心來搜尋就地等電子郵件、 文件和立即訊息交談 Office 365 組織中的項目。使用此工具來搜尋這些 Office 365 服務中的項目：
  
- Exchange Online 信箱及公用資料夾
    
- SharePoint Online 網站和 OneDrive for Business 的帳戶
    
- Skype 商務交談
    
- Microsoft Teams 
    
- Office 365 群組
    
之後執行內容搜尋] 的內容位置數目，並搜尋設定檔中顯示預估的搜尋結果數目。您可以也快速檢視統計資料，例如有最多個項目符合搜尋查詢的內容位置。執行搜尋之後，您可以預覽結果或將它們匯出到本機電腦。


## <a name="create-a-new-search"></a>建立新的搜尋

若要讓**內容搜尋**] 頁面上執行的搜尋及預覽，並將搜尋結果匯出至 access，系統管理員、 法務或 eDiscovery 管理員必須是安全性 eDiscovery 管理員角色群組的成員&amp;規範中心。如需詳細資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用您的 Office 365 電子郵件地址和密碼登入。 
    
3. 安全性&amp;規範中心，按一下 [**搜尋&amp;調查** \> **內容搜尋**。
    
4. 在 [**搜尋**] 頁面上按一下箭號旁![新增圖示](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新的搜尋**。 
    
    ![新的 [搜尋] 下拉式清單](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    您可以選擇下列其中一個選項：
    
  - **「 引導式搜尋**此選項啟動引導您完成建立搜尋] 精靈。選取的內容位置並建立搜尋查詢的使用者介面是**新的搜尋**選項相同。 
    
  - **新的搜尋**此選項會顯示已更新的使用者介面來建立新的搜尋。如果您按一下 [**新增搜尋**，這是預設選項。
    
  - **識別碼清單來搜尋**此選項可讓您搜尋特定的電子郵件訊息及使用 Exchange 識別碼清單其他信箱項目。若要建立 （正式稱為 「 目標的搜尋 」） 的識別碼清單搜尋，您提交識別特定信箱的項目要搜尋的逗號分隔的值 (CSV) 檔案。指示，請參閱[Prepare 識別碼清單內容搜尋 Office 365 中的 CSV 檔案](csv-file-for-an-id-list-content-search.md)。
    
    在此程序的步驟的其餘部分將會遵循預設新的搜尋工作流程。
    
5. 下拉式清單中的 [**新的搜尋**。 
    
6. 在 [**搜尋查詢**時，指定下列項目。
    
    ![指定的關鍵字、 條件及搜尋位置](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
- **要搜尋的關鍵字**-搜尋查詢**關鍵字**] 方塊中的類型。您可以指定關鍵字，訊息屬性例如傳送及接收日期或文件內容，例如檔案名稱或上次變更文件的日期。您可以使用較複雜的查詢使用布林運算子，例如**AND**、**或**、**不**及**NEAR**。您也可以搜尋文件或搜尋功能已從外部共用的文件中的機密資訊 （例如社會安全編號）。如果 [關鍵字] 方塊中保留空白，將會在搜尋結果中包含位於指定之內容的位置中的所有內容。
    
    或者，您可以按一下 [**顯示關鍵字清單**] 核取方塊和類型中的每一列的關鍵字。如果您這樣做，在每一列的關鍵字連接的作用與**OR**運算子會建立搜尋查詢中相似的邏輯運算子 ( **c:s**) 所連接。 
    
    為什麼要選擇使用 [關鍵字] 清單？您可以取得顯示多少個項目比對每個關鍵字的統計資料。這可協助您快速識別出哪些關鍵字是最 （且至少） 有效。您也可以使用 （以括弧括住） 的關鍵字文句] 列中。如需搜尋統計資料的詳細資訊，請參閱 ＜[檢視內容的搜尋結果的關鍵字統計資料](view-keyword-statistics-for-content-search.md)。

    [!NOTE] 若要協助減少大型關鍵字清單所導致的問題，現在是限制最大值為 20 列在 [關鍵字] 清單中。
    
- **條件**-您可以新增要將搜尋縮小並傳回結果集更精簡的搜尋條件。每個條件將子句新增至搜尋查詢，建立及執行當您啟動搜尋。條件是以邏輯方式連線到 （在 [關鍵字] 方塊中指定） 的關鍵字查詢類似的作用**和**運算子的邏輯運算子 （**列**）。這表示項目必須滿足的關鍵字查詢與結果中包含的一或多個條件。這是條件，縮減結果協助的方式。清單和說明您可以在搜尋查詢中使用的條件，請參閱 「 搜尋條件 」 一節[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md#search-conditions)。
    
- **位置**-選擇要搜尋的內容位置。
    
  - **所有位置**-使用此選項可在組織中搜尋所有內容的位置。這包括電子郵件 （包括所有非使用中信箱、 Office 365 的所有群組的信箱、 信箱的所有的 Microsoft 小組） 的所有 Exchange 信箱中的商務交談，所有 SharePoint 和 OneDrive for Business 網站 （包括網站的所有 Skype為所有 Office 365 群組和 Microsoft 小組），並在所有 Exchange 公用資料夾中的項目。
    
  - **特定位置**-使用此選項，以搜尋特定內容的位置。您可以搜尋特定 Office 365 服務的所有內容的位置 （例如搜尋所有 Exchange 信箱或搜尋所有 SharePoint 網站） 或您可以在任何顯示 Office 365 服務都搜尋特定的位置。 
    
    ![選擇要搜尋的內容位置的使用者介面](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
    請注意您也可以新增通訊群組來搜尋 Exchange 信箱的清單。通訊群組、 要搜尋的群組成員的信箱。請注意動態通訊群組不受支援。
    
    **重要：** 當您搜尋所有信箱位置或只是特定的信箱時，請從 MyAnalytics 和其他 Office 365 應用程式已儲存至使用者信箱的資料會包含匯出內容的都搜尋結果時。此資料不會包含在預估的搜尋結果，不適用於預覽。它只會包含當您匯出並下載搜尋結果;請參閱[MyAnalytics 匯出資料與其他 Office 365 應用程式](#exporting-data-from-myanalytics-and-other-office-365-applications)」 內容搜尋相關的詳細資訊 」 區段中。 
    
7. 您是否已設定您的搜尋查詢之後，按一下 [**儲存&amp;執行**。
    
8. **儲存搜尋**] 頁面上輸入搜尋，並選擇性描述，有助於找出搜尋的名稱。請注意搜尋的名稱是您組織中唯一的。 
    
9. 按一下 [**儲存**] 以啟動搜尋。 
    
    儲存並執行搜尋之後，在 [結果] 窗格中顯示搜尋傳回任何結果。根據方式有設定 [預覽] 設定，在搜尋結果會顯示或您已按一下 [檢視其**預覽結果**。請參閱 [下一步] 區段中的詳細資訊。 
    
若要重新存取此內容的搜尋或存取其他內容的搜尋列在 [**內容搜尋**] 頁面上，選取搜尋] 和 [**開啟**。 
  
若要清除結果或建立新的搜尋，請按一下 [![新增圖示](media/O365-MDM-CreatePolicy-AddIcon.gif)**新的搜尋**。 

  
## <a name="preview-search-results"></a>預覽搜尋結果

來預覽搜尋結果有兩種組態設定。在執行新的新搜尋或開啟現有的搜尋之後，按一下 [* * 個別結果 * * 以檢視下列預覽設定： 
  
![預覽搜尋結果設定](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. **自動預覽結果**-此設定會顯示在搜尋結果之後執行搜尋。
    
2. **手動預覽結果**-此設定會預留位置顯示在搜尋結果] 窗格中，並會顯示您必須按一下 [顯示搜尋結果的**預覽結果**] 按鈕。這是預設的設定 ；它可協助您開啟現有的搜尋時不會自動顯示搜尋結果，以提升搜尋效能。 
    
有多少個項目可用來預覽與相關的限制。如需詳細資訊，請參閱[Limits for Search in Office 365 安全性&amp;規範中心](limits-for-content-search.md)。 
  
如要預覽的支援的檔案類型清單，請參閱 「 內容搜尋的相關的詳細資訊 」 區段中的 [ [Previewing 搜尋結果](#previewing-search-results)。如果檔案類型不支援的預覽或下載文件的複本，您可以按一下 [**下載 [原始檔案**下載至您的本機電腦。針對.aspx 網頁，包含頁面的 URL 則但是您可能無法存取] 頁面上的權限。 
  
也請注意編製索引的項目不適用於預覽。
  
## <a name="view-information-and-statistics-about-a-search"></a>檢視資訊與搜尋相關的統計資料

建立並執行內容的搜尋後，您可以檢視有關預估的搜尋結果的統計資料。這包括的搜尋結果，例如內容的位置與符合搜尋查詢的項目數目及內容的位置具有最符合的項目名稱的查詢統計資料摘要。您可以顯示一或多個內容搜尋統計的資料。這可讓您快速比較的多個搜尋結果，並進行搜尋查詢的效益的相關決策。
  
您也可以下載到 CSV 檔案的搜尋統計資料和關鍵字統計資料。這可讓您在 Excel 中使用的篩選和排序的功能比較結果，並準備您的搜尋結果中的報告。
  
若要檢視搜尋統計資料：
  
1. 在 [安全性]**內容搜尋**] 頁面上&amp;規範中心，按一下 [**開啟**] 和 [您要檢視的統計資料的搜尋。 
    
2. 在飛入] 頁面上，按一下 [**開啟查詢**]。 
    
3. 在**個別的結果**] 下拉式清單中，按一下 [**搜尋設定檔**。
    
4. 在 [**類型**] 下拉式清單中，按一下其中一個下列選項根據您要檢視的搜尋統計資料。 
    
  - 搜尋**摘要**會顯示每種類型的內容位置的統計資料。此內容的內容位置包含符合搜尋查詢的項目數目及總計的數目與大小搜尋結果項目。這是預設設定。
    
  - **查詢**-顯示搜尋查詢的相關的統計資料。這包含的內容位置查詢統計資料適用於類型、 搜尋查詢的統計資料的組件所適用 （注意**主要**指出整個搜尋查詢），包含的內容位置的項目數找出符合搜尋查詢，總數和大小及項目 （在指定的內容位置） 所找到的比對搜尋查詢。請注意編製索引的項目 （也稱為部分已編製索引的項目） 的統計資料也會顯示。不過，只有部分已編製索引的項目從信箱中隨附的統計資料。從 SharePoint 和 OneDrive 部分已編製索引項目並不包含統計資料。
    
  - **上方的位置**-顯示統計資料相關的符合搜尋查詢中每個所搜尋的內容位置的項目數。會顯示前 1000 個位置。
    
如需搜尋統計資料的詳細資訊，請參閱[檢視內容的搜尋結果的關鍵字統計資料](view-keyword-statistics-for-content-search.md)。
  
  
## <a name="export-search-results"></a>匯出搜尋結果

成功執行搜尋之後，您可以將搜尋結果匯出到本機電腦。當您將電子郵件結果匯出時，他們可以下載到您的電腦為 PST 檔案或個別郵件 （.msg 檔）。當您從 SharePoint 和 OneDrive 網站匯出內容時，都要匯出的原生 Office 文件複本。也有其他文件和隨附匯出的搜尋結果的報告。您也只可以匯出搜尋結果報表並不實際的項目。
  
若要匯出搜尋結果：
  
1. 在 [安全性]**內容搜尋**] 頁面上&amp;規範中心，按一下 [**開啟**] 和 [您想要匯出的搜尋結果的搜尋。 
    
2. 在飛入] 頁面上，按一下 [![匯出搜尋結果圖示](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)**多個**，然後按一下 [**匯出結果**。請注意您也可以匯出搜尋結果報表。
    
3. 完成 [匯出結果]**** 彈出式頁面上的區段。請務必使用捲軸，以檢視所有匯出選項。 
    
如需更詳細的指示和疑難排解秘訣，請參閱：
  
- [從 Office 365 安全性匯出搜尋結果&amp;規範中心](export-search-results.md)
    
- [匯出內容搜尋報告](export-a-content-search-report.md)
    

  
## <a name="more-information-about-content-search"></a>內容搜尋的詳細資訊

請參閱下列各節的內容搜尋的詳細資訊。
  
[內容的搜尋限制](#content-search-limits)
  
[建立搜尋查詢](#building-a-search-query)
  
[搜尋 OneDrive 帳戶](#searching-onedrive-accounts)
  
[搜尋的 Microsoft 小組和 Office 365 群組](#searching-microsoft-teams-and-office-365-groups)
  
[搜尋非使用中信箱](#searching-inactive-mailboxes)
  
[預覽搜尋結果](#previewing-search-results)
  
[部分已編製索引的項目](#partially-indexed-items)
  
[將資料匯出從 MyAnalytics 和其他 Office 365 應用程式](#exporting-data-from-myanalytics-and-other-office-365-applications)
  
### <a name="content-search-limits"></a>內容的搜尋限制

- 會套用至內容的搜尋功能的限制的說明，請參閱[Limits for Search in Office 365 安全性&amp;規範中心](limits-for-content-search.md)。
    
- Microsoft 收集所有 Office 365 組織所執行的內容搜尋的效能資訊。雖然搜尋查詢的複雜性可能會影響搜尋時間，搜尋會影響搜尋讓有的信箱數目多長的最大因素。雖然 Microsoft 不會提供搜尋時間服務層級協議下, 表列出根據包含在搜尋中的信箱數目內容搜尋平均搜尋時間。
    
|**信箱數量**|**平均搜尋時間**|
|:-----|:-----|
|100  <br/> |30 秒  <br/> |
|1,000  <br/> |45 秒  <br/> |
|10,000  <br/> |4 分鐘  <br/> |
|25000  <br/> |10 分鐘  <br/> |
|各 50000 個  <br/> |20 分鐘  <br/> |
|100,000  <br/> |25 分鐘  <br/> |
  
### <a name="building-a-search-query"></a>建立搜尋查詢

如需建立搜尋查詢、 使用布林搜尋運算子和搜尋條件，以及搜尋的敏感資訊類型與組織外部的使用者與共用的內容的詳細資訊，請參閱[關鍵字查詢和搜尋條件內容搜尋](keyword-queries-and-search-conditions.md)。
  
使用 [關鍵字] 清單來建立搜尋查詢時保持記住下列事項。
  
- 您必須選取 [**顯示關鍵字清單**] 核取方塊，然後輸入來建立搜尋查詢的個別資料列中的 [每個關鍵字其中每一列中的關鍵字 （或關鍵字片語） 連接所連接的**OR**運算子。如果您只是在 [關鍵字] 方塊中貼上關鍵字的清單或按下**Enter**鍵後輸入關鍵字，他們將不會透過**OR**運算子連接。以下是不正確和正確範例新增關鍵字的清單。 
    
    **不正確**
    
    ![不正確的方式來格式化關鍵字清單 （由貼入 [關鍵字] 方塊中的清單）](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **更正**
    
    ![正確的方式來格式化關鍵字清單 （由選取核取方塊，然後貼上清單）](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- 您可以也準備的關鍵字或 Excel 檔案或純文字檔案中的關鍵字詞清單然後複製並貼上您在關鍵字清單的清單。為達成此目的，您必須選取 [**顯示關鍵字清單**] 核取方塊。然後按一下 [關鍵字] 清單中的第一列並貼上您的清單。Excel 或文字檔案中的每一行會貼上中以 [關鍵字] 清單中的列分隔開。 
    
- 建立查詢中使用 [關鍵字] 清單之後，它會是不錯的選項來確認搜尋查詢語法進行搜尋查詢是您對象。在詳細資料窗格中顯示 [**查詢**搜尋查詢，以文字 **(c:s)** 分隔的關鍵字。 這表示關鍵字會連接到由邏輯運算子**OR**運算子的作用如下。同樣地，如果您的搜尋查詢包含條件、 關鍵字及條件隔開文字 **（列）**。 這指出關鍵字可連線至及類似功能**及**邏輯運算子的條件運算子。以下是範例結果時使用 [關鍵字] 清單及條件的搜尋查詢 （顯示詳細資料窗格中）。 
    
    ![當使用關鍵字清單] 與 [條件時所建立的查詢的範例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- 當您執行內容的搜尋時，Office 365 自動檢查您的搜尋查詢不受支援的字元與可能未接的布林運算子。不支援的字元通常隱藏與通常搜尋的錯誤或傳回非預期的結果。如需會檢查有不支援字元的詳細資訊，請參閱[檢查錯誤的內容搜尋查詢](check-your-content-search-query-for-errors.md)。
    
- 如果您有包含非英文字元 （例如中文字元） 關鍵字搜尋查詢時，您可以按一下 [**查詢語言和國家/區域**![查詢語言和國家/區域中的內容搜尋] 圖示](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png)選取搜尋的語言和國家/區域文化特性代碼值。請注意預設語言/地區中性。您可以分清是否您需要變更內容的搜尋的語言設定？如果您是特定的內容位置包含非英文字元搜尋，但搜尋未傳回任何結果的語言設定可能原因。 
  
### <a name="searching-onedrive-accounts"></a>搜尋 OneDrive 帳戶

- 若要收集您組織中的 OneDrive 網站的 Url 清單，請參閱[建立的組織中的所有 OneDrive 位置清單](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。本文中的此指令碼會建立包含的所有 OneDrive 網站清單的文字檔案。若要執行此指令碼，您必須安裝及使用 SharePoint Online 管理命令介面。請務必附加至每個想要搜尋的 OneDrive 網站的組織的我的網站網域的 URL。這是包含您 OneDrive; 的網域例如， `https://contoso-my.sharepoint.com`。以下是使用者的 OneDrive 網站的 URL 範例： `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。
    
    在極罕見的情況下變更人員的使用者主體名稱 (UPN) 時，其 OneDrive 位置的 URL 會變更要併入新的 UPN。如果發生這種情況，您必須新增使用者的新 OneDrive URL 並移除舊來修改內容的搜尋。
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a>搜尋的 Microsoft 小組和 Office 365 群組

您可以搜尋與 Office 365 群組或 Microsoft 小組關聯的信箱。Office 365 群組之內建的 Microsoft 小組，因為這些搜尋是非常類似。在這兩種情況下，僅限的群組或小組信箱搜尋 ；群組或小組成員的信箱不搜尋。若要進行搜尋，您必須特別將它們新增至搜尋。
  
搜尋的 Microsoft 小組和 Office 365 群組中的內容時請記住下列事項。
  
- 若要搜尋的內容中的 Microsoft 小組與 Office 365 群組，您必須指定的信箱和相關聯的團隊或群組的 SharePoint 網站。
    
- 執行**Get UnifiedGroup** cmdlet 在 Exchange Online 中的 Microsoft 小組或 Office 365 群組檢視屬性。這是一個好方法來取得與小組或群組具有相關聯的網站的 URL。例如，下列命令會顯示所選的屬性名為資深領導小組 Office 365 群組： 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > 若要執行**Get UnifiedGroup**指令程式，您必須指派 「 僅檢視收件者 」 角色在 Exchange Online 或角色群組的成員，已指派 「 僅檢視收件者 」 角色。 
  
- 當使用者的信箱搜尋時，將不會搜尋所有的 Microsoft 小組或使用者為其成員的 Office 365 群組。同樣地，當您搜尋 Microsoft 小組或 Office 365 群組中，只有群組信箱和群組網站您指定搜尋 ；除非您明確地將其新增搜尋，不會搜尋信箱與 OneDrive for Business 的群組成員的帳戶。
    
- 若要取得的 Microsoft 小組或 Office 365 群組成員的清單，您可以檢視屬性**首頁\>群組**頁面上的 Office 365 系統管理中心。或者，您可以在 Exchange Online PowerShell 中執行下列命令： 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > 若要執行**Get UnifiedGroupLinks**指令程式，您必須指派 「 僅檢視收件者 」 角色在 Exchange Online 或角色群組的成員，已指派 「 僅檢視收件者 」 角色。 
  
- 屬於 Microsoft 小組通道的交談會儲存在具有 Microsoft 小組與相關聯的信箱。同樣地，小組成員共用通道中的檔案都會儲存在團隊的 SharePoint 網站上。因此，您必須將 Microsoft 小組信箱和 SharePoint 網站新增為通道中搜尋交談和檔案的內容位置。
    
- 或者，是 [聊天室] 清單中的 Microsoft 小組的一部分的交談會儲存在 Exchange Online 信箱的使用者參與交談。與使用者共用聊天交談中的檔案都會儲存在 OneDrive for Business 共用檔案的使用者帳戶。因此，您必須新增個別使用者信箱和 OneDrive for Business 帳戶做為在 [聊天室] 清單中搜尋交談和檔案的內容位置。
    
    > [!NOTE]
    > 在 Exchange 混合部署中與內部部署信箱的使用者可能會參與交談屬於 [聊天室] 清單中的 Microsoft 小組。在此例中，從這些交談內容也是可搜尋因為具有內部部署信箱的使用者將它儲存至雲端儲存區域 （稱為 「*雲端架構信箱的內部使用者*）。如需詳細資訊，請參閱 ＜[搜尋雲端架構信箱的內部部署 Office 365 中的使用者](search-cloud-based-mailboxes-for-on-premises-users.md)。
  
- 每個 Microsoft 小組或小組通道包含 Wiki 筆記記錄與共同作業。Wiki 內容會自動儲存至含有.mht 格式的檔案。此檔案儲存在團隊的 SharePoint 網站上的小組 Wiki 資料文件庫。您可以使用 「 內容搜尋工具來搜尋 wiki （英文） 指定為要搜尋的內容位置的團隊的 SharePoint 網站。 
    
    > [!NOTE]
    > 搜尋 wiki （英文） 的 Microsoft 小組或通道 （如果您搜尋團隊的 SharePoint 網站） 的功能已於 2017 年 6 月 22 日發行。Wiki 頁面儲存或在更新的日期或之後可用來搜尋。上次儲存或更新的日期之前的 Wiki 頁面都可供搜尋。 
 
- 會議與通話中的 Microsoft 小組通道的摘要資訊也會儲存在之撥入會議或通話之使用者的信箱。這表示您可以使用內容搜尋來搜尋這些摘要的記錄。摘要資訊包括： 
  - 日期、 開始時間、 結束時間以及的會議或通話持續時間

  - 日期和時間每位參與者加入或離開會議或通話時

  - 通話傳送至語音信箱

  - 未接或接聽電話

  - 來電轉接、 表示為兩個不同的通話

  請注意可能很多達 8 小時會議和通話摘要記錄可供搜尋。

  在搜尋結果中會議摘要會被識別為在**類型] 欄位**中，**會議**通話摘要會被識別為**呼叫**。此外，屬於小組通道及 1xN 聊天室的交談會被識別為**IM**的 [**類型**] 欄位。
  
  ![在 [類型] 欄位中識別小組會議、 通話及 1xN 聊天室](media/O365-ContentSearch-Teams-MessageKind.png)

- 您可以使用**種類**email 屬性或**訊息類型**搜尋條件來搜尋特別的 Microsoft 小組中的內容。 
  - 若要使用的**類型**屬性的搜尋查詢時，[**關鍵字**] 方塊中的關鍵字搜尋查詢的一部分輸入`kind:microsoftteams`。

    ![在 [關鍵字] 方塊中使用種類： microsoftteams](media/O365-ContentSearch-Teams-Keywords.png)
  
  - 若要使用的搜尋條件，新增**郵件類型**條件並使用的值`microsoftteams`。 

    ![使用值 microsoftteams 訊息 kind 條件。](media/O365-ContentSearch-Teams-MessageKindCondition.png)

請注意**和**接線生就必定關鍵字查詢連接條件。這表示項目必須符合關鍵字查詢和搜尋結果中要傳回的搜尋條件。如需詳細資訊，請參閱中的"的使用情況的指導方針 」 一節[關鍵字查詢和搜尋條件的內容搜尋。](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)

  
### <a name="searching-inactive-mailboxes"></a>搜尋非使用中信箱

您可以在內容搜尋中搜尋非使用中信箱。若要取得組織中不在作用中信箱的清單，請執行命令`Get-Mailbox -InactiveMailboxOnly`在 Exchange Online PowerShell。或者，您可以移至**資料控管** \> **保留**安全性&amp;規範中心] 和 [**更多**![導覽列省略符號](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **不在作用中的信箱**。
  
以下是搜尋非使用中信箱時請牢記的一些事項。
  
- 如果內容搜尋包含使用者信箱，該信箱再進行非使用中內容的搜尋會繼續搜尋不在作用中的信箱時變成非使用中之後重新執行搜尋。
    
- 在某些情況下，使用者可能會有作用中的信箱，而非使用中的信箱具有相同的 SMTP 地址。在此例中，只選取作為內容的搜尋位置的特定信箱拼寫須符合。換句話說，如果您將使用者的信箱新增到搜尋，您不能假設其作用中且非使用中的信箱拼寫須符合;要搜尋的明確新增到搜尋的信箱。
    
- 我們強烈建議您避免擁有作用中信箱和非使用中的信箱使用相同的 SMTP 地址。如果您需要重複使用的目前指派給非使用中信箱的 SMTP 位址，我們建議您復原非使用中的信箱或非使用中信箱的內容還原至作用中的信箱 （或 [作用中信箱的封存），然後刪除非使用中的信箱。如需詳細資訊，請參閱下列主題：
    
  - [復原 Office 365 中不在作用中信箱](recover-an-inactive-mailbox.md)
    
  - [還原 Office 365 中的非使用中信箱](restore-an-inactive-mailbox.md)
    
  - [刪除非作用中的信箱在 Office 365](delete-an-inactive-mailbox.md)

  
### <a name="previewing-search-results"></a>預覽搜尋結果

您可以預覽在 [預覽] 窗格中支援的檔案類型。如果不支援的檔案類型，您必須下載到您要檢視其的本機電腦的檔案。下列檔案類型支援與可以在搜尋結果] 窗格中預覽。
  
- .txt、.html、.mhtml
    
- .eml
    
- .doc、.docx、.docm
    
- .pptm、.pptx
    
- .pdf
    
此外，支援下列檔案容器類型。您可以在 [預覽] 窗格容器中檢視檔案的清單。
  
- .zip
    
- .gzip
    
### <a name="partially-indexed-items"></a>部分已編製索引的項目

- 如先前所述、 部分已編製索引的信箱中的項目會包含在預估的搜尋結果;從 SharePoint 和 OneDrive 部分已編製索引項目並不包含在預估的搜尋結果中。 
    
- 如果部分項目符合搜尋查詢 （因為其他訊息或文件屬性符合搜尋準則），它將不會包含在估計編製索引的項目數。如果部分項目排除的搜尋準則、 它也不會包含在估計部分已編製索引的項目數。如需詳細資訊，請參閱[部分編製索引中的 Office 365 中的內容搜尋的項目](partially-indexed-items-in-content-search.md)。
    
### <a name="exporting-data-from-myanalytics-and-other-office-365-applications"></a>將資料匯出從 MyAnalytics 和其他 Office 365 應用程式

- MyAnalytics （例如在使用者如何花費工時以根據他們的信箱中的郵件和行事曆資料的觀點） 和其他 Office 365 應用程式中的資料會儲存至 （在非 IPM 樹狀子目錄） 使用者的雲端架構信箱中隱藏的位置。執行內容的搜尋之後，此資料不包含預估的搜尋結果中的查詢統計資料並不是可供預覽。但此資料會匯出時匯出搜尋結果。
    
- MyAnalytics 資料與其他 Office 365 應用程式中的資料匯出至名為 「 其他 Office 365 資料 」 的資料夾。這個資料夾包含每位使用者的子的資料夾。
  
