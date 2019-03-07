---
title: 佇列的警示和佇列
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 系統管理員可以在 Office 365 安全性 & 合規性中心中的郵件流程儀表板中了解佇列的警示和佇列。
ms.openlocfilehash: 6abfe9e8b3edfc6b0ca02e11a9713dcdb5c19b7c
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454865"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="9d585-103">佇列的警示和佇列</span><span class="sxs-lookup"><span data-stu-id="9d585-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="9d585-104">佇列的警示</span><span class="sxs-lookup"><span data-stu-id="9d585-104">Queue alerts</span></span>

<span data-ttu-id="9d585-105">當郵件無法從 Office 365 組織傳送給內部或協力廠商電子郵件伺服器使用連接器，會將郵件佇列中 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9d585-105">When messages can't be sent from your Office 365 organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365.</span></span> <span data-ttu-id="9d585-106">造成這種情況的常見範例如下：</span><span class="sxs-lookup"><span data-stu-id="9d585-106">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="9d585-107">連接器的設定不正確。</span><span class="sxs-lookup"><span data-stu-id="9d585-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="9d585-108">在內部部署環境中已有網路或防火牆的變更。</span><span class="sxs-lookup"><span data-stu-id="9d585-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="9d585-109">Office 365 會繼續重試傳遞到 48 小時。</span><span class="sxs-lookup"><span data-stu-id="9d585-109">Office 365 will continue to retry to delivery for 48 hours.</span></span> <span data-ttu-id="9d585-110">48 小時之後，郵件會到期，且便會退回給寄件者的未傳遞回報 (也稱為 Ndr 或彈跳訊息)。</span><span class="sxs-lookup"><span data-stu-id="9d585-110">After 48 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="9d585-111">如果已排入佇列的電子郵件數量超過預先定義的臨界值 （預設值為 2000年郵件），提醒則可在**最近的通知**，在郵件流程儀表板，系統管理員也會收到電子郵件通知 （到他們的備用電子郵件地址）.</span><span class="sxs-lookup"><span data-stu-id="9d585-111">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address).</span></span> <span data-ttu-id="9d585-112">若要設定的警示臨界值，每日通知限制，及/或收件者的提醒，請參閱下方的**自訂佇列提醒**一節。</span><span class="sxs-lookup"><span data-stu-id="9d585-112">To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![在 Office 365 安全性 & 合規性中心中的郵件流程儀表板的最近使用的 [通知] 區域中的佇列警示](media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="9d585-114">自訂佇列的警示</span><span class="sxs-lookup"><span data-stu-id="9d585-114">Customize queue alerts</span></span>

<span data-ttu-id="9d585-115">郵件流程深入解析建立具名**的郵件已延遲**（**傳送電子郵件通知**] 核取方塊中範例螢幕擷取畫面下方） 找到**提醒**中的警示原則\>**警示原則**。</span><span class="sxs-lookup"><span data-stu-id="9d585-115">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**.</span></span> <span data-ttu-id="9d585-116">您可以藉由在原則上按一下 [修改閾值] 和 [警示收件者。</span><span class="sxs-lookup"><span data-stu-id="9d585-116">You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![提醒導覽](media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="9d585-118">您會看到新的原則資訊] 刀鋒視窗，您現在可以按一下 [**編輯原則**。</span><span class="sxs-lookup"><span data-stu-id="9d585-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![編輯原則](media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="9d585-120">[資訊] 刀鋒視窗會變更為**編輯原則**。</span><span class="sxs-lookup"><span data-stu-id="9d585-120">The information blade will change to the **Edit Policy**.</span></span> <span data-ttu-id="9d585-121">您現在可以變更警示電子郵件的每日和最小閾值傳送給觸發警示 （200 或多個） 的通知數目限制的收件者。</span><span class="sxs-lookup"><span data-stu-id="9d585-121">You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![編輯原則] 刀鋒視窗上](media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="9d585-123">佇列警示詳細資料</span><span class="sxs-lookup"><span data-stu-id="9d585-123">Queue alert details</span></span>

<span data-ttu-id="9d585-124">當您按一下警示時，警示的詳細資訊將出現在彈出式視窗窗格中。</span><span class="sxs-lookup"><span data-stu-id="9d585-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![在 Office 365 安全性 & 合規性中心中的郵件流程儀表板的最近使用的 [通知] 區域中選取佇列警示](media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![在 Office 365 安全性 & 合規性中心中佇列警示的詳細資訊彈出式視窗](media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="9d585-127">您可以按一下**檢視佇列**中警示的詳細資訊，請參閱佇列的詳細資訊、 問題和新的彈出式視窗窗格中可用的修正程式的連結。</span><span class="sxs-lookup"><span data-stu-id="9d585-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![在 Office 365 安全性 & 合規性中心中佇列警示的詳細資訊彈出式視窗](media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![檢視佇列中的警示的詳細資料](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="9d585-130">佇列</span><span class="sxs-lookup"><span data-stu-id="9d585-130">Queues</span></span>

<span data-ttu-id="9d585-131">即使已排入佇列的訊息數量並未超過臨界值，您仍然可以使用郵件流程儀表板的 [**佇列**] 區域若要查看已超過一小時已排入佇列的郵件。</span><span class="sxs-lookup"><span data-stu-id="9d585-131">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour.</span></span> <span data-ttu-id="9d585-132">您可以使用 [**佇列**] 區域來監視已排入佇列 （值為 0 表示郵件流程 [確定]） 的郵件數目，並採取動作之前已排入佇列的訊息數目變得太大。</span><span class="sxs-lookup"><span data-stu-id="9d585-132">You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![在 Office 365 安全性 & 合規性中心中的郵件流程儀表板中的佇列](media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="9d585-134">當您按一下 [已排入佇列中的郵件數目**佇列**，佇列的詳細資訊和指導方針如何修正問題都會出現在彈出式視窗窗格 （會在您按一下**檢視佇列**中的佇列警示詳細資料之後出現相同彈出式）。</span><span class="sxs-lookup"><span data-stu-id="9d585-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![佇列的詳細資訊](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)
