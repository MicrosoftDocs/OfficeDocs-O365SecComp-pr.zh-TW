---
title: 使用郵件流程規則來設定 Exchange Online Protection 中篩選大量電子郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
description: 系統管理員可以了解如何使用 Exchange Online Protection 中的郵件流程規則的大量電子郵件篩選。
ms.openlocfilehash: d308439b5c26569f85eb62ddee6f01786d2998b9
ms.sourcegitcommit: 32cb896aef370764ec6e8f8278ebaf16f1c5ff37
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30123914"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a><span data-ttu-id="bdcd5-103">使用郵件流程規則來設定 Exchange Online Protection 中篩選大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="bdcd5-103">Use mail flow rules to configure bulk email filtering in Exchange Online Protection</span></span>

<span data-ttu-id="bdcd5-p101">您可以設定為使用預設的垃圾郵件的內容篩選原則的垃圾郵件和大量電子郵件的全公司的內容篩選器。如何設定內容篩選原則查看[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)和[Set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) 。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-p101">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies. Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) on how to set the content filter policies.</span></span> 
  
<span data-ttu-id="bdcd5-p102">如果您想要更多選項] 以篩選大量郵件，您可以建立搜尋的文字模式或片語經常找到大量電子郵件中的郵件流程規則 （也稱為傳輸規則）。包含下列特性任何訊息將標記為垃圾郵件。使用這些規則可以協助減少組織會收到不想要的大量電子郵件。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-p102">If you want to more options to filter bulk messages, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases frequently found in bulk emails. Any message containing these characteristics will be marked as spam. Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bdcd5-109">建立郵件流程規則記載本主題之前，建議您先閱讀[垃圾郵件與大量電子郵件之間的差異為何吗？](what-s-the-difference-between-junk-email-and-bulk-email.md)和[大量抱怨層級的值](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-109">Before creating the mail flow rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span><br><span data-ttu-id="bdcd5-p103">下列程序會將郵件標示為整個組織的垃圾郵件。不過，您可以新增至這些規則僅適用於您組織中特定收件者的另一個條件。如此一來，篩選設定可以套用到高度目標的一些使用者不積極的大量電子郵件時您使用者 （多半要取得其簽署向上的大量電子郵件） 的其餘部分不會影響。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-p103"> The following procedures mark a message as spam for your entire organization. However, you can add another condition to apply these rules only to specific recipients in your organization. This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span> 
  
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="bdcd5-113">建立篩選根據文字模式的大量電子郵件的郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="bdcd5-113">Create a mail flow rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="bdcd5-114">在Exchange 系統管理中心 (EAC)，請移至 [ **郵件流程**\> **規則**。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-114">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="bdcd5-115">按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 [**建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-115">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="bdcd5-116">指定規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-116">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="bdcd5-p104">按一下 [**更多選項]**。在**套用此規則情況**] 下選取 [**在主旨或本文** \> **主旨或內文符合這些文字模式**。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-p104">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>
    
5. <span data-ttu-id="bdcd5-119">在 [**指定單字或片語**] 對話方塊中，新增下列的規則運算式通常位於第一次大量電子郵件和完成時按一下 [**確定]** ：</span><span class="sxs-lookup"><span data-stu-id="bdcd5-119">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - `If you are unable to view the content of this email\, please`
    
   - `\>(safe )?unsubscribe( here)?\</a\>`
    
   - `If you do not wish to receive further communications like this\, please`
    
   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
    
   - `To stop receiving these+emails\:http\://`
    
   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
    
   - `no longer (wish )?(to )?(be sent|receive) w+ email`
    
   - `If you are unable to view the content of this email\, please click here`
    
   - `To ensure you receive (your daily deals|our e-?mails)\, add`
    
   - `If you no longer wish to receive these emails`
    
   - `to change your (subscription preferences|preferences or unsubscribe)`
    
   - `click (here to|the) unsubscribe`
    
   <span data-ttu-id="bdcd5-p105">上述清單不是大量電子郵件 ； 中找到的規則運算式的詳盡集更多可以新增或移除視。不過，它是很好的起點。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-p105">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span><br><span data-ttu-id="bdcd5-p106">搜尋字詞或主旨中的文字模式或其他郵件中的標頭欄位發生已從 MIME 內容傳輸編碼方法用來傳輸 ASCII 文字中的 SMTP 伺服器之間的二進位郵件解碼*之後*郵件。您無法搜尋的原始使用條件或例外狀況 (通常 Base64) 編碼的主旨或其他訊息中的標頭欄位的值。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-p106">The search for words or text patterns in the subject or other header fields in the message occurs  *after*  the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span> 
    
6. <span data-ttu-id="bdcd5-124">在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-124">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="bdcd5-125">在 [**指定 SCL** ] 對話方塊中，將 SCL 設定為**5**、 **6**或**9**，並按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-125">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="bdcd5-p107">將 SCL 設定為 5 或 6 採用的**垃圾郵件**動作、 時設定為 9 SCL 採取**高信賴垃圾郵件**動作，設定的內容篩選原則。此服務會執行巨集指令中的內容篩選原則設定。預設動作是要將郵件傳遞給收件者的垃圾郵件] 資料夾，但是您可以設定不同的動作，[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)所述。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-p107">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   <span data-ttu-id="bdcd5-129">如果您已設定的動作是要隔離郵件而不是將其傳送給收件者的垃圾郵件] 資料夾，就會傳送訊息到管理員隔離如郵件流程規則比對及它將無法使用使用者垃圾郵件隔離區中或透過使用者垃圾郵件通知。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-129">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="bdcd5-130">如需服務中各 SCL 值的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-130">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="bdcd5-131">儲存規則。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-131">Save the rule.</span></span>
    
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="bdcd5-132">建立篩選根據片語的大量電子郵件的郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="bdcd5-132">Create a mail flow rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="bdcd5-133">在 EAC 中，移至 [**郵件流程** \> **規則**。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-133">In the EAC, go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="bdcd5-134">按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 [**建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-134">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="bdcd5-135">指定規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-135">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="bdcd5-p108">按一下 [**更多選項]**。在**套用此規則情況**] 下選取 [**在主旨或本文** \> **主旨或內文中包含任何這些字詞**。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-p108">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>
    
5. <span data-ttu-id="bdcd5-138">在 [**指定單字或片語**] 對話方塊中，新增下列常見於大量電子郵件，一次一個中然後在完成時按一下 [**確定]** ：</span><span class="sxs-lookup"><span data-stu-id="bdcd5-138">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - `to change your preferences or unsubscribe`
    
   - `Modify email preferences or unsubscribe`
    
   - `This is a promotional email`
    
   - `You are receiving this email because you requested a subscription`
    
   - `click here to unsubscribe`
    
   - `You have received this email because you are subscribed`
    
   - `If you no longer wish to receive our email newsletter`
    
   - `to unsubscribe from this newsletter`
    
   - `If you have trouble viewing this email`
    
   - `This is an advertisement`
    
   - `you would like to unsubscribe or change your`
    
   - `view this email as a webpage`
    
   - `You are receiving this email because you are subscribed`
    
   <span data-ttu-id="bdcd5-p109">這份清單不是大量電子郵件 ； 中找到的片語的詳盡集更多可以新增或移除視。不過，它是很好的起點。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-p109">This list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
6. <span data-ttu-id="bdcd5-141">在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-141">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="bdcd5-142">在 [**指定 SCL** ] 對話方塊中，將 SCL 設定為**5**、 **6**或**9**，並按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-142">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="bdcd5-p110">將 SCL 設定為 5 或 6 採用的**垃圾郵件**動作、 時設定為 9 SCL 採取**高信賴垃圾郵件**動作，設定的內容篩選原則。此服務會執行巨集指令中的內容篩選原則設定。預設動作是要將郵件傳遞給收件者的垃圾郵件] 資料夾，但是您可以設定不同的動作，[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)所述。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-p110">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   <span data-ttu-id="bdcd5-146">如果您已設定的動作是要隔離郵件而不是將其傳送給收件者的垃圾郵件] 資料夾，就會傳送訊息到管理員隔離如郵件流程規則比對及它將無法使用使用者垃圾郵件隔離區中或透過使用者垃圾郵件通知。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-146">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="bdcd5-147">如需服務中各 SCL 值的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-147">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="bdcd5-148">儲存規則。</span><span class="sxs-lookup"><span data-stu-id="bdcd5-148">Save the rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="bdcd5-149">相關資訊</span><span class="sxs-lookup"><span data-stu-id="bdcd5-149">For more information</span></span>

[<span data-ttu-id="bdcd5-150">垃圾郵件和大量電子郵件有什麼不同?</span><span class="sxs-lookup"><span data-stu-id="bdcd5-150">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)

[<span data-ttu-id="bdcd5-151">大量抱怨層級值</span><span class="sxs-lookup"><span data-stu-id="bdcd5-151">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)

[<span data-ttu-id="bdcd5-152">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="bdcd5-152">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="bdcd5-153">進階垃圾郵件篩選選項</span><span class="sxs-lookup"><span data-stu-id="bdcd5-153">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
