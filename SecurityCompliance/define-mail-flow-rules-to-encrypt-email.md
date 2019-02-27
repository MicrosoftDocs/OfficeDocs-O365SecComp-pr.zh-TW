---
title: 定義郵件流規則以加密 Office 365 中的電子郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: 系統管理員可以了解如何建立郵件流程規則 （也稱為傳輸規則） 來加密和解密郵件使用 Office 365 郵件加密 (OME) 中。
ms.openlocfilehash: f76abe2d341b9e3677a90d447e70f6091e3a91cc
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276203"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a><span data-ttu-id="f0c1d-103">定義郵件流規則以加密 Office 365 中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="f0c1d-103">Define mail flow rules to encrypt email messages in Office 365</span></span>

<span data-ttu-id="f0c1d-p101">身為 Office 365 全域管理員，您可以建立郵件流程規則 （也稱為傳輸規則） 來保護您傳送和接收的電子郵件訊息。您可以設定加密所有外寄電子郵件並從加密的郵件來自組織內或回覆加密郵件傳送自組織移除加密的規則。您可以使用 Exchange 系統管理中心 (EAC) 或 Exchange Online PowerShell 來建立這些規則。除了整體加密的郵件，您也可以選擇啟用或停用使用者的個別郵件加密選項。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p101">As an Office 365 global administrator, you can create mail flow rules (also known as transport rules) to help protect email messages you send and receive. You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization. You can use the Exchange admin center (EAC) or Exchange Online PowerShell to create these rules. In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end-users.</span></span>

||
|:-----|
|<span data-ttu-id="f0c1d-p102">本文屬於較大的一系列有關 Office 365 郵件加密的文章。本文適用於系統管理員和 ITPros 的。如果您只尋找的資訊在傳送或接收加密的郵件，請參閱[Office 365 郵件加密 (OME)](ome.md)中的文章的清單並找出最適合您需求的文章。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p102">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

<span data-ttu-id="f0c1d-p103">如果您最近移轉從 AD RMS Azure 資訊保護，您需要檢閱現有的郵件流程規則以確保其繼續在新環境中運作。此外，如果您想要利用新的 Office 365 郵件加密 (OME) 功能給您透過 Azure 資訊保護，您需要更新現有的郵件流程規則。否則，您的使用者會繼續接收加密的郵件而不是新的且相當順暢 OME 經驗會使用先前的 HTML 附件格式。如果您尚未設定 OME 尚未，請參閱[Set up Office 365 郵件加密的新功能](set-up-new-message-encryption-capabilities.md)的資訊。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p103">If you recently migrated from AD RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment. Additionally, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules. Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience. If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md) for information.</span></span>

<span data-ttu-id="f0c1d-p104">如需元件構成郵件流程規則與郵件流程規則運作的方式，請參閱[Exchange Online 中的郵件流程規則 （傳輸規則）](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。如需搭配 Azure 資訊保護的郵件流程規則如何運作的其他資訊，請參閱[Azure 資訊保護標籤設定 Exchange Online 郵件流程規則](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p104">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules). For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0c1d-p105">混合式 Exchange 環境中，內部使用者可以傳送加密的郵件會使用 OME 只能透過 Exchange Online 路由傳送電子郵件。若要設定 OME 混合式 Exchange 環境中，您需要[設定混合式使用混合組態精靈](https://docs.microsoft.com/Exchange/exchange-hybrid)的第一個，然後[設定郵件流程從 Office 365 電子郵件伺服器以](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。一次您已設定郵件流程透過 Office 365 以則您也可以使用這份指導的 OME 設定郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p105">For hybrid Exchange environments, on-premises users can send encrypted mail using OME only if email is routed through Exchange Online. To configure OME in a hybrid Exchange environment, you need to first [configure hybrid using the Hybrid Configuration wizard](https://docs.microsoft.com/Exchange/exchange-hybrid) and then [configure mail to flow from your email server to Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365). Once you've configured mail to flow through Office 365, then you can configure mail flow rules for OME by using this guidance.</span></span>

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="f0c1d-120">建立郵件流程規則來加密電子郵件使用的新 OME 功能</span><span class="sxs-lookup"><span data-stu-id="f0c1d-120">Create mail flow rules to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="f0c1d-121">您可以定義可使用 EAC 觸發新 OME 功能的郵件加密的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-121">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="f0c1d-122">使用 EAC 來建立可加密電子郵件使用的新 OME 功能的規則</span><span class="sxs-lookup"><span data-stu-id="f0c1d-122">Use the EAC to create a rule for encrypting email messages with the new OME capabilities</span></span>

1. <span data-ttu-id="f0c1d-123">在網頁瀏覽器中使用的工作或學校了已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-123">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="f0c1d-124">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-124">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="f0c1d-125">在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-125">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="f0c1d-p106">在 EAC 中，移至 [**郵件流程** \> **規則**並選取 [**新增**![圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。如需使用 EAC 的詳細資訊，請參閱[Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p106">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="f0c1d-128">在 [**名稱**] 輸入規則名稱，例如 Encrypt mail for DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-128">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="f0c1d-p107">在**套用此規則**選取條件和必要時輸入的值。例如，若要加密郵件移至 DrToniRamos@hotmail.com：</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p107">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="f0c1d-131">在**套用此規則**，請選取 [**收件者**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-131">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="f0c1d-132">從連絡人清單中選取現有名稱或 [**檢查名稱**] 方塊中輸入新的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-132">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="f0c1d-133">若要選取現有名稱，從清單中選取然後再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-133">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="f0c1d-134">輸入新名稱、 在 [**檢查名稱**] 方塊中輸入電子郵件地址，然後選取 [**檢查名稱** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-134">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="f0c1d-135">若要新增多個條件、 選擇 [**更多選項]** 然後選擇 [**新增條件**並從清單中選取。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-135">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span>

   <span data-ttu-id="f0c1d-136">例如，若要將規則套用只有在收件者為組織外部，選取 [**新增條件**，然後選取 [**收件者是外部/內部** \> **組織外** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-136">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="f0c1d-p108">若要啟用加密使用新的 OME 功能，從**執行下列動作**，選取 [**修改郵件安全性**，然後選擇**適用於 Office 365 郵件加密和權限保護**。從清單中選取的 RMS 範本、 選擇 [**儲存**]，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p108">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
  <span data-ttu-id="f0c1d-p109">範本的清單會包含所有的預設範本及 Office 365 所使用的選項為您已建立的任何自訂範本。如果清單是空的請確定您已設定 Office 365 郵件加密的新功能與[設定 Office 365 郵件加密的新功能](set-up-new-message-encryption-capabilities.md)所述。如需預設範本的資訊，請參閱[設定及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。[**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。**僅限加密**] 選項的相關資訊，請參閱[只加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p109">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

  <span data-ttu-id="f0c1d-144">您可以選擇**加入動作**如果您想要指定另一個巨集指令。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-144">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a><span data-ttu-id="f0c1d-145">使用 EAC 來更新現有的郵件流程規則使用的新 OME 功能</span><span class="sxs-lookup"><span data-stu-id="f0c1d-145">Use the EAC to update an existing mail flow rule to use the new OME capabilities</span></span>

1. <span data-ttu-id="f0c1d-146">在網頁瀏覽器中使用的工作或學校了已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-146">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="f0c1d-147">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-147">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="f0c1d-148">在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-148">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="f0c1d-149">在 EAC 中，移至 [**郵件流程** \> **規則**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-149">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

5. <span data-ttu-id="f0c1d-150">在郵件流程規則清單中，選取您想要修改以使用新的 OME 功能，然後選擇 [**編輯**的規則![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-150">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>

6. <span data-ttu-id="f0c1d-p110">若要啟用加密使用新的 OME 功能，從**執行下列動作**，選擇 [**修改郵件安全性**，然後選擇**適用於 Office 365 郵件加密和權限保護**。從清單中選取的 RMS 範本、 選擇 [**儲存]** ，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p110">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>

   <span data-ttu-id="f0c1d-p111">範本的清單會包含所有的預設範本及 Office 365 所使用的選項為您已建立的任何自訂範本。如果清單是空的請確定您已設定 Office 365 郵件加密的新功能與[設定在 Azure 資訊保護頂端上建立新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。如需預設範本的資訊，請參閱[設定及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。[**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。**僅限加密**] 選項的相關資訊，請參閱[只加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p111">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="f0c1d-158">您可以選擇**加入動作**如果您想要指定另一個巨集指令。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-158">You can choose **add action** if you want to specify another action.</span></span>

7. <span data-ttu-id="f0c1d-159">從**執行下列動作**] 清單中移除任何指派給**修改郵件安全性**的動作\>**套用 OME 的舊版本**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-159">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>

8. <span data-ttu-id="f0c1d-160">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-160">Choose **Save**.</span></span>

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="f0c1d-161">建立郵件流程規則 Office 365 郵件加密的沒有的新功能</span><span class="sxs-lookup"><span data-stu-id="f0c1d-161">Create mail flow rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="f0c1d-p112">若您尚未尚未移動 Office 365 組織到新的 OME 功能，可用於這些工作定義加密您的組織的郵件的郵件流程規則。Microsoft 建議您將移至新的 OME 功能一旦是組織的合理的計劃。指示，請參閱[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p112">If you haven't yet moved your Office 365 organization to the new OME capabilities, use these tasks to define mail flow rules to encrypt messages for your organization. Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span>

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="f0c1d-165">使用 EAC 來建立可加密電子郵件訊息的新 OME 功能而郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="f0c1d-165">Use the EAC to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="f0c1d-166">在網頁瀏覽器中使用的工作或學校了已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-166">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="f0c1d-167">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-167">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="f0c1d-168">在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-168">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="f0c1d-p113">在 EAC 中，移至 [**郵件流程** \> **規則**並選取 [**新增**![圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。如需使用 EAC 的詳細資訊，請參閱[Exchange admin 中心在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p113">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**. For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="f0c1d-171">在 [**名稱**] 輸入規則名稱，例如 Encrypt mail for DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-171">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="f0c1d-p114">在**套用此規則**選取條件和必要時輸入的值。例如，若要加密郵件移至 DrToniRamos@hotmail.com：</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p114">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="f0c1d-174">在**套用此規則**，請選取 [**收件者**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-174">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="f0c1d-175">從連絡人清單中選取現有名稱或 [**檢查名稱**] 方塊中輸入新的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-175">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="f0c1d-176">若要選取現有名稱，從清單中選取然後再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-176">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="f0c1d-177">輸入新名稱、 在 [**檢查名稱**] 方塊中輸入電子郵件地址，然後選取 [**檢查名稱** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-177">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="f0c1d-178">若要新增多個條件、 選擇 [**更多選項]** 然後選取 [**新增條件**與從清單中選取。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-178">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span>

   <span data-ttu-id="f0c1d-179">例如，若要將規則套用只有在收件者為組織外部，選取 [**新增條件**，然後選取 [**收件者是外部/內部** \> **組織外** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-179">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="f0c1d-180">若要啟用加密沒有使用新的 OME 功能，**請執行下列操作**，請選取 [**修改郵件安全性** \> **套用 OME 的前一版**]，然後選擇 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-180">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>

  <span data-ttu-id="f0c1d-p115">如果您收到未啟用 IRM 授權，則您尚未為您的組織尚未設定 OME 的錯誤。如果您想要立即設定 OME，您必須設定為使用新的 OME 功能。資訊，請參閱[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護](set-up-new-message-encryption-capabilities.md)。Microsoft 不再支援的 OME 而的新功能的新部署的設定。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p115">If you receive an error that IRM licensing isn't enabled, then you haven't set up OME for your organization yet. If you'd like to set up OME now, you must set it up to use the new OME capabilities. For information, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). Microsoft no longer supports setting up new deployments of OME without the new capabilities.</span></span>

  <span data-ttu-id="f0c1d-185">您可以選擇**加入動作**如果您想要指定另一個巨集指令。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-185">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="f0c1d-186">使用 Exchange Online PowerShell 建立可加密電子郵件的新 OME 功能而郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="f0c1d-186">Use Exchange Online PowerShell to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="f0c1d-p116">連線到 Exchange Online PowerShell。如需詳細資訊，請參閱[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p116">Connect to Exchange Online PowerShell. For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f0c1d-189">使用**New-transportrule**指令程式來建立規則並將_ApplyOME_參數設為`$true`。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-189">Create a rule by using the **New-TransportRule** cmdlet and set the _ApplyOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="f0c1d-190">這個範例需要在所有的電子郵件訊息傳送給 DrToniRamos@hotmail.com 必須進行加密。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-190">This example requires that all email messages sent to DrToniRamos@hotmail.com must be encrypted.</span></span>

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   <span data-ttu-id="f0c1d-191">**附註**：</span><span class="sxs-lookup"><span data-stu-id="f0c1d-191">**Notes**:</span></span>

   - <span data-ttu-id="f0c1d-192">新規則的唯一名稱為"加密規則 Dr Toni Ramos"。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-192">The unique name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>

   - <span data-ttu-id="f0c1d-p117">_SentTo_參數會指定郵件收件者 （識別由名稱、 電子郵件地址、 辨別的名稱等）。。在這個範例中，收件者可識別的電子郵件地址"DrToniRamos@hotmail.com"。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p117">The _SentTo_ parameter specifies the message recipients (identified by name, email address, distinguished name, etc.). In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span>

   - <span data-ttu-id="f0c1d-p118">_SentToScope_參數會指定郵件的收件者的位置。在本例中為收件者的信箱在 hotmail 而不屬於 Office 365 組織，所以值`NotInOrganization`使用。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p118">The _SentToScope_ parameter specifies the location of the message recipients. In this example, the recipient's mailbox is in hotmail and is not part of the Office 365 organization, so the value `NotInOrganization` is used.</span></span>

   <span data-ttu-id="f0c1d-197">如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-197">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="f0c1d-198">移除新 OME 功能不加密的電子郵件回覆的加密</span><span class="sxs-lookup"><span data-stu-id="f0c1d-198">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="f0c1d-p119">當您的電子郵件使用者傳送加密的郵件時，那些郵件的收件者可以使用加密回覆與回應。您可以建立郵件流程規則來自動移除加密回覆讓組織中的電子郵件使用者不需要登入加密入口網站以進行檢視。您可以使用 EAC 或 Windows PowerShell cmdlet 來定義這些規則。如果您不尚未使用新的 OME 功能，您可以僅解密其中一個從您的組織或組織內傳送訊息的回覆的郵件中傳送的郵件。您無法解密源自組織外的加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p119">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies. You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them. You can use the EAC or Windows PowerShell cmdlets to define these rules. If you are not yet using the new OME capabilities, you can only decrypt messages that are either sent from within your organization or messages that are replies to messages sent from within your organization. You cannot decrypt encrypted messages originating from outside of your organization.</span></span>

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="f0c1d-204">使用 EAC 來建立移除新 OME 功能不加密的電子郵件回覆中加密的規則</span><span class="sxs-lookup"><span data-stu-id="f0c1d-204">Use the EAC to create a rule for removing encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="f0c1d-205">在網頁瀏覽器中使用的工作或學校了已授與管理員的權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-205">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="f0c1d-206">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-206">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="f0c1d-207">在 Office 365 系統管理中心中，選擇 [ **Admin 中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-207">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="f0c1d-p120">在 EAC 中，移至 [**郵件流程** \> **規則**並選取 [**新增**![圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。如需使用 EAC 的詳細資訊，請參閱[Exchange admin 中心在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p120">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**. For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="f0c1d-210">在 [**名稱**] 輸入規則名稱，例如 Remove encryption from incoming mail。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-210">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>

6. <span data-ttu-id="f0c1d-211">在**套用此規則**選取的條件的郵件，例如**收件者位於**應該移除加密\>**在組織內**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-211">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>

7. <span data-ttu-id="f0c1d-212">在**執行下列動作**，選取 [**修改郵件安全性** \> **OME 的舊版本中移除**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-212">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>

8. <span data-ttu-id="f0c1d-213">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-213">Select **Save**.</span></span>

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="f0c1d-214">使用 Exchange Online PowerShell 建立可移除新 OME 功能不加密的電子郵件回覆中加密的規則</span><span class="sxs-lookup"><span data-stu-id="f0c1d-214">Use Exchange Online PowerShell to create a rule to remove encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="f0c1d-p121">連線到 Exchange Online PowerShell。如需詳細資訊，請參閱[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p121">Connect to Exchange Online PowerShell. For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f0c1d-217">使用**New-transportrule**指令程式來建立規則並將_RemoveOME_參數設為`$true`。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-217">Create a rule by using the **New-TransportRule** cmdlet and set the _RemoveOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="f0c1d-218">此範例會移除所有傳送給 Office 365 組織中的收件者的郵件加密。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-218">This example removes the encryption from all mail sent to recipients in the Office 365 organization.</span></span>

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   <span data-ttu-id="f0c1d-219">**附註**：</span><span class="sxs-lookup"><span data-stu-id="f0c1d-219">**Notes**:</span></span>

   - <span data-ttu-id="f0c1d-220">新規則的唯一名稱為"Remove encryption from incoming mail"。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-220">The unique name of the new rule is "Remove encryption from incoming mail".</span></span>

   - <span data-ttu-id="f0c1d-p122">_SentToScope_參數會指定郵件的收件者的位置。在這個範例中，此值`InOrganization`會使用值，這表示：</span><span class="sxs-lookup"><span data-stu-id="f0c1d-p122">The _SentToScope_ parameter specifies the location of the message recipients. In this example, the value `InOrganization` value is used, which indicates:</span></span>

     - <span data-ttu-id="f0c1d-223">收件者是信箱、 郵件使用者、 群組或擁有郵件功能在組織中的公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-223">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization.</span></span>

       <span data-ttu-id="f0c1d-224">或</span><span class="sxs-lookup"><span data-stu-id="f0c1d-224">or</span></span>

     - <span data-ttu-id="f0c1d-225">收件者的電子郵件地址是設定為授權網域] 或 [內部轉送網域_與_郵件已傳送或接收透過未經過驗證的連線在組織中公認的網域中。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-225">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain in your organization, _and_ the message was sent or received over an authenticated connection.</span></span>

<span data-ttu-id="f0c1d-226">如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="f0c1d-226">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f0c1d-227">相關主題</span><span class="sxs-lookup"><span data-stu-id="f0c1d-227">Related Topics</span></span>

[<span data-ttu-id="f0c1d-228">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="f0c1d-228">Encryption in Office 365</span></span>](encryption.md)

[<span data-ttu-id="f0c1d-229">設定全新的 Office 365 郵件加密功能</span><span class="sxs-lookup"><span data-stu-id="f0c1d-229">Set up new Office 365 Message Encryption capabilities</span></span>](set-up-new-message-encryption-capabilities.md)

[<span data-ttu-id="f0c1d-230">將商標新增至加密郵件</span><span class="sxs-lookup"><span data-stu-id="f0c1d-230">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)

[<span data-ttu-id="f0c1d-231">Exchange Online 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="f0c1d-231">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[<span data-ttu-id="f0c1d-232">Exchange Online Protection 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="f0c1d-232">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)
