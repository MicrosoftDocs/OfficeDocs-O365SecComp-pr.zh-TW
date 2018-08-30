---
title: Office 365 中的攻擊模擬器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/19/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: 了解您可以執行使用攻擊模擬器的適當攻擊的約三種不同類型。
ms.openlocfilehash: 364144c0b2f8109c67fb262ce879414088380ebe
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526488"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="72eba-103">Office 365 中的攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="72eba-103">Attack Simulator in Office 365</span></span>

<span data-ttu-id="72eba-p101">使用攻擊模擬器 （包含在[Office 365 威脅智慧](office-365-ti.md)），如果您的組織的安全性小組成員您可以執行真實感化的攻擊案例在組織中。這可協助您識別並尋找遭到入侵的使用者才能實際攻擊影響底部線條。</span><span class="sxs-lookup"><span data-stu-id="72eba-p101">With Attack Simulator (included in [Office 365 Threat Intelligence](office-365-ti.md)), if you are a member of your organization's security team, you can run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="72eba-106">攻擊</span><span class="sxs-lookup"><span data-stu-id="72eba-106">The Attacks</span></span>

<span data-ttu-id="72eba-107">在預覽版我們提供您可以執行的攻擊模擬的三種：</span><span class="sxs-lookup"><span data-stu-id="72eba-107">At preview release we offer three kinds of attack simulations that you can run:</span></span>
  
- [<span data-ttu-id="72eba-108">顯示名稱矛網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="72eba-108">Display name spear-phishing attack</span></span>](attack-simulator.md#spearphish)
    
- [<span data-ttu-id="72eba-109">密碼噴灑攻擊</span><span class="sxs-lookup"><span data-stu-id="72eba-109">Password-spray attack</span></span>](attack-simulator.md#passwordspray)
    
- [<span data-ttu-id="72eba-110">暴力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="72eba-110">Brute-force password attack</span></span>](attack-simulator.md#bruteforce)
    
<span data-ttu-id="72eba-111">若要成功啟動攻擊，執行攻擊及登入的帳戶必須使用多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="72eba-111">For an attack to be successfully launched, the account that is running the attack and logged on must use multi-factor authentication.</span></span>
  
> [!NOTE]
> <span data-ttu-id="72eba-112">條件式存取的支援即將推出。</span><span class="sxs-lookup"><span data-stu-id="72eba-112">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="72eba-113">若要存取安全性的攻擊模擬器&amp;規範中心選擇**Threat management** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="72eba-113">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="72eba-114">開始之前...]</span><span class="sxs-lookup"><span data-stu-id="72eba-114">Before you begin...</span></span>

<span data-ttu-id="72eba-115">請確定您和您的組織符合攻擊模擬器的需求如下：</span><span class="sxs-lookup"><span data-stu-id="72eba-115">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
  
- <span data-ttu-id="72eba-116">您的組織具有[Office 365 威脅智慧](office-365-ti.md)與可見安全性攻擊模擬器&amp;規範中心 (移至 [ **Threat management** \> **攻擊模擬器**)</span><span class="sxs-lookup"><span data-stu-id="72eba-116">Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span>
    
- <span data-ttu-id="72eba-p102">貴組織的電子郵件裝載於 Exchange Online。（攻擊模擬器不適用於內部部署電子郵件伺服器。）</span><span class="sxs-lookup"><span data-stu-id="72eba-p102">Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="72eba-119">您是 Office 365 全域管理員</span><span class="sxs-lookup"><span data-stu-id="72eba-119">You are an Office 365 global administrator</span></span>
    
- <span data-ttu-id="72eba-120">您的組織使用[的 Office 365 使用者的多重要素驗證](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)</span><span class="sxs-lookup"><span data-stu-id="72eba-120">Your organization is using [Multi-factor authentication for Office 365 users](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)</span></span>
    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="72eba-121">顯示名稱矛網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="72eba-121">Display name spear-phishing attack</span></span>

<span data-ttu-id="72eba-p103">網路釣魚是歸類為社交樣式攻擊的攻擊廣泛套件泛用詞。此攻擊著重於矛網路釣魚，旨在一組特定個人或組織更目標攻擊。通常具有某些偵察自訂的攻擊執行及使用會產生信任的收件者的顯示名稱，例如看起來像其電子郵件是來自組織內的主管。</span><span class="sxs-lookup"><span data-stu-id="72eba-p103">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="72eba-p104">此攻擊著重於可讓您管理者會出現訊息至郵件來自透過變更顯示名稱和來源地址。當矛網路釣魚攻擊都成功時，cybercriminals 存取使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="72eba-p104">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="72eba-127">若要模擬矛網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="72eba-127">To simulate a spear-phishing attack</span></span>

![撰寫電子郵件內文](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="72eba-p105">您可以製作直接在**電子郵件內文**] 欄位中本身豐富的 HTML 編輯器或與 HTML 來源搭配使用。有兩個重要納入 HTML 欄位：</span><span class="sxs-lookup"><span data-stu-id="72eba-p105">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source. There are two important fields for inclusion in the HTML:</span></span> 
  
1. <span data-ttu-id="72eba-131">安全性&amp;規範中心選擇**Threat management** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="72eba-131">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="72eba-132">指定攻擊的有意義的行銷活動名稱或選取範本。</span><span class="sxs-lookup"><span data-stu-id="72eba-132">Specify a meaningful campaign name for the attack or select a template.</span></span>
    
    ![網路釣魚起始頁面](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="72eba-p106">指定的目標收件者。這可以是個人或組織中的群組。目標的收件者必須有 Exchange Online 信箱的攻擊順序設為 [成功。</span><span class="sxs-lookup"><span data-stu-id="72eba-p106">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
    ![收件者的選取項目](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="72eba-138">設定網路釣魚電子郵件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="72eba-138">Configure the Phishing email details.</span></span>
    
    ![設定電子郵件的詳細資訊](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)
  
    <span data-ttu-id="72eba-p107">HTML 格式可為複雜或基本您 campaign 需求。如是 HTML，您可以插入影像和文字來加強 believability。您必須上接收的郵件中接收的電子郵件用戶端會尋找控制項。</span><span class="sxs-lookup"><span data-stu-id="72eba-p107">The HTML formatting can be as complex or basic as your campaign needs. As it is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.</span></span>
    
1. <span data-ttu-id="72eba-p108">**從 (Name)** ] 欄位中輸入文字。這是顯示在接收的電子郵件用戶端中的**顯示名稱**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="72eba-p108">Enter text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
2. <span data-ttu-id="72eba-p109">輸入的文字或 [**從**] 欄位。這是電子郵件地址接收的電子郵件用戶端的寄件者顯示的欄位。</span><span class="sxs-lookup"><span data-stu-id="72eba-p109">Enter text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="72eba-p110">您可以在組織內輸入現有的電子郵件命名空間 （執行此動作會使實際解決接收的用戶端，協助非常高信任模型中的電子郵件地址），或者您也可以輸入的外部電子郵件地址。電子郵件地址所指定並沒有實際存在，但它沒有需要遵循的有效的 SMTP 位址，例如 user@domainname.extension 格式。</span><span class="sxs-lookup"><span data-stu-id="72eba-p110">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
3. <span data-ttu-id="72eba-p111">使用下拉式選取器，請選取 [以反映您必須在您攻擊內的內容類型的網路釣魚登入伺服器 URL。您可以選擇的例如文件傳遞、 技術、 薪資等提供數個佈景主題的 Url。這實際上是按一下 [要求目標的使用者的 URL。</span><span class="sxs-lookup"><span data-stu-id="72eba-p111">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
4. <span data-ttu-id="72eba-p112">輸入自訂登陸頁面 URL]。使用這會將使用者重新導向至您指定成功攻擊結尾處的 URL。如果您有內部認識訓練，例如，您可以指定的以下。</span><span class="sxs-lookup"><span data-stu-id="72eba-p112">Enter a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.</span></span>
    
5. <span data-ttu-id="72eba-p113">針對 [**主旨**] 欄位中輸入文字。這是做為**主體名稱**接收的電子郵件用戶端中顯示的欄位。</span><span class="sxs-lookup"><span data-stu-id="72eba-p113">Enter text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
5. <span data-ttu-id="72eba-156">撰寫目標會收到**電子郵件內文**。</span><span class="sxs-lookup"><span data-stu-id="72eba-156">Compose the **Email body** that the target will receive.</span></span> 
  
 <span data-ttu-id="72eba-157">**${username}** 會插入電子郵件內文中的目標名稱</span><span class="sxs-lookup"><span data-stu-id="72eba-157">**${username}** inserts the targets name into the Email body</span></span> 
  
 <span data-ttu-id="72eba-158">**${loginserverurl}** 會插入我們想要按一下目標使用者的 URL</span><span class="sxs-lookup"><span data-stu-id="72eba-158">**${loginserverurl}** inserts the URL we want target users to click</span></span> 
    
6. <span data-ttu-id="72eba-p114">選擇 [**下一步]** [**完成]** 以啟動攻擊。矛網路釣魚電子郵件訊息會傳送到您目標收件者的信箱。</span><span class="sxs-lookup"><span data-stu-id="72eba-p114">Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="72eba-161">密碼噴灑攻擊</span><span class="sxs-lookup"><span data-stu-id="72eba-161">Password-spray attack</span></span>

<span data-ttu-id="72eba-p115">組織密碼噴灑攻擊通常用後 bad 動作項目已成功列舉的承租人，利用其專業知識的一般密碼的有效使用者清單。它是利用廣泛原狀便宜的攻擊執行，且更難偵測比暴力方法。</span><span class="sxs-lookup"><span data-stu-id="72eba-p115">A password spray attack against an organization is typically used after a bad actor has successfully enumerated a list of valid users from the tenant, utilizing their knowledge of common passwords used. It is utilized widely as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="72eba-164">此攻擊著重於讓您指定要對使用者的大型目標基底的一般密碼。</span><span class="sxs-lookup"><span data-stu-id="72eba-164">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="72eba-165">若要模擬密碼噴灑攻擊</span><span class="sxs-lookup"><span data-stu-id="72eba-165">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="72eba-166">安全性&amp;規範中心選擇**Threat management** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="72eba-166">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="72eba-167">指定攻擊的有意義的行銷活動名稱。</span><span class="sxs-lookup"><span data-stu-id="72eba-167">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="72eba-p116">指定的目標收件者。這可以是個人或組織中的群組。目標的收件者必須有 Exchange Online 信箱的攻擊順序設為 [成功。</span><span class="sxs-lookup"><span data-stu-id="72eba-p116">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="72eba-p117">指定要用於攻擊的密碼。例如，您可以嘗試的一個一般、 相關 password 是`Fall2017`。另一個可能`Spring2018`，或`Password1`。</span><span class="sxs-lookup"><span data-stu-id="72eba-p117">Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="72eba-174">選擇 [**完成**] 以啟動攻擊。</span><span class="sxs-lookup"><span data-stu-id="72eba-174">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="72eba-175">暴力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="72eba-175">Brute-force password attack</span></span>

<span data-ttu-id="72eba-p118">組織暴力密碼攻擊通常用後 bad 動作項目已成功列舉的承租人的主要使用者清單。此攻擊著重於讓您指定一組針對單一使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="72eba-p118">A brute-force password attack against an organization is typically used after a bad actor has successfully enumerated a list of key users from the tenant. This attack focuses on letting you specify a set of passwords against a single user.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="72eba-178">若要模擬暴力密碼攻擊</span><span class="sxs-lookup"><span data-stu-id="72eba-178">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="72eba-179">安全性&amp;規範中心選擇**Threat management** \> **攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="72eba-179">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="72eba-180">指定攻擊的有意義的行銷活動名稱。</span><span class="sxs-lookup"><span data-stu-id="72eba-180">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="72eba-p119">指定目標收件者。目標的收件者必須有 Exchange Online 信箱的攻擊順序設為 [成功。</span><span class="sxs-lookup"><span data-stu-id="72eba-p119">Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="72eba-p120">指定一組要用於攻擊的密碼。例如，您可以嘗試的一個一般、 相關 password 是`Fall2017`。另一個可能`Spring2018`，或`Password1`。</span><span class="sxs-lookup"><span data-stu-id="72eba-p120">Specify a set of passwords to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="72eba-186">選擇 [**完成**] 以啟動攻擊。</span><span class="sxs-lookup"><span data-stu-id="72eba-186">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="72eba-187">相關主題</span><span class="sxs-lookup"><span data-stu-id="72eba-187">Related topics</span></span>

[<span data-ttu-id="72eba-188">Office 365 威脅情報</span><span class="sxs-lookup"><span data-stu-id="72eba-188">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  

