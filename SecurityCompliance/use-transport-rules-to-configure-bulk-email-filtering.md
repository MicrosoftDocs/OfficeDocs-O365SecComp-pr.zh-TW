---
title: 使用傳輸規則來設定大量電子郵件篩選
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
description: 您可以設定為使用預設的垃圾郵件的內容篩選原則的垃圾郵件和大量電子郵件的全公司的內容篩選器。請參閱設定垃圾郵件篩選器原則和 Set-hostedcontentfilterpolicy 如何設定內容篩選原則。
ms.openlocfilehash: f72fa5cc50ab6aa5447e3af9fabc365457c82973
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027680"
---
# <a name="use-transport-rules-to-configure-bulk-email-filtering"></a><span data-ttu-id="265ba-104">使用傳輸規則來設定大量電子郵件篩選</span><span class="sxs-lookup"><span data-stu-id="265ba-104">Use transport rules to configure bulk email filtering</span></span>

<span data-ttu-id="265ba-p102">您可以設定為使用預設的垃圾郵件的內容篩選原則的垃圾郵件和大量電子郵件的全公司的內容篩選器。如何設定內容篩選原則查看[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)和[Set-hostedcontentfilterpolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="265ba-p102">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies. Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) on how to set the content filter policies.</span></span> 
  
<span data-ttu-id="265ba-p103">如果您想要更多選項] 以篩選大量郵件，您可以建立 Exchange 傳輸規則來搜尋的文字模式或片語經常大量電子郵件中找到。包含下列特性任何訊息將標記為垃圾郵件。使用這些規則可以協助減少組織會收到不想要的大量電子郵件。</span><span class="sxs-lookup"><span data-stu-id="265ba-p103">If you want to more options to filter bulk messages, you can create Exchange Transport rules to search for text patterns or phrases frequently found in bulk emails. Any message containing these characteristics will be marked as spam. Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>
  
> [!NOTE]
> <span data-ttu-id="265ba-110">建立傳輸規則記載本主題之前，建議您先閱讀[垃圾郵件與大量電子郵件之間的差異為何吗？](what-s-the-difference-between-junk-email-and-bulk-email.md)和[大量抱怨層級的值](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="265ba-110">Before creating the Transport rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="265ba-p104">下列程序會將郵件標示為整個組織的垃圾郵件。不過，您可以新增至這些規則僅適用於您組織中特定收件者的另一個條件。如此一來，篩選設定可以套用到高度目標的一些使用者不積極的大量電子郵件時您使用者 （多半要取得其簽署向上的大量電子郵件） 的其餘部分不會影響。</span><span class="sxs-lookup"><span data-stu-id="265ba-p104">The following procedures mark a message as spam for your entire organization. However, you can add another condition to apply these rules only to specific recipients in your organization. This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span> 
  
### <a name="create-an-exchange-transport-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="265ba-114">建立 Exchange 傳輸規則，以根據文字模式篩選大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="265ba-114">Create an Exchange Transport rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="265ba-115">在Exchange 系統管理中心 (EAC)，請移至 [ **郵件流程**\> **規則**。</span><span class="sxs-lookup"><span data-stu-id="265ba-115">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="265ba-116">按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.png)，然後選取 [**建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="265ba-116">Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="265ba-117">指定規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="265ba-117">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="265ba-p105">按一下 [**更多選項]**。在**套用此規則情況**] 下選取 [**在主旨或本文** \> **主旨或內文符合這些文字模式**。</span><span class="sxs-lookup"><span data-stu-id="265ba-p105">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>
    
5. <span data-ttu-id="265ba-120">在 [**指定單字或片語**] 對話方塊中，新增下列的規則運算式通常位於第一次大量電子郵件和完成時按一下 [**確定]** ：</span><span class="sxs-lookup"><span data-stu-id="265ba-120">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
  - <span data-ttu-id="265ba-121">如果您是無法檢視此電子郵件的內容\,請</span><span class="sxs-lookup"><span data-stu-id="265ba-121">If you are unable to view the content of this email\, please</span></span>
    
  - <span data-ttu-id="265ba-122">\\>(安全)?取消訂閱 (這裡)?\\</a\\></span><span class="sxs-lookup"><span data-stu-id="265ba-122">\\>(safe )?unsubscribe( here)?\\</a\\></span></span>
    
  - <span data-ttu-id="265ba-123">如果您不想要接收像這樣的進一步通訊\,請</span><span class="sxs-lookup"><span data-stu-id="265ba-123">If you do not wish to receive further communications like this\, please</span></span>
    
  - <span data-ttu-id="265ba-p106">\\<img height\="?1"? width\="?1"? src\=.?http\://</span><span class="sxs-lookup"><span data-stu-id="265ba-p106">\\<img height\="?1"? width\="?1"? src\=.?http\://</span></span>
    
  - <span data-ttu-id="265ba-127">若要停止接收這些電子郵件\:http\://</span><span class="sxs-lookup"><span data-stu-id="265ba-127">To stop receiving these\s+emails\:http\://</span></span>
    
  - <span data-ttu-id="265ba-128">若要取消訂閱 \w+ (e\-?letter|e?-?mail|newsletter)</span><span class="sxs-lookup"><span data-stu-id="265ba-128">To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)</span></span>
    
  - <span data-ttu-id="265ba-129">不再 (想)?(要)?(傳送|接收) \w+ 電子郵件</span><span class="sxs-lookup"><span data-stu-id="265ba-129">no longer (wish )?(to )?(be sent|receive) \w+ email</span></span>
    
  - <span data-ttu-id="265ba-130">如果您是無法檢視此電子郵件的內容\,請按一下這裡</span><span class="sxs-lookup"><span data-stu-id="265ba-130">If you are unable to view the content of this email\, please click here</span></span>
    
  - <span data-ttu-id="265ba-131">若要確保您收到 (每日的處理 | 我們 e ?mails)\,新增</span><span class="sxs-lookup"><span data-stu-id="265ba-131">To ensure you receive (your daily deals|our e-?mails)\, add</span></span>
    
  - <span data-ttu-id="265ba-132">如果您不想要再收到這些電子郵件</span><span class="sxs-lookup"><span data-stu-id="265ba-132">If you no longer wish to receive these emails</span></span>
    
  - <span data-ttu-id="265ba-133">變更您的 (訂閱喜好設定或取消訂閱)</span><span class="sxs-lookup"><span data-stu-id="265ba-133">to change your (subscription preferences|preferences or unsubscribe)</span></span>
    
  - <span data-ttu-id="265ba-134">按一下 (這裡) 以取消訂閱</span><span class="sxs-lookup"><span data-stu-id="265ba-134">click (here to|the) unsubscribe</span></span>
    
    <span data-ttu-id="265ba-135">**附註**：</span><span class="sxs-lookup"><span data-stu-id="265ba-135">**Notes**:</span></span>
    
  - <span data-ttu-id="265ba-p107">上述清單不是大量電子郵件 ； 中找到的規則運算式的詳盡集更多可以新增或移除視。不過，它是很好的起點。</span><span class="sxs-lookup"><span data-stu-id="265ba-p107">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
  - <span data-ttu-id="265ba-p108">搜尋字詞或主旨中的文字模式或其他郵件中的標頭欄位發生已從 MIME 內容傳輸編碼方法用來傳輸 ASCII 文字中的 SMTP 伺服器之間的二進位郵件解碼*之後*郵件。您無法搜尋的原始使用條件或例外狀況 (通常 Base64) 編碼的主旨或其他訊息中的標頭欄位的值。</span><span class="sxs-lookup"><span data-stu-id="265ba-p108">The search for words or text patterns in the subject or other header fields in the message occurs  *after*  the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span> 
    
6. <span data-ttu-id="265ba-140">在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。</span><span class="sxs-lookup"><span data-stu-id="265ba-140">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="265ba-141">在 [**指定 SCL** ] 對話方塊中，將 SCL 設定為**5**、 **6**或**9**，並按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="265ba-141">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
    <span data-ttu-id="265ba-p109">將 SCL 設定為 5 或 6 採用的**垃圾郵件**動作、 時設定為 9 SCL 採取**高信賴垃圾郵件**動作，設定的內容篩選原則。此服務會執行巨集指令中的內容篩選原則設定。預設動作是要將郵件傳遞給收件者的垃圾郵件] 資料夾，但是您可以設定不同的動作，[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)所述。</span><span class="sxs-lookup"><span data-stu-id="265ba-p109">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="265ba-145">如果您已設定的動作是要隔離郵件而不是將其傳送給收件者的垃圾郵件] 資料夾，就會傳送訊息到管理員隔離為符合傳輸規則，以及它將無法使用使用者垃圾郵件隔離區中或透過使用者垃圾郵件通知。</span><span class="sxs-lookup"><span data-stu-id="265ba-145">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a transport rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
    <span data-ttu-id="265ba-146">如需服務中各 SCL 值的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="265ba-146">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="265ba-147">儲存規則。</span><span class="sxs-lookup"><span data-stu-id="265ba-147">Save the rule.</span></span>
    
### <a name="create-an-exchange-transport-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="265ba-148">建立 Exchange 傳輸規則，以根據片語篩選大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="265ba-148">Create an Exchange Transport rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="265ba-149">在 EAC 中，移至 [**郵件流程** \> **規則**。</span><span class="sxs-lookup"><span data-stu-id="265ba-149">In the EAC, go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="265ba-150">按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.png)，然後選取 [**建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="265ba-150">Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="265ba-151">指定規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="265ba-151">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="265ba-p110">按一下 [**更多選項]**。在**套用此規則情況**] 下選取 [**在主旨或本文** \> **主旨或內文中包含任何這些字詞**。</span><span class="sxs-lookup"><span data-stu-id="265ba-p110">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>
    
5. <span data-ttu-id="265ba-154">在 [**指定單字或片語**] 對話方塊中，新增下列常見於大量電子郵件，一次一個中然後在完成時按一下 [**確定]** ：</span><span class="sxs-lookup"><span data-stu-id="265ba-154">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
  - <span data-ttu-id="265ba-155">變更您的喜好設定或取消訂閱</span><span class="sxs-lookup"><span data-stu-id="265ba-155">to change your preferences or unsubscribe</span></span>
    
  - <span data-ttu-id="265ba-156">修改電子郵件喜好設定或取消訂閱</span><span class="sxs-lookup"><span data-stu-id="265ba-156">Modify email preferences or unsubscribe</span></span>
    
  - <span data-ttu-id="265ba-157">這是促銷電子郵件</span><span class="sxs-lookup"><span data-stu-id="265ba-157">This is a promotional email</span></span>
    
  - <span data-ttu-id="265ba-158">您會收到此電子郵件是因為您已要求訂閱</span><span class="sxs-lookup"><span data-stu-id="265ba-158">You are receiving this email because you requested a subscription</span></span>
    
  - <span data-ttu-id="265ba-159">按一下這裡以取消訂閱</span><span class="sxs-lookup"><span data-stu-id="265ba-159">click here to unsubscribe</span></span>
    
  - <span data-ttu-id="265ba-160">您會收到此電子郵件是因為您已訂閱</span><span class="sxs-lookup"><span data-stu-id="265ba-160">You have received this email because you are subscribed</span></span>
    
  - <span data-ttu-id="265ba-161">如果您不想要再收到我們的電子報</span><span class="sxs-lookup"><span data-stu-id="265ba-161">If you no longer wish to receive our email newsletter</span></span>
    
  - <span data-ttu-id="265ba-162">取消訂閱此電子報</span><span class="sxs-lookup"><span data-stu-id="265ba-162">to unsubscribe from this newsletter</span></span>
    
  - <span data-ttu-id="265ba-163">如果您無法檢視此電子郵件</span><span class="sxs-lookup"><span data-stu-id="265ba-163">If you have trouble viewing this email</span></span>
    
  - <span data-ttu-id="265ba-164">這是廣告</span><span class="sxs-lookup"><span data-stu-id="265ba-164">This is an advertisement</span></span>
    
  - <span data-ttu-id="265ba-165">您想要取消訂閱或變更您的</span><span class="sxs-lookup"><span data-stu-id="265ba-165">you would like to unsubscribe or change your</span></span>
    
  - <span data-ttu-id="265ba-166">檢視此電子郵件的網頁版</span><span class="sxs-lookup"><span data-stu-id="265ba-166">view this email as a webpage</span></span>
    
  - <span data-ttu-id="265ba-167">您會收到此電子郵件是因為您已訂閱</span><span class="sxs-lookup"><span data-stu-id="265ba-167">You are receiving this email because you are subscribed</span></span>
    
    <span data-ttu-id="265ba-p111">**請注意**： 再次這份清單不是大量電子郵件 ； 中找到的片語的詳盡集更多可以新增或移除視。不過，它是很好的起點。</span><span class="sxs-lookup"><span data-stu-id="265ba-p111">**Note**: Once again, this list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
6. <span data-ttu-id="265ba-170">在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。</span><span class="sxs-lookup"><span data-stu-id="265ba-170">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="265ba-171">在 [**指定 SCL** ] 對話方塊中，將 SCL 設定為**5**、 **6**或**9**，並按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="265ba-171">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
    <span data-ttu-id="265ba-p112">將 SCL 設定為 5 或 6 採用的**垃圾郵件**動作、 時設定為 9 SCL 採取**高信賴垃圾郵件**動作，設定的內容篩選原則。此服務會執行巨集指令中的內容篩選原則設定。預設動作是要將郵件傳遞給收件者的垃圾郵件] 資料夾，但是您可以設定不同的動作，[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)所述。</span><span class="sxs-lookup"><span data-stu-id="265ba-p112">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="265ba-175">如果您已設定的動作是要隔離郵件而不是將其傳送給收件者的垃圾郵件] 資料夾，就會傳送訊息到管理員隔離為符合傳輸規則，以及它將無法使用使用者垃圾郵件隔離區中或透過使用者垃圾郵件通知。</span><span class="sxs-lookup"><span data-stu-id="265ba-175">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a transport rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
    <span data-ttu-id="265ba-176">如需服務中各 SCL 值的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="265ba-176">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="265ba-177">儲存規則。</span><span class="sxs-lookup"><span data-stu-id="265ba-177">Save the rule.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="265ba-178">相關資訊</span><span class="sxs-lookup"><span data-stu-id="265ba-178">For more information</span></span>

[<span data-ttu-id="265ba-179">垃圾郵件和大量電子郵件有什麼不同?</span><span class="sxs-lookup"><span data-stu-id="265ba-179">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)
  
[<span data-ttu-id="265ba-180">大量抱怨層級值</span><span class="sxs-lookup"><span data-stu-id="265ba-180">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)
  
[<span data-ttu-id="265ba-181">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="265ba-181">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="265ba-182">進階垃圾郵件篩選選項</span><span class="sxs-lookup"><span data-stu-id="265ba-182">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
  

