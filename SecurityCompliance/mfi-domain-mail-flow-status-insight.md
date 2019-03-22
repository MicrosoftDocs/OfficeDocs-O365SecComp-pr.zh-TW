---
title: 上層網域郵件流程狀態深入解析
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 系統管理員可以了解上方網域郵件流程狀態深入解析，在 Office 365 安全性 & 合規性中心中的郵件流程儀表板中。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 04aa986982465a4c66fbf99f517fb34622d65e19
ms.sourcegitcommit: fec1010e405f14e792d650aee0312b78fced3343
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2019
ms.locfileid: "30722811"
---
# <a name="top-domain-mail-flow-status-insight"></a><span data-ttu-id="ae835-103">上層網域郵件流程狀態深入解析</span><span class="sxs-lookup"><span data-stu-id="ae835-103">Top domain mail flow status insight</span></span>

> [!NOTE]
> <span data-ttu-id="ae835-104">本主題所述的功能尚未已部署至所有 Office 365 組織，並受限於變更。</span><span class="sxs-lookup"><span data-stu-id="ae835-104">The features described in this topic haven't been deployed to all Office 365 organizations, and are subject to change.</span></span>

<span data-ttu-id="ae835-105">**上層網域郵件流程狀態**深入了解提供您的目前狀態的郵件流程方面的貴組織的網域。</span><span class="sxs-lookup"><span data-stu-id="ae835-105">The **Top domain mail flow status** insight gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="ae835-106">此深入了解可協助您找出並疑難排解網域的***郵件流程影響***遇到問題 （例如，無法接收外部電子郵件），尤其是網域到期日或網域不正確的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="ae835-106">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![上層網域流程狀態深入了解在 Office 365 安全性 & 合規性中心中的郵件流程儀表板](media/domain-mail-flow-status-selected.png)

<span data-ttu-id="ae835-108">當您按一下 [**檢視詳細資料**中深入了解時，彈出式視窗會顯示，以顯示更多詳細資料，每個網域的狀態。</span><span class="sxs-lookup"><span data-stu-id="ae835-108">When you click **View details** in the insight, a flyout appears that shows you more details for the status of each domain.</span></span>

<span data-ttu-id="ae835-109">網域的綠色核取記號表示目前的 MX 記錄 （當您瀏覽至郵件流程深入了解儀表板） 符合我們對記錄的值與網域已在過去兩小時期間收到電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ae835-109">A green check mark for a domain indicates the current MX record (when you browsed to the mail flow insights dashboard) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

<span data-ttu-id="ae835-110">紅色的 x 網域會指出已經變更的 MX 記錄，並在網域已收到電子郵件不在過去的 6 個小時期間。</span><span class="sxs-lookup"><span data-stu-id="ae835-110">A red x for a domain indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="ae835-111">這可能表示，您的網域已過期，或 MX 記錄已正確更新。</span><span class="sxs-lookup"><span data-stu-id="ae835-111">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="ae835-112">請與您的網域註冊機構或 DNS 主機服務，才能查看如果網域已經過期，或者網域的 MX 記錄不正確。</span><span class="sxs-lookup"><span data-stu-id="ae835-112">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

![在上方網域流程狀態深入了解詳細資訊彈出式視窗](media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a><span data-ttu-id="ae835-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ae835-114">See also</span></span>

<span data-ttu-id="ae835-115">如需郵件流程儀表板中其他郵件流程深入解析的詳細資訊，請參閱 <<c0>安全性 &amp; 合規性中心中的郵件流程深入解析。</span><span class="sxs-lookup"><span data-stu-id="ae835-115">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
