---
title: 未驗證的寄件者
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 若要防止網路釣魚郵件送達您的信箱，Outlook.com 和網頁型 Outlook 確認寄件者是誰他們說他們且可疑的郵件標示為垃圾郵件。
ms.openlocfilehash: ad94a2953b6fd53612b2fc15038a7157e97f3b39
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157985"
---
# <a name="unverified-sender"></a><span data-ttu-id="56c07-103">未驗證的寄件者</span><span class="sxs-lookup"><span data-stu-id="56c07-103">Unverified Sender</span></span>

<span data-ttu-id="56c07-104">若要防止網路釣魚郵件送達您的信箱，Outlook.com 和網頁型 Outlook 確認寄件者是誰他們說他們且可疑的郵件標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="56c07-104">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56c07-105">當郵件標示為網路釣魚詐騙、 Outlook.com 和 Outlook 網頁顯示一則警告] 頁面頂端，但仍然可以開啟任何郵件中的連結。</span><span class="sxs-lookup"><span data-stu-id="56c07-105">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="56c07-106">如何識別我的收件匣中的可疑的郵件？</span><span class="sxs-lookup"><span data-stu-id="56c07-106">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="56c07-107">Outlook.com 和網頁型 Outlook 顯示指標，當郵件的寄件者也無法識別或其身分識別為不同於從地址中看到的內容。</span><span class="sxs-lookup"><span data-stu-id="56c07-107">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="56c07-108">如何管理哪些郵件接收未驗證的寄件者處理方式</span><span class="sxs-lookup"><span data-stu-id="56c07-108">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="56c07-109">如果您是 Office 365 客戶可以管理安全性 & 合規性中心透過這項功能。</span><span class="sxs-lookup"><span data-stu-id="56c07-109">If you are an Office 365 customer you can manage this feature through the Security & Compliance Center.</span></span> 

- <span data-ttu-id="56c07-110">在 Office 365 安全性 & 合規性中心，租用戶系統管理員可以開啟功能，開啟或關閉，透過反 Phish 原則] 底下的反詐騙保護。</span><span class="sxs-lookup"><span data-stu-id="56c07-110">In the Office 365 Security & Compliance Center, tenant admins can turn the feature on, or off, through the Anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="56c07-111">此外，它可以透過 ' 組 AntiPhishPolicy' 指令程式管理。</span><span class="sxs-lookup"><span data-stu-id="56c07-111">Additionally, it can be managed through the ‘Set-AntiPhishPolicy’ cmdlet.</span></span> <span data-ttu-id="56c07-112">如需詳細資訊，請參閱 < 在 Office 365 及集合 AntiPhishPolicy 反網路釣魚保護。</span><span class="sxs-lookup"><span data-stu-id="56c07-112">For more details, see Anti-phishing protection in Office 365 and Set-AntiPhishPolicy.</span></span>

    ![編輯的圖形介面中的未驗證寄件者。](media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="56c07-114">如果系統管理員已識別為誤判，而且寄件者應該不會收到未驗證的寄件者處理方式可採取下列動作，以將寄件者新增至詐騙智慧詐騙的其中一個允許清單：</span><span class="sxs-lookup"><span data-stu-id="56c07-114">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment they can take one of the following actions to add the sender to the Spoof Intelligence spoof allow list:</span></span>
        
    - <span data-ttu-id="56c07-115">加入網域組經由詐騙智慧深入解析。</span><span class="sxs-lookup"><span data-stu-id="56c07-115">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="56c07-116">如需詳細資訊，請參閱逐步解說： 詐騙智慧深入解析</span><span class="sxs-lookup"><span data-stu-id="56c07-116">For more details, see Walkthrough: spoof intelligence insight</span></span>
                
    - <span data-ttu-id="56c07-117">新增透過 PhishFilterPolicy 指令程式的網域組。</span><span class="sxs-lookup"><span data-stu-id="56c07-117">Add the domain pair through the PhishFilterPolicy cmdlet.</span></span> <span data-ttu-id="56c07-118">如需詳細資訊，請參閱 Office 365 中的 Set-phishfilterpolicy 和反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="56c07-118">For more details, see Set-PhishFilterPolicy and Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="56c07-119">此外，我們不會套用未驗證寄件者處理方式如果已將其傳遞至收件匣透過系統允許清單，包括電子郵件傳輸規則 (Etr)、 安全網域清單 （反垃圾郵件原則）、 安全的寄件者清單，或使用者已設定為 「 安全寄件者 」 這個使用者在其收件匣。</span><span class="sxs-lookup"><span data-stu-id="56c07-119">Additionally, we do not apply the unverified sender treatment if it was delivered to the inbox via an admin allow list, including Email Transport Rules (ETRs), Safe Domain List (Anti-Spam Policy), Safe Sender List or a user has set this user as a “Safe Sender” in their inbox.</span></span>

### <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="56c07-120">您會看到 '？ ' 中的寄件者影像</span><span class="sxs-lookup"><span data-stu-id="56c07-120">You see a '?' in the sender image</span></span>

<span data-ttu-id="56c07-121">當 Outlook.com 和網頁型 Outlook 無法驗證使用電子郵件驗證技術的寄件者的身分識別時，他們會顯示 '？ ' 中的寄件者相片。</span><span class="sxs-lookup"><span data-stu-id="56c07-121">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span> 

![郵件未通過驗證](media/message-did-not-pass-verification.jpg)

<span data-ttu-id="56c07-123">若要驗證失敗不是每個訊息是惡意。</span><span class="sxs-lookup"><span data-stu-id="56c07-123">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="56c07-124">不過，您應該謹慎互動與未驗證如果您不能辨識寄件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="56c07-124">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="56c07-125">或者，如果您辨識通常沒有寄件者 '？ ' 寄件者的影像，但您突然開始看到它，可能會登寄件者詐騙。</span><span class="sxs-lookup"><span data-stu-id="56c07-125">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

### <a name="the-senders-address-is-different-than-what-appears-in-the-from-address"></a><span data-ttu-id="56c07-126">寄件者地址是不同的 From 地址中顯示的內容</span><span class="sxs-lookup"><span data-stu-id="56c07-126">The sender's address is different than what appears in the From address</span></span>

<span data-ttu-id="56c07-127">通常，您看到訊息中的電子郵件地址是不同於從地址中看到的內容。</span><span class="sxs-lookup"><span data-stu-id="56c07-127">Frequently, the email address you see in a message is different than what you see in the From address.</span></span> <span data-ttu-id="56c07-128">有時網路釣客會嘗試誘騙寄件者是其他人以外人員它們確實是的想法。</span><span class="sxs-lookup"><span data-stu-id="56c07-128">Sometimes phishers try to trick you into thinking that the sender is someone other than who they really are.</span></span>

<span data-ttu-id="56c07-129">當 Outlook.com 和 outlook 網頁版偵測寄件者的實際地址與寄地址的地址之間的差異時，它們會顯示實際寄件者，並使用透過標記，這會加上底線。</span><span class="sxs-lookup"><span data-stu-id="56c07-129">When Outlook.com and Outlook on the web detect a difference between the sender's actual address and the address on the From address, they show the actual sender using the via tag, which will be underlined.</span></span>

![未驗證的寄件者的替代文字](media/unverified-sender-feature1.png)

<span data-ttu-id="56c07-131">在這個範例中，在傳送網域`suspicious.com`通過驗證，但寄件者放`unknown@contoso.com`From 地址。</span><span class="sxs-lookup"><span data-stu-id="56c07-131">In this example, the sending domain `suspicious.com` is authenticated, but the sender put `unknown@contoso.com` in the From address.</span></span>

<span data-ttu-id="56c07-132">不是每個郵件透過標記為可疑。</span><span class="sxs-lookup"><span data-stu-id="56c07-132">Not every message with a via tag is suspicious.</span></span> <span data-ttu-id="56c07-133">不過，如果您不能辨識郵件透過標記，您應該謹慎與其互動。</span><span class="sxs-lookup"><span data-stu-id="56c07-133">However, if you don't recognize a message with a via tag, you should be cautious about interacting with it.</span></span>

<span data-ttu-id="56c07-134">在 Outlook.com 和新網頁型 Outlook 中，您可以將游標停留寄件者的名稱或郵件清單中，查看他們的電子郵件地址，而不需要開啟該郵件的地址。</span><span class="sxs-lookup"><span data-stu-id="56c07-134">In Outlook.com and the new Outlook on the web, you can hover your cursor over a sender's name or address in the message list to see their email address, without needing to open the message.</span></span>

![開始使用 OneDrive](media/get-started-with-onedrive-message.png)

<span data-ttu-id="56c07-136">如何知道是否您使用新的 Outlook web 上？</span><span class="sxs-lookup"><span data-stu-id="56c07-136">How do you know if you're using the new Outlook on the web?</span></span> <span data-ttu-id="56c07-137">請參閱下列的範例：</span><span class="sxs-lookup"><span data-stu-id="56c07-137">See the following examples:</span></span>

![Outlook 與 Office 365](media/outlook-vs-outlook365.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="56c07-139">常見問題集</span><span class="sxs-lookup"><span data-stu-id="56c07-139">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="56c07-140">查看準則沒有 Outlook.com 和網頁型 Outlook 使用新增 '？ ' 和 '透過' 屬性？</span><span class="sxs-lookup"><span data-stu-id="56c07-140">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="56c07-141">為 '？ ' 中的寄件者影像： Outlook.com 需要郵件通過 SPF 或 DKIM 驗證。</span><span class="sxs-lookup"><span data-stu-id="56c07-141">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication.</span></span> <span data-ttu-id="56c07-142">如需詳細資訊，請參閱[設定 spf 以協助防止詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)和[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的外寄電子郵件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="56c07-142">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="56c07-143">針對透過標記： Outlook.com 中自地址的網域不同網域的 DKIM 簽章或 SMTP MAIL FROM 中時，顯示在兩個欄位 （偏好的 DKIM 簽章） 的其中一個網域。</span><span class="sxs-lookup"><span data-stu-id="56c07-143">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="can-i-override-these-properties-with-ip-allows-exchange-transport-rule-allows-or-safe-senders"></a><span data-ttu-id="56c07-144">可以覆寫這些屬性與 IP 允許、 Exchange 傳輸規則可讓，或安全的寄件者？</span><span class="sxs-lookup"><span data-stu-id="56c07-144">Can I override these properties with IP Allows, Exchange Transport Rule Allows, or safe senders?</span></span>

<span data-ttu-id="56c07-145">您不能覆寫這些屬性。</span><span class="sxs-lookup"><span data-stu-id="56c07-145">You can't override these properties.</span></span>

### <a name="how-do-i-remove-these-properties"></a><span data-ttu-id="56c07-146">如何移除這些內容？</span><span class="sxs-lookup"><span data-stu-id="56c07-146">How do I remove these properties?</span></span>

<span data-ttu-id="56c07-147">為 '？ ' 中的寄件者影像： 為寄件者，您應該驗證與 SPF 或 DKIM 郵件。</span><span class="sxs-lookup"><span data-stu-id="56c07-147">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="56c07-148">針對透過標記： 為寄件者，您應該確定是在 DKIM 簽章的網域或 SMTP 郵件從相同，或是的在 [從地址的網域子網域。</span><span class="sxs-lookup"><span data-stu-id="56c07-148">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="56c07-149">Outlook.com 和 Outlook 網頁顯示執行此動作不會通過驗證每個郵件嗎？</span><span class="sxs-lookup"><span data-stu-id="56c07-149">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="56c07-150">不是一定。</span><span class="sxs-lookup"><span data-stu-id="56c07-150">Not necessarily.</span></span> <span data-ttu-id="56c07-151">Outlook.com 和網頁型 Outlook 可能已驗證寄件者的郵件內的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="56c07-151">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="56c07-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="56c07-152">Related topics</span></span>

[<span data-ttu-id="56c07-153">協助保護您的 Outlook.com 電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="56c07-153">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="56c07-154">處理濫用、 網路釣魚，或在 Outlook.com 中詐騙</span><span class="sxs-lookup"><span data-stu-id="56c07-154">Deal with abuse, phishing, or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="56c07-155">篩選垃圾電子郵件和網頁型 Outlook 中的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="56c07-155">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
