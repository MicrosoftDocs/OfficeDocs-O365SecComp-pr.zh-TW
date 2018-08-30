---
title: 在 Office 365 進階電子文件探索中執行處理程序模組及載入資料
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: '了解如何使用 Office 365 安全性&amp;規範中心以存取 Office 365 進階 eDiscovery 及執行程序模組中的案例。  '
ms.openlocfilehash: 32052bccc37d20c8707a1efb0592f7c93daf3590
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526764"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a>在 Office 365 進階電子文件探索中執行處理程序模組及載入資料

> [!NOTE]
> 進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
本節中的 [進階的 eDiscovery 程序模組的功能。 
  
除了檔案資料檔案類型、 副檔名、 位置或路徑、 建立日期及時間、 author、 okay、 和主旨等的中繼資料可以載入至進階 eDiscovery 及儲存的每個案例。有些中繼資料會計算進階 eDiscovery，例如原生檔案會載入時。 
  
進階的 eDiscovery 提供系統的中繼資料值，例如接近重複群組或相關性分數。由系統管理員就可以新增其他中繼資料，例如檔案註釋。 
  
## <a name="running-process"></a>執行程序

> [!NOTE]
> 批次指派編號檔案程序期間允許的檔案追蹤。批次數目也可讓重新處理選項的程序批次的識別。其他篩選器可用來篩選的批次數目和工作階段。 
  
請執行下列步驟來執行程序。
  
1. [開啟的 Office 365 安全性&amp;規範中心](go-to-the-securitycompliance-center.md)。 
    
2. 移至 [**搜尋&amp;調查** \> **eDiscovery** ] 和 [**移至 [進階 eDiscovery**。
    
3. 進階 eDiscovery 中選取適當的案例中顯示的**情況下**] 頁面上，按一下 [**移至 [大小寫**。
    
4. 在 [**準備** \> **程序** \> **安裝程式**、 選取清單中的可用容器的容器。
    
    ![按一下 [新增至大小寫的搜尋結果的程序](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. 如果您想要作為植入的檔案或前標記檔案新增容器，請按一下 [**進階設定...** ]。 
    
    使用加速問題的訓練與低豐富植入的檔案 (通常是 2%或更少)。針對植入的檔案，建議您選取各種確定相關的檔案和程序的相關 20 50 種子個別 （太多植入檔案可以扭曲相關性結果） 的問題。將訓練問題相同者所應該檢閱植入的檔案。
    
    使用預先標記的檔案來自動化相關性訓練。您應該標記至少 1500 檔案，並保持的非相關的檔案與圖形成比例集合新增至相關性相同。這些檔案應該手動標記，以及您應該有信心以標記的品質。
    
    ![這個螢幕擷取畫面的進階設定] 頁面上處理批次檔案](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - 在 [**植入**] 區段中： 
    
    選擇 [**標示為植入的檔案**，將容器標示為植入的檔案。您也需要選擇將它們從**問題**下拉式指派每個問題。從**標籤**] 下拉式清單中選擇**相關**或**不相關**。 
    
    > [!NOTE]
    > 一旦您作為**植入**設定檔，您無法將它們標示為**預先標記**。 
  
  - 在 [**預先標記的檔案**] 區段中： 
    
    選擇 [**標示為預先標記檔案**標示為預先標記檔案的容器。您也需要將它們從**問題**下拉式指派每個問題。從**標籤**] 下拉式清單中選擇**相關**或**不相關**。 
    
    > [!NOTE]
    > 一旦您為**預先標記**設定檔，您無法將其標示為**植入**。 
  
  - 在 [**電子郵件標記**] 區段中。已處理的電子郵件的哪一部分要標示為植入或前已標記的設定。 
    
6. 若要開始，按一下 [**程序**。完成時，會顯示的程序結果。
    
7. （選用）如果您需要將指派給特定 okay 的資料來源，您可以新增和編輯中**Custodians** okay 名稱\> **Custodians**中的**管理**] 和 [指派 custodians \> **指派**。 
    
如果您新增至案例，然後您可以處理一次。
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[檢視程序模組結果](view-process-module-results-in-advanced-ediscovery.md)

