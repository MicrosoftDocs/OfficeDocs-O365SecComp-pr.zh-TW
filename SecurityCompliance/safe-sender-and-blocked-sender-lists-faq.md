---
title: 安全寄件者和封鎖寄件者清單在 Exchange Online
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
description: Exchange Online 或 Exchange Online Protection (EOP) 系統管理員身分有助於確保出差透過此服務的電子郵件不標示為垃圾郵件。若要執行這項作業的其中一個方法是針對在組織中的人員建立安全的寄件者和封鎖的寄件者清單。
ms.openlocfilehash: 923d71c4feeae16db538e381ee7c2ed7814cb8f8
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222942"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>安全寄件者和封鎖寄件者清單在 Exchange Online

Exchange Online 或 Exchange Online Protection (EOP) 系統管理員身分有助於確保出差透過此服務的電子郵件不標示為垃圾郵件。若要執行這項作業的其中一個方法是針對在組織中的人員建立安全的寄件者和封鎖的寄件者清單。 
  
 *請參閱秘訣及如何使用這些清單中的系統管理員身分的程序的更新的版本*[防止 false 正數電子郵件標示為垃圾郵件與安全清單或其他技術 （英文）](https://go.microsoft.com/fwlink/p/?LinkID=534224)。 
  
如果您不是系統管理員，而且您只想要管理自己在 Outlook 中的垃圾郵件使用安全的寄件者清單，請參閱的[垃圾郵件篩選工具](https://go.microsoft.com/fwlink/?LinkId=817222)概觀中的步驟。 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>什麼是安全及封鎖的寄件者限制在 Exchange Online？

從 Active Directory 與不同 Exchange Online 中的安全及封鎖的寄件者限制及 Outlook 的限制。他們是：
  
- 安全寄件者限制： 1024
    
- 封鎖的寄件者限制： 500
    
注意：
  
您可能會遇到錯誤[KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)中所述。若要解決此問題，請清除 「 信任的我的連絡人的電子郵件 」] 核取方塊。或者，減少是預設連絡人] 資料夾中將它移內允許的最大限制 1024年個在 Exchange Online 設定為"MaxSafeSenders"屬性的電子郵件地址的數量。如需此屬性與 Set-mailbox 指令程式的詳細資訊，seethe 下列主題：
  
[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)
  
## <a name="see-also"></a>另請參閱

[寄件者篩選中 Exchange 2016](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)

