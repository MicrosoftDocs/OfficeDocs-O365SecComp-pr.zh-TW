---
title: 定義加密 Office 365 中的電子郵件的郵件流程規則
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
description: 身為 Office 365 全域管理員，您可以建立郵件流程規則來啟用 Office 365 郵件加密 (OME)。您可以加密所有外寄電子郵件並從內部訊息或回覆加密郵件傳送自組織移除加密。
ms.openlocfilehash: bd94d36543653d5767fe27aee0f859fe9e374b2f
ms.sourcegitcommit: c0f5c92664b3fbed7b3c2f8232bb4046fc19d1b7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "25890031"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a><span data-ttu-id="af766-104">定義加密 Office 365 中的電子郵件的郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="af766-104">Define mail flow rules to encrypt email messages in Office 365</span></span>

<span data-ttu-id="af766-p102">身為 Office 365 全域管理員，您可以建立郵件流程規則，也稱為傳輸規則，以協助保護您傳送和接收的電子郵件訊息。您可以設定加密所有外寄電子郵件並從加密的郵件來自組織內或回覆加密郵件傳送自組織移除加密的規則。您可以使用 Exchange 系統管理中心 (EAC) 或 Exchange Online 的 Windows PowerShell cmdlet 建立這些規則。 除了整體加密的郵件，您也可以選擇啟用或停用使用者的個別郵件加密選項。</span><span class="sxs-lookup"><span data-stu-id="af766-p102">As an Office 365 global administrator, you can create mail flow rules, also known as transport rules, to help protect email messages you send and receive. You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization. You can use the Exchange admin center (EAC) or Windows PowerShell cmdlets for Exchange Online to create these rules.  In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end-users.</span></span>
  
<span data-ttu-id="af766-p103">如果您最近移轉從 AD RMS Azure 資訊保護，您需要檢閱現有的郵件流程規則以確保其繼續在新環境中運作。此外，如果您想要利用新的 Office 365 郵件加密 (OME) 功能給您透過 Azure 資訊保護，您需要更新現有的郵件流程規則。否則，您的使用者會繼續接收加密的郵件而不是新的且相當順暢 OME 經驗會使用先前的 HTML 附件格式。如果您尚未設定 OME 尚未，請參閱[Set up 新建置上方的 Azure 資訊保護的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="af766-p103">If you recently migrated from AD RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment. Additionally, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules. Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience. If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md) for information.</span></span> 
  
<span data-ttu-id="af766-p104">如需元件構成郵件流程規則與郵件流程規則運作的方式，請參閱[Exchange Online 中的郵件流程規則 （傳輸規則）](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)。如需搭配 Azure 資訊保護的郵件流程規則如何運作的其他資訊，請參閱[Azure 資訊保護標籤設定 Exchange Online 郵件流程規則](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。</span><span class="sxs-lookup"><span data-stu-id="af766-p104">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx). For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>
  
## <a name="hybrid-exchange-environments-do-this-first"></a><span data-ttu-id="af766-115">Exchange 的混合式環境： 先執行此作業</span><span class="sxs-lookup"><span data-stu-id="af766-115">Hybrid Exchange environments: Do this first</span></span>
<span data-ttu-id="af766-p105">內部使用者可以傳送加密的郵件路由傳送到 Exchange Online 電子郵件會使用 OME。若要這樣做，您需要設定流程電子郵件伺服器的 Office 365 的郵件。一次您已設定郵件以透過 Office 365 的流程接著您可以使用本文的 OME 設定郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="af766-p105">On-premises users can send encrypted mail using OME if you route email through Exchange Online. In order to do this, you need to configure mail to flow from your email server to Office 365. Once you've configured mail to flow through Office 365, then you can make mail flow rules for OME by using this article.</span></span>

<span data-ttu-id="af766-p106">指示，請參閱[Set up Office 365 與電子郵件伺服器之間的郵件路由傳送連接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)。特別是，完成的步驟 「 第 2 部分： 設定郵件流程電子郵件伺服器的 Office 365 以"。</span><span class="sxs-lookup"><span data-stu-id="af766-p106">For instructions, see [Set up connectors to route mail between Office 365 and your own email servers](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail). In particular, complete the steps in "Part 2: Configure mail to flow from your email server to Office 365".</span></span>

## <a name="create-a-mail-flow-rule-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="af766-121">建立郵件流程規則來加密電子郵件使用的新 OME 功能</span><span class="sxs-lookup"><span data-stu-id="af766-121">Create a mail flow rule to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="af766-122">您可以定義可使用 EAC 觸發新 OME 功能的郵件加密的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="af766-122">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>
  
### <a name="to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="af766-123">若要建立可加密電子郵件使用的新 OME 功能使用 EAC 的規則</span><span class="sxs-lookup"><span data-stu-id="af766-123">To create a rule for encrypting email messages with the new OME capabilities by using the EAC</span></span>

1. <span data-ttu-id="af766-124">在網頁瀏覽器中使用的工作或學校了已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="af766-124">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="af766-125">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="af766-125">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="af766-126">在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="af766-126">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="af766-p107">在 EAC 中，移至 [**郵件流程** \> **規則** \> ![圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)(**新增**) \> **建立新的規則**。如需使用 EAC 的詳細資訊，請參閱[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="af766-p107">In the EAC, go to **mail flow** \> **rules** \> ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) ( **New**) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx).</span></span>
    
5. <span data-ttu-id="af766-129">在 [**名稱**] 輸入規則名稱，例如 Encrypt mail for DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="af766-129">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>
    
6. <span data-ttu-id="af766-p108">在**套用此規則**選取條件和必要時輸入的值。例如，若要加密郵件移至 DrToniRamos@hotmail.com：</span><span class="sxs-lookup"><span data-stu-id="af766-p108">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span> 
    
    1. <span data-ttu-id="af766-132">在**套用此規則**，請選取 [**收件者**。</span><span class="sxs-lookup"><span data-stu-id="af766-132">In **Apply this rule if**, select **the recipient is**.</span></span>
    
    2. <span data-ttu-id="af766-133">從連絡人清單中選取現有名稱或 [**檢查名稱**] 方塊中輸入新的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="af766-133">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span> 
    
        <span data-ttu-id="af766-134">若要選取現有名稱，從清單中選取然後再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="af766-134">To select an existing name, select it from the list and then click **OK**.</span></span>
    
        <span data-ttu-id="af766-135">輸入新名稱、 在 [**檢查名稱**] 方塊中輸入電子郵件地址，然後選取 [**檢查名稱** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="af766-135">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>
    
7. <span data-ttu-id="af766-136">若要新增多個條件、 選擇 [**更多選項]** 然後選擇 [**新增條件**並從清單中選取。</span><span class="sxs-lookup"><span data-stu-id="af766-136">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span> 
    
    <span data-ttu-id="af766-137">例如，若要將規則套用只有在收件者為組織外部，選取 [**新增條件**，然後選取 [**收件者是外部/內部** \> **組織外** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="af766-137">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>
    
8. <span data-ttu-id="af766-p109">若要啟用加密使用新的 OME 功能，從**執行下列動作**，選取 [**修改郵件安全性**，然後選擇**適用於 Office 365 郵件加密和權限保護**。從清單中選取的 RMS 範本、 選擇 [**儲存**]，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="af766-p109">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
    
    <span data-ttu-id="af766-p110">範本的清單會包含所有的預設範本及 Office 365 所使用的選項為您已建立的任何自訂範本。如果清單是空的請確定您已設定 Office 365 郵件加密的新功能與[設定在 Azure 資訊保護頂端上建立新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。如需預設範本的資訊，請參閱[設定及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。[**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。**僅限加密**] 選項的相關資訊，請參閱[只加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="af766-p110">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>
    
    <span data-ttu-id="af766-145">您可以選擇**加入動作**如果您想要指定另一個巨集指令。</span><span class="sxs-lookup"><span data-stu-id="af766-145">You can choose **add action** if you want to specify another action.</span></span> 
    
### <a name="to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="af766-146">更新現有的郵件流程規則來使用 EAC OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="af766-146">To update an existing mail flow rule to use the new OME capabilities by using the EAC</span></span>

1. <span data-ttu-id="af766-147">在網頁瀏覽器中使用的工作或學校了已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="af766-147">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="af766-148">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="af766-148">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="af766-149">在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="af766-149">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="af766-150">在 EAC 中，移至 [**郵件流程** \> **規則**。</span><span class="sxs-lookup"><span data-stu-id="af766-150">In the EAC, go to **mail flow** \> **rules**.</span></span>
    
5. <span data-ttu-id="af766-151">在郵件流程規則清單中，選取您想要使用的新 OME 功能，然後選擇 [修改的規則![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)（**編輯**）。</span><span class="sxs-lookup"><span data-stu-id="af766-151">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ( **Edit**).</span></span>
    
6. <span data-ttu-id="af766-p111">若要啟用加密使用新的 OME 功能，從**執行下列動作**，選擇 [**修改郵件安全性**，然後選擇**適用於 Office 365 郵件加密和權限保護**。從清單中選取的 RMS 範本、 選擇 [**儲存]** ，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="af766-p111">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>
    
    <span data-ttu-id="af766-p112">範本的清單會包含所有的預設範本及 Office 365 所使用的選項為您已建立的任何自訂範本。如果清單是空的請確定您已設定 Office 365 郵件加密的新功能與[設定在 Azure 資訊保護頂端上建立新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。如需預設範本的資訊，請參閱[設定及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。[**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。**僅限加密**] 選項的相關資訊，請參閱[只加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="af766-p112">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>
    
    <span data-ttu-id="af766-159">您可以選擇**加入動作**如果您想要指定另一個巨集指令。</span><span class="sxs-lookup"><span data-stu-id="af766-159">You can choose **add action** if you want to specify another action.</span></span> 
    
7. <span data-ttu-id="af766-160">從**執行下列動作**] 清單中移除任何指派給**修改郵件安全性**的動作\>**套用 OME 的舊版本**。</span><span class="sxs-lookup"><span data-stu-id="af766-160">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>
    
8. <span data-ttu-id="af766-161">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="af766-161">Choose **Save**.</span></span>
    
## <a name="creating-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="af766-162">不使用的新功能建立 Office 365 郵件加密的規則</span><span class="sxs-lookup"><span data-stu-id="af766-162">Creating rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="af766-p113">若您尚未尚未移動 Office 365 組織到新的 OME 功能，可用於這些工作定義加密您的組織的郵件的郵件流程規則。Microsoft 建議您將移至新的 OME 功能一旦是組織的合理的計劃。指示，請參閱[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="af766-p113">If you haven't yet moved your Office 365 organization to the new OME capabilities, use these tasks to define mail flow rules to encrypt messages for your organization. Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span>
  
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="af766-166">若要建立可加密電子郵件訊息的新 OME 功能不使用 EAC 的規則</span><span class="sxs-lookup"><span data-stu-id="af766-166">To create a rule for encrypting email messages without the new OME capabilities by using the EAC</span></span>

1. <span data-ttu-id="af766-167">在網頁瀏覽器中使用的工作或學校了已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="af766-167">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="af766-168">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="af766-168">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="af766-169">在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="af766-169">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="af766-p114">在 EAC 中，移至 [**郵件流程** \> **規則** \> **+** (**新增**) \> **建立新的規則**。如需使用 EAC 的詳細資訊，請參閱[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="af766-p114">In the EAC, go to **mail flow** \> **rules** \> **+** ( **New**) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx).</span></span>
    
5. <span data-ttu-id="af766-172">在 [**名稱**] 輸入規則名稱，例如 Encrypt mail for DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="af766-172">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>
    
6. <span data-ttu-id="af766-p115">在**套用此規則**選取條件和必要時輸入的值。例如，若要加密郵件移至 DrToniRamos@hotmail.com：</span><span class="sxs-lookup"><span data-stu-id="af766-p115">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span> 
    
1. <span data-ttu-id="af766-175">在**套用此規則**，請選取 [**收件者**。</span><span class="sxs-lookup"><span data-stu-id="af766-175">In **Apply this rule if**, select **the recipient is**.</span></span>
    
2. <span data-ttu-id="af766-176">從連絡人清單中選取現有名稱或 [**檢查名稱**] 方塊中輸入新的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="af766-176">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span> 
    
    <span data-ttu-id="af766-177">若要選取現有名稱，從清單中選取然後再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="af766-177">To select an existing name, select it from the list and then click **OK**.</span></span>
    
    <span data-ttu-id="af766-178">輸入新名稱、 在 [**檢查名稱**] 方塊中輸入電子郵件地址，然後選取 [**檢查名稱** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="af766-178">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>
    
7. <span data-ttu-id="af766-179">若要新增多個條件、 選擇 [**更多選項]** 然後選取 [**新增條件**與從清單中選取。</span><span class="sxs-lookup"><span data-stu-id="af766-179">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span> 
    
    <span data-ttu-id="af766-180">例如，若要將規則套用只有在收件者為組織外部，選取 [**新增條件**，然後選取 [**收件者是外部/內部** \> **組織外** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="af766-180">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>
    
8. <span data-ttu-id="af766-181">若要啟用加密沒有使用新的 OME 功能，**請執行下列操作**，請選取 [**修改郵件安全性** \> **套用 OME 的前一版**]，然後選擇 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="af766-181">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>
    
    <span data-ttu-id="af766-p116">如果您收到未啟用 IRM 授權，則您尚未為您的組織尚未設定 OME 的錯誤。如果您想要立即設定 OME，您必須設定為使用新的 OME 功能。資訊，請參閱[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護](set-up-new-message-encryption-capabilities.md)。Microsoft 不再支援的 OME 而的新功能的新部署的設定。</span><span class="sxs-lookup"><span data-stu-id="af766-p116">If you receive an error that IRM licensing isn't enabled, then you haven't set up OME for your organization yet. If you'd like to set up OME now, you must set it up to use the new OME capabilities. For information, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). Microsoft no longer supports setting up new deployments of OME without the new capabilities.</span></span>
    
    <span data-ttu-id="af766-186">您可以選擇**加入動作**如果您想要指定另一個巨集指令。</span><span class="sxs-lookup"><span data-stu-id="af766-186">You can choose **add action** if you want to specify another action.</span></span> 
    
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a><span data-ttu-id="af766-187">若要建立可加密電子郵件訊息的新 OME 功能不使用 Exchange Online 的 Windows PowerShell 規則</span><span class="sxs-lookup"><span data-stu-id="af766-187">To create a rule for encrypting email messages without the new OME capabilities by using Windows PowerShell for Exchange Online</span></span>

1. <span data-ttu-id="af766-p117">使用本機電腦上的 Windows PowerShell 建立至 Exchange Online 的遠端 PowerShell 工作階段。如需詳細資訊，請參閱[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="af766-p117">Use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online. For more information, see [Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).</span></span>
    
2. <span data-ttu-id="af766-190">使用**New-transportrule**指令程式來定義規則並將**ApplyOME**屬性設定為**true**。</span><span class="sxs-lookup"><span data-stu-id="af766-190">Define a rule by using the **New-TransportRule** cmdlet and set the **ApplyOME** attribute to **true**.</span></span>
    
    <span data-ttu-id="af766-191">例如，若要要求必須加密所有電子郵件訊息傳送給 DrToniRamos@hotmail.com，請輸入：</span><span class="sxs-lookup"><span data-stu-id="af766-191">For example, to require that all email messages that are addressed to DrToniRamos@hotmail.com must be encrypted, type:</span></span>
    
     ```
     New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
     ```

    <span data-ttu-id="af766-192">在此範例中：</span><span class="sxs-lookup"><span data-stu-id="af766-192">In this example:</span></span>
    
  - <span data-ttu-id="af766-193">新規則的名稱為"加密規則 Dr Toni Ramos"。</span><span class="sxs-lookup"><span data-stu-id="af766-193">The name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>
    
  - <span data-ttu-id="af766-p118">**-SentTo**參數會指定尋找收件者電子郵件訊息中的條件。您可以使用唯一識別收件者，例如電子郵件地址、 名稱、 辨別的名稱 (DN) 等的任何值。在這個範例中，收件者可識別的電子郵件地址"DrToniRamos@hotmail.com"。</span><span class="sxs-lookup"><span data-stu-id="af766-p118">The **-SentTo** parameter, specifies a condition that looks for recipients in email messages. You can use any value that uniquely identifies the recipient, such as an email address, name, distinguished name (DN), etc. In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span> 
    
  - <span data-ttu-id="af766-p119">**-SentToScope**參數會指定條件所尋找的收件者的位置。在本例中為收件者的信箱在 hotmail 而不屬於 Office 365 組織，因此會使用"NotInOrganization"值。</span><span class="sxs-lookup"><span data-stu-id="af766-p119">The **-SentToScope** parameter specifies a condition that looks for the location of recipients. In this example, the recipient's mailbox is in hotmail and is not part of the Office 365 organization, so the "NotInOrganization" value is used.</span></span> 
    
    <span data-ttu-id="af766-198">如需詳細資訊條件您可以使用此指令程式的郵件流程規則上設定，請參閱[New-transportrule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="af766-198">For more information about the conditions you can set on mail flow rules using this cmdlet, see [New-TransportRule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx).</span></span>
    
### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="af766-199">移除新 OME 功能不加密的電子郵件回覆的加密</span><span class="sxs-lookup"><span data-stu-id="af766-199">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="af766-p120">當您的電子郵件使用者傳送加密的郵件時，那些郵件的收件者可以使用加密回覆與回應。您可以建立郵件流程規則來自動移除加密回覆讓組織中的電子郵件使用者不需要登入加密入口網站以進行檢視。您可以使用 EAC 或 Windows PowerShell cmdlet 來定義這些規則。如果您不尚未使用新的 OME 功能，您可以僅解密其中一個從您的組織或組織內傳送訊息的回覆的郵件中傳送的郵件。您無法解密源自組織外的加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="af766-p120">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies. You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them. You can use the EAC or Windows PowerShell cmdlets to define these rules. If you are not yet using the new OME capabilities, you can only decrypt messages that are either sent from within your organization or messages that are replies to messages sent from within your organization. You cannot decrypt encrypted messages originating from outside of your organization.</span></span>
  
#### <a name="to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="af766-205">若要建立移除新 OME 功能不使用 EAC 來加密的電子郵件回覆中加密的規則</span><span class="sxs-lookup"><span data-stu-id="af766-205">To create a rule for removing encryption from email replies encrypted without the new OME capabilities by using the EAC</span></span>
<span data-ttu-id="af766-206"><a name="DecryptruleEACNoNewOME"> </a></span><span class="sxs-lookup"><span data-stu-id="af766-206"></span></span>

1. <span data-ttu-id="af766-207">在網頁瀏覽器中使用的工作或學校了已授與管理員的權限，[登入 Office 365](https://support.office.com/article/Sign-in-to-Office-or-Office-365-b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="af766-207">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/Sign-in-to-Office-or-Office-365-b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="af766-208">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="af766-208">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="af766-209">在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="af766-209">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="af766-p121">在 EAC 中，移至 [**郵件流程** \> **規則** \> **+** (**新增**) \> **建立新的規則**。如需使用 EAC 的詳細資訊，請參閱[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/en-us/library/jj200743%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="af766-p121">In the EAC, go to **mail flow** \> **rules** \> **+** ( **New**) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/en-us/library/jj200743%28v=exchg.150%29.aspx).</span></span>
    
5. <span data-ttu-id="af766-212">在 [**名稱**] 輸入規則名稱，例如 Remove encryption from incoming mail。</span><span class="sxs-lookup"><span data-stu-id="af766-212">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>
    
6. <span data-ttu-id="af766-213">在**套用此規則**選取的條件的郵件，例如**收件者位於**應該移除加密\>**在組織內**。</span><span class="sxs-lookup"><span data-stu-id="af766-213">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>
    
7. <span data-ttu-id="af766-214">在**執行下列動作**，選取 [**修改郵件安全性** \> **OME 的舊版本中移除**。</span><span class="sxs-lookup"><span data-stu-id="af766-214">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>
    
8. <span data-ttu-id="af766-215">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="af766-215">Select **Save**.</span></span>
    
#### <a name="to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a><span data-ttu-id="af766-216">若要建立可移除新 OME 功能不使用 Exchange Online 的 Windows PowerShell 加密的電子郵件回覆中加密的規則</span><span class="sxs-lookup"><span data-stu-id="af766-216">To create a rule to remove encryption from email replies encrypted without the new OME capabilities by using Windows PowerShell for Exchange Online</span></span>
<span data-ttu-id="af766-217"><a name="DecryptrulePShellNoNewOME"> </a></span><span class="sxs-lookup"><span data-stu-id="af766-217"></span></span>

1. <span data-ttu-id="af766-p122">使用本機電腦上的 Windows PowerShell 建立至 Exchange Online 的遠端 PowerShell 工作階段。如需詳細資訊，請參閱[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="af766-p122">Use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online. For more information, see [Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).</span></span>
    
2. <span data-ttu-id="af766-220">使用**New-transportrule**指令程式來定義規則並將**RemoveOME**屬性設定為**true**。</span><span class="sxs-lookup"><span data-stu-id="af766-220">Define a rule by using the **New-TransportRule** cmdlet and set the **RemoveOME** attribute to **true**.</span></span>
    
    <span data-ttu-id="af766-221">例如，若要移除所有傳送給 Office 365 組織中的收件者的郵件加密，請輸入：</span><span class="sxs-lookup"><span data-stu-id="af766-221">For example, to remove the encryption from all mail sent to recipients in your Office 365 organization, type:</span></span>
    
     ```
     New-TransportRule - Name "Remove encryption from incoming mail"     -SentToScope "InOrganization" -RemoveOME $true
     ```

    <span data-ttu-id="af766-222">在此範例中：</span><span class="sxs-lookup"><span data-stu-id="af766-222">In this example:</span></span>
    
  - <span data-ttu-id="af766-223">新規則的名稱為"Remove encryption from incoming mail"。</span><span class="sxs-lookup"><span data-stu-id="af766-223">The name of the new rule is "Remove encryption from incoming mail".</span></span>
    
  - <span data-ttu-id="af766-p123">**-SentToScope**參數會指定條件所尋找的收件者的位置。在這個範例中，會使用"InOrganization"值會指出的：</span><span class="sxs-lookup"><span data-stu-id="af766-p123">The **-SentToScope** parameter specifies a condition that looks for the location of recipients. In this example, the "InOrganization" value is used which indicates that:</span></span> 
    
  - <span data-ttu-id="af766-226">收件者是信箱、 郵件使用者、 群組或擁有郵件功能在您的組織中的公用資料夾或</span><span class="sxs-lookup"><span data-stu-id="af766-226">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization, or</span></span>
    
  - <span data-ttu-id="af766-227">收件者的電子郵件地址中公認的網域設定為授權網域] 或 [內部轉送網域，且郵件已傳送或接收透過未經過驗證的連線。</span><span class="sxs-lookup"><span data-stu-id="af766-227">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain, and the message was sent or received over an authenticated connection.</span></span>
    
    <span data-ttu-id="af766-228">如需詳細資訊條件您可以使用此指令程式的郵件流程規則上設定，請參閱[New-transportrule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="af766-228">For more information about the conditions you can set on mail flow rules using this cmdlet, see [New-TransportRule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="af766-229">相關主題</span><span class="sxs-lookup"><span data-stu-id="af766-229">Related Topics</span></span>

[<span data-ttu-id="af766-230">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="af766-230">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="af766-231">設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="af766-231">Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection</span></span>](set-up-new-message-encryption-capabilities.md)
  
[<span data-ttu-id="af766-232">將商標新增至加密郵件</span><span class="sxs-lookup"><span data-stu-id="af766-232">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)
  
[<span data-ttu-id="af766-233">Exchange Online 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="af766-233">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)
  
[<span data-ttu-id="af766-234">Exchange Online Protection 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="af766-234">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)
  

