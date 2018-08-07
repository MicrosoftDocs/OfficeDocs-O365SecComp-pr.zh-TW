---
title: 使用以查看您的使用者會報告給 Microsoft 的郵件流程規則
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: 您可以建立 Exchange 傳輸規則，以防止使用者傳送電子郵件訊息給 Microsoft 進行分析並用於您自己的安全性程序
ms.openlocfilehash: 6c6af23e6a5f345e26c7dc09c898f2978ea51a5f
ms.sourcegitcommit: df1e9590a9fa152fa776f16d9b25c180ba7198f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2018
ms.locfileid: "22122583"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="42de5-103">使用以查看您的使用者會報告給 Microsoft 的郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="42de5-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="42de5-p101">有多個您可以傳送正誤差與 false 誤判正常的郵件給 Microsoft 進行分析的方式。身為管理員，您可以使用郵件流程規則以查看新使用者會向 Microsoft 回報垃圾郵件、 非垃圾郵件和網路釣魚詐騙。如需詳細資訊，請參閱[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件訊息給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。相反地，您可以建立 Exchange 傳輸規則，以防止使用者傳送電子郵件訊息給 Microsoft 進行分析並用於您自己的安全性程序。</span><span class="sxs-lookup"><span data-stu-id="42de5-p101">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis. As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams. For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Conversely, you can create an Exchange Transport rule to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="42de5-108">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="42de5-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="42de5-109">預估完成時間：5 分鐘</span><span class="sxs-lookup"><span data-stu-id="42de5-109">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="42de5-p102">您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[訊息原則及符合性權限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主題中的 「 傳輸規則 」 項目和[用戶端和行動裝置權限](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx)主題中的 「 Outlook Web App 信箱原則 」 項目。</span><span class="sxs-lookup"><span data-stu-id="42de5-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook Web App mailbox policies" entry in the [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic.</span></span> 
  
<span data-ttu-id="42de5-112">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。</span><span class="sxs-lookup"><span data-stu-id="42de5-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="42de5-113">使用 EAC 來建立檢視使用者手動垃圾郵件]、 [網路釣魚、 及 [不是垃圾郵件報告的郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="42de5-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="42de5-114">在 EAC 中，瀏覽至 **[郵件流程]** \> **[規則]**。</span><span class="sxs-lookup"><span data-stu-id="42de5-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="42de5-115">按一下 ![加入圖示](media/ITPro-EAC-AddIcon.png)，然後選取 **[建立新的規則]**。</span><span class="sxs-lookup"><span data-stu-id="42de5-115">Click ![Add Icon](media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="42de5-116">命名規則，然後按一下 **[更多選項]**。</span><span class="sxs-lookup"><span data-stu-id="42de5-116">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="42de5-117">在 **[套用此規則，如果]** 下選取 **[收件者]**，然後選擇 **[位址包含任何這些文字]**。</span><span class="sxs-lookup"><span data-stu-id="42de5-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>
    
5. <span data-ttu-id="42de5-118">在 **[指定單字或片語]** 方塊中，執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="42de5-118">In the **specify words or phrases** box, do the following:</span></span> 
    - <span data-ttu-id="42de5-p103">類型`abuse@messaging.microsoft.com`] 和 [![新增圖示](media/ITPro-EAC-AddIcon.png)，然後輸入`junk@office365.microsoft.com`] 和 [![新增圖示](media/ITPro-EAC-AddIcon.png)。這些電子郵件地址用來提交誤判正常的郵件給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="42de5-p103">Type `abuse@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.png), and then type `junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.png). These email addresses are used to submit false negative messages to Microsoft.</span></span>
    - <span data-ttu-id="42de5-p104">類型`phish@office365.microsoft.com`] 和 [![新增圖示](media/ITPro-EAC-AddIcon.png)。此電子郵件地址用來送出未接的網路釣魚訊息給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="42de5-p104">Type `phish@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.png). This email address is used to submit missed phishing messages to Microsoft.</span></span>
    - <span data-ttu-id="42de5-p105">類型`false_positive@messaging.microsoft.com`] 和 [![新增圖示](media/ITPro-EAC-AddIcon.png)，然後輸入`not_junk@office365.microsoft.com`] 和 [![新增圖示](media/ITPro-EAC-AddIcon.png)。這些電子郵件地址用來提交誤判的郵件給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="42de5-p105">Type `false_positive@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.png), and then type `not_junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.png). These email addresses are used to submit false positive messages to Microsoft.</span></span>
    - <span data-ttu-id="42de5-125">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="42de5-125">Click **ok**.</span></span>
    
6. <span data-ttu-id="42de5-126">在 [**執行下列動作**，選取 [ **[密件副本郵件至...** 與您想要的信箱然後，然後選取 [接收的郵件。</span><span class="sxs-lookup"><span data-stu-id="42de5-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span> 
    
7. <span data-ttu-id="42de5-p106">如果您想要您可以讓選取項目稽核規則、 測試規則、 特定時間期間啟動規則和其他選取項目。建議您測試一段之前您強制執行規則。請參閱[mail flow 規則的程序](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)。</span><span class="sxs-lookup"><span data-stu-id="42de5-p106">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period before you enforce it. See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span> 
    
8. <span data-ttu-id="42de5-p107">按一下 **[儲存]** 按鈕儲存規則。它就會出現在規則清單中。</span><span class="sxs-lookup"><span data-stu-id="42de5-p107">Click the **save** button to save the rule. It appears in your list of rules.</span></span> 
    
<span data-ttu-id="42de5-132">建立並強制執行規則後，從組織傳送至指定的電子郵件地址的任何郵件會複製到指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="42de5-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
  

