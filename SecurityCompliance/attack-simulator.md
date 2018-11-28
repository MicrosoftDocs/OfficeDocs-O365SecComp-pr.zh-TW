---
title: Office 365 中的攻擊模擬器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/09/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: 身為 Office 365 全域管理員，您可以使用攻擊模擬器您組織中執行真實感化的攻擊案例。這可協助您識別及之前實際攻擊拜訪人次業務找出遭到入侵的使用者。
ms.openlocfilehash: 9a7e1fd5327b4a764356df110c46ee7a9f496b53
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706437"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="b528e-104">Office 365 中的攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="b528e-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="b528e-p102">**摘要**如果您的組織具有[Office 365 威脅智慧](office-365-ti.md)Office 365 全域管理員，您可以使用攻擊模擬器您組織中執行真實感化的攻擊案例。這可協助您識別並尋找遭到入侵的使用者才能實際攻擊影響底部線條。請閱讀本篇文章以深入了解。</span><span class="sxs-lookup"><span data-stu-id="b528e-p102">**Summary** If you are an Office 365 global administrator and your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line. Read this article to learn more.</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="b528e-108">攻擊</span><span class="sxs-lookup"><span data-stu-id="b528e-108">The Attacks</span></span>

<span data-ttu-id="b528e-109">目前可用的三種攻擊模擬如下：</span><span class="sxs-lookup"><span data-stu-id="b528e-109">Three kinds of attack simulations are currently available:</span></span>
  
- [<span data-ttu-id="b528e-110">顯示名稱矛網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="b528e-110">Display name spear-phishing attack</span></span>](attack-simulator.md#spearphish)
    
- [<span data-ttu-id="b528e-111">密碼噴灑攻擊</span><span class="sxs-lookup"><span data-stu-id="b528e-111">Password-spray attack</span></span>](attack-simulator.md#passwordspray)
    
- [<span data-ttu-id="b528e-112">暴力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="b528e-112">Brute-force password attack</span></span>](attack-simulator.md#bruteforce)
    
<span data-ttu-id="b528e-p103">若要成功啟動攻擊，您使用多重要素驗證您用來執行模擬的攻擊的帳戶。此外，您必須是 Office 365 全域管理員。</span><span class="sxs-lookup"><span data-stu-id="b528e-p103">For an attack to be successfully launched, you use multi-factor authentication on the account you are using to run simulated attacks. In addition, you must be an Office 365 global administrator.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b528e-115">條件式存取的支援即將推出。</span><span class="sxs-lookup"><span data-stu-id="b528e-115">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="b528e-116">若要存取安全性的攻擊模擬器&amp;規範中心選擇**Threat management** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="b528e-116">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="b528e-117">開始之前...]</span><span class="sxs-lookup"><span data-stu-id="b528e-117">Before you begin...</span></span>

<span data-ttu-id="b528e-118">請確定您和您的組織符合攻擊模擬器的需求如下：</span><span class="sxs-lookup"><span data-stu-id="b528e-118">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
      
- <span data-ttu-id="b528e-p104">貴組織的電子郵件裝載於 Exchange Online。（攻擊模擬器不適用於內部部署電子郵件伺服器。）</span><span class="sxs-lookup"><span data-stu-id="b528e-p104">Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="b528e-121">您是 Office 365 全域管理員</span><span class="sxs-lookup"><span data-stu-id="b528e-121">You are an Office 365 global administrator</span></span>
    
- <span data-ttu-id="b528e-122">您的組織使用[的 Office 365 使用者的多重要素驗證](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="b528e-122">Your organization is using [Multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication&view=o365-worldwide)</span></span>
 
- <span data-ttu-id="b528e-123">您的組織具有[Office 365 威脅智慧](office-365-ti.md)與可見安全性攻擊模擬器&amp;規範中心 (移至 [ **Threat management** \> **攻擊模擬器**)</span><span class="sxs-lookup"><span data-stu-id="b528e-123">Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span><br/><span data-ttu-id="b528e-124">![Threat management-攻擊模擬器](media/ThreatMgmt-AttackSimulator.png)</span><span class="sxs-lookup"><span data-stu-id="b528e-124">![Threat management - Attack Simulator](media/ThreatMgmt-AttackSimulator.png)</span></span>

    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="b528e-125">顯示名稱矛網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="b528e-125">Display name spear-phishing attack</span></span>

<span data-ttu-id="b528e-p105">網路釣魚是歸類為社交樣式攻擊的攻擊廣泛套件泛用詞。此攻擊著重於矛網路釣魚，旨在一組特定個人或組織更目標攻擊。通常具有某些偵察自訂的攻擊執行及使用會產生信任的收件者的顯示名稱，例如看起來像其電子郵件是來自組織內的主管。</span><span class="sxs-lookup"><span data-stu-id="b528e-p105">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="b528e-p106">此攻擊著重於可讓您管理者會出現訊息至郵件來自透過變更顯示名稱和來源地址。當矛網路釣魚攻擊都成功時，cybercriminals 存取使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="b528e-p106">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="b528e-131">若要模擬矛網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="b528e-131">To simulate a spear-phishing attack</span></span>

![撰寫電子郵件內文](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="b528e-p107">您可以製作直接在**電子郵件內文**] 欄位中本身豐富的 HTML 編輯器或與 HTML 來源搭配使用。有兩個重要納入 HTML 欄位：</span><span class="sxs-lookup"><span data-stu-id="b528e-p107">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source. There are two important fields for inclusion in the HTML:</span></span> 
  
1. <span data-ttu-id="b528e-135">在[安全性&amp;規範中心](https://security.microsoft.com)、 選擇 [ **Threat management** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="b528e-135">In the [Security &amp; Compliance Center](https://security.microsoft.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="b528e-136">指定攻擊的有意義的行銷活動名稱或選取範本。</span><span class="sxs-lookup"><span data-stu-id="b528e-136">Specify a meaningful campaign name for the attack or select a template.</span></span> <br/>![網路釣魚起始頁面](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="b528e-p108">指定的目標收件者。這可以是個人或組織中的群組。每個目標的收件者必須有 Exchange Online 信箱的攻擊順序設為 [成功。</span><span class="sxs-lookup"><span data-stu-id="b528e-p108">Specify the target recipients. This can be individuals or groups in your organization. Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span> <br/>![收件者的選取項目](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="b528e-142">設定網路釣魚電子郵件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b528e-142">Configure the Phishing email details.</span></span> <br/>![設定電子郵件的詳細資訊](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/><span data-ttu-id="b528e-p109">HTML 格式可為複雜或基本您 campaign 需求。為電子郵件格式是 HTML，您可以插入影像和文字來加強 believability。您必須上接收的郵件中接收的電子郵件用戶端會尋找控制項。</span><span class="sxs-lookup"><span data-stu-id="b528e-p109">The HTML formatting can be as complex or basic as your campaign needs. As the email format is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.</span></span>
    
5. <span data-ttu-id="b528e-p110">指定文字**的 (Name)** ] 欄位。這是顯示在接收的電子郵件用戶端中的**顯示名稱**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="b528e-p110">Specify text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
6. <span data-ttu-id="b528e-p111">指定的文字或 [**從**] 欄位。這是電子郵件地址接收的電子郵件用戶端的寄件者顯示的欄位。</span><span class="sxs-lookup"><span data-stu-id="b528e-p111">Specify text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client. </span></span><br/><span data-ttu-id="b528e-p112">您可以在組織內輸入現有的電子郵件命名空間 （執行此動作會使實際解決接收的用戶端，協助非常高信任模型中的電子郵件地址），或者您也可以輸入的外部電子郵件地址。電子郵件地址所指定並沒有實際存在，但它沒有需要遵循的有效的 SMTP 位址，例如 user@domainname.extension 格式。</span><span class="sxs-lookup"><span data-stu-id="b528e-p112">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
7. <span data-ttu-id="b528e-p113">使用下拉式選取器，請選取 [以反映您必須在您攻擊內的內容類型的網路釣魚登入伺服器 URL。您可以選擇的例如文件傳遞、 技術、 薪資等提供數個佈景主題的 Url。這實際上是按一下 [要求目標的使用者的 URL。</span><span class="sxs-lookup"><span data-stu-id="b528e-p113">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
8. <span data-ttu-id="b528e-p114">指定自訂登陸頁面 URL]。使用這會將使用者重新導向至您指定成功攻擊結尾處的 URL。如果您有內部認識訓練，例如，您可以指定的以下。</span><span class="sxs-lookup"><span data-stu-id="b528e-p114">Specify a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.</span></span>
    
9. <span data-ttu-id="b528e-p115">指定文字的 [**主旨**] 欄位。這是做為**主體名稱**接收的電子郵件用戶端中顯示的欄位。</span><span class="sxs-lookup"><span data-stu-id="b528e-p115">Specify text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
10. <span data-ttu-id="b528e-160">撰寫目標會收到**電子郵件內文**。</span><span class="sxs-lookup"><span data-stu-id="b528e-160">Compose the **Email body** that the target will receive.</span></span> <br/><span data-ttu-id="b528e-161">`${username}`插入電子郵件內文中的目標名稱。</span><span class="sxs-lookup"><span data-stu-id="b528e-161">`${username}` inserts the targets name into the Email body.</span></span> <br/><span data-ttu-id="b528e-162">`${loginserverurl}`會插入我們想要按一下目標使用者的 URL</span><span class="sxs-lookup"><span data-stu-id="b528e-162">`${loginserverurl}` inserts the URL we want target users to click</span></span> 
    
11. <span data-ttu-id="b528e-p116">選擇 [**下一步]** [**完成]** 以啟動攻擊。矛網路釣魚電子郵件訊息會傳送到您目標收件者的信箱。</span><span class="sxs-lookup"><span data-stu-id="b528e-p116">Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="b528e-165">密碼噴灑攻擊</span><span class="sxs-lookup"><span data-stu-id="b528e-165">Password-spray attack</span></span>

<span data-ttu-id="b528e-p117">組織密碼噴灑攻擊通常用後 bad 動作項目已成功取得承租人的有效使用者清單。關於人員使用的一般密碼知道 bad 動作項目。這是廣泛用的攻擊、 時執行，並更困難比暴力方法偵測便宜攻擊。</span><span class="sxs-lookup"><span data-stu-id="b528e-p117">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant. The bad actor knows about common passwords that people use. This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="b528e-169">此攻擊著重於讓您指定要對使用者的大型目標基底的一般密碼。</span><span class="sxs-lookup"><span data-stu-id="b528e-169">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="b528e-170">若要模擬密碼噴灑攻擊</span><span class="sxs-lookup"><span data-stu-id="b528e-170">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="b528e-171">在[安全性&amp;規範中心](https://security.microsoft.com)、 選擇 [ **Threat management** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="b528e-171">In the [Security &amp; Compliance Center](https://security.microsoft.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="b528e-172">指定攻擊的有意義的行銷活動名稱。</span><span class="sxs-lookup"><span data-stu-id="b528e-172">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="b528e-p118">指定的目標收件者。這可以是個人或組織中的群組。目標的收件者必須有 Exchange Online 信箱的攻擊順序設為 [成功。</span><span class="sxs-lookup"><span data-stu-id="b528e-p118">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="b528e-p119">指定要用於攻擊的密碼。例如，您可以嘗試的一個一般、 相關 password 是`Fall2017`。另一個可能`Spring2018`，或`Password1`。</span><span class="sxs-lookup"><span data-stu-id="b528e-p119">Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="b528e-179">選擇 [**完成**] 以啟動攻擊。</span><span class="sxs-lookup"><span data-stu-id="b528e-179">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="b528e-180">暴力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="b528e-180">Brute-force password attack</span></span>

<span data-ttu-id="b528e-p120">組織暴力密碼攻擊通常用後 bad 動作項目已成功取得承租人的主要使用者清單。此攻擊著重在嘗試一組的單一使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="b528e-p120">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant. This attack focuses on trying a set of passwords on a single user's account.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="b528e-183">若要模擬暴力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="b528e-183">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="b528e-184">在[安全性&amp;規範中心](https://security.microsoft.com)、 選擇 [ **Threat management** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="b528e-184">In the [Security &amp; Compliance Center](https://security.microsoft.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="b528e-185">指定攻擊的有意義的行銷活動名稱。</span><span class="sxs-lookup"><span data-stu-id="b528e-185">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="b528e-p121">指定目標收件者。目標的收件者必須有 Exchange Online 信箱的攻擊順序設為 [成功。</span><span class="sxs-lookup"><span data-stu-id="b528e-p121">Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="b528e-p122">指定一組要用於攻擊的密碼。您可以使用的文字 (.txt) 檔案的清單中的密碼。將文字檔不可超過 10 MB 的檔案大小。使用一個密碼每行，並確認清單中的最後一個密碼之後加上固定傳回。</span><span class="sxs-lookup"><span data-stu-id="b528e-p122">Specify a set of passwords to use for the attack. You can use a text (.txt) file for your list of passwords. The text file cannot exceed 10 MB in file size. Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>
    
5. <span data-ttu-id="b528e-192">選擇 [**完成**] 以啟動攻擊。</span><span class="sxs-lookup"><span data-stu-id="b528e-192">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="b528e-193">攻擊模擬器中的新功能</span><span class="sxs-lookup"><span data-stu-id="b528e-193">New features in Attack Simulator</span></span>

<span data-ttu-id="b528e-p123">新功能會被新增至攻擊模擬器。這些包括：</span><span class="sxs-lookup"><span data-stu-id="b528e-p123">New features are being added to Attack Simulator. These include:</span></span>
- <span data-ttu-id="b528e-p124">**進階報表功能**。您將能看到資料按一下中郵件等等的連結以開啟攻擊模擬電子郵件訊息、 最快 （或速度最慢） 時間最快 （或速度最慢） 的時間。</span><span class="sxs-lookup"><span data-stu-id="b528e-p124">**Advanced reporting capabilities**. You'll be able to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more.</span></span>
- <span data-ttu-id="b528e-p125">**電子郵件範本編輯器**。您可以建立您可用於未來的攻擊模擬的自訂、 可重複使用的電子郵件範本。</span><span class="sxs-lookup"><span data-stu-id="b528e-p125">**Email template editor**. You can create a custom, reusable email template that you can use for future attack simulations.</span></span>

<span data-ttu-id="b528e-200">請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)功能開發、 功能已啟用，並什麼已經啟動。</span><span class="sxs-lookup"><span data-stu-id="b528e-200">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>



