---
title: 使用郵件流程規則來查看您的使用者報告給 Microsoft 哪些內容
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 您可以建立 Exchange 郵件流程規則，以防止使用者將電子郵件訊息傳送給 Microsoft 進行分析，並在您自己的安全性程序中使用它們
ms.openlocfilehash: 0086cf048dcffa912085f23b328ab1d51780f0df
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156135"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="8ccc5-103">使用郵件流程規則來查看您的使用者報告給 Microsoft 哪些內容</span><span class="sxs-lookup"><span data-stu-id="8ccc5-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="8ccc5-104">有多種方法可以將誤判和誤判正常郵件傳送給 Microsoft，以進行分析。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-104">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis.</span></span> <span data-ttu-id="8ccc5-105">身為管理員，您可以使用郵件流程規則來查看您的使用者會回報給 Microsoft 垃圾郵件、 非垃圾郵件和網路釣魚詐騙。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-105">As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams.</span></span> <span data-ttu-id="8ccc5-106">如需詳細資訊，請參閱[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-106">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> <span data-ttu-id="8ccc5-107">相反地，您可以建立 Exchange 郵件流程規則 （也稱為傳輸規則） 以防止使用者將電子郵件訊息傳送給 Microsoft 進行分析，並在您自己的安全性程序中使用它們。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-107">Conversely, you can create an Exchange mail flow rule (also known as a transport rule) to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8ccc5-108">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="8ccc5-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="8ccc5-109">預估完成時間：5 分鐘</span><span class="sxs-lookup"><span data-stu-id="8ccc5-109">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="8ccc5-110">您必須已獲指派權限，才能執行此程序或這些程序。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-110">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="8ccc5-111">若要查看您需要哪些權限，請參閱[訊息原則及符合性權限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主題中的 「 郵件流程規則 」 項目和[用戶端和行動裝置權限](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx)主題中的 「 Outlook web 信箱原則 」 項目。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-111">To see what permissions you need, see the "Mail flow rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook on the web mailbox policies" entry in the [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic.</span></span> 
  
<span data-ttu-id="8ccc5-112">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="8ccc5-113">使用 EAC 來建立郵件流程規則，以檢視使用者手動垃圾郵件、 網路釣魚，並不是垃圾郵件報告</span><span class="sxs-lookup"><span data-stu-id="8ccc5-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="8ccc5-114">在 EAC 中，瀏覽至 **[郵件流程]** \> **[規則]**。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="8ccc5-115">按一下 ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 **[建立新的規則]**。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-115">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="8ccc5-116">命名規則，然後按一下 **[更多選項]**。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-116">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="8ccc5-117">在 **[套用此規則，如果]** 下選取 **[收件者]**，然後選擇 **[位址包含任何這些文字]**。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>
    
5. <span data-ttu-id="8ccc5-118">在 **[指定單字或片語]** 方塊中，執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="8ccc5-118">In the **specify words or phrases** box, do the following:</span></span> 
    - <span data-ttu-id="8ccc5-119">型別`abuse@messaging.microsoft.com`，然後按一下 [![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後輸入`junk@office365.microsoft.com`，然後按一下 [![加入圖示](media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-119">Type `abuse@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="8ccc5-120">這些電子郵件地址可用來將誤判正常郵件提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-120">These email addresses are used to submit false negative messages to Microsoft.</span></span>
    - <span data-ttu-id="8ccc5-121">型別`phish@office365.microsoft.com`，然後按一下 [![加入圖示](media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-121">Type `phish@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="8ccc5-122">此電子郵件地址用來提交未接的網路釣魚郵件提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-122">This email address is used to submit missed phishing messages to Microsoft.</span></span>
    - <span data-ttu-id="8ccc5-123">型別`false_positive@messaging.microsoft.com`，然後按一下 [![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後輸入`not_junk@office365.microsoft.com`，然後按一下 [![加入圖示](media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-123">Type `false_positive@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `not_junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="8ccc5-124">這些電子郵件地址可用來將誤判郵件提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-124">These email addresses are used to submit false positive messages to Microsoft.</span></span>
    - <span data-ttu-id="8ccc5-125">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-125">Click **ok**.</span></span>
    
6. <span data-ttu-id="8ccc5-126">在 [**執行下列動作**，選取 [ **[密件副本郵件到...** ，然後，然後選取您想要的信箱接收郵件。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span> 
    
7. <span data-ttu-id="8ccc5-127">您也可以視需要選取稽核規則、測試規則、在特定期間啟動規則等等選項。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-127">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="8ccc5-128">施行規則之前，建議先測試規則一段時間。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-128">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="8ccc5-129">請參閱[郵件流程規則程序](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-129">See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span> 
    
8. <span data-ttu-id="8ccc5-130">按一下 **[儲存]** 按鈕儲存規則。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-130">Click the **save** button to save the rule.</span></span> <span data-ttu-id="8ccc5-131">它就會出現在規則清單中。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-131">It appears in your list of rules.</span></span> 
    
<span data-ttu-id="8ccc5-132">建立並強制執行規則後，從組織傳送至指定的電子郵件地址的任何郵件都會複製到指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="8ccc5-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
  

