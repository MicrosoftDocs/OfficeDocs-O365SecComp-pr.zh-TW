---
title: 尋找並調查惡意 （Office 365 威脅調查及回應已傳送的電子郵件
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 了解如何使用威脅調查及回應功能來尋找並調查惡意電子郵件。
ms.openlocfilehash: 7e2cef742339e54c094cfb0c3b32fbf596896a3d
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408298"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-advanced-threat-protection-plan-2"></a>尋找並調查惡意電子郵件已傳遞 (Office 365 進階威脅防護計劃 2)

[Office 365 進階威脅防護](office-365-atp.md)可讓您調查，將您的使用者放在風險，並採取動作來保護您的組織活動。 例如，如果您是貴組織的安全性小組的一部分，您可以尋找和調查可疑的電子郵件已傳遞至您的使用者。 您可以使用[威脅總管 （或即時偵測的資訊）](threat-explorer.md)。
  
## <a name="before-you-begin"></a>開始之前...]

請確定符合下列需求：
  
- 您的組織有[Office 365 進階威脅防護](office-365-atp.md)（方案 1 或計劃 2） 並[將授權指派給使用者](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。
    
- [Office 365 稽核記錄](turn-audit-log-search-on-or-off.md)已為您的組織。 
    
- 貴組織的原則定義的反垃圾郵件、 反惡意程式碼、 反網路釣魚，依此類推。 請參閱[針對 Office 365 中的威脅保護](protect-against-threats.md)。
    
- 您是 Office 365 全域管理員，或具有安全性系統管理員或 「 搜尋及清除角色指派安全性&amp;合規性中心。 請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。
    
## <a name="dealing-with-suspicious-emails"></a>處理可疑的電子郵件

惡意攻擊者可能會將郵件傳送至您的使用者嘗試與釣魚程式其認證，並存取您公司的機密資料 ！ 若要避免這個問題，您應該使用提供的 Office 365，包括[Exchange Online Protection](eop/exchange-online-protection-overview.md)和[進階威脅防護](office-365-atp.md)的威脅保護服務。 不過，有的時間攻擊者時將郵件傳送給使用者的 url 然後僅更新版本上將該 URL 點對惡意內容 （惡意程式碼等）。 或者，您可能會發現太晚而遭入侵您組織中的使用者，以及攻擊時遭到盜用了該使用者，使用該帳戶傳送電子郵件給您公司中的其他使用者。 一部分 < cleaning up 這兩種情況，您可能想要移除使用者收件匣的電子郵件。 在這類的情況下，您可以利用[威脅總管 （或即時偵測）](threat-explorer.md)來尋找和移除這些電子郵件訊息 ！
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>尋找並刪除可疑的電子郵件的郵件傳遞

> [!TIP]
> 威脅總管 （也稱為 「 檔案總管 」），是功能強大的報表，可以有多個用途，例如尋找及刪除的郵件，用來識別惡意電子郵件寄件者的 IP 位址或開始進一步調查的事件。 下列程序著重於使用 Explorer 來尋找並從收件者信箱刪除惡意電子郵件。 
  
1. 移至 [[https://protection.office.com](https://protection.office.com)和 Office 365 使用公司或學校帳戶登入。 這會帶您前往安全性&amp;合規性中心。 
    
2. 在左側導覽中，選擇 [**威脅管理，** \> **總管**。
    
3. 在 [檢視] 功能表中，選擇 [**所有電子郵件**。<br/>![使用 [檢視] 功能表的電子郵件和內容的報告之間選擇](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. 請注意報表，例如**已傳遞**、**未知**，或**傳遞至垃圾郵件**中顯示的標籤。<br/>![顯示所有的電子郵件資料的威脅總管](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>（根據對貴組織的電子郵件所採取的動作，您可能會看到其他標籤，例如**封鎖**或**取代**）。
    
5. 在報告中，選擇 [**已傳遞**的以檢視僅最後出現在使用者的收件匣的電子郵件]。<br/>![按一下 「 傳遞至垃圾郵件 」 從檢視中移除該資料](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. 下方圖表中，檢閱圖表下方的**電子郵件**清單。<br/>![下方圖表中，檢視已偵測到的電子郵件的清單](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. 在清單中，選擇 [項目來檢視電子郵件訊息的相關詳細資料]。 例如，您可以按一下 [檢視資訊寄件者、 收件者、 附件及其他類似的電子郵件的主旨行。<br/>![您可以檢視項目，包括詳細資料和任何附件相關的其他資訊](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. 之後檢視電子郵件的相關資訊，請啟動 **+ 動作**清單中選取一或多個項目。
    
9. 使用 **+ 動作**清單將套用的動作，例如**將移至刪除**的項目。 這會從收件者的信箱刪除選取的郵件。<br/>![當您選取一或多個電子郵件時，您可以選擇從數個可用的動作](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
## <a name="related-topics"></a>相關主題

[Office 365 進階的威脅保護計劃 2](office-365-ti.md)
  
[防範 Office 365 中的威脅](protect-against-threats.md)
  
[檢視 Office 365 進階威脅防護報告](view-reports-for-atp.md)
  

