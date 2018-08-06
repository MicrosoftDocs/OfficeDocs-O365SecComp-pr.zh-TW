---
title: 設定您的垃圾郵件篩選原則
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
description: 基本的垃圾郵件篩選設定包括選取會被識別為垃圾郵件的郵件上所採取的動作和選擇是否要篩選以特定語言編寫或寄自特定國家或地區的郵件。
ms.openlocfilehash: b0a5fa1a5640bd0baab68c29d8098059a6025f7d
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026530"
---
# <a name="configure-your-spam-filter-policies"></a><span data-ttu-id="e4b63-103">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="e4b63-103">Configure your spam filter policies</span></span>
  
<span data-ttu-id="e4b63-p101">基本的垃圾郵件篩選設定包括選取會被識別為垃圾郵件的郵件上所採取的動作和選擇是否要篩選以特定語言編寫或寄自特定國家或地區的郵件。垃圾郵件篩選器原則設定會套用至內送的郵件。您可以編輯預設垃圾郵件篩選器原則來設定全公司的垃圾郵件篩選器組態及建立自訂垃圾郵件篩選器原則，然後套用至特定使用者、 群組或組織中的網域。自訂原則一律優先預設原則。您可以變更您的自訂原則執行所變更的每個自訂原則優先順序的順序。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p101">Basic spam filter settings include selecting the action to take on messages that are identified as spam, and choosing whether to filter messages that are written in specific languages or sent from specific countries or regions. Spam filter policy settings are applied to inbound messages only. You can edit the default spam filter policy to configure your company-wide spam filter settings and create custom spam filter policies, and then apply them to specific users, groups, or domains in your organization. Custom policies always take precedence over the default policy. You can change the order in which your custom policies run by changing the priority of each custom policy.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e4b63-p102">Exchange Online Protection (EOP) 獨立客戶： 根據預設，EOP 垃圾郵件篩選器將垃圾郵件偵測到的郵件傳送至每個收件者的垃圾郵件] 資料夾。不過，以確保 [**移至 [垃圾郵件] 資料夾的郵件**] 動作運作的內部部署信箱，您必須設定 Exchange 傳輸規則來偵測新增的 EOP 的垃圾郵件標頭的內部伺服器上。如需詳細資訊，請參閱[確定垃圾郵件會路由傳送至每位使用者的垃圾郵件] 資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p102">For Exchange Online Protection (EOP) stand-alone customers: By default, the EOP spam filters send spam-detected messages to each recipient's Junk Email folder. However, in order to ensure that the **Move message to Junk Email folder** action works for on-premises mailboxes, you must configure Exchange Transport rules on your on-premises servers to detect spam headers that are added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
## <a name="what-you-must-know-before-you-begin"></a><span data-ttu-id="e4b63-112">您必須知道您開始之前</span><span class="sxs-lookup"><span data-stu-id="e4b63-112">What you must know before you begin</span></span>
<span data-ttu-id="e4b63-113"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="e4b63-113"></span></span>

<span data-ttu-id="e4b63-114">預估完成時間：30 分鐘</span><span class="sxs-lookup"><span data-stu-id="e4b63-114">Estimated time to complete: 30 minutes</span></span>
  
<span data-ttu-id="e4b63-p103">您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題中的反垃圾郵件項目。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="e4b63-117">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Keyboard shortcuts in Exchange 2013**。</span><span class="sxs-lookup"><span data-stu-id="e4b63-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-exchange-admin-center-eac-to-configure-spam-filter-policies"></a><span data-ttu-id="e4b63-118">使用 Exchange 系統管理中心 (EAC) 來設定垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="e4b63-118">Use the Exchange Admin Center (EAC) to configure spam filter policies</span></span>
<span data-ttu-id="e4b63-119"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="e4b63-119"></span></span>

1. <span data-ttu-id="e4b63-120">在 Exchange 系統管理中心 (EAC)，瀏覽至 **[保護]** \> **[垃圾郵件篩選]**。</span><span class="sxs-lookup"><span data-stu-id="e4b63-120">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="e4b63-121">在 **[一般]** 頁面上執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="e4b63-121">Do one of the following on the **general** page:</span></span> 
    
  - <span data-ttu-id="e4b63-122">按兩下預設原則，以編輯這個全公司的原則。</span><span class="sxs-lookup"><span data-stu-id="e4b63-122">Double-click the default policy in order to edit this company-wide policy.</span></span>
    
  - <span data-ttu-id="e4b63-p104">按一下 ![加入圖示](media/ITPro-EAC-AddIcon.png) **[新建]** 圖示，建立新的自訂垃圾郵件篩選原則，此原則可以套用到組織內的使用者、群組和網域。您也可以按兩下現有的自訂原則來編輯它們。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p104">Click the ![Add Icon](media/ITPro-EAC-AddIcon.png) **New** icon in order to create a new custom spam-filter policy that can be applied to users, groups, and domains in your organization. You can also edit existing custom policies by double-clicking them.</span></span> 
    
3. <span data-ttu-id="e4b63-p105">僅限自訂原則，指定此原則的名稱。或者，您也可以指定詳細的說明。您不能重新命名的預設原則。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p105">For custom policies only, specify a name for this policy. Optionally, you can also specify a more detailed description. You cannot rename the default policy.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e4b63-p106">當您建立原則時，單一畫面上會出現所有組態設定。相反地，當您編輯原則，您必須瀏覽到多個畫面。設定都是相同的兩種情況，但此程序的其餘部分說明如何編輯原則時存取這些設定。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p106">When you create a policy, all configuration settings appear on a single screen. By contrast, when you edit a policy, you must navigate through multiple screens. The settings are the same in either case, but the rest of this procedure describes how to access these settings when you edit a policy.</span></span> 
  
4. <span data-ttu-id="e4b63-p107">在 **[垃圾郵件和大量電子郵件動作]** 頁面上，在 **[垃圾郵件]** 和 **[高信賴度垃圾郵件]** 底下，選取要為內送的垃圾郵件和大量電子郵件採取的動作。根據預設，會選取 **[將郵件移至垃圾郵件資料夾]**。其他可能的值為：</span><span class="sxs-lookup"><span data-stu-id="e4b63-p107">On the **spam and bulk email actions** page, under **Spam** and **High confidence spam**, select the action to take for incoming spam and bulk email. By default, **Move messages to Junk Email folder** is selected. The other possible values are:</span></span> 
    
  - <span data-ttu-id="e4b63-134">**刪除郵件** 刪除整個郵件，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="e4b63-134">**Delete message** Deletes the entire message, including all attachments.</span></span> 
    
  - <span data-ttu-id="e4b63-p108">**隔離郵件**傳送至隔離而不是預定的收件者的訊息。如果您選取這個選項，請輸入 **（天） 的保留天數垃圾郵件**] 方塊中，指定要垃圾郵件隔離的期間的天數。（它將自動刪除後經過的時間。預設值為 15 天這是最大值。最小值是 1 天）。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p108">**Quarantine message** Sends the message to quarantine instead of to the intended recipients. If you select this option, in the **Retain spam for (days)** input box, specify the number of days during which the spam message will be quarantined. (It will automatically be deleted after the time elapses. The default value is 15 days which is the maximum value. The minimum value is 1 day.)</span></span> 
    
    > [!TIP]
    >  <span data-ttu-id="e4b63-p109">如需如何管理員可以管理位於隔離在 EAC 中信箱的電子郵件訊息，請參閱[隔離區](quarantine.md)並[尋找和釋出隔離的郵件系統管理員身分](find-and-release-quarantined-messages-as-an-administrator.md)。> 如需如何設定垃圾郵件通知訊息傳送給使用者的資訊，請參閱[設定使用者垃圾郵件通知中 EOP](configure-end-user-spam-notifications-in-eop.md)或[設定使用者垃圾郵件通知在 Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p109">For information about how administrators can manage email messages that reside in the quarantine in the EAC, see [Quarantine](quarantine.md) and [Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md). >  For information about how to configure spam notification messages to be sent to users, see [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md) or [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span></span> 
  
  - <span data-ttu-id="e4b63-p110">**將郵件移動到 [垃圾郵件] 資料夾** 將郵件傳送到指定收件者的 [垃圾郵件] 資料夾。這是兩種信賴閾值等級的預設動作。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p110">**Move message to Junk Email folder** Sends the message to the Junk Email folder of the specified recipients. This is the default action for both confidence threshold levels.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="e4b63-p111">針對 Exchange Online Protection (EOP) 客戶：為了在內部部署信箱中啟用此動作，您必須在內部部署伺服器上設定兩個 Exchange 傳輸規則，以偵測 EOP 所新增的垃圾郵件標頭。如需詳細資訊，請參閱[確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p111">For Exchange Online Protection (EOP) customers: In order for this action to work with on-premises mailboxes, you must configure two Exchange Transport rules on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
  - <span data-ttu-id="e4b63-p112">**新增 x-header**將郵件傳送給指定的收件者，但以識別為垃圾郵件的郵件將 x-header 文字新增至郵件標頭。使用此文字做為識別碼，可以選擇性地建立收件匣規則或使用下游裝置來處理郵件。預設的 x-header 文字是**設為垃圾郵件出現這個訊息**。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p112">**Add X-header** Sends the message to the specified recipients, but adds X-header text to the message header in order to identify the message as spam. Using this text as an identifier, you can optionally create inbox rules or use a downstream device to act on the message. The default X-header text is **This message appears to be spam**.</span></span>
    
    <span data-ttu-id="e4b63-p113">您可以使用 [**新增此 x-header 文字**輸入的方塊自訂 x-header 文字。如果您自訂 x-header 文字，請注意下列條件：</span><span class="sxs-lookup"><span data-stu-id="e4b63-p113">You can customize the X-header text by using the **Add this X-header text** input box. If you customize the X-header text, be aware of the following conditions:</span></span> 
    
  - <span data-ttu-id="e4b63-p114">如果您指定的標頭的格式\<*標頭*\>、 沒有中的不含空白\<*標頭*\>、 冒號便會附加至自訂的文字，後面加上預設文字。例如，如果您指定"這是-我-自訂-標頭"，x-header 文字會顯示為 「 這是-我-自訂-標頭： This message 看起來垃圾郵件。 」      </span><span class="sxs-lookup"><span data-stu-id="e4b63-p114">If you specify only the header in the format \< *header*  \>, where there are no spaces within the \<  *header*  \>, a colon will be appended to the custom text, followed by the default text. For example, if you specify "This-is-my-custom-header," the X-header text will appear as "This-is-my-custom-header: This message appears to be spam."</span></span> 
    
  - <span data-ttu-id="e4b63-153">如果您包括空格內自訂的標題文字，或如果您新增冒號自行 (例如"X 這是我自訂的標頭"或"X-This-is-my-custom-header:")、 x-header 文字回復成預設值為"X 此-是-垃圾郵件： This message 看起來垃圾郵件。 」</span><span class="sxs-lookup"><span data-stu-id="e4b63-153">If you include spaces within the custom header text, or if you add the colon yourself (such as "X This is my custom header" or "X-This-is-my-custom-header:"), the X-header text reverts to the default as "X-This-Is-Spam: This message appears to be spam."</span></span>
    
  - <span data-ttu-id="e4b63-p115">您無法指定的標題文字的格式\<*標頭*\>：\<*值*\>。如果您這樣做，同時值之前和之後冒號都會被忽略，並改用預設 x-header 文字出現:"X 此-是-垃圾郵件： This message 看起來垃圾郵件。 」      </span><span class="sxs-lookup"><span data-stu-id="e4b63-p115">You can't specify the header text in the format \< *header*  \>:\<  *value*  \>. If you do this, both values before and after the colon will be ignored, and the default X-header text appears instead: "X-This-Is-Spam: This message appears to be spam."</span></span> 
    
  - <span data-ttu-id="e4b63-p116">**Prepend 主旨行文字**將郵件傳送給預定的收件者，但是前面加上**前置詞與此文字的主旨行**輸入方塊中指定的文字具有的主旨行。使用此文字做為識別碼，您可以選擇性地建立篩選或路由傳送訊息所需的規則。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p116">**Prepend subject line with text** Sends the message to the intended recipients but prepends the subject line with the text that you specify in the **Prefix subject line with this text** input box. Using this text as an identifier, you can optionally create rules to filter or route the messages as necessary.</span></span> 
    
  - <span data-ttu-id="e4b63-p117">**重新導向至電子郵件地址的郵件**將郵件傳送給預定的收件者而不是指定的電子郵件地址。**重新導向至這個電子郵件地址**輸入方塊中指定的"重新導向 」 地址。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p117">**Redirect message to email address** Sends the message to a designated email address instead of to the intended recipients. Specify the "redirect" address in the **Redirect to this email address** input box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e4b63-160">如需垃圾郵件信賴等級的相關資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="e4b63-160">For more information about spam confidence levels, see [Spam confidence levels](spam-confidence-levels.md).</span></span> 
  
5. <span data-ttu-id="e4b63-p118">[**大量電子郵件**，您可以選取要將大量電子郵件視為垃圾郵件臨界值。此臨界值根據郵件的大量抱怨層級。您可以選擇 1 的臨界值設定為 9，其中 1 表示大部分的大量電子郵件為垃圾郵件和 9 允許大部分的大量電子郵件傳遞。服務再執行設定的動作，例如將郵件傳送給收件者的垃圾郵件] 資料夾。請參閱[大量抱怨層級值](bulk-complaint-level-values.md)和[垃圾郵件與大量電子郵件之間的差異為何吗？](what-s-the-difference-between-junk-email-and-bulk-email.md)如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p118">Under **Bulk email**, you can select a threshold to treat bulk email as spam. This threshold is based on the bulk complaint level of the message. You can choose a threshold setting from 1 to 9, where 1 indicates most bulk email as spam, and 9 allows the most bulk email to be delivered. The service then performs the configured action, such as sending the message to the recipient's Junk Email folder. See [Bulk Complaint Level values](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) for more details.</span></span> 
    
6. <span data-ttu-id="e4b63-p119">在 [ **封鎖清單**] 頁面上，您可以指定一律會標記為垃圾郵件的項目，例如寄件者或網域。此服務將會在符合這些項目的電子郵件上套用高信賴垃圾郵件動作。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p119">On the **Block Lists** page, you can specify entries, such as senders or domains, that will always be marked as spam. The service will apply the configured high confidence spam action on email that matches these entries.</span></span> 
    
  - <span data-ttu-id="e4b63-p120">將不想要的寄件者新增到「寄件者」封鎖清單。按一下 **[新增]**![加入圖示](media/ITPro-EAC-AddIcon.png)，然後在選取範圍對話方塊中新增您想要封鎖的寄件者地址。您可以使用分號或新行區隔多個項目。按一下 [ **確定**] 回到 [ **封鎖清單**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p120">Add unwanted senders to the Sender block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the sender addresses you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page.</span></span> 
    
  - <span data-ttu-id="e4b63-p121">將不想要的網域新增到「網域」封鎖清單。按一下 [ **新增**] ![加入圖示](media/ITPro-EAC-AddIcon.png)，然後在選取範圍對話方塊中新增您想要封鎖的網域。您可以使用分號或新行區隔多個項目。按一下 [ **確定**] 回到 [ **封鎖清單**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p121">Add unwanted domains to the Domain block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the domains you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="e4b63-176">如果您封鎖頂層網域，您想要的電子郵件可能會標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="e4b63-176">If you block top-level domains, it's likely that email you want will be marked as spam.</span></span> 
  
7. <span data-ttu-id="e4b63-p122">在 [ **允許清單**] 頁面上，您可以指定一律會傳遞到收件匣的項目，例如寄件者或網域。來自這些項目的電子郵件不會由垃圾郵件篩選器處理。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p122">On the **Allow Lists** page, you can specify entries, such as senders or domains, that will always be delivered to the inbox. Email from these entries is not processed by the spam filter.</span></span> 
    
  - <span data-ttu-id="e4b63-p123">將受信任的寄件者新增到寄件者允許清單。按一下 [ **新增**] ![加入圖示](media/ITPro-EAC-AddIcon.png)，然後在選取範圍對話方塊中新增您想要允許的寄件者地址。您可以使用分號或新行區隔多個項目。按一下 [確定] 回到 [ **允許清單**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p123">Add trusted senders to the Sender allow list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the sender addresses you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page.</span></span> 
    
  - <span data-ttu-id="e4b63-p124">將受信任的網域新增到網域允許清單。按一下 [ **新增**] ![加入圖示](media/ITPro-EAC-AddIcon.png)，然後在選取範圍對話方塊中新增您想要允許的網域。您可以使用分號或新行區隔多個項目。按一下 [確定] 回到 [ **允許清單**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p124">Add trusted domains to the Domain allow list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the domains you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="e4b63-187">如果您允許頂層網域，您不想要的電子郵件可能會傳遞至收件匣。</span><span class="sxs-lookup"><span data-stu-id="e4b63-187">If you allow top-level domains, it's likely that email you don't want will be delivered to an inbox.</span></span> 
  
8. <span data-ttu-id="e4b63-p125">您可在 「**國際垃圾郵件**」 頁面上篩選以特定語言編寫或寄自特定國家或地區的電子郵件訊息。您可以設定最多 86 不同語言和 250 不同的區域。此服務會套用高信賴垃圾郵件設定] 動作。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p125">On the **International Spam** page you can filter email messages that are written in specific languages or sent from specific countries or regions. You can configure up to 86 different languages and 250 different regions. The service will apply the configured action for high-confidence spam.</span></span> 
    
1. <span data-ttu-id="e4b63-p126">選取 [**以下列語言撰寫的篩選器電子郵件**] 核取方塊以啟用此功能。按一下 [![新增圖示](media/ITPro-EAC-AddIcon.png)，然後在選取項目] 對話方塊中，進行您 （支援多重選取項目） 的選擇。例如，如果您選取篩選郵件寫入在阿拉伯文 (AR)，和**隔離郵件**是您設定高信賴垃圾郵件] 動作，將隔離阿拉伯文中寫入任何郵件。按一下 [**確定]** 回到 [**國際垃圾郵件**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p126">Select the **Filter email messages written in the following languages** check box to enable this functionality. Click ![Add Icon](media/ITPro-EAC-AddIcon.png), and then, in the selection dialog box, make your choices (multi-selection is supported). For example, if you select to filter messages written in Arabic (AR), and **Quarantine message** is your configured action for high confidence spam messages, any messages written in Arabic will be quarantined. Click **ok** to return to the **International Spam** pane.</span></span> 
    
2. <span data-ttu-id="e4b63-p127">選取 [**從下列的國家或地區的篩選電子郵件傳送**] 核取方塊以啟用此功能。按一下 [![新增圖示](media/ITPro-EAC-AddIcon.png)，然後在選取項目] 對話方塊中，進行您 （支援多重選取項目） 的選擇。例如，如果您選取篩選出傳送從澳洲 (AU)，所有郵件和**隔離郵件**是您設定巨集指令的高信賴垃圾郵件，則任何郵件從澳洲傳送會被隔離。按一下 [**確定]** 回到 [**國際垃圾郵件**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p127">Select the **Filter email messages sent from the following countries or regions** check box to enable this functionality. Click ![Add Icon](media/ITPro-EAC-AddIcon.png), and then, in the selection dialog box, make your choices (multi-selection is supported). For example, if you select to filter all messages that are sent from Australia (AU), and **Quarantine message** is your configured action for high-confidence spam messages, then any messages that is sent from Australia will be quarantined. Click **ok** to return to the **International Spam** pane.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e4b63-p128">如果未選取國際垃圾郵件選項，則服務預設會對以所有語言傳送以及來自所有地區的郵件執行標準垃圾郵件篩選。郵件會經過分析，並在經判定為垃圾郵件或高信賴度垃圾郵件時，套用設定的動作。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p128">By default, if no international spam options are selected, the service performs normal spam filtering on messages sent in all languages and from all regions. Messages are analyzed and the configured actions are applied if the message is determined to be spam or high confidence spam.</span></span> 
  
9. <span data-ttu-id="e4b63-201">在 [**進階選項**] 頁面上，您可以選取**上**、**關閉**，或**測試**的每個進階垃圾郵件篩選選項。</span><span class="sxs-lookup"><span data-stu-id="e4b63-201">On the **Advanced Options** page, you can select **On**, **Off**, or **Test** for each advanced spam filtering option.</span></span> 
    
1. <span data-ttu-id="e4b63-p129">**在**郵件進行主動篩選根據該選項與相關聯的規則。訊息也會標示為垃圾郵件或將會有其垃圾郵件分數增加，根據哪些選項您開啟。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p129">**On** Messages are actively filtered according to the rule that is associated with that option. Messages are either marked as spam or will have their spam scores increased, depending on which options you turn on.</span></span> 
    
2. <span data-ttu-id="e4b63-p130">**關閉** 不會對符合垃圾郵件篩選條件的郵件採取任何動作。預設會關閉所有選項。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p130">**Off** No action is taken on messages that meet the spam filter criteria. All options are turned off by default.</span></span> 
    
3. <span data-ttu-id="e4b63-p131">**測試**在符合垃圾郵件篩選條件的郵件不採取任何動作。透過之前他們會傳遞至預定的收件者新增 x-header 但已標記的郵件。此 x-header 可讓您知道哪個 ASF 選項已符合。如果您指定**測試**任何進階選項，您可以設定相符項目進行測試已啟用] 選項時要套用的下列測試模式設定：</span><span class="sxs-lookup"><span data-stu-id="e4b63-p131">**Test** No action is taken on messages that meet the spam filter criteria. However, messages can be tagged by adding an X-header before they are delivered to the intended recipient. This X-header lets you know which ASF option was matched. If you specified **Test** for any of the advanced options, you can configure the following test mode settings to be applied when a match is made to a test-enabled option:</span></span> 
    
  - <span data-ttu-id="e4b63-p132">**無** 不對郵件採取任何測試模式動作。此為預設值。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p132">**None** Take no test mode action on the message. This is the default.</span></span> 
    
  - <span data-ttu-id="e4b63-212">**新增預設測試 x-header 文字**選取此選項可將郵件傳送給指定的收件者，但也將特殊的 x-header 新增至識別為具有符合特定的進階垃圾郵件篩選選項的訊息。</span><span class="sxs-lookup"><span data-stu-id="e4b63-212">**Add the default test X-header text** Selecting this option sends the message to the specified recipients, but also adds a special X-header to the message to identify it as having matched a specific advanced spam filtering option.</span></span> 
    
  - <span data-ttu-id="e4b63-213">**傳送密件副本郵件到這個地址**選取此選項將郵件的密件副本傳送給您在 [輸入] 方塊中指定的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e4b63-213">**Send a Bcc message to this address** Selecting this option sends a blind carbon copy of the message to the email address that you specify in the input box.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="e4b63-214">如需進階垃圾郵件篩選選項，包括說明每個、 相關聯的 x-header 文字及每個選項的詳細資訊請參閱[進階垃圾郵件篩選選項](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="e4b63-214">For more information about the advanced spam filtering options, including descriptions about each option and the X-header text that is associated with each one, see [Advanced spam filtering  options](advanced-spam-filtering-asf-options.md).</span></span> 
  
10. <span data-ttu-id="e4b63-p133">自訂原則只，按一下 [**套用]** 功能表項目，並再建立 [條件式規則以指定的使用者、 群組及要套用此原則的網域。他們是唯一可以建立多個條件。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p133">For custom policies only, click the **Apply to** menu item, and then create a condition-based rule to specify the users, groups, and domains to which to apply this policy. You can create multiple conditions, if they are unique.</span></span> 
    
  - <span data-ttu-id="e4b63-p134">若要選取的使用者，請選取 [**收件者**。在隨後出現的對話方塊中，從您的公司從使用者選擇清單中選取一或多個寄件者] 和 [**新增**。若要新增寄件者不在清單上，輸入其電子郵件地址，然後按一下 [**檢查名稱**。在此方塊中，您也可以使用萬用字元的多個電子郵件地址 (例如： \* @  _domainname_)。當您完成進行選取，按一下 [**確定]** 回到主畫面。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p134">To select users, select **The recipient is**. In the subsequent dialog box, select one or more senders from your company from the user picker list, and then click **add**. To add senders who aren't on the list, type their email addresses, and then click **Check names**. In this box, you can also use wildcards for multiple email addresses (for example: \*@ _domainname_). When you are done making your selections, click **ok** to return to the main screen.</span></span> 
    
  - <span data-ttu-id="e4b63-p135">若要選取群組，選取**收件者的成員**。然後，在隨後出現的對話方塊中，選取或指定群組。按一下 [**確定]** 回到主畫面。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p135">To select groups, select **The recipient is a member of**. Then, in the subsequent dialog box, select or specify the groups. Click **ok** to return to the main screen.</span></span> 
    
  - <span data-ttu-id="e4b63-p136">若要選取的網域，請選取 [**收件者的網域是**。然後，在隨後出現的對話方塊中，新增網域。按一下 [**確定]** 回到主畫面。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p136">To select domains, select **The recipient domain is**. Then, in the subsequent dialog box, add the domains. Click **ok** to return to the main screen.</span></span> 
    
    <span data-ttu-id="e4b63-p137">您可以建立內之規則的例外狀況。例如，您可以篩選來自但不包括在特定網域的所有網域的郵件。按一下 [**新增例外狀況**，然後再建立例外條件類似於您建立其他條件的方式。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p137">You can create exceptions within the rule. For example, you can filter messages from all domains except for a certain domain. Click **add exception**, and then create your exception conditions similar to the way that you created the other conditions.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e4b63-231">將垃圾郵件原則套用至群組僅適用於**擁有郵件功能的安全群組**的支援。</span><span class="sxs-lookup"><span data-stu-id="e4b63-231">Applying a spam policy to a group is supported only for **Mail Enabled Security Groups**.</span></span> 
  
11. <span data-ttu-id="e4b63-p138">按一下 **[儲存]**。原則設定的摘要隨即出現在右側窗格中。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p138">Click **save**. A summary of your policy settings appears in the right pane.</span></span>
    
> [!TIP]
>  <span data-ttu-id="e4b63-p139">您可以選取或清除核取方塊以啟用或停用您的自訂原則的 [**啟用**] 欄中。根據預設，會啟用所有原則。無法停用預設原則。> 若要刪除的自訂原則，請選取的原則，按一下 [![刪除圖示](media/ITPro-EAC-DeleteIcon.png)**刪除**圖示，然後確認您想要刪除之原則。無法刪除預設原則。> 自訂原則一律優先預設原則。自訂原則執行相反順序在其中建立它們 （從最舊到最新），但您可以依序按一下 [變更您的自訂原則的優先順序 （執行順序）![向上箭號圖示](media/ITPro-EAC-UpArrowIcon.png)向上鍵及![向下箭號圖示](media/ITPro-EAC-DownArrowIcon.png)向下箭號。具有**優先順序** **0**的原則將會執行第一筆、 後面接著**1**，則**2**，依此類推。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p139">You can select or clear the check boxes in the **ENABLED** column to enable or disable your custom policies. By default, all policies are enabled. The default policy cannot be disabled. >  To delete a custom policy, select the policy, click the ![Delete icon](media/ITPro-EAC-DeleteIcon.png) **Delete** icon, and then confirm that you want to delete the policy. The default policy cannot be deleted. >  Custom policies always take precedence over the default policy. Custom policies run in the reverse order in which you created them (from oldest to newest), but you can change the priority (running order) of your custom policies by clicking the ![Up Arrow Icon](media/ITPro-EAC-UpArrowIcon.png) up arrow and ![Down Arrow Icon](media/ITPro-EAC-DownArrowIcon.png) down arrow. The policy that has a **PRIORITY** of **0** will run first, followed by **1**, then **2**, and so on.</span></span> 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a><span data-ttu-id="e4b63-242">使用遠端 PowerShell 設定垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="e4b63-242">Use remote PowerShell to configure spam filter policies</span></span>
<span data-ttu-id="e4b63-243"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="e4b63-243"></span></span>

<span data-ttu-id="e4b63-p140">您也可以設定並套用 PowerShell 中的垃圾郵件篩選器原則。若要了解如何使用 Windows PowerShell 連線至 Exchange Online，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。若要了解如何使用 Windows PowerShell 連線至 Exchange Online Protection，請參閱[Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p140">You can also configure and apply spam filter policies in PowerShell. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554). To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span>
  
- <span data-ttu-id="e4b63-247">[Get-HostedContentFilterPolicy](http://technet.microsoft.com/library/d510471a-dda5-4df7-b3f8-2ee7a1948436.aspx) 檢視您的垃圾郵件篩選設定。</span><span class="sxs-lookup"><span data-stu-id="e4b63-247">[Get-HostedContentFilterPolicy](http://technet.microsoft.com/library/d510471a-dda5-4df7-b3f8-2ee7a1948436.aspx) View your spam filter settings.</span></span> 
    
- <span data-ttu-id="e4b63-248">[Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) 編輯您的垃圾郵件篩選設定。</span><span class="sxs-lookup"><span data-stu-id="e4b63-248">[Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) Edit your spam filter settings.</span></span> 
    
- <span data-ttu-id="e4b63-249">[New-HostedContentFilterPolicy](http://technet.microsoft.com/library/4d15128d-9e16-42a1-8ac5-36f07d4bbbf0.aspx) 建立新的自訂垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="e4b63-249">[New-HostedContentFilterPolicy](http://technet.microsoft.com/library/4d15128d-9e16-42a1-8ac5-36f07d4bbbf0.aspx) Create a new custom spam filter policy.</span></span> 
    
- <span data-ttu-id="e4b63-250">[Remove-HostedContentFilterPolicy](http://technet.microsoft.com/library/9fe1fe03-8f83-41e3-9bf5-084a392784d6.aspx) 刪除新的自訂垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="e4b63-250">[Remove-HostedContentFilterPolicy](http://technet.microsoft.com/library/9fe1fe03-8f83-41e3-9bf5-084a392784d6.aspx) Delete a custom spam filter policy.</span></span> 
    
<span data-ttu-id="e4b63-p141">若要將自訂垃圾郵件篩選原則套用至使用者、群組和 (或) 網域，請使用 [New-HostedContentFilterRule](http://technet.microsoft.com/library/2df13ba9-1eb0-4da3-bd72-a79d5fa15e26.aspx) Cmdlet (建立可套用至自訂原則的新篩選規則) 或 [Set-HostedContentFilterRule](http://technet.microsoft.com/library/ba259260-ffd3-43f3-8ef4-9d8659679d02.aspx) Cmdlet (編輯可套用至自訂原則的現有篩選規則)。使用 [Enable-HostedContentFilterRule](http://technet.microsoft.com/library/354ece28-dcde-4b5f-88ed-475115e7ea78.aspx) Cmdlet或 [Disable-HostedContentFilterRule](http://technet.microsoft.com/library/c1f8dafc-ef5d-47e3-b0fb-71a88e145fc5.aspx) Cmdlet 可以啟用或停用對原則套用的規則。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p141">To apply a custom spam filter policy to users, groups, and/or domains, use the [New-HostedContentFilterRule](http://technet.microsoft.com/library/2df13ba9-1eb0-4da3-bd72-a79d5fa15e26.aspx) cmdlet (to create a new filter rule that can be applied to custom policies) or the [Set-HostedContentFilterRule](http://technet.microsoft.com/library/ba259260-ffd3-43f3-8ef4-9d8659679d02.aspx) cmdlet (to edit an existing filter rule that can be applied to custom policies). Use the [Enable-HostedContentFilterRule](http://technet.microsoft.com/library/354ece28-dcde-4b5f-88ed-475115e7ea78.aspx) cmdlet or the [Disable-HostedContentFilterRule](http://technet.microsoft.com/library/c1f8dafc-ef5d-47e3-b0fb-71a88e145fc5.aspx) cmdlet to enable or disable the rule applied to the policy.</span></span> 
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e4b63-253">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="e4b63-253">How do you know this worked?</span></span>
<span data-ttu-id="e4b63-254"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="e4b63-254"></span></span>

<span data-ttu-id="e4b63-p142">若要確保已針對垃圾郵件進行適當偵測和採取行動，可以透過服務傳送 GTUBE 訊息。GTUBE 與 EICAR 防毒測試檔案類似，GTUBE 提供了一項測試，您可以用來確認服務正在偵測進入的垃圾郵件。GTUBE 訊息應該一律被垃圾郵件篩選器偵測為垃圾郵件，且對郵件執行的動作應該符合您進行的設定。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p142">To ensure that spam is being properly detected and acted upon, you can send a GTUBE message through the service. Similar to the EICAR antivirus test file, GTUBE provides a test by which you can verify that the service is detecting incoming spam. A GTUBE message should always be detected as spam by the spam filter, and the actions that are performed upon the message should match your configured settings.</span></span>
  
<span data-ttu-id="e4b63-258">請在郵件訊息中，將下列 GTUBE 文字包含在單一行上，不加任何空格或換行：</span><span class="sxs-lookup"><span data-stu-id="e4b63-258">Include the following GTUBE text in a mail message on a single line, without any spaces or line breaks:</span></span>
  
```
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="fine-tuning-your-spam-filter-policy-to-prevent-false-positives-and-false-negatives"></a><span data-ttu-id="e4b63-259">調整您的垃圾郵件篩選原則，以避免誤判和漏報</span><span class="sxs-lookup"><span data-stu-id="e4b63-259">Fine tuning your spam filter policy to prevent false positives and false negatives</span></span>
<span data-ttu-id="e4b63-260"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="e4b63-260"></span></span>

<span data-ttu-id="e4b63-p143">如果想要使用積極的垃圾郵件篩選方法，您可以啟用進階的垃圾郵件篩選選項。如需套用至整個組織的一般垃圾郵件設定，請參閱[使用安全清單或其他技術防止誤判電子郵件標示為垃圾郵件](https://go.microsoft.com/fwlink/p/?LinkId=534224)，或[使用 Office 365 垃圾郵件篩選器封鎖垃圾郵件以避免漏報問題](https://go.microsoft.com/fwlink/p/?LinkId=534225)。如果您有系統管理員層級的控制權，且您想要避免誤判或漏報，這些內容很有幫助。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p143">You can enable advanced spam filtering options if you want to pursue an aggressive approach to spam filtering. For general spam settings that apply to the whole organization, take a look at [Prevent false positive email marked as spam with a safelist or other techniques](https://go.microsoft.com/fwlink/p/?LinkId=534224) or [Block email spam with the Office 365 spam filter to prevent false negative issues](https://go.microsoft.com/fwlink/p/?LinkId=534225). These are helpful if you have administrator-level control and you want to prevent false positives or false negatives.</span></span>
  
## <a name="new-to-office-365"></a><span data-ttu-id="e4b63-264">初次使用 Office 365 嗎？</span><span class="sxs-lookup"><span data-stu-id="e4b63-264">New to Office 365?</span></span>
<span data-ttu-id="e4b63-265"><a name="sectionSection5"> </a></span><span class="sxs-lookup"><span data-stu-id="e4b63-265"></span></span>

||
|:-----|
|<span data-ttu-id="e4b63-p144">![LinkedIn Learning 的短圖示](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **初次使用 Office 365？**         探索 LinkedIn Learning 提供的 **Office 365 admins and IT pros** 免費影片課程。</span><span class="sxs-lookup"><span data-stu-id="e4b63-p144">![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span> |
   
## <a name="for-more-information"></a><span data-ttu-id="e4b63-268">相關資訊</span><span class="sxs-lookup"><span data-stu-id="e4b63-268">For more information</span></span>
<span data-ttu-id="e4b63-269"><a name="sectionSection6"> </a></span><span class="sxs-lookup"><span data-stu-id="e4b63-269"></span></span>

[<span data-ttu-id="e4b63-270">設定連線篩選原則</span><span class="sxs-lookup"><span data-stu-id="e4b63-270">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="e4b63-271">設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="e4b63-271">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="e4b63-272">隔離</span><span class="sxs-lookup"><span data-stu-id="e4b63-272">Quarantine</span></span>](quarantine.md)
  
[<span data-ttu-id="e4b63-273">使用安全清單或其他技術防止誤判電子郵件標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="e4b63-273">Prevent false positive email marked as spam with a safelist or other techniques</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[<span data-ttu-id="e4b63-274">利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件以避免誤判正常</span><span class="sxs-lookup"><span data-stu-id="e4b63-274">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

