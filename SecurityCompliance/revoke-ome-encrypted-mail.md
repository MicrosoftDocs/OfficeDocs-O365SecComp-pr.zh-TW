---
title: 撤消加密的 Office 365 郵件加密的電子郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/24/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
description: Office 365 系統管理員身分您可以撤銷已加密的 Office 365 郵件加密特定電子郵件。
ms.openlocfilehash: 19eb874fa15a21c29a9eb2823829e81ff244a555
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011819"
---
# <a name="office-365-message-encryption-email-revocation"></a><span data-ttu-id="f2f83-103">Office 365 郵件加密的電子郵件撤銷</span><span class="sxs-lookup"><span data-stu-id="f2f83-103">Office 365 Message Encryption email revocation</span></span>

<span data-ttu-id="f2f83-p101">本文屬於較大的一系列有關[Office 365 郵件加密](ome.md)的文章。現在右、 加密的電子郵件撤銷處於預覽。我們繼續提升我們可以如預期更新和變更功能和內容。</span><span class="sxs-lookup"><span data-stu-id="f2f83-p101">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md). Right now, encrypted email revocation is in preview. Expect updates and changes to the feature and the content as we continue to improve our offering.</span></span>

<span data-ttu-id="f2f83-p102">您可能會發現需要撤銷已送出之電子郵件。如果已加密的電子郵件使用 Office 365 郵件加密，而且您的 Office 365 系統管理員，您可以這麼做以在某些情況下電子郵件。本文說明 [這是可行何種情況和執行方式。</span><span class="sxs-lookup"><span data-stu-id="f2f83-p102">You may find it necessary to revoke an email that has already been sent. If the email was encrypted using Office 365 Message Encryption, and you are an Office 365 admin, you can do this for email under certain conditions. This article describes under what circumstances this is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="f2f83-110">您可以撤銷的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="f2f83-110">Encrypted emails that you can revoke</span></span>
<span data-ttu-id="f2f83-p103">如果收件者收到連結型、 具有品牌形象的加密的電子郵件，可以撤銷已加密的電子郵件。如果收件者收到的原生內嵌體驗中支援的 Outlook 用戶端，不會撤銷這些電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f2f83-p103">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email. If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="f2f83-113">收件者會收到連結型經驗還是內嵌經驗取決於收件者的身分識別類型： Office 365 及 Microsoft 帳戶收件者 （例如 outlook.com 使用者） 取得中支援的 Outlook 用戶端的內嵌經驗。</span><span class="sxs-lookup"><span data-stu-id="f2f83-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span>  
<span data-ttu-id="f2f83-114">所有其他收件者類型，例如 Gmail 收件者] 取得連結為基礎的體驗。</span><span class="sxs-lookup"><span data-stu-id="f2f83-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span> 

<span data-ttu-id="f2f83-p104">即將推出的組織必須強制不論收件者的身分識別的連結型經驗的能力。如此一來，所有收件者會取得加上品牌的電子郵件與其中他們將能夠讀取和回覆加密的電子郵件的 Office 365 郵件加密入口網站的連結。將可撤銷之所有這類加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f2f83-p104">Coming soon, organizations will have the ability to force a link-based experience regardless of the recipient identity. This way, all recipients will get a branded email with a link to the Office 365 Message Encryption portal where they will be able to read and reply to encrypted emails. All such encrypted emails will be revocable.</span></span> 
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="f2f83-118">撤銷已加密的電子郵件的收件者經驗</span><span class="sxs-lookup"><span data-stu-id="f2f83-118">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="f2f83-119">收件者之後已被撤銷電子郵件，將會在嘗試透過 Office 365 郵件加密入口網站存取加密的電子郵件時收到的錯誤： 「 寄件者，郵件已被撤銷"。</span><span class="sxs-lookup"><span data-stu-id="f2f83-119">Once an email has been revoked, the recipient will get an error when trying to access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![這個螢幕擷取畫面顯示撤銷加密的電子郵件。](media/revoked-encrypted-email.png)
    
## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="f2f83-121">若要撤銷加密的電子郵件的方式</span><span class="sxs-lookup"><span data-stu-id="f2f83-121">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="f2f83-p105">步驟 1。取得電子郵件訊息識別碼</span><span class="sxs-lookup"><span data-stu-id="f2f83-p105">Step 1. Obtain the Message ID of the email</span></span>

<span data-ttu-id="f2f83-p106">您可以撤銷已加密的郵件之前您必須收集郵件訊息識別碼。MessageId 通常是之格式的：</span><span class="sxs-lookup"><span data-stu-id="f2f83-p106">Before you can revoke an encrypted mail you need to gather the Message ID of the mail. The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="f2f83-p107">有多個方法來尋找您想要撤銷的電子郵件訊息識別碼。本節說明一些選項，但是您可以使用任何方法可提供 [識別碼]。</span><span class="sxs-lookup"><span data-stu-id="f2f83-p107">There are multiple ways to find the Message ID of the email that you want to revoke. This section describes a couple of options, but you can use any method that provides the ID.</span></span>

  #### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="f2f83-128">若要找出您想要撤銷安全性使用郵件追蹤電子郵件訊息識別碼&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="f2f83-128">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="f2f83-129">搜尋由寄件者或收件者使用[新的 Message Trace in Office 365 的安全性與規範中心](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f2f83-129">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>
2. <span data-ttu-id="f2f83-p108">一旦您已經找到電子郵件選取其相反的**郵件追蹤詳細資料**窗格。依序展開 [**更多的資訊**來找出郵件的識別碼。</span><span class="sxs-lookup"><span data-stu-id="f2f83-p108">Once you've located the email select it to bring up the **Message trace details** pane. Expand **More Information** to locate the Message ID.</span></span>

  #### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="f2f83-132">若要找出您想要撤銷安全性中使用 Office 郵件加密報告的電子郵件訊息識別碼&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="f2f83-132">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>
1. <span data-ttu-id="f2f83-133">安全性&amp;規範中心瀏覽至 [**郵件加密報告**。</span><span class="sxs-lookup"><span data-stu-id="f2f83-133">In the Security &amp; Compliance Center, navigate to the **Message Encryption Report**.</span></span>
2. <span data-ttu-id="f2f83-134">選擇 [**檢視詳細資料**] 表格，並找出您想要撤銷的訊息。</span><span class="sxs-lookup"><span data-stu-id="f2f83-134">Choose the **View details** table and identify the message that you want to revoke.</span></span> 
3. <span data-ttu-id="f2f83-135">按兩下 [檢視詳細資料] 包含郵件識別碼的訊息</span><span class="sxs-lookup"><span data-stu-id="f2f83-135">Double-click the message to view details that include the Message ID.</span></span> 

### <a name="step-2-revoke-the-mail"></a><span data-ttu-id="f2f83-p109">步驟 2。撤消郵件</span><span class="sxs-lookup"><span data-stu-id="f2f83-p109">Step 2. Revoke the mail</span></span>  

<span data-ttu-id="f2f83-138">一旦您知道您想要撤銷的電子郵件訊息識別碼，您可以使用組 OMEMessageRevocation 指令程式撤銷電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f2f83-138">Once you know the Message ID of the email you want to revoke, you can revoke the email by using the Set-OMEMessageRevocation cmdlet.</span></span> 

1. <span data-ttu-id="f2f83-139">[連線至 Exchange Online 使用遠端 PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="f2f83-139">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="f2f83-140">執行設定 OMEMessageRevocation 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f2f83-140">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>
    
    ```
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```  

3. <span data-ttu-id="f2f83-141">若要檢查是否已遭撤銷電子郵件，如下執行 Get OMEMessageStatus cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f2f83-141">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>
    
    ```
    Get-OMEMessageStatus -MessageId "<messageId>"
    ```  
    <span data-ttu-id="f2f83-142">如果撤銷成功，指令程式會傳回下列結果：</span><span class="sxs-lookup"><span data-stu-id="f2f83-142">If revocation was successful, the cmdlet returns the following result:</span></span>  

    ```The encrypted email with the subject "<subject>" and Message ID "<messageId>" was successfully revoked.```
