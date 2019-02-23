---
title: 佇列的警示和佇列
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 系統管理員可在 Office 365 安全性 & 規範中心中的郵件流程儀表板中了解佇列提醒和佇列。
ms.openlocfilehash: 45c03ae8d5f646c4514b19669ca83b3eac561f68
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220793"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="50c66-103">佇列的警示和佇列</span><span class="sxs-lookup"><span data-stu-id="50c66-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="50c66-104">佇列提醒</span><span class="sxs-lookup"><span data-stu-id="50c66-104">Queue alerts</span></span>

<span data-ttu-id="50c66-p101">當郵件無法從 Office 365 組織傳送至您的內部或協力廠商電子郵件伺服器使用連接器，會將郵件佇列在 Office 365 中。此條件會造成的常見範例是：</span><span class="sxs-lookup"><span data-stu-id="50c66-p101">When messages can't be sent from your Office 365 organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365. Common examples that cause this condition are:</span></span>

- <span data-ttu-id="50c66-107">未正確設定連接器。</span><span class="sxs-lookup"><span data-stu-id="50c66-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="50c66-108">內部部署環境中已有網路或防火牆的變更。</span><span class="sxs-lookup"><span data-stu-id="50c66-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="50c66-p102">Office 365 會繼續重試傳遞至 48 小時。48 小時之後郵件到期及會傳回給寄件者的未傳遞回報 (也稱為 Ndr 或彈跳訊息)。</span><span class="sxs-lookup"><span data-stu-id="50c66-p102">Office 365 will continue to retry to delivery for 48 hours. After 48 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="50c66-p103">如果已排入佇列的電子郵件數量超過預先定義的臨界值 （預設值為 2000年郵件），提醒會出現在**最近提醒**、 郵件流程儀表板和系統管理員會收到電子郵件通知 （其替代的電子郵件地址）.若要設定的警示臨界值、 每日的通知限制及/或收件者的提醒，請參閱 ＜ **Customize 佇列提醒**] 區段下。</span><span class="sxs-lookup"><span data-stu-id="50c66-p103">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address). To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![在 Office 365 安全性 & 規範中心中的郵件流程儀表板的最近通知區域中的佇列提醒](media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="50c66-114">自訂佇列提醒</span><span class="sxs-lookup"><span data-stu-id="50c66-114">Customize queue alerts</span></span>

<span data-ttu-id="50c66-p104">郵件流程前瞻建立具名**的郵件已延遲**（**傳送電子郵件通知**] 核取方塊的範例螢幕擷取畫面下方）**提醒**中找到的警示原則\>**通知原則**。您可以在原則上按一下 [修改閾值] 和 [通知收件者。</span><span class="sxs-lookup"><span data-stu-id="50c66-p104">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**. You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![提醒導覽](media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="50c66-118">您會看見新的原則資訊 blade，您現在可以按一下 [**編輯原則**。</span><span class="sxs-lookup"><span data-stu-id="50c66-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![編輯原則 ](media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="50c66-p105">資訊 blade 會變更為**編輯原則**。您現在可以變更提醒電子郵件通知來觸發提醒 （200 或多個） 傳送每日和最小閾值數目限制的收件者。</span><span class="sxs-lookup"><span data-stu-id="50c66-p105">The information blade will change to the **Edit Policy**. You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![編輯原則 Blade](media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="50c66-123">佇列警示詳細資料</span><span class="sxs-lookup"><span data-stu-id="50c66-123">Queue alert details</span></span>

<span data-ttu-id="50c66-124">當您按一下此通知、 提醒的詳細資料窗格中出現彈出式。</span><span class="sxs-lookup"><span data-stu-id="50c66-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![在 Office 365 安全性 & 規範中心中的郵件流程儀表板最近的 [提醒] 區域中選取佇列提醒](media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![佇列警示的詳細資訊彈出式在 Office 365 安全性 & 規範中心](media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="50c66-127">您可以按一下**檢視佇列**中查看佇列的詳細資訊、 問題和連結的新彈出式窗格中可用的修正程式警示的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="50c66-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![佇列警示的詳細資訊彈出式在 Office 365 安全性 & 規範中心](media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![檢視佇列中的警示的詳細資料](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="50c66-130">佇列</span><span class="sxs-lookup"><span data-stu-id="50c66-130">Queues</span></span>

<span data-ttu-id="50c66-p106">即使已排入佇列的訊息數量尚未超出臨界值，您仍可以查看有一個小時以上的已排入佇列的郵件中使用郵件流程儀表板的 [**佇列**] 的區域。您可以使用 [**佇列**] 區域中監視佇列 （0 的值表示郵件流程 [確定]） 的郵件數目及已排入佇列的訊息數目變得太大之前採取動作。</span><span class="sxs-lookup"><span data-stu-id="50c66-p106">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour. You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![在 Office 365 安全性 & 規範中心中的郵件流程儀表板中的佇列](media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="50c66-134">當您按一下 [已排入佇列中的郵件數**佇列**佇列的詳細資訊和指導如何修正的問題會出現在彈出式窗格 （出現之後按一下佇列提醒的詳細資料中的 [**檢視佇列**相同彈出式）。</span><span class="sxs-lookup"><span data-stu-id="50c66-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![佇列的詳細資訊](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)
