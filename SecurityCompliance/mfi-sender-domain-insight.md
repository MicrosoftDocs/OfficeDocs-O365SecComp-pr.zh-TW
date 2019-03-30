---
title: 修正寄件者網域深入解析
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 系統管理員可以了解修正寄件者網域深入了解安全性 & 合規性中心中的郵件流程儀表板中。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: bd62d6d0b42edfd1eedf543d7d8bb68903c7c608
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000306"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="de491-103">修正寄件者網域深入解析</span><span class="sxs-lookup"><span data-stu-id="de491-103">Fix sender domain insight</span></span>

> [!NOTE]
> <span data-ttu-id="de491-104">本主題所述的功能尚未已部署至所有 Office 365 組織，並受限於變更。</span><span class="sxs-lookup"><span data-stu-id="de491-104">The features described in this topic haven't been deployed to all Office 365 organizations, and are subject to change.</span></span>

<span data-ttu-id="de491-105">Office 365 需要從內部電子郵件環境到 Office 365 傳送到符合特定安全性條件的郵件：</span><span class="sxs-lookup"><span data-stu-id="de491-105">Office 365 requires messages sending from internal on-premises email environments to Office 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="de491-106">您已在使用來源 IP 位址或憑證驗證從您的內部部署電子郵件伺服器的 SMTP 連線的 Office 365 中建立的輸入的連接器。</span><span class="sxs-lookup"><span data-stu-id="de491-106">You've created an inbound connector in Office 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="de491-107">您已設定內部部署電子郵件伺服器轉送外部世界透過 Office 365 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="de491-107">You've configured your on-premises email server to relay email via Office 365 to external world.</span></span>

- <span data-ttu-id="de491-108">在您的組態，其中一個下列陳述式為真：</span><span class="sxs-lookup"><span data-stu-id="de491-108">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="de491-109">寄件者的電子郵件網域註冊 Office 365 組織中。</span><span class="sxs-lookup"><span data-stu-id="de491-109">The sender's email domain is registered in your Office 365 organization.</span></span> <span data-ttu-id="de491-110">如需詳細資訊，請參閱 < Office 365 中的 [新增網域。</span><span class="sxs-lookup"><span data-stu-id="de491-110">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="de491-111">內部部署電子郵件伺服器設定為使用憑證來傳送電子郵件給 Office 365 憑證包含或完全符合您已在 Office 365 中註冊的網域名稱，您已在 Office 365 中建立憑證型連接器程式網域。</span><span class="sxs-lookup"><span data-stu-id="de491-111">Your on-premises email server is configured to use a certificate to send email to Office 365, the certificate contains or exactly matches a domain name that you've registered in Office 365, and you've created a certificate based connector in Office 365 with that domain.</span></span> 

<span data-ttu-id="de491-112">不符合準則的郵件不歸因於組織，可能會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="de491-112">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="de491-113">**修正寄件者網域**深入了解顯示您的電子郵件從內部部署環境不符合準則，可協助您識別可能入侵的機器和使用者帳戶在內部部署電子郵件環境中，可協助您採取修復動作。</span><span class="sxs-lookup"><span data-stu-id="de491-113">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![在 [郵件流程儀表板中的安全性 & 合規性中心修正寄件者網域深入解析](media/sender-domain-insight-selected.png)

<span data-ttu-id="de491-115">當您按一下 [**檢視詳細資料**時，您將被帶往另一個小工具以更多的詳細資訊，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="de491-115">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![[詳細資料] 小工具在修正寄件者網域深入解析](media/sender-domain-view-details.png)

<span data-ttu-id="de491-117">您會看到已用來將郵件傳遞到 Office 365 的輸入的連接器。</span><span class="sxs-lookup"><span data-stu-id="de491-117">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="de491-118">您也可以按一下**檢視範例郵件識別碼**，以查看從內部部署電子郵件環境傳送郵件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="de491-118">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="de491-119">因為這些郵件所拒絕的 Office 365，您無法使用郵件追蹤，但您可以使用範例郵件識別碼在內部部署電子郵件環境中追蹤郵件。</span><span class="sxs-lookup"><span data-stu-id="de491-119">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![在修正寄件者網域深入了解檢視範例郵件識別碼](media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a><span data-ttu-id="de491-121">請參閱</span><span class="sxs-lookup"><span data-stu-id="de491-121">See also</span></span>

<span data-ttu-id="de491-122">如需郵件流程儀表板中其他郵件流程深入解析的詳細資訊，請參閱 <<c0>安全性 &amp; 合規性中心中的郵件流程深入解析。</span><span class="sxs-lookup"><span data-stu-id="de491-122">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
