---
title: Office 365 中的攻擊模擬器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/13/2019
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
description: 作為 Office 365 全域系統管理員, 您可以使用攻擊模擬器, 在您的組織中執行實際的攻擊案例。 這可協助您找出並尋找有漏洞的使用者, 然後才會真正受到攻擊。
ms.openlocfilehash: 938a8f944fee22fb16b87923d7608b3bfcfee0fb
ms.sourcegitcommit: 62447503300376aa95dd05fb5276f93a9f6a20b6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2019
ms.locfileid: "34927566"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="7ffe5-104">Office 365 中的攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="7ffe5-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="7ffe5-105">**摘要**如果您是 Office 365 全域系統管理員或安全性系統管理員, 而且您的組織有[office 365 威脅調查和回應功能](office-365-ti.md), 您可以使用攻擊模擬器, 在您的組織中執行實際的攻擊案例。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-105">**Summary** If you are an Office 365 global administrator or a security administrator and your organization has [Office 365 Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="7ffe5-106">這可協助您找出並尋找有漏洞的使用者, 而真正的攻擊會影響您的底部線路。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="7ffe5-107">若要深入瞭解, 請閱讀本文。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-107">Read this article to learn more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ffe5-108">Office 365 Advanced 威脅防護和威脅調查與回應 (先前稱為威脅情報) 是 Office 365 高級威脅防護計畫2的一部分, 以及額外的威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-108">Office 365 Advanced Threat Protection and Threat Investigation and Response (formerly known as Threat Intelligence) are part of Office 365 Advanced Threat Protection Plan 2, along with additional threat protection capabilities.</span></span> <span data-ttu-id="7ffe5-109">若要深入瞭解, 請參閱[office 365 高級威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection), 以及[Office 365 高級威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-109">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="7ffe5-110">攻擊</span><span class="sxs-lookup"><span data-stu-id="7ffe5-110">The Attacks</span></span>

<span data-ttu-id="7ffe5-111">目前有三種攻擊模擬類型:</span><span class="sxs-lookup"><span data-stu-id="7ffe5-111">Three kinds of attack simulations are currently available:</span></span>
  
- [<span data-ttu-id="7ffe5-112">顯示名稱 spear-網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="7ffe5-112">Display name spear-phishing attack</span></span>](#display-name-spear-phishing-attack)
- [<span data-ttu-id="7ffe5-113">密碼噴塗攻擊</span><span class="sxs-lookup"><span data-stu-id="7ffe5-113">Password-spray attack</span></span>](#password-spray-attack)
- [<span data-ttu-id="7ffe5-114">強力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="7ffe5-114">Brute-force password attack</span></span>](#brute-force-password-attack)
    
<span data-ttu-id="7ffe5-115">若要成功啟動攻擊, 請確定用來執行模擬攻擊的帳戶是使用多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-115">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="7ffe5-116">此外, 您必須是 Office 365 全域系統管理員或安全性系統管理員。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-116">In addition, you must be an Office 365 global administrator or a security administrator.</span></span> <span data-ttu-id="7ffe5-117">(若要深入瞭解角色和許可權, 請參閱[Office 365 安全性 & 規範中心中的許可權](permissions-in-the-security-and-compliance-center.md)。)</span><span class="sxs-lookup"><span data-stu-id="7ffe5-117">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>
    
<span data-ttu-id="7ffe5-118">若要存取攻擊模擬器, 請在&amp;安全性與合規性中心中選擇 [**威脅管理** \> **攻擊模擬器**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-118">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="7ffe5-119">開始之前 .。。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-119">Before you begin...</span></span>

<span data-ttu-id="7ffe5-120">請確定您和您的組織符合下列攻擊模擬器的需求:</span><span class="sxs-lookup"><span data-stu-id="7ffe5-120">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
      
- <span data-ttu-id="7ffe5-121">**貴組織的電子郵件裝載于 Exchange Online 中**。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-121">**Your organization's email is hosted in Exchange Online**.</span></span> <span data-ttu-id="7ffe5-122">(內部部署電子郵件伺服器無法使用攻擊模擬器)。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-122">(Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="7ffe5-123">**您是 Office 365 全域系統管理員或安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="7ffe5-123">**You are an Office 365 global administrator or security administrator**</span></span>
    
- <span data-ttu-id="7ffe5-124">**已開啟[多重要素驗證/條件式存取](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide), 至少適用于 Office 365 全域系統管理員帳戶和安全性系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-124">**[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide) is turned on, for at least the Office 365 global administrator account and security administrators**.</span></span> <span data-ttu-id="7ffe5-125">(理想情況下, 您組織中的所有使用者都已開啟多重要素驗證/條件式存取)。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-125">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>
 
- <span data-ttu-id="7ffe5-126">**您的組織有[Office 365 Advanced 威脅防護方案 2](office-365-ti.md)**, 在安全性&amp;與合規性中心中會顯示攻擊模擬器 (移至**威脅管理** \> **攻擊模擬器**)</span><span class="sxs-lookup"><span data-stu-id="7ffe5-126">**Your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md)**, with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span><br/><span data-ttu-id="7ffe5-127">![威脅管理-攻擊模擬器](media/ThreatMgmt-AttackSimulator.png)</span><span class="sxs-lookup"><span data-stu-id="7ffe5-127">![Threat management - Attack Simulator](media/ThreatMgmt-AttackSimulator.png)</span></span>

## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="7ffe5-128">顯示名稱 spear-網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="7ffe5-128">Display name spear-phishing attack</span></span>

<span data-ttu-id="7ffe5-129">網路釣魚是一種廣泛的攻擊 classed, 作為社交工程風格的攻擊。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-129">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="7ffe5-130">此攻擊的重點是 spear 網路釣魚, 是一種更具針對性的攻擊, 是針對特定的個人或組織群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-130">This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="7ffe5-131">一般來說, 已執行某些偵測的自訂攻擊, 並使用將在收件者中產生信任的顯示名稱, 例如看起來像是來自組織內執行者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-131">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="7ffe5-132">此攻擊的重點是讓您可以透過變更顯示名稱和來源位址, 來操縱訊息似乎來自何處。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-132">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address.</span></span> <span data-ttu-id="7ffe5-133">當 spear 網路釣魚攻擊成功時, 網路罪犯就能存取使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-133">When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="7ffe5-134">模擬 spear 網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="7ffe5-134">To simulate a spear-phishing attack</span></span>

![撰寫電子郵件本文](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="7ffe5-136">您可以直接在**電子郵件**內文欄位中手工製作 rich HTML 編輯器, 或使用 HTML 來源。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-136">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>
  
1. <span data-ttu-id="7ffe5-137">在[安全性&amp;與合規性中心](https://protection.office.com)中, 選擇 [**威脅管理** \> **攻擊模擬器**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-137">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="7ffe5-138">指定攻擊的有意義的活動名稱, 或選取範本。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-138">Specify a meaningful campaign name for the attack or select a template.</span></span> <br/>![[網路釣魚開始] 頁面](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="7ffe5-140">指定目標收件者。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-140">Specify the target recipients.</span></span> <span data-ttu-id="7ffe5-141">這可以是組織中的個人或群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-141">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="7ffe5-142">每個目標收件者都必須有 Exchange Online 信箱, 攻擊才會成功。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-142">Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span> <br/>![收件者選取](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="7ffe5-144">設定網路釣魚電子郵件詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-144">Configure the Phishing email details.</span></span> <br/>![設定電子郵件詳細資料](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/><span data-ttu-id="7ffe5-146">HTML 格式設定可以像是您的市場活動需求一樣複雜或基本。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-146">The HTML formatting can be as complex or basic as your campaign needs.</span></span> <span data-ttu-id="7ffe5-147">電子郵件格式為 HTML 時, 您可以插入影像和文字以增強 believability。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-147">As the email format is HTML, you can insert images and text to enhance believability.</span></span> <span data-ttu-id="7ffe5-148">您可以控制接收到的郵件在接收的電子郵件用戶端中的外觀。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-148">You have control on what the received message will look like in the receiving email client.</span></span>
    
5. <span data-ttu-id="7ffe5-149">指定 [**寄件者] (名稱)** 欄位的文字。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-149">Specify text for the **From (Name)** field.</span></span> <span data-ttu-id="7ffe5-150">這是在接收電子郵件客戶程式的**顯示名稱**中顯示的欄位。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-150">This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
6. <span data-ttu-id="7ffe5-151">指定文字或 [**寄件者**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-151">Specify text or the **From** field.</span></span> <span data-ttu-id="7ffe5-152">此欄位會顯示為接收電子郵件用戶端中寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-152">This is the field that shows as the email address of the sender in the receiving email client.</span></span> <br/><span data-ttu-id="7ffe5-153">您可以在組織內輸入現有的電子郵件命名空間 (這樣做會讓電子郵件地址在接收用戶端中實際解析, 採用非常高的信任模型), 也可以輸入外部電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-153">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address.</span></span> <span data-ttu-id="7ffe5-154">您指定的電子郵件地址不一定確實存在, 但是必須遵循有效的 SMTP 位址格式, 例如使用者 @ domainname。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-154">The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
7. <span data-ttu-id="7ffe5-155">使用下拉式選擇器, 選取一個網路釣魚登入伺服器 URL, 以反映您在攻擊中所擁有的內容類型。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-155">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack.</span></span> <span data-ttu-id="7ffe5-156">有幾個主題 Url 可供您選擇, 例如檔傳遞、技術、薪資等。這實際上就是要求目標使用者按一下的 URL。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-156">Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
8. <span data-ttu-id="7ffe5-157">指定自訂登陸頁面 URL。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-157">Specify a custom landing page URL.</span></span> <span data-ttu-id="7ffe5-158">使用這會將使用者重新導向至您在成功攻擊結束時指定的 URL。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-158">Using this will redirect users to a URL you specify at the end of a successful attack.</span></span> <span data-ttu-id="7ffe5-159">例如, 如果您有內部的認識訓練, 您可以在這裡指定。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-159">If you have internal awareness training, for example, you can specify that here.</span></span>
    
9. <span data-ttu-id="7ffe5-160">指定 [主旨] \*\*\*\* 欄位的文字。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-160">Specify text for the **Subject** field.</span></span> <span data-ttu-id="7ffe5-161">此欄位顯示為接收電子郵件客戶程式中的**主體名稱**。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-161">This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
10. <span data-ttu-id="7ffe5-162">撰寫目標將會接收的**電子郵件**內文。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-162">Compose the **Email body** that the target will receive.</span></span> <br/><span data-ttu-id="7ffe5-163">`${username}`將目標名稱插入電子郵件內文。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-163">`${username}` inserts the targets name into the Email body.</span></span> <br/><span data-ttu-id="7ffe5-164">`${loginserverurl}`插入想要讓目標使用者按一下的 URL</span><span class="sxs-lookup"><span data-stu-id="7ffe5-164">`${loginserverurl}` inserts the URL we want target users to click</span></span> 
    
11. <span data-ttu-id="7ffe5-165">選擇 [**下一步],** 然後按一下 **[完成]** 以啟動攻擊。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-165">Choose **Next,** then **Finish** to launch the attack.</span></span> <span data-ttu-id="7ffe5-166">Spear 網路釣魚電子郵件會傳遞至您的目標收件者的信箱。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-166">The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="7ffe5-167">密碼噴塗攻擊</span><span class="sxs-lookup"><span data-stu-id="7ffe5-167">Password-spray attack</span></span>

<span data-ttu-id="7ffe5-168">在不良參與者從租使用者成功取得有效使用者清單之後, 通常會使用組織的密碼噴塗攻擊。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-168">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant.</span></span> <span data-ttu-id="7ffe5-169">不良參與者知道人們所使用的一般密碼。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-169">The bad actor knows about common passwords that people use.</span></span> <span data-ttu-id="7ffe5-170">這是一種廣泛使用的攻擊, 因為這是執行的廉價攻擊, 而且難以偵測到蠻力方法。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-170">This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="7ffe5-171">這個攻擊的重點是讓您針對大型使用者的使用者指定一般密碼。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-171">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="7ffe5-172">模擬密碼噴塗攻擊</span><span class="sxs-lookup"><span data-stu-id="7ffe5-172">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="7ffe5-173">在[安全性&amp;與合規性中心](https://protection.office.com)中, 選擇 [**威脅管理** \> **攻擊模擬器**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-173">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="7ffe5-174">指定攻擊的有意義的活動名稱。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-174">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="7ffe5-175">指定目標收件者。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-175">Specify the target recipients.</span></span> <span data-ttu-id="7ffe5-176">這可以是組織中的個人或群組。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-176">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="7ffe5-177">目標收件者必須有 Exchange Online 信箱, 攻擊才會成功。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-177">A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="7ffe5-178">指定要用於攻擊的密碼。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-178">Specify a password to use for the attack.</span></span> <span data-ttu-id="7ffe5-179">例如, 您可以嘗試的一種常見的相關密碼`Fall2017`。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-179">For example, one common, relevant password you could try is `Fall2017`.</span></span> <span data-ttu-id="7ffe5-180">另一個可能`Spring2018`是或`Password1`。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-180">Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="7ffe5-181">選擇 **[完成]** 以啟動攻擊。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-181">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="7ffe5-182">強力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="7ffe5-182">Brute-force password attack</span></span>

<span data-ttu-id="7ffe5-183">在不良參與者從租使用者成功取得主要使用者清單之後, 通常會使用對組織進行強力密碼攻擊。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-183">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant.</span></span> <span data-ttu-id="7ffe5-184">此攻擊著重于嘗試單一使用者帳戶上的一組密碼。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-184">This attack focuses on trying a set of passwords on a single user's account.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="7ffe5-185">模擬蠻力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="7ffe5-185">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="7ffe5-186">在[安全性&amp;與合規性中心](https://protection.office.com)中, 選擇 [**威脅管理** \> **攻擊模擬器**]。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-186">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="7ffe5-187">指定攻擊的有意義的活動名稱。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-187">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="7ffe5-188">指定目標收件者。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-188">Specify the target recipient.</span></span> <span data-ttu-id="7ffe5-189">目標收件者必須有 Exchange Online 信箱, 攻擊才會成功。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-189">A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="7ffe5-190">指定要用於攻擊的一組密碼。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-190">Specify a set of passwords to use for the attack.</span></span> <span data-ttu-id="7ffe5-191">若要這麼做, 您可以使用文字檔 (.txt) 來做為您的密碼清單。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-191">To do this, you can use a text (.txt) file for your list of passwords.</span></span> <span data-ttu-id="7ffe5-192">檔案大小的文字檔不能超過 10 MB。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-192">The text file cannot exceed 10 MB in file size.</span></span> <span data-ttu-id="7ffe5-193">每行使用一個密碼, 並確定在清單中的最後一個密碼之後包含強制換行。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-193">Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>
    
5. <span data-ttu-id="7ffe5-194">選擇 **[完成]** 以啟動攻擊。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-194">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="7ffe5-195">攻擊模擬器中的新功能</span><span class="sxs-lookup"><span data-stu-id="7ffe5-195">New features in Attack Simulator</span></span>

<span data-ttu-id="7ffe5-196">最近新增功能已新增至攻擊模擬器。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-196">New features have recently been added to Attack Simulator.</span></span> <span data-ttu-id="7ffe5-197">這些包括：</span><span class="sxs-lookup"><span data-stu-id="7ffe5-197">These include:</span></span>

- <span data-ttu-id="7ffe5-198">**高級報告功能**。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-198">**Advanced reporting capabilities**.</span></span> <span data-ttu-id="7ffe5-199">查看資料 (如最快 (或最慢) 時間) 開啟攻擊模擬電子郵件訊息的功能、最快 (或最慢) 的時間, 以按一下郵件中的連結, 以及更多的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-199">The ability to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more visualizations.</span></span>

- <span data-ttu-id="7ffe5-200">**電子郵件範本編輯器**。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-200">**Email template editor**.</span></span> <span data-ttu-id="7ffe5-201">建立自訂且可重複使用的電子郵件範本的功能, 可用於未來的攻擊模擬。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-201">The ability to create a custom, reusable email template's that you can use for future attack simulations.</span></span>

- <span data-ttu-id="7ffe5-202">**CSV 收件**者匯入。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-202">**CSV Recipient Import**.</span></span> <span data-ttu-id="7ffe5-203">使用 CSV 檔案來匯入目標收件者清單, 而不是使用通訊錄選擇器的功能。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-203">The ability to use a CSV file to import your target recipient list instead of using the address book picker.</span></span>

<span data-ttu-id="7ffe5-204">**有更多新功能會在攻擊模擬器之後推出**。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-204">**More new features are coming soon to Attack Simulator**.</span></span> <span data-ttu-id="7ffe5-205">這些包括：</span><span class="sxs-lookup"><span data-stu-id="7ffe5-205">These include:</span></span>

- <span data-ttu-id="7ffe5-206">**附件負載網路釣魚模擬模擬**。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-206">**Attachment payload phishing simulation**.</span></span> <span data-ttu-id="7ffe5-207">使用附件做為網路釣魚模擬的負載, 以取代 URL 的功能。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-207">The ability to use an attachment as the payload for phishing simulation in place of a URL.</span></span>

<span data-ttu-id="7ffe5-208">請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap), 以查看正在開發的專案、正在進行的功能以及已啟動的功能。</span><span class="sxs-lookup"><span data-stu-id="7ffe5-208">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ffe5-209">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7ffe5-209">See also</span></span>

[<span data-ttu-id="7ffe5-210">Office 365 Advanced 威脅防護服務 Desription</span><span class="sxs-lookup"><span data-stu-id="7ffe5-210">Office 365 Advanced Threat Protection Service Desription</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[<span data-ttu-id="7ffe5-211">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="7ffe5-211">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)



