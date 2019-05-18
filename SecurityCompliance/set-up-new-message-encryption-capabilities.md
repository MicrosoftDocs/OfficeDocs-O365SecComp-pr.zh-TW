---
title: 設定全新的 Office 365 郵件加密功能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 以 Azure 資訊保護，您的組織內建的功能可以使用新的 Office 365 郵件加密保護與組織內外的人員的電子郵件通訊。 全新的 OME 功能與其他 Office 365 組織、 Outlook.com、 Gmail，以及其他電子郵件服務搭配使用。
ms.openlocfilehash: 415e598a28033271b115aff639fb1ddd7a6345af
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156505"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="704ea-104">設定全新的 Office 365 郵件加密功能</span><span class="sxs-lookup"><span data-stu-id="704ea-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="704ea-105">新的 Office 365 郵件加密 (OME) 功能讓組織能與任何裝置上的任何人共用受保護的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="704ea-105">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="704ea-106">使用者可以交換與其他 Office 365 組織，以及使用 Outlook.com、 Gmail，以及其他電子郵件服務的非 Office 365 客戶受保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="704ea-106">Users can exchange protected messages with other Office 365 organizations, as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

||
|:-----|
|<span data-ttu-id="704ea-107">本文屬於較大的一連串的 Office 365 郵件加密的相關文章。</span><span class="sxs-lookup"><span data-stu-id="704ea-107">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="704ea-108">本文適用於系統管理員和 IT 專業人員。</span><span class="sxs-lookup"><span data-stu-id="704ea-108">This article is intended for administrators and IT Pros.</span></span> <span data-ttu-id="704ea-109">如果您只是正在尋找的資訊傳送或接收的加密的訊息，請參閱在[Office 365 郵件加密 (OME)](ome.md)中的文章的清單，並找出最適合您需求的文章。</span><span class="sxs-lookup"><span data-stu-id="704ea-109">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

<span data-ttu-id="704ea-110">請遵循下列步驟來確保 Office 365 組織中可用的新 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="704ea-110">Follow the steps below to ensure that the New OME capabilities are available in your Office 365 organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="704ea-111">確認 Azure Rights Management 正在使用中</span><span class="sxs-lookup"><span data-stu-id="704ea-111">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="704ea-112">全新的 OME 功能利用[Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection)，由[Azure 資訊保護](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)來保護電子郵件和文件透過加密和存取控制技術中的保護功能。</span><span class="sxs-lookup"><span data-stu-id="704ea-112">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="704ea-113">使用全新的 OME 功能僅必要條件是，必須在您的組織租用戶中啟動[Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) 。</span><span class="sxs-lookup"><span data-stu-id="704ea-113">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="704ea-114">如果是，Office 365 會自動啟動全新的 OME 功能，而且不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="704ea-114">If it is, Office 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="704ea-115">Azure RMS 便也會自動啟動最合格的方案，因此您可能不需要執行任何動作在這方面可以。</span><span class="sxs-lookup"><span data-stu-id="704ea-115">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="704ea-116">如需詳細資訊，請參閱[啟用 Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) 。</span><span class="sxs-lookup"><span data-stu-id="704ea-116">See [Activating Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="704ea-117">如果您使用 Active Directory Rights Management 服務 (AD RMS) 與 Exchange Online，您需要移轉[至 Azure 資訊保護](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms)之後才能使用全新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="704ea-117">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="704ea-118">OME 不相容的 AD RMS。</span><span class="sxs-lookup"><span data-stu-id="704ea-118">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="704ea-119">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="704ea-119">For more information, see:</span></span>

- <span data-ttu-id="704ea-120">[我需要使用全新的 OME 功能何種訂閱？](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)若要查看您的訂閱計劃是否包含 Azure 資訊保護 （其中包含 Azure RMS 功能）。</span><span class="sxs-lookup"><span data-stu-id="704ea-120">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="704ea-121">如需購買合格的訂閱的[Azure 資訊保護](https://azure.microsoft.com/en-us/services/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="704ea-121">[Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="704ea-122">手動啟動 Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="704ea-122">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="704ea-123">如果您停用 Azure RMS，或如果它不會自動啟動因任何原因，您可以啟用它中手動:</span><span class="sxs-lookup"><span data-stu-id="704ea-123">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="704ea-124">**Office 365 系統管理中心**： 如需相關指示，請參閱[How to 啟用從 Office 365 系統管理中心的 Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) 。</span><span class="sxs-lookup"><span data-stu-id="704ea-124">**Office 365 admin center**: See [How to activate Azure Rights Management from the Office 365 admin center](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="704ea-125">**Azure 入口網站**： 如需相關指示，請參閱[How to 啟動 Azure Rights Management，從 Azure 入口網站](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure)。</span><span class="sxs-lookup"><span data-stu-id="704ea-125">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="704ea-126">設定您的 Azure 資訊保護租用戶金鑰管理</span><span class="sxs-lookup"><span data-stu-id="704ea-126">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="704ea-127">這是選用的步驟。</span><span class="sxs-lookup"><span data-stu-id="704ea-127">This is an optional step.</span></span> <span data-ttu-id="704ea-128">允許 Microsoft，以管理 Azure 資訊保護根機碼是預設設定，並針對大多數的 Office 365 租用戶的建議最佳作法。</span><span class="sxs-lookup"><span data-stu-id="704ea-128">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most Office 365 tenants.</span></span> <span data-ttu-id="704ea-129">如果是這樣，您不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="704ea-129">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="704ea-130">有許多原因，例如動作，可能必須產生您的合規性需求及管理自己根機碼 （也稱為攜帶您自己的金鑰 (BYOK)）。</span><span class="sxs-lookup"><span data-stu-id="704ea-130">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="704ea-131">如果是這樣，建議您在設定全新的 OME 功能之前完成所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="704ea-131">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="704ea-132">如需詳細資訊，請參閱[規劃及實作 Azure 資訊保護您的租用戶金鑰](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="704ea-132">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="704ea-133">確認 Exchange Online PowerShell 中的新 OME 組態</span><span class="sxs-lookup"><span data-stu-id="704ea-133">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="704ea-134">您可以驗證您的 Office 365 租用戶正確設定為使用[Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)中的全新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="704ea-134">You can verify that your Office 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="704ea-135">使用 Office 365 租用戶中的全域系統管理員權限的帳戶[連線到 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="704ea-135">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="704ea-136">執行 Get-irmconfiguration 指令程式。</span><span class="sxs-lookup"><span data-stu-id="704ea-136">Run the Get-IRMConfiguration cmdlet.</span></span>

     <span data-ttu-id="704ea-137">您應該會看到 $True AzureRMSLicensingEnabled 參數，即表示 OME 在您的租用戶中設定的值。</span><span class="sxs-lookup"><span data-stu-id="704ea-137">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="704ea-138">如果不是，使用 Set-irmconfiguration 設定為啟用 OME $True AzureRMSLicensingEnabled 的值。</span><span class="sxs-lookup"><span data-stu-id="704ea-138">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="704ea-139">執行 Test-irmconfiguration 指令程式使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="704ea-139">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="704ea-140">**範例**：</span><span class="sxs-lookup"><span data-stu-id="704ea-140">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="704ea-141">提供的寄件者電子郵件是選擇性的但會強制執行的額外檢查系統。</span><span class="sxs-lookup"><span data-stu-id="704ea-141">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="704ea-142">使用 Office 365 租用戶中的任何使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="704ea-142">Use the email address of any user in your Office 365 tenant.</span></span>

     <span data-ttu-id="704ea-143">您的結果應該會類似：</span><span class="sxs-lookup"><span data-stu-id="704ea-143">Your results should be similar to:</span></span>

     ```text
    Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
    ```

   - <span data-ttu-id="704ea-144">Office 365 組織的名稱將會取代*Contoso*。</span><span class="sxs-lookup"><span data-stu-id="704ea-144">Your Office 365 organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="704ea-145">預設範本名稱可能不同顯示上方。</span><span class="sxs-lookup"><span data-stu-id="704ea-145">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="704ea-146">如需詳細資訊，請參閱[Azure 資訊保護的設定和管理範本](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="704ea-146">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="704ea-147">執行 Remove-pssession cmdlet，從 Rights Management 服務中斷連線。</span><span class="sxs-lookup"><span data-stu-id="704ea-147">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="704ea-148">後續步驟： 定義郵件流程規則來使用全新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="704ea-148">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="704ea-149">如果沒有先前設定的郵件流程規則以加密 Office 365 組織中的電子郵件，您需要更新現有的規則，以使用全新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="704ea-149">If there are previously configured mail flow rules to encrypt email in your Office 365 organization, you need to update the existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="704ea-150">針對新的部署，您需要建立新的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="704ea-150">For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="704ea-151">如果您沒有更新現有的郵件流程規則，您的使用者將會繼續收到加密的郵件使用先前的 HTML 附件格式，而不是新的無縫 OME 體驗。</span><span class="sxs-lookup"><span data-stu-id="704ea-151">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="704ea-152">郵件流程規則決定在哪些條件電子郵件訊息應該加密，以及移除該加密的條件。</span><span class="sxs-lookup"><span data-stu-id="704ea-152">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="704ea-153">當您設定的規則動作時，他們正在傳送時加密符合規則條件的任何郵件。</span><span class="sxs-lookup"><span data-stu-id="704ea-153">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="704ea-154">如需 OME 建立郵件流程規則的步驟，請參閱 <<c0>定義郵件流規則以加密 Office 365 中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="704ea-154">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="704ea-155">若要更新現有的規則，以使用全新的 OME 功能：</span><span class="sxs-lookup"><span data-stu-id="704ea-155">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="704ea-156">在 Office 365 系統管理中心中，移至**系統置 > Exchange**。</span><span class="sxs-lookup"><span data-stu-id="704ea-156">In the Office 365 admin center, go to **Admin centers > Exchange**.</span></span>
2. <span data-ttu-id="704ea-157">在 Exchange 系統管理中心，移至 [**郵件流程 > 規則**。</span><span class="sxs-lookup"><span data-stu-id="704ea-157">In the Exchange admin center, go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="704ea-158">每個規則，以**執行下列動作**：</span><span class="sxs-lookup"><span data-stu-id="704ea-158">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="704ea-159">選取 [**修改郵件安全性**]。</span><span class="sxs-lookup"><span data-stu-id="704ea-159">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="704ea-160">選取 [**適用於 Office 365 郵件加密和權限保護**。</span><span class="sxs-lookup"><span data-stu-id="704ea-160">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="704ea-161">從清單中選取的 RMS 範本。</span><span class="sxs-lookup"><span data-stu-id="704ea-161">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="704ea-162">選取**儲存**。</span><span class="sxs-lookup"><span data-stu-id="704ea-162">Select **Save**.</span></span>
    - <span data-ttu-id="704ea-163">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="704ea-163">Select **OK**.</span></span>
