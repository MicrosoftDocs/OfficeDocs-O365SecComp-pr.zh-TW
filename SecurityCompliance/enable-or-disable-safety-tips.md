---
title: 啟用或停用 Office 365 中的安全提示
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/6/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
description: 指示 Office 365 和 EOP 系統管理員如何啟用和停用的電子郵件安全性提示。
ms.openlocfilehash: 3a8257f9d34ec5def54e2b9c9e919172366d023f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526855"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a><span data-ttu-id="2a1a9-103">啟用或停用 Office 365 中的安全提示</span><span class="sxs-lookup"><span data-stu-id="2a1a9-103">Enable or disable safety tips in Office 365</span></span>

<span data-ttu-id="2a1a9-p101">Exchange Online Protection (EOP)，或者戳記，safety 提示以它傳送的電子郵件訊息。如果郵件已標示為垃圾郵件的 Office 365 中，如果郵件包含如網路釣魚詐騙郵件可疑的某個項目或外部圖像有這些 safety 秘訣提供一個快速而 visual 方法來判斷訊息是否從安全的收件者已驗證寄件者已封鎖。Office 365 和 EOP 獨立版系統管理員可以編輯垃圾郵件原則設定啟用或停用不會顯示 Outlook 與其他桌面電子郵件用戶端中的電子郵件安全性提示。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-p101">Exchange Online Protection (EOP) adds, or stamps, a safety tip to email messages that it delivers. These safety tips provide recipients with a quick, visual way to determine if a message is from a safe, verified sender, if the message has been marked as spam by Office 365, if the message contains something suspicious such as a phishing scam, or if external images have been blocked. Office 365 and EOP-standalone admins can edit a spam policy setting to enable or disable safety tips from being displayed in email in Outlook and other desktop email clients.</span></span> 
  
<span data-ttu-id="2a1a9-p102">Office 365 讓組織的預設安全秘訣和建議您保留這些功能可協助戰鬥垃圾郵件和網路釣魚攻擊。您無法停用 Outlook web 上 safety 秘訣。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-p102">Office 365 enables safety tips by default for your organization and we recommend that you leave them enabled to help combat spam and phishing attacks. You can't disable safety tips for Outlook on the web.</span></span>
  
<span data-ttu-id="2a1a9-109">若要查看範例並了解 safety 提示中顯示的資訊，請參閱[Safety 秘訣 （英文） Office 365 中的電子郵件訊息中。](safety-tips-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="2a1a9-109">To see examples and to learn about the information displayed in safety tips, see [Safety tips in email messages in Office 365.](safety-tips-in-office-365.md)</span></span>
  
<span data-ttu-id="2a1a9-110">本主題內容：</span><span class="sxs-lookup"><span data-stu-id="2a1a9-110">In this topic:</span></span>
  
- [<span data-ttu-id="2a1a9-111">若要啟用或停用 safety 祕訣使用 Office 365 安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="2a1a9-111">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [<span data-ttu-id="2a1a9-112">若要啟用或停用 safety 秘訣 （英文） 透過 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a1a9-112">To enable or disable safety tips by using PowerShell</span></span>](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="2a1a9-113">若要啟用或停用 safety 祕訣使用 Office 365 安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="2a1a9-113">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>
<span data-ttu-id="2a1a9-114"><a name="SandCCsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="2a1a9-114"></span></span>

1. <span data-ttu-id="2a1a9-115">移至 [ [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-115">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="2a1a9-116">以您的工作或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-116">Sign in to Office 365 with your work or school account.</span></span>
    
3. <span data-ttu-id="2a1a9-117">選擇 [ **Threat Management** \> **原則**。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-117">Choose **Threat Management** \> **Policy**.</span></span> 
    
4. <span data-ttu-id="2a1a9-118">在 [**原則**] 頁面上選擇 [**反垃圾郵件**]。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-118">On the **Policy** page, choose **Anti-Spam**.</span></span>
    
    ![這個螢幕擷取畫面顯示如何取得反垃圾郵件設定] 頁面上的 [安全性]&amp;規範中心。](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. <span data-ttu-id="2a1a9-120">**反垃圾郵件設定**] 頁面上選擇 [**自訂**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-120">On the **Anti-spam settings** page choose the **Custom** tab.</span></span> 
    
    ![這個螢幕擷取畫面顯示 [自訂] 索引標籤的位置上反垃圾郵件設定] 頁面上的 [安全性]&amp;規範中心。](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. <span data-ttu-id="2a1a9-p103">若有必要，請選擇 [**自訂設定**轉換到開啟的自訂設定。自訂設定參數設為**關閉**，如果您將不能夠修改垃圾郵件篩選器原則。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-p103">If necessary, choose the **Custom settings** switch to turn on custom settings. If the custom settings switch is set to **Off**, you won't be able to modify spam filter policies.</span></span>
    
    ![這個螢幕擷取畫面顯示自訂的反垃圾郵件篩選已關閉的原則設定。](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. <span data-ttu-id="2a1a9-p104">展開您想要修改，然後選擇 [**編輯原則**的垃圾郵件原則。例如，選擇 [**預設垃圾郵件篩選原則**旁的向下箭號。或者，如果您想，您可以選擇 [**新增原則**建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-p104">Expand the spam policy you want to modify and then choose **Edit policy**. For example, choose the down arrow next to **Default spam filter policy**. Or, if you want, you can create a new policy by choosing **Add a policy**.</span></span>
    
8. <span data-ttu-id="2a1a9-128">依序展開 [**垃圾郵件和大量**動作。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-128">Expand **Spam and bulk** actions.</span></span> 
    
9. <span data-ttu-id="2a1a9-p105">若要啟用安全秘訣、 下**Safety 秘訣**、 [**上**] 核取方塊。若要停用安全秘訣，請清除 [**上**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-p105">To enable safety tips, under **Safety Tips**, check the **On** checkbox. To disable safety tips, clear the **On** checkbox.</span></span> 
    
10. <span data-ttu-id="2a1a9-131">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-131">Choose **Save**.</span></span>
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a><span data-ttu-id="2a1a9-132">若要啟用或停用 safety 秘訣 （英文） 透過 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a1a9-132">To enable or disable safety tips by using PowerShell</span></span>
<span data-ttu-id="2a1a9-133"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="2a1a9-133"></span></span>

<span data-ttu-id="2a1a9-p106">系統管理員可以使用 Exchange Online PowerShell 啟用或停用安全秘訣。使用 Set-hostedcontentfilterpolicy 指令程式來啟用或停用垃圾郵件篩選器原則中的安全秘訣。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-p106">Admins can use Exchange Online PowerShell to enable or disable safety tips. Use the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips in a spam filter policy.</span></span>
  
1. <span data-ttu-id="2a1a9-p107">連線到 Exchange Online PowerShell。資訊，請參閱[Connect to Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-p107">Connect to Exchange Online PowerShell. For information, see [Connect to Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="2a1a9-138">執行 Set-hostedcontentfilterpolicy 指令程式來啟用或停用安全秘訣：</span><span class="sxs-lookup"><span data-stu-id="2a1a9-138">Run the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips:</span></span>
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

    <span data-ttu-id="2a1a9-139">其中：</span><span class="sxs-lookup"><span data-stu-id="2a1a9-139">Where:</span></span>
    
  -  <span data-ttu-id="2a1a9-140">*原則名稱*是您要修改，例如**預設**原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-140">*policy name*  is the name of the policy you want to modify, for example **default**.</span></span>
    
  -  <span data-ttu-id="2a1a9-141">`$true`可讓 safety 秘訣垃圾郵件篩選器原則。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-141">`$true` enables safety tips for the spam filter policy.</span></span> 
    
  -  <span data-ttu-id="2a1a9-142">`$false`停用垃圾郵件篩選器原則 safety 的秘訣。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-142">`$false` disables safety tips for the spam filter policy.</span></span> 
    
    <span data-ttu-id="2a1a9-143">例如，若要停用預設的垃圾郵件篩選器原則的安全秘訣，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="2a1a9-143">For example, to disable safety tips for the default spam filter policy, run the following command:</span></span>
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

    <span data-ttu-id="2a1a9-144">如需此 cmdlet 的詳細資訊，請參閱[Set-hostedcontentfilterpolicy](https://technet.microsoft.com/library/jj200781.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-144">For more information about this cmdlet, see [Set-HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx).</span></span>
    
## <a name="still-need-help"></a><span data-ttu-id="2a1a9-145">仍然需要說明嗎？</span><span class="sxs-lookup"><span data-stu-id="2a1a9-145">Still need help?</span></span>
<span data-ttu-id="2a1a9-146"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="2a1a9-146"></span></span>

<span data-ttu-id="2a1a9-147">如果您停用安全秘訣，但卻還是看到這些電子郵件訊息中，檢查下列事項：</span><span class="sxs-lookup"><span data-stu-id="2a1a9-147">If you disabled safety tips but are still seeing them in your email messages, check these things:</span></span>
  
- <span data-ttu-id="2a1a9-p108">您無法停用 Outlook web 上 safety 秘訣。嘗試在另一個用戶端，例如 Outlook 檢視相同的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-p108">You can't disable safety tips for Outlook on the web. Try viewing the same email in another client, such as Outlook.</span></span>
    
- <span data-ttu-id="2a1a9-p109">Safety 提示上根據預設會針對每一個使用 EOP，這包括具有 Office 365 的任何人。若要停用電子郵件中顯示來自 safety 秘訣，您必須使用停用其垃圾郵件篩選器原則本主題所述。一旦您已設定的原則，請確定已啟用。如需啟用垃圾郵件篩選器原則，請參閱[設定垃圾郵件篩選器原則](https://technet.microsoft.com/library/jj200684.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-p109">Safety tips are on by default for every one who uses EOP, this includes everyone who has Office 365. In order to disable safety tips from showing up in email, you must disable them by using a spam filter policy as described in this topic. Once you've set up the policy, ensure that it is enabled. For information on enabling spam filter policies, see [Configure your spam filter policies](https://technet.microsoft.com/library/jj200684.aspx).</span></span>
    
<span data-ttu-id="2a1a9-154">更多抵禦垃圾郵件和網路釣魚的方式，請參閱[Office 365 電子郵件反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-154">For more ways to combat spam and phishing, see [Office 365 Email Anti-Spam Protection](anti-spam-protection.md).</span></span>
  

