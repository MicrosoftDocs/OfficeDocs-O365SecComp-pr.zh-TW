---
title: 輸出及輸入郵件流程
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 8/7/2018
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 系統管理員可了解輸出和輸入的郵件流程 widget Office 365 安全性 & 規範中心中的郵件流程儀表板中。
ms.openlocfilehash: 57792c0347490b40f97a8b92945a9c809484ba4f
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685386"
---
# <a name="outbound-and-inbound-mail-flow"></a><span data-ttu-id="ae1b9-103">輸出及輸入郵件流程</span><span class="sxs-lookup"><span data-stu-id="ae1b9-103">Outbound and inbound mail flow</span></span>

<span data-ttu-id="ae1b9-104">**輸出和輸入的郵件流程**widget 結合**連接器報告**與先前**TLS 概觀報告**集中一處的資訊。</span><span class="sxs-lookup"><span data-stu-id="ae1b9-104">The **Outbound and inbound mail flow** widget combines the information from the **Connector Report** and the former **TLS Overview Report** in one place.</span></span>

![輸出和輸入郵件流程報表中的 Office 365 安全性 & 規範中心郵件流程儀表板](media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

<span data-ttu-id="ae1b9-p101">連接器與 Office 365 中的 TLS 郵件保護相關 widget 中的資訊。如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="ae1b9-p101">The information in the widget is related to connectors and TLS message protection in Office 365. For more information, see these topics:</span></span>

- [<span data-ttu-id="ae1b9-108">Configure mail flow using connectors in Office 365</span><span class="sxs-lookup"><span data-stu-id="ae1b9-108">Configure mail flow using connectors in Office 365</span></span>](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)

- [<span data-ttu-id="ae1b9-109">Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線</span><span class="sxs-lookup"><span data-stu-id="ae1b9-109">How Exchange Online uses TLS to secure email connections in Office 365</span></span>](https://support.office.com/article/4CDE0CDA-3430-4DC0-B489-F2C0736C929F)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="ae1b9-110">受保護傳輸 （TLS) 的郵件</span><span class="sxs-lookup"><span data-stu-id="ae1b9-110">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="ae1b9-p102">**輸出和輸入的郵件流程**widget 顯示時所使用之連線的訊息傳遞到與 Office 365 組織 TLS 加密。當 TLS 由兩側提供由 TLS 加密與其他電子郵件服務所建立的連線。Widget 提供郵件流程的最後一週的快照。當您按一下 [**檢視詳細資料**時] **（透過 TLS) 傳送過程中受保護的郵件**彈出式會顯示您的郵件進入和離開貴組織的 TLS 保護。</span><span class="sxs-lookup"><span data-stu-id="ae1b9-p102">The **Outbound and inbound mail flow** widget displays the TLS encryption that's used for the connection when messages are delivered to and from your Office 365 organization. The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides. The widget offers a snapshot of the last week of mail flow. When you click **View Details**, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![在 Office 365 安全性 & 規範中心中的傳輸 （透過 TLS) 彈出式受保護的郵件](media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

<span data-ttu-id="ae1b9-p103">目前 TLS 1.2 是最安全版本的 Office 365 所提供的 TLS。通常，您需要知道用於規範稽核 TLS 加密。您可能沒有直接的關聯性大部分的來源和目的地電子郵件伺服器 （不屬於您，與 Microsoft 未實務） 與因此您不需要以改善這些伺服器所使用 TLS 加密的許多選項。</span><span class="sxs-lookup"><span data-stu-id="ae1b9-p103">Currently, TLS 1.2 is the most secure version of TLS that's offered by Office 365. Often, you'll need to know the TLS encryption that's being used for compliance audits. You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="ae1b9-p104">但是，您可以使用[連接器](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)來確保最佳可用 TLS 的保護您的電子郵件伺服器和 Office 365 之間傳送的郵件。Office 365 與您自己的電子郵件伺服器或該隸屬於您的協力廠商伺服器之間的郵件流程通常是多重要且敏感比一般郵件，讓您將想要將額外的安全性與警戒套用至那些郵件。您可以升級或修正電子郵件伺服器以改善正在使用，則或給您執行相同的協力廠商連絡 TLS 加密。**連接器報表**顯示郵件流程大量及使用 Office 365 連接器的郵件的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="ae1b9-p104">But, you can use [connectors](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx) to ensure the best available TLS protection for messages that are sent between your email servers and Office 365. Mail flow between Office 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages. You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same. The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Office 365 connectors.</span></span>

## <a name="connector-report"></a><span data-ttu-id="ae1b9-123">連接器報告</span><span class="sxs-lookup"><span data-stu-id="ae1b9-123">Connector report</span></span>

<span data-ttu-id="ae1b9-p105">當您按一下 [從 **（透過 TLS) 傳送過程中受保護的郵件**彈出式**連接器報告**] 連結時，報表會顯示會傳遞至與從 Office 365 組織使用連接器的郵件的相關資訊。您使用電子郵件伺服器與 Office 365 或協力廠商伺服器與 Office 365 之間的連接器。每個連接器的郵件量和 TLS 加密連線使用。此外，您也可以檢視傳送或接收到 Office 365 中不需要使用連接器的郵件的資料。</span><span class="sxs-lookup"><span data-stu-id="ae1b9-p105">When you click on the **Connector Report** link from the **Message protected in transit (by TLS)** flyout, the report displays information about messages that are delivered to and from your Office 365 organization using connectors. You use connectors between your own email servers and Office 365 or your partner's servers and Office 365. The message volume for each connector and the TLS encryption for the connection is available. In addition, you can also view data for messages that were sent or received in Office 365 without using a connector.</span></span>

<span data-ttu-id="ae1b9-p106">[**郵件流程**] 檢視顯示過去一週透過連接器訊息的數量。您可以藉由選取**篩選**出您可增加最大值為 30 天的範圍變更的日期範圍。所有的郵件流程與 Office 365 組織的所有連接線到**所有郵件流程**檢視顯示。您可以在下拉式清單功能表中的名稱選取特定的連接器。</span><span class="sxs-lookup"><span data-stu-id="ae1b9-p106">The **Mail Flow** view shows the volume of messages through the connector for the past week. You can change the date range by selecting **Filter** where you can increase the range to a maximum of 30 days. The **All Mail Flow** view shows all mail flow to and from your Office 365 organization through all connectors. You can select a specific connector by name in the drop down menu.</span></span>

<span data-ttu-id="ae1b9-p107">您可以從下分解為 TLS 保護郵件通過連接器，請參閱下拉式選取**TLS 使用狀況**] 檢視。為使用**TLS 概觀報告**報表這個檢視會顯示不同的 TLS 版本的百分比。TLS 1.0 連線真的要取得您的電子郵件伺服器或協力廠商伺服器升級或固定以避免 TLS 1.0 支援最後取代 Office 365 中的所有問題。如需詳細資訊，請參閱 ＜ [Office 365 中加密的相關的技術參考 （英文） 詳細資料](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221)。</span><span class="sxs-lookup"><span data-stu-id="ae1b9-p107">You can select the **TLS usage** view from the drop down to see the breakdown of TLS protection for messages through the connector. As with the **TLS Overview Report** report, this view shows the percentage of the different TLS versions. For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Office 365. For more information, see [Technical reference details about encryption in Office 365](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221).</span></span>

<span data-ttu-id="ae1b9-p108">前瞻指向連接器可協助您注意到連接器的潛在 TLS 加密等問題。觀點是：**無 TLS 超過 25%** 或**TLS 1.0 是高於 50%**。如果您看到這些觀點，您需要調查您的電子郵件伺服器相關聯連接器或到達協力廠商組織。</span><span class="sxs-lookup"><span data-stu-id="ae1b9-p108">Insights point to connectors to help draw your attention to potential TLS encryption problems for the connector. The insights are: **No TLS is over 25%** or **TLS 1.0 is above 50%**. If you see these insights, you need to investigate your email servers that are associated with the connector, or reach out to your partner organization.</span></span>
