---
<span data-ttu-id="03d42-101">標題: 「 啟用或停用 Office 365 中的安全提示"ms.author: krowley 作者： kccross manager: laurawi ms.date: 2018/12/05 ms.audience: Admin ms.topic： 文章 ms.service: o365 管理 localization_priority: Normal search.appverid:</span><span class="sxs-lookup"><span data-stu-id="03d42-101">title: "Enable or disable safety tips in Office 365" ms.author: krowley author: kccross manager: laurawi ms.date: 12/05/2018 ms.audience: Admin ms.topic: article ms.service: o365-administration localization_priority: Normal search.appverid:</span></span> 
- <span data-ttu-id="03d42-102">MET150 ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7 ms.collection:</span><span class="sxs-lookup"><span data-stu-id="03d42-102">MET150 ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7   ms.collection:</span></span>
    - <span data-ttu-id="03d42-103">M365 安全性合規性描述: 「 告訴 Office 365 和 EOP 系統管理員如何啟用及停用電子郵件訊息中的安全提示。 」</span><span class="sxs-lookup"><span data-stu-id="03d42-103">M365-security-compliance description: "Tells Office 365 and EOP admins how to enable and disable safety tips in email messages."</span></span>
---

# <a name="enable-or-disable-safety-tips-in-office-365"></a><span data-ttu-id="03d42-104">啟用或停用 Office 365 中的安全提示</span><span class="sxs-lookup"><span data-stu-id="03d42-104">Enable or disable safety tips in Office 365</span></span>

<span data-ttu-id="03d42-105">Exchange Online Protection (EOP) 新增，或傳送的電子郵件的戳記，safety 提示。</span><span class="sxs-lookup"><span data-stu-id="03d42-105">Exchange Online Protection (EOP) adds, or stamps, a safety tip to email messages that it delivers.</span></span> <span data-ttu-id="03d42-106">如果郵件已標示為垃圾郵件由 Office 365 中，如果郵件包含可疑的網路釣魚詐騙，例如某個項目或外部影像有這些安全提示提供快速、 視覺化的方式，來判斷郵件是否安全，從收件者驗證寄件者已封鎖。</span><span class="sxs-lookup"><span data-stu-id="03d42-106">These safety tips provide recipients with a quick, visual way to determine if a message is from a safe, verified sender, if the message has been marked as spam by Office 365, if the message contains something suspicious such as a phishing scam, or if external images have been blocked.</span></span> <span data-ttu-id="03d42-107">Office 365 與獨立式 EOP 系統管理員可以編輯若要啟用或停用安全提示顯示於 Outlook 和其他桌面電子郵件用戶端中的電子郵件的垃圾郵件原則設定。</span><span class="sxs-lookup"><span data-stu-id="03d42-107">Office 365 and EOP-standalone admins can edit a spam policy setting to enable or disable safety tips from being displayed in email in Outlook and other desktop email clients.</span></span> 
  
<span data-ttu-id="03d42-108">Office 365 組織的預設啟用安全提示，並建議您保留加以啟用，以協助抵禦垃圾郵件和網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="03d42-108">Office 365 enables safety tips by default for your organization and we recommend that you leave them enabled to help combat spam and phishing attacks.</span></span> <span data-ttu-id="03d42-109">您無法停用 outlook 網頁版安全提示。</span><span class="sxs-lookup"><span data-stu-id="03d42-109">You can't disable safety tips for Outlook on the web.</span></span>
  
<span data-ttu-id="03d42-110">若要查看範例，以及了解安全提示中顯示的資訊，請參閱[安全提示在 Office 365 中的電子郵件訊息中。](safety-tips-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="03d42-110">To see examples and to learn about the information displayed in safety tips, see [Safety tips in email messages in Office 365.](safety-tips-in-office-365.md)</span></span>
  
<span data-ttu-id="03d42-111">本主題內容：</span><span class="sxs-lookup"><span data-stu-id="03d42-111">In this topic:</span></span>
  
- [<span data-ttu-id="03d42-112">若要啟用或停用安全提示使用 Office 365 安全性&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="03d42-112">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [<span data-ttu-id="03d42-113">若要啟用或停用安全提示，藉由使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="03d42-113">To enable or disable safety tips by using PowerShell</span></span>](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="03d42-114">若要啟用或停用安全提示使用 Office 365 安全性&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="03d42-114">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>
<span data-ttu-id="03d42-115"><a name="SandCCsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="03d42-115"></span></span>

1. <span data-ttu-id="03d42-116">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="03d42-116">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="03d42-117">以公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="03d42-117">Sign in to Office 365 with your work or school account.</span></span>
    
3. <span data-ttu-id="03d42-118">選擇 [**威脅管理** \> **原則**。</span><span class="sxs-lookup"><span data-stu-id="03d42-118">Choose **Threat Management** \> **Policy**.</span></span> 
    
4. <span data-ttu-id="03d42-119">在 [**原則**] 頁面上，選擇 [**反垃圾郵件**]。</span><span class="sxs-lookup"><span data-stu-id="03d42-119">On the **Policy** page, choose **Anti-Spam**.</span></span>
    
    ![這個螢幕擷取畫面顯示如何取得反垃圾郵件設定] 頁面上，安全性&amp;合規性中心。](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. <span data-ttu-id="03d42-121">在 [**反垃圾郵件設定**] 頁面上選擇 [**自訂**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="03d42-121">On the **Anti-spam settings** page choose the **Custom** tab.</span></span> 
    
    ![這個螢幕擷取畫面顯示 [自訂] 索引標籤的位置上反垃圾郵件設定] 頁面上，安全性&amp;合規性中心。](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. <span data-ttu-id="03d42-123">如有必要，選擇 [開啟自訂設定的**自訂設定**參數。</span><span class="sxs-lookup"><span data-stu-id="03d42-123">If necessary, choose the **Custom settings** switch to turn on custom settings.</span></span> <span data-ttu-id="03d42-124">如果自訂設定參數設為**關閉**，您無法修改垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="03d42-124">If the custom settings switch is set to **Off**, you won't be able to modify spam filter policies.</span></span>
    
    ![這個螢幕擷取畫面顯示自訂的反垃圾郵件篩選原則設定為關閉。](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. <span data-ttu-id="03d42-126">展開您要修改]，然後選擇 [**編輯原則**的垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="03d42-126">Expand the spam policy you want to modify and then choose **Edit policy**.</span></span> <span data-ttu-id="03d42-127">例如，選擇**預設垃圾郵件篩選原則**旁的向下箭號。</span><span class="sxs-lookup"><span data-stu-id="03d42-127">For example, choose the down arrow next to **Default spam filter policy**.</span></span> <span data-ttu-id="03d42-128">或者，如果您想，您可以選擇 [**新增原則**建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="03d42-128">Or, if you want, you can create a new policy by choosing **Add a policy**.</span></span>
    
8. <span data-ttu-id="03d42-129">展開 [**垃圾郵件] 和 [大量**動作]。</span><span class="sxs-lookup"><span data-stu-id="03d42-129">Expand **Spam and bulk** actions.</span></span> 
    
9. <span data-ttu-id="03d42-130">若要啟用安全提示，[**安全提示**，請**在 [上**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="03d42-130">To enable safety tips, under **Safety Tips**, check the **On** checkbox.</span></span> <span data-ttu-id="03d42-131">若要停用安全提示，請清除 [**上**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="03d42-131">To disable safety tips, clear the **On** checkbox.</span></span> 
    
10. <span data-ttu-id="03d42-132">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="03d42-132">Choose **Save**.</span></span>
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a><span data-ttu-id="03d42-133">若要啟用或停用安全提示，藉由使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="03d42-133">To enable or disable safety tips by using PowerShell</span></span>
<span data-ttu-id="03d42-134"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="03d42-134"></span></span>

<span data-ttu-id="03d42-135">系統管理員可以使用 Exchange Online PowerShell，啟用或停用安全提示。</span><span class="sxs-lookup"><span data-stu-id="03d42-135">Admins can use Exchange Online PowerShell to enable or disable safety tips.</span></span> <span data-ttu-id="03d42-136">使用 Set-hostedcontentfilterpolicy 指令程式來啟用或停用垃圾郵件篩選原則中的安全提示。</span><span class="sxs-lookup"><span data-stu-id="03d42-136">Use the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips in a spam filter policy.</span></span>
  
1. <span data-ttu-id="03d42-137">連線至 Exchange Online PowerShell (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="03d42-137">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="03d42-138">如需資訊，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="03d42-138">For information, see [Connect to Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="03d42-139">執行 Set-hostedcontentfilterpolicy 指令程式來啟用或停用安全提示：</span><span class="sxs-lookup"><span data-stu-id="03d42-139">Run the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips:</span></span>
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

<span data-ttu-id="03d42-140">其中：</span><span class="sxs-lookup"><span data-stu-id="03d42-140">Where:</span></span>
    
  -  <span data-ttu-id="03d42-141">*原則名稱*是您想要修改，例如**預設**原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="03d42-141">*policy name*  is the name of the policy you want to modify, for example **default**.</span></span>
    
  -  <span data-ttu-id="03d42-142">`$true`啟用安全的祕訣垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="03d42-142">`$true` enables safety tips for the spam filter policy.</span></span> 
    
  -  <span data-ttu-id="03d42-143">`$false`停用垃圾郵件篩選器原則的安全提示。</span><span class="sxs-lookup"><span data-stu-id="03d42-143">`$false` disables safety tips for the spam filter policy.</span></span> 
    
    <span data-ttu-id="03d42-144">例如，若要停用預設垃圾郵件篩選器原則的安全提示，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="03d42-144">For example, to disable safety tips for the default spam filter policy, run the following command:</span></span>
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

<span data-ttu-id="03d42-145">如需有關此 cmdlet 的詳細資訊，請參閱 < <b0>Set-hostedcontentfilterpolicy</b0>。</span><span class="sxs-lookup"><span data-stu-id="03d42-145">For more information about this cmdlet, see [Set-HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx).</span></span>
    
## <a name="still-need-help"></a><span data-ttu-id="03d42-146">仍需要協助嗎？</span><span class="sxs-lookup"><span data-stu-id="03d42-146">Still need help?</span></span>
<span data-ttu-id="03d42-147"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="03d42-147"></span></span>

<span data-ttu-id="03d42-148">如果您停用安全提示，卻仍看到它們在您的電子郵件中，請檢查下列事項：</span><span class="sxs-lookup"><span data-stu-id="03d42-148">If you disabled safety tips but are still seeing them in your email messages, check these things:</span></span>
  
- <span data-ttu-id="03d42-149">您無法停用 outlook 網頁版安全提示。</span><span class="sxs-lookup"><span data-stu-id="03d42-149">You can't disable safety tips for Outlook on the web.</span></span> <span data-ttu-id="03d42-150">請嘗試在另一個用戶端，例如 Outlook 中檢視相同的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="03d42-150">Try viewing the same email in another client, such as Outlook.</span></span>
    
- <span data-ttu-id="03d42-151">安全提示都預設為每一個使用 EOP 的人員，這包括具有 Office 365 的人。</span><span class="sxs-lookup"><span data-stu-id="03d42-151">Safety tips are on by default for every one who uses EOP, this includes everyone who has Office 365.</span></span> <span data-ttu-id="03d42-152">若要停用安全提示從出現在 [電子郵件，您必須予以停用使用垃圾郵件篩選原則，如本主題所述。</span><span class="sxs-lookup"><span data-stu-id="03d42-152">In order to disable safety tips from showing up in email, you must disable them by using a spam filter policy as described in this topic.</span></span> <span data-ttu-id="03d42-153">一旦您已設定的原則，請確定已啟用。</span><span class="sxs-lookup"><span data-stu-id="03d42-153">Once you've set up the policy, ensure that it is enabled.</span></span> <span data-ttu-id="03d42-154">啟用垃圾郵件篩選原則的詳細資訊，請參閱[設定垃圾郵件篩選原則](https://technet.microsoft.com/library/jj200684.aspx)。</span><span class="sxs-lookup"><span data-stu-id="03d42-154">For information on enabling spam filter policies, see [Configure your spam filter policies](https://technet.microsoft.com/library/jj200684.aspx).</span></span>
    
<span data-ttu-id="03d42-155">如需更多，以便抵禦垃圾郵件和網路釣魚方法，請參閱 < <b0>Office 365 電子郵件反垃圾郵件保護</b0>。</span><span class="sxs-lookup"><span data-stu-id="03d42-155">For more ways to combat spam and phishing, see [Office 365 Email Anti-Spam Protection](anti-spam-protection.md).</span></span>
  

