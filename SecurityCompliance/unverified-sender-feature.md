---
title: 識別 Outlook.com 和網頁型 Outlook 中的可疑郵件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 若要防止網路釣魚郵件送達您的信箱，Outlook.com 和網頁型 Outlook 確認寄件者是誰他們說他們且可疑的郵件標示為垃圾郵件。
ms.openlocfilehash: edba30bb2ac0f9dc6ebc12db957a518de0c1b543
ms.sourcegitcommit: 9907bebc5f225032f681c4952de0b0be2df278ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2019
ms.locfileid: "33345888"
---
# <a name="identify-suspicious-messages-in-outlookcom-and-outlook-on-the-web"></a><span data-ttu-id="04e5b-103">識別 Outlook.com 和網頁型 Outlook 中的可疑郵件</span><span class="sxs-lookup"><span data-stu-id="04e5b-103">Identify suspicious messages in Outlook.com and Outlook on the web</span></span>

<span data-ttu-id="04e5b-104">若要防止網路釣魚郵件送達您的信箱，Outlook.com 和網頁型 Outlook 確認寄件者是誰他們說他們且可疑的郵件標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="04e5b-104">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04e5b-105">當郵件標示為網路釣魚詐騙、 Outlook.com 和 Outlook 網頁顯示一則警告] 頁面頂端，但仍然可以開啟任何郵件中的連結。</span><span class="sxs-lookup"><span data-stu-id="04e5b-105">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="04e5b-106">如何識別我的收件匣中的可疑的郵件？</span><span class="sxs-lookup"><span data-stu-id="04e5b-106">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="04e5b-107">Outlook.com 和網頁型 Outlook 顯示指標，當郵件的寄件者也無法識別或其身分識別為不同於從地址中看到的內容。</span><span class="sxs-lookup"><span data-stu-id="04e5b-107">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

### <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="04e5b-108">您會看到 '？ ' 中的寄件者影像</span><span class="sxs-lookup"><span data-stu-id="04e5b-108">You see a '?' in the sender image</span></span>

<span data-ttu-id="04e5b-109">當 Outlook.com 和網頁型 Outlook 無法驗證使用電子郵件驗證技術的寄件者的身分識別時，他們會顯示 '？ ' 中的寄件者相片。</span><span class="sxs-lookup"><span data-stu-id="04e5b-109">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span>

![郵件未通過驗證](media/message-did-not-pass-verification.jpg)

<span data-ttu-id="04e5b-111">若要驗證失敗不是每個訊息是惡意。</span><span class="sxs-lookup"><span data-stu-id="04e5b-111">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="04e5b-112">不過，您應該謹慎互動與未驗證如果您不能辨識寄件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="04e5b-112">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="04e5b-113">或者，如果您辨識通常沒有寄件者 '？ ' 寄件者的影像，但您突然開始看到它，可能會登寄件者詐騙。</span><span class="sxs-lookup"><span data-stu-id="04e5b-113">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

### <a name="the-senders-address-is-different-than-what-appears-in-the-from-address"></a><span data-ttu-id="04e5b-114">寄件者地址是不同的 From 地址中顯示的內容</span><span class="sxs-lookup"><span data-stu-id="04e5b-114">The sender's address is different than what appears in the From address</span></span>

<span data-ttu-id="04e5b-115">通常，您看到訊息中的電子郵件地址是不同於從地址中看到的內容。</span><span class="sxs-lookup"><span data-stu-id="04e5b-115">Frequently, the email address you see in a message is different than what you see in the From address.</span></span> <span data-ttu-id="04e5b-116">有時網路釣客會嘗試誘騙寄件者是其他人以外人員它們確實是的想法。</span><span class="sxs-lookup"><span data-stu-id="04e5b-116">Sometimes phishers try to trick you into thinking that the sender is someone other than who they really are.</span></span>

<span data-ttu-id="04e5b-117">當 Outlook.com 和 outlook 網頁版偵測寄件者的實際地址與寄地址的地址之間的差異時，它們會顯示實際寄件者，並使用透過標記，這會加上底線。</span><span class="sxs-lookup"><span data-stu-id="04e5b-117">When Outlook.com and Outlook on the web detect a difference between the sender's actual address and the address on the From address, they show the actual sender using the via tag, which will be underlined.</span></span>

![未驗證的寄件者的替代文字](media/unverified-sender-feature1.png)

<span data-ttu-id="04e5b-119">在這個範例中，在傳送網域`suspicious.com`通過驗證，但寄件者放`unknown@contoso.com`From 地址。</span><span class="sxs-lookup"><span data-stu-id="04e5b-119">In this example, the sending domain `suspicious.com` is authenticated, but the sender put `unknown@contoso.com` in the From address.</span></span>

<span data-ttu-id="04e5b-120">不是每個郵件透過標記為可疑。</span><span class="sxs-lookup"><span data-stu-id="04e5b-120">Not every message with a via tag is suspicious.</span></span> <span data-ttu-id="04e5b-121">不過，如果您不能辨識郵件透過標記，您應該謹慎與其互動。</span><span class="sxs-lookup"><span data-stu-id="04e5b-121">However, if you don't recognize a message with a via tag, you should be cautious about interacting with it.</span></span>

<span data-ttu-id="04e5b-122">在 Outlook.com 和新網頁型 Outlook 中，您可以將游標停留寄件者的名稱或郵件清單中，查看他們的電子郵件地址，而不需要開啟該郵件的地址。</span><span class="sxs-lookup"><span data-stu-id="04e5b-122">In Outlook.com and the new Outlook on the web, you can hover your cursor over a sender's name or address in the message list to see their email address, without needing to open the message.</span></span>

![開始使用 OneDrive](media/get-started-with-onedrive-message.png)

<span data-ttu-id="04e5b-124">如何知道是否您使用新的 Outlook web 上？</span><span class="sxs-lookup"><span data-stu-id="04e5b-124">How do you know if you're using the new Outlook on the web?</span></span> <span data-ttu-id="04e5b-125">請參閱下列的範例：</span><span class="sxs-lookup"><span data-stu-id="04e5b-125">See the following examples:</span></span>

![Outlook 與 Office 365](media/outlook-vs-outlook365.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="04e5b-127">常見問題集</span><span class="sxs-lookup"><span data-stu-id="04e5b-127">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="04e5b-128">查看準則沒有 Outlook.com 和網頁型 Outlook 使用新增 '？ ' 和 '透過' 屬性？</span><span class="sxs-lookup"><span data-stu-id="04e5b-128">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="04e5b-129">為 '？ ' 中的寄件者影像： Outlook.com 需要郵件通過 SPF 或 DKIM 驗證。</span><span class="sxs-lookup"><span data-stu-id="04e5b-129">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication.</span></span> <span data-ttu-id="04e5b-130">如需詳細資訊，請參閱[設定 spf 以協助防止詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)和[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的外寄電子郵件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="04e5b-130">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="04e5b-131">針對透過標記： Outlook.com 中自地址的網域不同網域的 DKIM 簽章或 SMTP MAIL FROM 中時，顯示在兩個欄位 （偏好的 DKIM 簽章） 的其中一個網域。</span><span class="sxs-lookup"><span data-stu-id="04e5b-131">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="can-i-override-these-properties-with-ip-allows-exchange-transport-rule-allows-or-safe-senders"></a><span data-ttu-id="04e5b-132">可以覆寫這些屬性與 IP 允許、 Exchange 傳輸規則可讓，或安全的寄件者？</span><span class="sxs-lookup"><span data-stu-id="04e5b-132">Can I override these properties with IP Allows, Exchange Transport Rule Allows, or safe senders?</span></span>

<span data-ttu-id="04e5b-133">您不能覆寫這些屬性。</span><span class="sxs-lookup"><span data-stu-id="04e5b-133">You can't override these properties.</span></span>

### <a name="how-do-i-remove-these-properties"></a><span data-ttu-id="04e5b-134">如何移除這些內容？</span><span class="sxs-lookup"><span data-stu-id="04e5b-134">How do I remove these properties?</span></span>

<span data-ttu-id="04e5b-135">為 '？ ' 中的寄件者影像： 為寄件者，您應該驗證與 SPF 或 DKIM 郵件。</span><span class="sxs-lookup"><span data-stu-id="04e5b-135">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="04e5b-136">針對透過標記： 為寄件者，您應該確定是在 DKIM 簽章的網域或 SMTP 郵件從相同，或是的在 [從地址的網域子網域。</span><span class="sxs-lookup"><span data-stu-id="04e5b-136">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="04e5b-137">Outlook.com 和 Outlook 網頁顯示執行此動作不會通過驗證每個郵件嗎？</span><span class="sxs-lookup"><span data-stu-id="04e5b-137">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="04e5b-138">不是一定。</span><span class="sxs-lookup"><span data-stu-id="04e5b-138">Not necessarily.</span></span> <span data-ttu-id="04e5b-139">Outlook.com 和網頁型 Outlook 可能已驗證寄件者的郵件內的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="04e5b-139">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="04e5b-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="04e5b-140">Related topics</span></span>

[<span data-ttu-id="04e5b-141">協助保護您的 Outlook.com 電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="04e5b-141">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="04e5b-142">處理濫用、 網路釣魚，或在 Outlook.com 中詐騙</span><span class="sxs-lookup"><span data-stu-id="04e5b-142">Deal with abuse, phishing, or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="04e5b-143">篩選垃圾電子郵件和網頁型 Outlook 中的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="04e5b-143">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
