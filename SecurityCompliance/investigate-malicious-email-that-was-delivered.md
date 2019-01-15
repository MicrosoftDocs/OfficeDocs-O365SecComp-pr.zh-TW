---
title: 尋找與調查惡意的電子郵件已傳遞 （Office 365 威脅智慧）
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/6/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
description: 了解如何使用威脅智慧尋找及調查惡意的電子郵件。
ms.openlocfilehash: b6d4f8a5d1fcfce4461b91796b1264f94d1eb4d1
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014915"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-threat-intelligence"></a>尋找與調查惡意的電子郵件已傳遞 （Office 365 威脅智慧）

[Office 365 威脅智慧](office-365-ti.md)可讓您調查放在風險的使用者，並採取動作來保護您的組織的活動。例如，如果您組織的安全性小組的一部分，可以尋找及調查可疑的電子郵件已傳遞給您的使用者。您可以使用[瀏覽器威脅](get-started-with-ti.md#threat-explorer)。
  
> [!NOTE]
> 在 Office 365 企業版 E5 中使用 office 365 威脅智慧。如果貴組織要使用另一個 Office 365 企業版訂閱，可做為附加元件購買 Office 365 威脅智慧。(全域管理員在 Office 365 系統管理中心中，選擇 [**計費** \> **新增訂閱**。)如需詳細資訊，請參閱[Office 365 平台服務說明： Office 365 安全性&amp;規範中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[購買或編輯企業版的 Office 365 的附加元件](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。 
  
## <a name="before-you-begin"></a>開始之前...]

請確定符合下列需求：
  
- 您的組織具有[Office 365 威脅智慧](office-365-ti.md)及[指派給 Office 365 中的商務使用者的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。
    
- [Office 365 稽核記錄](turn-audit-log-search-on-or-off.md)會開啟您的組織。 
    
- 您的組織已定義的反垃圾郵件、 反惡意程式碼、 反網路釣魚等等的原則。請參閱[威脅管理 Office 365 安全性&amp;規範中心](threat-management.md)。
    
- 您是 Office 365 全域管理員，或您有安全性管理員或安全性指派搜尋及清除角色&amp;規範中心。請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。
    
## <a name="dealing-with-suspicious-emails"></a>處理可疑的電子郵件

惡意攻擊者可能會傳送郵件給使用者，嘗試和 phish 其認證及存取貴公司機密資料時會 ！若要避免此問題，您應該使用 Office 365，包括 Exchange Online Protection 和進階威脅保護所提供的威脅保護服務。但有當攻擊者無法將郵件傳送給您包含 URL 的使用者，並只更新版本 URL 這時惡意內容 （惡意程式碼等） 的次數。或者，您可能會發現太晚在組織中的使用者已遭洩露，及攻擊時該使用者已危害，用來傳送電子郵件給其他使用者在您的公司該帳戶。清除這兩種案例的一部分，您可能會想要移除使用者收件匣中的電子郵件訊息。像這些情況，您可以運用尋找及移除這些電子郵件訊息的威脅 Explorer ！
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>尋找並刪除可疑的電子郵件已傳遞

> [!TIP]
> [威脅瀏覽器](get-started-with-ti.md#threat-explorer)（也稱為 Explorer），是功能強大的適合多種目的，例如尋找和刪除郵件、 識別惡意的電子郵件寄件者的 IP 位址或開始進一步調查事件。下列程序著重於使用總管來尋找並從收件者的信箱中刪除惡意的電子郵件。 
  
1. 移至 [[https://protection.office.com](https://protection.office.com)及使用 Office 365 工作或學校帳戶登入。這會引導您安全性&amp;規範中心。 
    
2. 在左導覽列中，選擇 [ **Threat management** \> **瀏覽器**。
    
3. 在 [檢視] 功能表中選擇 [**所有電子郵件**]。<br/>![使用 [檢視] 功能表選擇電子郵件及內容的報表](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. 請注意會出現在報表，例如**已傳遞**、**未知**，或**傳遞至垃圾郵件**標籤。<br/>![顯示所有的電子郵件資料的威脅瀏覽器](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>（根據對您的組織的電子郵件訊息所採取的動作，您可能會看到其他標籤，例如**封鎖**或**取代**）。
    
5. 在報表中，選擇 [檢視使用者的收件匣中的結束電子郵件**已傳遞**。<br/>![按一下 「 傳遞至垃圾郵件 」 從檢視中移除該資料](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. 圖表下方檢閱**電子郵件**清單圖表下方。<br/>![圖表下方檢視所偵測到的電子郵件的清單](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. 在清單中，選擇檢視該電子郵件訊息的更多詳細資料的項目。例如，您可以按一下 [檢視資訊寄件者、 收件者、 附件及其他類似的電子郵件的主旨行。<br/>![您可以檢視項目，包括詳細資料和任何附件的其他資訊](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. 之後檢視的電子郵件的相關資訊，請啟動 **+ 動作**清單中選取一或多個項目。
    
9. 使用 [ **+ 動作**] 清單中套用的動作，例如**移至刪除**的項目。這會從收件者的信箱中刪除所選的郵件。<br/>![當您選取一或多個電子郵件訊息時，您可以選擇從數個可用的動作](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
## <a name="related-topics"></a>相關主題

[Office 365 威脅情報](office-365-ti.md)
  
[防範 Office 365 中的威脅](protect-against-threats.md)
  
[Office 365 進階威脅保護的檢視報告](view-reports-for-atp.md)
  

