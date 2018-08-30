---
title: 定義加密 Office 365 中的電子郵件的郵件流程規則
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
description: 身為 Office 365 全域管理員，您可以建立郵件流程規則來啟用 Office 365 郵件加密 (OME)。您可以加密所有外寄電子郵件並從內部訊息或回覆加密郵件傳送自組織移除加密。
ms.openlocfilehash: 06668f29e69c885adb8c67d723efe42b4a4aa166
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526416"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a><span data-ttu-id="93ff1-104">定義加密 Office 365 中的電子郵件的郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="93ff1-104">Define mail flow rules to encrypt email messages in Office 365</span></span>

<span data-ttu-id="93ff1-p102">身為 Office 365 全域管理員，您可以建立郵件流程規則，也稱為傳輸規則，以協助保護您傳送和接收的電子郵件訊息。您可以設定加密所有外寄電子郵件並從加密的郵件來自組織內或回覆加密郵件傳送自組織移除加密的規則。您可以使用 Exchange 系統管理中心 (EAC) 或 Exchange Online 的 Windows PowerShell cmdlet 建立這些規則。除了整體加密的郵件，您也可以選擇啟用或停用使用者的個別郵件加密選項。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p102">As an Office 365 global administrator, you can create mail flow rules, also known as transport rules, to help protect email messages you send and receive. You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization. You can use the Exchange admin center (EAC) or Windows PowerShell cmdlets for Exchange Online to create these rules. In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end-users.</span></span>
  
<span data-ttu-id="93ff1-p103">如果您最近移轉從 AD RMS Azure 資訊保護，您需要檢閱現有的郵件流程規則以確保其繼續在新環境中運作。此外，如果您想要利用新的 Office 365 郵件加密 (OME) 功能給您透過 Azure 資訊保護，您需要更新現有的郵件流程規則。否則，您的使用者會繼續接收加密的郵件而不是新的且相當順暢 OME 經驗會使用先前的 HTML 附件格式。如果您尚未設定 OME 尚未，請參閱[Set up 新建置上方的 Azure 資訊保護的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p103">If you recently migrated from AD RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment. Additionally, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules. Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience. If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md) for information.</span></span> 
  
<span data-ttu-id="93ff1-p104">如需元件構成郵件流程規則與郵件流程規則運作的方式，請參閱[Exchange Online 中的郵件流程規則 （傳輸規則）](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)。如需搭配 Azure 資訊保護的郵件流程規則如何運作的其他資訊，請參閱[Azure 資訊保護標籤設定 Exchange Online 郵件流程規則](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p104">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx). For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>
  
## <a name="create-a-mail-flow-rule-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="93ff1-115">建立郵件流程規則來加密電子郵件使用的新 OME 功能</span><span class="sxs-lookup"><span data-stu-id="93ff1-115">Create a mail flow rule to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="93ff1-116">您可以定義可使用 EAC 觸發新 OME 功能的郵件加密的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="93ff1-116">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>
  
### <a name="to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="93ff1-117">若要建立可加密電子郵件使用的新 OME 功能使用 EAC 的規則</span><span class="sxs-lookup"><span data-stu-id="93ff1-117">To create a rule for encrypting email messages with the new OME capabilities by using the EAC</span></span>

1. <span data-ttu-id="93ff1-118">在網頁瀏覽器中使用的工作或學校了已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-118">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="93ff1-119">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="93ff1-119">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="93ff1-120">在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-120">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="93ff1-p105">在 EAC 中，移至 [**郵件流程** \> **規則** \> ![圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)(**新增**) \> **建立新的規則**。如需使用 EAC 的詳細資訊，請參閱[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p105">In the EAC, go to **mail flow** \> **rules** \> ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) ( **New**) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx).</span></span>
    
5. <span data-ttu-id="93ff1-123">在 [**名稱**] 輸入規則名稱，例如 Encrypt mail for DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="93ff1-123">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>
    
6. <span data-ttu-id="93ff1-p106">在**套用此規則**選取條件和必要時輸入的值。例如，若要加密郵件移至 DrToniRamos@hotmail.com：</span><span class="sxs-lookup"><span data-stu-id="93ff1-p106">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span> 
    
    1. <span data-ttu-id="93ff1-126">在**套用此規則**，請選取 [**收件者**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-126">In **Apply this rule if**, select **the recipient is**.</span></span>
    
    2. <span data-ttu-id="93ff1-127">從連絡人清單中選取現有名稱或 [**檢查名稱**] 方塊中輸入新的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="93ff1-127">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span> 
    
        <span data-ttu-id="93ff1-128">若要選取現有名稱，從清單中選取然後再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-128">To select an existing name, select it from the list and then click **OK**.</span></span>
    
        <span data-ttu-id="93ff1-129">輸入新名稱、 在 [**檢查名稱**] 方塊中輸入電子郵件地址，然後選取 [**檢查名稱** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-129">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>
    
7. <span data-ttu-id="93ff1-130">若要新增多個條件、 選擇 [**更多選項]** 然後選擇 [**新增條件**並從清單中選取。</span><span class="sxs-lookup"><span data-stu-id="93ff1-130">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span> 
    
    <span data-ttu-id="93ff1-131">例如，若要將規則套用只有在收件者為組織外部，選取 [**新增條件**，然後選取 [**收件者是外部/內部** \> **組織外** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-131">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>
    
8. <span data-ttu-id="93ff1-p107">若要啟用加密使用新的 OME 功能，從**執行下列動作**，選取 [**修改郵件安全性**，然後選擇**適用於 Office 365 郵件加密和權限保護**。從清單中選取的 RMS 範本、 選擇 [**儲存**]，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p107">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
    
    <span data-ttu-id="93ff1-p108">範本的清單會包含所有的預設範本及 Office 365 所使用的選項為您已建立的任何自訂範本。如果清單是空的請確定您已設定 Office 365 郵件加密的新功能與[設定在 Azure 資訊保護頂端上建立新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。如需預設範本的資訊，請參閱[設定及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。[**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。**僅限加密**] 選項的相關資訊，請參閱[只加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p108">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>
    
    <span data-ttu-id="93ff1-139">您可以選擇**加入動作**如果您想要指定另一個巨集指令。</span><span class="sxs-lookup"><span data-stu-id="93ff1-139">You can choose **add action** if you want to specify another action.</span></span> 
    
### <a name="to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="93ff1-140">更新現有的郵件流程規則來使用 EAC OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="93ff1-140">To update an existing mail flow rule to use the new OME capabilities by using the EAC</span></span>

1. <span data-ttu-id="93ff1-141">在網頁瀏覽器中使用的工作或學校了已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-141">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="93ff1-142">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="93ff1-142">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="93ff1-143">在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-143">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="93ff1-144">在 EAC 中，移至 [**郵件流程** \> **規則**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-144">In the EAC, go to **mail flow** \> **rules**.</span></span>
    
5. <span data-ttu-id="93ff1-145">在郵件流程規則清單中，選取您想要使用的新 OME 功能，然後選擇 [修改的規則![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)（**編輯**）。</span><span class="sxs-lookup"><span data-stu-id="93ff1-145">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ( **Edit**).</span></span>
    
6. <span data-ttu-id="93ff1-p109">若要啟用加密使用新的 OME 功能，從**執行下列動作**，選擇 [**修改郵件安全性**，然後選擇**適用於 Office 365 郵件加密和權限保護**。從清單中選取的 RMS 範本、 選擇 [**儲存]** ，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p109">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>
    
    <span data-ttu-id="93ff1-p110">範本的清單會包含所有的預設範本及 Office 365 所使用的選項為您已建立的任何自訂範本。如果清單是空的請確定您已設定 Office 365 郵件加密的新功能與[設定在 Azure 資訊保護頂端上建立新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。如需預設範本的資訊，請參閱[設定及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。[**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。**僅限加密**] 選項的相關資訊，請參閱[只加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p110">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>
    
    <span data-ttu-id="93ff1-153">您可以選擇**加入動作**如果您想要指定另一個巨集指令。</span><span class="sxs-lookup"><span data-stu-id="93ff1-153">You can choose **add action** if you want to specify another action.</span></span> 
    
7. <span data-ttu-id="93ff1-154">從**執行下列動作**] 清單中移除任何指派給**修改郵件安全性**的動作\>**套用 OME 的舊版本**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-154">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>
    
8. <span data-ttu-id="93ff1-155">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="93ff1-155">Choose **Save**.</span></span>
    
## <a name="creating-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="93ff1-156">不使用的新功能建立 Office 365 郵件加密的規則</span><span class="sxs-lookup"><span data-stu-id="93ff1-156">Creating rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="93ff1-p111">若您尚未尚未移動 Office 365 組織到新的 OME 功能，可用於這些工作定義加密您的組織的郵件的郵件流程規則。Microsoft 建議您將移至新的 OME 功能一旦是組織的合理的計劃。指示，請參閱[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p111">If you haven't yet moved your Office 365 organization to the new OME capabilities, use these tasks to define mail flow rules to encrypt messages for your organization. Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span>
  
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="93ff1-160">若要建立可加密電子郵件訊息的新 OME 功能不使用 EAC 的規則</span><span class="sxs-lookup"><span data-stu-id="93ff1-160">To create a rule for encrypting email messages without the new OME capabilities by using the EAC</span></span>

1. <span data-ttu-id="93ff1-161">在網頁瀏覽器中使用的工作或學校了已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-161">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="93ff1-162">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="93ff1-162">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="93ff1-163">在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-163">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="93ff1-p112">在 EAC 中，移至 [**郵件流程** \> **規則** \> **+** (**新增**) \> **建立新的規則**。如需使用 EAC 的詳細資訊，請參閱[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p112">In the EAC, go to **mail flow** \> **rules** \> **+** ( **New**) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx).</span></span>
    
5. <span data-ttu-id="93ff1-166">在 [**名稱**] 輸入規則名稱，例如 Encrypt mail for DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="93ff1-166">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>
    
6. <span data-ttu-id="93ff1-p113">在**套用此規則**選取條件和必要時輸入的值。例如，若要加密郵件移至 DrToniRamos@hotmail.com：</span><span class="sxs-lookup"><span data-stu-id="93ff1-p113">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span> 
    
1. <span data-ttu-id="93ff1-169">在**套用此規則**，請選取 [**收件者**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-169">In **Apply this rule if**, select **the recipient is**.</span></span>
    
2. <span data-ttu-id="93ff1-170">從連絡人清單中選取現有名稱或 [**檢查名稱**] 方塊中輸入新的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="93ff1-170">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span> 
    
    <span data-ttu-id="93ff1-171">若要選取現有名稱，從清單中選取然後再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-171">To select an existing name, select it from the list and then click **OK**.</span></span>
    
    <span data-ttu-id="93ff1-172">輸入新名稱、 在 [**檢查名稱**] 方塊中輸入電子郵件地址，然後選取 [**檢查名稱** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-172">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>
    
7. <span data-ttu-id="93ff1-173">若要新增多個條件、 選擇 [**更多選項]** 然後選取 [**新增條件**與從清單中選取。</span><span class="sxs-lookup"><span data-stu-id="93ff1-173">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span> 
    
    <span data-ttu-id="93ff1-174">例如，若要將規則套用只有在收件者為組織外部，選取 [**新增條件**，然後選取 [**收件者是外部/內部** \> **組織外** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-174">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>
    
8. <span data-ttu-id="93ff1-175">若要啟用加密沒有使用新的 OME 功能，**請執行下列操作**，請選取 [**修改郵件安全性** \> **套用 OME 的前一版**]，然後選擇 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-175">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>
    
    <span data-ttu-id="93ff1-p114">如果您收到未啟用 IRM 授權，則您尚未為您的組織尚未設定 OME 的錯誤。如果您想要立即設定 OME，您必須設定為使用新的 OME 功能。資訊，請參閱[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護](set-up-new-message-encryption-capabilities.md)。Microsoft 不再支援的 OME 而的新功能的新部署的設定。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p114">If you receive an error that IRM licensing isn't enabled, then you haven't set up OME for your organization yet. If you'd like to set up OME now, you must set it up to use the new OME capabilities. For information, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). Microsoft no longer supports setting up new deployments of OME without the new capabilities.</span></span>
    
    <span data-ttu-id="93ff1-180">您可以選擇**加入動作**如果您想要指定另一個巨集指令。</span><span class="sxs-lookup"><span data-stu-id="93ff1-180">You can choose **add action** if you want to specify another action.</span></span> 
    
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a><span data-ttu-id="93ff1-181">若要建立可加密電子郵件訊息的新 OME 功能不使用 Exchange Online 的 Windows PowerShell 規則</span><span class="sxs-lookup"><span data-stu-id="93ff1-181">To create a rule for encrypting email messages without the new OME capabilities by using Windows PowerShell for Exchange Online</span></span>

1. <span data-ttu-id="93ff1-p115">使用本機電腦上的 Windows PowerShell 建立至 Exchange Online 的遠端 PowerShell 工作階段。如需詳細資訊，請參閱[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p115">Use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online. For more information, see [Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).</span></span>
    
2. <span data-ttu-id="93ff1-184">使用**New-transportrule**指令程式來定義規則並將**ApplyOME**屬性設定為**true**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-184">Define a rule by using the **New-TransportRule** cmdlet and set the **ApplyOME** attribute to **true**.</span></span>
    
    <span data-ttu-id="93ff1-185">例如，若要要求必須加密所有電子郵件訊息傳送給 DrToniRamos@hotmail.com，請輸入：</span><span class="sxs-lookup"><span data-stu-id="93ff1-185">For example, to require that all email messages that are addressed to DrToniRamos@hotmail.com must be encrypted, type:</span></span>
    
     ```
     New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
     ```

    <span data-ttu-id="93ff1-186">在此範例中：</span><span class="sxs-lookup"><span data-stu-id="93ff1-186">In this example:</span></span>
    
  - <span data-ttu-id="93ff1-187">新規則的名稱為"加密規則 Dr Toni Ramos"。</span><span class="sxs-lookup"><span data-stu-id="93ff1-187">The name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>
    
  - <span data-ttu-id="93ff1-p116">**-SentTo**參數會指定尋找收件者電子郵件訊息中的條件。您可以使用唯一識別收件者，例如電子郵件地址、 名稱、 辨別的名稱 (DN) 等的任何值。在這個範例中，收件者可識別的電子郵件地址"DrToniRamos@hotmail.com"。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p116">The **-SentTo** parameter, specifies a condition that looks for recipients in email messages. You can use any value that uniquely identifies the recipient, such as an email address, name, distinguished name (DN), etc. In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span> 
    
  - <span data-ttu-id="93ff1-p117">**-SentToScope**參數會指定條件所尋找的收件者的位置。在本例中為收件者的信箱在 hotmail 而不屬於 Office 365 組織，因此會使用"NotInOrganization"值。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p117">The **-SentToScope** parameter specifies a condition that looks for the location of recipients. In this example, the recipient's mailbox is in hotmail and is not part of the Office 365 organization, so the "NotInOrganization" value is used.</span></span> 
    
    <span data-ttu-id="93ff1-192">如需詳細資訊條件您可以使用此指令程式的郵件流程規則上設定，請參閱[New-transportrule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-192">For more information about the conditions you can set on mail flow rules using this cmdlet, see [New-TransportRule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx).</span></span>
    
### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="93ff1-193">移除新 OME 功能不加密的電子郵件回覆的加密</span><span class="sxs-lookup"><span data-stu-id="93ff1-193">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="93ff1-p118">當您的電子郵件使用者傳送加密的郵件時，那些郵件的收件者可以使用加密回覆與回應。您可以建立郵件流程規則來自動移除加密回覆讓組織中的電子郵件使用者不需要登入加密入口網站以進行檢視。您可以使用 EAC 或 Windows PowerShell cmdlet 來定義這些規則。如果您不尚未使用新的 OME 功能，您可以僅解密其中一個從您的組織或組織內傳送訊息的回覆的郵件中傳送的郵件。您無法解密源自組織外的加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p118">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies. You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them. You can use the EAC or Windows PowerShell cmdlets to define these rules. If you are not yet using the new OME capabilities, you can only decrypt messages that are either sent from within your organization or messages that are replies to messages sent from within your organization. You cannot decrypt encrypted messages originating from outside of your organization.</span></span>
  
#### <a name="to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="93ff1-199">若要建立移除新 OME 功能不使用 EAC 來加密的電子郵件回覆中加密的規則</span><span class="sxs-lookup"><span data-stu-id="93ff1-199">To create a rule for removing encryption from email replies encrypted without the new OME capabilities by using the EAC</span></span>
<span data-ttu-id="93ff1-200"><a name="DecryptruleEACNoNewOME"> </a></span><span class="sxs-lookup"><span data-stu-id="93ff1-200"></span></span>

1. <span data-ttu-id="93ff1-201">在網頁瀏覽器中使用的工作或學校了已授與管理員的權限，[登入 Office 365](https://support.office.com/article/Sign-in-to-Office-or-Office-365-b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-201">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/Sign-in-to-Office-or-Office-365-b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="93ff1-202">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="93ff1-202">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="93ff1-203">在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-203">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="93ff1-p119">在 EAC 中，移至 [**郵件流程** \> **規則** \> **+** (**新增**) \> **建立新的規則**。如需使用 EAC 的詳細資訊，請參閱[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/en-us/library/jj200743%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p119">In the EAC, go to **mail flow** \> **rules** \> **+** ( **New**) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/en-us/library/jj200743%28v=exchg.150%29.aspx).</span></span>
    
5. <span data-ttu-id="93ff1-206">在 [**名稱**] 輸入規則名稱，例如 Remove encryption from incoming mail。</span><span class="sxs-lookup"><span data-stu-id="93ff1-206">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>
    
6. <span data-ttu-id="93ff1-207">在**套用此規則**選取的條件的郵件，例如**收件者位於**應該移除加密\>**在組織內**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-207">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>
    
7. <span data-ttu-id="93ff1-208">在**執行下列動作**，選取 [**修改郵件安全性** \> **OME 的舊版本中移除**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-208">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>
    
8. <span data-ttu-id="93ff1-209">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-209">Select **Save**.</span></span>
    
#### <a name="to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a><span data-ttu-id="93ff1-210">若要建立可移除新 OME 功能不使用 Exchange Online 的 Windows PowerShell 加密的電子郵件回覆中加密的規則</span><span class="sxs-lookup"><span data-stu-id="93ff1-210">To create a rule to remove encryption from email replies encrypted without the new OME capabilities by using Windows PowerShell for Exchange Online</span></span>
<span data-ttu-id="93ff1-211"><a name="DecryptrulePShellNoNewOME"> </a></span><span class="sxs-lookup"><span data-stu-id="93ff1-211"></span></span>

1. <span data-ttu-id="93ff1-p120">使用本機電腦上的 Windows PowerShell 建立至 Exchange Online 的遠端 PowerShell 工作階段。如需詳細資訊，請參閱[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-p120">Use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online. For more information, see [Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).</span></span>
    
2. <span data-ttu-id="93ff1-214">使用**New-transportrule**指令程式來定義規則並將**RemoveOME**屬性設定為**true**。</span><span class="sxs-lookup"><span data-stu-id="93ff1-214">Define a rule by using the **New-TransportRule** cmdlet and set the **RemoveOME** attribute to **true**.</span></span>
    
    <span data-ttu-id="93ff1-215">例如，若要移除所有傳送給 Office 365 組織中的收件者的郵件加密，請輸入：</span><span class="sxs-lookup"><span data-stu-id="93ff1-215">For example, to remove the encryption from all mail sent to recipients in your Office 365 organization, type:</span></span>
    
     ```
     New-TransportRule - Name "Remove encryption from incoming mail"     -SentToScope "InOrganization" -RemoveOME $true
     ```

    <span data-ttu-id="93ff1-216">在此範例中：</span><span class="sxs-lookup"><span data-stu-id="93ff1-216">In this example:</span></span>
    
  - <span data-ttu-id="93ff1-217">新規則的名稱為"Remove encryption from incoming mail"。</span><span class="sxs-lookup"><span data-stu-id="93ff1-217">The name of the new rule is "Remove encryption from incoming mail".</span></span>
    
  - <span data-ttu-id="93ff1-p121">**-SentToScope**參數會指定條件所尋找的收件者的位置。在這個範例中，會使用"InOrganization"值會指出的：</span><span class="sxs-lookup"><span data-stu-id="93ff1-p121">The **-SentToScope** parameter specifies a condition that looks for the location of recipients. In this example, the "InOrganization" value is used which indicates that:</span></span> 
    
  - <span data-ttu-id="93ff1-220">收件者是信箱、 郵件使用者、 群組或擁有郵件功能在您的組織中的公用資料夾或</span><span class="sxs-lookup"><span data-stu-id="93ff1-220">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization, or</span></span>
    
  - <span data-ttu-id="93ff1-221">收件者的電子郵件地址中公認的網域設定為授權網域] 或 [內部轉送網域，且郵件已傳送或接收透過未經過驗證的連線。</span><span class="sxs-lookup"><span data-stu-id="93ff1-221">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain, and the message was sent or received over an authenticated connection.</span></span>
    
    <span data-ttu-id="93ff1-222">如需詳細資訊條件您可以使用此指令程式的郵件流程規則上設定，請參閱[New-transportrule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="93ff1-222">For more information about the conditions you can set on mail flow rules using this cmdlet, see [New-TransportRule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="93ff1-223">相關主題</span><span class="sxs-lookup"><span data-stu-id="93ff1-223">Related Topics</span></span>

[<span data-ttu-id="93ff1-224">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="93ff1-224">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="93ff1-225">設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="93ff1-225">Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection</span></span>](set-up-new-message-encryption-capabilities.md)
  
[<span data-ttu-id="93ff1-226">將商標新增至加密郵件</span><span class="sxs-lookup"><span data-stu-id="93ff1-226">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)
  
[<span data-ttu-id="93ff1-227">Exchange Online 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="93ff1-227">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)
  
[<span data-ttu-id="93ff1-228">Exchange Online Protection 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="93ff1-228">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)
  

