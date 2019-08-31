---
title: 在 EOP 中設定使用者垃圾郵件通知
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
ms.collection:
- M365-security-compliance
description: 您可以針對預設的全公司內容篩選原則或是網域所套用的自訂內容篩選原則，設定使用者垃圾郵件通知。
ms.openlocfilehash: c1345ffdfec734d28d5c0e461602716e1fd6a0f2
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2019
ms.locfileid: "36699268"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a><span data-ttu-id="701eb-103">在 EOP 中設定使用者垃圾郵件通知</span><span class="sxs-lookup"><span data-stu-id="701eb-103">Configure end-user spam notifications in EOP</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="701eb-104">本主題適用於要保護內部部署信箱的 Exchange Online Protection (EOP) 獨立版客戶。</span><span class="sxs-lookup"><span data-stu-id="701eb-104">This topic is for Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes.</span></span> <span data-ttu-id="701eb-105">保護雲端託管信箱的 Exchange Online 客戶應改閱讀下列主題：[設定使用者垃圾郵件通知中 Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="701eb-105">Exchange Online customers who are protecting cloud-hosted mailboxes should read the following topic instead: [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span></span> 
  
<span data-ttu-id="701eb-p102">您可以針對預設的全公司內容篩選原則或是網域所套用的自訂內容篩選原則，設定使用者垃圾郵件通知。啟用使用者垃圾郵件通知訊息，可讓您的使用者自行管理其被當成垃圾郵件隔離的郵件。使用者或群組所套用的原則或具有例外狀況的原則所套用的原則，無法使用使用者垃圾郵件通知。</span><span class="sxs-lookup"><span data-stu-id="701eb-p102">You can configure end-user spam notifications for the default company-wide content filter policy or for custom content filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="701eb-p103">使用者垃圾郵件通知包含使用者在您設定的時間期間 (您可指定 1 到 15 天之間的值) 內收到，被當成垃圾郵件隔離的所有郵件清單。您也可以設定用來撰寫通知郵件的語言。</span><span class="sxs-lookup"><span data-stu-id="701eb-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="701eb-111">之後收到通知郵件，使用者可以選擇下列選項：</span><span class="sxs-lookup"><span data-stu-id="701eb-111">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="701eb-112">**預覽**郵件如果您想要預覽的內容或之前採取動作的標頭。</span><span class="sxs-lookup"><span data-stu-id="701eb-112">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

<span data-ttu-id="701eb-113">**下載**郵件如果您想要檢閱的訊息和附件 （如果有的話） 之前採取行動裝置上。</span><span class="sxs-lookup"><span data-stu-id="701eb-113">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

<span data-ttu-id="701eb-114">**版本**如果郵件不是垃圾郵件，而且您希望 Office 365 將郵件傳送至您的信箱。</span><span class="sxs-lookup"><span data-stu-id="701eb-114">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="701eb-115">**釋出 & 允許寄件者**如果郵件不是垃圾郵件和您想要新增至安全的寄件者和收件者清單的未來的電子郵件的寄件者的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="701eb-115">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails.</span></span> <span data-ttu-id="701eb-116">請記住您的系統管理員可能會有您的安全寄件者清單會覆寫其他組織整體允許/封鎖組態。</span><span class="sxs-lookup"><span data-stu-id="701eb-116">Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

<span data-ttu-id="701eb-117">**版本 & 報表**，如果郵件不是垃圾郵件和您想要將郵件傳送至您的信箱及該問題報告給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="701eb-117">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

<span data-ttu-id="701eb-118">**封鎖寄件者**如果您希望 Office 365 將寄件者新增至封鎖的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="701eb-118">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="701eb-119">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="701eb-119">What do you need to know before you begin?</span></span>
<span data-ttu-id="701eb-120"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="701eb-120"></span></span>

<span data-ttu-id="701eb-121">預估完成時間：5 分鐘</span><span class="sxs-lookup"><span data-stu-id="701eb-121">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="701eb-p105">您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](eop/feature-permissions-in-eop.md)主題中的「反垃圾郵件」項目。</span><span class="sxs-lookup"><span data-stu-id="701eb-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature permissions in EOP](eop/feature-permissions-in-eop.md) topic.</span></span> 
  
<span data-ttu-id="701eb-124">適用於此主題中程序的鍵盤快速鍵相關資訊，請參閱[Exchange 系統管理員的鍵盤快速鍵置在 Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="701eb-124">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="701eb-125">使用 EAC 來設定使用者垃圾郵件通知</span><span class="sxs-lookup"><span data-stu-id="701eb-125">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="701eb-126">在 Exchange 系統管理中心 (EAC)，瀏覽至 [**保護** > **垃圾郵件篩選器**。</span><span class="sxs-lookup"><span data-stu-id="701eb-126">In the Exchange Admin Center (EAC), navigate to **Protection** > **Spam filter**.</span></span>
    
2. <span data-ttu-id="701eb-127">選取要啟用使用者垃圾郵件通知 (預設為停用) 的內容篩選原則。</span><span class="sxs-lookup"><span data-stu-id="701eb-127">Select the content filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="701eb-128">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span><span class="sxs-lookup"><span data-stu-id="701eb-128">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="701eb-129">在後續的對話方塊中，您可以設定下列選項：</span><span class="sxs-lookup"><span data-stu-id="701eb-129">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="701eb-p106">**啟用使用者垃圾郵件通知** 選取此核取方塊，以啟用此原則的使用者垃圾郵件通知。(反之，如果此原則已啟用，您可以清除此核取方塊，以停用此原則的使用者垃圾郵件通知。)</span><span class="sxs-lookup"><span data-stu-id="701eb-p106">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="701eb-p107">**傳送使用者垃圾郵件通知的間隔時間 (天數)** 指定傳送使用者垃圾郵件通知的頻率。預設值為 3 天。您可以指定 1 到 15 天之間的值。例如，如果您指定 7 天，則此通知將包含在過去 7 天內對象為該使用者，卻被當成垃圾郵件隔離的所有郵件的清單。</span><span class="sxs-lookup"><span data-stu-id="701eb-p107">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="701eb-136">**通知語言** 您可以使用下拉式清單，選取用來撰寫此原則之使用者垃圾郵件通知的語言。</span><span class="sxs-lookup"><span data-stu-id="701eb-136">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="701eb-p108">按一下 **[儲存]**。右側窗格便會出現內容篩選原則設定的摘要，包括使用者垃圾郵件通知設定。</span><span class="sxs-lookup"><span data-stu-id="701eb-p108">Click **save**. A summary of your content filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="701eb-p109">使用者垃圾郵件通知只會對已啟用的內容篩選原則作用。 >  每天只傳送一次使用者垃圾郵件通知。無法向任何特定客戶保證通知傳遞的時間，且無法加以設定。</span><span class="sxs-lookup"><span data-stu-id="701eb-p109">End-user spam notifications will only be functional for content filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="701eb-142">**提示：** 如果您想要在完全實作使用者垃圾郵件通知之前將其傳送給有限的使用者集，藉以測試使用者垃圾郵件通知，請建立一個自訂內容篩選器原則，為使用者所在的網域啟用使用者垃圾郵件通知。</span><span class="sxs-lookup"><span data-stu-id="701eb-142">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom content filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="701eb-143">接著，在 EAC 中，[**郵件流程\>規則**，且您想要的使用者的例外狀況從 quarantine@messaging.microsoft.com （傳送通知電子郵件通訊） 建立郵件流程規則 （也稱為傳輸規則） 來封鎖郵件若要收到通知。</span><span class="sxs-lookup"><span data-stu-id="701eb-143">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="701eb-144">下圖是從網域 Contoso.com 建立兩個使用者 (SaraD 和 AlexD) 之例外狀況的範例：</span><span class="sxs-lookup"><span data-stu-id="701eb-144">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![測試使用者垃圾郵件通知的傳輸規則](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="701eb-146">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="701eb-146">For more information</span></span>

[<span data-ttu-id="701eb-147">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="701eb-147">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
