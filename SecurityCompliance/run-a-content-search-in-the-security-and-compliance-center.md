---
title: 在 Office 365 安全性執行內容搜尋&amp;合規性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ComplianceSearch
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 61852fd9-fe8a-4880-a339-cb19ed3bff4a
description: '在 Office 365 安全性中使用內容搜尋&amp;合規性中心來搜尋信箱、 SharePoint Online 網站和 OneDrive for Business 位置。 '
ms.openlocfilehash: 255d53240d360557dc6ff1370c8112ceea676622
ms.sourcegitcommit: 54a2cbe5d13f448e0c28655bdf88deb9e5434cac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/27/2019
ms.locfileid: "30935318"
---
# <a name="run-a-content-search-in-the-office-365-security-amp-compliance-center"></a>在 Office 365 安全性執行內容搜尋&amp;合規性中心

您可以使用內容搜尋電子文件探索工具在 Office 365 安全性&amp;若要搜尋的項目，例如電子郵件、 文件，並立即訊息交談中 Office 365 組織的合規性中心。 使用此工具來搜尋這些 Office 365 服務中的項目：
  
- Exchange Online 信箱與公用資料夾
    
- SharePoint Online 和 OneDrive for Business 網站
    
- Skype 商務交談
    
- Microsoft Teams 
    
- Office 365 群組
    
內容搜尋是新的 eDiscovery 搜尋工具新增和改善縮放和效能功能。 使用「內容搜尋」執行極大型的 eDiscovery 搜尋。 您可以搜尋所有信箱、 所有的 Exchange 公用資料夾，以及所有 SharePoint Online 網站與 OneDrive for 商務用帳戶，在單一的內容都搜尋中。 有，您可以搜尋的內容位置的數目沒有限制。 同時可以執行的搜尋數目也沒有限制。 之後您執行內容搜尋的內容位置數和預估的搜尋結果數目會顯示在 [**內容搜尋**] 頁面上的詳細資料窗格中。 執行搜尋之後，您可以預覽結果、 取得關鍵字統計資料的一個或多個搜尋大量編輯內容搜尋，並將結果匯出到本機電腦上。 
  
 **Contents**
  
[Create a search](run-a-content-search-in-the-security-and-compliance-center.md#create)
  
[匯出搜尋結果](run-a-content-search-in-the-security-and-compliance-center.md#export)
  
[Preview search results](run-a-content-search-in-the-security-and-compliance-center.md#preview)
  
[Update search results](run-a-content-search-in-the-security-and-compliance-center.md#restart)
  
[Edit a search](run-a-content-search-in-the-security-and-compliance-center.md#edit)
  
[Retry a search](run-a-content-search-in-the-security-and-compliance-center.md#retry)
  

  
## <a name="before-you-begin"></a>開始之前

- 建置相關資訊與指導搜尋查詢和使用布林搜尋運算子，請參閱 <<c0>關鍵字查詢和搜尋條件的內容搜尋。 本文也包含搜尋與您組織內部和外部的人員共用的內容，並搜尋敏感資訊類型的相關資訊。
    
- 若要擁有存取權來執行搜尋和預覽和匯出搜尋結果的 [**內容搜尋**] 頁面上，系統管理員、 法務人員或 eDiscovery 管理員必須是安全性中的 eDiscovery 管理員角色群組的成員&amp;合規性置中。 您不需要額外的搜尋將權限指派在 Exchange Online、 SharePoint Online 或 onedrive for Business 網站。 如需詳細資訊，請參閱[指派 Office 365 安全性中的 eDiscovery 權限&amp;合規性中心](assign-ediscovery-permissions.md)。
    
- 有限制套用到內容搜尋來維護的健康狀況和 Office 365 組織所提供的服務品質。 在大部分情況下，您無法修改這些限制，但您應注意這些限制以在進行規劃、執行和疑難排解搜尋時將這些限制納入考量。 如需詳細資訊，請參閱[適用於 Office 365 安全性中的搜尋限制&amp;合規性中心](limits-for-content-search.md)。
    
- 以預估的搜尋時間為基礎的單一內容搜尋中搜尋的信箱數目，請參閱一節。 
    
- 如先前所述，您可以使用內容搜尋來搜尋 Office 365 群組及 Microsoft Teams 中的內容。 這表示您可以搜尋群組信箱、 共用行事曆及與 Office 365 群組和 Microsoft 小組相關聯的 SharePoint 網站。 此外，您可以搜尋 Microsoft 小組通道交談。 如需 Office 365 群組和 Microsoft Teams 的詳細資訊，請參閱：
    
  - [了解 Office 365 群組](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
    
  - [Microsoft Teams 說明](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
    請參閱 Office 365 群組及 Microsoft Teams 中的內容搜尋的秘訣 > 一節。 
    
[回到頁首](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="create-a-search"></a>Create a search
<a name="create"> </a>

1. 移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 在安全性與合規性中心的左窗格中，按一下 [搜尋與調查]**** \> [內容搜尋]****。
    
4. 按一下 [**新增**![加入圖示](media/O365-MDM-CreatePolicy-AddIcon.gif)。
    
5. 在 [新增搜尋]**** 頁面上，輸入內容搜尋的名稱。 此名稱在您的組織中必須是唯一的。 
    
6. 選擇您想要搜尋的內容位置。 您可以在相同的搜尋來搜尋信箱、 網站及公用資料夾。
    
    ![選擇您想要搜尋的內容位置](media/da32e3f9-6cd6-4a26-8217-e97a5a7071e4.png)
  
1. **搜尋位置**選取此選項可搜尋組織中的所有內容位置。 當您選取此選項時，您可以選擇搜尋所有信箱 （包括非使用中信箱和信箱的所有 Office 365 群組和 Microsoft Teams），所有 SharePoint 和 OneDrive for Business 網站 (包括所有 Office 365 群組網站和Microsoft Teams)，及其所有的公用資料夾。
    
    ![按一下 [搜尋] 無所不在選項可搜尋所有內容位置](media/86f132f1-0a2a-4048-900c-9f219d909ef2.png)
  
2. **自訂位置選取項目**選取此選項以選取您想要搜尋的網站與信箱。 如果您選擇此選項，您有彈性，可搜尋的特定服務 （例如搜尋所有 Exchange 信箱） 的所有內容的位置，或您可以搜尋特定內容的位置，Office 365 服務。
    
    新增要搜尋的內容位置時，請牢記下列：
    
    **信箱**
    
  - 當您按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)若要指定要搜尋信箱，會顯示信箱選擇器是空的。 這項設計的目的是提升效能。 若要新增至這份清單的收件者，在 [搜尋] 方塊中輸入的名稱 （最少的 3 個字元），然後按一下 [**搜尋**![搜尋圖示](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)。
    
  - 您可以將非使用中信箱和通訊群組新增至要搜尋的信箱清單。 通訊群組、 會搜尋群組成員的信箱。 請注意，不支援動態通訊群組。
    
  - 若要取得您組織中的非使用中信箱的清單，請執行命令`Get-Mailbox -InactiveMailboxOnly`在 Exchange Online PowerShell。 或者，您可以移至 [**資料控管** \> **保留**安全性&amp;合規性中心，然後按一下 [**更多**![導覽列中省略符號](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **非使用中信箱**。
    
  - 您也可以新增與 Office 365 群組或 Microsoft 小組相關聯的信箱。 在此情況下，只有群組或小組信箱被搜尋;不搜尋群組或小組成員的信箱。 若要進行搜尋，您必須特別是將其新增至搜尋]。
    
  - 如果您不想要包含在搜尋任何信箱，選取**要搜尋的選擇特定信箱**，但不將信箱新增至清單。
    
    **網站**
    
  - 按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)將網站新增至搜尋]。 輸入您想要搜尋每個網站的 URL。 「 內容搜尋 」 工具會驗證 URL，並再將其新增至搜尋的網站清單。 
    
  - 您可以新增 SharePoint 與 Office 365 群組或 Microsoft 小組相關聯。 請參閱 < 如何尋找群組或小組的 URL 的相關指引 > 一節。 
    
  - 如果您不想要在搜尋中包含的所有網站，選取 [**選擇特定網站新增至搜尋**，但不將網站新增至清單。
    
    **公用資料夾**
    
    公用資料夾，您可以選擇搜尋 Exchange Online 組織中的所有公用資料夾或搜尋任何公用資料夾。
    
7. 按 [下一步]****。
    
8. 在 [新搜尋]**** 頁面上，您可以新增關鍵字和條件來建立搜尋查詢。 
    
    ![使用關鍵字和條件建立搜尋查詢](media/1b7cf7b5-f1e1-471a-ad5c-48aad8435b00.png)
  
1. 在 [您希望我們尋找什麼?]**** 下方的方塊，在方塊中輸入搜尋查詢。 您可以指定關鍵字、例如傳送和接收日期的郵件屬性，或者例如檔案名稱或文件上次變更的日期的文件屬性。 您可以使用更複雜的查詢，請使用布林運算子，例如**AND**、**或**、**不**、 **NEAR**或**ONEAR**。 您也可以搜尋 （如社會安全編號） 中的文件或外部共用的文件中搜尋的敏感資訊。 如果您將 [關鍵字] 方塊保留空白，位於指定的內容位置中的所有內容將會都包含在搜尋結果中。 
    
2. 您可以按一下**顯示關鍵字清單**] 核取方塊並輸入每一列中的關鍵字。 如果您這麼做時，每一列上的關鍵字來建立搜尋查詢中的**OR**運算子連線。 
    
    ![您可以在 [關鍵字] 清單中的資料列中輸入關鍵字或關鍵字階段](media/aea1a361-639d-4a82-8c3c-48645ef3fc05.png)
  
    為什麼要使用關鍵字清單？ 您可以取得顯示多少個項目比對每個關鍵字的統計資料。 這可協助您快速找出哪些關鍵字是最 （和至少） 有效。 您也可以使用 （以括號括住） 的關鍵字文句] 列中。 如需搜尋統計資料的詳細資訊，請參閱 <<c0>檢視的內容搜尋結果的關鍵字統計資料。
    
    使用關鍵字清單，請參閱指南 > 一節。 
    
3. 按一下 [檢查您的查詢不受支援的字元，以及可能不會被大寫的布林值運算子 [**檢查查詢錯字**。 不支援的字元通常隱藏和通常會造成搜尋錯誤或傳回非預期的結果。 如需會檢查不支援字元的詳細資訊，請參閱[檢查您的內容搜尋查詢有錯誤](check-your-content-search-query-for-errors.md)。
    
4. **條件**，將新增至搜尋查詢以縮小搜尋範圍，並傳回更精細的結果集的條件。 每個條件會將一個子句新增至 KQL 搜尋查詢，當您啟動搜尋時便會建立並執行。 條件會以 **AND** 運算子的邏輯方式連接至關鍵字查詢 (在關鍵字方塊中指定)。 這表示結果中包含的項目必須同時滿足關鍵字查詢與條件。 這就是條件如何協助您縮小搜尋結果。 
    
||
|:-----|
|如需有關建立搜尋查詢和使用條件的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。 |
   
9. 按一下 [搜尋]**** 以儲存搜尋設定並開始搜尋。 
    
    已啟動搜尋。 搜尋完成時，下列資訊會顯示在詳細資料窗格中。
    
    ![會在選取的內容搜尋的詳細資料窗格中顯示搜尋統計資料](media/2046bb5e-f4cb-4ba7-b7fc-8e5e53dae567.png)
  
1. 日期和時間上次執行搜尋。
    
2. 數字 （和大小總計） 的項目中所找到的符合搜尋查詢。 項目類型的範例包括電子郵件、 行事曆項目和文件。 如果項目中包含多個關鍵字，要搜尋的執行個體，它就只會計算一次中的項目總數。 例如，如果您搜尋的字詞 「 股票 」 或 「 工具提示 」，電子郵件訊息包含的 「 股票 」 這個字的三個執行個體，它就只會計算一次在 [**項目**] 欄位。 
    
3. 數目和所搜尋的內容位置中的未編製索引項目的總大小。 不符合搜尋準則的未建立索引的項目數會包含在詳細資料窗格中顯示的搜尋統計資料。 如果搜尋查詢 （因為其他郵件或文件的內容符合搜尋準則） 未編製索引的項目相符，就不會包括在估計的未編製索引的項目數目。 不過，如果未編製索引的項目會排除的搜尋準則，就不包括在未編製索引的項目估計值。
    
4. 每一種內容所搜尋的位置數目。 針對信箱，請注意所搜尋的信箱總數中所列的封存信箱。 在前一個範例中，所搜尋的四個使用者信箱並啟用每個這些使用者的封存信箱。 這就是為什麼搜尋統計資料中所引用八個信箱。
    
5. 連結以預覽搜尋結果，或者執行搜尋一次更新搜尋統計資料。
    
    如有必要，請按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)更新選取搜尋詳細資料窗格中的資訊。 
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="export-search-results"></a>匯出搜尋結果
<a name="export"> </a>

成功執行搜尋之後，您可以匯出到本機電腦上的搜尋結果。 當您匯出電子郵件結果時，其會以 PST 檔案下載到您的電腦。 當您匯出內容從 SharePoint 和 OneDrive for Business 網站時，匯出的原生 Office 文件複本。 匯出的搜尋結果中另外還有其他文件和報告。 如需詳細資訊，請參閱[匯出搜尋結果從 Office 365 安全性&amp;合規性中心](export-search-results.md)。
  
## <a name="preview-search-results"></a>預覽搜尋結果
<a name="preview"> </a>

成功完成搜尋之後，您可以預覽搜尋結果。 關於預覽內容搜尋結果有一些限制。 如需詳細資訊，請參閱[適用於 Office 365 安全性中的搜尋限制&amp;合規性中心](limits-for-content-search.md)。 請注意未編製索引的項目不適用於預覽。
  
1. 在 [**內容搜尋**] 頁面上，選取搜尋。 
    
2. 在詳細資料窗格中的 [結果]**** 底下，按一下 [預覽搜尋結果]****。[預覽搜尋結果]**** 頁面隨即開啟，並且包含搜尋結果項目的清單。 
    
    您可以按一下欄標題來排序結果根據主旨、 類型、 寄件者或來源信箱中收到郵件的日期。
    
3. 按一下 [若要預覽項目。
    
    在 [預覽] 窗格中開啟項目。
    
4. 如果預覽或下載一份文件，不支援的檔案類型，您可以按一下 [**下載原始的檔案**下載到本機電腦。 .aspx 網頁，但是您可能沒有權限來存取] 頁面上，會包含頁面的 URL。 
    
> [!NOTE]
> 如果您預覽 7 天之前所執行之搜尋的搜尋結果，系統會提示您更新搜尋結果。 搜尋是重新執行以取得最新符合搜尋查詢的結果。 
  
### <a name="file-types-that-can-be-previewed"></a>可以預覽的檔案類型

您可以預覽在 [預覽] 窗格中的受支援的檔案類型。 如果不支援的檔案類型，您必須檔案的複本下載到本機電腦來進行檢視。 下列檔案類型支援，且可以**預覽搜尋結果**頁面上預覽。 
  
- .txt、.html、.mhtml
    
- .eml
    
- .doc、.docx、.docm
    
- .pptm、.pptx
    
- .pdf
    
此外，也支援下列檔案容器類型。 您可以檢視檔案的清單容器中預覽窗格。
  
- .zip
    
- .gzip
    
[回到頁首](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="update-search-results"></a>更新搜尋結果
<a name="restart"> </a>

當您更新現有的內容搜尋結果時，搜尋查詢是重新執行指定的所有內容位置上。 若要更新的搜尋結果的明顯原因是要取得最新的資料。
  
1. 在**內容搜尋**頁面上，選取您想要更新結果的搜尋。 
    
2. 在詳細資料窗格中的 [結果]**** 底下，按一下 [**更新搜尋結果**]。
    
    狀態訊息隨即顯示，表示正在擷取結果。 搜尋完成時，更新的資訊會顯示在詳細資料窗格中的 [結果]**** 底下。 請注意，在詳細資料窗格中的 [搜尋]**** 欄位的日期會更新為目前日期和時間。 若要重新整理的內容搜尋] 清單中的資訊，請按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)。
    
[回到頁首](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="edit-a-search"></a>編輯搜尋
<a name="edit"> </a>

您可以變更來源信箱和搜尋查詢現有的內容搜尋。
  
1. 在 [**內容搜尋**] 頁面上，選取搜尋。 
    
2. 在詳細資料窗格中的 [查詢]**** 底下，按一下 [編輯搜尋]****。
    
3. 在 [**位置**] 頁面中，您可以變更哪些信箱、 群組、 SharePoint 網站或 OneDrive for Business 網站來搜尋。 您也可以選取 (或取消選取) 來搜尋 Exchange 中的所有公用資料夾。 
    
4. 在 [**查詢**] 頁面上，您可以編輯搜尋查詢。 
    
5. 若要啟動修訂的搜尋，按一下 [**來源**] 或 [**位置**] 頁面上的 [**搜尋**]。 
    
    便會啟動修訂的搜尋。 搜尋完成時，修訂的搜尋的估計結果會顯示在詳細資料窗格中。
    
## <a name="retry-a-search"></a>重試搜尋
<a name="retry"> </a>

如果搜尋結果未傳回任何錯誤，您不必重新搜尋的所有內容位置。 以便只失敗的內容位置是一次搜尋，您可以重新執行搜尋。 若要重新搜尋的所有內容的位置，您可以更新搜尋結果。
  
1. 在 [**內容搜尋**] 頁面上，選取包含您想要重新搜尋的內容位置搜尋。 
    
2. 在詳細資料窗格中的 [錯誤]**** 底下，按一下 [重試搜尋]****。
    
    狀態訊息隨即顯示，表示正在擷取結果。 搜尋完成時，更新的資訊會顯示在詳細資料窗格中的 [結果]**** 底下。 請注意，在詳細資料窗格中的 [搜尋]**** 欄位的日期會更新為目前日期和時間。 若要重新整理搜尋的清單中的資訊，請按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)。
    
[回到頁首](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="more-information"></a>其他資訊
<a name="moreinfo"> </a>

以下是相關內容搜尋的詳細資訊。
  
[限制和效能](#limits-and-performance)
  
[未編製索引的項目](#unindexed-items) 
 
[Microsoft Teams 和 Office 365 群組](#microsoft-teams-and-office-365-groups)
  
[商務用 OneDrive](#onedrive-for-business)
  
[搜尋查詢](#search-queries)
  
[搜尋非使用中信箱](#searching-inactive-mailboxes)
  
[其他工作](#miscellaneous)
  
[回到頁首](#before-you-begin)
  
### <a name="limits-and-performance"></a>限制和效能
  
- 會套用至內容的搜尋功能限制的說明，請參閱[適用於 Office 365 安全性中的搜尋限制&amp;合規性中心](limits-for-content-search.md)。
    
- Microsoft 會收集所有 Office 365 組織所執行的內容搜尋的效能資訊。 雖然複雜的搜尋查詢可能會影響搜尋的時間，搜尋會影響搜尋採取多久為的信箱數目的最大因素。 雖然 Microsoft 不會提供搜尋次數的服務層級協議下, 表會列出根據包含在搜尋中的信箱數目內容搜尋的平均搜尋時間。
    
|**信箱數量**|**平均搜尋時間**|
|:-----|:-----|
|100  <br/> |30 秒  <br/> |
|1,000  <br/> |45 秒  <br/> |
|10,000  <br/> |4 分鐘  <br/> |
|25000  <br/> |10 分鐘  <br/> |
|各 50000 個  <br/> |20 分鐘  <br/> |
|100,000  <br/> |25 分鐘  <br/> |
   
  
### <a name="unindexed-items"></a>未編製索引的項目
  
- 為要搜尋的內容位置中的先前所述，未編製索引項目會包含在預估的搜尋結果。 如果搜尋查詢 （因為其他郵件或文件的內容符合搜尋準則） 未編製索引的項目相符，就不會包括在估計的未編製索引的項目數目。 如果未編製索引的項目會排除的搜尋準則，它也不會包括在估計的未編製索引的項目數目。 如需詳細資訊，請參閱 <<c0>內容搜尋中的未編製索引項目。
    

  
### <a name="microsoft-teams-and-office-365-groups"></a>Microsoft Teams 和 Office 365 群組
  
- Microsoft Teams 之內建 Office 365 群組。 因此，這些搜尋是非常類似。 Microsoft Teams 和 Office 365 群組中的內容搜尋時，請記住下列事項。
    
  - 若要搜尋位於 Microsoft Teams 和 Office 365 群組的內容，您必須指定信箱和相關聯的小組或群組的 SharePoint 網站。
    
  - 執行**Get UnifiedGroup**指令程式在 Exchange Online 中檢視的 Microsoft Team 或 Office 365 群組內容。 這是一個好方法來取得與小組或群組相關聯的網站的 URL。 例如，下列指令會選取的內容顯示名為資深領導團隊的 Office 365 群組： 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > 若要執行**Get UnifiedGroup**指令程式，您必須獲指派 「 僅檢視收件者角色在 Exchange Online 或是角色群組的成員，才會有指派 「 僅檢視收件者 」 角色。 
  
  - 當使用者的信箱被搜尋時，將不會搜尋任何 Microsoft Team 或 Office 365 群組的使用者所屬的成員。 同樣地，當您搜尋 Microsoft Team 或 Office 365 群組，只有群組信箱和群組網站，您指定為搜尋;除非您明確地將它們加入搜尋，不會搜尋信箱和商務用 OneDrive 帳戶的群組成員。
    
  - 若要取得的 Microsoft Team 或 Office 365 群組成員的清單，您可以檢視上的內容**首頁\>群組**Office 365 系統管理中心] 頁面。 或者，您可以在 Exchange Online PowerShell 中執行下列命令： 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > 若要執行**Get UnifiedGroupLinks**指令程式，您必須獲指派 「 僅檢視收件者角色在 Exchange Online 或是角色群組的成員，才會有指派 「 僅檢視收件者 」 角色。 
  
  - 屬於 Microsoft Teams 通道的交談儲存在 Microsoft 小組與相關聯的信箱。 同樣地，小組成員共用通道中的檔案會儲存在小組的 SharePoint 網站上。 因此，您必須將 SharePoint 網站與 Microsoft 小組信箱新增為在通道中搜尋對話和檔案的內容位置。
    
  - 
    
    或者，屬於 Microsoft Teams 中的聊天室清單的交談會儲存在 Exchange Online 信箱的使用者參與聊天。 與使用者共用聊天交談中的檔案會儲存在商務用 OneDrive 帳戶的使用者共用檔案。 因此，您必須新增個別使用者信箱和 OneDrive 商務帳戶做為搜尋對話和檔案，在 [聊天室] 清單中的內容位置。
    
    > [!NOTE]
    > 參與 Microsoft Teams 中的聊天室清單的一部分的交談中的使用者必須具有 Exchange Online （以雲端為基礎） 中的信箱，您才能搜尋聊天交談。 這是因為是 [聊天室] 清單的一部分的交談會儲存在雲端式信箱的交談參與者。 如果交談參與者都不會有 Exchange Online 信箱，您無法搜尋聊天交談。 例如，在 Exchange 混合式部署中，使用內部部署信箱的使用者可能可以參與 Microsoft Teams 中的聊天室清單的一部分的交談。 不過在此情況下，這些對話中的內容不可以搜尋因為使用者不具有雲端式信箱。 
  
  - 每個 Microsoft Team 或小組通道包含 Wiki 筆記記錄及共同作業。 Wiki 內容會自動儲存至含有.mht 格式的檔案。 此檔案會儲存在小組的 SharePoint 網站上的 microsoft Teams Wiki 資料文件庫。 您可以使用 「 內容搜尋 」 工具來搜尋 Wiki 小組的 SharePoint 網站指定為要搜尋的內容位置。 
    
    > [!NOTE]
    > 若要搜尋 Wiki Microsoft Team 或通道 （當您搜尋小組的 SharePoint 網站） 的功能已於 2017 年 6 月 22 日發行。 Wiki 頁面儲存或更新的日期或之後可供搜尋。 上次儲存或更新該日期之前的 Wiki 頁面不適用於搜尋。 
  
### <a name="onedrive-for-business"></a>商務用 OneDrive
  
- Onedrive for Business 網站組織中收集的 Url 清單，請參閱[建立您組織中的所有 OneDrive 位置清單](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。 本文中的指令碼會建立文字檔，其中包含所有 OneDrive for Business 網站的清單。 若要執行此指令碼，您必須安裝並使用 SharePoint Online 管理命令介面。 請務必附加至每個商務用 OneDrive 網站，您想要搜尋的貴組織的我的網站網域的 URL。 這是包含所有您商務用 OneDrive; 的網域例如， `https://contoso-my.sharepoint.com`。 以下是使用者的 OneDrive for Business 網站的 URL 範例： `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。
    

### <a name="search-queries"></a>搜尋查詢
  
- 使用關鍵字清單來建立搜尋查詢時，請保持記住下列事項。
    
  - 您必須選取**顯示關鍵字清單**] 核取方塊，然後在要建立搜尋查詢的個別資料列中輸入每個關鍵字其中每一列中的關鍵字 （或關鍵字片語） 連接所連接**OR**運算子。 如果您只要在 [關鍵字] 方塊中貼上的關鍵字清單，或輸入關鍵字之後按**Enter**鍵，他們將不會透過**OR**運算子連接。 以下是不正確和正確新增的關鍵字清單的範例。 
    
    **不正確**
    
    ![若要設定關鍵字清單格式 （透過貼入 [關鍵字] 方塊中的清單） 不正確的方式](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **修正**
    
    ![若要設定關鍵字清單格式 （藉由選取核取方塊，然後貼上清單） 之正確方式](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
  - 您可以也準備一份關鍵字或關鍵字片語中的 Excel 檔案或純文字檔案，然後複製並貼上您的清單中 [關鍵字] 清單。 若要這麼做，您必須選取 [**顯示關鍵字清單**] 核取方塊。 然後，按一下 [關鍵字] 清單中的第一列，並貼上您的清單。 從 [Excel] 或 [文字檔案每一行會貼上中來分隔列在 [關鍵字] 清單中。 
    
  - 建立查詢中使用關鍵字清單之後，它是不錯的選項，若要確認搜尋查詢語法 （在選取的搜尋的詳細資料窗格） 中進行搜尋查詢是您的意思。 在 [詳細資料窗格中顯示**查詢**] 底下的搜尋查詢，關鍵字會以文字 **(c:s)** 隔開。 這表示關鍵字由**OR**運算子連線。 同樣地，如果您的搜尋查詢中包含的條件，關鍵字和條件就會以文字 **(c:c)** 隔開。 這表示**AND**運算子將關鍵字連線至條件。 以下是使用關鍵字清單和條件時，會產生搜尋查詢 （顯示在詳細資料窗格中） 的範例。 
    
    ![使用關鍵字清單和條件時，會建立查詢的範例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
  - 如果您有包含非英文字元 （例如中文字元為單位） 的關鍵字搜尋查詢，您可能必須使用**Set-compliancesearch** cmdlet 來設定內容搜尋的語言屬性。 當您建立 「 內容搜尋 」 安全性使用 GUI&amp;合規性中心的預設語言便是中性。 
    
    您可以告訴您是否要變更內容搜尋的語言設定？ 如果您是特定內容的位置包含您要搜尋的非英文字元，但搜尋作業沒有傳回任何結果的語言設定可能的原因。
    
    若要變更現有的內容搜尋的語言設定，請執行下列命令中安全性&amp;合規性中心 PowerShell:
    
  ```
  Set-ComplianceSearch <name of content search> -Language <culture code value>
  ```

    例如，若要變更中文的語言設定，您可以使用`zh-CN`文化特性代碼值。 變更語言設定之後，您必須重新執行搜尋。 如需可能的文化特性代碼值的清單，請參閱[CultureInfo 類別](https://go.microsoft.com/fwlink/p/?LinkID=184859)。 內容搜尋，我們建議您使用的語言設定值; 兩個部分文化特性代碼例如，`ja-JP`和 not `ja`。
    

### <a name="searching-inactive-mailboxes"></a>搜尋非使用中信箱
  
如先前所述，您可以在內容搜尋中搜尋非使用中信箱。 以下是搜尋非使用中信箱時，請牢記的一些事項。
  
- 如果內容搜尋包含使用者信箱，而且該信箱接著就會成為非使用中，內容搜尋會繼續搜尋非使用中的信箱，當您重新執行搜尋後變成非使用中。
    
- 在某些情況下，使用者可能會有作用中信箱和擁有相同的 SMTP 地址不在作用中信箱。 在此情況下，只有您選取 [內容搜尋的位置為特定的信箱可供搜尋。 也就是說，如果您將使用者的信箱新增至搜尋時，您不能假定，其作用中且非使用中的信箱可供搜尋;將搜尋明確新增至搜尋的信箱。
    
- 我們強烈建議您避免有作用中信箱和非使用中信箱的相同的 SMTP 地址。 如果您要重複使用目前指派給非使用中信箱的 SMTP 地址，我們建議您復原非使用中信箱或非使用中信箱的內容還原至作用中信箱 （或 [作用中信箱的封存），然後刪除非使用中信箱。 如需詳細資訊，請參閱下列主題：
    
  - [復原非使用中信箱 Office 365 中](recover-an-inactive-mailbox.md)
    
  - [還原 Office 365 中的非使用中信箱](restore-an-inactive-mailbox.md)
    
  - [刪除 Office 365 中的非使用中信箱](delete-an-inactive-mailbox.md)
    
### <a name="miscellaneous"></a>雜項
  
- 內容搜尋安全性中的 [**內容搜尋**] 頁面上建立&amp;合規性中心不會顯示在**就地 eDiscovery&amp;保留**Exchange 系統管理中心] 頁面。 這是因為內容的搜尋架構和搜尋物件建立安全性&amp;合規性中心是完全不同於 Exchange Online 中就地 eDiscovery 」 功能。 
    
    基於同樣的理由，建立**內容搜尋**] 頁面上的搜尋不會顯示在 [**搜尋**] 頁面上的 eDiscovery 案例中安全性&amp;合規性中心。 
    
- 重新啟動與重試搜尋之間有何差異？ 當您重新啟動搜尋時，搜尋中指定的所有內容位置會在新的預覽搜尋一次搜尋。 不過，當您重試搜尋，只失敗上次執行搜尋的內容的位置會一次搜尋。
   

