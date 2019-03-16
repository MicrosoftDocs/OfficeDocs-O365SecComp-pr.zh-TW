---
title: 預設的 DLP 原則快速入門
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/10/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
description: 您甚至是建立您第一資料外洩防護 (DLP) 原則之前，DLP 協助保護您的機密資訊與預設原則。 此預設的原則和敏感內容安全的電子郵件或文件包含信用卡卡號碼時通知您已與組織外部人員共用其建議 （如下所示） 說明保留。
ms.openlocfilehash: fa48025a7b979ad69c600b21a10fbb62567234c3
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2019
ms.locfileid: "30638940"
---
# <a name="get-started-with-the-default-dlp-policy"></a>預設的 DLP 原則快速入門

您甚至是建立您第一資料外洩防護 (DLP) 原則之前，DLP 協助保護您的機密資訊與預設原則。 此預設的原則和敏感內容安全的電子郵件或文件包含信用卡卡號碼時通知您已與組織外部人員共用其建議 （如下所示） 說明保留。 您會看到這項建議在**首頁**上的安全性&amp;合規性中心。 
  
您可以使用此 widget 快速檢視時機與討論方向共用多少機密資訊，然後調整 [預設的 DLP 原則，只要按一下或兩個。 您也可以編輯任何時候預設的 DLP 原則，因為它是完全可自訂。 請注意，如果您沒有看到一開始，建議嘗試按一下 [ **+ 詳細**底部的 [**為您的建議**] 區段中。 
  
![名為進一步的 widget 保護共用的內容](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>檢視報表，並調整預設的 DLP 原則

當] 小工具會顯示使用者已與組織外部人員共用機密資訊時，請底部選擇**調整 DLP 原則**。 
  
詳細的報告顯示過去 30 天內何時和如何共用包含信用卡號碼的內容量。 請注意規則相符項目可能需要多達 48 小時] 小工具上顯示。
  
若要協助保護敏感資訊，也就是預設的 DLP 原則：
  
- 偵測與組織外部人員共用 Exchange、 SharePoint 和 OneDrive 包含至少一個信用卡號碼中的內容。
    
- 顯示原則提示，並將電子郵件通知傳送給使用者，當他們嘗試與組織外部人員共用機密資訊。 如需有關這些選項的詳細資訊，請參閱[傳送電子郵件通知並顯示原則提示的 DLP 原則](use-notifications-and-policy-tips.md)。
    
- 讓您可以追蹤之類的使用者與組織外部人員共用內容及他們沒有的時，會產生詳細的活動報告。 您可以使用[DLP 報告](view-the-dlp-reports.md)和[稽核記錄檔資料](search-the-audit-log-in-security-and-compliance.md)(其中**活動** = **DLP**) 若要查看此資訊。
    
若要快速修改預設的 DLP 原則，您可以選擇讓它：
  
- 您傳送附隨報告電子郵件時的使用者與組織外部人員共用機密資訊。
    
- 將其他使用者新增至電子郵件附隨報告。
    
- 封鎖存取內容包含敏感資訊，但允許使用者覆寫和共用或傳送如果他們需要。
    
如需有關附隨報告或限制存取的詳細資訊，請參閱 <<c0>資料外洩防護原則概觀。
  
如果您想要稍後變更這些選項，您可以編輯預設的 DLP 原則隨時-請參閱下一節。
  
![設定名為進一步的 widget 保護共用的內容](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>編輯預設的 DLP 原則

此原則名為 「**預設 Office 365 DLP 原則**，並出現在 [**資料外洩防護**] 下的安全性**原則**] 頁面上&amp;合規性中心。 
  
此原則可完全自訂，任何，從頭開始建立您自己的 DLP 原則相同。 您也可以關閉或刪除原則，使您的使用者不會再收到原則提示或電子郵件通知。
  
![名為預設的 Office 365 DLP 原則的 DLP 原則](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>當] 小工具會以及不會出現

Widget 名為**進一步保護共用的內容**會出現在 [**為您的建議**] 區段中的 [**首頁**] 頁面上的安全性&amp;合規性中心。 
  
此 widget 出現僅當：
  
- 安全性中有沒有資料外洩防護原則&amp;合規性中心或 Exchange 系統管理中心。 此 widget 被要幫助您快速入門 DLP 時，讓它不會出現，如果您已經有 DLP 原則。
    
- 包含至少一個信用卡內容已與過去 30 天內組織外部人員共用。
    
請注意規則相符項目可能需要多達 48 小時可] 小工具，讓外部共用的敏感資訊偵測到程式碼之後，可能需要最多兩天的顯示的建議。
  
最後，您使用 [] 小工具來調整預設的 DLP 原則之後，[] 小工具會消失從 [**首頁**] 頁面。 
  

