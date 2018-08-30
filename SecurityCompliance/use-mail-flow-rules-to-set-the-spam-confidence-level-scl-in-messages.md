---
title: 使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)
ms.author: krowley
author: kccross
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
description: 您可以建立的傳輸規則會將電子郵件的垃圾郵件信賴等級 (SCL)。SCL 為量值的方式有可能郵件為垃圾郵件。垃圾郵件是來路不明的 （且通常不想要的） 的電子郵件訊息。服務會根據其 scl 郵件上採取不同的動作。例如，您可能會想略過垃圾郵件內容之郵件的傳送來自組織內的人員因為您信任從同事內部傳送的訊息不是垃圾郵件篩選。您使用傳輸規則將郵件的 SCL 值提供增加處理垃圾郵件中的控制項。
ms.openlocfilehash: 7abd0d1881374b1f2a4bd32ee480445f7683d1b3
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002892"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="dbfbb-108">使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)</span><span class="sxs-lookup"><span data-stu-id="dbfbb-108">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="dbfbb-p102">您可以建立的傳輸規則會將電子郵件的垃圾郵件信賴等級 (SCL)。SCL 為量值的方式有可能郵件為垃圾郵件。垃圾郵件是來路不明的 （且通常不想要的） 的電子郵件訊息。服務會根據其 scl 郵件上採取不同的動作。例如，您可能會想略過垃圾郵件內容之郵件的傳送來自組織內的人員因為您信任從同事內部傳送的訊息不是垃圾郵件篩選。您使用傳輸規則將郵件的 SCL 值提供增加處理垃圾郵件中的控制項。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-p102">You can create a transport rule that sets the spam confidence level (SCL) of an email message. The SCL is a measure of how likely a message is to be spam. Spam is unsolicited (and typically unwanted) email messages. The service takes different action on a message depending on its SCL rating. For example, you might want to bypass spam content filtering for messages that are sent from people inside your organization because you trust that a message sent internally from a colleague isn't spam. Using transport rules to set the SCL value of a message gives you increased control in handling spam.</span></span> 
  
 <span data-ttu-id="dbfbb-115">**開始之前有哪些須知？**</span><span class="sxs-lookup"><span data-stu-id="dbfbb-115">**What do you need to know before you begin?**</span></span>
  
- <span data-ttu-id="dbfbb-116">完成此程序預估時間： 10 分鐘。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-116">Estimated time to complete this procedure: 10 minutes.</span></span>
    
- <span data-ttu-id="dbfbb-p103">您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)或[功能 EOP 中的權限](eop/feature-permissions-in-eop.md)中的 「 傳輸規則 」 項目。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) or [Feature permissions in EOP](eop/feature-permissions-in-eop.md).</span></span> 
    
- <span data-ttu-id="dbfbb-119">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
### <a name="to-create-a-transport-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="dbfbb-120">若要建立的傳輸規則會將郵件的 SCL</span><span class="sxs-lookup"><span data-stu-id="dbfbb-120">To create a transport rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="dbfbb-121">在 Exchange 系統管理中心 (EAC) 中，選擇 [**郵件流程** \> **規則**。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-121">In the Exchange admin center (EAC), choose **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="dbfbb-122">選擇 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 [**建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-122">Choose **New**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="dbfbb-123">指定規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-123">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="dbfbb-124">選擇 [**更多選項**]，然後在 [**套用此規則**，指定 [會觸發此規則 （這是設定 SCL 值） 將設定的巨集指令的條件。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-124">Choose **More options**, and then under **Apply this rule if**, specify a condition that will trigger the action you'll be setting for this rule (which is to set the SCL value).</span></span>
    
    <span data-ttu-id="dbfbb-125">例如，您可以設定**寄件者** \> **內部/外部**，然後**選取 [寄件者位置**] 對話方塊中，選取**在組織內**，並選擇 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-125">For example, you can set **The sender** \> **is internal/external**, and then in the **select sender location** dialog box, select **Inside the organization**, and choose **ok**.</span></span></br>
    <span data-ttu-id="dbfbb-126">![選取寄件者位置](media/EOP-ETR-SetSCL-1.jpg)</span><span class="sxs-lookup"><span data-stu-id="dbfbb-126">![Select sender location](media/EOP-ETR-SetSCL-1.jpg)</span></span>
  
5. <span data-ttu-id="dbfbb-127">在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-127">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
  
6. <span data-ttu-id="dbfbb-128">在 [**指定 SCL** ] 對話方塊中，選取下列其中一個的下列值並選擇 [**確定]**：</span><span class="sxs-lookup"><span data-stu-id="dbfbb-128">In the **specify SCL** dialog box, select one of the following values, and choose **ok**:</span></span>
    
  - <span data-ttu-id="dbfbb-129">**略過垃圾郵件篩選**-將不會執行為-1、 內容篩選這表示 SCL 此設定。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-129">**Bypass spam filtering** - This sets the SCL to -1, which means that content filtering won't be performed.</span></span> 
    
  - <span data-ttu-id="dbfbb-130">**0-4** -當您將 SCL 設定為下列值之一，將郵件傳遞沿著以做其他處理的內容篩選器。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-130">**0-4** - When you set the SCL to one of these values, the message will be passed along to the content filter for additional processing.</span></span> 
    
  - <span data-ttu-id="dbfbb-p104">會套用**5、 6** -當您將 SCL 設定為其中一個值，可用的內容篩選器原則中指定的**垃圾郵件**的動作。根據預設，動作是要將郵件傳送給收件者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-p104">**5, 6** - When you set the SCL to one of these values, the action specified for **Spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
  - <span data-ttu-id="dbfbb-p105">會套用**7-9** -當您將 SCL 設定為其中一個值，指定**高信賴垃圾郵件**的適用的內容篩選器原則中的巨集指令。根據預設，動作是要將郵件傳送給收件者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-p105">**7-9** - When you set the SCL to one of these values, the action specified for **High confidence spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
    <span data-ttu-id="dbfbb-p106">如需設定內容篩選原則的詳細資訊，請參閱[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)。如需服務中各 SCL 值的詳細資訊，請參閱[Spam confidence levels](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-p106">For more information about configuring your content filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
7. <span data-ttu-id="dbfbb-137">指定規則的其他屬性，並選擇 [**儲存]**。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-137">Specify additional properties for the rule, and choose **save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="dbfbb-138">如需您可以選取或指定為此規則的其他屬性的詳細資訊，請參閱[使用 EAC 建立傳輸規則](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx#CreateEAC)。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-138">For more information about the additional properties you can select or specify for this rule, see [Use the EAC to create a transport rule](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx#CreateEAC).</span></span> 
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="dbfbb-139">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="dbfbb-139">How do you know this worked?</span></span>

<span data-ttu-id="dbfbb-p107">若要確認此程序運作正常，請傳送電子郵件訊息給您的組織內的某個人並確認訊息上執行的動作如預期般運作。例如，如果您為**略過垃圾郵件篩選**，則郵件的 [**設定垃圾郵件信賴等級 (SCL)** 應該傳送給指定之收件者的收件匣。不過，如果您**設定垃圾郵件信賴等級 (SCL)** **9**、 及適用的內容篩選器原則的**高信賴垃圾郵件**動作是要將郵件移至 [垃圾郵件] 資料夾，然後應該訊息傳送至指定之收件者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="dbfbb-p107">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected. For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox. However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span> 
  

