---
title: SMTP 驗證用戶端報告
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 系統管理員可以在安全性與合規性中心中郵件流程儀表板深入了解 SMTP 驗證用戶端報告。
ms.openlocfilehash: 21d2446bd7441f17c2371186d098118c6403de0c
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598129"
---
# <a name="smtp-auth-clients-report"></a><span data-ttu-id="72985-103">SMTP 驗證用戶端報告</span><span class="sxs-lookup"><span data-stu-id="72985-103">SMTP Auth clients report</span></span>

<span data-ttu-id="72985-104">**SMTP 驗證用戶端**報告會醒目提示您組織中的使用者或系統帳戶對 SMTP 驗證用戶端提交通訊協定的使用。</span><span class="sxs-lookup"><span data-stu-id="72985-104">The **SMTP Auth clients** report highlights the use of the SMTP Auth client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="72985-105">此舊通訊協定（使用端點 smtp.office365.com）僅提供基本身份驗證，並且易受帳戶洩漏使用以發送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="72985-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span>  <span data-ttu-id="72985-106">這份報告可讓您檢查是否有異常活動。</span><span class="sxs-lookup"><span data-stu-id="72985-106">This report allows you to check for unusual activity.</span></span> <span data-ttu-id="72985-107">它也顯示使用 SMTP 驗證的客戶端或裝置的 TLS 使用量資料。</span><span class="sxs-lookup"><span data-stu-id="72985-107">It also shows the TLS usage data for clients or devices using SMTP Auth.</span></span>

<span data-ttu-id="72985-108">郵件流程儀表板中顯示的小工具表示前 7 天內使用 SMTP 驗證通訊協定的使用者或服務帳戶的數量。</span><span class="sxs-lookup"><span data-stu-id="72985-108">The widget that's shown in the Mail Flow dashboard indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![安全性與合規性中心中郵件流程儀表板的 SMTP 驗證用戶端](media/smtp-auth-clients-report-selected.png)

<span data-ttu-id="72985-110">按一下小工具中會開啟一個飛出示窗，提供上週 TLS 的使用情況與用量的彙總檢視。</span><span class="sxs-lookup"><span data-stu-id="72985-110">Clicking on the widget opens a flyout that provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![SMTP 驗證用戶端報告的飛出視窗](media/smtp-auth-clients-flyout.png)

<span data-ttu-id="72985-112">當您按一下**SMTP 驗證用戶端報告**的連結，您會看到兩個主要資料樞紐與兩個資料檢視。</span><span class="sxs-lookup"><span data-stu-id="72985-112">When you click on the **SMTP Auth Clients Report** link, you'll see two main data pivots and two data views.</span></span> <span data-ttu-id="72985-113">資料樞紐是**寄出量**與 **TLS 使用方式**。</span><span class="sxs-lookup"><span data-stu-id="72985-113">The data pivots are the **Sending Volume** and **TLS Usage**.</span></span> <span data-ttu-id="72985-114">資料檢視是圖表和詳細資料表格。</span><span class="sxs-lookup"><span data-stu-id="72985-114">The data views are the chart and the details table.</span></span>

<span data-ttu-id="72985-115">**寄出量**檢視會顯示在指定時間範圍內使用 SMTP 驗證所傳送的訊息數量。</span><span class="sxs-lookup"><span data-stu-id="72985-115">The **Sending Volume** view shows the number of messages that were sent using SMTP Auth for the specified time range.</span></span> <span data-ttu-id="72985-116">您可以按一下**篩選條件**來調整範圍。</span><span class="sxs-lookup"><span data-stu-id="72985-116">You can adjust the range by clicking **Filters**.</span></span> <span data-ttu-id="72985-117">圖表會依寄件者的網域來排列。</span><span class="sxs-lookup"><span data-stu-id="72985-117">The chart is organized by sender domain.</span></span> <span data-ttu-id="72985-118">您可以透過選取**顯示資料**下拉式清單中的網域看到不同網域的資料。</span><span class="sxs-lookup"><span data-stu-id="72985-118">You can see separate data for each domain by selecting the domain in the **Show data for** drop down.</span></span>

![SMTP 驗證用戶端報告的寄出量](media/smtp-auth-clients-report-sending-volume.png)

<span data-ttu-id="72985-120">您可以透過點選**檢視詳細資料表格**來檢視寄件者與訊息數的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="72985-120">You can view detailed information about the senders and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="72985-121">若要返回圖表，請按一下**檢視報告**。</span><span class="sxs-lookup"><span data-stu-id="72985-121">To return to the chart, click **View report**.</span></span>

![SMTP 驗證用戶端報告的寄出量詳細資料表格](media/smtp-auth-clients-report-details-sending-volume.png)

<span data-ttu-id="72985-123">**TLS 使用方式**樞紐是很重要，因為 Office 365 TLS1.0 和 TLS1.1 即將面臨淘汰。</span><span class="sxs-lookup"><span data-stu-id="72985-123">The **TLS Usage** pivot is important due to the upcoming deprecation of TLS1.0 and TLS1.1 in Office 365.</span></span> <span data-ttu-id="72985-124">如果許多舊裝置和應用程式僅能夠使用帶有 SMTP 驗證的TLS1.0，則將無法發送電子郵件。透過此樞紐，您可以識別仍在使用舊版 TLS 的用戶和系統帳戶，並對其執行操作。</span><span class="sxs-lookup"><span data-stu-id="72985-124">Many legacy devices and applications will be unable to send email if they are only capable of using TLS1.0 with SMTP Auth. This pivot allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

![SMTP 驗證用戶端報告的 TLS 使用方式](media/smtp-auth-clients-report-tls-usage.png)

<span data-ttu-id="72985-126">您可以透過點選**檢視詳細資料表格**來檢視寄件者，寄件者使用 SMTP 驗證的 TLS 版本，與訊息數的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="72985-126">You can view detailed information about the senders, the versions of TLS they are using with SMTP Auth, and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="72985-127">若要返回圖表，請按一下**檢視報告**。</span><span class="sxs-lookup"><span data-stu-id="72985-127">To return to the chart, click **View report**.</span></span>

<span data-ttu-id="72985-128">您也可以透過點按要求報告，下載更詳細的報告版本。</span><span class="sxs-lookup"><span data-stu-id="72985-128">You can also download a more detailed version of the report by clicking Request report.</span></span>

![SMTP 驗證用戶端報告的 TLS 使用方式詳細資料表格](media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a><span data-ttu-id="72985-130">請參閱</span><span class="sxs-lookup"><span data-stu-id="72985-130">See also</span></span>

<span data-ttu-id="72985-131">如需有關郵件流程儀表板中的其他郵件流程深入解析，請參閱[安全性與合規性中心內的郵件流程深入解析](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="72985-131">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
