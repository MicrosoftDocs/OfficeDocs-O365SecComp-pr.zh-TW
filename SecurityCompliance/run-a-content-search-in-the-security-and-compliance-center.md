---
title: Office 365 安全性執行內容的搜尋&amp;規範中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ComplianceSearch
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 61852fd9-fe8a-4880-a339-cb19ed3bff4a
description: '使用 Office 365 安全性內容搜尋&amp;規範中心來搜尋信箱、 SharePoint Online 站台及 OneDrive for Business 位置。 '
ms.openlocfilehash: 61c6c3933a75567acb04f793cb6815322fb3fada
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526596"
---
# <a name="run-a-content-search-in-the-office-365-security-amp-compliance-center"></a>Office 365 安全性執行內容的搜尋&amp;規範中心

您可以使用 「 內容搜尋 eDiscovery 工具在 Office 365 安全性&amp;搜尋的項目如電子郵件、 文件和立即訊息交談 Office 365 組織中的規範中心。使用此工具來搜尋這些 Office 365 服務中的項目：
  
- Exchange Online 信箱及公用資料夾
    
- SharePoint Online 和 OneDrive for Business 的網站
    
- Skype 商務交談
    
- Microsoft Teams 
    
- Office 365 群組
    
內容搜尋是新的 eDiscovery 搜尋工具新增及改良的延展性與效能功能。使用內容搜尋執行非常大的 eDiscovery 搜尋。您可以搜尋所有信箱、 所有的 Exchange 公用資料夾中，所有 SharePoint Online 網站和 OneDrive 單一內容都搜尋中的商務帳戶。有無限制的可搜尋的內容位置數目而定。也有可以同時執行的搜尋數目沒有限制。之後執行內容搜尋] 的內容位置數目，並在**內容搜尋**] 頁面上的 [詳細資料] 窗格中顯示預估的搜尋結果數目。執行搜尋後您可以預覽結果、 取得關鍵字統計資料的一個或多個搜尋大量編輯內容的搜尋，並將結果匯出至本機電腦。 
  
 **目錄**
  
[建立搜尋](run-a-content-search-in-the-security-and-compliance-center.md#create)
  
[匯出搜尋結果](run-a-content-search-in-the-security-and-compliance-center.md#export)
  
[預覽搜尋結果](run-a-content-search-in-the-security-and-compliance-center.md#preview)
  
[更新搜尋結果](run-a-content-search-in-the-security-and-compliance-center.md#restart)
  
[編輯搜尋](run-a-content-search-in-the-security-and-compliance-center.md#edit)
  
[重試搜尋](run-a-content-search-in-the-security-and-compliance-center.md#retry)
  

  
## <a name="before-you-begin"></a>開始之前

- 資訊和指導建立搜尋查詢並使用布林搜尋運算子，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。本文也包含敏感資訊類型的搜尋及搜尋與您組織內部和外部人員共用內容的相關資訊。
    
- 若要有權限來執行搜尋和預覽和匯出搜尋結果的**內容搜尋**] 頁面上，系統管理員、 法務或 eDiscovery 管理員必須是安全性 eDiscovery 管理員角色群組的成員&amp;規範置中。您不需要額外的搜尋權限指派在 Exchange Online、 SharePoint Online、 或 for OneDrive Business 網站。如需詳細資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。
    
- 有限制套用至內容搜尋維護的健康狀況和至 Office 365 組織提供服務的品質。在大多數情況下，您無法修改這些限制，但您應該要知道有這些，讓您可以考量這些限制時規劃、 執行及疑難排解搜尋。如需詳細資訊，請參閱[Limits for Search in Office 365 安全性&amp;規範中心](limits-for-content-search.md)。
    
- 請參閱] 區段中的單一內容搜尋中搜尋的信箱數目為基礎的預估的搜尋時間。 
    
- 先前所述，您可以使用內容搜尋來搜尋 Office 365 群組與的 Microsoft 小組的內容。這表示您可以搜尋群組信箱、 共用的行事曆及與 Office 365 群組及 Microsoft 小組相關聯的 SharePoint 網站。此外，您可以搜尋通道交談中的 Microsoft 小組。如需 Office 365 群組及 Microsoft 小組資訊，請參閱：
    
  - [了解 Office 365 群組](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
    
  - [Microsoft 小組說明](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
    請參閱 Office 365 群組與的 Microsoft 小組的內容搜尋的提示 ＞ 小節。 
    
[回到頁首](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="create-a-search"></a>建立搜尋
<a name="create"> </a>

1. 移至 [ [https://protection.office.com](https://protection.office.com)。
    
2. 登入 Office 365 中，使用您工作或學校的帳戶。
    
3. 在安全性與合規性中心的左窗格中，按一下 [搜尋與調查]**** \> [內容搜尋]****。
    
4. 按一下 [**新增**![新增圖示](media/O365-MDM-CreatePolicy-AddIcon.gif)。
    
5. 在 [**新的搜尋**] 頁面上輸入內容搜尋的名稱。此名稱必須是唯一的組織中。 
    
6. 選擇您要搜尋的內容位置。您可以在相同的搜尋中搜尋信箱、 網站及公用資料夾。
    
    ![選擇您要搜尋的內容位置](media/da32e3f9-6cd6-4a26-8217-e97a5a7071e4.png)
  
1. **寄件人搜尋**選取此選項可在組織中搜尋所有內容的位置。當您選取這個選項時，您可以選擇搜尋所有信箱 （包括非使用中信箱與信箱的所有 Office 365 群組與的 Microsoft 小組），所有 SharePoint 和 OneDrive for Business 的網站 (包括 Office 365 的所有群組的網站和Microsoft 小組） 及所有公用資料夾。
    
    ![按一下 [搜尋寄件人搜尋內容的所有位置選項](media/86f132f1-0a2a-4048-900c-9f219d909ef2.png)
  
2. **自訂位置選取項目**選取此選項可選取的信箱與您想要搜尋的網站。如果您選擇這個選項，您有彈性來搜尋特定的服務 （例如搜尋所有的 Exchange 信箱） 的所有內容的位置或可搜尋 Office 365 服務的特定內容的位置。
    
    新增要搜尋的內容位置時，請記住下列：
    
    **信箱**
    
  - 當您按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)來指定要搜尋的信箱，會顯示信箱選擇是空的。這是由設計，以提升效能。若要新增至這份清單的收件者，在搜尋方塊中輸入的名稱 （至少要有 3 個字元） 並按一下 [**搜尋**]![搜尋圖示](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)。
    
  - 您可以將非使用中信箱和通訊群組新增至搜尋信箱清單。通訊群組、 要搜尋的群組成員的信箱。請注意動態通訊群組不受支援。
    
  - 若要取得組織中不在作用中信箱的清單，請執行命令`Get-Mailbox -InactiveMailboxOnly`在 Exchange Online PowerShell。或者，您可以移至**資料控管** \> **保留**安全性&amp;規範中心] 和 [**更多**![導覽列省略符號](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **不在作用中的信箱**。
    
  - 您也可以新增與 Office 365 群組或 Microsoft 小組關聯的信箱。在此例中，只有群組或小組信箱搜尋 ；群組或小組成員的信箱不搜尋。若要進行搜尋，您必須特別將它們新增至搜尋。
    
  - 如果您不想要包含於搜尋所有信箱，選取 [**選擇特定信箱搜尋**，但不要將信箱新增至清單。
    
    **網站**
    
  - 按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)網站新增至搜尋]。輸入您要搜尋的每個網站的 URL。內容搜尋工具會驗證 URL，並再將它新增至網站來搜尋的清單。 
    
  - 您可以新增 SharePoint 與 Office 365 群組或 Microsoft 小組相關聯。請參閱] 區段中的指導如何尋找群組或小組的 URL。 
    
  - 如果您不想要包含在搜尋中的任何網站中，選取 [**選擇要搜尋的特定網站**、 但不將網站新增至清單。
    
    **公用資料夾**
    
    公用資料夾，您可以選擇在 Exchange Online 組織中搜尋所有的公用資料夾或搜尋任何公用資料夾。
    
7. 按 [下一步]。
    
8. 您可以在 [**新的搜尋**] 頁面上新增關鍵字和條件來建立搜尋查詢。 
    
    ![使用關鍵字和條件建立搜尋查詢](media/1b7cf7b5-f1e1-471a-ad5c-48aad8435b00.png)
  
1. 在下] 方塊中**您想什麼我們要尋找的？**、] 方塊中輸入搜尋查詢。您可以指定關鍵字，訊息屬性例如傳送及接收日期或文件內容，例如檔案名稱或上次變更文件的日期。您可以使用較複雜的查詢使用布林運算子，例如**AND**、**或**、**不**、 **NEAR**或**ONEAR**。您也可以搜尋文件或搜尋功能已從外部共用的文件中的機密資訊 （例如社會安全編號）。如果 [關鍵字] 方塊中保留空白，將會在搜尋結果中包含位於指定之內容的位置中的所有內容。 
    
2. 您可以按一下 [**顯示關鍵字清單**] 核取方塊和類型中的每一列的關鍵字。如果您這樣做，在每一列的關鍵字連接**OR**運算子會建立搜尋查詢中所連接。 
    
    ![您可以在 [關鍵字] 清單中的列中輸入關鍵字或關鍵字階段](media/aea1a361-639d-4a82-8c3c-48645ef3fc05.png)
  
    為什麼要選擇使用 [關鍵字] 清單？您可以取得顯示多少個項目比對每個關鍵字的統計資料。這可協助您快速識別出哪些關鍵字是最 （且至少） 有效。您也可以使用 （以括弧括住） 的關鍵字文句] 列中。如需搜尋統計資料的詳細資訊，請參閱 ＜[檢視內容的搜尋結果的關鍵字統計資料](view-keyword-statistics-for-content-search.md)。
    
    請參閱的指引上使用 [關鍵字] 清單。 
    
3. 按一下 [**檢查查詢錯字**檢查查詢不受支援的字元與可能未接的布林運算子。不支援的字元通常隱藏與通常搜尋的錯誤或傳回非預期的結果。如需會檢查有不支援字元的詳細資訊，請參閱[檢查錯誤的內容搜尋查詢](check-your-content-search-query-for-errors.md)。
    
4. 在 [**條件**新增條件來縮小搜尋及傳回一組更精簡的結果在搜尋查詢。每個條件將子句新增至 KQL 搜尋查詢，建立及執行當您啟動搜尋。條件是以邏輯方式連線到 （在 [關鍵字] 方塊中指定） 的關鍵字查詢**和**運算子。這表示項目必須滿足的關鍵字查詢與結果中包含的條件。這是條件，縮減結果協助的方式。 
    
||
|:-----|
|如需建立搜尋查詢和使用情況的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。 |
   
9. 按一下 [**搜尋**] 以儲存搜尋設定並啟動搜尋。 
    
    啟動搜尋。搜尋完成時，下列資訊會顯示在 [詳細資料] 窗格中。
    
    ![在所選的內容搜尋的詳細資料窗格中顯示搜尋統計資料](media/2046bb5e-f4cb-4ba7-b7fc-8e5e53dae567.png)
  
1. 日期與時間的上次執行搜尋。
    
2. 數字 （和總大小） 的項目所找到的比對搜尋查詢。項目類型的範例包括電子郵件、 行事曆項目和文件。如果項目包含多個執行個體的搜尋關鍵字，它會只計算一次中的項目總數。例如，如果您搜尋的單字"stock"或"訣竅 」 及電子郵件訊息包含三個執行個體的"stock"這個字，其是只計算一次**項目**] 欄位中。 
    
3. 數量及編製索引中的項目所搜尋的內容位置的總大小。編製索引不符合搜尋準則的項目數將包含在詳細資料窗格中顯示的搜尋統計資料。如果搜尋查詢 （因為其他訊息或文件屬性符合搜尋準則） 編製索引的項目相符，則不會包含在估計編製索引的項目數。不過，如果編製索引的項目會排除的搜尋準則，它將不會包含在評估編製索引的項目。
    
4. 每種類型所搜尋的內容位置的編號。信箱，請注意所搜尋的信箱總數中所列的封存信箱。在上述範例中，所搜尋的四個使用者信箱並啟用每一個使用者的封存信箱。這就是為什麼八個信箱所引用中搜尋統計資料。
    
5. 連結至預覽搜尋結果或執行一次要更新的搜尋統計資料的搜尋。
    
    若有必要，請按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)更新所選搜尋的詳細資料窗格中的資訊。 
    
[回到頁首](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="export-search-results"></a>匯出搜尋結果
<a name="export"> </a>

成功執行搜尋之後，您可以將搜尋結果匯出到本機電腦。當您將電子郵件結果匯出時，他們正在為 PST 檔案下載到電腦。當您匯出 SharePoint 與內容 OneDrive for Business 的網站時，都要匯出的原生 Office 文件複本。也有其他文件和隨附匯出的搜尋結果的報告。如需詳細資訊，請參閱[匯出搜尋結果的 Office 365 安全性&amp;規範中心](export-search-results.md)。
  
## <a name="preview-search-results"></a>預覽搜尋結果
<a name="preview"> </a>

搜尋已順利完成之後，您可預覽搜尋結果。有限制相關預覽內容搜尋結果數目。如需詳細資訊，請參閱[Limits for Search in Office 365 安全性&amp;規範中心](limits-for-content-search.md)。請注意編製索引的項目不適用於預覽。
  
1. 在 [**內容搜尋**] 頁面上選取 [搜尋。 
    
2. 在 [詳細資料] 窗格中，[**結果**，請按一下 [**預覽搜尋結果**。**預覽搜尋結果**頁面會隨即開啟，並包含搜尋結果項目清單。 
    
    您可以按一下欄標題來排序結果取決於主旨、 類型、 寄件者或項目已接收到的來源信箱中的日期。
    
3. 按一下 [預覽項目。
    
    在 [預覽] 窗格中開啟項目。
    
4. 如果檔案類型不支援的預覽或下載文件的複本，您可以按一下 [**下載 [原始檔案**下載至您的本機電腦。針對.aspx 網頁，包含頁面的 URL 則但是您可能無法存取] 頁面上的權限。 
    
> [!NOTE]
> 如果您預覽搜尋結果的上次執行超過 7 天以上，系統會提示您更新的搜尋結果。搜尋會重新執行以取得最新符合搜尋查詢的結果。 
  
### <a name="file-types-that-can-be-previewed"></a>要預覽的檔案類型

您可以預覽在 [預覽] 窗格中支援的檔案類型。如果不支援的檔案類型，您必須下載到您要檢視其的本機電腦的檔案。下列檔案類型支援與可以預覽**預覽搜尋結果**頁面上。 
  
- .txt、.html、.mhtml
    
- .eml
    
- .doc、.docx、.docm
    
- .pptm、.pptx
    
- .pdf
    
此外，支援下列檔案容器類型。您可以在 [預覽] 窗格容器中檢視檔案的清單。
  
- .zip
    
- .gzip
    
[回到頁首](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="update-search-results"></a>更新搜尋結果
<a name="restart"> </a>

當您更新現有的內容搜尋結果時，搜尋查詢會重新執行所有指定的內容位置上。若要更新的搜尋結果明顯的原因是可以取得最新的資料。
  
1. 在**內容搜尋**頁面上，選取您想要更新結果的搜尋。 
    
2. 在 [詳細資料] 窗格中，[**結果**，請按一下 [**更新搜尋結果**。
    
    表示正在擷取結果的顯示狀態訊息。搜尋完成時，會顯示已更新的資訊 [**結果**詳細資料窗格中。請注意**在搜尋**欄位中詳細資料窗格中的日期會更新為目前日期與時間。若要重新整理的內容搜尋] 清單中的資訊，請按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)。
    
[回到頁首](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="edit-a-search"></a>編輯搜尋
<a name="edit"> </a>

您可以變更現有的內容搜尋的來源信箱和搜尋查詢。
  
1. 在 [**內容搜尋**] 頁面上選取 [搜尋。 
    
2. 在 [詳細資料] 窗格中 [**查詢**]，按一下 [**編輯搜尋**。
    
3. 在 [**位置**] 頁面中，您可以變更哪些信箱、 群組、 SharePoint 網站或 OneDrive for Business 的網站來搜尋。您也可以選取 （或未選取） 來搜尋 Exchange 中的所有公用資料夾。 
    
4. 在 [**查詢**] 頁面上，您可以編輯搜尋查詢。 
    
5. 若要啟動的修訂的搜尋、 按一下 [**來源**] 或 [**位置**] 頁面上的 [**搜尋**]。 
    
    便會啟動修訂的搜尋。搜尋完成時，修訂的搜尋的估計結果會顯示在詳細資料窗格中。
    
## <a name="retry-a-search"></a>重試搜尋
<a name="retry"> </a>

如果搜尋結果未傳回任何錯誤，您不需要重新搜尋所有內容的位置。您可以重新執行搜尋以便只有內容位置無法再次可搜尋。若要重新搜尋所有內容的位置，您可以更新的搜尋結果。
  
1. 在**內容搜尋**] 頁面上選取包含您想要重新搜尋的內容位置的搜尋。 
    
2. 在 [詳細資料] 窗格中的 [**錯誤**、 按一下 [**重試搜尋**。
    
    表示正在擷取結果的顯示狀態訊息。搜尋完成時，會顯示已更新的資訊下**結果**詳細資料窗格中。請注意**在搜尋**欄位中詳細資料窗格中的日期會更新為目前日期與時間。若要重新整理搜尋的清單中的資訊，請按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)。
    
[回到頁首](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="more-information"></a>其他資訊
<a name="moreinfo"> </a>

以下是內容搜尋的詳細資訊。
  
[限制與效能](run-a-content-search-in-the-security-and-compliance-center.md#limits)
  
[編製索引的項目](run-a-content-search-in-the-security-and-compliance-center.md#unindexeditems)
  
[Microsoft 小組與 Office 365 群組](run-a-content-search-in-the-security-and-compliance-center.md#teams)
  
[商務用 OneDrive](run-a-content-search-in-the-security-and-compliance-center.md#onedrive)
  
[搜尋查詢](run-a-content-search-in-the-security-and-compliance-center.md#queries)
  
[搜尋非使用中信箱](run-a-content-search-in-the-security-and-compliance-center.md#inactivemailboxes)
  
[其他](run-a-content-search-in-the-security-and-compliance-center.md#misc)
  
[（回到前）](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
 **限制與效能**
  
- 會套用至內容的搜尋功能的限制的說明，請參閱[Limits for Search in Office 365 安全性&amp;規範中心](limits-for-content-search.md)。
    
- Microsoft 收集所有 Office 365 組織所執行的內容搜尋的效能資訊。雖然搜尋查詢的複雜性可能會影響搜尋時間，搜尋會影響搜尋讓有的信箱數目多長的最大因素。雖然 Microsoft 不會提供搜尋時間服務層級協議下, 表列出根據包含在搜尋中的信箱數目內容搜尋平均搜尋時間。
    
|**信箱數目**|**平均搜尋時間**|
|:-----|:-----|
|100  <br/> |30 秒  <br/> |
|1,000  <br/> |45 秒  <br/> |
|10,000  <br/> |4 分鐘  <br/> |
|25000  <br/> |10 分鐘  <br/> |
|各 50000 個  <br/> |20 分鐘  <br/> |
|100,000  <br/> |25 分鐘  <br/> |
   

  
 **編製索引的項目**
  
- 為要搜尋的內容位置中先前所述、 編製索引的項目中會包含預估的搜尋結果。如果搜尋查詢 （因為其他訊息或文件屬性符合搜尋準則） 編製索引的項目相符，則不會包含在估計編製索引的項目數。如果編製索引的項目會排除的搜尋準則，它也不會包含在估計編製索引的項目數。如需詳細資訊，請參閱[在內容搜尋編製索引項目](https://go.microsoft.com/fwlink/p/?LinkId=780739)。
    

  
 **Microsoft 小組與 Office 365 群組**
  
- Office 365 群組之內建的 Microsoft 小組。因此，搜尋它們是非常類似。搜尋的 Microsoft 小組和 Office 365 群組中的內容時請記住下列事項。
    
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
    
  - 
    
    或者，是 [聊天室] 清單中的 Microsoft 小組的一部分的交談會儲存在 Exchange Online 信箱的使用者參與交談。與使用者共用聊天交談中的檔案都會儲存在 OneDrive for Business 共用檔案的使用者帳戶。因此，您必須新增個別使用者信箱和 OneDrive for Business 帳戶做為在 [聊天室] 清單中搜尋交談和檔案的內容位置。
    
    > [!NOTE]
    > 參與交談屬於 [聊天室] 清單中的 Microsoft 小組的使用者必須擁有為了讓您可以搜尋聊天室交談 Exchange Online （雲端型） 信箱。那是因為交談屬於 [聊天室] 清單會儲存在雲端架構信箱的交談參與者。如果交談參與者都不會有 Exchange Online 信箱，將不能夠搜尋交談的交談。例如，在 Exchange 混合部署，可能會能夠參與交談屬於 [聊天室] 清單中的 Microsoft 小組與內部部署信箱的使用者。但在此例中，這些交談的內容都可供搜尋因為使用者沒有雲端架構信箱。 
  
  - 每個 Microsoft 小組或小組通道包含 Wiki 筆記記錄與共同作業。Wiki 內容會自動儲存至含有.mht 格式的檔案。此檔案儲存在團隊的 SharePoint 網站上的小組 Wiki 資料文件庫。您可以使用 「 內容搜尋工具來搜尋 wiki （英文） 指定為要搜尋的內容位置的團隊的 SharePoint 網站。 
    
    > [!NOTE]
    > 搜尋 wiki （英文） 的 Microsoft 小組或通道 （如果您搜尋團隊的 SharePoint 網站） 的功能已於 2017 年 6 月 22 日發行。Wiki 頁面儲存或在更新的日期或之後可用來搜尋。上次儲存或更新的日期之前的 Wiki 頁面都可供搜尋。 
  

  
 **商務用 OneDrive **
  
- Onedrive for Business 您組織中的網站收集的 Url 清單，請參閱[建立的組織中的所有 OneDrive 位置清單](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。本文中的指令碼會建立包含的所有 OneDrive for Business 的網站清單的文字檔案。若要執行此指令碼，您必須安裝及使用 SharePoint Online 管理命令介面。請務必附加至每個 OneDrive for Business 想要搜尋的網站的組織的我的網站網域的 URL。這是包含所有您 OneDrive for Business; 的網域例如， `https://contoso-my.sharepoint.com`。以下是使用者的 OneDrive for Business 網站的 URL 範例： `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。
    

  
 **搜尋查詢**
  
- 使用 [關鍵字] 清單來建立搜尋查詢時保持記住下列事項。
    
  - 您必須選取 [**顯示關鍵字清單**] 核取方塊，然後輸入來建立搜尋查詢的個別資料列中的 [每個關鍵字其中每一列中的關鍵字 （或關鍵字片語） 連接所連接的**OR**運算子。如果您只是在 [關鍵字] 方塊中貼上關鍵字的清單或按下**Enter**鍵後輸入關鍵字，他們將不會透過**OR**運算子連接。以下是不正確和正確範例新增關鍵字的清單。 
    
    **不正確**
    
    ![不正確的方式來格式化關鍵字清單 （由貼入 [關鍵字] 方塊中的清單）](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **更正**
    
    ![正確的方式來格式化關鍵字清單 （由選取核取方塊，然後貼上清單）](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
  - 您可以也準備的關鍵字或 Excel 檔案或純文字檔案中的關鍵字詞清單然後複製並貼上您在關鍵字清單的清單。為達成此目的，您必須選取 [**顯示關鍵字清單**] 核取方塊。然後按一下 [關鍵字] 清單中的第一列並貼上您的清單。Excel 或文字檔案中的每一行會貼上中以 [關鍵字] 清單中的列分隔開。 
    
  - 建立查詢中使用 [關鍵字] 清單之後，根據確認搜尋查詢語法 （在所選搜尋的詳細資料窗格） 是以進行搜尋查詢是您對象。在詳細資料窗格中顯示 [**查詢**搜尋查詢，以文字 **(c:s)** 分隔的關鍵字。 這表示由**OR**運算子會連接到關鍵字。同樣地，如果您的搜尋查詢包含條件、 關鍵字及條件隔開文字 **（列）**。 這表示**AND**運算子將關鍵字連線至條件。以下是範例結果時使用 [關鍵字] 清單及條件的搜尋查詢 （顯示詳細資料窗格中）。 
    
    ![當使用關鍵字清單] 與 [條件時所建立的查詢的範例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
  - 如果您有包含非英文字元 （例如中文字元） 關鍵字搜尋查詢時，您可能必須使用**組 ComplianceSearch** cmdlet 可設定內容搜尋的 language 屬性。當您建立內容的搜尋安全性使用 GUI&amp;規範中心 」 的預設語言是中性。 
    
    您可以分清是否您需要變更內容的搜尋的語言設定？如果您是特定的內容位置包含非英文字元搜尋，但搜尋未傳回任何結果的語言設定可能原因。
    
    若要變更現有的內容搜尋的語言設定，請執行下列命令安全性&amp;規範中心 PowerShell：
    
  ```
  Set-ComplianceSearch <name of content search> -Language <culture code value>
  ```

    例如若要變更中文的語言設定，您可使用`zh-CN`的文化特性代碼值。變更語言設定之後，您必須重新執行搜尋。如需可行的文化特性代碼值的清單，請參閱[CultureInfo 類別](https://go.microsoft.com/fwlink/p/?LinkID=184859)。內容搜尋，我們建議您使用的語言設定 ； 值兩組件的文化特性代碼例如，`ja-JP`且未`ja`。
    

  
 **搜尋非使用中信箱**
  
先前所述，您可以在內容搜尋中搜尋非使用中信箱。以下是搜尋非使用中信箱時請牢記的一些事項。
  
- 如果內容搜尋包含使用者信箱，該信箱再進行非使用中內容的搜尋會繼續搜尋不在作用中的信箱時變成非使用中之後重新執行搜尋。
    
- 在某些情況下，使用者可能會有作用中的信箱，而非使用中的信箱具有相同的 SMTP 地址。在此例中，只選取作為內容的搜尋位置的特定信箱拼寫須符合。換句話說，如果您將使用者的信箱新增到搜尋，您不能假設其作用中且非使用中的信箱拼寫須符合;要搜尋的明確新增到搜尋的信箱。
    
- 我們強烈建議您避免擁有作用中信箱和非使用中的信箱使用相同的 SMTP 地址。如果您需要重複使用的目前指派給非使用中信箱的 SMTP 位址，我們建議您復原非使用中的信箱或非使用中信箱的內容還原至作用中的信箱 （或 [作用中信箱的封存），然後刪除非使用中的信箱。如需詳細資訊，請參閱下列主題：
    
  - [復原 Office 365 中不在作用中信箱](recover-an-inactive-mailbox.md)
    
  - [還原 Office 365 中的非使用中信箱](restore-an-inactive-mailbox.md)
    
  - [刪除非作用中的信箱在 Office 365](delete-an-inactive-mailbox.md)
    

  
 **其他**
  
- 內容建立安全性**內容搜尋**] 頁面上的搜尋&amp;規範中心不會在顯示**就地 eDiscovery&amp;保留**頁面上的 Exchange 系統管理中心。這是因為內容的搜尋架構與搜尋物件建立安全性&amp;規範中心會完全不同於 Exchange Online 中的就地 eDiscovery 功能。 
    
    有相同的原因建立**內容的搜尋**頁面上的搜尋不會在顯示 [**搜尋**] 頁面上的 eDiscovery 案例安全性&amp;規範中心。 
    
- 重新啟動和重試中搜尋之間的差異為何？當您重新啟動搜尋時，搜尋中指定的所有內容位置會在新的預覽搜尋再次搜尋。不過時再試一次搜尋，, 只失敗時上次執行搜尋的內容位置會再次搜尋。
   

