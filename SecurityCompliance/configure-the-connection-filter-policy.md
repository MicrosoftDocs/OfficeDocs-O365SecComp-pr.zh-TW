---
title: 設定連線篩選原則
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/24/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
description: 若要確定，不會封鎖從您信任的人員傳送電子郵件，您可以使用連線篩選原則來建立一份允許清單，也就是安全的寄件者清單中，您信任的 IP 位址。 您也可以建立的封鎖寄件者清單。
ms.openlocfilehash: 5d19898b6baf01c7348b434f3caced202507c4d8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151295"
---
# <a name="configure-the-connection-filter-policy"></a><span data-ttu-id="8f993-104">設定連線篩選原則</span><span class="sxs-lookup"><span data-stu-id="8f993-104">Configure the connection filter policy</span></span>
 
<span data-ttu-id="8f993-105">大多數的人都有信任的朋友和企業夥伴。</span><span class="sxs-lookup"><span data-stu-id="8f993-105">Most of us have friends and business partners we trust.</span></span> <span data-ttu-id="8f993-106">發現這些人寄送的電子郵件出現在垃圾郵件資料夾或甚至遭到垃圾郵件篩選器整個封鎖，會令人感覺不便。</span><span class="sxs-lookup"><span data-stu-id="8f993-106">It can be frustrating to find email from them in your junk email folder, or even blocked entirely by a spam filter.</span></span> <span data-ttu-id="8f993-107">如果您想要確定不會封鎖從您信任的人員傳送電子郵件，您可用來建立一份允許清單，也就是安全的寄件者] 清單中，連線篩選原則的 IP 位址，您信任。</span><span class="sxs-lookup"><span data-stu-id="8f993-107">If you want to make sure that email sent from people you trust isn't blocked, you can use the connection filter policy to create an Allow list, also known as a safe sender list, of IP addresses that you trust.</span></span> <span data-ttu-id="8f993-108">您也可以建立不想收到電子郵件的封鎖寄件者清單，其中列出一般來自已知濫發垃圾郵件者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8f993-108">You can also create a blocked senders list, which is a list of IP addresses, typically from known spammers, that you don't ever want to receive email messages from.</span></span>
  
 <span data-ttu-id="8f993-109">如需更多套用到整個組織的垃圾郵件設定，請參閱[如何協助確保郵件不會標示為垃圾郵件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[利用 Office 365 垃圾郵件篩選器封鎖電子郵件的垃圾郵件，以避免誤判正常問題](https://go.microsoft.com/fwlink/p/?LinkId=534225)。</span><span class="sxs-lookup"><span data-stu-id="8f993-109">For more spam settings that apply to the whole organization, take a look at [How to help ensure that a message isn't marked as spam](https://go.microsoft.com/fwlink/p/?LinkId=534224) or [Block email spam with the Office 365 spam filter to prevent false negative issues](https://go.microsoft.com/fwlink/p/?LinkId=534225).</span></span> <span data-ttu-id="8f993-110">如果您有系統管理員層級的控制權，且您想要避免誤判或漏報，這些內容很有幫助。</span><span class="sxs-lookup"><span data-stu-id="8f993-110">These are helpful if you have administrator-level control and you want to prevent false positives or false negatives.</span></span>
  
<span data-ttu-id="8f993-111">下列影片顯示連線篩選原則的組態步驟：</span><span class="sxs-lookup"><span data-stu-id="8f993-111">The following video shows the configuration steps for the connection filter policy:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8f993-112">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="8f993-112">What do you need to know before you begin?</span></span>
<span data-ttu-id="8f993-113"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="8f993-113"></span></span>

- <span data-ttu-id="8f993-114">預估完成時間：15 分鐘</span><span class="sxs-lookup"><span data-stu-id="8f993-114">Estimated time to complete: 15 minutes</span></span>
    
- <span data-ttu-id="8f993-115">您必須已獲指派權限，才能執行此程序或這些程序。</span><span class="sxs-lookup"><span data-stu-id="8f993-115">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="8f993-116">若要查看您需要的權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題中的 「 反垃圾郵件 」 項目。</span><span class="sxs-lookup"><span data-stu-id="8f993-116">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
    
- <span data-ttu-id="8f993-117">若要取得寄件者的 IP 位址以允許或封鎖其郵件，您可以檢查郵件的 Internet 標頭。</span><span class="sxs-lookup"><span data-stu-id="8f993-117">To obtain the IP address of the sender whose messages you want to allow or block, you can check the Internet header of the message.</span></span> <span data-ttu-id="8f993-118">如＜[反垃圾郵件訊息標頭](anti-spam-message-headers.md)＞所述尋找 CIP 標頭。</span><span class="sxs-lookup"><span data-stu-id="8f993-118">Look for the CIP header as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="8f993-119">如需如何在各種電子郵件用戶端中檢視郵件標頭資訊，請參閱 <<c0>郵件標頭分析器。</span><span class="sxs-lookup"><span data-stu-id="8f993-119">For information about how to view a message header in various email clients, see [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583).</span></span> 
    
- <span data-ttu-id="8f993-120">從 IP 封鎖清單上的 IP 位址傳送的電子郵件遭到拒絕，未標示為垃圾郵件，並沒有其他的篩選，就會發生。</span><span class="sxs-lookup"><span data-stu-id="8f993-120">Email messages sent from an IP address on the IP Block list are rejected, not marked as spam, and no additional filtering occurs.</span></span>
    
- <span data-ttu-id="8f993-121">下列連線篩選程序也可以透過遠端 PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="8f993-121">The following connection filter procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="8f993-122">使用 [Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) 指令程式可以檢閱您的設定，使用 [Set-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) 則可以編輯連線篩選原則設定。</span><span class="sxs-lookup"><span data-stu-id="8f993-122">Use the [Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) cmdlet to review your settings, and the [Set-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) to edit your connection filter policy settings.</span></span> <span data-ttu-id="8f993-123">若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱[Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。</span><span class="sxs-lookup"><span data-stu-id="8f993-123">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span> <span data-ttu-id="8f993-124">若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="8f993-124">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a><span data-ttu-id="8f993-125">使用 EAC 編輯預設連線篩選原則</span><span class="sxs-lookup"><span data-stu-id="8f993-125">Use the EAC to edit the default connection filter policy</span></span>
<span data-ttu-id="8f993-126"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="8f993-126"></span></span>

<span data-ttu-id="8f993-p107">您可以在 Exchange 系統管理中心 (EAC) 編輯連線篩選原則，以建立 IP 允許清單或 IP 封鎖清單。連線篩選原則設定僅適用於輸入郵件。</span><span class="sxs-lookup"><span data-stu-id="8f993-p107">You create an IP Allow list or IP Block list by editing the connection filter policy in the Exchange admin center (EAC). The connection filter policy settings are applied to inbound messages only.</span></span>
  
1. <span data-ttu-id="8f993-129">在 Exchange 系統管理中心 (EAC)，瀏覽至 **[保護]** \> **[連線篩選器]**，然後連按兩下預設原則。</span><span class="sxs-lookup"><span data-stu-id="8f993-129">In the Exchange admin center (EAC), navigate to **Protection** \> **Connection filter**, and then double-click the default policy.</span></span>
    
2. <span data-ttu-id="8f993-130">Click the **Connection filtering** menu item and then create the lists you want: an IP Allow list, an IP Block list, or both.</span><span class="sxs-lookup"><span data-stu-id="8f993-130">Click the **Connection filtering** menu item and then create the lists you want: an IP Allow list, an IP Block list, or both.</span></span> 
    
    <span data-ttu-id="8f993-p108">若要建立這些清單，請按一下![加入圖示](media/ITPro-EAC-AddIcon.gif)。在後續對話方塊中，指定 IP 位址或位址範圍，然後按一下 **[確定]**。重複此程序來新增其他位址。(新增 IP 位址後，您也可以編輯或移除 IP 位址。)</span><span class="sxs-lookup"><span data-stu-id="8f993-p108">To create these lists, click ![Add Icon](media/ITPro-EAC-AddIcon.gif). In the subsequent dialog box, specify the IP address or address range, and then click **ok**. Repeat this process to add additional addresses. (You can also edit or remove IP addresses after they have been added.)</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="8f993-135">如果您將 IP 位址新增至兩個清單時，會允許來自該 IP 位址傳送的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8f993-135">If you add an IP address to both lists, email sent from that IP address is allowed.</span></span> 

    <span data-ttu-id="8f993-136">指定其中 nnn 是 0 到 255 的數字格式以 IPV4 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8f993-136">Specify IPV4 IP addresses in the format nnn.nnn.nnn.nnn where nnn is a number from 0 to 255.</span></span> <span data-ttu-id="8f993-137">您也可以用 nnn.nnn.nnn.nnn/rr 格式來指定無類別網域間路由選擇 (CIDR) 範圍，其中 rr 是 24 到 32 的數字。</span><span class="sxs-lookup"><span data-stu-id="8f993-137">You can also specify Classless Inter-Domain Routing (CIDR) ranges in the format nnn.nnn.nnn.nnn/rr where rr is a number from 24 to 32.</span></span> <span data-ttu-id="8f993-138">若要指定 24 到 32 以外的範圍，請參閱 [設定 IP 允許清單時的其他考量](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists)。</span><span class="sxs-lookup"><span data-stu-id="8f993-138">To specify ranges outside of the 24 to 32 range, see [Additional considerations when configuring IP Allow lists](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists).</span></span> 

    <span data-ttu-id="8f993-139">您最多可以指定 1273 個項目，一個項目就是單一 IP 位址，或 IP 位址從 /24 至 /32 的 CIDR 範圍。</span><span class="sxs-lookup"><span data-stu-id="8f993-139">You can specify a maximum of 1273 entries, where an entry is either a single IP address or a CIDR range of IP addresses from /24 to /32.</span></span> <span data-ttu-id="8f993-140">如果您正在傳送 TLS 加密訊息 >，IPv6 位址與位址範圍不受支援。</span><span class="sxs-lookup"><span data-stu-id="8f993-140">>  If you're sending TLS-encrypted messages, IPv6 addresses and address ranges are not supported.</span></span> 
  
3. <span data-ttu-id="8f993-141">或者，選取 **[啟用安全清單]** 核取方塊避免某些已知寄件者的電子郵件遺失。</span><span class="sxs-lookup"><span data-stu-id="8f993-141">Optionally, select the **Enable safe list** check box to prevent missing email from certain well-known senders.</span></span> <span data-ttu-id="8f993-142">怎麼做？</span><span class="sxs-lookup"><span data-stu-id="8f993-142">How?</span></span> <span data-ttu-id="8f993-143">Microsoft 會訂閱協力廠商來源的信任寄件者。</span><span class="sxs-lookup"><span data-stu-id="8f993-143">Microsoft subscribes to third-party sources of trusted senders.</span></span> <span data-ttu-id="8f993-144">使用這份安全清單表示不會將信任的寄件者錯誤標記為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="8f993-144">Using this safe list means that these trusted senders aren't mistakenly marked as spam.</span></span> <span data-ttu-id="8f993-145">我們建議您選取此選項，因為它應該減少誤判 （歸類為垃圾郵件的良好郵件） 的數目，您會收到。</span><span class="sxs-lookup"><span data-stu-id="8f993-145">We recommend selecting this option because it should reduce the number of false positives (good mail that's classified as spam) that you receive.</span></span> 
    
4. <span data-ttu-id="8f993-p112">按一下 **[儲存]**。預設原則設定的摘要隨即出現在右側窗格中。</span><span class="sxs-lookup"><span data-stu-id="8f993-p112">Click **save**. A summary of your default policy settings appears in the right pane.</span></span>
    
## <a name="additional-considerations-when-configuring-ip-allow-lists"></a><span data-ttu-id="8f993-148">設定 IP 允許清單時的其他考量</span><span class="sxs-lookup"><span data-stu-id="8f993-148">Additional considerations when configuring IP Allow lists</span></span>
<span data-ttu-id="8f993-149"><a name="bkmk_addtionalconsiderationswhenconfiguringipallowlists"> </a></span><span class="sxs-lookup"><span data-stu-id="8f993-149"></span></span>

<span data-ttu-id="8f993-150">以下是設定 IP 允許清單時需要考慮或應該注意的其他事項。</span><span class="sxs-lookup"><span data-stu-id="8f993-150">The following are additional considerations you may want to consider or that you should be aware of when configuring an IP Allow list.</span></span>
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a><span data-ttu-id="8f993-151">指定超出建議範圍的 CIDR 範圍</span><span class="sxs-lookup"><span data-stu-id="8f993-151">Specifying a CIDR range that falls outside of the recommended range</span></span>

<span data-ttu-id="8f993-152">若要指定 /23 從/1 CIDR IP 位址範圍，您必須建立郵件流程規則的運作上設定垃圾郵件信賴等級 (SCL) 的 IP 位址範圍**略過垃圾郵件篩選**（亦即從收到此 IP 位址範圍內的所有郵件都都會設定為 「 非垃圾郵件 」） 和任何其他的篩選服務執行)。</span><span class="sxs-lookup"><span data-stu-id="8f993-152">To specify a CIDR IP address range from /1 to /23, you must create a mail flow rule that operates on the IP address range that sets the spam confidence level (SCL) to **Bypass spam filtering** (meaning that all messages received from within this IP address range are set to "not spam") and no additional filtering is performed by the service).</span></span> <span data-ttu-id="8f993-153">However, if any of these IP addresses appear on any of Microsoft's proprietary block lists or on any of our third-party block lists, these messages will still be blocked.</span><span class="sxs-lookup"><span data-stu-id="8f993-153">However, if any of these IP addresses appear on any of Microsoft's proprietary block lists or on any of our third-party block lists, these messages will still be blocked.</span></span> <span data-ttu-id="8f993-154">因此強烈建議您使用/24 至/32 的 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="8f993-154">It is therefore strongly recommended that you use the /24 to /32 IP address range.</span></span> 
  
<span data-ttu-id="8f993-155">若要建立此郵件流程規則，請執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="8f993-155">To create this mail flow rule, perform the following steps.</span></span>
  
1. <span data-ttu-id="8f993-156">在 EAC 中，瀏覽至 **[郵件流程]** \> **[規則]**。</span><span class="sxs-lookup"><span data-stu-id="8f993-156">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="8f993-157">按一下 ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 **[建立新的規則]**。</span><span class="sxs-lookup"><span data-stu-id="8f993-157">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="8f993-158">命名規則，然後按一下 **[更多選項]**。</span><span class="sxs-lookup"><span data-stu-id="8f993-158">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="8f993-159">在 **[套用此規則情況]** 下，選取 **[寄件者]**，然後選擇 **[IP 位址在任何這些範圍中或完全符合]**。</span><span class="sxs-lookup"><span data-stu-id="8f993-159">Under **Apply this rule if**, select **The sender** and then choose **IP address is in any of these ranges or exactly matches**.</span></span>
    
5. <span data-ttu-id="8f993-160">在 [**指定 IP 位址**，請指定 IP 位址範圍，按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="8f993-160">In the **specify IP addresses**, specify the IP address range, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then click **ok**.</span></span>
    
6. <span data-ttu-id="8f993-p114">在 **[執行下列動作]** 方塊下，選擇 **[修改訊息屬性]**，再選擇 **[設定垃圾郵件信賴等級 (SCL)]** 來設定動作。在 **[指定 SCL]** 方塊中，選取 **[略過垃圾郵件篩選]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8f993-p114">Under **Do the following** box, set the action by choosing **Modify the message properties** and then **set the spam confidence level (SCL)**. In the **specify SCL** box, select **Bypass spam filtering**, and click **ok**.</span></span>
    
7. <span data-ttu-id="8f993-163">您也可以視需要選取稽核規則、測試規則、在特定期間啟動規則等等選項。</span><span class="sxs-lookup"><span data-stu-id="8f993-163">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="8f993-164">施行規則之前，建議先測試規則一段時間。</span><span class="sxs-lookup"><span data-stu-id="8f993-164">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="8f993-165">[程序的郵件流程規則在 Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)包含這些選項的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8f993-165">[Procedures for mail flow rules in Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) contains more information about these selections.</span></span> 
    
8. <span data-ttu-id="8f993-166">按一下 [**儲存**] 以儲存規則。</span><span class="sxs-lookup"><span data-stu-id="8f993-166">Click **save** to save the rule.</span></span> <span data-ttu-id="8f993-167">此規則會出現在規則清單。</span><span class="sxs-lookup"><span data-stu-id="8f993-167">The rule appears in your list of rules.</span></span> 
    
<span data-ttu-id="8f993-168">建立並強制執行規則後，此服務會略過垃圾郵件篩選，以便您所指定的 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="8f993-168">After you create and enforce the rule, the service bypasses spam filtering for the IP address range you specified.</span></span>
  
### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a><span data-ttu-id="8f993-169">針對特定網域設定 IP 允許清單例外狀況</span><span class="sxs-lookup"><span data-stu-id="8f993-169">Scoping an IP Allow list exception for a specific domain</span></span>

<span data-ttu-id="8f993-170">一般而言，建議將您認為安全的所有網域的 IP 位址 (或 IP 位址範圍) 新增至 IP 允許清單。</span><span class="sxs-lookup"><span data-stu-id="8f993-170">In general, we recommend that you add the IP addresses (or IP address ranges) for all your domains that you consider safe to the IP Allow list.</span></span> <span data-ttu-id="8f993-171">不過，如果您不想要套用至所有網域 IP 允許清單項目，您可以建立排除特定網域的郵件流程規則 （也稱為傳輸規則）。</span><span class="sxs-lookup"><span data-stu-id="8f993-171">However, if you don't want your IP Allow List entry to apply to all your domains, you can create a mail flow rule (also known as a transport rule) that excepts specific domains.</span></span> 
  
<span data-ttu-id="8f993-172">例如，假設您有三個網域：ContosoA.com、ContosoB.com 和 ContosoC.com，而您想要新增 IP 位址 (為了簡單起見，我們用 1.2.3.4)，並僅針對網域 ContosoB.com 來略過篩選。</span><span class="sxs-lookup"><span data-stu-id="8f993-172">For example, let's say you have three domains: ContosoA.com, ContosoB.com, and ContosoC.com, and you want to add the IP address (for simplicity's sake, let's use 1.2.3.4) and skip filtering only for domain ContosoB.com.</span></span> <span data-ttu-id="8f993-173">您可以建立 1.2.3.4 的 IP 允許清單，以針對所有網域將垃圾郵件信賴等級 (SCL) 設定為 -1 (表示歸類為非垃圾郵件)。</span><span class="sxs-lookup"><span data-stu-id="8f993-173">You would create an IP Allow list for 1.2.3.4, which sets the spam confidence level (SCL) to -1 (meaning it is classified as non-spam) for all domains.</span></span> <span data-ttu-id="8f993-174">然後，您可以建立郵件流程規則，將以針對 ContosoB.com 以外的所有網域的 SCL 設定為 0。</span><span class="sxs-lookup"><span data-stu-id="8f993-174">You can then create a mail flow rule that sets the SCL for all domains except ContosoB.com to 0.</span></span> <span data-ttu-id="8f993-175">這會導致針對與此 IP 位址相關聯的所有網域 (在規則中列為例外的 ContosoB.com 除外) 來重新掃描郵件。</span><span class="sxs-lookup"><span data-stu-id="8f993-175">This results in the message being rescanned for all domains associated with the IP address except for ContosoB.com which is the domain listed as the exception in the rule.</span></span> <span data-ttu-id="8f993-176">ContosoB.com 的 SCL 仍為 -1 (表示略過篩選)，然而 ContosoA.com 和 ContosoC.com 的 SCL 為 0 (表示將由內容篩選器進行重複掃描)。</span><span class="sxs-lookup"><span data-stu-id="8f993-176">ContosoB.com still has an SCL of -1 which means skip filtering, whereas ContosoA.com and ContosoC.com have SCLs of 0, meaning they will be rescanned by the content filter.</span></span>
  
<span data-ttu-id="8f993-177">若要執行此動作，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="8f993-177">To do this, perform the following steps:</span></span>
  
1. <span data-ttu-id="8f993-178">在 EAC 中，瀏覽至 **[郵件流程]** \> **[規則]**。</span><span class="sxs-lookup"><span data-stu-id="8f993-178">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="8f993-179">按一下 ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 **[建立新的規則]**。</span><span class="sxs-lookup"><span data-stu-id="8f993-179">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="8f993-180">命名規則，然後按一下 **[更多選項]**。</span><span class="sxs-lookup"><span data-stu-id="8f993-180">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="8f993-181">在 **[套用此規則情況]** 下，選取 **[寄件者]**，然後選擇 **[IP 位址在任何這些範圍中或完全符合]**。</span><span class="sxs-lookup"><span data-stu-id="8f993-181">Under **Apply this rule if**, select **The sender** and then choose **IP address is in any of these ranges or exactly matches**.</span></span>
    
5. <span data-ttu-id="8f993-182">在 [**指定 IP 位址**] 方塊中，指定的 IP 位址或 IP 位址範圍，您輸入的 IP 允許清單中，按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="8f993-182">In the **specify IP addresses** box, specify the IP address or IP address range you entered in the IP Allow list, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then click **ok**.</span></span>
    
6. <span data-ttu-id="8f993-p119">在 **[執行下列動作]** 下，選擇 **[修改訊息屬性]**，再選擇 **[設定垃圾郵件信賴等級 (SCL)]** 來設定動作。在 **[指定 SCL]** 方塊中，選取 **[0]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8f993-p119">Under **Do the following**, set the action by choosing **Modify the message properties** and then **set the spam confidence level (SCL)**. In the **specify SCL** box, select **0**, and click **ok**.</span></span>
    
7. <span data-ttu-id="8f993-185">按一下 **[新增例外狀況]**，在 **[除非]** 下，選取 **[寄件者]**，然後選擇 **[網域是]**。</span><span class="sxs-lookup"><span data-stu-id="8f993-185">Click **add exception**, and under **Except if**, select **The sender** and choose **domain is**.</span></span> 
    
8. <span data-ttu-id="8f993-186">在 **[指定網域]** 方塊中，輸入您要略過垃圾郵件篩選的網域，例如 **contosob.com**。</span><span class="sxs-lookup"><span data-stu-id="8f993-186">In the **specify domain** box, enter the domain for which you want to bypass spam filtering, such as **contosob.com**.</span></span> <span data-ttu-id="8f993-187">按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)將其移至片語清單。</span><span class="sxs-lookup"><span data-stu-id="8f993-187">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) to move it to the list of phrases.</span></span> <span data-ttu-id="8f993-188">如果要新增其他網域當作例外狀況，請重複此步驟，完成時按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8f993-188">Repeat this step if you want to add additional domains as exceptions, and click **ok** when you are finished.</span></span> 
    
9. <span data-ttu-id="8f993-189">您也可以視需要選取稽核規則、測試規則、在特定期間啟動規則等等選項。</span><span class="sxs-lookup"><span data-stu-id="8f993-189">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="8f993-190">施行規則之前，建議先測試規則一段時間。</span><span class="sxs-lookup"><span data-stu-id="8f993-190">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="8f993-191">[程序的郵件流程規則在 Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)包含這些選項的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8f993-191">[Procedures for mail flow rules in Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) contains more information about these selections.</span></span> 
    
10. <span data-ttu-id="8f993-192">按一下 [**儲存**] 以儲存規則。</span><span class="sxs-lookup"><span data-stu-id="8f993-192">Click **save** to save the rule.</span></span> <span data-ttu-id="8f993-193">此規則會出現在規則清單。</span><span class="sxs-lookup"><span data-stu-id="8f993-193">The rule appears in your list of rules.</span></span> 
    
<span data-ttu-id="8f993-194">建立並強制執行規則後，系統就只會針對您輸入的例外網域，對您指定的 IP 位址或 IP 位址範圍略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="8f993-194">After you create and enforce the rule, spam filtering for the IP address or IP address range you specified is bypassed only for the domain exception you entered.</span></span>
  
## <a name="new-to-office-365"></a><span data-ttu-id="8f993-195">第一次使用 Office 365？</span><span class="sxs-lookup"><span data-stu-id="8f993-195">New to Office 365?</span></span>
<span data-ttu-id="8f993-196"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="8f993-196"></span></span>

||
|:-----|
|<span data-ttu-id="8f993-p123">![LinkedIn Learning 的短圖示](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **初次使用 Office 365？**         探索 LinkedIn Learning 提供的 **Office 365 admins and IT pros** 免費影片課程。</span><span class="sxs-lookup"><span data-stu-id="8f993-p123">![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span> |
   
## <a name="for-more-information"></a><span data-ttu-id="8f993-199">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="8f993-199">For more information</span></span>
<span data-ttu-id="8f993-200"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="8f993-200"></span></span>

[<span data-ttu-id="8f993-201">安全寄件者和封鎖的寄件者會列出在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8f993-201">Safe sender and blocked sender lists in Exchange Online</span></span>](safe-sender-and-blocked-sender-lists-faq.md)
  
[<span data-ttu-id="8f993-202">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="8f993-202">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="8f993-203">設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="8f993-203">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="8f993-204">如何協助確保郵件不會標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="8f993-204">How to help ensure that a message isn't marked as spam</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[<span data-ttu-id="8f993-205">利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件以避免誤判正常</span><span class="sxs-lookup"><span data-stu-id="8f993-205">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

