---
title: 處置檢閱概觀
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 當您建立的保留標籤，會保留在 Microsoft 365 中的內容時，您可以選擇觸發處置檢閱的保留期間的結尾。
ms.openlocfilehash: 1828f4055e9048260db7d16df8ad87db36438211
ms.sourcegitcommit: 799a958fcac643f62dfac6fa04020f2f4758635c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30997259"
---
# <a name="overview-of-disposition-reviews"></a>處置檢閱概觀

當內容達到其保留期間結束時，有幾個理由為什麼您可能想要檢閱決定是否可將它安全地刪除該內容 （「 處置 」）。 例如，您可能需要：
  
- 擱置發生訴訟或稽核的相關內容的刪除 （「 處理 」）。
    
- 如果內容有 research 或歷程記錄的值，則您可以移除儲存在封存中，[處理] 清單內容。
    
- 如果原始的原則是暫時性或暫時性的解決方案，請將不同的保留期間指派給內容。
    
- 用戶端中傳回的內容，或將它轉接至另一個組織。
    
當您建立 Microsoft 365 合規性中心、 Microsoft 365 安全中心或 Office 365 安全性 & 合規性中心中的保留標籤時，您可以選擇觸發處置檢閱的保留期間的結尾。 在 [處置檢閱：
  
- 您選擇的人員會收到電子郵件通知他們有若要檢閱的內容。 這些檢閱者可以是個別使用者、 通訊群組或安全性群組或 Office 365 群組。 請注意，每週傳送通知。
    
- 檢閱者移至安全性中的 [**處理**] 頁面上&amp;合規性中心，以檢閱的內容。 檢閱者可以查看每一個保留標籤多少個項目正在等待處理，，然後選取 [保留標籤若要查看具有該標籤的所有內容。
    
- 每個文件或電子郵件，檢閱者可以：
    
  - 適用於不同的保留標籤。
    
  - 擴充其保留期間。
    
  - 永久刪除它。
    
- 檢閱者可以檢視擱置或完成的配置，並將該清單匯出成.csv 檔案。

> [!NOTE]
> 處置檢閱需要 Office 365 企業版 E5 訂閱。
  
處置檢閱可以將內容包含在 Exchange 信箱、 SharePoint 網站、 OneDrive 帳戶和 Office 365 群組。 檢閱者選擇永久刪除內容之後，才會刪除送交處置檢閱在這些位置的內容。
  
![安全性與合規性中心的配置頁面](media/Retention_Dispositions_v2_page.png)

## <a name="setting-up-the-disposition-review-by-creating-a-retention-label"></a>藉由建立保留標籤設定處置檢閱

這是設定處置檢閱的基本工作流程。 請注意，此流程顯示保留標籤要發佈，然後手動套用的使用者;或者，觸發處置檢閱保留標籤可以是自動套用至內容。
  
![圖表顯示流量處理的運作方式](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
處置檢閱 Office 365 中建立的保留標籤時的選項。 請注意，此選項不適用於保留原則，但只有在已設定為保留內容保留標籤。
  
如需保留標籤的詳細資訊，請參閱 < <b0>Overview of 保留標籤</b0>。
  
![Label 的保留設定](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a>處置內容

當內容已準備好要檢閱，他們可以移至安全性中的 [**處理**] 頁面上，檢閱者會以電子郵件通知&amp;合規性中心。 檢閱者可以查看每一個保留標籤多少個項目正在等待處理，，然後選取 [保留標籤若要查看具有該標籤的所有內容。

您選擇保留標籤之後下, 一個頁面會顯示該標籤的所有暫止配置。

![處理選項](media/Retention_Disposition_options_v2.png)

檢閱者可以： 
  
- 適用於不同的保留標籤。
    
- 擴充的保留期間。
    
- 永久刪除的項目。

請注意檢閱者可以選取多個項目，並處置它們在同一時間。
    
檢閱者是否該位置的權限檢閱者也可以檢視文件在其原始位置，使用連結。 處置檢閱，期間內容永遠不會移動從原始位置，並永遠不會刪除前檢閱者選擇若要這麼做。
  
請注意，電子郵件通知會自動傳送給檢閱者以每週為基礎。 因此，當內容達到其保留期間結束時，可能需要多達七天的檢閱者收到電子郵件通知的內容會等待處理。
  
也請注意，稽核所有處理動作。 若要確保這種情況，您必須開啟稽核至少一天前的第一個的處理動作-如需詳細資訊，請參閱[搜尋稽核記錄以在 Office 365 安全性&amp;合規性中心](search-the-audit-log-in-security-and-compliance.md)。 
  
## <a name="permissions-for-disposition"></a>處理權限

若要存取 [**處理**] 頁面上，檢閱者必須**處理管理**角色和 「**僅檢視稽核記錄**」 角色的成員。 建議您建立新的角色群組，稱為處置檢閱者、 新增這兩個角色給該角色群組，並再新增成員至角色群組。 
  
如需詳細資訊，請參閱[讓使用者能夠存取 Office 365 安全性&amp;合規性中心](grant-access-to-the-security-and-compliance-center.md)
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a>處置的內容永久刪除之前的時間長度

檢閱者選擇永久刪除內容之後，才會刪除送交處置檢閱的內容。 當檢閱者選擇此選項時，SharePoint 網站或 OneDrive 帳戶中的內容會變成適合此一節所述的標準的清除程序：[將保留原則如何就地處理內容](retention-policies.md#how-a-retention-policy-works-with-content-in-place)。
  
這表示：
  
- 文件庫中的內容將會移至第一階段資源回收筒**7 天內**的處理，然後再後，永久刪除**93 天**。 資源回收筒無法搜尋編製索引，因此它的內容並不適用於 eDiscovery 保留。

- 內容中保留保留文件庫將會永久刪除**7 天內**的處理。

- 在 Exchange 信箱中的項目將會永久刪除**14 天內**的處理。 （請注意的預設設定是 14 天，但是可以設定中設定為 30 天）。
    
## <a name="view-pending-dispositions-and-disposed-items"></a>檢視擱置配置及處置項目

在**擱置處置**頁面上，您可以檢視擱置和完成配置的特定保留標籤： 
  
- **擱置處置**顯示已達到其保留期間結束且需要處置檢閱項目。 檢閱每個項目之後, 決定是否您想要將不同的保留標籤套用至此、 擴充其保留期間，或永久刪除它。 您可以選取多個項目。
    
- **處置項目**] 索引標籤顯示配置已核准為待刪除期間處置檢閱，以及現在正在永久刪除。 有不同的保留標籤套用或延伸一部分檢閱其保留期間內的項目不會出現在這裡。

![處理] 索引標籤](media/Retention_Disposition_tabs.png)
    
### <a name="filter-the-disposition-views"></a>篩選處理檢視

您可以篩選這些檢視以保留標籤或時間範圍。 暫止的配置，時間範圍為基礎的到期日。 處置項目的時間範圍根據刪除日期。
  
![處理篩選選項](media/Retention_filter_options.png)

### <a name="export-the-disposition-items"></a>匯出的處理項目

此外，您可以匯出檢視中的項目為.csv 檔案，您可以在 Excel 中開啟。
  
![在 Excel 中的匯出的處理資料](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

