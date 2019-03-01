---
title: 使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 系統管理員可以了解如何在 Exchange Online Protection 設定郵件的 SCL。
ms.openlocfilehash: 48569087fe8455dbb5500add435430ec8e78ea30
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341344"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="c806d-103">使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)</span><span class="sxs-lookup"><span data-stu-id="c806d-103">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="c806d-p101">您可以建立郵件流程規則 （也稱為傳輸規則），設定電子郵件的垃圾郵件信賴等級 (SCL)。SCL 為量值的方式可能郵件是垃圾郵件。垃圾郵件是來路不明 （和通常不想要） 的電子郵件訊息。服務上根據其 SCL 分級的郵件採取不同的動作。例如，您可能想要略過垃圾郵件內容篩選的郵件，因為您信任從同事內部傳送的郵件不是垃圾郵件傳送來自組織內部的人員。使用郵件流程規則來設定郵件的 SCL 值可讓您增加中處理垃圾郵件的控制項。</span><span class="sxs-lookup"><span data-stu-id="c806d-p101">You can create a mail flow rule (also known as a transport rule) that sets the spam confidence level (SCL) of an email message. The SCL is a measure of how likely a message is to be spam. Spam is unsolicited (and typically unwanted) email messages. The service takes different action on a message depending on its SCL rating. For example, you might want to bypass spam content filtering for messages that are sent from people inside your organization because you trust that a message sent internally from a colleague isn't spam. Using mail flow rules to set the SCL value of a message gives you increased control in handling spam.</span></span> 
  
 <span data-ttu-id="c806d-110">**開始之前有哪些須知？**</span><span class="sxs-lookup"><span data-stu-id="c806d-110">**What do you need to know before you begin?**</span></span>
  
- <span data-ttu-id="c806d-111">完成此程序預估時間： 10 分鐘。</span><span class="sxs-lookup"><span data-stu-id="c806d-111">Estimated time to complete this procedure: 10 minutes.</span></span>
    
- <span data-ttu-id="c806d-p102">您必須獲指派權限，才能執行此程序或各個程序。若要查看您需要的權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)或[EOP 中的權限的功能](eop/feature-permissions-in-eop.md)中的 「 郵件流程規則 」 項目。</span><span class="sxs-lookup"><span data-stu-id="c806d-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Mail flow rules" entry in [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) or [Feature permissions in EOP](eop/feature-permissions-in-eop.md).</span></span> 
    
- <span data-ttu-id="c806d-114">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。</span><span class="sxs-lookup"><span data-stu-id="c806d-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="c806d-115">若要建立將郵件的 SCL 設定郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="c806d-115">To create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="c806d-116">在 Exchange 系統管理中心 (EAC) 中，選擇 [**郵件流程** \> **規則**。</span><span class="sxs-lookup"><span data-stu-id="c806d-116">In the Exchange admin center (EAC), choose **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="c806d-117">選擇 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 [**建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="c806d-117">Choose **New**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="c806d-118">指定規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="c806d-118">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="c806d-119">選擇 [**更多選項**]，然後在 [**如果套用此規則**，請指定會觸發此規則 （也就是可設定的 SCL 值） 將設定的巨集指令的條件。</span><span class="sxs-lookup"><span data-stu-id="c806d-119">Choose **More options**, and then under **Apply this rule if**, specify a condition that will trigger the action you'll be setting for this rule (which is to set the SCL value).</span></span>
    
    <span data-ttu-id="c806d-120">例如，您可以設定**寄件者** \> **內部/外部**，然後在 [**選取寄件者位置**] 對話方塊中，選取**在組織內**，並選擇 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="c806d-120">For example, you can set **The sender** \> **is internal/external**, and then in the **select sender location** dialog box, select **Inside the organization**, and choose **ok**.</span></span><br/>
    <span data-ttu-id="c806d-121">![選取寄件者位置](media/EOP-ETR-SetSCL-1.jpg)</span><span class="sxs-lookup"><span data-stu-id="c806d-121">![Select sender location](media/EOP-ETR-SetSCL-1.jpg)</span></span>
  
5. <span data-ttu-id="c806d-122">在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。</span><span class="sxs-lookup"><span data-stu-id="c806d-122">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
  
6. <span data-ttu-id="c806d-123">在 [**指定 SCL** ] 對話方塊中，選取下列其中一個下列值，並選擇 [**確定]**:</span><span class="sxs-lookup"><span data-stu-id="c806d-123">In the **specify SCL** dialog box, select one of the following values, and choose **ok**:</span></span>
    
  - <span data-ttu-id="c806d-124">**略過垃圾郵件篩選**-將 SCL 設為-1，表示內容篩選不會執行此設定。</span><span class="sxs-lookup"><span data-stu-id="c806d-124">**Bypass spam filtering** - This sets the SCL to -1, which means that content filtering won't be performed.</span></span> 
    
  - <span data-ttu-id="c806d-125">**0-4** -當您將 SCL 設定為下列其中一個這些值時，郵件會傳遞沿著做其他處理的 「 內容篩選器。</span><span class="sxs-lookup"><span data-stu-id="c806d-125">**0-4** - When you set the SCL to one of these values, the message will be passed along to the content filter for additional processing.</span></span> 
    
  - <span data-ttu-id="c806d-p103">**5、 6** -當您將 SCL 設定為其中一個值，指定**垃圾郵件**的適用的內容篩選器原則中的動作將會套用。根據預設，動作是要將郵件傳送至收件者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c806d-p103">**5, 6** - When you set the SCL to one of these values, the action specified for **Spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
  - <span data-ttu-id="c806d-p104">**7-9** -當您將 SCL 設定為其中一個值，指定**高信賴度垃圾郵件**的適用的內容篩選器原則中的巨集指令將會套用。根據預設，動作是要將郵件傳送至收件者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c806d-p104">**7-9** - When you set the SCL to one of these values, the action specified for **High confidence spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
    <span data-ttu-id="c806d-p105">如需設定內容篩選原則的詳細資訊，請參閱<b0>設定垃圾郵件篩選原則</b0>。如需服務中各 SCL 值的詳細資訊，請參閱 <<c1>垃圾郵件信賴等級。</span><span class="sxs-lookup"><span data-stu-id="c806d-p105">For more information about configuring your content filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
7. <span data-ttu-id="c806d-132">指定規則的其他屬性，然後選擇 [**儲存]**。</span><span class="sxs-lookup"><span data-stu-id="c806d-132">Specify additional properties for the rule, and choose **save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c806d-133">如需其他屬性，您可以選取或指定為此規則的詳細資訊，請參閱 <<c0>使用 EAC 來建立郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="c806d-133">For more information about the additional properties you can select or specify for this rule, see [Use the EAC to create mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules).</span></span> 
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c806d-134">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="c806d-134">How do you know this worked?</span></span>

<span data-ttu-id="c806d-p106">若要確認此程序正常運作，電子郵件傳送給組織內的人員，並確認已如預期般地對郵件執行的巨集指令。例如，如果您**略過垃圾郵件篩選**，然後將郵件的 [**設定垃圾郵件信賴等級 (SCL)** 應該傳送給指定收件者的收件匣。不過，如果您**設定垃圾郵件信賴等級 (SCL)** 設為**9**，以及針對適用的內容篩選器原則**高信賴度垃圾郵件**動作是要將郵件移至 [垃圾郵件] 資料夾，然後應該訊息傳送至指定之收件者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c806d-p106">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected. For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox. However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span> 
  

