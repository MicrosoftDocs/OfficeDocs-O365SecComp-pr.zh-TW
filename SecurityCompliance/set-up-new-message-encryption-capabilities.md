---
title: 設定全新的 Office 365 郵件加密功能
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: 內建置於 Azure 資訊保護、 貴組織的功能可以使用新的 Office 365 郵件加密受保護的電子郵件通訊與組織內外的人。與其他 Office 365 組織、 Outlook.com、 Gmail、 及其他電子郵件服務搭配使用的新 OME 功能。
ms.openlocfilehash: 90247a7e3cd7e5978eb144a2b6f66a9de21a8f96
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296186"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="a51ca-104">設定全新的 Office 365 郵件加密功能</span><span class="sxs-lookup"><span data-stu-id="a51ca-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="a51ca-p102">新的 Office 365 郵件加密 (OME) 功能允許與任何裝置上的任何人共用受保護的電子郵件組織。使用者可以交換受保護的訊息與其他 Office 365 組織以及非 Office 365 客戶使用 Outlook.com、 Gmail，以及其他電子郵件服務。</span><span class="sxs-lookup"><span data-stu-id="a51ca-p102">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device. Users can exchange protected messages with other Office 365 organizations, as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>


>[!NOTE]
><span data-ttu-id="a51ca-p103">本文適用於系統管理員及 IT 專業人員的。如果您是使用者，請參閱[Office 365 郵件加密 (OME)](ome.md)中的適當解決方案的文章的清單。</span><span class="sxs-lookup"><span data-stu-id="a51ca-p103">This article is intended for administrators and IT professionals. If you're an end-user, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) for appropriate solutions.</span></span>

<span data-ttu-id="a51ca-109">請遵循下列步驟來確保您的 Office 365 租用戶中可用的新 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="a51ca-109">Follow the steps below to ensure that the New OME capabilities are available in your Office 365 tenant.</span></span> 

## <a name="verify-azure-rights-management-arm-is-active"></a><span data-ttu-id="a51ca-110">確認已啟用 Azure 版權管理 (ARM)</span><span class="sxs-lookup"><span data-stu-id="a51ca-110">Verify Azure Rights Management (ARM) is active</span></span>

>[!NOTE]
><span data-ttu-id="a51ca-111">新的 OME 功能利用[Azure 資訊保護](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection)、 [Azure 版權管理 (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)所用的技術中的保護功能。</span><span class="sxs-lookup"><span data-stu-id="a51ca-111">The new OME capabilities leverage the protection features in [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), the technology used by [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms).</span></span>

<span data-ttu-id="a51ca-p104">使用新的 OME 功能僅必要條件是[Azure 版權管理 (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)必須要啟動 Office 365 租用戶中。如果它是 Office 365 會自動啟動新的 OME 功能和您不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="a51ca-p104">The only prerequisite for using the new OME capabilities is that [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) must be activated in your Office 365 tenant. If it is, Office 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span> 

<span data-ttu-id="a51ca-p105">ARM 也啟動自動最合格的計劃，因此您可能不需要執行任何動作在這方面也。如需詳細資訊，請參閱[啟動 Azure 版權管理](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="a51ca-p105">ARM is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either. See [Activating Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) for more.</span></span>

>[!IMPORTANT]
><span data-ttu-id="a51ca-p106">如果您使用 Active Directory Rights Management service (AD RMS) 與 Exchange Online 時，您需要移轉[至 Azure 資訊保護](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms)才能使用新的 OME 功能。AD RMS 不相容於 ARM。</span><span class="sxs-lookup"><span data-stu-id="a51ca-p106">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities. AD RMS is not compatible with ARM.</span></span>  

<span data-ttu-id="a51ca-118">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="a51ca-118">For more, see:</span></span>

- <span data-ttu-id="a51ca-119">[我需要使用新的 OME 功能何種訂閱？](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)若要檢查您的訂閱計劃是否包含 Azure 資訊保護 （其中包括 ARM）。</span><span class="sxs-lookup"><span data-stu-id="a51ca-119">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes ARM).</span></span>   
-  <span data-ttu-id="a51ca-120">如需購買合格的訂閱資訊[Azure 資訊保護](https://azure.microsoft.com/en-us/services/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="a51ca-120">[Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-arm"></a><span data-ttu-id="a51ca-121">手動啟動 ARM</span><span class="sxs-lookup"><span data-stu-id="a51ca-121">Manually activating ARM</span></span>

<span data-ttu-id="a51ca-122">如果您停用 ARM，或如果它尚未自動啟動任何原因，您可以啟動其以手動方式：</span><span class="sxs-lookup"><span data-stu-id="a51ca-122">If you disabled ARM, or if it was not automatically activated for any reason, you can activated it manually in the :</span></span>

- <span data-ttu-id="a51ca-123">**Office 365 系統管理中心**： 了解[如何啟用 Azure 版權管理 Office 365 系統管理中心中](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365)的指示</span><span class="sxs-lookup"><span data-stu-id="a51ca-123">**Office 365 admin center**: See [How to activate Azure Rights Management from the Office 365 admin center](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) for instructions</span></span>
- <span data-ttu-id="a51ca-124">**Azure 入口網站**： 了解[如何啟動 Azure Rights Management 從 Azure 入口網站](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure)的指示。</span><span class="sxs-lookup"><span data-stu-id="a51ca-124">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) for instructions.</span></span> 


## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="a51ca-125">設定管理 Azure 資訊保護承租人索引鍵</span><span class="sxs-lookup"><span data-stu-id="a51ca-125">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="a51ca-p107">這是選用的步驟。允許 Microsoft Azure 資訊保護管理根機碼是預設設定與大部分的 Office 365 租用戶的建議最佳作法。如果是這樣，您不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="a51ca-p107">This is an optional step. Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most Office 365 tenants. If this is the case, you don't need to do anything.</span></span> 

<span data-ttu-id="a51ca-p108">有許多原因，例如規範需求，也許您產生及管理自己根 （也稱為將您自己的金鑰 (BYOK)） 的索引鍵。如果是這樣，建議您設定的新 OME 功能之前完成的必要的步驟。如需詳細資訊，請參閱[規劃及實作您 Azure 資訊保護租用戶金鑰](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="a51ca-p108">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)). If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities. See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span> 


## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="a51ca-132">確認 Exchange Online PowerShell 中的新 OME 組態</span><span class="sxs-lookup"><span data-stu-id="a51ca-132">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="a51ca-133">您可以驗證您的 Office 365 租用戶正確設定為在[Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)中使用的新 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="a51ca-133">You can verify that your Office 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="a51ca-134">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)使用的帳戶具有您的 Office 365 租用戶中的全域系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="a51ca-134">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="a51ca-135">執行 Test-irmconfiguration 指令程式使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a51ca-135">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="a51ca-136">**範例**：</span><span class="sxs-lookup"><span data-stu-id="a51ca-136">**Example**:</span></span> 
   
     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```
     
     - <span data-ttu-id="a51ca-p109">提供的寄件者電子郵件是選擇性的但會強制執行其他檢查系統。在您的 Office 365 租用戶中使用之任何使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a51ca-p109">Providing a sender email is optional, but forces the system to perform additional checks. Use the email address of any user in your Office 365 tenant.</span></span> 
     
    <span data-ttu-id="a51ca-139">您的結果應該會類似：</span><span class="sxs-lookup"><span data-stu-id="a51ca-139">Your results should be similar to:</span></span>

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

   - <span data-ttu-id="a51ca-140">Office 365 組織的名稱將會取代*Contoso*。</span><span class="sxs-lookup"><span data-stu-id="a51ca-140">Your Office 365 organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="a51ca-p110">預設範本名稱可能會不同顯示上方。如需詳細資訊，請參閱[Azure 資訊保護的設定及管理範本](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="a51ca-p110">The default template names may be different from those displayed above. See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) for more.</span></span>

3. <span data-ttu-id="a51ca-143">執行 Remove-pssession cmdlet 來中斷與版權管理服務的連線。</span><span class="sxs-lookup"><span data-stu-id="a51ca-143">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>
    
     ```powershell
     Remove-PSSession $session
     ```

## <a name="update-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="a51ca-144">若要使用 OME 的新功能的郵件流程規則更新</span><span class="sxs-lookup"><span data-stu-id="a51ca-144">Update mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="a51ca-p111">如果您的 Office 365 租用戶中有先前已設定的[來加密電子郵件的郵件流程規則](define-mail-flow-rules-to-encrypt-email.md)，您需要更新下列現有的規則來使用新的 OME 功能。新部署的這個步驟是不需要此階段。</span><span class="sxs-lookup"><span data-stu-id="a51ca-p111">If there are previously configured [mail flow rules to encrypt email](define-mail-flow-rules-to-encrypt-email.md) in your Office 365 tenant, you need to update these existing rules to use the new OME capabilities. For new deployments, this step is unnecessary at this stage.</span></span>   

>[!Note]
><span data-ttu-id="a51ca-p112">郵件流程規則定義的電子郵件訊息會經過加密，以及何時應該移除加密的條件。如需詳細資訊，請參閱[定義郵件流程規則來加密 Office 365 中的電子郵件訊息](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="a51ca-p112">Mail flow rules define the conditions under which email messages are encrypted, and when encryption should be removed. See [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md) for more.</span></span>

<span data-ttu-id="a51ca-149">若要更新現有規則，以使用新的 OME 功能：</span><span class="sxs-lookup"><span data-stu-id="a51ca-149">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="a51ca-150">在 Office 365 系統管理中心，移至**系統中心 > Exchange**。</span><span class="sxs-lookup"><span data-stu-id="a51ca-150">In the Office 365 admin center, go to **Admin centers > Exchange**.</span></span>

2. <span data-ttu-id="a51ca-151">在 Exchange 系統管理中心，移至 [**郵件流程 > 規則**。</span><span class="sxs-lookup"><span data-stu-id="a51ca-151">In the Exchange admin center, go to **Mail flow > Rules**.</span></span> 
3. <span data-ttu-id="a51ca-152">針對每個規則中**執行下列動作**：</span><span class="sxs-lookup"><span data-stu-id="a51ca-152">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="a51ca-153">選取 [**修改郵件安全性**]。</span><span class="sxs-lookup"><span data-stu-id="a51ca-153">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="a51ca-154">選取**適用於 Office 365 郵件加密和權限保護**。</span><span class="sxs-lookup"><span data-stu-id="a51ca-154">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="a51ca-155">從清單中選取的 RMS 範本</span><span class="sxs-lookup"><span data-stu-id="a51ca-155">Select an RMS template from the list</span></span>
    - <span data-ttu-id="a51ca-156">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="a51ca-156">Select **Save**.</span></span>
    - <span data-ttu-id="a51ca-157">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a51ca-157">Select **OK**.</span></span>
  
>[!IMPORTANT]
><span data-ttu-id="a51ca-158">如果您未更新現有的郵件流程規則，您的使用者會繼續接收加密的郵件而不是新的 OME 功能使用先前的 HTML 附件格式。</span><span class="sxs-lookup"><span data-stu-id="a51ca-158">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new OME capabilities.</span></span>
