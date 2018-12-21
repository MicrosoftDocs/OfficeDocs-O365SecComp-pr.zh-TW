---
title: 設定舊版的 Office 365 郵件加密的 Azure Rights Management
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 舊版的 Office 365 郵件加密取決於 Microsoft Azure Rights Management （先前稱為 Windows Azure Active Directory Rights Management）。
ms.openlocfilehash: 994364fd74881e40f97daa3c2d12e31282b421fd
ms.sourcegitcommit: 1c00bba6ddcdd7ead6cc0153c8a2c20de05262ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/20/2018
ms.locfileid: "27382924"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="4deac-103">設定舊版的 Office 365 郵件加密的 Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="4deac-103">Set up Azure Rights Management for the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="4deac-104">本主題說明您必須遵循以啟動，然後設定 [向上 Azure 版權管理 (RMS)、 一部分 Azure 資訊保護，先前版本的 Office 365 郵件加密 (OME) 搭配使用的步驟。</span><span class="sxs-lookup"><span data-stu-id="4deac-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="4deac-105">本文僅適用於 OME 的前一版</span><span class="sxs-lookup"><span data-stu-id="4deac-105">This article only applies to the previous version of OME</span></span>
<span data-ttu-id="4deac-p101">如果您尚未尚未移動 Office 365 組織到新的 OME 功能，但您已部署 OME，本文資訊適用於您組織。Microsoft 建議您將移至新的 OME 功能一旦是組織的合理的計劃。指示，請參閱[Set up Office 365 郵件加密的新功能](set-up-new-message-encryption-capabilities.md)。如果您想要了解更多有關的新功能如何運作前，請參閱[Office 365 郵件加密](ome.md)。本文的其餘部分是指 OME 行為的新 OME 功能發行前。</span><span class="sxs-lookup"><span data-stu-id="4deac-p101">If you haven't yet moved your Office 365 organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization. Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md). If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md). The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="4deac-111">使用舊版的 Office 365 郵件加密的必要條件</span><span class="sxs-lookup"><span data-stu-id="4deac-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="4deac-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="4deac-112"></span></span>

<span data-ttu-id="4deac-p102">Office 365 郵件加密 (OME)，包括 IRM，取決於 Azure 版權管理 (Azure RMS)。Azure RMS 是 Azure 資訊保護所用的保護技術。若要使用 OME，Office 365 組織必須包含 Exchange Online 或 Exchange Online Protection，接著，包含訂閱 Azure 版權管理訂閱。</span><span class="sxs-lookup"><span data-stu-id="4deac-p102">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS). Azure RMS is the protection technology used by Azure Information Protection. To use OME, your Office 365 organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="4deac-116">如果您不確定您的訂閱所包含的內容，請參閱[訊息原則、 復原及規範](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)的 Exchange Online 服務說明。</span><span class="sxs-lookup"><span data-stu-id="4deac-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span></span>

- <span data-ttu-id="4deac-117">如果您沒有 Azure RMS 訂閱的 Exchange Online 或 Exchange Online Protection，您必須購買訂閱和先加以啟動。</span><span class="sxs-lookup"><span data-stu-id="4deac-117">If you don't have an Azure RMS subscription for Exchange Online or Exchange Online Protection, you must purchase a subscription and activate it first.</span></span>

    <span data-ttu-id="4deac-p103">如需購買 Azure 版權管理訂閱，請參閱[Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT)。下一步] 區段可讓您啟動 Azure 版權管理的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4deac-p103">For information about purchasing a subscription to Azure Rights Management, see [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). The next section gives you information about activating Azure Rights Management.</span></span>

- <span data-ttu-id="4deac-120">如果您有 Azure Rights Management，但它未設定 Exchange Online 或 Exchange Online Protection，本文說明如何啟動 Azure Rights Management 並加上 then 說明 OME 設為使用 Azure 版權管理的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="4deac-120">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="4deac-p104">如果您已經設定 OME 使用 Azure 版權管理 Exchange Online 或 Exchange Online Protection，根據您如何設定它，您可能即可開始使用 OME 及新功能，其立即。本文說明如何決定是否您已設定 OME 正確，如果您需要變更您的安裝程式，該怎麼辦以及如果您選擇不要變更您的安裝程式會發生什麼事。例如，才可使用的新功能，您必須使用 Azure RMS 與 OME。您不能搭配內部部署 Active Directory RMS 的新功能。</span><span class="sxs-lookup"><span data-stu-id="4deac-p104">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away. This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup. For example, in order to use the new capabilities, you must use Azure RMS with OME. You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="4deac-125">啟動先前版本的 Office 365 中的 OME Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="4deac-125">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="4deac-p105">您必須啟用 Azure 版權管理組織中的使用者可以將資訊保護套用到傳送時的訊息和開啟郵件與具備已受到 Azure 版權管理服務的檔案。指示，請參閱[啟動 Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775)。一旦您已經完成啟用，此處傳回並繼續執行本文中的工作。</span><span class="sxs-lookup"><span data-stu-id="4deac-p105">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service. For instructions, see [Activating Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="4deac-129">設定 OME 的前一版使用 Azure RMS 匯入信任的發行網域 (TPDs)</span><span class="sxs-lookup"><span data-stu-id="4deac-129">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="4deac-p106">TPD 是 XML 檔案包含您的組織版權管理設定的相關資訊。例如，TPD 包含用於簽署和加密憑證和授權的伺服器授權人憑證 (SLC) 的相關資訊、 Url 用於授權和發佈、 等等。使用 Windows PowerShell TPD 匯 Office 365 組織中。</span><span class="sxs-lookup"><span data-stu-id="4deac-p106">A TPD is an XML file that contains information about your organization's rights management settings. For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on. You import the TPD into your Office 365 organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4deac-p107">之前，您可以選擇從 Active Directory Rights Management service (AD RMS) TPDs 匯入至您的 Office 365 組織。不過，這麼會防止使用新的 OME 功能並不建議使用。如果您的組織是目前的 Office 365 設定如此一來，Microsoft 建議您建立從您的內部部署 Active Directory RMS 移轉至雲端式 Azure 資訊保護計劃。如需詳細資訊，請參閱 ＜ [Migrating from AD RMS 以 Azure 資訊保護](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。您無法使用新的 OME 功能直到您完成移轉至 Azure 資訊保護。</span><span class="sxs-lookup"><span data-stu-id="4deac-p107">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your Office 365 organization. However, doing so will prevent you from using the new OME capabilities and is not recommended. If your Office 365 organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection. For more information, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="4deac-138">**若要從 Azure RMS 匯入 TPDs**</span><span class="sxs-lookup"><span data-stu-id="4deac-138">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="4deac-139">[連線至 Exchange Online 使用遠端 PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4deac-139">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="4deac-140">選擇金鑰共用 URL 對應至 Office 365 組織的地理位置：</span><span class="sxs-lookup"><span data-stu-id="4deac-140">Choose the key-sharing URL that corresponds to your Office 365 organization's geographic location:</span></span>

|<span data-ttu-id="4deac-141">**位置**</span><span class="sxs-lookup"><span data-stu-id="4deac-141">**Location**</span></span>|<span data-ttu-id="4deac-142">**金鑰共用位置 URL**</span><span class="sxs-lookup"><span data-stu-id="4deac-142">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4deac-143">北美</span><span class="sxs-lookup"><span data-stu-id="4deac-143">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="4deac-144">歐盟</span><span class="sxs-lookup"><span data-stu-id="4deac-144">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="4deac-145">亞洲</span><span class="sxs-lookup"><span data-stu-id="4deac-145">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="4deac-146">南美洲</span><span class="sxs-lookup"><span data-stu-id="4deac-146">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="4deac-147">Office 365 for Government (政府社群雲端)</span><span class="sxs-lookup"><span data-stu-id="4deac-147">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="4deac-148">此 RMS 金鑰共用位置保留供已購買 Office 365 for Government Sku 的客戶。</span><span class="sxs-lookup"><span data-stu-id="4deac-148">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. <span data-ttu-id="4deac-149">設定金鑰共用位置執行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx)指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4deac-149">Configure the key-sharing location by running the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet as follows:</span></span> 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    <span data-ttu-id="4deac-150">例如，若要設定金鑰共用位置若您的組織位於 「 北美地區 」：</span><span class="sxs-lookup"><span data-stu-id="4deac-150">For example, to configure the key sharing location if your organization is located in North America:</span></span>
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. <span data-ttu-id="4deac-151">使用 Azure Rights Management 從匯入 TPD-RMSOnline 參數執行[Import-rmstrustedpublishingdomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx)指令程式：</span><span class="sxs-lookup"><span data-stu-id="4deac-151">Run the [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    <span data-ttu-id="4deac-p108">您想要用於 TPD *TPDName*所在的名稱。例如，"Contoso 北美地區 TPD"。</span><span class="sxs-lookup"><span data-stu-id="4deac-p108">Where  *TPDName*  is the name you want to use for the TPD. For example, "Contoso North American TPD".</span></span> 
    
5. <span data-ttu-id="4deac-154">若要確認您已順利設定 Office 365 組織使用 Azure 版權管理服務，執行[Test-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx)指令程式搭配-RMSOnline 參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4deac-154">To verify that you successfully configured your Office 365 organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet with the -RMSOnline switch as follows:</span></span> 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    <span data-ttu-id="4deac-155">除此之外，此指令程式會檢查使用 Azure Rights Management service 的連線、 下載 TPD，並檢查其有效性。</span><span class="sxs-lookup"><span data-stu-id="4deac-155">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>
    
6. <span data-ttu-id="4deac-156">執行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)指令程式，如下所示停用來在網頁伺服器和 Outlook 在 Outlook 中可用的 Azure Rights Management 範本：</span><span class="sxs-lookup"><span data-stu-id="4deac-156">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. <span data-ttu-id="4deac-157">執行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)指令程式，如下所示的雲端架構電子郵件組織啟用 Azure Rights Management 並將它設定成使用 Office 365 郵件加密的 Azure Rights Management：</span><span class="sxs-lookup"><span data-stu-id="4deac-157">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span> 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. <span data-ttu-id="4deac-p109">若要確認您已成功匯入 TPD 並啟用 Azure Rights Management，請使用 Test-irmconfiguration 指令程式來測試 Azure 版權管理功能。如需詳細資訊，請參閱[Test-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)中的 「 範例 1"。</span><span class="sxs-lookup"><span data-stu-id="4deac-p109">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality. For details, see "Example 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span></span>
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="4deac-160">我必須設定與 Active Directory Rights Management 未 Azure 資訊保護 OME 的前一版，該怎麼辦吗？</span><span class="sxs-lookup"><span data-stu-id="4deac-160">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="4deac-161"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="4deac-161"></span></span>

<span data-ttu-id="4deac-p110">您可以繼續使用現有的 Office 365 郵件加密郵件流程規則具有 Active Directory Rights Management，但您無法設定或使用新的 OME 功能。而您需要移轉至 Azure 資訊保護。如需移轉與這表示您的組織資訊，請參閱 ＜ [Migrating from AD RMS 以 Azure 資訊保護](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)。</span><span class="sxs-lookup"><span data-stu-id="4deac-p110">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities. Instead, you need to migrate to Azure Information Protection. For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="4deac-165">後續步驟</span><span class="sxs-lookup"><span data-stu-id="4deac-165">Next steps</span></span>
<span data-ttu-id="4deac-166"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="4deac-166"></span></span>

<span data-ttu-id="4deac-167">如果您想要啟用新的 OME 功能，請參閱完成 Azure 版權管理安裝後[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護之上。](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span><span class="sxs-lookup"><span data-stu-id="4deac-167">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span></span>
  
<span data-ttu-id="4deac-168">您已設定您的組織使用的新 OME 功能之後，您準備好[定義郵件流程規則來保護電子郵件訊息與 OME 的新功能](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="4deac-168">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4deac-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="4deac-169">Related topics</span></span>
<span data-ttu-id="4deac-170"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="4deac-170"></span></span>

[<span data-ttu-id="4deac-171">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="4deac-171">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="4deac-172">關於 Office 365 中加密的技術參考細節</span><span class="sxs-lookup"><span data-stu-id="4deac-172">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="4deac-173">Azure 版權管理新功能</span><span class="sxs-lookup"><span data-stu-id="4deac-173">What is Azure Rights Management?</span></span>](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  

