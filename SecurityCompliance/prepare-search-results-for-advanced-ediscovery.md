---
title: 準備 Office 365 進階 eDiscovery 的搜尋結果
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: 了解如何準備 Office 365 安全性內容的搜尋結果&amp;規範中心供進一步分析與進階的 eDiscovery 工具。
ms.openlocfilehash: de96e06dcbb5ae9a3cbf80b66f976e6ffdfd5b0e
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296916"
---
# <a name="prepare-search-results-for-office-365-advanced-ediscovery"></a>準備 Office 365 進階 eDiscovery 的搜尋結果

與 Office 365 安全性 eDiscovery 案例具有相關聯的搜尋之後&amp;成功執行規範中心、 準備進一步分析與 Office 365 進階 eDiscovery 可讓您分析大型、 的搜尋結果非結構化的資料設定，並減少法律案例相關的資料量。進階的 eDiscovery 功能包括：
  
- **光學字元辨識**-當您在準備搜尋結果進階 eDiscovery 光學字元辨識 (OCR) 功能自動從圖像、 擷取文字及包含這與在載入至搜尋結果進階的 eDiscovery 的分析。OCR 支援寬鬆的檔案、 電子郵件附件、 和內嵌圖像。這可讓您將文字分析功能的進階 eDiscovery （接近重複項目、 電子郵件執行緒、 佈景主題及預測編碼） 套用至圖像檔案中的文字內容。進階的 eDiscovery OCR 影像檔支援下列格式：

    - GIF
    - JPEG
    - JPG
    - PNG
    - TIFF
    
- **接近重複資料偵測**-可讓您更有效率地建構資料檢閱讓某個人檢閱一群類似的文件。這有助於防止多位檢閱者不必檢視不同版本的相同文件。 
    
- **電子郵件執行緒**-可協助您識別唯一的郵件中的電子郵件執行緒讓您可以專注在僅限每則訊息中的新資訊。在電子郵件執行緒，第二個訊息會包含第一封郵件。同樣地，更新版本的訊息會包含所有先前的郵件。電子郵件超執行緒會需要檢閱每封郵件的電子郵件執行緒全文中移除。 
    
- **佈景主題**-幫助您取得寶貴洞察力有關您的資料超過剛關鍵字搜尋統計資料。佈景主題可協助調查來群組相關的文件讓您可以查看內容中的文件。時使用佈景主題，您可以檢視文件的一組相關的佈景主題、 決定任何重疊，並再識別 cross-sections 的相關資料。 
    
- **Predictive 編碼**-可讓您訓練上您要尋找的讓您進行決策 （是否有相關或不） 的系統上小型的文件。進階的 eDiscovery 然後套用該學習 （根據您的指引） 分析資料組中的文件的所有時。根據該學習、 進階的 eDiscovery 提供相關性排名，讓您可以決定哪些文件檢閱根據何種文件都很有可能是相關的案例。 
    
- **匯出資料的檢閱應用程式**-您也可以將資料匯出從進階的 eDiscovery 與 Office 365 後您已完成分析並減少資料集。匯出套件包含 CSV 檔案包含匯出的內容及分析中繼資料屬性。此匯出封裝則匯入至 eDiscovery 檢閱應用程式。 
    
## <a name="before-you-begin"></a>開始之前

- 若要分析使用進階的 eDiscovery 的使用者資料，使用者 (資料 okay) 必須指派 Office 365 E5 授權。或者，使用 Office 365 E1 或 E3 授權的使用者可以將指派進階的 eDiscovery 獨立授權。系統管理員及法務人員對於已指派給的情況下並使用進階的 eDiscovery 分析資料不需要的 E5 授權。 
    
- 您必須是 eDiscovery 管理員或 Office 365 安全性管理員 eDiscovery&amp;規範中心準備進階 eDiscovery 搜尋結果。EDiscovery 管理員是 eDiscovery 管理員角色群組的成員。EDiscovery 管理員也是 eDiscovery 管理員角色群組成員，但已指派其他 eDiscovery 權限。如需指派 eDiscovery 管理員權限的指示，請參閱[Office 365 安全性 & 規範中心中的 eDiscovery 案例](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)中的步驟 1。
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a>步驟 1： 準備搜尋結果進階 ediscovery （英文）

您可以準備與 eDiscovery 案例具有相關聯的搜尋結果。當您準備進階 eDiscovery 搜尋結果時，將資料上傳且暫時儲存在 Microsoft cloud 中唯一 Windows Azure 的儲存區中。此時會 OCR 功能會從搜尋結果中的影像擷取文字。在 [[步驟 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery)，此文字和其他搜尋結果的資料會載入至進階 ediscovery 案例。
  
1. 在安全性與合規性中心，按一下 [搜尋和調查]**** \> [電子文件探索]****，來顯示貴組織中的案例清單。 
    
2. 按一下您想要準備分析進階在 eDiscovery 中搜尋結果的大小寫] 旁的 [**開啟**]。 
    
3. 在 [**首頁**] 頁面的大小寫 [**搜尋**]，然後選取搜尋]。
    
4. 在詳細資料] 窗格中，[**具有進階 eDiscovery 的分析結果**，請按一下 [**準備進行分析的結果**。
    
    > [!NOTE]
    > 如果搜尋的結果是早於 7 天前，則會提示您更新搜尋結果。 
  
5. 在**準備供分析的結果**的頁面上，執行下列動作︰  
    
    - 選擇 [準備進階 ediscovery 分析已編製索引的項目、 已編製索引及編製索引項目或僅編製索引的項目。
    
    - 選擇是否要包含的文件符合搜尋準則的 SharePoint 上找到的所有版本。只有當搜尋的內容來源包含網站會出現此選項。
    
    - 指定是否要通知訊息傳送 （或複製） 來準備程序完成時的人員及資料已準備好進階 ediscovery 處理。
    
6. 按一下 [**準備**]。
    
    在搜尋結果已備妥與進階 eDiscovery 的分析。
    
7. 在 [詳細資料] 窗格中，按一下 [**檢查準備狀態**顯示的準備程序的相關資訊。準備程序完成時，您可以前往處理分析之資料的進階 ediscovery 案例。 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a>步驟 2： 將搜尋結果資料新增至進階 ediscovery 案例
<a name="step2"> </a>

準備完成時下, 一步是移至 [進階的 eDiscovery 及搜尋結果資料 （其已上載至 Azure 中儲存區 Microsoft cloud） 載入至進階 ediscovery 案例。如先前清楚存取您必須是 eDiscovery 安全性的系統管理員的進階的 eDiscovery&amp;規範中心或進階的 ediscovery 的管理員。
  
> [!NOTE]
> 所花費的時間之資料的安全性&amp;規範中心可新增至進階 ediscovery 案例而異，eDiscovery 搜尋結果的大小。 
  
1. 在安全性與合規性中心，按一下 [搜尋和調查]**** \> [電子文件探索]****，來顯示貴組織中的案例清單。 
    
2. 按一下您想要將資料載入的進階 ediscovery 案例] 旁的 [**開啟**]。 
    
3. 在案例的 [首頁]**** 頁面上，按一下 [進階電子文件探索]****。 
    
    ![若要開啟 [進階在 eDiscovery 中的 [大小寫的進階 ediscovery 按一下切換參數](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    會顯示 [**連線至進階 eDiscovery**進度列。當您連線至進階的 eDiscovery 時、 容器清單隨即顯示在 [安裝] 頁面的大小寫。 
    
    ![大小寫會顯示在進階的 eDiscovery](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     這些容器代表您準備進行分析的步驟 1 中的進階 eDiscovery 搜尋結果。請注意此容器的名稱會在安全性案例中具有相同名稱的搜尋&amp;規範中心。在清單容器是過您準備。如果不同的使用者準備進階 eDiscovery 搜尋結果，相對應的容器不會包含在清單中。 
    
4. 從容器中的搜尋結果資料載入進階 ediscovery 案例中，選取容器和 [**程序**。
    
## <a name="next-steps"></a>後續步驟

EDiscovery 的結果後搜尋會新增至案例中下, 一步是使用進階的 eDiscovery 工具來分析的資料並識別特定的法律案例回應的內容。如需使用進階的 eDiscovery 的資訊，請參閱[Office 365 進階 eDiscovery](office-365-advanced-ediscovery.md)。
  
## <a name="more-information"></a>詳細資訊

當您準備進階 ediscovery 分析會解密的搜尋結果中包含任何 RMS 加密電子郵件訊息。預設會啟用此解密功能的 eDiscovery 管理員角色群組的成員。這是因為 RMS 解密管理角色指派給此角色群組。保留有關解密電子郵件訊息記住下列事項：
  
- 目前此解密功能不包括商務網站的 SharePoint 和 OneDrive 加密的內容。當您將其匯出將解密僅 RMS 加密電子郵件訊息。
    
- 如果 RMS 加密電子郵件訊息的附件 （例如文件或另一個電子郵件訊息） 也加密，只有最上層的電子郵件將解密的郵件。
    
- 如果您需要防止其他人解密 RMS 加密郵件準備分析進階在 eDiscovery 中搜尋結果時，您必須複製以建立自訂角色群組 （內建的 eDiscovery 管理員角色群組），然後移除 RMS解密從自訂角色群組的管理角色。然後將新增您不想將郵件解密自訂角色群組的成員身分的人員。
