---
title: 保護您電子郵件快速入門影片
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: laurawi
ms.date: 2/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: 簡介本文可協助您了解 Exchange Online Protection (EOP)，以及一些重要術語。 這是適用於 Office 365 客戶可以保護 Exchange Online 雲端託管信箱，而且獨立式 EOP 客戶負責保護內部部署信箱，例如 Exchange Server 2016。
ms.openlocfilehash: f9c966fd2e4ca4788b6400aba337019c49f56b84
ms.sourcegitcommit: 9403f8f038a9940f1b6299fc7d5c560bb7fbcc41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/27/2019
ms.locfileid: "30310003"
---
## <a name="what-is-exchange-online-protection-eop"></a><span data-ttu-id="4a3ff-104">Exchange Online Protection (EOP) 是什麼</span><span class="sxs-lookup"><span data-stu-id="4a3ff-104">What is Exchange Online Protection (EOP)</span></span>

<span data-ttu-id="4a3ff-105">Exchange Online Protection (EOP) 是雲端式電子郵件篩選服務，可協助組織抵禦垃圾郵件和惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-105">Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="4a3ff-106">如果您有 Office 365 中的信箱時，他們會自動由 EOP 保護因為它是服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-106">If you have mailboxes in Office 365, they are automatically protected by EOP since it is part of the service.</span></span> <span data-ttu-id="4a3ff-107">這包括擁有信箱 Office 365 和內部部署，這通常稱為混合式案例中的組織。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-107">This includes organizations that have mailboxes in both Office 365 and on-premise, which is commonly known as a hybrid scenario.</span></span> <span data-ttu-id="4a3ff-108">獨立式 EOP 也適用於在雲端中沒有信箱，但想要保護其內部部署信箱的客戶。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-108">EOP standalone is also available for customers who do not have mailboxes in the cloud but want to protect their on-premise mailboxes.</span></span> 

<span data-ttu-id="4a3ff-109">EOP 會嘗試篩選出垃圾郵件，並保留清除使用者不想要看到的內容的收件匣。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-109">EOP attempts to filter out junk, keeping your Inbox clear of content that users don't want to see.</span></span> <span data-ttu-id="4a3ff-110">一般而言，垃圾郵件會傳遞至垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-110">Normally, junk mail is delivered to the Junk Email folder.</span></span> <span data-ttu-id="4a3ff-111">某些使用者想要檢查並確認篩選所做的動作他們想要讓 [垃圾郵件] 資料夾是簡單的方法若要檢查其自己的使用者。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-111">Some users like to check to make sure the filtering is doing what they want so the Junk Email folder is an easy way for users to check on their own.</span></span>  

> [!TIP]
> <span data-ttu-id="4a3ff-112">它是個好方法時垃圾或否則不正確的電子郵件郵件會移至 [垃圾郵件] 資料夾會自動。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-112">It is a good thing when junk or otherwise bad email goes into the Junk Email folder automatically.</span></span> <span data-ttu-id="4a3ff-113">此服務會執行什麼是必要項目為基礎的預設或自訂的系統管理員設定狀態。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-113">The service will do what is necessary based on what the default or the custom admin settings state.</span></span> <span data-ttu-id="4a3ff-114">也就是說，使用者不必擔心看到大量的垃圾郵件] 資料夾中的 [垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-114">In other words, users should not worry about seeing a lot of spam mail in the Junk Email folder.</span></span> <span data-ttu-id="4a3ff-115">如果系統管理員想要移動所有目視超出垃圾郵件，則應該設定隔離區。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-115">If admins prefer to move all junk out of sight, then the Quarantine should be configured.</span></span> <span data-ttu-id="4a3ff-116">如需詳細資訊，請參閱 < <b0>Office 365 中的隔離電子郵件</b0>> 一文。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-116">For more details, see the [Quarantine email messages in Office 365](quarantine-email-messages.md) article.</span></span>

## <a name="important-terms"></a><span data-ttu-id="4a3ff-117">重要詞彙</span><span class="sxs-lookup"><span data-stu-id="4a3ff-117">Important terms</span></span>

<span data-ttu-id="4a3ff-118">**輸入：** 會進入 Office 365 的郵件。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-118">**Inbound:** Messages that are coming into Office 365.</span></span>

<span data-ttu-id="4a3ff-119">**輸出：** 即將登出 Office 365 的郵件。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-119">**Outbound:** Messages that are going out of Office 365.</span></span>

<span data-ttu-id="4a3ff-120">**內部：** 會從組織內部的人員給某人在組織內的郵件。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-120">**Internal:** Messages that are from someone inside the organization to someone inside the organization.</span></span> <span data-ttu-id="4a3ff-121">這包括混合式案例中的客戶和一個信箱可能是內部部署與其他信箱位於雲端。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-121">This includes customers who are in hybrid scenarios and one mailbox could be on-premise and the other mailbox is in the cloud.</span></span>

<span data-ttu-id="4a3ff-122">**誤判 (FN):** 垃圾郵件和其他不正確地取得傳送至收件匣的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-122">**False Negative (FN):** Spam and other junk that incorrectly gets sent into the inbox.</span></span>

<span data-ttu-id="4a3ff-123">**誤判 (FP):** 不正確地取得標示為垃圾郵件並放入垃圾郵件] 資料夾或隔離的合法郵件。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-123">**False Positive (FP):** Legitimate messages that incorrectly get marked as spam and put into the Junk Email folder or Quarantine.</span></span>

<span data-ttu-id="4a3ff-124">**垃圾郵件，也稱為來路不明的電子郵件：** 這樣的處理的商業廣告、 鏈結字母、 政治郵寄等形式。這是使用者未登入和 from 人員嘗試請求產品或嘗試認可詐騙濫發垃圾郵件者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-124">**Spam, also known as unsolicited e-mail:** This comes in the form of commercial advertising, chain letters, political mailings, etc. This is email that users do not sign up for and from spammers who are trying to solicit products or attempting to commit fraud.</span></span>

<span data-ttu-id="4a3ff-125">**Phish:** 網路釣魚是特殊類型的要放棄目的認可 identity 竊取或詐騙的個人資訊誘使您的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-125">**Phish:** Phishing is a special type of spam that is intended to trick you into giving up personal information for the purpose of committing identity theft or fraud.</span></span> <span data-ttu-id="4a3ff-126">此類型的郵件通常包含惡意連結或附件，但並非絕對。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-126">This type of message usually contains a malicious link or attachment, but not always.</span></span>

<span data-ttu-id="4a3ff-127">**詐騙：** 詐騙是濫發垃圾郵件者偽造 FROM 標頭，以便郵件似乎來自是由其他人或地方以外的實際的來源時。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-127">**Spoof:** Spoofing is when spammers forge the FROM header so that messages appear to have originated from someone or somewhere other than the actual source.</span></span> <span data-ttu-id="4a3ff-128">這可以是垃圾郵件，但最常用於釣魚程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-128">This can be spam but most commonly used to phish users.</span></span>

<span data-ttu-id="4a3ff-129">**模擬：** 這種類型的垃圾郵件也是一種偽造的寄件者地址，但是它，就可以修改的名稱或網域的一部分，使它看起來像是的真正來源。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-129">**Impersonation:** This type of spam is also a way to forge the sender address, but it is done by modifying part of the name or domain so that it looks like the real source.</span></span> <span data-ttu-id="4a3ff-130">例如，Bi11@micr0s0ft.com，其中"l"Bill 中的處於實際數目 eleven 和 「 o 「 Microsoft 已取代數字零。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-130">For example, Bi11@micr0s0ft.com, where the "l" in Bill was actually the number eleven and the "o" in Microsoft was replaced with the number zero.</span></span>

<span data-ttu-id="4a3ff-131">**大量：** 大宗郵件通常會請求的使用者，雖然有時間接時公司銷售資訊給其他公司。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-131">**Bulk:** Bulk mail is usually solicited by users, although sometimes indirectly when companies sell information to other companies.</span></span> <span data-ttu-id="4a3ff-132">它是常見的使用者是刻意註冊大宗郵件 (亦即 newletters)，但稍後忘記並認為它是垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-132">It is common that users intentionally sign up for bulk mail (i.e. newletters) but forget later on and think it is spam.</span></span> <span data-ttu-id="4a3ff-133">更多的使用者註冊及抱怨層級取得太高傳送大量郵件寄件者時，大宗郵件就會成為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="4a3ff-133">Bulk mail becomes spam when bulk mailers send more than users sign up and complaint levels get too high.</span></span>
