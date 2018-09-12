---
title: 設定全新的 Office 365 郵件加密功能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: 內建置於 Azure 資訊保護、 貴組織的功能可以使用新的 Office 365 郵件加密受保護的電子郵件通訊與組織內外的人。與其他 Office 365 組織、 Outlook.com、 Gmail、 及其他電子郵件服務搭配使用的新 OME 功能。
ms.openlocfilehash: c24b2f9b612b863217df8afd951424d1a89295c9
ms.sourcegitcommit: d89c24258123a3ffde574a391d59afd3aea8470d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2018
ms.locfileid: "23955415"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="3308f-104">設定全新的 Office 365 郵件加密功能</span><span class="sxs-lookup"><span data-stu-id="3308f-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="3308f-p102">新的 Office 365 郵件加密 (OME) 功能運用在 Azure 資訊保護的保護功能，您的組織可以輕鬆地共用受保護的電子郵件與任何裝置上的任何人。使用者可以傳送及接收與其他 Office 365 組織以及非 Office 365 客戶使用 Outlook.com、 Gmail，以及其他電子郵件服務受保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="3308f-p102">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device. Users can send and receive protected messages with other Office 365 organizations as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>
  
## <a name="get-started-with-ome-by-activating-azure-rights-management-part-of-azure-information-protection"></a><span data-ttu-id="3308f-107">快速入門 OME 啟用 Azure Rights Management，Azure 資訊保護的一部分</span><span class="sxs-lookup"><span data-stu-id="3308f-107">Get started with OME by activating Azure Rights Management, part of Azure Information Protection</span></span>

<span data-ttu-id="3308f-p103">現在要並容易開始使用新的 OME 功能。年 2 月 2018 Office 365 會自動啟用合格組織內我們資料中心的新 OME 功能。如果它是新的 Office 365 租用戶和您的組織有適當訂閱，則合格貴組織。**如果您已啟用 Azure 版權管理 (Azure RMS) 一部分 Azure 資訊保護，則我們會自動為您啟用 Office 365 郵件加密。** 您不需要執行任何動作啟用 OME。若要啟動 Azure Rights Management，請參閱 ＜[啟動 Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)。如需訂閱，請參閱"何種訂閱的我需要使用新的 OME capabilities?" [Office 365 郵件加密常見問題集](ome-faq.md)。如需購買訂閱 Azure 資訊保護資訊，請參閱[Azure 資訊保護](https://azure.microsoft.com/services/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="3308f-p103">It's now easy to get started with the new OME capabilities. As of February 2018, Office 365 automatically enables the new OME capabilities for eligible organizations within our datacenters. Your organization is eligible if it is a new Office 365 tenant and your organization has the appropriate subscriptions. **If you have enabled Azure Rights Management (Azure RMS), part of Azure Information Protection, then we automatically enable Office 365 Message Encryption for you.** You don't have to do anything else to enable OME. To activate Azure Rights Management, see [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service). For information on subscriptions, see "What subscriptions do I need to use the new OME capabilities?" in the [Office 365 Message Encryption FAQ](ome-faq.md). For information about purchasing a subscription to Azure Information Protection, see [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>
  
<span data-ttu-id="3308f-p104">如果您使用 Exchange Online 與 Active Directory Rights Management service (AD RMS)，就無法立即啟用這些新功能。而您需要先移轉從 AD RMS Azure 資訊保護。當您已經完成移轉時，您可以成功地完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="3308f-p104">If you are using Exchange Online with Active Directory Rights Management service (AD RMS), you can't enable these new capabilities right away. Instead, you need to migrate from AD RMS to Azure Information Protection first. When you've finished the migration, you can successfully complete these steps.</span></span>
  
<span data-ttu-id="3308f-120">如果您選擇繼續使用內部部署 AD RMS 與 Exchange Online 而不是移轉至 Azure 資訊保護，您將無法使用這些新功能。</span><span class="sxs-lookup"><span data-stu-id="3308f-120">If you choose to continue to use on-premises AD RMS with Exchange Online instead of migrating to Azure Information Protection, you will not be able to use these new capabilities.</span></span>
  
## <a name="how-the-new-capabilities-for-ome-work"></a><span data-ttu-id="3308f-121">OME 新功能的運作方式</span><span class="sxs-lookup"><span data-stu-id="3308f-121">How the new capabilities for OME work</span></span>

<span data-ttu-id="3308f-p105">新的 Office 365 郵件加密功能使用的保護功能，又稱為 Azure 版權管理 (Azure RMS) 從 Azure 資訊保護。這包括加密、 identity 及授權原則，以協助保護您的電子郵件。您可以使用權限管理範本、[不要轉寄] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)，並[僅加密的選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)來加密的郵件。使用者接著可以加密電子郵件訊息與 Office 365 附件各種使用這些選項。支援的附件類型的完整清單，請參閱["的檔案類型涵蓋它們是貼附至郵件的 IRM 原則 」 中的電子郵件的 IRM 的簡介](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)。身為管理員，您也可以定義要套用此保護的郵件流程規則。例如，您可以定義的規則其中的預設傳送給特定收件者或包含特定字詞的主旨行中的所有未受保護的郵件保護免於未經授權存取，而收件者無法複製或列印郵件的內容。</span><span class="sxs-lookup"><span data-stu-id="3308f-p105">The new Office 365 Message Encryption capabilities use the protection capabilities, also called Azure Rights Management (Azure RMS), from Azure Information Protection. This includes encryption, identity, and authorization policies to help secure your email. You can encrypt messages by using rights management templates, the [Do Not Forward option](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails), and the [encrypt-only option](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails). Users can then encrypt email messages and a variety of Office 365 attachments by using these options. For a full list of supported attachment types, see ["File types covered by IRM policies when they are attached to messages" in Introduction to IRM for email messages](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM). As an administrator, you can also define mail flow rules to apply this protection. For example, you can define a rule where all unprotected messages that are addressed to a specific recipient or that contain specific words in the subject line are protected from unauthorized access, and the recipients can't copy or print the contents of the message.</span></span>
  
<span data-ttu-id="3308f-p106">不同於 OME 先前的版本，這些新功能提供統一的寄件者經驗無論您在貴組織內或 Office 365 外部的收件者傳送郵件。此外，收件者收到受保護的電子郵件訊息傳送至 Outlook 2016 或在網頁上的 Outlook 中的 Office 365 帳戶不需要採取任何其他檢視郵件。順暢地運作。收件者使用其他電子郵件用戶端和電子郵件服務提供者也有體驗。資訊，請參閱[了解 Office 365 中受保護的郵件](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)及[如何開啟受保護的郵件](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)。</span><span class="sxs-lookup"><span data-stu-id="3308f-p106">Unlike the previous version of OME, these new capabilities provide a unified sender experience whether you're sending mail inside your organization or to recipients outside of Office 365. In addition, recipients who receive a protected email message sent to an Office 365 account in Outlook 2016 or Outlook on the web, don't have to take any additional action to view the message. It works seamlessly. Recipients using other email clients and email service providers also have an improved experience. For information, see [Learn about protected messages in Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) and [How do I open a protected message](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).</span></span>
  
## <a name="steps-to-manually-set-up-the-new-capabilities-for-ome"></a><span data-ttu-id="3308f-134">若要手動設定的新功能的 OME 步驟</span><span class="sxs-lookup"><span data-stu-id="3308f-134">Steps to manually set up the new capabilities for OME</span></span>

<span data-ttu-id="3308f-135">如果您的組織自動沒有 OME 啟用，或開啟關閉 OME，遵循下列步驟以手動方式設定 OME 的新功能。</span><span class="sxs-lookup"><span data-stu-id="3308f-135">If your organization does not automatically have OME enabled, or if you turned OME off, follow these steps to manually set up the new capabilities for OME.</span></span>
  
### <a name="to-manually-set-up-the-new-capabilities-for-ome"></a><span data-ttu-id="3308f-136">若要手動設定 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="3308f-136">To manually set up the new capabilities for OME</span></span>

1. <span data-ttu-id="3308f-p107">請確定您的組織有右訂閱。訂閱的詳細資訊，請參閱"何種訂閱我需要使用新的 OME capabilities?"中[Office 365 郵件加密常見問題集。](ome-faq.md)如需購買訂閱 Azure 資訊保護資訊，請參閱[Azure 資訊保護](https://azure.microsoft.com/services/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="3308f-p107">Ensure you have the right subscription for your organization. For information on subscriptions, see "What subscriptions do I need to use the new OME capabilities?" in the [Office 365 Message Encryption FAQ.](ome-faq.md) For information about purchasing a subscription to Azure Information Protection, see [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>
    
2. <span data-ttu-id="3308f-p108">決定您是否希望 Microsoft Azure 資訊保護 （預設值），管理根金鑰或產生和 （稱為將您自己的索引鍵或 BYOK） 自行管理此機碼。如果您想要產生及自行管理此機碼，您需要完成某些步驟，才可設定的新功能的 OME。如需詳細資訊，請參閱[規劃及實作您 Azure 資訊保護租用戶金鑰](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。Microsoft 建議您設定 OME 之前完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="3308f-p108">Decide whether you want Microsoft to manage the root key for Azure Information Protection (the default), or generate and manage this key yourself (known as bring your own key, or BYOK). If you want to generate and manage this key yourself, you need to complete some steps before you set up the new capabilities for OME. For more information, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key). Microsoft recommends that you complete these steps before you set up OME.</span></span>
    
3. <span data-ttu-id="3308f-p109">啟用來啟用 Azure Rights Management OME 的新功能。指示，請參閱[啟動 Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)。當您這麼做時，Office 365 自動為您啟用新 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="3308f-p109">Enable the new capabilities for OME by activating Azure Rights Management. For instructions, see [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service). When you do this, Office 365 automatically enables the new OME capabilities for you.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3308f-p110">在 Web 上的 outlook 快取其使用者介面，讓它是不錯的選項等待您嘗試將新功能的 OME 套用至使用此用戶端的電子郵件的前一天。使用者介面更新以反映新的設定之前，將不可以使用 OME 新功能。使用者介面更新之後，使用者可以使用 OME 的新功能來保護電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="3308f-p110">Outlook on the Web caches its UI, so it's a good idea to wait a day before you try applying the new capabilities for OME to email messages using this client. Before the UI updates to reflect the new configuration, the new capabilities for OME won't be available. After the UI updates, users can protect email messages by using the new capabilities for OME.</span></span> 
  
4. <span data-ttu-id="3308f-151">（選用）設定新的郵件流程規則或更新現有的郵件流程規則，以定義如何及何時您希望 Office 365 加密郵件傳送從您的組織。</span><span class="sxs-lookup"><span data-stu-id="3308f-151">(Optional) Set up new mail flow rules or update existing mail flow rules that define how and when you want Office 365 to encrypt messages sent from your organization.</span></span>
    
## <a name="verify-that-the-new-capabilities-for-ome-are-configured-properly-by-using-windows-powershell"></a><span data-ttu-id="3308f-152">確認 OME 新功能均已正確設定使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3308f-152">Verify that the new capabilities for OME are configured properly by using Windows PowerShell</span></span>

<span data-ttu-id="3308f-153">遵循下列步驟以確認您的租用戶已正確設定要用於 OME 透過 Exchange Online PowerShell 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3308f-153">Follow these steps to verify that your tenant is properly configured to use the new capabilities for OME through Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="3308f-p111">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段並連線至 Exchange Online。指示，請參閱[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="3308f-p111">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="3308f-156">執行 Test-irmconfiguration 指令程式使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="3308f-156">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>
    
    ```Test-IRMConfiguration [-Sender <email address >]```  

   <span data-ttu-id="3308f-157">例如：</span><span class="sxs-lookup"><span data-stu-id="3308f-157">For example:</span></span>
    
    ```Test-IRMConfiguration -Sender securityadmin@contoso.com```

    <span data-ttu-id="3308f-p112">其中電子郵件地址是 Office 365 組織中使用者的電子郵件地址。雖然選用、 提供寄件者電子郵件地址會強制執行其他檢查系統。</span><span class="sxs-lookup"><span data-stu-id="3308f-p112">Where email address is the email address of a user in your Office 365 organization. While optional, providing a sender email address forces the system to perform additional checks.</span></span>
    
    <span data-ttu-id="3308f-160">結果應該類似下列：</span><span class="sxs-lookup"><span data-stu-id="3308f-160">Your results should look like these:</span></span>
    
    ```
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

    <span data-ttu-id="3308f-161">其中*Contoso*被由 Office 365 組織的名稱取代。</span><span class="sxs-lookup"><span data-stu-id="3308f-161">Where  *Contoso*  is replaced with the name of your Office 365 organization.</span></span> 
    
    <span data-ttu-id="3308f-162">在結果中傳回的預設範本的名稱可能會不同顯示在上面的結果。</span><span class="sxs-lookup"><span data-stu-id="3308f-162">The names of the default templates returned in the results may be different from those displayed in the results above.</span></span>
    
    <span data-ttu-id="3308f-p113">範本和預設範本的相關資訊的簡介，請參閱[設定及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。[不要轉寄的相關資訊的選項，僅加密] 選項，及如何建立其他範本，了解權限包括或現有的範本，請參閱 ＜[設定 Azure 版權管理使用權限](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights)。</span><span class="sxs-lookup"><span data-stu-id="3308f-p113">For an introduction to templates and information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the Do Not Forward option, encrypt-only option, and how to create additional templates, or find out what rights are included in an existing template, see [Configuring usage rights for Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights).</span></span>
    
3. <span data-ttu-id="3308f-165">執行 Remove-pssession cmdlet 來中斷與版權管理服務的連線。</span><span class="sxs-lookup"><span data-stu-id="3308f-165">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>
    
    ```Remove-PSSession $session```

## <a name="next-steps-define-new-mail-flow-rules-that-use-the-new-ome-capabilities"></a><span data-ttu-id="3308f-166">後續步驟： 定義新的郵件流程規則使用的新 OME 功能</span><span class="sxs-lookup"><span data-stu-id="3308f-166">Next steps: Define new mail flow rules that use the new OME capabilities</span></span>
<span data-ttu-id="3308f-167"><a name="Rules_1"> </a></span><span class="sxs-lookup"><span data-stu-id="3308f-167"></span></span>

<span data-ttu-id="3308f-p114">這是選用的新 OME 部署步驟，不過，則已有郵件流程設定規則最多加密外寄郵件的現有 OME 部署需要此步驟。如果您想要利用新 OME 功能，您必須更新現有的郵件流程規則。否則，您的使用者會繼續接收加密的郵件而不是新的且相當順暢 OME 經驗會使用先前的 HTML 附件格式。</span><span class="sxs-lookup"><span data-stu-id="3308f-p114">This step is optional for new OME deployments, however, this step is required for existing OME deployments that already have mail flow rules set up to encrypt outgoing mail. If you want to take advantage of the new OME capabilities, you must update your existing mail flow rules. Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience.</span></span>
  
<span data-ttu-id="3308f-p115">郵件流程規則決定下何種條件電子郵件訊息應加密，以及移除該加密的條件。當您設定規則動作時，他們正在傳送時將會加密任何符合的規則條件的郵件。</span><span class="sxs-lookup"><span data-stu-id="3308f-p115">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption. When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="3308f-173">如需郵件流程規則的詳細資訊，請參閱 ＜ [Define 郵件流程規則來加密 Office 365 中的電子郵件](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="3308f-173">For more information about mail flow rules, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3308f-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="3308f-174">Related Topics</span></span>
<span data-ttu-id="3308f-175"><a name="Rules_1"> </a></span><span class="sxs-lookup"><span data-stu-id="3308f-175"></span></span>

[<span data-ttu-id="3308f-176">傳送、 檢視和回覆加密郵件在 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="3308f-176">Send, view, and reply to encrypted messages in Outlook</span></span>](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)
  
[<span data-ttu-id="3308f-177">啟用 Aadrm</span><span class="sxs-lookup"><span data-stu-id="3308f-177">Enable-Aadrm</span></span>](https://docs.microsoft.com/powershell/module/aadrm/enable-aadrm?view=azureipps)
  
[<span data-ttu-id="3308f-178">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3308f-178">Connect to Exchange Online PowerShell</span></span>](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="3308f-179">定義加密 Office 365 中的電子郵件的郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="3308f-179">Define mail flow rules to encrypt email messages in Office 365</span></span>](define-mail-flow-rules-to-encrypt-email.md)
  

