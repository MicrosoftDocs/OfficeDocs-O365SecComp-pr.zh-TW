---
title: Office 365 Skype 為商務資料刪除的
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 說明在 Skype 資料刪除 for Business。
ms.openlocfilehash: f3ddd0ad0797c465857919e8f7b28341492769ba
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527006"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a>Office 365 中的商務資料刪除的 Skype

適用於企業的 Skype 提供對等立即訊息、 多方立即訊息和會議中的內容上傳活動的封存。封存功能需要 Exchange 管理及控制由使用者的 Exchange 信箱就地保留 」 屬性、 商務內容封存電子郵件和 Skype 的。

Skype for Business 中的所有封存會被視為"使用者層級封存 」 因為啟用或停用它的一或多個特定使用者或使用者群組建立、 設定及套用這些使用者的使用者層級封存原則。封存中的設定商務系統管理中心 Skype 沒有直接控制。

下列類型的內容不會封存中的商務 Skype： 
- 端對端檔案傳輸
- 端對端即時訊息與會議的音訊／影片
- 端對端即時訊息與會議的應用程式分享
- 會議註釋 

## <a name="meeting-content-retention"></a>會議內容保留
使用 Skype for Business 的客戶可以將內容上傳至 Skype 商務會議做為附件，例如 PowerPoint 簡報、 OneNote 檔案及其他檔案。已上傳至會議內容保留期間是如下：
- **一次性會議**內容會保留 15 天開始從最後一個人離開會議的時間。
- **週期性會議**內容會保留 15 天後最後一個人離開會議的最後一個工作階段。保留計時器重設如果某人加入 15 天內相同的會議工作階段。例如，假設 Skype 商務會議排定要根據每週發生一年和檔案上載至會議期間的第一個執行個體。如果至少一個人加入會議工作階段每週，該檔案會保留在 Skype 商務線上伺服器一整年 plus 15 天後最後一個人離開數列的最後一個會議的時間。
- **立即開會會議**-內容會保留在會議結束時間之後的 8 小時。

> [!NOTE]
> 如果使用者是未授權或停用 （例如，如果**msrtcsip-userenabled**設*為 False*），並再重新授權或重新啟用功能、 會議內容不會 」 保留。

## <a name="meeting-expiration"></a>會議到期
使用者可以在特定會議結束之後存取該會議，但需注意下列到期時段：
- **一次性會議**-會議會在排定的會議結束時間後的 14 天到期。
- **具有結束日期的週期性會議**-會議會的最後一個會議之排定的結束時間後的 14 天到期。
- **立即開會會議**-會議會在 8 小時後到期。

## <a name="whiteboard-collaboration"></a>白板共同作業
白板上進行註解將會看到所所有參與者。當儲存白板、 白板和所有註會儲存在 Skype Business server 並將會保留在根據會議內容到期原則管理員所設定之伺服器上。

## <a name="audio-test-service"></a>音訊測試服務
語音 short （大約 5 秒） 範例會記錄音訊測試服務通話期間。語音範例是由您用來檢查及 （或） 確認您 Skype 商務通話品質的錄製為基礎的聲音品質。當音訊測試服務通話結束時，會刪除語音範例。

## <a name="persistent-group-chat"></a>持續性群組聊天
持續 Group Chat 儲存群組聊天交談的內容。若啟用，系統管理員可以控制保留期間，此資訊會儲存的伺服器，如果群組聊天歷程記錄封存的規範或其他用途，和管理/修改在會議室的任何屬性。使用不同的角色的使用者具有不同保存的資料存取，如下所示：
- 管理員可以刪除任何聊天室保留從大幅增加資料庫的大小較舊的內容 （例如張貼特定日期之前的內容）。或可移除或取代郵件被視為不適當的給定的聊天室 （或被視為不適用）。
- 使用者，包括訊息作者無法刪除任何聊天室的內容。
- 聊天室管理員可以停用的聊天室，但是無法刪除聊天室。會在建立之後只有系統管理員可以刪除聊天室。