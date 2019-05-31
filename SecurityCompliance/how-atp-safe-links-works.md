---
title: Office 365 ATP 安全連結的運作方式
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.date: 05/19/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 安全連結功能提供 Office 文件和電子郵件訊息中的超連結的時間按一下 [的驗證。 閱讀本篇文章以了解 ATP 安全連結的運作方式。
ms.openlocfilehash: eb4c9f9eea18990df190185a78b5a8c333e53659
ms.sourcegitcommit: 424a614141c1f19a1c84a67ec2d71dd3d7ef6694
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/30/2019
ms.locfileid: "34592252"
---
# <a name="how-office-365-atp-safe-links-works"></a><span data-ttu-id="11474-104">Office 365 ATP 安全連結的運作方式</span><span class="sxs-lookup"><span data-stu-id="11474-104">How Office 365 ATP Safe Links works</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="11474-105">ATP 安全連結的運作方式與 Url 以電子郵件</span><span class="sxs-lookup"><span data-stu-id="11474-105">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="11474-106">在高的層級，以下是[ATP 安全連結](atp-safe-links.md)保護中的運作方式的 Url （裝載於 Office 365，不在內部） 的電子郵件：</span><span class="sxs-lookup"><span data-stu-id="11474-106">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="11474-107">人員會收到電子郵件訊息，其中有些包含的 Url。</span><span class="sxs-lookup"><span data-stu-id="11474-107">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="11474-108">所有電子郵件通過 Exchange Online Protection，其中網際網路通訊協定 (IP) 及信封篩選，簽章型惡意程式碼防護，反垃圾郵件和反惡意軟體篩選器。</span><span class="sxs-lookup"><span data-stu-id="11474-108">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="11474-109">電子郵件會送達人民收件匣。</span><span class="sxs-lookup"><span data-stu-id="11474-109">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="11474-110">使用者登入 Office 365，並移至其電子郵件收件匣。</span><span class="sxs-lookup"><span data-stu-id="11474-110">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="11474-111">使用者開啟電子郵件訊息，並按一下電子郵件訊息中的 URL。</span><span class="sxs-lookup"><span data-stu-id="11474-111">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="11474-112">ATP 安全連結功能立即檢查才能開啟之網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="11474-112">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="11474-113">URL 被識別為惡意，/ 安全封鎖。</span><span class="sxs-lookup"><span data-stu-id="11474-113">The URL is identified as blocked, malicious, or safe.</span></span>
    
    - <span data-ttu-id="11474-114">如果 URL 包含在[自訂 「 不要重寫 」 Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)將套用至使用者原則的網站，網站會隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="11474-114">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens.</span></span> 
    
    - <span data-ttu-id="11474-115">組織[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的網站 URL 時，會開啟[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="11474-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="11474-116">已判定為惡意的網站 URL 時，會開啟[警告] 頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="11474-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="11474-117">如果 URL 會前往可下載的檔案，且貴組織的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定可掃描這類內容，會檢查可下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="11474-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
    - <span data-ttu-id="11474-118">如果 URL 會決定為了安全起見，網站會隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="11474-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="11474-119">ATP 安全連結的運作方式與 Url 中的 Office 文件</span><span class="sxs-lookup"><span data-stu-id="11474-119">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="11474-120">在高的層級，以下是[ATP 安全連結](atp-safe-links.md)保護中的運作方式 Url 的 Office 365 專業增強版應用程式 （目前版本的 Word、 Excel 及 PowerPoint Windows 或 Mac、 iOS 或 Android 裝置，Windows、 OneNote Online，與 Office Visio 的 Office 應用程式線上）：</span><span class="sxs-lookup"><span data-stu-id="11474-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Office 365 ProPlus applications (current versions of Word, Excel, and PowerPoint on Windows or Mac, Office apps on iOS or Android devices, Visio on Windows, OneNote Online, and Office Online):</span></span>
  
1. <span data-ttu-id="11474-121">人員在其電腦、 智慧型手機或平板電腦上安裝 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="11474-121">People have installed Office 365 ProPlus on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="11474-122">（或者，他們會使用 Office Online 在其瀏覽器中）。</span><span class="sxs-lookup"><span data-stu-id="11474-122">(Or, they are using Office Online in their browser.)</span></span>
    
2. <span data-ttu-id="11474-123">使用者開啟 Word、 Excel、 PowerPoint 或 Visio，並為 Office 365 企業版使用其公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="11474-123">A user opens a Word, Excel, PowerPoint, or Visio, and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="11474-124">文件中包含的 Url。</span><span class="sxs-lookup"><span data-stu-id="11474-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="11474-125">當使用者在 [文件中的 URL 時，連結會檢查 ATP 安全連結服務。</span><span class="sxs-lookup"><span data-stu-id="11474-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
      - <span data-ttu-id="11474-126">如果 URL 是包含在[自訂 「 不要重寫 」 Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)將套用至使用者原則的網站，該使用者不會採取至網站。</span><span class="sxs-lookup"><span data-stu-id="11474-126">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
      - <span data-ttu-id="11474-127">URL 是包含在組織的[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)的網站，如果使用者不會採取至[警告頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="11474-127">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
      - <span data-ttu-id="11474-128">如果已決定為惡意的網站 URL，使用者會採取至[警告頁面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="11474-128">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
      - <span data-ttu-id="11474-129">如果 URL 會前往可下載的檔案，且[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定可掃描這類的下載項目，會檢查可下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="11474-129">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
      - <span data-ttu-id="11474-130">URL 會被視為安全，如果使用者不會採取至網站。</span><span class="sxs-lookup"><span data-stu-id="11474-130">If the URL is considered safe, the user is taken to the website.</span></span>

