---
title: 管理 Office 365 中的資料管理
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 5/9/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 48064107-fed2-4db0-9e5c-aa5ddd5ccb09
description: 資料控管是保持周圍需要其資料及取得相關的所有刪除它時您不要。與 Office 365 中的資料控管，您可以從匯入及儲存的開頭建立原則的保留與永久刪除內容結尾的資料管理的內容完全的生命週期。
ms.openlocfilehash: ca3443c3b90a067bf171ddf89be604d262a7b9a4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527271"
---
# <a name="manage-data-governance-in-office-365"></a>管理 Office 365 中的資料管理

資料控管是保持周圍需要其資料及取得相關的所有刪除它時您不要。與 Office 365 中的資料控管，您可以從匯入及儲存的開頭建立原則的保留與永久刪除內容結尾的資料管理的內容完全的生命週期。
  
## <a name="import"></a>匯入

有些資料可能會儲存在雲端，類似的內部伺服器或協力廠商應用程式的外的位置。匯入服務可讓您更輕鬆將帶您的通訊、 SharePoint 及 OneDrive 商務資料到 Office 365 中，藉由上載直接透過網路或對我們傳送加密的磁碟機。您也可以使用的匯入服務中的智慧型匯入功能來篩選實際取得匯入至目標信箱的 PST 檔案中的項目。 
  
- [將 PST 檔案匯入 Office 365 的概觀](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)
    
- [使用網路上傳將 PST 檔案匯入 Office 365](use-network-upload-to-import-pst-files.md)
    
- [使用磁碟機運送將 PST 檔案匯入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- [使用 PST 集合工具來尋找、 複製及刪除組織中的 PST 檔案](find-copy-and-delete-pst-files-in-your-organization.md)
    
- [篩選資料時將 PST 檔案匯入 Office 365](filter-data-when-importing-pst-files.md)
    
- [使用 PowerShell Cmdlet 將內部部署內容上傳到 SharePoint Online](https://support.office.com/article/555049c6-15ef-45a6-9a1f-a1ef673b867c)
    
## <a name="govern-i-store-data"></a>控管 i： 儲存資料

匯入資料之後，您可能需要增加您儲存。不受限制的封存功能 （稱為自動展開封存） 的 Office 365 中提供不受限制的封存信箱中的儲存空間量。
  
- [啟用封存信箱在 Office 365 安全性&amp;規範中心](enable-archive-mailboxes.md)

- [Office 365 中不受限制封存概觀](unlimited-archiving.md)
    
- [啟用 Office 365 中沒有限制之封存](enable-unlimited-archiving.md)
    

    
## <a name="govern-ii-create-policies-and-labels-to-retain-content"></a>控管 ii 部分： 建立原則和保留內容的標籤

保留原則可協助您符合主動產業規定與內部原則來確保您保留只要但不再需要比的內容。單一保留原則可涵蓋整個組織。此外，您可以使用標籤來實作檔案計劃整個組織的控管、 分類資料並再強制執行該分類為基礎的保留規則。
  
- [保留原則概觀](retention-policies.md)
    
- [標籤概觀](labels.md)
    
- [大量建立及發佈使用 PowerShell 標籤](https://support.office.com/article/8986701b-ffa1-46ec-8fd0-8f7e81d5b25f.aspx)
    
- [處置檢閱概觀](disposition-reviews.md)
    
- [事件導向保留的概觀](event-driven-retention.md)
    
## <a name="govern-iii-retain-the-email-of-former-employees"></a>控管 III： 保留先前的員工的電子郵件

當一個人離開貴組織時，您可以藉由建立非使用中的信箱保留的電子郵件。信箱成為非使用中訴訟保留狀態時，Office 365 保留原則，或其他類型的保留套用到其中，並接著刪除對應的 Office 365 使用者帳戶。非使用中的信箱中的項目都會保留為之前已進行非使用中被指定信箱的保留或保留原則的持續期間。
  
- [Office 365 中的非使用中信箱的概觀](inactive-mailboxes-in-office-365.md)
    
- [建立及管理 Office 365 中的非使用中信箱](create-and-manage-inactive-mailboxes.md)

- [變更 Office 365 中不在作用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)
  
- [復原 Office 365 中不在作用中信箱](recover-an-inactive-mailbox.md)
 
- [還原 Office 365 中的非使用中信箱](restore-an-inactive-mailbox.md)

- [刪除非作用中的信箱在 Office 365](delete-an-inactive-mailbox.md)

## <a name="monitor"></a>監視

監督可讓您定義擷取電子郵件和組織中的第 3 廠商通訊讓他們可以由內部或外部檢閱者檢查的原則。檢閱者然後分類這些通訊、 確定它們符合貴組織的原則，並視呈報問題材料。
  
您也可以使用資料管理報告] 及 [標籤活動檔案總管來監視的標籤] 會套用到內容如您預期。
  
- [為您的組織設定監督原則](configure-supervision-policies.md)
    
- [監督報告](supervision-reports.md)
    
- [檢視文件的標籤活動](view-label-activity-for-documents.md)
    
- [檢視資料控管報告](view-the-data-governance-reports.md)
    
## <a name="more-information"></a>其他資訊

- [觀看 Microsoft 資料控管小組的影片](https://go.microsoft.com/fwlink/?linkid=867039)
    
- [觀看 Office 365 中的資料管理概觀](https://go.microsoft.com/fwlink/?linkid=852644)
    
- [Office 365 安全性&amp;規範中心指令程式](https://go.microsoft.com/fwlink/?linkid=852310)
    

