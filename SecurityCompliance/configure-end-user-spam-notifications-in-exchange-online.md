---
title: Exchange Online 中設定使用者垃圾郵件通知
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: 您可以設定使用者垃圾郵件通知或自訂的垃圾郵件篩選器原則套用至網域的預設全公司的垃圾郵件篩選器原則。
ms.openlocfilehash: ea2994a3f772b407a35be2d64e8afcc639d24f31
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214493"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="b8de0-103">Exchange Online 中設定使用者垃圾郵件通知</span><span class="sxs-lookup"><span data-stu-id="b8de0-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8de0-p101">本主題是 Exchange Online 客戶若要保護雲端託管信箱。會保護內部部署信箱的 Exchange Online Protection (EOP) 獨立客戶應該改閱讀下列主題：[在 EOP 中的設定使用者垃圾郵件通知](configure-end-user-spam-notifications-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="b8de0-p101">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes. Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="b8de0-p102">您可以設定使用者垃圾郵件通知或自訂的垃圾郵件篩選器原則套用至網域的預設全公司的垃圾郵件篩選器原則。啟用使用者垃圾郵件通知訊息可讓您的使用者自我管理自己被當成垃圾郵件隔離的郵件。使用者垃圾郵件通知不能與原則套用至使用者或群組，或有例外的原則。</span><span class="sxs-lookup"><span data-stu-id="b8de0-p102">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="b8de0-p103">使用者垃圾郵件通知包含使用者在您設定的時間期間 (您可指定 1 到 15 天之間的值) 內收到，被當成垃圾郵件隔離的所有郵件清單。您也可以設定用來撰寫通知郵件的語言。</span><span class="sxs-lookup"><span data-stu-id="b8de0-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="b8de0-111">後接收通知訊息，使用者可以選擇下列選項：</span><span class="sxs-lookup"><span data-stu-id="b8de0-111">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="b8de0-112">**預覽**郵件如果您想要預覽的內容或之前先進行動作的標頭。</span><span class="sxs-lookup"><span data-stu-id="b8de0-112">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

<span data-ttu-id="b8de0-113">**下載**郵件] 如果您想要檢閱郵件和附件 （如果有的話） 之前先採取行動裝置上。</span><span class="sxs-lookup"><span data-stu-id="b8de0-113">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

<span data-ttu-id="b8de0-114">**版本**如果郵件不是垃圾郵件和您希望 Office 365 將郵件傳送給您的信箱。</span><span class="sxs-lookup"><span data-stu-id="b8de0-114">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="b8de0-p104">**釋出 & 允許寄件者**如果郵件不是垃圾郵件和您想要新增至安全的寄件者和收件者清單未來的電子郵件的寄件者的 Office 365。請記住您系統可能會有其他組織整體允許/封鎖設定會覆寫 [安全的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="b8de0-p104">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails. Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

<span data-ttu-id="b8de0-117">**版本 & 報表**，如果郵件不是垃圾郵件和您想要將郵件傳送給您的信箱並向 Microsoft 報告進行分析。</span><span class="sxs-lookup"><span data-stu-id="b8de0-117">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

<span data-ttu-id="b8de0-118">**封鎖**如果您希望 Office 365 將寄件者新增至封鎖的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="b8de0-118">**Block** if you want Office 365 to add the sender to your blocked senders list.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b8de0-119">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="b8de0-119">What do you need to know before you begin?</span></span>

<span data-ttu-id="b8de0-120">預估完成時間：2 分鐘</span><span class="sxs-lookup"><span data-stu-id="b8de0-120">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="b8de0-p105">您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題中的 「 反垃圾郵件 」 項目。</span><span class="sxs-lookup"><span data-stu-id="b8de0-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="b8de0-123">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Keyboard shortcuts in Exchange 2013**。</span><span class="sxs-lookup"><span data-stu-id="b8de0-123">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="b8de0-124">使用 EAC 來設定使用者垃圾郵件通知</span><span class="sxs-lookup"><span data-stu-id="b8de0-124">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="b8de0-125">在 Exchange 系統管理中心 (EAC)，瀏覽至 **[保護]** \> **[垃圾郵件篩選]**。</span><span class="sxs-lookup"><span data-stu-id="b8de0-125">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="b8de0-126">選取您要啟用使用者垃圾郵件通知 （已停用預設值） 的垃圾郵件篩選器原則。</span><span class="sxs-lookup"><span data-stu-id="b8de0-126">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="b8de0-127">在右窗格中，其中會顯示您的原則摘要資訊，請按一下 [**設定使用者垃圾郵件通知**] 連結。</span><span class="sxs-lookup"><span data-stu-id="b8de0-127">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="b8de0-128">在後續的對話方塊中，您可以設定下列選項：</span><span class="sxs-lookup"><span data-stu-id="b8de0-128">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="b8de0-p106">**啟用使用者垃圾郵件通知** 選取此核取方塊，以啟用此原則的使用者垃圾郵件通知。(反之，如果此原則已啟用，您可以清除此核取方塊，以停用此原則的使用者垃圾郵件通知。)</span><span class="sxs-lookup"><span data-stu-id="b8de0-p106">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="b8de0-p107">**傳送使用者垃圾郵件通知的間隔時間 (天數)** 指定傳送使用者垃圾郵件通知的頻率。預設值為 3 天。您可以指定 1 到 15 天之間的值。例如，如果您指定 7 天，則此通知將包含在過去 7 天內對象為該使用者，卻被當成垃圾郵件隔離的所有郵件的清單。</span><span class="sxs-lookup"><span data-stu-id="b8de0-p107">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="b8de0-135">**通知語言** 您可以使用下拉式清單，選取用來撰寫此原則之使用者垃圾郵件通知的語言。</span><span class="sxs-lookup"><span data-stu-id="b8de0-135">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="b8de0-p108">按一下 [**儲存**]。在右窗格中會出現在垃圾郵件篩選器原則設定，包括您使用者垃圾郵件通知的設定，摘要。</span><span class="sxs-lookup"><span data-stu-id="b8de0-p108">Click **save**. A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="b8de0-p109">使用者垃圾郵件通知只會啟用的垃圾郵件篩選原則作用。每天一次只能傳送 > 使用者垃圾郵件通知。傳送通知的時間無法向任何特定客戶保證和且無法加以設定。</span><span class="sxs-lookup"><span data-stu-id="b8de0-p109">End-user spam notifications will only be functional for spam filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="b8de0-p110">**提示：** 如果您想要測試使用者垃圾郵件通知完整實作它們之前將它們傳送至一組有限的使用者，建立自訂垃圾郵件篩選器原則可讓使用者都位於之網域的使用者垃圾郵件通知。然後，在 EAC 中下,**郵件流程\>規則**、 例外狀況為您想要接收通知的使用者與來自 quarantine@messaging.microsoft.com （傳送通知電子郵件位址） 建立傳輸規則封鎖的郵件。下圖是來自網域 Contoso.com 建立兩個使用者 （SaraD 和 AlexD） 的例外狀況的範例：</span><span class="sxs-lookup"><span data-stu-id="b8de0-p110">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside. Then, in the EAC, under **Mail flow \> rules**, create a transport rule to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications. The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![測試使用者垃圾郵件通知的傳輸規則](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="b8de0-145">相關資訊</span><span class="sxs-lookup"><span data-stu-id="b8de0-145">For more information</span></span>

[<span data-ttu-id="b8de0-146">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="b8de0-146">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
