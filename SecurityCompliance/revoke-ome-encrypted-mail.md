---
title: 撤銷由 Office 365 郵件加密所加密的電子郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 是 Office 365 系統管理員，您可以撤銷某些使用 Office 365 郵件加密所加密的電子郵件。
ms.openlocfilehash: 75b5e46e25f447ddac0de5a7911d0df8385da6b9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264818"
---
# <a name="office-365-message-encryption-email-revocation"></a><span data-ttu-id="9a631-103">Office 365 郵件加密的電子郵件被撤銷</span><span class="sxs-lookup"><span data-stu-id="9a631-103">Office 365 Message Encryption email revocation</span></span>

<span data-ttu-id="9a631-104">本文屬於較大的一連串的[Office 365 郵件加密](ome.md)的相關文章。</span><span class="sxs-lookup"><span data-stu-id="9a631-104">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="9a631-105">現在右、 加密的電子郵件被撤銷處於預覽狀態。</span><span class="sxs-lookup"><span data-stu-id="9a631-105">Right now, encrypted email revocation is in preview.</span></span> <span data-ttu-id="9a631-106">預期更新和變更功能和內容，因為我們繼續改善我們供應項目。</span><span class="sxs-lookup"><span data-stu-id="9a631-106">Expect updates and changes to the feature and the content as we continue to improve our offering.</span></span>

<span data-ttu-id="9a631-107">您可能會發現不必撤銷已經傳送一封電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9a631-107">You may find it necessary to revoke an email that has already been sent.</span></span> <span data-ttu-id="9a631-108">如果使用 Office 365 郵件加密，加密電子郵件，而您是 Office 365 系統管理員，您可以在某些情況下的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9a631-108">If the email was encrypted using Office 365 Message Encryption, and you are an Office 365 admin, you can do this for email under certain conditions.</span></span> <span data-ttu-id="9a631-109">本文說明 [這是可能何種情況下，以及如何這樣做。</span><span class="sxs-lookup"><span data-stu-id="9a631-109">This article describes under what circumstances this is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="9a631-110">您可以撤銷的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="9a631-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="9a631-111">如果收件者收到連結為基礎，品牌加密的電子郵件，您可以撤銷加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9a631-111">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="9a631-112">如果收件者收到的原生內嵌體驗中支援的 Outlook 用戶端，無法撤銷這些電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9a631-112">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="9a631-113">收件者收到的連結為基礎的體驗還是內嵌經驗會視收件者的身分識別類型而定： Office 365 和 Microsoft 帳戶收件者 （例如，outlook.com 使用者） 中支援的 Outlook 用戶端取得內嵌體驗。</span><span class="sxs-lookup"><span data-stu-id="9a631-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="9a631-114">所有其他收件者類型，例如 Gmail 收件者，取得連結為基礎的體驗。</span><span class="sxs-lookup"><span data-stu-id="9a631-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

<span data-ttu-id="9a631-115">即將推出，組織會有強制連結為基礎的經驗，無論收件者的身分識別的能力。</span><span class="sxs-lookup"><span data-stu-id="9a631-115">Coming soon, organizations will have the ability to force a link-based experience regardless of the recipient identity.</span></span> <span data-ttu-id="9a631-116">如此一來，所有收件者會收到包含連結至 Office 365 郵件加密入口網站，他們將可以閱讀和回覆加密的電子郵件的品牌電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9a631-116">This way, all recipients will get a branded email with a link to the Office 365 Message Encryption portal where they will be able to read and reply to encrypted emails.</span></span> <span data-ttu-id="9a631-117">所有這類加密的電子郵件將會是可撤銷之。</span><span class="sxs-lookup"><span data-stu-id="9a631-117">All such encrypted emails will be revocable.</span></span>
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="9a631-118">撤銷已加密的電子郵件的收件者體驗</span><span class="sxs-lookup"><span data-stu-id="9a631-118">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="9a631-119">嘗試透過 Office 365 郵件加密入口網站存取加密的電子郵件時，收件者之後已撤銷電子郵件，會收到錯誤: 「 寄件者，該訊息已被撤銷 」。</span><span class="sxs-lookup"><span data-stu-id="9a631-119">Once an email has been revoked, the recipient will get an error when trying to access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![螢幕擷取畫面顯示 [撤銷加密的電子郵件。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="9a631-121">若要撤銷加密的電子郵件的方式</span><span class="sxs-lookup"><span data-stu-id="9a631-121">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="9a631-122">步驟 1。</span><span class="sxs-lookup"><span data-stu-id="9a631-122">Step 1.</span></span> <span data-ttu-id="9a631-123">取得電子郵件訊息識別碼</span><span class="sxs-lookup"><span data-stu-id="9a631-123">Obtain the Message ID of the email</span></span>

<span data-ttu-id="9a631-124">您可以撤銷加密的郵件之前您需要收集郵件訊息識別碼。</span><span class="sxs-lookup"><span data-stu-id="9a631-124">Before you can revoke an encrypted mail you need to gather the Message ID of the mail.</span></span> <span data-ttu-id="9a631-125">MessageId 通常是的格式：</span><span class="sxs-lookup"><span data-stu-id="9a631-125">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="9a631-126">有多種方式來尋找您想要撤銷的電子郵件訊息識別碼。</span><span class="sxs-lookup"><span data-stu-id="9a631-126">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="9a631-127">本小節會說明兩個選項，但您可以使用任何方法，提供識別碼。</span><span class="sxs-lookup"><span data-stu-id="9a631-127">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="9a631-128">若要找出您想要撤銷安全性使用郵件追蹤的電子郵件訊息識別碼&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="9a631-128">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="9a631-129">搜尋由寄件者或收件者使用[新的郵件追蹤，在 Office 365 安全性 & 合規性中心中](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9a631-129">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>
2. <span data-ttu-id="9a631-130">一旦您已經找到電子郵件選取它帶出 [**郵件追蹤詳細資料**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="9a631-130">Once you've located the email select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="9a631-131">依序展開 [**更多的資訊**來找出郵件的識別碼。</span><span class="sxs-lookup"><span data-stu-id="9a631-131">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="9a631-132">若要找出您想要使用 Office 郵件加密報告安全性撤銷電子郵件訊息識別碼&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="9a631-132">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="9a631-133">安全性&amp;合規性中心，瀏覽至**郵件加密報告**。</span><span class="sxs-lookup"><span data-stu-id="9a631-133">In the Security &amp; Compliance Center, navigate to the **Message Encryption Report**.</span></span>
2. <span data-ttu-id="9a631-134">選擇 [**檢視詳細資料]** 表格，並找出您想要撤銷的訊息。</span><span class="sxs-lookup"><span data-stu-id="9a631-134">Choose the **View details** table and identify the message that you want to revoke.</span></span>
3. <span data-ttu-id="9a631-135">按兩下 [檢視詳細資料] 包含郵件識別碼訊息</span><span class="sxs-lookup"><span data-stu-id="9a631-135">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="9a631-136">步驟 2。</span><span class="sxs-lookup"><span data-stu-id="9a631-136">Step 2.</span></span> <span data-ttu-id="9a631-137">確認便可撤銷之電子郵件</span><span class="sxs-lookup"><span data-stu-id="9a631-137">Verify that the mail is revocable</span></span>

<span data-ttu-id="9a631-138">若要確認您可以撤銷將特定電子郵件，完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="9a631-138">To verify whether or not you can revoke a particular email message, complete these steps.</span></span>

1. <span data-ttu-id="9a631-139">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9a631-139">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9a631-140">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="9a631-140">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9a631-141">執行設定 OMEMessageStatus 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9a631-141">Run the Set-OMEMessageStatus cmdlet as follows:</span></span>
     ```powershell
     Get-OMEMessageStatus -MessageId "<messagieid>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="9a631-142">這會傳回郵件以及是否可撤銷之郵件的主旨。</span><span class="sxs-lookup"><span data-stu-id="9a631-142">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="9a631-143">For example,</span><span class="sxs-lookup"><span data-stu-id="9a631-143">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="9a631-144">步驟 3。</span><span class="sxs-lookup"><span data-stu-id="9a631-144">Step 3.</span></span> <span data-ttu-id="9a631-145">撤銷郵件</span><span class="sxs-lookup"><span data-stu-id="9a631-145">Revoke the mail</span></span>  

<span data-ttu-id="9a631-146">一旦您知道想要撤銷，請將電子郵件訊息識別碼，並確認郵件可撤銷之，您可以利用組 OMEMessageRevocation 指令程式撤銷電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9a631-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="9a631-147">[連線至 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="9a631-147">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9a631-148">執行設定 OMEMessageRevocation 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9a631-148">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="9a631-149">若要檢查是否已撤銷電子郵件，請執行 Get OMEMessageStatus 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9a631-149">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```  
    <span data-ttu-id="9a631-150">如果撤銷成功，cmdlet 就會傳回下列結果：</span><span class="sxs-lookup"><span data-stu-id="9a631-150">If revocation was successful, the cmdlet returns the following result:</span></span>  

    `Revoked: True`
