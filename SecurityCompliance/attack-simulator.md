---
title: Office 365 中的攻擊模擬器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: 身為 Office 365 全域管理員，您可以使用的攻擊模擬器在組織中執行真實的攻擊案例。 這可協助您找出並之前真實的攻擊拜訪人次貴公司，找出受到使用者。
ms.openlocfilehash: a39259cdcc47e2c881b3977aa570b1f221f0b2bd
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077619"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="dd0d7-104">Office 365 中的攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="dd0d7-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="dd0d7-105">**摘要**如果您是 Office 365 全域系統管理員，而且您的組織有[Office 365 威脅調查及回應功能](office-365-ti.md)，您可以在組織中執行真實的攻擊案例使用攻擊模擬器。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-105">**Summary** If you are an Office 365 global administrator and your organization has [Office 365 Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="dd0d7-106">這可協助您找出並尋找容易遭受使用者之前真實的攻擊影響底部線條。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="dd0d7-107">閱讀本篇文章以了解更多。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-107">Read this article to learn more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd0d7-108">Office 365 進階威脅防護和威脅調查及回應 （以前稱為威脅情報） 是現在的一部分 Office 365 進階威脅防護計劃 2，與其他威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-108">Office 365 Advanced Threat Protection and Threat Investigation and Response (formerly known as Threat Intelligence) are now part of Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities.</span></span> <span data-ttu-id="dd0d7-109">若要深入了解，請參閱[Office 365 進階威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)和[Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-109">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="dd0d7-110">攻擊</span><span class="sxs-lookup"><span data-stu-id="dd0d7-110">The Attacks</span></span>

<span data-ttu-id="dd0d7-111">目前可用的三種類型的攻擊模擬如下：</span><span class="sxs-lookup"><span data-stu-id="dd0d7-111">Three kinds of attack simulations are currently available:</span></span>
  
- [<span data-ttu-id="dd0d7-112">顯示名稱矛網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="dd0d7-112">Display name spear-phishing attack</span></span>](#display-name-spear-phishing-attack)
- [<span data-ttu-id="dd0d7-113">密碼噴灑攻擊</span><span class="sxs-lookup"><span data-stu-id="dd0d7-113">Password-spray attack</span></span>](#password-spray-attack)
- [<span data-ttu-id="dd0d7-114">暴力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="dd0d7-114">Brute-force password attack</span></span>](#brute-force-password-attack)
    
<span data-ttu-id="dd0d7-115">已成功啟動攻擊，您可以使用多重要素驗證您用來執行模擬的攻擊的帳戶。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-115">For an attack to be successfully launched, you use multi-factor authentication on the account you are using to run simulated attacks.</span></span> <span data-ttu-id="dd0d7-116">此外，您必須是 Office 365 全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-116">In addition, you must be an Office 365 global administrator.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dd0d7-117">條件式存取的支援即將推出。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-117">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="dd0d7-118">若要存取安全性的攻擊模擬器&amp;合規性中心，選擇 [**威脅管理** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-118">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="dd0d7-119">開始之前...]</span><span class="sxs-lookup"><span data-stu-id="dd0d7-119">Before you begin...</span></span>

<span data-ttu-id="dd0d7-120">請確定您和您的組織符合的攻擊模擬器需求如下：</span><span class="sxs-lookup"><span data-stu-id="dd0d7-120">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
      
- <span data-ttu-id="dd0d7-121">**貴組織的電子郵件會託管於 Exchange Online**。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-121">**Your organization's email is hosted in Exchange Online**.</span></span> <span data-ttu-id="dd0d7-122">（攻擊模擬器不適用於內部部署電子郵件伺服器。）</span><span class="sxs-lookup"><span data-stu-id="dd0d7-122">(Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="dd0d7-123">**您是 Office 365 全域系統管理員**</span><span class="sxs-lookup"><span data-stu-id="dd0d7-123">**You are an Office 365 global administrator**</span></span>
    
- <span data-ttu-id="dd0d7-124">**[多重要素驗證](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)(MFA) 已關閉，如在最低的 Office 365 全域系統管理員帳戶**。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-124">**[Multi-factor authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide) (MFA) is turned on, for at least the Office 365 global administrator account**.</span></span> <span data-ttu-id="dd0d7-125">（理想狀況下，MFA 已為您組織中的所有使用者。）</span><span class="sxs-lookup"><span data-stu-id="dd0d7-125">(Ideally, MFA is turned on for all users in your organization.)</span></span>
 
- <span data-ttu-id="dd0d7-126">**您的組織有[Office 365 進階威脅防護計劃 2](office-365-ti.md)**，與安全性可見的攻擊模擬器&amp;合規性中心 (前往**威脅管理** \> **攻擊模擬器**)</span><span class="sxs-lookup"><span data-stu-id="dd0d7-126">**Your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md)**, with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span><br/><span data-ttu-id="dd0d7-127">![威脅管理-攻擊模擬器](media/ThreatMgmt-AttackSimulator.png)</span><span class="sxs-lookup"><span data-stu-id="dd0d7-127">![Threat management - Attack Simulator](media/ThreatMgmt-AttackSimulator.png)</span></span>

    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="dd0d7-128">顯示名稱矛網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="dd0d7-128">Display name spear-phishing attack</span></span>

<span data-ttu-id="dd0d7-129">網路釣魚是通稱歸類為社交樣式攻擊的攻擊廣泛套件。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-129">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="dd0d7-130">此類攻擊著重於矛網路釣魚，針對特定群組的個人或組織在多目標攻擊。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-130">This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="dd0d7-131">一般而言，自訂的攻擊與某些偵察執行，並使用會產生收件者，例如看起來像來自組織內的高階主管的電子郵件訊息中的信任的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-131">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="dd0d7-132">此類攻擊著重於給您，讓您管理誰會顯示訊息，有來自藉由變更顯示名稱和來源地址。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-132">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address.</span></span> <span data-ttu-id="dd0d7-133">矛網路釣魚攻擊成功時，cybercriminals 存取使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-133">When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="dd0d7-134">若要模擬矛網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="dd0d7-134">To simulate a spear-phishing attack</span></span>

![撰寫電子郵件內文](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="dd0d7-136">您可以製作豐富的 HTML 編輯器，直接在**電子郵件內文**欄位本身或與 HTML 來源搭配使用。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-136">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>
  
1. <span data-ttu-id="dd0d7-137">在[安全性&amp;合規性中心](https://protection.office.com)，選擇 [**威脅管理** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-137">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="dd0d7-138">指定攻擊的有意義的活動名稱，或者選取範本。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-138">Specify a meaningful campaign name for the attack or select a template.</span></span> <br/>![網路釣魚起始頁面](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="dd0d7-140">指定目標收件者。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-140">Specify the target recipients.</span></span> <span data-ttu-id="dd0d7-141">這可以是個人或組織中的群組。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-141">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="dd0d7-142">每個目標收件者必須擁有 Exchange Online 信箱攻擊的順序才會成功。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-142">Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span> <br/>![收件者的選取範圍](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="dd0d7-144">設定網路釣魚電子郵件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-144">Configure the Phishing email details.</span></span> <br/>![設定電子郵件的詳細資訊](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/><span data-ttu-id="dd0d7-146">HTML 格式可以為複雜或基本與您的行銷活動需求。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-146">The HTML formatting can be as complex or basic as your campaign needs.</span></span> <span data-ttu-id="dd0d7-147">為電子郵件格式是 HTML，您可以插入影像和以增強 believability 的文字。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-147">As the email format is HTML, you can insert images and text to enhance believability.</span></span> <span data-ttu-id="dd0d7-148">您可以在所收到的訊息中接收電子郵件用戶端外觀的控制。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-148">You have control on what the received message will look like in the receiving email client.</span></span>
    
5. <span data-ttu-id="dd0d7-149">指定文字**從 （名稱）** ] 欄位。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-149">Specify text for the **From (Name)** field.</span></span> <span data-ttu-id="dd0d7-150">這是顯示在接收的電子郵件用戶端中的**顯示名稱**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-150">This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
6. <span data-ttu-id="dd0d7-151">指定的文字或 [**從**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-151">Specify text or the **From** field.</span></span> <span data-ttu-id="dd0d7-152">這是顯示為接收電子郵件用戶端的寄件者的電子郵件地址] 欄位。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-152">This is the field that shows as the email address of the sender in the receiving email client.</span></span> <br/><span data-ttu-id="dd0d7-153">您可以在組織內輸入現有的電子郵件命名空間 （這樣會使實際解決接收用戶端，促進非常高信任模型中的電子郵件地址），或您可以輸入的外部電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-153">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address.</span></span> <span data-ttu-id="dd0d7-154">您指定並沒有實際存在，電子郵件地址，但它並需要下列的有效的 SMTP 位址，例如 user@domainname.extension 格式。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-154">The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
7. <span data-ttu-id="dd0d7-155">使用下拉式清單選取器，請選取 [反映您必須在您攻擊內的內容類型的網路釣魚登入伺服器 URL。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-155">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack.</span></span> <span data-ttu-id="dd0d7-156">多個已設佈景主題的 Url 被提供給您從中選擇，例如文件傳遞、 技術、 薪資等。這實際上是目標的使用者上當系統要您按一下 [URL。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-156">Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
8. <span data-ttu-id="dd0d7-157">指定自訂的登陸頁面 URL。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-157">Specify a custom landing page URL.</span></span> <span data-ttu-id="dd0d7-158">使用這將使用者重新導向至您指定的攻擊成功結尾的 URL。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-158">Using this will redirect users to a URL you specify at the end of a successful attack.</span></span> <span data-ttu-id="dd0d7-159">如果您有內部認知訓練，例如，您可以指定，這裡。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-159">If you have internal awareness training, for example, you can specify that here.</span></span>
    
9. <span data-ttu-id="dd0d7-160">指定文字的 [**主旨**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-160">Specify text for the **Subject** field.</span></span> <span data-ttu-id="dd0d7-161">這是顯示為中接收電子郵件用戶端的**主體名稱**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-161">This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
10. <span data-ttu-id="dd0d7-162">撰寫目標會收到**電子郵件內文**。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-162">Compose the **Email body** that the target will receive.</span></span> <br/><span data-ttu-id="dd0d7-163">`${username}`電子郵件本文中插入的目標名稱。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-163">`${username}` inserts the targets name into the Email body.</span></span> <br/><span data-ttu-id="dd0d7-164">`${loginserverurl}`會插入我們想要目標使用者按一下的 URL</span><span class="sxs-lookup"><span data-stu-id="dd0d7-164">`${loginserverurl}` inserts the URL we want target users to click</span></span> 
    
11. <span data-ttu-id="dd0d7-165">選擇 [**下一步]** ，然後**完成]** 來啟動攻擊。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-165">Choose **Next,** then **Finish** to launch the attack.</span></span> <span data-ttu-id="dd0d7-166">矛網路釣魚電子郵件會傳遞至您目標收件者的信箱。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-166">The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="dd0d7-167">密碼噴灑攻擊</span><span class="sxs-lookup"><span data-stu-id="dd0d7-167">Password-spray attack</span></span>

<span data-ttu-id="dd0d7-168">壞動作項目已成功取得從租用戶的有效使用者的清單之後，通常會使用組織的密碼噴灑攻擊。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-168">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant.</span></span> <span data-ttu-id="dd0d7-169">壞動作項目所知的人員使用常見密碼。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-169">The bad actor knows about common passwords that people use.</span></span> <span data-ttu-id="dd0d7-170">此為廣泛使用的攻擊，來執行，且更難偵測比暴力方法便宜攻擊。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-170">This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="dd0d7-171">此類攻擊著重於讓您指定要對使用者的大型目標基底常見的密碼。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-171">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="dd0d7-172">若要模擬密碼噴灑攻擊</span><span class="sxs-lookup"><span data-stu-id="dd0d7-172">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="dd0d7-173">在[安全性&amp;合規性中心](https://protection.office.com)，選擇 [**威脅管理** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-173">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="dd0d7-174">指定攻擊的有意義的活動名稱。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-174">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="dd0d7-175">指定目標收件者。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-175">Specify the target recipients.</span></span> <span data-ttu-id="dd0d7-176">這可以是個人或組織中的群組。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-176">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="dd0d7-177">目標收件者必須擁有 Exchange Online 信箱攻擊的順序才會成功。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-177">A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="dd0d7-178">指定要用於攻擊的密碼。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-178">Specify a password to use for the attack.</span></span> <span data-ttu-id="dd0d7-179">例如，您可以嘗試的一個常見、 相關密碼是`Fall2017`。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-179">For example, one common, relevant password you could try is `Fall2017`.</span></span> <span data-ttu-id="dd0d7-180">另一個可能是`Spring2018`，或`Password1`。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-180">Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="dd0d7-181">選擇 [**完成**] 以啟動攻擊。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-181">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="dd0d7-182">暴力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="dd0d7-182">Brute-force password attack</span></span>

<span data-ttu-id="dd0d7-183">壞動作項目已成功取得從租用戶的關鍵使用者的清單之後，通常會使用組織暴力密碼攻擊。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-183">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant.</span></span> <span data-ttu-id="dd0d7-184">此類攻擊著重在嘗試一組單一使用者的帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-184">This attack focuses on trying a set of passwords on a single user's account.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="dd0d7-185">若要模擬暴力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="dd0d7-185">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="dd0d7-186">在[安全性&amp;合規性中心](https://protection.office.com)，選擇 [**威脅管理** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-186">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="dd0d7-187">指定攻擊的有意義的活動名稱。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-187">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="dd0d7-188">指定目標收件者。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-188">Specify the target recipient.</span></span> <span data-ttu-id="dd0d7-189">目標收件者必須擁有 Exchange Online 信箱攻擊的順序才會成功。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-189">A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="dd0d7-190">指定一組用於攻擊的密碼。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-190">Specify a set of passwords to use for the attack.</span></span> <span data-ttu-id="dd0d7-191">若要這麼做，您可以使用文字檔 (.txt) 的清單中的密碼。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-191">To do this, you can use a text (.txt) file for your list of passwords.</span></span> <span data-ttu-id="dd0d7-192">將文字檔不可超過 10 MB 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-192">The text file cannot exceed 10 MB in file size.</span></span> <span data-ttu-id="dd0d7-193">使用一個密碼每一行，並確定要包含在清單中的最後一個密碼之後硬式傳回。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-193">Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>
    
5. <span data-ttu-id="dd0d7-194">選擇 [**完成**] 以啟動攻擊。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-194">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="dd0d7-195">攻擊模擬器中的新功能</span><span class="sxs-lookup"><span data-stu-id="dd0d7-195">New features in Attack Simulator</span></span>

<span data-ttu-id="dd0d7-196">新功能會被新增至攻擊模擬器。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-196">New features are being added to Attack Simulator.</span></span> <span data-ttu-id="dd0d7-197">這些包括：</span><span class="sxs-lookup"><span data-stu-id="dd0d7-197">These include:</span></span>

- <span data-ttu-id="dd0d7-198">**進階報告功能**。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-198">**Advanced reporting capabilities**.</span></span> <span data-ttu-id="dd0d7-199">您將能夠看到最快 （或速度最慢） 時間按一下中的郵件，並更多連結開啟攻擊模擬電子郵件的最快 （或速度最慢） 時間等資料。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-199">You'll be able to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more.</span></span>

- <span data-ttu-id="dd0d7-200">**電子郵件範本編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-200">**Email template editor**.</span></span> <span data-ttu-id="dd0d7-201">您可以建立您可用於未來的攻擊模擬的自訂、 可重複使用的電子郵件範本。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-201">You can create a custom, reusable email template that you can use for future attack simulations.</span></span>

<span data-ttu-id="dd0d7-202">請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)請參閱什麼是在開發中、 什麼推行和功能已啟動。</span><span class="sxs-lookup"><span data-stu-id="dd0d7-202">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd0d7-203">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dd0d7-203">See also</span></span>

[<span data-ttu-id="dd0d7-204">Office 365 進階的威脅防護服務 Desription</span><span class="sxs-lookup"><span data-stu-id="dd0d7-204">Office 365 Advanced Threat Protection Service Desription</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[<span data-ttu-id="dd0d7-205">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="dd0d7-205">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)



