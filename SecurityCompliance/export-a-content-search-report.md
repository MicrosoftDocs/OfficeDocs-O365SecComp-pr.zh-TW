---
title: 匯出內容搜尋報告
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: 而不是實際的 Office 365 安全性內容的搜尋結果匯出&amp;規範中心，您可以只將匯出的搜尋結果報表。報表會包含在搜尋結果和每個項目會匯出的詳細資訊與文件的摘要。
ms.openlocfilehash: d98f70d4f38f524de8751aecb197d0f85ee7f088
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295976"
---
# <a name="export-a-content-search-report"></a>匯出內容搜尋報告

而不是匯出完整的搜尋結果從 Office 365 安全性內容搜尋&amp;規範中心 （及內容搜尋與 eDiscovery 案例相關聯的），您可以只將匯出是同一個報表產生何時您匯出搜尋結果。
  
當您將報表匯出時，它會下載至具有相同名稱內容的搜尋，但會附加 *_ReportsOnly*的資料夾。例如，如果內容搜尋名稱為*ContosoCase0815* ，報表會下載至名為*ContosoCase0815_ReportsOnly*的資料夾。包含報表中的文件的清單，請參閱[報告中提供的功能](#whats-included-in-the-report)。

## <a name="before-you-begin"></a>開始之前

- 若要匯出內容搜尋報告，您必須要指派給 Office 365 安全性規範搜尋管理角色&amp;規範中心。此角色指派給內建的 eDiscovery 管理員和組織管理角色群組。它不是預設指派給組織管理角色群組。如需詳細資訊，請參閱[指派 Office 365 安全性 eDiscovery 權限&amp;規範中心](assign-ediscovery-permissions.md)。
    
- 當您將報表匯出資料會暫時儲存在 Microsoft cloud 中唯一 Windows Azure 的儲存區之前就會下載至您的本機電腦。請確定您的組織可以連線到 Azure，這是在端點**\*。 blob.core.windows.net** （萬用字元代表您匯出的唯一識別碼）。會在建立之後的兩週刪除搜尋結果資料從 Azure 儲存區。 
    
- 您要用來匯出搜尋結果的電腦必須符合下列系統需求：
    
  - Windows 7 和更新版本的 32 或 64 位元版本



    
  - Microsoft.NET Framework 4.7
    
  - 支援的瀏覽器：
    
    - Microsoft Edge
    
      或
    
    - Microsoft Internet Explorer 10 或更新版本
    
    **附註：** Microsoft 不會製造協力廠商擴充功能或 ClickOnce 應用程式的附加元件。不支援將匯出使用不受支援的瀏覽器與協力廠商擴充功能或附加元件的搜尋結果。 

- 如果內容的搜尋所傳回的結果的估計總大小超過 20&nbsp;TB、 匯出報表將會失敗。若要成功匯出報表，請嘗試縮小範圍並重新執行搜尋結果的估計的大小小於 20 讓&nbsp;TB。

- 匯出內容搜尋報告針對匯出執行於同一時間以及匯出單一使用者可以執行的最大數目的最大數目的計數。如需匯出限制的詳細資訊，請參閱[Office 365 安全性 & 規範中心匯出內容的搜尋結果](export-search-results.md#export-limits)。

## <a name="generate-and-download-a-content-search-report"></a>產生及下載的內容搜尋報告

產生及下載的內容搜尋報表的步驟是非常類似實際匯出搜尋結果。
  
## <a name="step-1-generate-the-report-for-export"></a>步驟 1： 產生匯出的報告

第一個步驟是準備報表下載到電腦匯出。當您報表，報表文件上傳至 Azure 中儲存區是由 Microsoft 雲端。
  
1. 移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 在安全性與合規性中心的左窗格中，按一下 [搜尋與調查]**** \> [內容搜尋]****。
    
4. 在 [**內容搜尋**] 頁面上選取 [搜尋。 
    
5. 在 [詳細資料] 窗格中，[**匯出至電腦的報告**，請按一下 [**產生報表**。
    
    > [!NOTE]
    > 如果超過 7 天的搜尋結果，系統會提示您更新的搜尋結果。如果發生這種情況，取消匯出、 選取搜尋的詳細資料] 窗格中按一下 [**更新搜尋結果**並更新結果之後再啟動報表匯出。 
  
6. 在**將報表匯出**] 索引標籤下**包含這些項目] 搜尋中的**，選擇下列選項之一：
    
    - 僅匯出已編製索引的項目
    
    - 匯出已編製索引和未編製索引的項目
    
    - 僅匯出未編製索引的項目
    
    如需編製索引的項目的詳細資訊，請參閱[部分編製索引內容的搜尋中的項目](partially-indexed-items-in-content-search.md)。
    
7. 選擇要包含的所有版本的 SharePoint 文件的搜尋統計資料。只有當內容來源的搜尋包含 SharePoint 或 OneDrive for Business 的網站會出現此選項。
    
8. 按一下 [**產生報表**。
    
    搜尋結果報表已備妥下載，這表示報表文件將上傳至 Microsoft 雲端中的 [Azure 存放區] 區域。備妥可供下載報表時，請**下載報告**連結將顯示 [**匯出至電腦的報告**詳細資料窗格中。 
    
> [!NOTE]
> 您也可以將報表匯出內容的搜尋與 eDiscovery 案例相關聯的。若要這樣做，請移至**搜尋&amp;調查** \> **eDiscovery**選取案例中，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。在 [**搜尋**] 頁面上選取 [搜尋] 和 [**匯出**![匯出搜尋結果圖示](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **將報表匯出**。 
  
## <a name="step-2-download-the-report"></a>步驟 2： 下載報告

下一步是從 Azure 儲存區的報表下載至本機電腦。
  
1. 在搜尋您產生的報告、 [**匯出至電腦的報告**詳細資料窗格中，按一下 [**下載報告**]。
    
    [**下載報告**] 頁面上會顯示並包含下列資訊直到報告下載到您的電腦。 
    
    - 將下載的項目數目。
    
    - 將下載的項目估計總數。
    
    - 將匯出編製索引或未建立索引。項目已辨識的格式、 加密，或未編製索引的其他原因會花很多項目。
    
    - 是否下載 SharePoint 文件的版本。
    
    - 報表匯出程序的狀態。您可以啟動即使未完成的報表準備下載報告。
    
2. **匯出金鑰**，請按一下 [**複製到剪貼簿**。您將在步驟 5 中使用此機碼下載報表。
    
    > [!IMPORTANT]
    > 因為任何人都可以安裝並啟動 eDiscovery 匯出工具，再使用此機碼下載搜尋報告，請務必採取預防措施就像您會保護密碼或其他安全性相關的資訊保護此機碼。 
  
3. 按一下 [**下載報告**。
    
4. 如果系統提示您安裝**MicrosoftOffice 365 eDiscovery 匯出工具**，請按一下 [**安裝**]。
    
5. 在**eDiscovery 匯出工具**中，貼上您在步驟 2 中適當的方塊中複製的匯出金鑰。
    
6. 按一下 [**瀏覽]** 以指定您要下載報告的位置。 
    
7. 按一下 [開始]**** 將搜尋結果下載至您的電腦。 
    
    **EDiscovery 匯出工具**會顯示狀態資訊匯出程序，包括評估會有數 （與大小） 的其餘的項目下載。匯出程序完成時，您可以存取已下載的所在位置的檔案。 
    
> [!NOTE]
> 您可以下載報告的內容搜尋與 eDiscovery 案例相關聯。若要這樣做，請移至**搜尋&amp;調查** \> **eDiscovery**選取案例中，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。在 [**匯出**] 頁面上選取 [匯出報表] 和 [**下載報告**詳細資料窗格中。 
  
## <a name="whats-included-in-the-report"></a>報告中提供的功能

如果您產生匯出相關內容的搜尋結果報表，下載下列文件：
  
- **匯出摘要**-Excel 文件包含匯出的摘要。這包括資訊例如所搜尋的內容來源數目、 從每個內容的位置、 估計項目數、 實際的將匯出的項目數的搜尋結果數目以及評估及實際大小的項目將匯出的。 
    
    > [!NOTE]
    > 如果您包括編製索引的項目匯出報表時，編製索引的項目數是預估的搜尋結果的總數與下載的搜尋結果 （如果您已將搜尋結果匯出） 中所列的總數匯出摘要報告。換句話說，將下載的項目總數等於評估結果總數及編製索引的項目總數。 
  
- **資訊清單**-內含搜尋結果中包含每個項目的相關資訊 （以 XML 格式） 的資訊清單檔案。 
    
- **結果**集的 Excel 文件包含一列的每個已編製索引的項目會匯出與搜尋結果的資訊。為電子郵件、 結果記錄檔包含每個郵件的資訊包括： 
    
  - 來源信箱中訊息的位置 (包括訊息位於主要或封存信箱)。
    
  - 送出或收到郵件的日期。
    
  - 郵件的主旨行。
    
  - 郵件的寄件者和收件者。
    
    文件從 SharePoint 和 OneDrive for Business 網站的結果記錄檔包含每個文件的資訊包括：
    
  - 文件的 URL。
    
  - 文件庫所在之網站集合的 URL。
    
  - 上次修改文件的日期。
    
  - (位於結果記錄檔中的 [主旨] 欄) 的文件名稱。
    
    > [!NOTE]
    > **結果**報表中的列數應該是等於會下載減去**編製索引的項目**] 報告中所列的項目數總計的搜尋結果的總數。 
  
- **編製索引的項目**-Excel 文件包含將搜尋結果中包含任何編製索引項目的相關資訊。如果您未包含編製索引的項目時產生搜尋結果報表，這份報告仍會下載，但會是空的。
