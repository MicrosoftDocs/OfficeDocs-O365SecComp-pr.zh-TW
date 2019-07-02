---
title: 開始使用 DLP 原則建議
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/7/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
description: 此深入瞭解導向的建議可協助您的組織在 DLP 原則範圍中有可能的差距時, 通知您, 讓您的組織在儲存和365共用機密內容時保持安全。 您會在安全性&amp;規範中心的首頁上看到這個建議, 如果您的檔包含任何最常使用的敏感資訊類型, 但是不會受到 DLP 原則保護。
ms.openlocfilehash: 326efb7591ba75ada9eec6a5e61e39e2a1fc09f9
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077969"
---
# <a name="get-started-with-dlp-policy-recommendations"></a>開始使用 DLP 原則建議

此深入瞭解導向的建議可協助您的組織在 DLP 原則範圍中有可能的差距時, 通知您, 讓您的組織在儲存和365共用機密內容時保持安全。 您會在安全性&amp;規範中心的**首頁**上看到這個建議, 如果您的檔包含任何最常使用的敏感資訊類型, 但是不會受到資料遺失防護 (DLP) 原則的保護。 
  
您可以使用這個小工具快速建立自訂的 DLP 原則, 只需按一下一次或兩次, 然後在建立此 DLP 原則之後, 即可完全自訂。 請注意, 如果您先看不到建議, 請嘗試在 [**建議的**位置] 區段的底部再按一下 [ **+** ]。 
  
![名為未受保護的敏感資訊的小工具](media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a>建立建議的 DLP 原則

當 widget 顯示您未受保護的機密資訊時, 請選擇底部的 [**開始**使用], 以快速建立 DLP 原則。 
  
為了協助保護敏感資訊, 此 DLP 原則:
  
- 在 Exchange、SharePoint 和 OneDrive 中包含其中一種未受保護的敏感資訊類型的內容與組織外部的人員共用時, 會偵測到。
    
- 產生詳細的活動報告, 讓您可以追蹤與組織外的人員共用內容的人員, 以及他們的情況。 您可以使用[DLP 報告](view-the-dlp-reports.md)和[審核記錄資料](search-the-audit-log-in-security-and-compliance.md)(其中**活動** = **DLP**) 來查看此資訊。
    
您也可以選擇擁有 DLP 原則:
  
- 當使用者與組織外部人員共用大量的敏感資訊時, 傳送您的附隨報告電子郵件。
    
- 將其他使用者新增至電子郵件附隨報告。
    
- 顯示原則提示, 並在使用者嘗試與組織外部的人員共用此機密資訊時, 傳送電子郵件通知給使用者。 如需這些選項的詳細資訊, 請參閱[傳送電子郵件通知及顯示 DLP 原則的原則提示](use-notifications-and-policy-tips.md)。
    
如果您想要稍後變更這些選項, 您可以在建立 DLP 原則之後進行編輯。 例如, 您可以讓原則更具限制性, 即使封鎖使用者在第一次的位置共用包含機密資訊的內容-請參閱下一節。
  
![名為「不受保護的敏感資訊」的小工具設定](media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a>編輯建議的 DLP 原則

使用 widget 建立 DLP 原則之後, 原則會出現在安全性&amp;規範中心的 [**原則**] 頁面的 [**資料遺失防護**] 下。 
  
根據預設, 此原則會命名為「**系統建議」原則, 以共用敏感資訊**。 此原則可完全自訂, 與您從頭開始建立的任何 DLP 原則相同。 例如, 如果您決定在使用小工具時不會開啟附隨報告和原則提示, 您可以隨時編輯原則, 並隨時開啟這些選項。
  
![共用機密資訊的系統建議原則](media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>當構件有且未出現時

&amp;在安全性與合規性中心首頁的 [**建議使用**] 區段中, **** 會顯示名為 [未**受保護的機密資訊**] 的小工具。 
  
只有在下列情況時才會顯示此小工具:
  
- 在過去30天內, SharePoint 或 OneDrive 中都會偵測到包含五種最常見的機密資訊類型的新檔。
    
- 該機密資訊尚未受到現有 DLP 原則的保護。
    
不同于持續掃描資料的 DLP 原則, 此建議會掃描每48小時大約 DLP 原則覆蓋率的差距, 因此在上傳新內容之後, 可能需要最多兩天的時間才能顯示建議。
  
最後, 在您使用 widget 來建立建議的 DLP 原則之後, 該小工具就會從**首頁**消失。 
  

