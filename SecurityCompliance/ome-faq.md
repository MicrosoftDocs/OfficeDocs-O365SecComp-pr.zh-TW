---
title: Office 365 郵件加密常見問題集
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/11/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: 已在 Office 365 中的新郵件保護功能的運作方式的相關問題嗎？檢查的答案。
ms.openlocfilehash: 651d3f5953f0a6864259ed3a0c8ecde79f40d631
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217113"
---
# <a name="office-365-message-encryption-faq"></a><span data-ttu-id="9b12e-104">Office 365 郵件加密常見問題集</span><span class="sxs-lookup"><span data-stu-id="9b12e-104">Office 365 Message Encryption FAQ</span></span>

<span data-ttu-id="9b12e-p102">已在 Office 365 中的新郵件保護功能的運作方式的相關問題嗎？檢查的答案。此外，仔細[常見問題集關於 Azure 資訊保護中的資料保護](https://docs.microsoft.com/information-protection/get-started/faqs-rms)的資料保護服務、 Azure 版權管理] 的相關問題的答案在 Azure 資訊保護。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p102">Have a question about how the new message protection capabilities in Office 365 work? Check for an answer here. Also, take a look at [Frequently asked questions about data protection in Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/faqs-rms) for answers to questions about the data protection service, Azure Rights Management, in Azure Information Protection.</span></span>

||
|:-----|
|<span data-ttu-id="9b12e-p103">本文屬於較大的一系列有關 Office 365 郵件加密的文章。本文適用於系統管理員和 ITPros 的。如果您只尋找的資訊在傳送或接收加密的郵件，請參閱[Office 365 郵件加密 (OME)](ome.md)中的文章的清單並找出最適合您需求的文章。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||
  
## <a name="what-is-office-365-message-encryption-ome"></a><span data-ttu-id="9b12e-111">什麼是 Office 365 郵件加密 (OME)？</span><span class="sxs-lookup"><span data-stu-id="9b12e-111">What is Office 365 Message Encryption (OME)?</span></span>

<span data-ttu-id="9b12e-p104">OME 合併電子郵件加密和權限管理功能。版權管理功能是由 Azure 資訊保護提供。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p104">OME combines email encryption and rights management capabilities. Rights management capabilities are powered by Azure Information Protection.</span></span>
  
## <a name="who-can-use-ome"></a><span data-ttu-id="9b12e-114">誰可以使用 OME？</span><span class="sxs-lookup"><span data-stu-id="9b12e-114">Who can use OME?</span></span>

<span data-ttu-id="9b12e-115">您可以在下列情況下使用 OME 的新功能：</span><span class="sxs-lookup"><span data-stu-id="9b12e-115">You can use the new capabilities for OME under the following conditions:</span></span>
  
- <span data-ttu-id="9b12e-116">如果您有永不 set up OME 或 IRM for Office 365 中的 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9b12e-116">If you have never set up OME or IRM for Exchange Online in Office 365.</span></span>
    
- <span data-ttu-id="9b12e-117">如果您已設定好 OME 和 IRM，您可以使用下列步驟，如果您使用 Azure 資訊保護 Azure 版權管理服務。</span><span class="sxs-lookup"><span data-stu-id="9b12e-117">If you have set up OME and IRM, you can use these steps if you are using the Azure Rights Management service from Azure Information Protection.</span></span>
    
- <span data-ttu-id="9b12e-p105">如果您使用 Exchange Online 與 Active Directory Rights Management service (AD RMS)，就無法立即啟用這些新功能。而您需要[移轉至 Azure 資訊保護 AD RMS](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)第一次。當您已經完成移轉時，您可以成功設定 OME。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p105">If you are using Exchange Online with Active Directory Rights Management service (AD RMS), you can't enable these new capabilities right away. Instead, you need to [migrate AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) first. When you've finished the migration, you can successfully set up OME.</span></span> 
    
    <span data-ttu-id="9b12e-121">如果您選擇繼續使用內部部署 AD RMS 與 Exchange Online 而不是移轉至 Azure 資訊保護，您將無法使用這些新功能。</span><span class="sxs-lookup"><span data-stu-id="9b12e-121">If you choose to continue to use on-premises AD RMS with Exchange Online instead of migrating to Azure Information Protection, you will not be able to use these new capabilities.</span></span>
    
## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a><span data-ttu-id="9b12e-122">我需要何種訂閱使用新的 OME 功能？</span><span class="sxs-lookup"><span data-stu-id="9b12e-122">What subscriptions do I need to use the new OME capabilities?</span></span>

<span data-ttu-id="9b12e-123">若要使用的新 OME 功能，您需要下列計劃其中一項：</span><span class="sxs-lookup"><span data-stu-id="9b12e-123">To use the new OME capabilities, you need one of the following plans:</span></span>
  
- <span data-ttu-id="9b12e-p106">Office 365 郵件加密被提供 Office 365 企業版 E3 和 E5、 Microsoft 企業 E3 和 E5、 Microsoft 365 Business、 Office 365 A1、 A3 和 A5、 與 Office 365 政府 G3 及 G5 的一部分。客戶不需要以接收新的保護功能由 Azure 資訊保護提供額外的授權。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p106">Office 365 Message Encryption is offered as part of Office 365 Enterprise E3 and E5, Microsoft Enterprise E3 and E5, Microsoft 365 Business, Office 365 A1, A3, and A5, and Office 365 Government G3 and G5. Customers do not need additional licenses to receive the new protection capabilities powered by Azure Information Protection.</span></span> 
    
- <span data-ttu-id="9b12e-126">您也可以新增 Azure 資訊保護計劃 1 的下列計劃以接收新的 Office 365 郵件加密功能： Exchange Online 計劃 1、 Exchange Online 計劃 2、 Office 365 F1、 Office 365 商務 Essentials、 Office 365 企業進階版或Office 365 企業版 E1。</span><span class="sxs-lookup"><span data-stu-id="9b12e-126">You can also add Azure Information Protection Plan 1 to the following plans to receive the new Office 365 Message Encryption capabilities: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Office 365 Business Essentials, Office 365 Business Premium, or Office 365 Enterprise E1.</span></span>
    
- <span data-ttu-id="9b12e-127">從 Office 365 郵件加密而且可以享有每位使用者必須被授權功能所涵蓋。</span><span class="sxs-lookup"><span data-stu-id="9b12e-127">Each user benefiting from Office 365 Message Encryption needs to be licensed to be covered by the feature.</span></span>
    
- <span data-ttu-id="9b12e-128">完整清單請參閱[Exchange Online 服務說明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)Office 365 郵件加密。</span><span class="sxs-lookup"><span data-stu-id="9b12e-128">For the full list see the [Exchange Online service descriptions](https://technet.microsoft.com/library/exchange-online-service-description.aspx) for Office 365 Message Encryption.</span></span> 
    
## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a><span data-ttu-id="9b12e-129">我可以使用 Exchange Online 與整合 Azure 資訊保護您自己的金鑰 (BYOK) 吗？</span><span class="sxs-lookup"><span data-stu-id="9b12e-129">Can I use Exchange Online with bring your own key (BYOK) in Azure Information Protection?</span></span>

<span data-ttu-id="9b12e-p107">是 ！Microsoft 建議您完成之前設定 OME BYOK 設定步驟。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p107">Yes! Microsoft recommends that you complete the steps to set up BYOK before you set up OME.</span></span>
  
<span data-ttu-id="9b12e-132">如需 BYOK 的詳細資訊，請參閱[規劃及實作您 Azure 資訊保護租用戶金鑰](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="9b12e-132">For more information about BYOK, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).</span></span>
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a><span data-ttu-id="9b12e-133">不要 OME 和 Azure 資訊保護 BYOK 變更 Microsoft 的方法如 subpoenas 協力廠商資料要求吗？</span><span class="sxs-lookup"><span data-stu-id="9b12e-133">Do OME and BYOK with Azure Information Protection change Microsoft's approach to third-party data requests such as subpoenas?</span></span>

<span data-ttu-id="9b12e-p108">[否]。OME 和選項提供並控制您自己的加密金鑰，從 Azure 資訊保護呼叫 BYOK，不是以回應 law 強制執行 subpoenas 而設計。OME，與 BYOK Azure 資訊保護，旨在規範為主的客戶。Microsoft 非常嚴重採用客戶資料的第三方的要求。做為雲端服務提供者，我們一律主張的客戶資料的隱私。我們要取得傳票、 可行我們永遠嘗試將第三方重新導向至客戶資訊。(請參閱此 Smith 的部落格： [＜ Protecting 政府側錄的客戶資料](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。我們會定期發行我們會收到的要求的詳細的資訊。如需有關協力廠商資料要求，請參閱 Microsoft 信任中心上的[政府及存取客戶資料 law 強制執行要求的回應](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data)。請參閱 「 洩漏的客戶資料 」 在[線上服務合約 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p108">No. OME and the option to provide and control your own encryption keys, called BYOK, from Azure Information Protection were not designed to respond to law enforcement subpoenas. OME, with BYOK for Azure Information Protection, was designed for compliance-focused customers. Microsoft takes third-party requests for customer data very seriously. As a cloud service provider, we always advocate for the privacy of customer data. In the event we get a subpoena, we always attempt to redirect the third party to the customer to obtain the information. (Please read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). We periodically publish detailed information of the request we receive. For more information regarding third-party data requests, see [Responding to government and law enforcement requests to access customer data](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data) on the Microsoft Trust Center. Also, see "Disclosure of Customer Data" in the [Online Services Terms (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx).</span></span>
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a><span data-ttu-id="9b12e-144">這項功能如何與舊版的 Office 365 郵件加密 (OME) 」 和 「 資訊版權管理 (IRM) 功能？</span><span class="sxs-lookup"><span data-stu-id="9b12e-144">How is this feature related to legacy Office 365 Message Encryption (OME) and Information Rights Management (IRM) features?</span></span>

<span data-ttu-id="9b12e-p109">Office 365 郵件加密的新功能的現有 IRM 和舊版 OME 解決方案的發展。下表提供更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p109">The new capabilities for Office 365 Message Encryption are an evolution of the existing IRM and legacy OME solutions. The following table provides more details.</span></span>
  
<span data-ttu-id="9b12e-147">**舊版 OME、 IRM、 與 OME 的新功能的比較**</span><span class="sxs-lookup"><span data-stu-id="9b12e-147">**Comparison of legacy OME, IRM, and new OME capabilities**</span></span>

|<span data-ttu-id="9b12e-148">**功能**</span><span class="sxs-lookup"><span data-stu-id="9b12e-148">**Capability**</span></span>|<span data-ttu-id="9b12e-149">**舊版的 OME**</span><span class="sxs-lookup"><span data-stu-id="9b12e-149">**Previous versions of OME**</span></span>|<span data-ttu-id="9b12e-150">**IRM**</span><span class="sxs-lookup"><span data-stu-id="9b12e-150">**IRM**</span></span>|<span data-ttu-id="9b12e-151">**OME 的新功能**</span><span class="sxs-lookup"><span data-stu-id="9b12e-151">**New OME capabilities**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9b12e-152">**傳送加密的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="9b12e-152">**Sending an encrypted email**</span></span>|<span data-ttu-id="9b12e-153">只能透過 Exchange 郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="9b12e-153">Only through Exchange mail flow rules</span></span>|<span data-ttu-id="9b12e-154">從 Outlook PC、 Outlook for Mac，或 Outlook web; 上的起始的使用者或透過 Exchange 郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="9b12e-154">End-user initiated from Outlook for PC, Outlook for Mac, or Outlook on the web; or through Exchange mail flow rules</span></span>|<span data-ttu-id="9b12e-155">從 Outlook PC、 Outlook for Mac，或 Outlook web; 上的起始的使用者或透過郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="9b12e-155">End-user initiated from Outlook for PC, Outlook for Mac, or Outlook on the web; or through mail flow rules</span></span>|
|<span data-ttu-id="9b12e-156">**版權管理**</span><span class="sxs-lookup"><span data-stu-id="9b12e-156">**Rights management**</span></span>|-|<span data-ttu-id="9b12e-157">不要轉寄選項和自訂範本</span><span class="sxs-lookup"><span data-stu-id="9b12e-157">Do Not Forward option and custom templates</span></span>|<span data-ttu-id="9b12e-158">不要轉寄] 選項、 僅加密的選項、 預設和自訂範本</span><span class="sxs-lookup"><span data-stu-id="9b12e-158">Do Not Forward option, encrypt-only option, default and custom templates</span></span>|
|<span data-ttu-id="9b12e-159">**支援的收件者類型**</span><span class="sxs-lookup"><span data-stu-id="9b12e-159">**Supported recipient type**</span></span>|<span data-ttu-id="9b12e-160">僅外部收件者</span><span class="sxs-lookup"><span data-stu-id="9b12e-160">External recipients only</span></span>|<span data-ttu-id="9b12e-161">僅限內部收件者</span><span class="sxs-lookup"><span data-stu-id="9b12e-161">Internal recipients only</span></span>|<span data-ttu-id="9b12e-162">內部和外部收件者</span><span class="sxs-lookup"><span data-stu-id="9b12e-162">Internal and external recipients</span></span>|
|<span data-ttu-id="9b12e-163">**收件者經驗**</span><span class="sxs-lookup"><span data-stu-id="9b12e-163">**Experience for recipient**</span></span>|<span data-ttu-id="9b12e-164">外部收件者接收到的 HTML 郵件他們下載和瀏覽器中開啟或下載行動裝置應用程式。</span><span class="sxs-lookup"><span data-stu-id="9b12e-164">External recipients received an HTML message that they downloaded and opened in a browser or downloaded mobile app.</span></span>|<span data-ttu-id="9b12e-165">內部收件者只在收到的 PC Outlook、 Outlook for Mac 及 web 上的 Outlook 中加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9b12e-165">Internal recipients only received encrypted email in Outlook for PC, Outlook for Mac, and Outlook on the web.</span></span>|<span data-ttu-id="9b12e-p110">內部和外部收件者電子郵件中接收的 PC Outlook、 Outlook for Mac、 網路上的 Outlook、 Outlook for android （英文)、 和 Outlook iOS，或透過入口網站，不論都在相同的 Office 365 組織或任何 Office 365組織。OME 入口網站需要沒有個別下載。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p110">Internal and external recipients receive email in Outlook for PC, Outlook for Mac, Outlook on the web, Outlook for Android, and Outlook for iOS, or through a web portal, regardless of whether or not they are in the same Office 365 organization or in any Office 365 organization. The OME portal requires no separate download.</span></span>|
|<span data-ttu-id="9b12e-168">**將您自己的金鑰支援**</span><span class="sxs-lookup"><span data-stu-id="9b12e-168">**Bring Your Own Key support**</span></span>|<span data-ttu-id="9b12e-169">無法使用</span><span class="sxs-lookup"><span data-stu-id="9b12e-169">Not available</span></span>|<span data-ttu-id="9b12e-170">無法使用</span><span class="sxs-lookup"><span data-stu-id="9b12e-170">Not available</span></span>| <span data-ttu-id="9b12e-171">BYOK 支援</span><span class="sxs-lookup"><span data-stu-id="9b12e-171">BYOK supported</span></span>|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a><span data-ttu-id="9b12e-172">如何在 「 我的組織啟用新 OME 功能？</span><span class="sxs-lookup"><span data-stu-id="9b12e-172">How do I enable the new OME capabilities for my organization?</span></span>

<span data-ttu-id="9b12e-173">請參閱 ＜ [Set up Office 365 郵件加密的新功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="9b12e-173">See [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a><span data-ttu-id="9b12e-174">將會過時 OME 的舊版本吗？</span><span class="sxs-lookup"><span data-stu-id="9b12e-174">Will the previous version of OME be deprecated?</span></span>

<span data-ttu-id="9b12e-p111">您仍然可以使用舊版 OME，它不會在此階段過時。不過，我們強烈鼓勵使用新增及改良的 OME 解決方案的組織。您尚未部署 OME 的客戶無法設定 OME 的前一版的新部署。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p111">You can still use the previous version of OME, it will not be deprecated at this time. However, we highly encourage organizations to use the new and improved OME solution. Customers that have not already deployed OME cannot set up a new deployment of the previous version of OME.</span></span>
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a><span data-ttu-id="9b12e-178">「 我的組織使用 Active Directory Rights Management，可以使用這項功能嗎？</span><span class="sxs-lookup"><span data-stu-id="9b12e-178">My organization uses Active Directory Rights Management, can I use this functionality?</span></span>

<span data-ttu-id="9b12e-p112">[否]。如果您使用 Exchange Online 與 Active Directory Rights Management service (AD RMS)，就無法立即啟用這些新功能。而您需要[移轉至 Azure 資訊保護 AD RMS](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)第一次。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p112">No. If you are using Exchange Online with Active Directory Rights Management service (AD RMS), you can't enable these new capabilities right away. Instead, you need to [migrate AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) first.</span></span> 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a><span data-ttu-id="9b12e-p113">我的組織具有 Exchange 混合部署。可以使用這項功能吗？</span><span class="sxs-lookup"><span data-stu-id="9b12e-p113">My organization has an Exchange Hybrid deployment. Can I use this feature?</span></span>

<span data-ttu-id="9b12e-p114">內部使用者可以傳送加密的郵件使用 Exchange Online 郵件流程規則。為達成此目的，您需要透過 Exchange Online 電子郵件路由。如需詳細資訊，請參閱[第 2 部分： 設定郵件流程電子郵件伺服器的 Office 365 以](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p114">On-premises users can send encrypted mail using Exchange Online mail flow rules. In order to do this, you need to route email through Exchange Online. For more information, see [Part 2: Configure mail to flow from your email server to Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).</span></span>
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a><span data-ttu-id="9b12e-p115">我需要哪些電子郵件用戶端使用，以建立 OME 加密的郵件？支援哪些應用程式傳送受保護的郵件？</span><span class="sxs-lookup"><span data-stu-id="9b12e-p115">What email client do I need to use in order to create an OME encrypted message? What applications are supported for sending protected messages?</span></span>

<span data-ttu-id="9b12e-189">您可以在從 Outlook 2016 和 Outlook 2013 的 PC 或 Mac，然後從 Outlook web 上建立受保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="9b12e-189">You can create protected messages from Outlook 2016, and Outlook 2013 for PC and Mac, and from Outlook on the web.</span></span>
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a><span data-ttu-id="9b12e-190">讀取和對受保護的電子郵件回覆支援何種電子郵件用戶端？</span><span class="sxs-lookup"><span data-stu-id="9b12e-190">What email clients are supported to read and reply to protected emails?</span></span>

<span data-ttu-id="9b12e-p116">您可以閱讀和回應從 Outlook PC 和 Mac （2013年和 2016年）、 在 web 上的 Outlook 和 Outlook 行動裝置 （Android 和 iOS） 如果您是 Office 365 使用者。您也可以使用 iOS 原生的郵件用戶端如果貴組織可讓它。如果您是非 Office 365 使用者，您可以閱讀和回覆加密郵件在 web 上透過網頁瀏覽器中。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p116">You can read and respond from Outlook for PC and Mac (2013 and 2016), Outlook on the web, and Outlook mobile (Android and iOS) if you are an Office 365 user. You can also use the iOS native mail client if your organization allows it. If you are a non-Office 365 user, you can read and reply to encrypted messages on the web through your web browser.</span></span>
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a><span data-ttu-id="9b12e-p117">做為受保護的電子郵件中的附件支援何種檔案類型？不要附件繼承受保護的電子郵件相關聯的保護原則吗？</span><span class="sxs-lookup"><span data-stu-id="9b12e-p117">What file types are supported as attachments in protected emails? Do attachments inherit the protection policies associated with protected emails?</span></span>

<span data-ttu-id="9b12e-196">不過，保護原則會套用只在檔案格式提及之[以下](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)可以受保護的郵件，附加任何檔案類型。</span><span class="sxs-lookup"><span data-stu-id="9b12e-196">You can attach any file type to a protected mail, however protection policies are applied only on the file formats mentioned [here](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types).</span></span> 
  
<span data-ttu-id="9b12e-p118">如果支援的檔案格式，例如 Word、 Excel、 或 PowerPoint 檔案檔案會永遠受到保護，即使收件者已下載附件。例如如果附件受到保護的 [不要轉寄、 和原始收件者下載並將新的收件者的附件轉寄、 新的收件者將無法開啟受保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p118">If a file format is supported, such as a Word, Excel, or PowerPoint file, the file is always protected, even after the attachment has been downloaded by the recipient. For example, if an attachment is protected by Do Not Forward, and the original recipient downloads and forwards the attachment to a new recipient, the new recipient will not be able to open the protected file.</span></span>
  
## <a name="are-pdf-file-attachments-supported"></a><span data-ttu-id="9b12e-199">所支援的 PDF 檔案附件</span><span class="sxs-lookup"><span data-stu-id="9b12e-199">Are PDF file attachments supported?</span></span>

<span data-ttu-id="9b12e-p119">如果您以受保護的郵件附加的 PDF 檔案本身的郵件將會受到保護，但沒有其他保護會套用至 PDF 檔案後收件者已收到它。這表示的收件者可以另存新檔、 轉接、 複製及列印的 PDF 檔案。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p119">If you attach a PDF file to a protected message, the message itself will be protected, but no additional protection will be applied to the PDF file after the recipient has received it. This means that the recipient can Save As, Forward, Copy, and Print the PDF file.</span></span>
  
## <a name="are-onedrive-for-business-attachments-supported"></a><span data-ttu-id="9b12e-202">支援的商務附件是否 OneDrive 吗？</span><span class="sxs-lookup"><span data-stu-id="9b12e-202">Are OneDrive for Business attachments supported?</span></span>

<span data-ttu-id="9b12e-p120">尚未。OneDrive for Business 附件不受支援與使用者無法加密雲端 OneDrive for Business 附件的郵件。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p120">Not yet. OneDrive for Business attachments are not supported and end-users can't encrypt a mail that contains a cloud OneDrive for Business attachment.</span></span>
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a><span data-ttu-id="9b12e-205">可以藉由設定原則會自動加密郵件吗？</span><span class="sxs-lookup"><span data-stu-id="9b12e-205">Can I automatically encrypt messages by setting up policies?</span></span>

<span data-ttu-id="9b12e-p121">[是]。郵件流程規則在 Exchange Online 使用自動加密根據特定條件的郵件。例如，您可以建立原則為基礎的收件者的識別碼，收件者的網域，或在本文或主旨郵件的內容。請參閱[定義加密 Office 365 中的電子郵件的郵件流程規則。](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="9b12e-p121">Yes. Use mail flow rules in Exchange Online to automatically encrypt a message based on certain conditions. For example, you can create policies that are based on recipient ID, recipient domain, or on the content in the body or subject of the message. See [Define mail flow rules to encrypt email messages in Office 365.](define-mail-flow-rules-to-encrypt-email.md)</span></span>
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a><span data-ttu-id="9b12e-210">可以使用自動加密郵件所設定的原則中的資料遺失防護 (DLP) 透過安全性&amp;規範中心吗？</span><span class="sxs-lookup"><span data-stu-id="9b12e-210">Can I automatically encrypt messages by setting up policies in Data Loss Prevention (DLP) through the Security &amp; Compliance Center?</span></span>

<span data-ttu-id="9b12e-p122">是 ！您可以設定郵件流程規則 in Exchange Online 或使用 DLP 安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p122">Yes! You can set up mail flow rules in Exchange Online or by using DLP in the Security &amp; Compliance Center.</span></span>
  
## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a><span data-ttu-id="9b12e-213">可開啟加密的郵件傳送至共用信箱吗？</span><span class="sxs-lookup"><span data-stu-id="9b12e-213">Can I open encrypted messages sent to a Shared Mailbox?</span></span>

<span data-ttu-id="9b12e-214">共用信箱不支援目前加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="9b12e-214">Currently encrypted messages are not supported for a Shared Mailbox.</span></span>

## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a><span data-ttu-id="9b12e-215">可自訂加密的郵件具有我的公司品牌吗？</span><span class="sxs-lookup"><span data-stu-id="9b12e-215">Can I customize encrypted messages with my company branding?</span></span>

<span data-ttu-id="9b12e-p123">是 ！如需自訂電子郵件及 OME 入口網站，請參閱 ＜ 將您的組織的商標新增至加密的郵件。請參閱[將您的組織的商標新增至加密的郵件。](add-your-organization-brand-to-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="9b12e-p123">Yes! For information on customizing email messages and the OME portal, see Add your organization's brand to your encrypted messages. See [Add your organization's brand to your encrypted messages.](add-your-organization-brand-to-encrypted-messages.md)</span></span>
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a><span data-ttu-id="9b12e-219">是否有任何報表功能或前瞻加密的電子郵件吗？</span><span class="sxs-lookup"><span data-stu-id="9b12e-219">Are there any reporting capabilities or insights for encrypted emails?</span></span>

<span data-ttu-id="9b12e-220">不在此時間但即將推出。</span><span class="sxs-lookup"><span data-stu-id="9b12e-220">Not at this time but coming soon.</span></span>
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a><span data-ttu-id="9b12e-221">可以使用郵件加密與符合性功能，例如 eDiscovery 吗？</span><span class="sxs-lookup"><span data-stu-id="9b12e-221">Can I use message encryption with compliance features such as eDiscovery?</span></span>

<span data-ttu-id="9b12e-p124">[是]。所有加密的電子郵件訊息是由 Office 365 的符合性功能可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="9b12e-p124">Yes. All encrypted email messages are discoverable by Office 365 compliance features.</span></span>
  

