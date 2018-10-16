---
title: 檔案計劃管理員的概觀
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 9/25/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 檔案計劃管理員提供對於保留標籤和原則的進階管理功能，並且提供整合的方式讓標籤和標籤至內容活動周遊整個內容生命週期 – 從建立、共同作業、記錄宣告、保留，到最終的處置。
ms.openlocfilehash: 4feacf20444591f6da2d55a928a81e86b56c5d9a
ms.sourcegitcommit: 9f34ace6bbe3d5e07e24ebaae96613750869cddf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2018
ms.locfileid: "25019274"
---
# <a name="overview-of-file-plan-manager"></a>檔案計劃管理員的概觀

檔案計劃管理員提供對於保留標籤和原則的進階管理功能，並且提供整合的方式讓標籤和標籤至內容活動周遊整個內容生命週期 – 從建立、共同作業、記錄宣告、保留，到最終的處置。

![檔案計劃頁面](media/file-plan-page.png)

## <a name="important-this-feature-is-currently-available-only-as-part-of-the-office-365-preview-program"></a>重要：此功能目前僅作為 Office 365 Preview 程式的一部分

如果貴組織已註冊 Office 365 Preview 程式，則您會在您的租用戶中看到這項功能。

## <a name="accessing-file-plan-manager"></a>存取檔案計劃管理員

存取檔案計劃管理員有兩個需求，需求如下：
- Office 365 企業版 E5 訂閱。
- 使用者已獲指派「安全性與合規性中心」的下列其中一個角色： 
    - 保留管理員
    - 僅檢視保留管理員

## <a name="navigating-your-file-plan"></a>瀏覽您的檔案計劃

檔案計劃管理員可讓您更輕鬆地從單一檢視，查看所有保留標籤和原則及其設定。

請注意，在檔案計劃外部所建立的保留標籤可以在檔案計劃中使用，反之亦然。

在 [檔案計劃標籤]**** 索引標籤上，下列額外資訊和功能可供使用：

### <a name="label-settings-columns"></a>標籤設定資料行
 
- [根據]**** 會識別觸發程序類型，該觸發程序會開始保留期間。有效的值是： 
    - 事件
    - 建立時機
    - 上次修改時間
    - 套用標籤時機
- [記錄]**** 會識別項目是否會在套用標籤時變成宣告的記錄。有效的值是：
    - 否
    - 是
    - Yes(Regulatory)
- [保留]**** 會識別保留類型。有效的值是：
    - 保留
    - 保留與刪除
    - 刪除
- [處置]**** 會識別保留期間結束時內容會發生什麼情形。有效的值是： 
    - Null
    - 不執行任何動作
    - 自動刪除
    - 需要檢閱 (也稱為處置檢閱)

![檔案計劃中的標籤設定](media/file-plan-label-columns.png)

### <a name="label-file-plan-descriptors-columns"></a>標籤檔案計劃描述元資料行

您現在可以在保留標籤組態中包含詳細資訊。將檔案計劃描述元插入標籤可以改善檔案計劃的管理性和組織。

為了讓您開始使用，檔案計劃管理員會為以下項目提供現成的值：函式/部門、分類、授權類型和佈建/引文。您可以在建立或編輯保留標籤時新增檔案計劃描述元值。

以下是建立或編輯保留標籤時的檔案計劃描述元步驟檢視。

![檔案計劃描述元](media/file-plan-descriptors.png)

以下是檔案計劃管理員的標籤索引標籤上，檔案計劃描述元的檢視。

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-labels-out-of-your-file-plan"></a>從檔案計劃匯出標籤

您可以從檔案計劃管理員將所有保留標籤的詳細資料匯出至 .csv 檔案，以協助您加速與貴組織中資料控管專案關係人進行的定期合規性檢閱。

若要匯出所有保留標籤，請移至 [檔案計劃管理員]**** \> [檔案計劃動作]**** \> [匯出標籤]****。

![匯出檔案計劃的選項](media/file-plan-export-labels-option.png)

包含所有現有保留標籤的 *.csv 檔案隨即開啟。

![顯示所有保留標籤的 CSV 檔案](media/file-plan-csv-file.png)

## <a name="import-labels-into-your-file-plan"></a>將標籤匯入至您的檔案計劃

您可以從檔案計劃管理員大量匯入新的標籤，以及修改現有的保留標籤。

若要匯入新的保留標籤以及對現有保留標籤進行更新，請移至 [檔案計劃管理員]**** \> [檔案計劃動作]**** \> [匯入標籤]****。

![匯入檔案計劃的選項](media/file-plan-import-labels-option.png)

![下載空白檔案計劃範本的選項](media/file-plan-blank-template-option.png)

下載空白範本 (或從匯出目前的檔案計劃開始)。

![在 Excel 中開啟空白檔案計劃範本](media/file-plan-blank-template.png)

填入範本 (項目有效值的參考資訊即將推出)。

![已填入資訊的檔案計劃範本](media/file-plan-filled-out-template.png)

上傳已填入資訊的範本，檔案計劃管理員會驗證項目並且顯示匯入統計資料。

![檔案計劃匯入統計資料](media/file-plan-import-statistics.png)

匯入完成後，返回檔案計劃管理員，將新標籤指派給新的或現有的原則。

![發佈標籤的選項](media/file-plan-publish-labels-option.png)
