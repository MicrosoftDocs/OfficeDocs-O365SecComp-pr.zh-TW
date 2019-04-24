---
title: Office 365 Skype for Business 資料刪除
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 商務用 skype 資料刪除說明。
ms.openlocfilehash: ca48a4bc57cdba7301a51cc6404a7d402166ffb0
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261301"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a>Office 365 中的商務資料刪除商務用 Skype

商務用 Skype 提供封存的端對端即時訊息、 多方立即訊息和會議中的內容上傳活動。 封存功能，需要 Exchange，而且由使用者的 Exchange 信箱原有範圍暫止屬性，其封存電子郵件與 Skype for Business 內容所控制。

商務用 Skype 中的所有封存會被視為 「 使用者層級封存 」 因為您啟用或停用它的一或多個特定使用者或群組的使用者建立、 設定及套用這些使用者的封存使用者層級原則。 從 [Skype 商務版系統管理中心內的封存設定沒有直接控制項。

下列內容類型未封存於商務用 Skype: 
- 對等檔案傳輸
- 對等立即訊息和會議的音訊/視訊
- 應用程式共用的端對端即時訊息與會議
- 會議註釋 

## <a name="meeting-content-retention"></a>會議內容保留
使用商務用 Skype 的客戶可以將內容上傳到 Skype 會議做為附件，例如 PowerPoint 簡報、 OneNote 檔案，以及其他檔案。 上傳至會議的內容有如下的保留期：
- **一次性會議**內容會保留 15 天從最後一個人離開會議的時間開始。
- **週期性會議**內容會保留 15 天後最後一個人離開會議的最後一個工作階段。 如果某人加入相同的會議工作階段，15 天內，重設為保留計時器。 例如，假設 Skype 會議排程進行每週為一年，而且檔案上傳至會議期間的第一個執行個體。 如果至少一位人員加入會議工作階段每週，檔案會保留在 Skype for Business Online 伺服器一整年 plus 最後一個人離開最後一個數列的會議之後的 15 天。
- **立即開會會議**的內容會保留在會議結束時間之後的 8 小時。

> [!NOTE]
> 如果使用者是未經授權或停用 （例如，如果**包含 userenabled**設為*False*），並再重新授權或之後，無法保留會議內容。

## <a name="meeting-expiration"></a>會議到期
使用者可以在特定會議結束之後存取該會議，但需注意下列到期時段：
- **一次性會議**的會議排定的會議結束時間後的 14 天到期。
- **具有結束日期的週期性會議**的會議的最後一個會議之排定的結束時間後的 14 天到期。
- **立即開會會議**的會議會在 8 小時後到期。

## <a name="whiteboard-collaboration"></a>白板共同作業
在白板上所做的註釋，所有參與者都看得到。 當儲存白板、 白板和所有註解將會儲存在 Skype for Business server，它會保留在根據會議內容到期原則管理員所設定的伺服器上。

## <a name="audio-test-service"></a>音訊測試服務
您的聲音短 （大約 5 秒） 範例會記錄音訊測試服務通話期間。 語音範例是由您用來檢查及/或確認您 Skype for Business 呼叫根據錄製的品質的聲音品質。 音訊測試服務呼叫結束時，會刪除語音範例。

## <a name="persistent-group-chat"></a>持續性群組聊天
常設 Group Chat 儲存群組聊天交談的內容。 如果啟用，系統管理員可以控制在保留期間，這項資訊會儲存的伺服器，如果群組聊天歷程記錄封存的符合性或其他用途，並管理/修改會議室的任何屬性。 具有不同角色的使用者有不同的存取權的保存的資料，如下所示：
- 系統管理員可以保留資料庫的大小變得很大的差異任何聊天室中刪除舊內容 （例如，在特定日期之前發佈的內容）。 或者，他們可以移除或取代的訊息視為不適用於指定的聊天室 （或被視為不適用）。
- 使用者，包括訊息作者無法刪除任何聊天室中的內容。
- 聊天室管理員可以停用聊天室，但是無法刪除聊天室。 建立後，只有系統管理員可以刪除聊天室。