---
title: 撤銷由 Office 365 進階郵件加密所加密的電子郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 是 Office 365 系統管理員，您可以撤銷某些使用 Office 365 進階郵件加密所加密的電子郵件。
ms.openlocfilehash: 7135d2bdb35ddb4866499e66d53ea8d15a284b3d
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835107"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="d3d94-103">撤銷由 Office 365 進階郵件加密所加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="d3d94-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="d3d94-104">電子郵件被撤銷被提供作為 Office 365 進階郵件加密的一部分。</span><span class="sxs-lookup"><span data-stu-id="d3d94-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="d3d94-105">掌握 Office 365 郵件加密在特定的訂閱中使用 office 365 進階郵件加密。</span><span class="sxs-lookup"><span data-stu-id="d3d94-105">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="d3d94-106">進階的郵件加密包含在[Microsoft 365 企業版 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、 Office 365 企業版 E5 和 Office 365 教育版 A5 中。</span><span class="sxs-lookup"><span data-stu-id="d3d94-106">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="d3d94-107">如果貴組織擁有不包含 Office 365 進階郵件加密的 Office 365 訂閱，您可以以 E5 合規性的進階合規性 SKU 與附加元件形式購買進階郵件加密。</span><span class="sxs-lookup"><span data-stu-id="d3d94-107">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="d3d94-108">本文屬於較大的一連串的[Office 365 郵件加密](ome.md)的相關文章。</span><span class="sxs-lookup"><span data-stu-id="d3d94-108">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="d3d94-109">您可能會發現不必撤銷已經傳送一封電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d3d94-109">You may find it necessary to revoke an email that has already been sent.</span></span> <span data-ttu-id="d3d94-110">如果使用 Office 365 進階郵件加密，加密電子郵件，而您是 Office 365 系統管理員，您可以在某些情況下的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d3d94-110">If the email was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do this for email under certain conditions.</span></span> <span data-ttu-id="d3d94-111">本文說明 [這是可能何種情況下，以及如何這樣做。</span><span class="sxs-lookup"><span data-stu-id="d3d94-111">This article describes under what circumstances this is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="d3d94-112">您可以撤銷的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="d3d94-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="d3d94-113">如果收件者收到連結為基礎，品牌加密的電子郵件，您可以撤銷加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d3d94-113">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="d3d94-114">如果收件者收到的原生內嵌體驗中支援的 Outlook 用戶端，無法撤銷這些電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d3d94-114">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="d3d94-115">收件者收到的連結為基礎的體驗還是內嵌經驗會視收件者的身分識別類型而定： Office 365 和 Microsoft 帳戶收件者 （例如，outlook.com 使用者） 中支援的 Outlook 用戶端取得內嵌體驗。</span><span class="sxs-lookup"><span data-stu-id="d3d94-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="d3d94-116">所有其他收件者類型，例如 Gmail 收件者，取得連結為基礎的體驗。</span><span class="sxs-lookup"><span data-stu-id="d3d94-116">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="d3d94-117">撤銷已加密的電子郵件的收件者體驗</span><span class="sxs-lookup"><span data-stu-id="d3d94-117">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="d3d94-118">嘗試透過 Office 365 郵件加密入口網站存取加密的電子郵件時，收件者之後已撤銷電子郵件，會收到錯誤: 「 寄件者，該訊息已被撤銷 」。</span><span class="sxs-lookup"><span data-stu-id="d3d94-118">Once an email has been revoked, the recipient will get an error when trying to access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![螢幕擷取畫面顯示 [撤銷加密的電子郵件。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="d3d94-120">若要撤銷加密的電子郵件的方式</span><span class="sxs-lookup"><span data-stu-id="d3d94-120">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="d3d94-121">步驟 1。</span><span class="sxs-lookup"><span data-stu-id="d3d94-121">Step 1.</span></span> <span data-ttu-id="d3d94-122">取得電子郵件訊息識別碼</span><span class="sxs-lookup"><span data-stu-id="d3d94-122">Obtain the Message ID of the email</span></span>

<span data-ttu-id="d3d94-123">您可以撤銷加密的郵件之前您需要收集郵件訊息識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3d94-123">Before you can revoke an encrypted mail you need to gather the Message ID of the mail.</span></span> <span data-ttu-id="d3d94-124">MessageId 通常是的格式：</span><span class="sxs-lookup"><span data-stu-id="d3d94-124">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="d3d94-125">有多種方式來尋找您想要撤銷的電子郵件訊息識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3d94-125">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="d3d94-126">本小節會說明兩個選項，但您可以使用任何方法，提供識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3d94-126">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="d3d94-127">若要找出您想要撤銷安全性使用郵件追蹤的電子郵件訊息識別碼&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="d3d94-127">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d3d94-128">搜尋由寄件者或收件者使用[新的郵件追蹤，在 Office 365 安全性 & 合規性中心中](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d3d94-128">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="d3d94-129">一旦您已經找到電子郵件，請選取帶出 [**郵件追蹤詳細資料**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="d3d94-129">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="d3d94-130">依序展開 [**更多的資訊**來找出郵件的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3d94-130">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="d3d94-131">若要找出您想要使用 Office 郵件加密報告安全性撤銷電子郵件訊息識別碼&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="d3d94-131">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d3d94-132">安全性&amp;合規性中心，瀏覽至**郵件加密報告**。</span><span class="sxs-lookup"><span data-stu-id="d3d94-132">In the Security &amp; Compliance Center, navigate to the **Message Encryption Report**.</span></span>

2. <span data-ttu-id="d3d94-133">選擇 [**檢視詳細資料]** 表格，並找出您想要撤銷的訊息。</span><span class="sxs-lookup"><span data-stu-id="d3d94-133">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="d3d94-134">按兩下 [檢視詳細資料] 包含郵件識別碼訊息</span><span class="sxs-lookup"><span data-stu-id="d3d94-134">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="d3d94-135">步驟 2。</span><span class="sxs-lookup"><span data-stu-id="d3d94-135">Step 2.</span></span> <span data-ttu-id="d3d94-136">確認便可撤銷之電子郵件</span><span class="sxs-lookup"><span data-stu-id="d3d94-136">Verify that the mail is revocable</span></span>

<span data-ttu-id="d3d94-137">若要確認您是否可以撤銷將特定電子郵件，請檢查 [撤銷狀態] 欄位是否為可見**詳細資料**表格中的安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="d3d94-137">To verify whether you can revoke a particular email message, check whether the Revocation Status field is visible in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="d3d94-138">若要確認您可以使用 Windows Powershell 撤銷將特定電子郵件，完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="d3d94-138">To verify whether or not you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="d3d94-139">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="d3d94-139">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="d3d94-140">如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。</span><span class="sxs-lookup"><span data-stu-id="d3d94-140">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="d3d94-141">執行設定 OMEMessageStatus 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d3d94-141">Run the Set-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="d3d94-142">這會傳回郵件以及是否可撤銷之郵件的主旨。</span><span class="sxs-lookup"><span data-stu-id="d3d94-142">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="d3d94-143">For example,</span><span class="sxs-lookup"><span data-stu-id="d3d94-143">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="d3d94-144">步驟 3。</span><span class="sxs-lookup"><span data-stu-id="d3d94-144">Step 3.</span></span> <span data-ttu-id="d3d94-145">撤銷郵件</span><span class="sxs-lookup"><span data-stu-id="d3d94-145">Revoke the mail</span></span>  

<span data-ttu-id="d3d94-146">一旦您知道想要撤銷，請將電子郵件訊息識別碼，並確認郵件可撤銷之，您可以撤銷電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d3d94-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email.</span></span>

<span data-ttu-id="d3d94-147">若要撤銷安全性中的電子郵件&amp;合規性中心，在**Details** ] 資料表中，選擇 [**撤銷**。</span><span class="sxs-lookup"><span data-stu-id="d3d94-147">To revoke the email in the Security &amp; Compliance Center, in the **Details** table, choose **Revoke**.</span></span>

<span data-ttu-id="d3d94-148">您可以使用 Windows Powershell 設定 OMEMessageRevocation 指令程式撤銷電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d3d94-148">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="d3d94-149">[連線至 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="d3d94-149">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="d3d94-150">執行設定 OMEMessageRevocation 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d3d94-150">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="d3d94-151">若要檢查是否已撤銷電子郵件，請執行 Get OMEMessageStatus 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d3d94-151">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="d3d94-152">如果撤銷成功，cmdlet 就會傳回下列結果：</span><span class="sxs-lookup"><span data-stu-id="d3d94-152">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="d3d94-153">Office 365 進階郵件加密的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d3d94-153">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="d3d94-154">Office 365 進階郵件加密</span><span class="sxs-lookup"><span data-stu-id="d3d94-154">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- <span data-ttu-id="d3d94-155">[Office 365 進階的郵件加密]-電子郵件到期](ome-advanced-expiration.md)</span><span class="sxs-lookup"><span data-stu-id="d3d94-155">[Office 365 Advanced Message Encryption - email expiration](ome-advanced-expiration.md)</span></span>

- [<span data-ttu-id="d3d94-156">郵件原則及符合性服務說明</span><span class="sxs-lookup"><span data-stu-id="d3d94-156">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)