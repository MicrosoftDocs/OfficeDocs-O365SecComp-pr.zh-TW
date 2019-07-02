---
title: 撤銷由 Office 365 進階郵件加密所加密的電子郵件
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 作為 Office 365 系統管理員, 您可以使用 Office 365 高級郵件加密來撤銷某些已加密的電子郵件。
ms.openlocfilehash: e55129f68c7add589bd973b36f069d7cdbf631cf
ms.sourcegitcommit: 5a93c2f3df35d06a59a7fbaff5c91f7afde11781
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857613"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="15ae2-103">撤銷由 Office 365 進階郵件加密所加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="15ae2-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="15ae2-104">電子郵件撤銷是以 Office 365 高級郵件加密的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="15ae2-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="15ae2-105">Office 365 高級郵件加密可在特定訂閱中的 Office 365 郵件加密上使用。</span><span class="sxs-lookup"><span data-stu-id="15ae2-105">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="15ae2-106">[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)e5、Office 365 企業版 E5 和 Office 365 教育版 A5 包含先進的郵件加密。</span><span class="sxs-lookup"><span data-stu-id="15ae2-106">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="15ae2-107">如果您的組織有 Office 365 訂閱, 但未包含 Office 365 的高級郵件加密, 您可以使用 advanced 合規性 SKU 的 E5 規範, 以附加元件形式購買高級郵件加密。</span><span class="sxs-lookup"><span data-stu-id="15ae2-107">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="15ae2-108">本文是更多有關[Office 365 郵件加密](ome.md)的文章系列的一部分。</span><span class="sxs-lookup"><span data-stu-id="15ae2-108">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="15ae2-109">如果郵件是使用 Office 365 高級郵件加密進行加密, 而且您是 Office 365 系統管理員, 您可以在特定情況下撤銷郵件。</span><span class="sxs-lookup"><span data-stu-id="15ae2-109">If a message was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do revoke the message under certain conditions.</span></span> <span data-ttu-id="15ae2-110">本文說明可進行撤銷的情況及其執行方式。</span><span class="sxs-lookup"><span data-stu-id="15ae2-110">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="15ae2-111">您可以撤銷的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="15ae2-111">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="15ae2-112">如果收件者收到以連結為基礎且署名的加密電子郵件, 您可以撤銷加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="15ae2-112">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="15ae2-113">如果收件者在支援的 Outlook 用戶端中收到本機內嵌體驗, 則無法撤銷這些電子郵件。</span><span class="sxs-lookup"><span data-stu-id="15ae2-113">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="15ae2-114">收件者是否收到連結式經驗或內嵌經驗取決於收件者的身分識別類型: Office 365 和 Microsoft 帳戶收件者 (例如, outlook.com 使用者) 在支援的 Outlook 用戶端中取得內嵌體驗。</span><span class="sxs-lookup"><span data-stu-id="15ae2-114">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="15ae2-115">所有其他收件者類型 (例如 Gmail 收件者) 都會取得連結式體驗。</span><span class="sxs-lookup"><span data-stu-id="15ae2-115">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="15ae2-116">撤銷加密電子郵件的收件者體驗</span><span class="sxs-lookup"><span data-stu-id="15ae2-116">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="15ae2-117">一旦電子郵件遭到吊銷, 當收件者透過 Office 365 郵件加密入口網站存取加密的電子郵件時, 會收到錯誤訊息: 「寄件者已撤銷該郵件」。</span><span class="sxs-lookup"><span data-stu-id="15ae2-117">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![顯示已撤銷加密之電子郵件的螢幕擷取畫面。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="15ae2-119">如何撤銷加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="15ae2-119">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="15ae2-120">步驟 1。</span><span class="sxs-lookup"><span data-stu-id="15ae2-120">Step 1.</span></span> <span data-ttu-id="15ae2-121">取得電子郵件的郵件識別碼</span><span class="sxs-lookup"><span data-stu-id="15ae2-121">Obtain the Message ID of the email</span></span>

<span data-ttu-id="15ae2-122">在您可以撤銷已加密的郵件之前, 您會收集郵件的郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="15ae2-122">Before you can revoke an encrypted mail you gather the Message ID of the mail.</span></span> <span data-ttu-id="15ae2-123">MessageId 的格式通常為:</span><span class="sxs-lookup"><span data-stu-id="15ae2-123">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="15ae2-124">有多種方法可以尋找您要撤銷之電子郵件的郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="15ae2-124">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="15ae2-125">本節說明一些選項, 但您可以使用任何提供識別碼的方法。</span><span class="sxs-lookup"><span data-stu-id="15ae2-125">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="15ae2-126">若要使用安全性&amp;與合規性中心中的郵件追蹤來識別您要撤銷之電子郵件的郵件識別碼</span><span class="sxs-lookup"><span data-stu-id="15ae2-126">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="15ae2-127">使用[Office 365 安全性 & 規範中心內的新郵件追蹤](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/), 以寄件者或收件者搜尋電子郵件。</span><span class="sxs-lookup"><span data-stu-id="15ae2-127">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="15ae2-128">一旦您找到電子郵件, 請選取它以顯示 [**郵件追蹤詳細資料**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="15ae2-128">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="15ae2-129">展開 [**更多資訊**] 以找出郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="15ae2-129">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="15ae2-130">使用安全性&amp;與合規性中心中的 Office 郵件加密報告來識別您要撤銷之電子郵件的郵件識別碼</span><span class="sxs-lookup"><span data-stu-id="15ae2-130">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="15ae2-131">在安全性&amp;與合規性中心內, 流覽至 [**郵件加密] 報告**。</span><span class="sxs-lookup"><span data-stu-id="15ae2-131">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="15ae2-132">如需此報告的詳細資訊, 請參閱[在&amp;安全性與合規性中心中查看電子郵件安全性報告](view-email-security-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="15ae2-132">For information on this report, see [View email security reports in the Security &amp; Compliance Center](view-email-security-reports.md).</span></span>

2. <span data-ttu-id="15ae2-133">選擇 [**查看詳細資料**] 表格, 並找出您要撤銷的郵件。</span><span class="sxs-lookup"><span data-stu-id="15ae2-133">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="15ae2-134">連按兩下郵件, 以查看包含郵件識別碼的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="15ae2-134">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="15ae2-135">步驟 2。</span><span class="sxs-lookup"><span data-stu-id="15ae2-135">Step 2.</span></span> <span data-ttu-id="15ae2-136">確認郵件是可撤銷的</span><span class="sxs-lookup"><span data-stu-id="15ae2-136">Verify that the mail is revocable</span></span>

<span data-ttu-id="15ae2-137">若要確認您是否可以撤銷郵件, 請檢查 [安全&amp;規範中心] 的 [**詳細資料**] 表格中的 [吊銷狀態] 欄位是否可見。</span><span class="sxs-lookup"><span data-stu-id="15ae2-137">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="15ae2-138">若要確認您是否可以使用 Windows Powershell 來撤銷特定的電子郵件, 請完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="15ae2-138">To verify whether you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="15ae2-139">使用在 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶, 啟動 Windows PowerShell 會話, 並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="15ae2-139">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="15ae2-140">如需相關指示, 請參閱[Connect To Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="15ae2-140">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="15ae2-141">請執行 OMEMessageStatus 指令程式, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="15ae2-141">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="15ae2-142">這會傳回郵件的主旨, 以及郵件是否可撤銷。</span><span class="sxs-lookup"><span data-stu-id="15ae2-142">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="15ae2-143">For example,</span><span class="sxs-lookup"><span data-stu-id="15ae2-143">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="15ae2-144">步驟 3。</span><span class="sxs-lookup"><span data-stu-id="15ae2-144">Step 3.</span></span> <span data-ttu-id="15ae2-145">撤銷郵件</span><span class="sxs-lookup"><span data-stu-id="15ae2-145">Revoke the mail</span></span>

<span data-ttu-id="15ae2-146">一旦您知道想要撤銷之電子郵件的郵件識別碼, 並確認該郵件是可撤銷的, 您就可以使用安全性&amp;合規性中心或 Windows Powershell 來撤銷電子郵件。</span><span class="sxs-lookup"><span data-stu-id="15ae2-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows Powershell.</span></span>

<span data-ttu-id="15ae2-147">使用安全性&amp;與合規性中心撤銷郵件</span><span class="sxs-lookup"><span data-stu-id="15ae2-147">To revoke the message using the Security &amp; Compliance Center</span></span>

<span data-ttu-id="15ae2-148">若要撤銷安全性&amp;合規性中心內的電子郵件, 請在加密報告的 [**詳細資料**] 表格中, 選擇 **[撤銷郵件]**。</span><span class="sxs-lookup"><span data-stu-id="15ae2-148">To revoke the email in the Security &amp; Compliance Center, in the Encryption report, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="15ae2-149">您可以使用 OMEMessageRevocation 指令程式, 透過使用 Windows Powershell 來撤銷電子郵件。</span><span class="sxs-lookup"><span data-stu-id="15ae2-149">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="15ae2-150">[連線至 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="15ae2-150">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="15ae2-151">請執行 OMEMessageRevocation 指令程式, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="15ae2-151">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="15ae2-152">若要檢查電子郵件是否已被撤銷, 請執行 OMEMessageStatus 指令程式, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="15ae2-152">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="15ae2-153">如果撤銷成功, Cmdlet 會傳回下列結果:</span><span class="sxs-lookup"><span data-stu-id="15ae2-153">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="15ae2-154">有關 Office 365 高級郵件加密的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="15ae2-154">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="15ae2-155">Office 365 進階郵件加密</span><span class="sxs-lookup"><span data-stu-id="15ae2-155">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="15ae2-156">Office 365 高級郵件加密-電子郵件到期</span><span class="sxs-lookup"><span data-stu-id="15ae2-156">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="15ae2-157">郵件原則及符合性服務說明</span><span class="sxs-lookup"><span data-stu-id="15ae2-157">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
