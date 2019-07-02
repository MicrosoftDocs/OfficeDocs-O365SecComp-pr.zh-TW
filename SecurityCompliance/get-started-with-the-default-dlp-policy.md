---
title: 開始使用預設的 DLP 原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
description: 在您建立第一次資料遺失防護 (DLP) 原則之前, DLP 會協助使用預設原則來保護您的機密資訊。 此預設原則及其建議 (如下所示) 可在您的組織外的人員共用包含信用卡號碼的電子郵件或檔時通知您, 以協助保護您的敏感內容。
ms.openlocfilehash: a14e2c9c1f833552c11e55ec76f6f804e0311479
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077919"
---
# <a name="get-started-with-the-default-dlp-policy"></a>開始使用預設的 DLP 原則

在您建立第一次資料遺失防護 (DLP) 原則之前, DLP 會協助使用預設原則來保護您的機密資訊。 此預設原則及其建議 (如下所示) 可在您的組織外的人員共用包含信用卡號碼的電子郵件或檔時通知您, 以協助保護您的敏感內容。 您會在安全性**** &amp;與合規性中心的首頁看到此建議。 
  
您可以使用此小工具快速查看共用的機密資訊的時間和數量, 然後只需按一次或兩次, 以精煉預設的 DLP 原則。 您也可以隨時編輯預設的 DLP 原則, 因為它是完全可自訂的。 請注意, 如果您先看不到建議, 請嘗試在 [**建議的**位置] 區段的底部再按一下 [ **+** ]。 
  
![已命名的小工具會進一步保護共用內容](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>查看報表並精煉預設的 DLP 原則

當 widget 顯示使用者與組織外部人員共用敏感資訊時, 請選擇 [**精簡 DLP 原則**] 底部。 
  
詳細報告顯示在過去30天內共用包含信用卡號碼的內容的時間和數量。 請注意, 規則相符可能需要最多48小時才能顯示在 widget 中。
  
為了協助保護機密資訊, 預設的 DLP 原則:
  
- 在 Exchange、SharePoint 和 OneDrive 中包含至少一張信用卡號碼的內容與組織外部人員共用時, 會偵測到此內容。
    
- 顯示原則提示, 並在使用者嘗試與組織外部的人員共用此機密資訊時, 將電子郵件通知傳送給使用者。 如需這些選項的詳細資訊, 請參閱[傳送電子郵件通知及顯示 DLP 原則的原則提示](use-notifications-and-policy-tips.md)。
    
- 產生詳細的活動報告, 讓您可以追蹤與組織外的人員共用內容的人員, 以及他們的情況。 您可以使用[DLP 報告](view-the-dlp-reports.md)和[審核記錄資料](search-the-audit-log-in-security-and-compliance.md)(其中**活動** = **DLP**) 來查看此資訊。
    
若要快速精煉預設的 DLP 原則, 您可以選擇讓它擁有:
  
- 當使用者與組織外部人員共用此機密資訊時, 傳送您的附隨報告電子郵件。
    
- 將其他使用者新增至電子郵件附隨報告。
    
- 封鎖對包含機密資訊的內容的存取, 但允許使用者在需要時覆寫及共用或傳送。
    
如需有關附隨報告或限制存取的詳細資訊, 請參閱[資料遺失防護原則的總覽](data-loss-prevention-policies.md)。
  
如果您想要稍後變更這些選項, 您可以隨時編輯預設的 DLP 原則-請參閱下一節。
  
![名為進一步保護共用內容的小工具設定](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>編輯預設的 DLP 原則

此原則命名為**預設的 Office 365 DLP 原則**, 並顯示在&amp;安全性與合規性中心的 [**原則**] 頁面的 [**資料遺失防護**] 底下。 
  
此原則可完全自訂, 與您從頭開始建立的任何 DLP 原則相同。 您也可以關閉或刪除原則, 如此一來, 您的使用者就不會再收到原則提示或電子郵件通知。
  
![名為「預設 Office 365 DLP 原則」的 DLP 原則](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>當構件有且未出現時

&amp; [安全性規範中心] 首頁的 [**建議使用**] 區段中會顯示名**** 為 [**進一步保護共用內容**] 的小工具。 
  
只有在下列情況時才會顯示此小工具:
  
- 安全性&amp;合規性中心或 Exchange 系統管理中心沒有資料遺失防護原則。 這個小工具是用來協助您開始使用 DLP, 因此如果您已經擁有 DLP 原則, 就不會顯示。
    
- 在過去30天內, 包含至少一張信用卡的內容已與組織外部的人員共用。
    
請注意, 規則比對最多可能需要48小時才能供 widget 使用, 因此在偵測到外部共用敏感資訊後, 可能需要最多兩天的時間, 才會出現建議。
  
最後, 在您使用 widget 來精煉預設的 DLP 原則之後, 該小工具就會從**首頁**消失。 
  

