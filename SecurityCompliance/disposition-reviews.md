---
title: 處置檢查概覽
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 當您建立保留標籤, 以保留 Microsoft 365 中的內容時, 您可以選擇在保留期間結束時觸發處置檢查。
ms.openlocfilehash: 06b85d1ac4c8ed0527a8018129e146fee074d942
ms.sourcegitcommit: 044003455eb36071806c9f008ac631d54c64dde6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2019
ms.locfileid: "35199678"
---
# <a name="overview-of-disposition-reviews"></a>處置檢查概覽

當內容達到其保留期間的結尾時, 有幾個原因會讓您想要檢查內容, 以決定是否可以安全刪除 (「已釋放」)。 例如, 您可能需要:
  
- 在訴訟或審計的情況中, 暫止相關內容的刪除 (「處置」)。
    
- 如果內容有調研或歷史值, 請從 [處理] 清單中移除要儲存的內容。
    
- 將不同的保留期間指派給內容, 如果原始原則是暫時或臨時的解決方案。
    
- 將內容傳回給用戶端, 或將內容轉移至其他組織。
    
當您在 Microsoft 365 規範中心、Microsoft 365 安全性中心或 Office 365 安全性 & 合規性中心建立保留標籤時, 您可以選擇在保留期間結束時觸發處置檢查。 在處置評審中:
  
- 您選擇的人員會收到他們有內容可供審閱的電子郵件通知。 這些檢閱者可以是個別使用者、發佈或安全性群組, 或 Office 365 群組。 請注意, 每週會傳送通知。
    
- 檢閱者會移至**** 安全性&amp;與合規性中心中的 [部署] 頁面, 以查看內容。 檢閱者可以查看每個保留標籤中等待處理的專案數, 然後選取保留標籤, 以查看具有該標籤的所有內容。
    
- 對於每個檔或電子郵件, 檢閱者可以:
    
  - 套用不同的保留標籤。
    
  - 延長其保留期間。
    
  - 永久刪除它。
    
- 檢閱者可以查看擱置或已完成的處理, 並將該清單匯出為 .csv 檔案。

> [!NOTE]
> 處置評審需要 Office 365 企業版 E5 訂閱。
  
處置評審可包含 Exchange 信箱、SharePoint 網站、OneDrive 帳戶及 Office 365 群組中的內容。 只有在檢閱者選擇永久刪除內容之後, 才會刪除在這些位置等候處置評審的內容。
  
![安全性與合規性中心中的 [處置] 頁面](media/Retention-Dispositions-v2-page.png)

## <a name="setting-up-the-disposition-review-by-creating-a-retention-label"></a>建立保留標籤來設定處置評審

這是設定處置評審的基本工作流程。 請注意, 此流程會顯示已發佈的保留標籤, 然後由使用者手動套用;或者, 也可以將觸發處置評審的保留標籤自動套用至內容。
  
![圖表顯示處置的運作方式](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
當您在 Office 365 中建立保留標籤時, 會有一個選項可供使用。 請注意, 保留原則中不提供此選項, 只是設定為保留內容的保留標籤。
  
如需保留標籤的詳細資訊, 請參閱[保留標籤](labels.md)。
  
![標籤的保留設定](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a>處置內容

當檢閱者透過電子郵件收到內容供您審閱時, 他們可以移至安全性&amp;與合規性中心中的 [**部署**] 頁面。 檢閱者可以查看每個保留標籤中等待處理的專案數, 然後選取保留標籤, 以查看具有該標籤的所有內容。

在您選取保留標籤之後, 下一頁會顯示該標籤的所有暫止的處置。

![處理選項](media/Retention-Disposition-options-v2.png)

然後, 檢閱者可以: 
  
- 套用不同的保留標籤。
    
- 延伸保留期間。
    
- 永久刪除專案。

請注意, 檢閱者可以同時選取多個專案並將它們處置。
    
如果檢閱者有該位置的許可權, 則檢閱者也可以使用連結來查看其原始位置中的檔。 在處置檢查期間, 內容永遠不會從其原始位置移動, 也不會刪除, 直到檢閱者選擇這麼做。
  
請注意, 電子郵件通知會每週自動傳送給檢閱者。 因此, 當內容達到其保留期間的結尾時, 最多可能需要七天的時間, 讓檢閱者能夠收到內容正在等待處理的電子郵件通知。
  
另外請注意, 所有的處置動作都會經過審核。 若要確保如此, 您必須至少在第一次處理前的一天開啟審計-如需詳細資訊, 請參閱[Search the audit log in The Office &amp; 365 Security 合規性中心](search-the-audit-log-in-security-and-compliance.md)。 
  
## <a name="permissions-for-disposition"></a>處置的許可權

若要存取 [**處置**] 頁面, 檢閱者必須是「處理**管理**」角色的成員, 以及「**僅供查看的審核記錄**」角色。 我們建議您建立名為「處置檢閱者」的新角色群組, 將這兩個角色新增至該角色群組, 然後將成員新增至角色群組。 
  
如需詳細資訊, 請參閱[授與使用者存取 Office 365 &amp;安全性與規範中心](grant-access-to-the-security-and-compliance-center.md)
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a>在永久刪除已釋放的內容之前的時間

只有在檢閱者選擇永久刪除內容之後, 才會刪除等待處理考核的內容。 當檢閱者選擇此選項時, SharePoint 網站或 OneDrive 帳戶中的內容就符合本節所述的標準清理程式:[保留原則如何就地使用內容](retention-policies.md#how-a-retention-policy-works-with-content-in-place)。
  
這表示:
  
- 文件庫中的內容將會移至第一階段的回收站, **** 並在完成之前永久刪除**93 天**。 回收站不是由搜尋編制索引, 因此它的內容無法供 eDiscovery 保留使用。

- 在處理**7 天內**, 會永久刪除 [保留保留] 文件庫中的內容。

- Exchange 信箱中的專案會在部署**14 天內**永久刪除。 (請注意, 14 天是預設的設定, 但可設定為最多30天)。
    
## <a name="view-pending-dispositions-and-disposed-items"></a>查看擱置中的處置和釋放的專案

在 [**暫**止的處理] 頁面上, 您可以同時查看特定保留標籤的擱置和已完成的處理常式: 
  
- **擱置的處理**會顯示已到達保留期間結束且需要進行處置評審的專案。 檢查每個專案之後, 決定您是否要將不同的保留標籤套用至它、延伸保留期間或永久刪除。 您可以選取多個專案。
    
- [已**釋放的專案**] 索引標籤會顯示已核准在處置檢查期間刪除的處理常式, 而且目前已被永久刪除。 已套用不同保留標籤或其保留期間延伸為審閱一部分的專案將不會出現在這裡。

![處置索引標籤](media/Retention-Disposition-tabs.png)
    
### <a name="filter-the-disposition-views"></a>篩選處置視圖

您可以依保留標籤或時間範圍來篩選這些視圖。 針對暫止的處理, 時間範圍是以到期日為基礎。 針對已釋放的專案, 時間範圍是以刪除日期為基礎。
  
![處置篩選選項](media/Retention-filter-options.png)

### <a name="export-the-disposition-items"></a>匯出處置專案

此外, 您可以將其中一個視圖的專案匯出為您可以在 Excel 中開啟的 .csv 檔案。
  
![在 Excel 中匯出的處置資料](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

