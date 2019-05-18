---
title: 輸出和輸入郵件流程
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 8/7/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 系統管理員可以了解輸出和輸入的郵件流程 widget 安全性 & 合規性中心中的郵件流程儀表板中。
ms.openlocfilehash: 629599f6a71c1b871abb819ae4cdd339ffa5e56b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158725"
---
# <a name="outbound-and-inbound-mail-flow"></a><span data-ttu-id="09d88-103">輸出和輸入郵件流程</span><span class="sxs-lookup"><span data-stu-id="09d88-103">Outbound and inbound mail flow</span></span>

<span data-ttu-id="09d88-104">**輸出和輸入的郵件流程**] 小工具結合了來自**連接器報表**及離職**TLS 概觀報告**在同一個位置的資訊。</span><span class="sxs-lookup"><span data-stu-id="09d88-104">The **Outbound and inbound mail flow** widget combines the information from the **Connector Report** and the former **TLS Overview Report** in one place.</span></span>

![輸入與輸出郵件流程報表中的郵件流程儀表板中安全性 & 合規性中心](media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

<span data-ttu-id="09d88-106">[] 小工具中的資訊有關連接器和 Office 365 中的 TLS 郵件保護。</span><span class="sxs-lookup"><span data-stu-id="09d88-106">The information in the widget is related to connectors and TLS message protection in Office 365.</span></span> <span data-ttu-id="09d88-107">如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="09d88-107">For more information, see these topics:</span></span>

- [<span data-ttu-id="09d88-108">Configure mail flow using connectors in Office 365</span><span class="sxs-lookup"><span data-stu-id="09d88-108">Configure mail flow using connectors in Office 365</span></span>](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)

- [<span data-ttu-id="09d88-109">Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線</span><span class="sxs-lookup"><span data-stu-id="09d88-109">How Exchange Online uses TLS to secure email connections in Office 365</span></span>](https://support.office.com/article/4CDE0CDA-3430-4DC0-B489-F2C0736C929F)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="09d88-110">受保護傳輸中 （TLS) 的郵件</span><span class="sxs-lookup"><span data-stu-id="09d88-110">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="09d88-111">**輸出和輸入的郵件流程**] 小工具會顯示 TLS 加密的郵件會傳遞到及傳送自 Office 365 組織時所使用的連線。</span><span class="sxs-lookup"><span data-stu-id="09d88-111">The **Outbound and inbound mail flow** widget displays the TLS encryption that's used for the connection when messages are delivered to and from your Office 365 organization.</span></span> <span data-ttu-id="09d88-112">建立與其他電子郵件服務的連線加密的 TLS 時由兩邊所提供 TLS。</span><span class="sxs-lookup"><span data-stu-id="09d88-112">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="09d88-113">[] 小工具提供郵件流程中的最後一週的快照集。</span><span class="sxs-lookup"><span data-stu-id="09d88-113">The widget offers a snapshot of the last week of mail flow.</span></span> <span data-ttu-id="09d88-114">當您按一下 [**檢視詳細資料**時，**郵件保護 （由 TLS) 的傳輸中**彈出式視窗會顯示您進入及離開貴組織的 TLS 保護。</span><span class="sxs-lookup"><span data-stu-id="09d88-114">When you click **View Details**, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![保護安全性 & 合規性中心中 （藉由 TLS) 加密彈出式視窗中的郵件](media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

<span data-ttu-id="09d88-116">目前，TLS 1.2 是最安全的 Office 365 所提供的 TLS 版本。</span><span class="sxs-lookup"><span data-stu-id="09d88-116">Currently, TLS 1.2 is the most secure version of TLS that's offered by Office 365.</span></span> <span data-ttu-id="09d88-117">通常，您需要知道規範稽核正在使用 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="09d88-117">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="09d88-118">您可能沒有直接的關聯性與大部分的來源和目的地電子郵件伺服器 （不屬於您，以及 Microsoft 都不會），因此您不需要以改善這些伺服器會使用 TLS 加密的許多選項。</span><span class="sxs-lookup"><span data-stu-id="09d88-118">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="09d88-119">但是，您可以使用[連接器](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)來確保最佳使用 TLS 保護您的電子郵件伺服器和 Office 365 之間所傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="09d88-119">But, you can use [connectors](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx) to ensure the best available TLS protection for messages that are sent between your email servers and Office 365.</span></span> <span data-ttu-id="09d88-120">Office 365 和您自己的電子郵件伺服器或屬於協力廠商的伺服器之間的郵件流程會是較重要且機密比一般的郵件，因此您會想要將額外的安全性和警覺套用到這些郵件。</span><span class="sxs-lookup"><span data-stu-id="09d88-120">Mail flow between Office 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span> <span data-ttu-id="09d88-121">您可以升級或修正您自己的電子郵件伺服器，以改善正在使用中，或連絡您的夥伴進行相同的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="09d88-121">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="09d88-122">**連接器報表**顯示郵件流程音量和使用 Office 365 連接器的郵件使用 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="09d88-122">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Office 365 connectors.</span></span>

## <a name="connector-report"></a><span data-ttu-id="09d88-123">連接器報表</span><span class="sxs-lookup"><span data-stu-id="09d88-123">Connector report</span></span>

<span data-ttu-id="09d88-124">當您按一下**郵件保護 （由 TLS) 的傳輸中**的彈出式視窗**連接器報告**連結時，報表就會顯示郵件傳送到及傳送自使用連接器的 Office 365 組織的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="09d88-124">When you click on the **Connector Report** link from the **Message protected in transit (by TLS)** flyout, the report displays information about messages that are delivered to and from your Office 365 organization using connectors.</span></span> <span data-ttu-id="09d88-125">您使用您自己的電子郵件伺服器和 Office 365 或您的合作夥伴伺服器與 Office 365 之間的連接器。</span><span class="sxs-lookup"><span data-stu-id="09d88-125">You use connectors between your own email servers and Office 365 or your partner's servers and Office 365.</span></span> <span data-ttu-id="09d88-126">每個連接器的郵件音量和 TLS 加密的連線使用。</span><span class="sxs-lookup"><span data-stu-id="09d88-126">The message volume for each connector and the TLS encryption for the connection is available.</span></span> <span data-ttu-id="09d88-127">此外，您也可以檢視已傳送或接收 Office 365 中，而不需使用連接器的郵件資料。</span><span class="sxs-lookup"><span data-stu-id="09d88-127">In addition, you can also view data for messages that were sent or received in Office 365 without using a connector.</span></span>

<span data-ttu-id="09d88-128">[**郵件流程**] 檢視顯示過去一週的透過連接器的郵件數量。</span><span class="sxs-lookup"><span data-stu-id="09d88-128">The **Mail Flow** view shows the volume of messages through the connector for the past week.</span></span> <span data-ttu-id="09d88-129">您可以藉由選取**篩選**您可以在此提高為 30 天的最大值的範圍變更的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="09d88-129">You can change the date range by selecting **Filter** where you can increase the range to a maximum of 30 days.</span></span> <span data-ttu-id="09d88-130">**所有郵件流程**檢視顯示所有的郵件流程到及傳送自所有連接器透過 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="09d88-130">The **All Mail Flow** view shows all mail flow to and from your Office 365 organization through all connectors.</span></span> <span data-ttu-id="09d88-131">您可以選取特定連接器以在下拉式功能表中的名稱。</span><span class="sxs-lookup"><span data-stu-id="09d88-131">You can select a specific connector by name in the drop down menu.</span></span>

<span data-ttu-id="09d88-132">您可以從下分解為 TLS 保護透過連接器的郵件，請參閱下拉式清單選取**TLS 使用狀況**] 檢視。</span><span class="sxs-lookup"><span data-stu-id="09d88-132">You can select the **TLS usage** view from the drop down to see the breakdown of TLS protection for messages through the connector.</span></span> <span data-ttu-id="09d88-133">為**TLS 概觀報告**」 報告，這個檢視顯示不同的 TLS 版本的百分比。</span><span class="sxs-lookup"><span data-stu-id="09d88-133">As with the **TLS Overview Report** report, this view shows the percentage of the different TLS versions.</span></span> <span data-ttu-id="09d88-134">為 TLS 1.0 連線，您真的需要取得您的電子郵件伺服器或您的合作夥伴伺服器升級，或若要避免發生問題時 TLS 1.0 支援會最後已被取代的 Office 365 中修正。</span><span class="sxs-lookup"><span data-stu-id="09d88-134">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Office 365.</span></span> <span data-ttu-id="09d88-135">如需詳細資訊，請參閱[關於 Office 365 中加密的技術參考細節](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221)。</span><span class="sxs-lookup"><span data-stu-id="09d88-135">For more information, see [Technical reference details about encryption in Office 365](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221).</span></span>

<span data-ttu-id="09d88-136">深入了解指向連接器，以協助您注意到連接器的潛在 TLS 加密問題。</span><span class="sxs-lookup"><span data-stu-id="09d88-136">Insights point to connectors to help draw your attention to potential TLS encryption problems for the connector.</span></span> <span data-ttu-id="09d88-137">深入了解是：**否 TLS 是超過 25%** 或**TLS 1.0 大於 50%**。</span><span class="sxs-lookup"><span data-stu-id="09d88-137">The insights are: **No TLS is over 25%** or **TLS 1.0 is above 50%**.</span></span> <span data-ttu-id="09d88-138">如果您看到這些見解，您需要調查之相關聯的連接器，或連絡您的夥伴組織的電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="09d88-138">If you see these insights, you need to investigate your email servers that are associated with the connector, or reach out to your partner organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="09d88-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="09d88-139">See also</span></span>

<span data-ttu-id="09d88-140">如需郵件流程儀表板中其他郵件流程深入解析的詳細資訊，請參閱 <<c0>安全性 &amp; 合規性中心中的郵件流程深入解析。</span><span class="sxs-lookup"><span data-stu-id="09d88-140">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights.md).</span></span>
