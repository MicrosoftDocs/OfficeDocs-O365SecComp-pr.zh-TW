---
title: 設定舊版 Office 365 郵件加密的 Azure 版權管理
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 舊版的 Office 365 郵件加密取決於 Microsoft Azure 版權管理 （先前稱為 Windows Azure Active Directory Rights Management）。
ms.openlocfilehash: 84922a57c6245cf3214f17ba922417b5e025b796
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158495"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="20f63-103">設定舊版 Office 365 郵件加密的 Azure 版權管理</span><span class="sxs-lookup"><span data-stu-id="20f63-103">Set up Azure Rights Management for the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="20f63-104">本主題說明您所須才能啟動並再將設定備份 Azure 版權管理 (RMS)，與舊版 Office 365 郵件加密 (OME) 搭配使用的組件的 Azure 資訊保護，請依照下列步驟。</span><span class="sxs-lookup"><span data-stu-id="20f63-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="20f63-105">本文僅適用於舊版 OME</span><span class="sxs-lookup"><span data-stu-id="20f63-105">This article only applies to the previous version of OME</span></span>
<span data-ttu-id="20f63-106">如果您尚未尚未將您的 Office 365 組織移動到全新的 OME 功能，但您已部署 OME，本文資訊適用於您的組織。</span><span class="sxs-lookup"><span data-stu-id="20f63-106">If you haven't yet moved your Office 365 organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="20f63-107">Microsoft 建議您先將移至全新的 OME 功能，只要是合理的貴組織的計劃。</span><span class="sxs-lookup"><span data-stu-id="20f63-107">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="20f63-108">如需相關指示，請參閱 <<c0>設定新的 Office 365 郵件加密功能。</span><span class="sxs-lookup"><span data-stu-id="20f63-108">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="20f63-109">如果您想要深入了解新功能的運作方式第一次，請參閱[Office 365 郵件加密](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="20f63-109">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="20f63-110">本文的其餘部分指的是全新的 OME 功能的發行前 OME 行為。</span><span class="sxs-lookup"><span data-stu-id="20f63-110">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="20f63-111">使用舊版的 Office 365 郵件加密的必要條件</span><span class="sxs-lookup"><span data-stu-id="20f63-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="20f63-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="20f63-112"></span></span>

<span data-ttu-id="20f63-113">Office 365 郵件加密 (OME)，包括 IRM，取決於 Azure 版權管理 (Azure RMS)。</span><span class="sxs-lookup"><span data-stu-id="20f63-113">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="20f63-114">Azure RMS 是使用 Azure 資訊保護來保護技術。</span><span class="sxs-lookup"><span data-stu-id="20f63-114">Azure RMS is the protection technology used by Azure Information Protection.</span></span> <span data-ttu-id="20f63-115">若要使用 OME，Office 365 組織必須包含 Exchange Online 或 Exchange Online Protection，接著，包含訂閱的 Azure Rights Management 訂閱。</span><span class="sxs-lookup"><span data-stu-id="20f63-115">To use OME, your Office 365 organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="20f63-116">如果您不確定您的訂閱所包含的內容，請參閱[訊息原則、 復原和法規遵循](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)的 Exchange Online 服務說明。</span><span class="sxs-lookup"><span data-stu-id="20f63-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span></span>

- <span data-ttu-id="20f63-117">如果您不需要 Azure RMS 訂閱 Exchange Online 或 Exchange Online Protection，您必須購買訂閱，並先啟動它。</span><span class="sxs-lookup"><span data-stu-id="20f63-117">If you don't have an Azure RMS subscription for Exchange Online or Exchange Online Protection, you must purchase a subscription and activate it first.</span></span>

    <span data-ttu-id="20f63-118">如需購買 Azure Rights management 訂閱資訊，請參閱 < <b0>Azure Rights Management</b0>。</span><span class="sxs-lookup"><span data-stu-id="20f63-118">For information about purchasing a subscription to Azure Rights Management, see [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT).</span></span> <span data-ttu-id="20f63-119">下節提供啟動 Azure Rights Management 的資訊。</span><span class="sxs-lookup"><span data-stu-id="20f63-119">The next section gives you information about activating Azure Rights Management.</span></span>

- <span data-ttu-id="20f63-120">如果您有 Azure Rights Management，但它未設定 Exchange Online 或 Exchange Online Protection，這篇文章說明如何啟用 Azure Rights Management，然後說明設定 OME，以使用 Azure 版權管理的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="20f63-120">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="20f63-121">如果您已經設定好 OME 能搭配 Azure 版權管理 Exchange Online 或 Exchange Online Protection，根據您如何設定它，您可能會準備好開始使用 OME 與新功能，其立即。</span><span class="sxs-lookup"><span data-stu-id="20f63-121">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away.</span></span> <span data-ttu-id="20f63-122">本文說明如何判斷是否您已設定 OME 正確，如果您要變更您的設定，該怎麼辦以及如果您選擇不要變更您的設定，會發生什麼事。</span><span class="sxs-lookup"><span data-stu-id="20f63-122">This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup.</span></span> <span data-ttu-id="20f63-123">例如，若要使用的新功能，您必須使用 Azure RMS OME。</span><span class="sxs-lookup"><span data-stu-id="20f63-123">For example, in order to use the new capabilities, you must use Azure RMS with OME.</span></span> <span data-ttu-id="20f63-124">您不能搭配內部部署 Active Directory RMS 的新功能。</span><span class="sxs-lookup"><span data-stu-id="20f63-124">You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="20f63-125">前一版本的 Office 365 中的 OME 啟動 Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="20f63-125">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="20f63-126">您要啟用 Azure Rights Management，以便您組織中的使用者可以將資訊保護套用至他們傳送的郵件，並開啟郵件和已受 Azure 版權管理服務的檔案。</span><span class="sxs-lookup"><span data-stu-id="20f63-126">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service.</span></span> <span data-ttu-id="20f63-127">如需相關指示，請參閱 <<c0>啟動 Azure Rights Management。</span><span class="sxs-lookup"><span data-stu-id="20f63-127">For instructions, see [Activating Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775).</span></span> <span data-ttu-id="20f63-128">當您完成在啟動時，以下傳回，並繼續執行本文中的工作。</span><span class="sxs-lookup"><span data-stu-id="20f63-128">Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="20f63-129">設定舊版的 OME 使用 Azure RMS 匯入受信任發行網域 (Tpd)</span><span class="sxs-lookup"><span data-stu-id="20f63-129">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="20f63-130">TPD 是 XML 檔案，其中包含貴組織的版權管理設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="20f63-130">A TPD is an XML file that contains information about your organization's rights management settings.</span></span> <span data-ttu-id="20f63-131">例如，將 TPD 包含用來簽署及加密憑證和授權的伺服器授權人憑證 (SLC) 的相關資訊、 Url 用於授權和發行，依此類推。</span><span class="sxs-lookup"><span data-stu-id="20f63-131">For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on.</span></span> <span data-ttu-id="20f63-132">您使用 Windows PowerShell 將 TPD 匯入 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="20f63-132">You import the TPD into your Office 365 organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="20f63-133">之前，您可以選擇從 Active Directory Rights Management 服務 (AD RMS) 將 Tpd 匯入到 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="20f63-133">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your Office 365 organization.</span></span> <span data-ttu-id="20f63-134">不過，這樣會使您無法使用全新的 OME 功能並不建議使用。</span><span class="sxs-lookup"><span data-stu-id="20f63-134">However, doing so will prevent you from using the new OME capabilities and is not recommended.</span></span> <span data-ttu-id="20f63-135">如果您的組織是目前的 Office 365 設定如此一來，Microsoft 建議您建立計劃從您的內部部署 Active Directory RMS 移轉至雲端式 Azure 資訊保護。</span><span class="sxs-lookup"><span data-stu-id="20f63-135">If your Office 365 organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection.</span></span> <span data-ttu-id="20f63-136">如需詳細資訊，請參閱 <<c0>從 AD RMS 進行 Azure 資訊保護。</span><span class="sxs-lookup"><span data-stu-id="20f63-136">For more information, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span> <span data-ttu-id="20f63-137">您無法使用全新的 OME 功能，直到您已經完成移轉至 Azure 資訊保護。</span><span class="sxs-lookup"><span data-stu-id="20f63-137">You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="20f63-138">**若要從 Azure RMS 匯入 Tpd**</span><span class="sxs-lookup"><span data-stu-id="20f63-138">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="20f63-139">[連線至 Exchange Online 使用遠端 PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="20f63-139">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="20f63-140">選擇金鑰共用 URL 對應至 Office 365 組織的地理位置：</span><span class="sxs-lookup"><span data-stu-id="20f63-140">Choose the key-sharing URL that corresponds to your Office 365 organization's geographic location:</span></span>

|<span data-ttu-id="20f63-141">**位置**</span><span class="sxs-lookup"><span data-stu-id="20f63-141">**Location**</span></span>|<span data-ttu-id="20f63-142">**金鑰共用位置的 URL**</span><span class="sxs-lookup"><span data-stu-id="20f63-142">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="20f63-143">北美</span><span class="sxs-lookup"><span data-stu-id="20f63-143">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="20f63-144">歐盟</span><span class="sxs-lookup"><span data-stu-id="20f63-144">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="20f63-145">亞</span><span class="sxs-lookup"><span data-stu-id="20f63-145">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="20f63-146">南美洲</span><span class="sxs-lookup"><span data-stu-id="20f63-146">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="20f63-147">Office 365 for Government (政府社群雲端)</span><span class="sxs-lookup"><span data-stu-id="20f63-147">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="20f63-148">此 RMS 金鑰共用位置被保留給客戶已購買 Office 365 for Government Sku。</span><span class="sxs-lookup"><span data-stu-id="20f63-148">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. <span data-ttu-id="20f63-149">設定金鑰共用位置執行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx)指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20f63-149">Configure the key-sharing location by running the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet as follows:</span></span> 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    <span data-ttu-id="20f63-150">例如，若要設定的金鑰共用位置，如果您的組織位於 「 北美地區 」:</span><span class="sxs-lookup"><span data-stu-id="20f63-150">For example, to configure the key sharing location if your organization is located in North America:</span></span>
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. <span data-ttu-id="20f63-151">執行[Import-rmstrustedpublishingdomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx)指令程式搭配-RMSOnline 參數，以匯入 TPD 從 Azure 版權管理：</span><span class="sxs-lookup"><span data-stu-id="20f63-151">Run the [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    <span data-ttu-id="20f63-152">您想要用於 TPD *TPDName*所在的名稱。</span><span class="sxs-lookup"><span data-stu-id="20f63-152">Where  *TPDName*  is the name you want to use for the TPD.</span></span> <span data-ttu-id="20f63-153">例如，「 Contoso 北美地區 TPD 」。</span><span class="sxs-lookup"><span data-stu-id="20f63-153">For example, "Contoso North American TPD".</span></span> 
    
5. <span data-ttu-id="20f63-154">若要確認您成功設定 Office 365 組織要使用 Azure 版權管理服務，請執行[Test-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx)指令程式搭配-RMSOnline 參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20f63-154">To verify that you successfully configured your Office 365 organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet with the -RMSOnline switch as follows:</span></span> 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    <span data-ttu-id="20f63-155">除此之外，這個 cmdlet 會檢查以 Azure 版權管理服務的連線、 下載 TPD，並檢查其有效性。</span><span class="sxs-lookup"><span data-stu-id="20f63-155">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>
    
6. <span data-ttu-id="20f63-156">執行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)指令程式，如下所示來停用不會出現在網頁伺服器與 Outlook 上的 Outlook 中的 Azure Rights Management 範本：</span><span class="sxs-lookup"><span data-stu-id="20f63-156">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. <span data-ttu-id="20f63-157">執行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)指令程式，如下所示為雲端式電子郵件組織啟用 Azure Rights Management，並將其用於 Office 365 郵件加密的 Azure 版權管理設定：</span><span class="sxs-lookup"><span data-stu-id="20f63-157">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span> 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. <span data-ttu-id="20f63-158">若要確認您已成功匯入 TPD 並啟用 Azure Rights Management，請使用 Test-irmconfiguration 指令程式來測試 Azure 版權管理功能。</span><span class="sxs-lookup"><span data-stu-id="20f63-158">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality.</span></span> <span data-ttu-id="20f63-159">如需詳細資訊，請參閱[Test-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)中的 「 範例 1 」。</span><span class="sxs-lookup"><span data-stu-id="20f63-159">For details, see "Example 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span></span>
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="20f63-160">我有舊版的 OME 設定與 Active Directory Rights Management Azure 資訊保護，我該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="20f63-160">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="20f63-161"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="20f63-161"></span></span>

<span data-ttu-id="20f63-162">您可以繼續使用現有的 Office 365 郵件加密郵件流程規則與 Active Directory Rights Management，但您無法設定或使用全新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="20f63-162">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities.</span></span> <span data-ttu-id="20f63-163">相反地，您需要移轉至 Azure 資訊保護。</span><span class="sxs-lookup"><span data-stu-id="20f63-163">Instead, you need to migrate to Azure Information Protection.</span></span> <span data-ttu-id="20f63-164">移轉和這對您的組織相關資訊，請參閱[從 AD RMS 進行 Azure 資訊保護](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)。</span><span class="sxs-lookup"><span data-stu-id="20f63-164">For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="20f63-165">後續步驟</span><span class="sxs-lookup"><span data-stu-id="20f63-165">Next steps</span></span>
<span data-ttu-id="20f63-166"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="20f63-166"></span></span>

<span data-ttu-id="20f63-167">當您完成 Azure 版權管理設定] 中，如果您想要啟用全新的 OME 功能，請參閱[設定以 Azure 資訊保護基礎所建置的全新 Office 365 郵件加密功能。](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span><span class="sxs-lookup"><span data-stu-id="20f63-167">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span></span>
  
<span data-ttu-id="20f63-168">您已設定您的組織使用全新的 OME 功能之後，就可以[定義郵件流程](define-mail-flow-rules-to-encrypt-email.md)規則來保護電子郵件訊息與全新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="20f63-168">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="20f63-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="20f63-169">Related topics</span></span>
<span data-ttu-id="20f63-170"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="20f63-170"></span></span>

[<span data-ttu-id="20f63-171">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="20f63-171">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="20f63-172">關於 Office 365 中加密的技術參考細節</span><span class="sxs-lookup"><span data-stu-id="20f63-172">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="20f63-173">什麼是 Azure 版權管理？</span><span class="sxs-lookup"><span data-stu-id="20f63-173">What is Azure Rights Management?</span></span>](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  

