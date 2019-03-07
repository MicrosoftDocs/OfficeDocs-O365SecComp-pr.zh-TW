---
title: 處置檢閱概觀
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 當您建立的標籤，會保留在 Office 365 中的內容時，您可以選擇觸發處置檢閱的保留期間的結尾。
ms.openlocfilehash: 5dac91368ff2aff6ca7e1a2c3591b50466b869ac
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455035"
---
# <a name="overview-of-disposition-reviews"></a>處置檢閱概觀

當內容達到其保留期間結束時，有幾個理由為什麼您可能想要檢閱決定是否可將它安全地刪除該內容 （「 處置 」）。 例如，您可能需要：
  
- 擱置發生訴訟或稽核的相關內容的刪除 （「 處理 」）。
    
- 如果內容有 research 或歷程記錄的值，則您可以移除儲存在封存中，[處理] 清單內容。
    
- 如果原始的原則是暫時性或暫時性的解決方案，請將不同的保留期間指派給內容。
    
- 用戶端中傳回的內容，或將它轉接至另一個組織。
    
當您建立的標籤，會保留在 Office 365 中的內容時，您可以選擇觸發處置檢閱的保留期間的結尾。 在 [處置檢閱：
  
- 您選擇的人員會收到電子郵件通知他們有若要檢閱的內容。 這些檢閱者可以是個別使用者、 通訊群組或安全性群組或 Office 365 群組。 請注意，每週傳送通知。
    
- 檢閱者移至安全性中的 [**處理**] 頁面上&amp;合規性中心，以檢閱的內容。 
    
- 每份文件檢閱者可以：
    
  - 適用於不同的標籤。
    
  - 擴充其保留期間。
    
  - 永久刪除它。
    
- 檢閱者可以檢視擱置或歷史配置，並將該清單匯出成.csv 檔案。
    
請注意該處置檢閱需要 Office 365 企業版 E5 訂閱。
  
處置檢閱可以將內容包含在 Exchange 信箱、 SharePoint 網站、 OneDrive 帳戶和 Office 365 群組。 檢閱者選擇永久刪除內容之後，才會刪除送交處置檢閱在這些位置的內容。
  
![處理] 頁面](media/b7436fb2-1f35-4146-8ca2-32c9d10f7e09.png)
  
## <a name="setting-up-the-disposition-review-by-creating-a-label"></a>藉由建立標籤設定處置檢閱

這是設定處置檢閱的基本工作流程。 請注意，此流程顯示的標籤所發佈，然後手動套用的使用者;或者，觸發處置檢閱標籤可以是自動套用至內容。
  
![圖表顯示流量處理的運作方式](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
處置檢閱 Office 365 中建立標籤時的選項。 請注意，此選項不適用於保留原則，但只能在具有保留設定標籤。
  
如需標籤的詳細資訊，請參閱[標籤概觀](labels.md)。
  
![Label 的保留設定](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a>處置內容

當檢閱者會以電子郵件通知的內容已準備好檢閱，他們可以移至安全性中的 [**處理**] 頁面上&amp;規範中心和選取一或多個項目。 檢閱者可以： 
  
- 適用於不同的標籤。
    
- 擴充的保留期間。
    
- 永久刪除的項目。
    
檢閱者可以使用連結至其原始位置，以檢視文件檢閱者是否該位置的權限。 處置檢閱，期間內容永遠不會移動從原始位置，並永遠不會刪除前檢閱者選擇若要這麼做。
  
請注意，電子郵件通知會自動傳送給檢閱者以每週為基礎。 因此，當內容達到其保留期間結束時，可能需要多達七天的檢閱者收到電子郵件通知的內容會等待處理。
  
也請注意，稽核所有處理動作。 若要確保這種情況，您必須開啟稽核至少一天前的第一個的處理動作-如需詳細資訊，請參閱[搜尋稽核記錄以在 Office 365 安全性&amp;合規性中心](search-the-audit-log-in-security-and-compliance.md)。 
  
![文件的配置選項](media/771630fd-a9b0-47cf-983b-fe85eb4cdafd.png)
  
## <a name="permissions-for-disposition"></a>處理權限

若要存取 [**處理**] 頁面上，檢閱者必須**處理管理**角色和 「**僅檢視稽核記錄**」 角色的成員。 建議您建立新的角色群組，稱為處置檢閱者、 新增這兩個角色給該角色群組，並再新增成員至角色群組。 
  
如需詳細資訊，請參閱[讓使用者能夠存取 Office 365 安全性&amp;合規性中心](grant-access-to-the-security-and-compliance-center.md)
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a>處置的內容永久刪除之前的時間長度

檢閱者選擇永久刪除內容之後，才會刪除送交處置檢閱的內容。 當檢閱者選擇此選項時，SharePoint 網站或 OneDrive 帳戶中的內容會變成適合此一節所述的標準的清除程序：[將保留原則如何就地處理內容](retention-policies.md#how-a-retention-policy-works-with-content-in-place)。
  
這表示：
  
- 文件庫中的內容將會移至第一階段資源回收筒**7 天內**的處理，然後再後，永久刪除**93 天**。 資源回收筒無法搜尋編製索引，因此它的內容並不適用於 eDiscovery 保留。 
    
- 內容中保留保留文件庫將會永久刪除**7 天內**的處理。 
    
## <a name="view-pending-and-completed-dispositions"></a>檢視擱置和完成的配置

在 [**處理**] 頁面上的安全性&amp;合規性中心，您可以檢視擱置和完成配置： 
  
- **暫止**配置已達到其保留期間結束，且需要處置檢閱。 檢閱每個項目之後, 決定是否您想要將不同標籤套用至此、 擴充其保留期間，或永久刪除它。 
    
- **已完成**配置期間處置檢閱刪除已核准，現在正在永久刪除。 具有不同套用的標籤或擴充為檢閱的組件將不會出現在這裡其保留期間內的項目。 
    
### <a name="filter-the-disposition-views"></a>篩選處理檢視

您可以依標籤或時間範圍篩選這些檢視。 暫止的配置，時間範圍為基礎的到期日期。 歷史配置的時間範圍根據刪除日期。
  
![在 [處理] 頁面上的篩選選項](media/8682a9f5-a77d-45ae-b902-8418a3ebbea1.png)
  
### <a name="export-the-disposition-items"></a>匯出的處理項目

此外，您可以匯出檢視中的項目為.csv 檔案，您可以在 Excel 中開啟。
  
![在 Excel 中的匯出的處理資料](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

