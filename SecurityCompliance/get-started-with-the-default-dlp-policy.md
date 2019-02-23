---
title: 預設的 DLP 原則快速入門
ms.author: stephow
author: stephow-MSFT
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
description: 您甚至可以建立您第一個資料外洩防護 (DLP) 原則之前，DLP 協助保護您的機密資訊與預設原則。此預設原則和敏感內容安全的電子郵件或包含信用文件介面卡數目時通知您已與組織外的某個人共用其建議 （如下所示） 說明保留。
ms.openlocfilehash: 25d42a7c7598a82fcf153ce05b64ee990e104b40
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216583"
---
# <a name="get-started-with-the-default-dlp-policy"></a>預設的 DLP 原則快速入門

您甚至可以建立您第一個資料外洩防護 (DLP) 原則之前，DLP 協助保護您的機密資訊與預設原則。此預設原則和敏感內容安全的電子郵件或包含信用文件介面卡數目時通知您已與組織外的某個人共用其建議 （如下所示） 說明保留。在 [**首頁**] 頁面上的 [安全性] 看到此建議&amp;規範中心。 
  
您可以使用此 widget 快速檢視時機與討論方向多少敏感資訊的形式共用，並再調整預設的 DLP 原則中只要按一兩。您也可以編輯預設 DLP 原則隨時因為完全可自訂。如果看不建議在第一筆、 嘗試按一下 **+ 詳細**底部的 [**您的建議**] 區段中的記事。 
  
![Widget 名為進一步保護共用的內容](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>檢視報告及調整預設 DLP 原則

Widget 會顯示使用者已與組織外部人員共用機密資訊、 底部選擇**調整 DLP 原則**。 
  
詳細的報告顯示您何時及如何在過去 30 天的形式共用包含信用卡數字的內容。請注意規則比對約在 widget 顯示最多達 48 小時。
  
若要協助保護敏感資訊、 預設的 DLP 原則：
  
- 偵測與組織外部人員共用 Exchange、 SharePoint 及 OneDrive 包含至少一個信用卡號中的內容。
    
- 顯示原則提示及時他們嘗試與組織外部人員共用此機密資訊傳送給使用者的電子郵件通知。如需有關這些選項的詳細資訊，請參閱[傳送電子郵件通知與 DLP 原則的顯示原則提示](use-notifications-and-policy-tips.md)。
    
- 使您可以追蹤之類的人員與組織外部人員共用內容及當他們並未產生詳細的活動報告。您可以使用[DLP 報告](view-the-dlp-reports.md)和[稽核記錄檔資料](search-the-audit-log-in-security-and-compliance.md)(其中**活動** = **DLP**) 若要查看此資訊。
    
快速調整預設 DLP 原則，您可以選擇予有：
  
- 傳送給您附隨報告電子郵件時的使用者與組織外部人員共用此機密資訊。
    
- 將其他使用者新增至電子郵件附隨報告。
    
- 封鎖包含機密資訊、 內容的存取權，但允許使用者覆寫及共用或傳送如果所需。
    
如需有關附隨報告或限制存取的詳細資訊，請參閱 ＜[資料外洩防護原則的概觀](data-loss-prevention-policies.md)。
  
如果您想要稍後變更這些選項，您可以編輯預設的 DLP 原則隨時-請參閱下一節。
  
![設定名為進一步 widget 保護共用的內容](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>編輯預設 DLP 原則

此原則命名為**預設的 Office 365 DLP 原則**並的安全性**原則**] 頁面上會出現 [**資料外洩防護**&amp;規範中心。 
  
此原則可完全自訂，自行建立從頭任何 DLP 原則相同。您也可以關閉或刪除原則，使您的使用者不會再收到原則提示或電子郵件通知。
  
![DLP 原則名為預設的 Office 365 DLP 原則](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>當 widget 提供與未出現

名為**進一步保護共用的內容**widget 會出現在 [**您的建議**] 區段中的 [**首頁**] 頁面上的 [安全性]&amp;規範中心。 
  
此 widget 出現只有當：
  
- 在 [安全性] 中有無資料外洩防護原則&amp;規範中心 」 或 「 Exchange 系統管理中心。此 widget 被為了幫助您快速入門 DLP，讓它不會顯示如果您已經有 DLP 原則。
    
- 已與您在過去 30 天的組織外的某個人共用內容包含至少一個信用卡。
    
請注意規則比對約最多達 48 小時供 widget，因此會偵測敏感資訊從外部共用之後，可能會需要顯示的建議最多兩天。
  
最後，使用 widget 調整預設 DLP 原則後，從 [**首頁**] 頁面會消失 widget。 
  

