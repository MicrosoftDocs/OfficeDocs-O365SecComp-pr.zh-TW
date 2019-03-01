---
title: 在 Office 365 中建立整個組織的安全寄件者或封鎖的寄件者清單
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/8/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: 如果您想要是確定您接收來自特定寄件者的郵件，因為您信任它們與他們的郵件，您可以調整您允許在 Exchange 系統管理中心中的垃圾郵件篩選原則中的清單。
ms.openlocfilehash: 0759d054f270cae03b98d9da7e2e2dcfe442d68f
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341594"
---
# <a name="create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365"></a><span data-ttu-id="530b6-103">在 Office 365 中建立整個組織的安全寄件者或封鎖的寄件者清單</span><span class="sxs-lookup"><span data-stu-id="530b6-103">Create organization-wide safe sender or blocked sender lists in Office 365</span></span>
  
<span data-ttu-id="530b6-p101">如果您想要是確定您接收來自特定寄件者的郵件，因為您信任它們與他們的郵件，您可以調整您允許清單中**保護**在 Exchange 系統管理中心 (EAC) 中的垃圾郵件篩選原則\>**垃圾郵件篩選器**。深入了解這在[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。另一個方式則是建立 works 像網域或使用者型允許清單，垃圾郵件篩選器中的 Exchange 郵件流程規則 （也稱為傳輸規則）。您可以封鎖傳送的郵件來自特定網域或使用者以類似方式太。</span><span class="sxs-lookup"><span data-stu-id="530b6-p101">If you want to be sure that you receive mail from a particular sender, because you trust them and their messages, you can adjust your allow list in a spam filter policy in the Exchange admin center (EAC) at **Protection** \> **Spam filter**. Learn more about this at [Configure your spam filter policies](configure-your-spam-filter-policies.md). Another option would be create an Exchange mail flow rule (also known as a transport rule) that works like the domain or user-based allow list in the spam filter. You can block messages sent from a particular domain or user in a similar manner too.</span></span>
  
<span data-ttu-id="530b6-p102">郵件流程規則會很有用在此情況下，如果您要篩選的複雜的準則，例如檢查郵件標頭或附件的名稱，或如果您想要新增複雜的動作，例如將免責聲明新增至郵件或套用一段時間其中 rule 才有作用。不過，若要確保從特定寄件者或網域的電子郵件略過垃圾郵件篩選器的慣用的方法是將它們新增至您的垃圾郵件篩選原則。開始使用這在 EAC 中移至 [**保護** \> **垃圾郵件篩選器**。深入瞭解如何[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="530b6-p102">A mail flow rule would be useful in this situation if you need to filter for complex criteria such as checking message headers or the names of attachments or if you want to add complex actions such as adding a disclaimer to the message or applying a time period where the rule is active. However, the preferred method to make sure emails from a specific sender or domain bypass your spam filter is to add them to your spam filter policy. Get started with this in the EAC by going to **Protection** \> **Spam filter**. Learn more at [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="530b6-p103">網域型清單中的郵件流程規則不一樣安全 IP 位址型清單，因為網域可以假冒。此外，如果傳送 IP 位址是在封鎖清單上，它仍然會被封鎖即使篩選網域或使用者已被略過。這是因為網域或使用者的郵件流程規則不覆寫全域 IP 封鎖清單。我們建議在大多數情況下使用 IP 位址型清單。若要建立 IP 位址型清單，您可以使用的 IP 允許清單或 IP 封鎖清單中連線篩選器。任何來自這些 IP 位址傳送的郵件未由內容篩選檢查。如需如何設定連線篩選原則來新增 IP 位址至 IP 允許清單或 IP 封鎖清單的相關指示，請參閱 < <b0>Configure the connection filter policy </b0>。</span><span class="sxs-lookup"><span data-stu-id="530b6-p103">A domain-based list in a mail flow rule isn't as secure as an IP address-based list, because domains can be spoofed. Also, if the sending IP address is on a Block list, it will still be blocked even if filtering for the domain or user is being bypassed. This is because a mail flow rule on a domain or user does not override the global IP Block list. We recommend using an IP address-based list in most cases. To create an IP address-based list, you can use the IP Allow list or IP Block list in the connection filter. Any messages sent from these IP addresses aren't checked by the content filter. For instructions on how to configure the connection filter policy by adding IP addresses to the IP Allow list or IP Block list, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> 
  
<span data-ttu-id="530b6-119">郵件流程規則相關的其他管理工作，請參閱[郵件流程規則 （傳輸規則） 在 [Exchange Online](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)。</span><span class="sxs-lookup"><span data-stu-id="530b6-119">For additional management tasks related to mail flow rules, see [Mail flow rules (transport rules) in Exchange Online](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).</span></span>
  
## <a name="use-the-eac-to-customize-a-block-or-allow-list-to-prevent-or-receive-email-from-a-domain-or-user"></a><span data-ttu-id="530b6-120">使用 EAC 自訂封鎖或允許清單，以防止或從某個網域或使用者接收電子郵件</span><span class="sxs-lookup"><span data-stu-id="530b6-120">Use the EAC to customize a block or allow list to prevent or receive email from a domain or user</span></span>

1. <span data-ttu-id="530b6-121">在 EAC 中，移至 [**保護** \> **垃圾郵件篩選器**。</span><span class="sxs-lookup"><span data-stu-id="530b6-121">In the EAC, go to **Protection** \> **Spam filter**.</span></span> 
    
2. <span data-ttu-id="530b6-122">在 [**一般**] 頁面上，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="530b6-122">On the **general** page, do one of the following:</span></span> 
    
  - <span data-ttu-id="530b6-123">若要開始編輯它，按兩下 [預設原則或現有的原則。</span><span class="sxs-lookup"><span data-stu-id="530b6-123">Double-click the default policy or an existing policy in order to start editing it.</span></span>
    
  - <span data-ttu-id="530b6-124">若要建立新的自訂垃圾郵件篩選器原則可以套用至使用者、 群組及組織中的網域，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="530b6-124">Click **New** in order to create a new custom spam-filter policy that can be applied to users, groups, and domains in your organization.</span></span> 
    
3. <span data-ttu-id="530b6-p104">在 [**允許清單**] 頁面上，您可以指定項目，例如寄件者或網域，一律會傳遞至收件匣。垃圾郵件篩選器不會處理來自這些項目的電子郵件。執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="530b6-p104">On the **Allow Lists** page, you can specify entries, such as senders or domains, that will always be delivered to the inbox. Email from these entries is not processed by the spam filter. Do the following:</span></span> 
    
  - <span data-ttu-id="530b6-p105">新增信任的寄件者寄件者允許清單。按一下 [**新增**]，然後在 [選取項目] 對話方塊中，新增 [您想要允許的寄件者地址。您可以分開使用分號或新行的多個項目。按一下 [確定] 回到 [**允許清單**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="530b6-p105">Add trusted senders to the Sender allow list. Click **Add**, and then in the selection dialog box, add the sender addresses you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page.</span></span> 
    
  - <span data-ttu-id="530b6-p106">新增受信任的網域到網域允許清單。按一下 [**新增**]，然後在 [選取項目] 對話方塊中，新增 [您想要允許的網域。您可以分開使用分號或新行的多個項目。按一下 [確定] 回到 [**允許清單**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="530b6-p106">Add trusted domains to the Domain allow list. Click **Add**, and then in the selection dialog box, add the domains you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="530b6-136">如果您允許頂層網域，您不想要的電子郵件可能會傳遞至收件匣。</span><span class="sxs-lookup"><span data-stu-id="530b6-136">If you allow top-level domains, it's likely that email you don't want will be delivered to an inbox.</span></span> 
  
4. <span data-ttu-id="530b6-p107">在 [ **封鎖清單**] 頁面上，您可以指定一律會標記為垃圾郵件的項目，例如寄件者或網域。此服務將會在符合這些項目的電子郵件上套用高信賴垃圾郵件動作。</span><span class="sxs-lookup"><span data-stu-id="530b6-p107">On the **Block Lists** page, you can specify entries, such as senders or domains, that will always be marked as spam. The service will apply the configured high confidence spam action on email that matches these entries.</span></span> 
    
  - <span data-ttu-id="530b6-p108">將不想要的寄件者新增到「寄件者」封鎖清單。按一下 **[新增]**![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要封鎖的寄件者地址。您可以使用分號或新行區隔多個項目。按一下 [ **確定**] 回到 [ **封鎖清單**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="530b6-p108">Add unwanted senders to the Sender block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then in the selection dialog box, add the sender addresses you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page.</span></span> 
    
  - <span data-ttu-id="530b6-p109">將不想要的網域新增到「網域」封鎖清單。按一下 [ **新增**] ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要封鎖的網域。您可以使用分號或新行區隔多個項目。按一下 [ **確定**] 回到 [ **封鎖清單**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="530b6-p109">Add unwanted domains to the Domain block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then in the selection dialog box, add the domains you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="530b6-147">如果您封鎖頂層網域，您想要的電子郵件可能會標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="530b6-147">If you block top-level domains, it's likely that email you want will be marked as spam.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin-creating-a-mail-flow-rule"></a><span data-ttu-id="530b6-148">您需要知道之前建立郵件流程規則什麼？</span><span class="sxs-lookup"><span data-stu-id="530b6-148">What do you need to know before you begin creating a mail flow rule?</span></span>
    
- <span data-ttu-id="530b6-p110">您不需要建立郵件流程規則，以略過垃圾郵件篩選] 或 [標記電子郵件為垃圾郵件的寄件者或網域。使用 Exchange Online Protection 封鎖及允許清單中的垃圾郵件原則，而不是此郵件流程規則，如果您只想要封鎖或允許特定寄件者或網域，並沒有附加任何額外的條件。深入了解這在[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="530b6-p110">You don't need to create a mail flow rule to bypass spam filtering or mark email as spam for a sender or domain. Use the Exchange Online Protection block and allow lists in a spam policy instead of this mail flow rule if you simply want to block or allow a specific sender or domain and not attach any extra conditions. Learn more about this at [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
- <span data-ttu-id="530b6-p111">您必須獲指派權限，才能執行此程序或各個程序。若要查看您需要的權限，請參閱[通訊原則及符合性權限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主題中的 「 郵件流程規則 」 項目。</span><span class="sxs-lookup"><span data-stu-id="530b6-p111">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Mail flow rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="530b6-154">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。</span><span class="sxs-lookup"><span data-stu-id="530b6-154">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="530b6-p112">有問題嗎？要求在 Exchange 論壇中的協助。此論壇的網址為： [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、 [Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="530b6-p112">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612), [Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-bypass-spam-filtering-for-a-domain-or-user"></a><span data-ttu-id="530b6-158">使用 EAC 來建立郵件流程規則，以略過網域或使用者的垃圾郵件篩選</span><span class="sxs-lookup"><span data-stu-id="530b6-158">Use the EAC to create a mail flow rule to bypass spam filtering for a domain or user</span></span>

1. <span data-ttu-id="530b6-p113">在 EAC 中，瀏覽至 [**郵件流程** \> **規則**。選擇 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)]，然後選擇 [**略過垃圾郵件篩選**。</span><span class="sxs-lookup"><span data-stu-id="530b6-p113">In the EAC, navigate to **Mail flow** \> **Rules**. Choose **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then choose **Bypass spam filtering**.</span></span>
    
2. <span data-ttu-id="530b6-p114">為規則命名。在 **[套用此規則，如果]** 下，選擇 **[寄件者]**，然後選取下列其中一個條件：</span><span class="sxs-lookup"><span data-stu-id="530b6-p114">Give the rule a name. Under **Apply this rule if**, choose **The sender** and then select one of the following conditions:</span></span> 
    
  - <span data-ttu-id="530b6-p115">如果您要指定網域，請選擇 [**網域是**]。在 [**指定網域**] 對話方塊中，輸入您想要指定為安全，例如 contoso.com 的寄件者的網域。**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)將其移至片語清單。如果您想要新增其他網域，並按一下 [**確定]** ，當您完成時，請重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="530b6-p115">If you want to specify a domain, choose **domain is**. In the **Specify domain** dialog box, enter the domain of the sender you want to designate as safe, such as contoso.com. **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) to move it to the list of phrases. Repeat this step if you want to add additional domains, and click **OK** when you are finished.</span></span> 
    
  - <span data-ttu-id="530b6-p116">如果您要指定使用者，請選擇 **[是此人]**。在 **[選取成員]** 對話方塊中，新增清單中的使用者，或輸入使用者並按一下 **[檢查名稱]**。如果要新增其他使用者，請重複此步驟，並在完成後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="530b6-p116">If you want to specify a user, choose **is this person**. In the **Select members** dialog box, add the user from the list or type the user and click **Check names**. Repeat this step if you want to add additional users, and click **OK** when you are finished.</span></span> 
    
3. <span data-ttu-id="530b6-170">選取 [**停止處理其他規則**] 核取方塊，以確保沒有其他規則能夠逆轉略過動作</span><span class="sxs-lookup"><span data-stu-id="530b6-170">Select the **Stop processing more rules** check box to ensure that no other rule can reverse the bypass action</span></span> 
    
4. <span data-ttu-id="530b6-171">**郵件中的比對寄件者地址**] 選項中，選取 [**標頭或信封**。</span><span class="sxs-lookup"><span data-stu-id="530b6-171">For the **Match sender address in message** option, select **Header or envelope**.</span></span>
    
5. <span data-ttu-id="530b6-172">您也可以視需要選取稽核規則、測試規則、在特定期間啟動規則等等選項。</span><span class="sxs-lookup"><span data-stu-id="530b6-172">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span>
    
6. <span data-ttu-id="530b6-173">選擇 **[儲存]** 儲存規則。</span><span class="sxs-lookup"><span data-stu-id="530b6-173">Choose **Save** to save the rule.</span></span> 
    
<span data-ttu-id="530b6-174">建立並強制執行規則後，垃圾郵件篩選就會略過您指定的網域或使用者。</span><span class="sxs-lookup"><span data-stu-id="530b6-174">After you create and enforce the rule, spam filtering is bypassed for the domain or user you specified.</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-that-blocks-messages-sent-from-a-domain-or-user"></a><span data-ttu-id="530b6-175">使用 EAC 來建立郵件流程規則會封鎖從某個網域或使用者傳送的郵件</span><span class="sxs-lookup"><span data-stu-id="530b6-175">Use the EAC to create a mail flow rule that blocks messages sent from a domain or user</span></span>

1. <span data-ttu-id="530b6-p117">在 EAC 中，瀏覽至 [**郵件流程** \> **規則**。選擇 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後選擇 [**建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="530b6-p117">In the EAC, navigate to **Mail flow** \> **Rules**. Choose **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then choose **Create a new rule**.</span></span>
    
2. <span data-ttu-id="530b6-178">命名規則，然後按一下 **[更多選項]**。</span><span class="sxs-lookup"><span data-stu-id="530b6-178">Give the rule a name and then click **More options**.</span></span> 
    
3. <span data-ttu-id="530b6-179">在 **[套用此規則，如果]** 下，選擇 **[寄件者]**，然後選取下列其中一個條件：</span><span class="sxs-lookup"><span data-stu-id="530b6-179">Under **Apply this rule if**, choose **The sender** and then select one of the following conditions:</span></span> 
    
  - <span data-ttu-id="530b6-p118">如果您要指定網域，請選擇 [**網域是**]。在 [指定網域] 對話方塊中，輸入您要封鎖郵件，例如 contoso.com 的寄件者網域。按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)將其移至片語清單。如果您想要新增其他網域，並按一下 [**確定]** ，當您完成時，請重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="530b6-p118">If you want to specify a domain, choose **domain is**. In the Specify domain dialog box, enter the sender domain from which you want to block messages, such as contoso.com. Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) to move it to the list of phrases. Repeat this step if you want to add additional domains, and click **OK** when you are finished.</span></span> 
    
  - <span data-ttu-id="530b6-p119">如果您要指定使用者，請選擇 **[是此人]**。在 **[選取成員]** 對話方塊中，新增清單中的使用者，或輸入使用者並按一下 **[檢查名稱]**。如果要新增其他使用者，請重複此步驟，並在完成後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="530b6-p119">If you want to specify a user, choose **is this person**. In the **Select members** dialog box, add the user from the list or type the user and click **Check names**. Repeat this step if you want to add additional users, and click **OK** when you are finished.</span></span> 
    
4. <span data-ttu-id="530b6-187">在 **[執行下列作業]** 下方，選擇 **[封鎖郵件]**，然後按其餘選項之一，例如 **[刪除郵件而不通知任何人]**。</span><span class="sxs-lookup"><span data-stu-id="530b6-187">Under **Do the following**, choose **Block the message** and then click one of the other options such as **Delete the message without notifying anyone**.</span></span>
    
5. <span data-ttu-id="530b6-188">按一下 [**更多選項**]，然後 [**比對郵件中的寄件者地址**] 選項中，選取 [**標頭或信封**。</span><span class="sxs-lookup"><span data-stu-id="530b6-188">Click **More options**, and then for the **Match sender address in message** option, select **Header or envelope**.</span></span>
    
6. <span data-ttu-id="530b6-p120">如果您想要您可以將需要選取稽核規則、 測試規則，在特定時間期間啟動規則和其他選取項目。我們建議您測試規則一段之前強制執行組織中的時間。</span><span class="sxs-lookup"><span data-stu-id="530b6-p120">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period of time before enforcing it in your organization.</span></span>
    
7. <span data-ttu-id="530b6-191">選擇 **[儲存]** 儲存規則。</span><span class="sxs-lookup"><span data-stu-id="530b6-191">Choose **Save** to save the rule.</span></span> 
    
<span data-ttu-id="530b6-192">建立並強制執行規則後，將會封鎖從您指定的網域或使用者傳來的任何郵件。</span><span class="sxs-lookup"><span data-stu-id="530b6-192">After you create and enforce the rule, any messages sent from the domain or user you specify will be blocked.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="530b6-193">另請參閱</span><span class="sxs-lookup"><span data-stu-id="530b6-193">See also</span></span>

[<span data-ttu-id="530b6-194">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="530b6-194">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="530b6-195">使用郵件流程規則來設定大量電子郵件篩選</span><span class="sxs-lookup"><span data-stu-id="530b6-195">Use mail flow rules to configure bulk email filtering</span></span>](use-transport-rules-to-configure-bulk-email-filtering.md)

