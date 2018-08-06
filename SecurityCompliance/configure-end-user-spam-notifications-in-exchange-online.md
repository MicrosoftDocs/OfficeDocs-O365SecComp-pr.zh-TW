---
title: Exchange Online 中設定使用者垃圾郵件通知
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
description: 您可以設定使用者垃圾郵件通知或自訂的垃圾郵件篩選器原則套用至網域的預設全公司的垃圾郵件篩選器原則。
ms.openlocfilehash: 4a4c7c6b139fe0f8b0a1f6b69c1b95e321293af5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027530"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="eebf1-103">Exchange Online 中設定使用者垃圾郵件通知</span><span class="sxs-lookup"><span data-stu-id="eebf1-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eebf1-p101">本主題是 Exchange Online 客戶若要保護雲端託管信箱。會保護內部部署信箱的 Exchange Online Protection (EOP) 獨立客戶應該改閱讀下列主題：[在 EOP 中的設定使用者垃圾郵件通知](configure-end-user-spam-notifications-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="eebf1-p101">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes. Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="eebf1-p102">您可以設定使用者垃圾郵件通知或自訂的垃圾郵件篩選器原則套用至網域的預設全公司的垃圾郵件篩選器原則。啟用使用者垃圾郵件通知訊息可讓您的使用者自我管理自己被當成垃圾郵件隔離的郵件。使用者垃圾郵件通知不能與原則套用至使用者或群組，或有例外的原則。</span><span class="sxs-lookup"><span data-stu-id="eebf1-p102">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="eebf1-p103">使用者垃圾郵件通知包含使用者在您設定的時間期間 (您可指定 1 到 15 天之間的值) 內收到，被當成垃圾郵件隔離的所有郵件清單。您也可以設定用來撰寫通知郵件的語言。</span><span class="sxs-lookup"><span data-stu-id="eebf1-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="eebf1-111">在收到通知郵件之後，使用者可以點擊以將垃圾郵件移至收件匣，或將垃圾郵件回報為「不是垃圾郵件」，在此情況下，該郵件會被傳送至 Microsoft 垃圾郵件分析小組。</span><span class="sxs-lookup"><span data-stu-id="eebf1-111">After receiving a notification message, end users can click to move the spam email to their inbox, or report the spam email as Not Junk, in which case it will be sent to the Microsoft Spam Analysis Team.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eebf1-112">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="eebf1-112">What do you need to know before you begin?</span></span>

<span data-ttu-id="eebf1-113">預估完成時間：2 分鐘</span><span class="sxs-lookup"><span data-stu-id="eebf1-113">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="eebf1-p104">您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題中的 「 反垃圾郵件 」 項目。</span><span class="sxs-lookup"><span data-stu-id="eebf1-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="eebf1-116">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Keyboard shortcuts in Exchange 2013**。</span><span class="sxs-lookup"><span data-stu-id="eebf1-116">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="eebf1-117">使用 EAC 來設定使用者垃圾郵件通知</span><span class="sxs-lookup"><span data-stu-id="eebf1-117">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="eebf1-118">在 Exchange 系統管理中心 (EAC)，瀏覽至 **[保護]** \> **[垃圾郵件篩選]**。</span><span class="sxs-lookup"><span data-stu-id="eebf1-118">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="eebf1-119">選取您要啟用使用者垃圾郵件通知 （已停用預設值） 的垃圾郵件篩選器原則。</span><span class="sxs-lookup"><span data-stu-id="eebf1-119">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="eebf1-120">在右窗格中，其中會顯示您的原則摘要資訊，請按一下 [**設定使用者垃圾郵件通知**] 連結。</span><span class="sxs-lookup"><span data-stu-id="eebf1-120">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="eebf1-121">在後續的對話方塊中，您可以設定下列選項：</span><span class="sxs-lookup"><span data-stu-id="eebf1-121">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="eebf1-p105">**啟用使用者垃圾郵件通知** 選取此核取方塊，以啟用此原則的使用者垃圾郵件通知。(反之，如果此原則已啟用，您可以清除此核取方塊，以停用此原則的使用者垃圾郵件通知。)</span><span class="sxs-lookup"><span data-stu-id="eebf1-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="eebf1-p106">**傳送使用者垃圾郵件通知的間隔時間 (天數)** 指定傳送使用者垃圾郵件通知的頻率。預設值為 3 天。您可以指定 1 到 15 天之間的值。例如，如果您指定 7 天，則此通知將包含在過去 7 天內對象為該使用者，卻被當成垃圾郵件隔離的所有郵件的清單。</span><span class="sxs-lookup"><span data-stu-id="eebf1-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="eebf1-128">**通知語言** 您可以使用下拉式清單，選取用來撰寫此原則之使用者垃圾郵件通知的語言。</span><span class="sxs-lookup"><span data-stu-id="eebf1-128">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="eebf1-p107">按一下 [**儲存**]。在右窗格中會出現在垃圾郵件篩選器原則設定，包括您使用者垃圾郵件通知的設定，摘要。</span><span class="sxs-lookup"><span data-stu-id="eebf1-p107">Click **save**. A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="eebf1-p108">使用者垃圾郵件通知只會啟用的垃圾郵件篩選原則作用。> 每天一次只能傳送使用者垃圾郵件通知。傳送通知的時間無法向任何特定客戶保證和且無法加以設定。</span><span class="sxs-lookup"><span data-stu-id="eebf1-p108">End-user spam notifications will only be functional for spam filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="eebf1-p109">**提示：** 如果您想要測試使用者垃圾郵件通知完整實作它們之前將它們傳送至一組有限的使用者，建立自訂垃圾郵件篩選器原則可讓使用者都位於之網域的使用者垃圾郵件通知。然後，在 EAC 中下,**郵件流程\>規則**、 例外狀況為您想要接收通知的使用者與來自 quarantine@messaging.microsoft.com （傳送通知電子郵件位址） 建立傳輸規則封鎖的郵件。下圖是來自網域 Contoso.com 建立兩個使用者 （SaraD 和 AlexD） 的例外狀況的範例：</span><span class="sxs-lookup"><span data-stu-id="eebf1-p109">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside. Then, in the EAC, under **Mail flow \> rules**, create a transport rule to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications. The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![測試使用者垃圾郵件通知的傳輸規則](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="eebf1-138">相關資訊</span><span class="sxs-lookup"><span data-stu-id="eebf1-138">For more information</span></span>

[<span data-ttu-id="eebf1-139">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="eebf1-139">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
