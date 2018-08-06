---
title: 安全寄件者和封鎖寄件者清單在 Exchange Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
description: Exchange Online 或 Exchange Online Protection (EOP) 系統管理員身分有助於確保出差透過此服務的電子郵件不標示為垃圾郵件。若要執行這項作業的其中一個方法是針對在組織中的人員建立安全的寄件者和封鎖的寄件者清單。
ms.openlocfilehash: fcb43f990750782788dc6f459dd5c7d296146a38
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22028080"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="f5fed-104">安全寄件者和封鎖寄件者清單在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f5fed-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="f5fed-p102">Exchange Online 或 Exchange Online Protection (EOP) 系統管理員身分有助於確保出差透過此服務的電子郵件不標示為垃圾郵件。若要執行這項作業的其中一個方法是針對在組織中的人員建立安全的寄件者和封鎖的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="f5fed-p102">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam. One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span> 
  
 <span data-ttu-id="f5fed-107">*請參閱秘訣及如何使用這些清單中的系統管理員身分的程序的更新的版本*[防止 false 正數電子郵件標示為垃圾郵件與安全清單或其他技術 （英文）](https://go.microsoft.com/fwlink/p/?LinkID=534224)。</span><span class="sxs-lookup"><span data-stu-id="f5fed-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [Prevent false positive email marked as spam with a safelist or other techniques](https://go.microsoft.com/fwlink/p/?LinkID=534224).</span></span> 
  
<span data-ttu-id="f5fed-108">如果您不是系統管理員，而且您只想要管理自己在 Outlook 中的垃圾郵件使用安全的寄件者清單，請參閱的[垃圾郵件篩選工具](https://go.microsoft.com/fwlink/?LinkId=817222)概觀中的步驟。</span><span class="sxs-lookup"><span data-stu-id="f5fed-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in this overview of [the Junk Email Filter](https://go.microsoft.com/fwlink/?LinkId=817222).</span></span> 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="f5fed-109">什麼是安全及封鎖的寄件者限制在 Exchange Online？</span><span class="sxs-lookup"><span data-stu-id="f5fed-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="f5fed-p103">從 Active Directory 與不同 Exchange Online 中的安全及封鎖的寄件者限制及 Outlook 的限制。他們是：</span><span class="sxs-lookup"><span data-stu-id="f5fed-p103">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits. They are:</span></span>
  
- <span data-ttu-id="f5fed-112">安全寄件者限制： 1024</span><span class="sxs-lookup"><span data-stu-id="f5fed-112">Safe sender limit: 1,024</span></span>
    
- <span data-ttu-id="f5fed-113">封鎖的寄件者限制： 500</span><span class="sxs-lookup"><span data-stu-id="f5fed-113">Blocked sender limit: 500</span></span>
    
<span data-ttu-id="f5fed-114">注意：</span><span class="sxs-lookup"><span data-stu-id="f5fed-114">Note:</span></span>
  
<span data-ttu-id="f5fed-p104">您可能會遇到錯誤 KB 2590466 （"收到錯誤 「 垃圾電子郵件驗證錯誤 「 Outlook Web App 中的 Exchange Server 2010"） 中所述。若要解決此問題，請清除 「 信任的我的連絡人的電子郵件 」] 核取方塊。或者，減少是預設連絡人] 資料夾中將它移內允許的最大限制的 1024 在 Exchange Online 設定為"MaxSafeSenders"屬性的電子郵件地址的數量。如需此屬性與 Set-mailbox 指令程式的詳細資訊，seethe 下列主題：</span><span class="sxs-lookup"><span data-stu-id="f5fed-p104">You may experience the error that is described in KB 2590466 ("You receive the error "Junk e-mail validation error" in Outlook Web App for Exchange Server 2010"). To resolve this issue, clear the "Trust emails from my contacts" check box. Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1,024 in Exchange Online that is set for "MaxSafeSenders" attribute. For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>
  
[<span data-ttu-id="f5fed-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="f5fed-119">Set-Mailbox</span></span>](https://docs.microsoft.com/en-us/powershell/module/exchange/mailboxes/Set-Mailbox?view=exchange-ps)
  
## <a name="see-also"></a><span data-ttu-id="f5fed-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f5fed-120">See also</span></span>

[<span data-ttu-id="f5fed-121">寄件者篩選中 Exchange 2016</span><span class="sxs-lookup"><span data-stu-id="f5fed-121">Sender filtering in Exchange 2016</span></span>](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)

