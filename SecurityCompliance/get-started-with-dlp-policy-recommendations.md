---
title: DLP 原則建議快速入門
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/7/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2ea4459b-cb13-4ce2-b9d1-0619316df88c
description: 此洞察力導向建議可協助貴組織保護敏感內容安全性時已儲存並共用 Office 365 中通知您何時在可能缺口 DLP 原則涵蓋範圍。在 [安全性] 首頁上看到此建議&amp;規範中心，如果您的文件包含下列任何前五常用的敏感資訊類型，但不受保護的 DLP 原則。
ms.openlocfilehash: 842387397b9b95d236660c5809174c2b356cf14a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527298"
---
# <a name="get-started-with-dlp-policy-recommendations"></a>DLP 原則建議快速入門

此洞察力導向建議可協助貴組織保護敏感內容安全性時已儲存並共用 Office 365 中通知您何時在可能缺口 DLP 原則涵蓋範圍。在 [**首頁**] 頁面上的 [安全性] 看到此建議&amp;規範中心，如果您的文件包含下列任何前五常用的敏感資訊類型，但不受保護的資料遺失防護 (DLP) 原則。 
  
您可以使用此 widget 快速建立自訂的 DLP 原則中按一下 [或兩個，並建立此 DLP 原則之後，它可完全自訂。如果看不建議在第一筆、 嘗試按一下 **+ 詳細**底部的 [**您的建議**] 區段中的記事。 
  
![Widget 名為未受保護敏感資訊](media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a>建立建議的 DLP 原則

時所顯示的 widget 保護敏感資料，選擇 [快速建立 DLP 原則底部**開始**。 
  
若要協助保護機密資訊，此 DLP 原則：
  
- 偵測與組織外部人員共用中 Exchange、 SharePoint 及 OneDrive 包含其中一個未受保護的敏感資訊類型的內容。
    
- 使您可以追蹤之類的人員與組織外部人員共用內容及當他們並未產生詳細的活動報告。您可以使用[DLP 報告](view-the-dlp-reports.md)和[稽核記錄檔資料](search-the-audit-log-in-security-and-compliance.md)(其中**活動** = **DLP**) 若要查看此資訊。
    
您也可以選擇有 DLP 原則：
  
- 傳送給您附隨報告電子郵件使用者與組織外部人員共用大量此機密資訊時。
    
- 將其他使用者新增至電子郵件附隨報告。
    
- 顯示原則提示，當他們嘗試與組織外部人員共用此機密資訊傳送給使用者的電子郵件通知。如需有關這些選項的詳細資訊，請參閱[傳送電子郵件通知與 DLP 原則的顯示原則提示](use-notifications-and-policy-tips.md)。
    
如果您想要稍後變更這些選項，您可以編輯 DLP 原則會在建立之後。例如，您可以進行原則更嚴格甚至封鎖的人共用包含敏感資訊的內容從最初-請參閱下一節。
  
![Widget 設定名為未受保護敏感資訊](media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a>編輯建議的 DLP 原則

您使用 widget 建立 DLP 原則之後，原則會顯示 [**資料外洩防護**的安全性**原則**] 頁面上&amp;規範中心。 
  
根據預設，將原則命名為**系統建議原則共用機密資訊**。此原則可完全自訂，自行建立從頭任何 DLP 原則相同。例如，如果您決定不使用 widget 時開啟附隨報告和原則提示，您可以一律編輯原則並隨時開啟這些選項。
  
![系統建議共用機密資訊的原則](media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>當 widget 提供與未出現

名為**未受保護的機密資訊**widget 會出現在 [**您的建議**] 區段中的 [**首頁**] 頁面上的 [安全性]&amp;規範中心。 
  
此 widget 出現只有當：
  
- 包含任何五個最常見的敏感資訊類型的新文件 SharePoint 或 OneDrive 中偵測到過去 30 天。
    
- 現有的 DLP 原則已經不受該機密資訊。
    
不同於正比掃描資料的 DLP 原則，此建議掃描 DLP 原則涵蓋範圍中的間距大致上每隔 48 小時，讓上傳新內容後，可能需要顯示的建議最多兩天。
  
最後，您使用 widget 來建立建議的 DLP 原則之後，從 [**首頁**] 頁面上會消失 widget。 
  

