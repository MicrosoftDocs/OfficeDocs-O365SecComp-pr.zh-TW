---
title: 尋找並調查已傳遞的惡意電子郵件 (Office 365 威脅調查和回應
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
description: 瞭解如何使用威脅調查和回應功能來尋找並調查惡意電子郵件。
ms.openlocfilehash: 5f8c615bed07b75cd3c06ec48f5ba73586f0f6d5
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394288"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-advanced-threat-protection-plan-2"></a>尋找並調查已傳遞的惡意電子郵件 (Office 365 高級威脅防護方案 2)

[Office 365 高級威脅防護](office-365-atp.md)可讓您調查讓使用者面臨風險的活動, 並採取行動以保護您的組織。 例如, 如果您是組織的安全小組的一部分, 您可以尋找並調查已傳遞給使用者的可疑電子郵件訊息。 您可以使用[威脅瀏覽器 (或即時偵測)](threat-explorer.md)來執行此動作。
  
## <a name="before-you-begin"></a>開始之前 .。。

請確定符合下列需求:
  
- 您的組織有[Office 365 Advanced 威脅防護](office-365-atp.md)(plan 1 或 plan 2) 和[授權已指派給使用者](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。
    
- 您的組織已開啟[Office 365 的 audit 記錄](turn-audit-log-search-on-or-off.md)。 
    
- 您的組織有針對反垃圾郵件、反惡意程式碼、反網路釣魚等所定義的原則。 請參閱[防範 Office 365 中的威脅](protect-against-threats.md)。
    
- 您是 Office 365 全域系統管理員, 或您擁有安全性系統管理員或在安全性&amp;與合規性中心中指派的搜尋和清除角色。 請參閱[Office 365 安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。
    
## <a name="dealing-with-suspicious-emails"></a>處理可疑的電子郵件

惡意攻擊者可能會將郵件傳送給您的使用者, 以嘗試和詐騙其認證, 並取得公司機密的存取權! 若要避免這種情況, 您應該使用 Office 365 中的威脅防護服務, 包括[Exchange Online protection](eop/exchange-online-protection-overview.md)和[高級威脅防護](office-365-atp.md)。 不過, 在某些情況下, 攻擊者可以傳送郵件給您的使用者包含 URL, 而只是稍後再讓該 URL 指向惡意內容 (惡意程式碼等等)。 或者, 您可能會發現組織中的使用者已遭到破壞, 而且該使用者遭到破壞時, 攻擊者會使用該帳戶, 將電子郵件傳送給公司中的其他使用者。 在這兩種情況下, 您可能會想要移除使用者收件匣中的電子郵件訊息。 在這類情況下, 您可以利用[威脅瀏覽器 (或即時偵測)](threat-explorer.md)來尋找並移除這些電子郵件!

## <a name="where-re-routed-emails-are-located-after-actions-are-taken"></a>在採取動作後, 重新路由傳送電子郵件的位置

威脅 Explorer 即時偵測已新增 [傳遞動作] 和 [傳遞位置] 欄位的 [傳遞] 狀態。 這會使您在電子郵件中的位置產生更完整的圖片。 此變更的其中一部分是讓搜尋更容易進行安全性操作人員, 但是 net 結果是一眼就知道問題電子郵件的位置。

傳遞狀態現在會分成兩欄:

- **傳遞動作**-此電子郵件的狀態為何？
- **傳遞位置**-這封電子郵件會做為結果的路由？

傳遞動作是由於現有的原則或偵測而對電子郵件採取的動作。 以下是電子郵件可能採取的動作:

1. **傳遞**–電子郵件已傳遞至使用者的收件匣或資料夾, 而且使用者可以直接存取它。
2. **Junked** –電子郵件會傳送至使用者的 [垃圾郵件] 資料夾或 [已刪除的資料夾], 而且使用者可以存取其垃圾郵件或已刪除的資料夾中的電子郵件。
3. **封鎖**–隔離、失敗或已捨棄的任何電子郵件。 使用者完全無法存取此功能!
4. **已更換**–任何惡意附件都由 .txt 檔案取代, 以指出附件是惡意的電子郵件。
 
[傳遞位置] 顯示執行傳遞後的原則和偵測結果。 它會連結至傳遞動作。 新增此欄位是為了深入瞭解當發現問題郵件時所採取的動作。 以下是傳遞位置的可能值:

1. **收件匣或資料夾**-電子郵件位於 [收件匣] 或 [資料夾 (根據您的電子郵件規則)。
2. **部署或外部**–信箱不存在於雲端上, 但在內部部署。
3. **垃圾郵件資料夾**–在使用者的 [垃圾郵件] 資料夾中的電子郵件。
4. [**刪除的郵件] 資料夾**–使用者的 [刪除的郵件] 資料夾中的電子郵件。
5. **隔離**–隔離中的電子郵件, 且不在使用者的信箱中。
6. **失敗**–電子郵件無法送達信箱。
7. **** 捨棄–電子郵件會在郵件流程中的某處遺失。
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>尋找並刪除已傳遞的可疑電子郵件

> [!TIP]
> 威脅瀏覽器 (有時稱為 Explorer) 是一種功能強大的報表, 可用於多種用途, 例如尋找和刪除郵件、識別惡意電子郵件寄件者的 IP 位址, 或啟動事件以進一步進行調查。 下列程式著重于使用 Explorer 來尋找和刪除收件者信箱中的惡意電子郵件。

若要查看對前一個傳遞狀態欄位所做的變更 (現在是傳遞動作和傳遞位置): 

1. 請移[https://protection.office.com](https://protection.office.com)至並使用您的公司或學校帳戶登入 Office 365。 這會將您帶到&amp;安全性與合規性中心。 
    
2. 在左側導覽中, 選擇 [**威脅管理** \> **瀏覽器**]。

![威脅瀏覽器螢幕擷取畫面。](media/Threat Explorer Delivery Action and Delivery Location.PNG)

<!--Comment>
    
3. In the View menu, choose **All email**.<br/>![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.<br/>![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only emails that ended up in users' inboxes.<br/>![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.<br/>![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.<br/>![You can view additional information about an item, including details and any attachments](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This will delete the selected messages from the recipients' mailboxes.<br/>![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
-->
## <a name="related-topics"></a>相關主題

[Office 365 高級威脅防護方案2](office-365-ti.md)
  
[防止 Office 365 中的威脅](protect-against-threats.md)
  
[查看 Office 365 的報告高級威脅防護](view-reports-for-atp.md)
  

