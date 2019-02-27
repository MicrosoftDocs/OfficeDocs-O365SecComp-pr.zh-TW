---
title: Office 365 加密傳送過程中的資料
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 摘要： 簡短說明 Microsoft 加密傳送過程中的資料的方式。
ms.openlocfilehash: 596b884ac76c9b138d01958363c7921acf926345
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275843"
---
# <a name="office-365-encryption-for-data-in-transit"></a><span data-ttu-id="73304-103">Office 365 加密傳送過程中的資料</span><span class="sxs-lookup"><span data-stu-id="73304-103">Office 365 encryption for data in transit</span></span>

<span data-ttu-id="73304-104">除了在其餘的客戶資料保護、 Microsoft 會使用加密技術來保護傳輸的 Office 365 客戶資料。</span><span class="sxs-lookup"><span data-stu-id="73304-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect Office 365 customer data in transit.</span></span> 

<span data-ttu-id="73304-105">資料會傳送過程中：</span><span class="sxs-lookup"><span data-stu-id="73304-105">Data is in transit:</span></span>
- <span data-ttu-id="73304-106">在用戶端電腦與 Office 365 伺服器的通訊時</span><span class="sxs-lookup"><span data-stu-id="73304-106">when a client machine communicates with an Office 365 server;</span></span>
- <span data-ttu-id="73304-107">Office 365 伺服器會與其他 Office 365 伺服器通訊的時機與</span><span class="sxs-lookup"><span data-stu-id="73304-107">when an Office 365 server communicates with another Office 365 server; and</span></span>
- <span data-ttu-id="73304-108">當 Office 365 伺服器就會與非 Office 365 伺服器 (例如 Exchange Online 提供電子郵件至外部的電子郵件伺服器） 通訊。</span><span class="sxs-lookup"><span data-stu-id="73304-108">when an Office 365 server communicates with a non-Office 365 server (e.g., Exchange Online delivering email to a foreign email server).</span></span>

<span data-ttu-id="73304-p101">Office 365 伺服器之間的文字資料中心通訊，是透過 TLS 或 IPsec，進行與客戶使用的所有伺服器都交涉 TLS 使用用戶端機器安全工作階段 (例如 Exchange Online 使用 TLS 1.2 256 位元加密強度搭配使用 (FIPS140-2 層級 2 驗證)。（請參閱[Office 365 中加密的技術參考 （英文） 詳細](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221)如需 Office 365 支援 TLS 加密套件的清單）。這適用於 for Business 和 （例如 HTTP、 POP3、 等） 在 web 上的 Outlook 用戶端如 Outlook、 Skype 所使用的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="73304-p101">Inter-datacenter communications between Office 365 servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated). (See [Technical reference details about encryption in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="73304-p102">公用憑證是由發行 Microsoft IT SSL 使用 SSLAdmin，以保護傳輸資訊的機密性內部的 Microsoft 工具。Microsoft IT 所發出的所有憑證都具有至少要有 2048 位元長度，且[Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf)規範需要 SSLAdmin 以確定憑證會發出只以 Microsoft 所擁有的公用 IP 位址。無法以符合此準則的任何 IP 位址都被透過的例外狀況處理程序。</span><span class="sxs-lookup"><span data-stu-id="73304-p102">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information. All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf) compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft. Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="73304-p103">公開可用如 TLS 正在使用的版本、 是否要啟用轉寄加密 (FS)、 編碼器套件、 等的順序的所有實作詳細資料。請參閱下列詳細資料的其中一個方法是使用第三方網站，例如 Qualys SSL 實驗室 (www.ssllabs.com)。以下是可自動的測試的網頁連結從 Qualys 顯示下列服務的資訊：</span><span class="sxs-lookup"><span data-stu-id="73304-p103">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly. One way to see these details is to use a third-party website, such as Qualys SSL Labs (www.ssllabs.com). Below are the links to automated test pages from Qualys that display information for the following services:</span></span>
- [<span data-ttu-id="73304-117">Office 365 入口網站</span><span class="sxs-lookup"><span data-stu-id="73304-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="73304-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="73304-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="73304-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="73304-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="73304-120">Skype for Business (SIP)</span><span class="sxs-lookup"><span data-stu-id="73304-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="73304-121">Skype for Business (Web)</span><span class="sxs-lookup"><span data-stu-id="73304-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="73304-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="73304-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="73304-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73304-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="73304-124">Exchange Online Protection 的 Url 會因租用戶名稱 ；但是，所有客戶可以都測試使用**microsoft com.mail.protection.outlook.com**的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="73304-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Office 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>
