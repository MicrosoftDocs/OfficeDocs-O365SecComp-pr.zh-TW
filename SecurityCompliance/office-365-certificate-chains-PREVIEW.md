---
title: Office 365 憑證鏈結
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.assetid: 0c03e6b3-e73f-4316-9e2b-bf4091ae96bb
description: Office 365 如何運用不同的憑證提供者的數目。下面會說明客戶存取 Office 365 時可能會遇到的已知 Office 365 根憑證的完整清單。如需憑證的資訊可能必須安裝在您自己的基礎結構，請參閱 Office 365 的規劃第三方 SSL 憑證。下列的憑證資訊適用於所有的 Office 365 的全球和雲端執行個體。
ms.openlocfilehash: 1dcc2dc38bb8e3239a3be3983791b0c60917dc5e
ms.sourcegitcommit: 13f40ff7c1799152bf45af2d8110f4f3235b770a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "25549745"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="4d401-106">Office 365 憑證鏈結</span><span class="sxs-lookup"><span data-stu-id="4d401-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="4d401-p102">Office 365 如何運用不同的憑證提供者的數目。下面會說明客戶存取 Office 365 時可能會遇到的已知 Office 365 根憑證的完整清單。在憑證上的資訊可能需要將安裝在您自己的基礎結構中，請參閱[第三方 SSL 憑證的 Office 365 計劃](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce)。下列的憑證資訊適用於所有的 Office 365 的全球和雲端執行個體。</span><span class="sxs-lookup"><span data-stu-id="4d401-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="4d401-111">**憑證類型**</span><span class="sxs-lookup"><span data-stu-id="4d401-111">**Certificate type**</span></span>|<span data-ttu-id="4d401-112">**P7b 下載 （英文）**</span><span class="sxs-lookup"><span data-stu-id="4d401-112">**P7b download**</span></span>|<span data-ttu-id="4d401-113">**CRL 端點**</span><span class="sxs-lookup"><span data-stu-id="4d401-113">**CRL Endpoints**</span></span>|<span data-ttu-id="4d401-114">**OCSP 端點**</span><span class="sxs-lookup"><span data-stu-id="4d401-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="4d401-115">**AIA 端點**</span><span class="sxs-lookup"><span data-stu-id="4d401-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="4d401-116">公開受信任的根憑證</span><span class="sxs-lookup"><span data-stu-id="4d401-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="4d401-117">Office 365 根憑證組合 (P7B)</span><span class="sxs-lookup"><span data-stu-id="4d401-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="4d401-118">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="4d401-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="4d401-119">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="4d401-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="4d401-120">不適用</span><span class="sxs-lookup"><span data-stu-id="4d401-120">N/A</span></span>  <br/> |<span data-ttu-id="4d401-121">不適用</span><span class="sxs-lookup"><span data-stu-id="4d401-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="4d401-122">公開信任中繼憑證</span><span class="sxs-lookup"><span data-stu-id="4d401-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="4d401-123">Office 365 中繼憑證組合 (P7B)</span><span class="sxs-lookup"><span data-stu-id="4d401-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="4d401-124">cdp1.public trust.com</span><span class="sxs-lookup"><span data-stu-id="4d401-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="4d401-125">crl.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="4d401-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="4d401-126">crl.entrust.net</span><span class="sxs-lookup"><span data-stu-id="4d401-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="4d401-127">crl.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="4d401-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="4d401-128">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="4d401-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="4d401-129">crl.identrust.com</span><span class="sxs-lookup"><span data-stu-id="4d401-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="4d401-130">crl.thawte.com</span><span class="sxs-lookup"><span data-stu-id="4d401-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="4d401-131">crl3.digicert.com</span><span class="sxs-lookup"><span data-stu-id="4d401-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="4d401-132">crl4.digicert.com</span><span class="sxs-lookup"><span data-stu-id="4d401-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="4d401-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="4d401-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="4d401-134">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="4d401-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="4d401-135">isrg.trustid.ocsp.identrust.com</span><span class="sxs-lookup"><span data-stu-id="4d401-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="4d401-136">ocsp.digicert.com</span><span class="sxs-lookup"><span data-stu-id="4d401-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="4d401-137">ocsp.entrust.net</span><span class="sxs-lookup"><span data-stu-id="4d401-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="4d401-138">ocsp.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="4d401-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="4d401-139">ocsp.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="4d401-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="4d401-140">ocsp.startssl.com</span><span class="sxs-lookup"><span data-stu-id="4d401-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="4d401-141">ocsp.thawte.com</span><span class="sxs-lookup"><span data-stu-id="4d401-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="4d401-142">ocsp2.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="4d401-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="4d401-143">ocspcnnicroot.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="4d401-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="4d401-144">根-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="4d401-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="4d401-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="4d401-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="4d401-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="4d401-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="4d401-147">aia.startssl.com</span><span class="sxs-lookup"><span data-stu-id="4d401-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="4d401-148">apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="4d401-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="4d401-149">cacert.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="4d401-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="4d401-150">www.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="4d401-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="4d401-151">展開根目錄與以下以查看憑證提供者相關的其他詳細資料的中階章節。</span><span class="sxs-lookup"><span data-stu-id="4d401-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="4d401-152">Office 365 根憑證的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="4d401-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="4d401-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="4d401-153"></span></span>

 <span data-ttu-id="4d401-154">**Baltimore CyberTrust Root**</span><span class="sxs-lookup"><span data-stu-id="4d401-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="4d401-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="4d401-155">|:-----|</span></span>
|<span data-ttu-id="4d401-156">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="4d401-157">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-157">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-158">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-158"></span></span>|
|<span data-ttu-id="4d401-159">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-159">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-160">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-160"></span></span>|
|<span data-ttu-id="4d401-161">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-162">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-162"></span></span>|
|<span data-ttu-id="4d401-163">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-164">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-164"></span></span>|
|<span data-ttu-id="4d401-165">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-165">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-166">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-166"></span></span>|
|<span data-ttu-id="4d401-167">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-168">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-168"></span></span>|
|<span data-ttu-id="4d401-169">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-170">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-170"></span></span>|
|<span data-ttu-id="4d401-171">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-172">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-172"></span></span>|
|<span data-ttu-id="4d401-173">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-174">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-174"></span></span>|
   
 <span data-ttu-id="4d401-175">**CNNIC 根目錄**</span><span class="sxs-lookup"><span data-stu-id="4d401-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-176">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-176">**Subject**</span></span>|
|<span data-ttu-id="4d401-177">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-177"></span></span>|
|<span data-ttu-id="4d401-178">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-178">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-179">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-179"></span></span>|
|<span data-ttu-id="4d401-180">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-180">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-181">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-181"></span></span>|
|<span data-ttu-id="4d401-182">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-183">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-183"></span></span>|
|<span data-ttu-id="4d401-184">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-185">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-185"></span></span>|
|<span data-ttu-id="4d401-186">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-186">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-187">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-187"></span></span>|
|<span data-ttu-id="4d401-188">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-189">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-189"></span></span>|
|<span data-ttu-id="4d401-190">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-191">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-191"></span></span>|
|<span data-ttu-id="4d401-192">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-193">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-193"></span></span>|
|<span data-ttu-id="4d401-194">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-195">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-195"></span></span>|
|<span data-ttu-id="4d401-196">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-197">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-197"></span></span>|
   
 <span data-ttu-id="4d401-198">**DigiCert 通用的根 CA**</span><span class="sxs-lookup"><span data-stu-id="4d401-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-199">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-199">**Subject**</span></span>|
|<span data-ttu-id="4d401-200">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-200"></span></span>|
|<span data-ttu-id="4d401-201">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-201">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-202">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-202"></span></span>|
|<span data-ttu-id="4d401-203">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-203">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-204">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-204"></span></span>|
|<span data-ttu-id="4d401-205">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-206">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-206"></span></span>|
|<span data-ttu-id="4d401-207">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-208">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-208"></span></span>|
|<span data-ttu-id="4d401-209">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-209">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-210">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-210"></span></span>|
|<span data-ttu-id="4d401-211">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-212">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-212"></span></span>|
|<span data-ttu-id="4d401-213">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-214">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-214"></span></span>|
|<span data-ttu-id="4d401-215">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-216">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-216"></span></span>|
|<span data-ttu-id="4d401-217">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-218">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-218"></span></span>|
|<span data-ttu-id="4d401-219">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-220">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-220"></span></span>|
   
 <span data-ttu-id="4d401-221">**DigiCert 高保證 EV 根 CA**</span><span class="sxs-lookup"><span data-stu-id="4d401-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-222">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-222">**Subject**</span></span>|
|<span data-ttu-id="4d401-223">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-223"></span></span>|
|<span data-ttu-id="4d401-224">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-224">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-225">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-225"></span></span>|
|<span data-ttu-id="4d401-226">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-226">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-227">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-227"></span></span>|
|<span data-ttu-id="4d401-228">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-229">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-229"></span></span>|
|<span data-ttu-id="4d401-230">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-231">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-231"></span></span>|
|<span data-ttu-id="4d401-232">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-232">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-233">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-233"></span></span>|
|<span data-ttu-id="4d401-234">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-235">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-235"></span></span>|
|<span data-ttu-id="4d401-236">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-237">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-237"></span></span>|
|<span data-ttu-id="4d401-238">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-239">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-239"></span></span>|
|<span data-ttu-id="4d401-240">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-241">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-241"></span></span>|
|<span data-ttu-id="4d401-242">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-243">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-243"></span></span>|
   
 <span data-ttu-id="4d401-244">**D 信任根類別 3 CA 2 2009**</span><span class="sxs-lookup"><span data-stu-id="4d401-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-245">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-245">**Subject**</span></span>|
|<span data-ttu-id="4d401-246">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-246"></span></span>|
|<span data-ttu-id="4d401-247">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-247">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-248">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-248"></span></span>|
|<span data-ttu-id="4d401-249">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-249">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-250">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-250"></span></span>|
|<span data-ttu-id="4d401-251">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-252">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-252"></span></span>|
|<span data-ttu-id="4d401-253">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-254">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-254"></span></span>|
|<span data-ttu-id="4d401-255">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-255">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-256">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-256"></span></span>|
|<span data-ttu-id="4d401-257">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-258">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-258"></span></span>|
|<span data-ttu-id="4d401-259">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-260">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-260"></span></span>|
|<span data-ttu-id="4d401-261">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-262">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-262"></span></span>|
|<span data-ttu-id="4d401-263">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-264">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-264"></span></span>|
|<span data-ttu-id="4d401-265">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-265">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-266">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-266"></span></span>|
   
 <span data-ttu-id="4d401-267">**D 信任根類別 3 CA 2 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="4d401-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-268">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-268">**Subject**</span></span>|
|<span data-ttu-id="4d401-269">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-269"></span></span>|
|<span data-ttu-id="4d401-270">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-270">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-271">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-271"></span></span>|
|<span data-ttu-id="4d401-272">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-272">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-273">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-273"></span></span>|
|<span data-ttu-id="4d401-274">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-275">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-275"></span></span>|
|<span data-ttu-id="4d401-276">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-277">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-277"></span></span>|
|<span data-ttu-id="4d401-278">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-278">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-279">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-279"></span></span>|
|<span data-ttu-id="4d401-280">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-281">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-281"></span></span>|
|<span data-ttu-id="4d401-282">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-283">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-283"></span></span>|
|<span data-ttu-id="4d401-284">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-285">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-285"></span></span>|
|<span data-ttu-id="4d401-286">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-287">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-287"></span></span>|
|<span data-ttu-id="4d401-288">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-288">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-289">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-289"></span></span>|
   
 <span data-ttu-id="4d401-290">**DST 根 CA X3**</span><span class="sxs-lookup"><span data-stu-id="4d401-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-291">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-291">**Subject**</span></span>|
|<span data-ttu-id="4d401-292">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-292"></span></span>|
|<span data-ttu-id="4d401-293">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-293">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-294">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-294"></span></span>|
|<span data-ttu-id="4d401-295">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-295">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-296">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-296"></span></span>|
|<span data-ttu-id="4d401-297">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-298">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-298"></span></span>|
|<span data-ttu-id="4d401-299">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-300">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-300"></span></span>|
|<span data-ttu-id="4d401-301">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-301">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-302">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-302"></span></span>|
|<span data-ttu-id="4d401-303">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-304">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-304"></span></span>|
|<span data-ttu-id="4d401-305">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-306">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-306"></span></span>|
|<span data-ttu-id="4d401-307">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-308">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-308"></span></span>|
|<span data-ttu-id="4d401-309">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-310">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-310"></span></span>|
   
 <span data-ttu-id="4d401-311">**過程錄影根憑證授權單位-G2**</span><span class="sxs-lookup"><span data-stu-id="4d401-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-312">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-312">**Subject**</span></span>|
|<span data-ttu-id="4d401-313">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-313"></span></span>|
|<span data-ttu-id="4d401-314">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-314">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-315">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-315"></span></span>|
|<span data-ttu-id="4d401-316">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-316">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-317">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-317"></span></span>|
|<span data-ttu-id="4d401-318">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-319">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-319"></span></span>|
|<span data-ttu-id="4d401-320">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-321">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-321"></span></span>|
|<span data-ttu-id="4d401-322">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-322">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-323">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-323"></span></span>|
|<span data-ttu-id="4d401-324">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-325">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-325"></span></span>|
|<span data-ttu-id="4d401-326">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-327">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-327"></span></span>|
|<span data-ttu-id="4d401-328">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-329">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-329"></span></span>|
|<span data-ttu-id="4d401-330">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-331">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-331"></span></span>|
   
 <span data-ttu-id="4d401-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="4d401-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-333">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-333">**Subject**</span></span>|
|<span data-ttu-id="4d401-334">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-334"></span></span>|
|<span data-ttu-id="4d401-335">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-335">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-336">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-336"></span></span>|
|<span data-ttu-id="4d401-337">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-337">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-338">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-338"></span></span>|
|<span data-ttu-id="4d401-339">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-340">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-340"></span></span>|
|<span data-ttu-id="4d401-341">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-342">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-342"></span></span>|
|<span data-ttu-id="4d401-343">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-343">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-344">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-344"></span></span>|
|<span data-ttu-id="4d401-345">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-346">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-346"></span></span>|
|<span data-ttu-id="4d401-347">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-348">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-348"></span></span>|
|<span data-ttu-id="4d401-349">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-350">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-350"></span></span>|
|<span data-ttu-id="4d401-351">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-352">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-352"></span></span>|
   
 <span data-ttu-id="4d401-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="4d401-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-354">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-354">**Subject**</span></span>|
|<span data-ttu-id="4d401-355">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-355"></span></span>|
|<span data-ttu-id="4d401-356">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-356">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-357">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-357"></span></span>|
|<span data-ttu-id="4d401-358">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-358">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-359">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-359"></span></span>|
|<span data-ttu-id="4d401-360">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-361">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-361"></span></span>|
|<span data-ttu-id="4d401-362">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-363">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-363"></span></span>|
|<span data-ttu-id="4d401-364">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-364">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-365">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-365"></span></span>|
|<span data-ttu-id="4d401-366">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-367">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-367"></span></span>|
|<span data-ttu-id="4d401-368">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-369">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-369"></span></span>|
|<span data-ttu-id="4d401-370">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-371">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-371"></span></span>|
|<span data-ttu-id="4d401-372">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-373">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-373"></span></span>|
|<span data-ttu-id="4d401-374">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-375">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-375"></span></span>|
|<span data-ttu-id="4d401-376">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-376">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-377">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-377"></span></span>|
   
 <span data-ttu-id="4d401-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="4d401-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-379">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-379">**Subject**</span></span>|
|<span data-ttu-id="4d401-380">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-380"></span></span>|
|<span data-ttu-id="4d401-381">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-381">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-382">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-382"></span></span>|
|<span data-ttu-id="4d401-383">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-383">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-384">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-384"></span></span>|
|<span data-ttu-id="4d401-385">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-386">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-386"></span></span>|
|<span data-ttu-id="4d401-387">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-388">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-388"></span></span>|
|<span data-ttu-id="4d401-389">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-389">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-390">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-390"></span></span>|
|<span data-ttu-id="4d401-391">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-392">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-392"></span></span>|
|<span data-ttu-id="4d401-393">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-394">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-394"></span></span>|
|<span data-ttu-id="4d401-395">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-396">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-396"></span></span>|
|<span data-ttu-id="4d401-397">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-398">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-398"></span></span>|
   
 <span data-ttu-id="4d401-399">**thawte 主要的根 CA-G3**</span><span class="sxs-lookup"><span data-stu-id="4d401-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-400">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-400">**Subject**</span></span>|
|<span data-ttu-id="4d401-401">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-401"></span></span>|
|<span data-ttu-id="4d401-402">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-402">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-403">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-403"></span></span>|
|<span data-ttu-id="4d401-404">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-404">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-405">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-405"></span></span>|
|<span data-ttu-id="4d401-406">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-407">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-407"></span></span>|
|<span data-ttu-id="4d401-408">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-409">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-409"></span></span>|
|<span data-ttu-id="4d401-410">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-410">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-411">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-411"></span></span>|
|<span data-ttu-id="4d401-412">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-413">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-413"></span></span>|
|<span data-ttu-id="4d401-414">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-415">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-415"></span></span>|
|<span data-ttu-id="4d401-416">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-417">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-417"></span></span>|
|<span data-ttu-id="4d401-418">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-419">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-419"></span></span>|
   
 <span data-ttu-id="4d401-420">**VeriSign 類別 3 主要的公用憑證授權單位-G5**</span><span class="sxs-lookup"><span data-stu-id="4d401-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-421">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-421">**Subject**</span></span>|
|<span data-ttu-id="4d401-422">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-422"></span></span>|
|<span data-ttu-id="4d401-423">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-423">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-424">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-424"></span></span>|
|<span data-ttu-id="4d401-425">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-425">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-426">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-426"></span></span>|
|<span data-ttu-id="4d401-427">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-428">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-428"></span></span>|
|<span data-ttu-id="4d401-429">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-430">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-430"></span></span>|
|<span data-ttu-id="4d401-431">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-431">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-432">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-432"></span></span>|
|<span data-ttu-id="4d401-433">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-434">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-434"></span></span>|
|<span data-ttu-id="4d401-435">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-436">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-436"></span></span>|
|<span data-ttu-id="4d401-437">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-438">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-438"></span></span>|
|<span data-ttu-id="4d401-439">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-440">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="4d401-441">Office 365 中繼憑證的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="4d401-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="4d401-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="4d401-442"></span></span>

 <span data-ttu-id="4d401-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="4d401-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-444">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-444">**Subject**</span></span>|
|<span data-ttu-id="4d401-445">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-445"></span></span>|
|<span data-ttu-id="4d401-446">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-446">**Issuer**</span></span>|
|<span data-ttu-id="4d401-447">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-447"></span></span>|
|<span data-ttu-id="4d401-448">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-448">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-449">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-449"></span></span>|
|<span data-ttu-id="4d401-450">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-450">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-451">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-451"></span></span>|
|<span data-ttu-id="4d401-452">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-453">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-453"></span></span>|
|<span data-ttu-id="4d401-454">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-455">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-455"></span></span>|
|<span data-ttu-id="4d401-456">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-456">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-457">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-457"></span></span>|
|<span data-ttu-id="4d401-458">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-459">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-459"></span></span>|
|<span data-ttu-id="4d401-460">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-461">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-461"></span></span>|
|<span data-ttu-id="4d401-462">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-463">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-463"></span></span>|
|<span data-ttu-id="4d401-464">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-465">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-465"></span></span>|
|<span data-ttu-id="4d401-466">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-467">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-467"></span></span>|
|<span data-ttu-id="4d401-468">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-468">**AIA URLs**</span></span>|
|<span data-ttu-id="4d401-469">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-469"></span></span>|
|<span data-ttu-id="4d401-470">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-470">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-471">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-471"></span></span>|
|<span data-ttu-id="4d401-472">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-473">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-473"></span></span>|
   
 <span data-ttu-id="4d401-474">**D 信任 SSL 類別 3 CA 1 2009**</span><span class="sxs-lookup"><span data-stu-id="4d401-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-475">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-475">**Subject**</span></span>|
|<span data-ttu-id="4d401-476">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-476"></span></span>|
|<span data-ttu-id="4d401-477">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-477">**Issuer**</span></span>|
|<span data-ttu-id="4d401-478">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-478"></span></span>|
|<span data-ttu-id="4d401-479">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="4d401-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="4d401-480">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-480"></span></span>|
|<span data-ttu-id="4d401-481">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-481">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-482">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-482"></span></span>|
|<span data-ttu-id="4d401-483">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-483">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-484">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-484"></span></span>|
|<span data-ttu-id="4d401-485">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-486">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-486"></span></span>|
|<span data-ttu-id="4d401-487">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-488">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-488"></span></span>|
|<span data-ttu-id="4d401-489">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-489">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-490">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-490"></span></span>|
|<span data-ttu-id="4d401-491">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-492">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-492"></span></span>|
|<span data-ttu-id="4d401-493">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-494">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-494"></span></span>|
|<span data-ttu-id="4d401-495">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-496">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-496"></span></span>|
|<span data-ttu-id="4d401-497">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-498">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-498"></span></span>|
|<span data-ttu-id="4d401-499">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-500">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-500"></span></span>|
|<span data-ttu-id="4d401-501">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-501">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-502">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-502"></span></span>|
|<span data-ttu-id="4d401-503">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-504">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-504"></span></span>|
   
 <span data-ttu-id="4d401-505">**D 信任 SSL 類別 3 CA 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="4d401-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-506">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-506">**Subject**</span></span>|
|<span data-ttu-id="4d401-507">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-507"></span></span>|
|<span data-ttu-id="4d401-508">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-508">**Issuer**</span></span>|
|<span data-ttu-id="4d401-509">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-509"></span></span>|
|<span data-ttu-id="4d401-510">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="4d401-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="4d401-511">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-511"></span></span>|
|<span data-ttu-id="4d401-512">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-512">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-513">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-513"></span></span>|
|<span data-ttu-id="4d401-514">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-514">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-515">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-515"></span></span>|
|<span data-ttu-id="4d401-516">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-517">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-517"></span></span>|
|<span data-ttu-id="4d401-518">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-519">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-519"></span></span>|
|<span data-ttu-id="4d401-520">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-520">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-521">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-521"></span></span>|
|<span data-ttu-id="4d401-522">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-523">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-523"></span></span>|
|<span data-ttu-id="4d401-524">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-525">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-525"></span></span>|
|<span data-ttu-id="4d401-526">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-527">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-527"></span></span>|
|<span data-ttu-id="4d401-528">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-529">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-529"></span></span>|
|<span data-ttu-id="4d401-530">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-531">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-531"></span></span>|
|<span data-ttu-id="4d401-532">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-532">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-533">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-533"></span></span>|
|<span data-ttu-id="4d401-534">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-535">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-535"></span></span>|
   
 <span data-ttu-id="4d401-536">**DigiCert 雲端服務 CA-1**</span><span class="sxs-lookup"><span data-stu-id="4d401-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-537">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-537">**Subject**</span></span>|
|<span data-ttu-id="4d401-538">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-538"></span></span>|
|<span data-ttu-id="4d401-539">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-539">**Issuer**</span></span>|
|<span data-ttu-id="4d401-540">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-540"></span></span>|
|<span data-ttu-id="4d401-541">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-541">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-542">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-542"></span></span>|
|<span data-ttu-id="4d401-543">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-543">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-544">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-544"></span></span>|
|<span data-ttu-id="4d401-545">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-546">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-546"></span></span>|
|<span data-ttu-id="4d401-547">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-548">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-548"></span></span>|
|<span data-ttu-id="4d401-549">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-549">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-550">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-550"></span></span>|
|<span data-ttu-id="4d401-551">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-552">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-552"></span></span>|
|<span data-ttu-id="4d401-553">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-554">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-554"></span></span>|
|<span data-ttu-id="4d401-555">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-556">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-556"></span></span>|
|<span data-ttu-id="4d401-557">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-558">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-558"></span></span>|
|<span data-ttu-id="4d401-559">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-560">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-560"></span></span>|
|<span data-ttu-id="4d401-561">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-561">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-562">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-562"></span></span>|
|<span data-ttu-id="4d401-563">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-564">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-564"></span></span>|
   
 <span data-ttu-id="4d401-565">**DigiCert SHA2 高保證伺服器 CA**</span><span class="sxs-lookup"><span data-stu-id="4d401-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-566">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-566">**Subject**</span></span>|
|<span data-ttu-id="4d401-567">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-567"></span></span>|
|<span data-ttu-id="4d401-568">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-568">**Issuer**</span></span>|
|<span data-ttu-id="4d401-569">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-569"></span></span>|
|<span data-ttu-id="4d401-570">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-570">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-571">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-571"></span></span>|
|<span data-ttu-id="4d401-572">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-572">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-573">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-573"></span></span>|
|<span data-ttu-id="4d401-574">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-575">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-575"></span></span>|
|<span data-ttu-id="4d401-576">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-577">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-577"></span></span>|
|<span data-ttu-id="4d401-578">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-578">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-579">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-579"></span></span>|
|<span data-ttu-id="4d401-580">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-581">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-581"></span></span>|
|<span data-ttu-id="4d401-582">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-583">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-583"></span></span>|
|<span data-ttu-id="4d401-584">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-585">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-585"></span></span>|
|<span data-ttu-id="4d401-586">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-587">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-587"></span></span>|
|<span data-ttu-id="4d401-588">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-589">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-589"></span></span>|
|<span data-ttu-id="4d401-590">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-590">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-591">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-591"></span></span>|
|<span data-ttu-id="4d401-592">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-593">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-593"></span></span>|
   
 <span data-ttu-id="4d401-594">**DigiCert SHA2 保護伺服器的 CA**</span><span class="sxs-lookup"><span data-stu-id="4d401-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-595">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-595">**Subject**</span></span>|
|<span data-ttu-id="4d401-596">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-596"></span></span>|
|<span data-ttu-id="4d401-597">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-597">**Issuer**</span></span>|
|<span data-ttu-id="4d401-598">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-598"></span></span>|
|<span data-ttu-id="4d401-599">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-599">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-600">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-600"></span></span>|
|<span data-ttu-id="4d401-601">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-601">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-602">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-602"></span></span>|
|<span data-ttu-id="4d401-603">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-604">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-604"></span></span>|
|<span data-ttu-id="4d401-605">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-606">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-606"></span></span>|
|<span data-ttu-id="4d401-607">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-607">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-608">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-608"></span></span>|
|<span data-ttu-id="4d401-609">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-610">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-610"></span></span>|
|<span data-ttu-id="4d401-611">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-612">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-612"></span></span>|
|<span data-ttu-id="4d401-613">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-614">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-614"></span></span>|
|<span data-ttu-id="4d401-615">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-616">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-616"></span></span>|
|<span data-ttu-id="4d401-617">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-618">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-618"></span></span>|
|<span data-ttu-id="4d401-619">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-619">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-620">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-620"></span></span>|
|<span data-ttu-id="4d401-621">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-622">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-622"></span></span>|
   
 <span data-ttu-id="4d401-623">**過程錄影憑證授權單位-L1C**</span><span class="sxs-lookup"><span data-stu-id="4d401-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-624">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-624">**Subject**</span></span>|
|<span data-ttu-id="4d401-625">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-625"></span></span>|
|<span data-ttu-id="4d401-626">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-626">**Issuer**</span></span>|
|<span data-ttu-id="4d401-627">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-627"></span></span>|
|<span data-ttu-id="4d401-628">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-628">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-629">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-629"></span></span>|
|<span data-ttu-id="4d401-630">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-630">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-631">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-631"></span></span>|
|<span data-ttu-id="4d401-632">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-633">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-633"></span></span>|
|<span data-ttu-id="4d401-634">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-635">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-635"></span></span>|
|<span data-ttu-id="4d401-636">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-636">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-637">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-637"></span></span>|
|<span data-ttu-id="4d401-638">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-639">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-639"></span></span>|
|<span data-ttu-id="4d401-640">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-641">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-641"></span></span>|
|<span data-ttu-id="4d401-642">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-643">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-643"></span></span>|
|<span data-ttu-id="4d401-644">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-645">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-645"></span></span>|
|<span data-ttu-id="4d401-646">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-647">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-647"></span></span>|
|<span data-ttu-id="4d401-648">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-648">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-649">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-649"></span></span>|
|<span data-ttu-id="4d401-650">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-651">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-651"></span></span>|
   
 <span data-ttu-id="4d401-652">**過程錄影憑證授權單位-L1K**</span><span class="sxs-lookup"><span data-stu-id="4d401-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-653">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-653">**Subject**</span></span>|
|<span data-ttu-id="4d401-654">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-654"></span></span>|
|<span data-ttu-id="4d401-655">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-655">**Issuer**</span></span>|
|<span data-ttu-id="4d401-656">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-656"></span></span>|
|<span data-ttu-id="4d401-657">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-657">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-658">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-658"></span></span>|
|<span data-ttu-id="4d401-659">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-659">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-660">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-660"></span></span>|
|<span data-ttu-id="4d401-661">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-662">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-662"></span></span>|
|<span data-ttu-id="4d401-663">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-664">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-664"></span></span>|
|<span data-ttu-id="4d401-665">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-665">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-666">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-666"></span></span>|
|<span data-ttu-id="4d401-667">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-668">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-668"></span></span>|
|<span data-ttu-id="4d401-669">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-670">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-670"></span></span>|
|<span data-ttu-id="4d401-671">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-672">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-672"></span></span>|
|<span data-ttu-id="4d401-673">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-674">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-674"></span></span>|
|<span data-ttu-id="4d401-675">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-676">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-676"></span></span>|
|<span data-ttu-id="4d401-677">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-677">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-678">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-678"></span></span>|
|<span data-ttu-id="4d401-679">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-680">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-680"></span></span>|
   
 <span data-ttu-id="4d401-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="4d401-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-682">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-682">**Subject**</span></span>|
|<span data-ttu-id="4d401-683">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-683"></span></span>|
|<span data-ttu-id="4d401-684">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-684">**Issuer**</span></span>|
|<span data-ttu-id="4d401-685">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-685"></span></span>|
|<span data-ttu-id="4d401-686">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-686">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-687">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-687"></span></span>|
|<span data-ttu-id="4d401-688">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-688">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-689">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-689"></span></span>|
|<span data-ttu-id="4d401-690">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-691">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-691"></span></span>|
|<span data-ttu-id="4d401-692">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-693">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-693"></span></span>|
|<span data-ttu-id="4d401-694">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-694">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-695">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-695"></span></span>|
|<span data-ttu-id="4d401-696">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-697">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-697"></span></span>|
|<span data-ttu-id="4d401-698">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-699">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-699"></span></span>|
|<span data-ttu-id="4d401-700">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-701">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-701"></span></span>|
|<span data-ttu-id="4d401-702">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-703">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-703"></span></span>|
|<span data-ttu-id="4d401-704">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-705">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-705"></span></span>|
|<span data-ttu-id="4d401-706">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-706">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-707">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-707"></span></span>|
|<span data-ttu-id="4d401-708">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-709">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-709"></span></span>|
   
 <span data-ttu-id="4d401-710">**GlobalSign 擴充驗證 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="4d401-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-711">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-711">**Subject**</span></span>|
|<span data-ttu-id="4d401-712">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-712"></span></span>|
|<span data-ttu-id="4d401-713">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-713">**Issuer**</span></span>|
|<span data-ttu-id="4d401-714">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-714"></span></span>|
|<span data-ttu-id="4d401-715">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-715">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-716">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-716"></span></span>|
|<span data-ttu-id="4d401-717">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-717">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-718">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-718"></span></span>|
|<span data-ttu-id="4d401-719">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-720">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-720"></span></span>|
|<span data-ttu-id="4d401-721">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-722">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-722"></span></span>|
|<span data-ttu-id="4d401-723">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-723">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-724">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-724"></span></span>|
|<span data-ttu-id="4d401-725">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-726">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-726"></span></span>|
|<span data-ttu-id="4d401-727">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-728">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-728"></span></span>|
|<span data-ttu-id="4d401-729">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-730">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-730"></span></span>|
|<span data-ttu-id="4d401-731">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-732">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-732"></span></span>|
|<span data-ttu-id="4d401-733">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-734">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-734"></span></span>|
|<span data-ttu-id="4d401-735">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-735">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-736">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-736"></span></span>|
|<span data-ttu-id="4d401-737">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-738">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-738"></span></span>|
   
 <span data-ttu-id="4d401-739">**GlobalSign 擴充驗證 CA-SHA256-G3**</span><span class="sxs-lookup"><span data-stu-id="4d401-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-740">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-740">**Subject**</span></span>|
|<span data-ttu-id="4d401-741">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-741"></span></span>|
|<span data-ttu-id="4d401-742">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-742">**Issuer**</span></span>|
|<span data-ttu-id="4d401-743">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-743"></span></span>|
|<span data-ttu-id="4d401-744">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-744">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-745">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-745"></span></span>|
|<span data-ttu-id="4d401-746">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-746">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-747">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-747"></span></span>|
|<span data-ttu-id="4d401-748">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-749">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-749"></span></span>|
|<span data-ttu-id="4d401-750">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-751">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-751"></span></span>|
|<span data-ttu-id="4d401-752">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-752">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-753">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-753"></span></span>|
|<span data-ttu-id="4d401-754">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-755">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-755"></span></span>|
|<span data-ttu-id="4d401-756">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-757">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-757"></span></span>|
|<span data-ttu-id="4d401-758">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-759">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-759"></span></span>|
|<span data-ttu-id="4d401-760">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-761">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-761"></span></span>|
|<span data-ttu-id="4d401-762">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-763">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-763"></span></span>|
|<span data-ttu-id="4d401-764">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-764">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-765">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-765"></span></span>|
|<span data-ttu-id="4d401-766">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-767">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-767"></span></span>|
   
 <span data-ttu-id="4d401-768">**GlobalSign 組織驗證 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="4d401-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-769">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-769">**Subject**</span></span>|
|<span data-ttu-id="4d401-770">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-770"></span></span>|
|<span data-ttu-id="4d401-771">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-771">**Issuer**</span></span>|
|<span data-ttu-id="4d401-772">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-772"></span></span>|
|<span data-ttu-id="4d401-773">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-773">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-774">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-774"></span></span>|
|<span data-ttu-id="4d401-775">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-775">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-776">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-776"></span></span>|
|<span data-ttu-id="4d401-777">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-778">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-778"></span></span>|
|<span data-ttu-id="4d401-779">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-780">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-780"></span></span>|
|<span data-ttu-id="4d401-781">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-781">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-782">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-782"></span></span>|
|<span data-ttu-id="4d401-783">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-784">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-784"></span></span>|
|<span data-ttu-id="4d401-785">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-786">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-786"></span></span>|
|<span data-ttu-id="4d401-787">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-788">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-788"></span></span>|
|<span data-ttu-id="4d401-789">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-790">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-790"></span></span>|
|<span data-ttu-id="4d401-791">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-792">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-792"></span></span>|
|<span data-ttu-id="4d401-793">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-793">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-794">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-794"></span></span>|
|<span data-ttu-id="4d401-795">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-796">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-796"></span></span>|
   
 <span data-ttu-id="4d401-797">**GlobalSign 組織驗證 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="4d401-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-798">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-798">**Subject**</span></span>|
|<span data-ttu-id="4d401-799">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-799"></span></span>|
|<span data-ttu-id="4d401-800">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-800">**Issuer**</span></span>|
|<span data-ttu-id="4d401-801">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-801"></span></span>|
|<span data-ttu-id="4d401-802">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-802">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-803">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-803"></span></span>|
|<span data-ttu-id="4d401-804">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-804">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-805">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-805"></span></span>|
|<span data-ttu-id="4d401-806">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-807">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-807"></span></span>|
|<span data-ttu-id="4d401-808">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-809">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-809"></span></span>|
|<span data-ttu-id="4d401-810">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-810">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-811">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-811"></span></span>|
|<span data-ttu-id="4d401-812">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-813">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-813"></span></span>|
|<span data-ttu-id="4d401-814">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-815">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-815"></span></span>|
|<span data-ttu-id="4d401-816">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-817">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-817"></span></span>|
|<span data-ttu-id="4d401-818">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-819">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-819"></span></span>|
|<span data-ttu-id="4d401-820">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-821">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-821"></span></span>|
|<span data-ttu-id="4d401-822">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-822">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-823">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-823"></span></span>|
|<span data-ttu-id="4d401-824">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-825">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-825"></span></span>|
   
 <span data-ttu-id="4d401-826">**我們加密授權 X3**</span><span class="sxs-lookup"><span data-stu-id="4d401-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-827">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-827">**Subject**</span></span>|
|<span data-ttu-id="4d401-828">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-828"></span></span>|
|<span data-ttu-id="4d401-829">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-829">**Issuer**</span></span>|
|<span data-ttu-id="4d401-830">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-830"></span></span>|
|<span data-ttu-id="4d401-831">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-831">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-832">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-832"></span></span>|
|<span data-ttu-id="4d401-833">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-833">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-834">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-834"></span></span>|
|<span data-ttu-id="4d401-835">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-836">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-836"></span></span>|
|<span data-ttu-id="4d401-837">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-838">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-838"></span></span>|
|<span data-ttu-id="4d401-839">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-839">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-840">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-840"></span></span>|
|<span data-ttu-id="4d401-841">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-842">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-842"></span></span>|
|<span data-ttu-id="4d401-843">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-844">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-844"></span></span>|
|<span data-ttu-id="4d401-845">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-846">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-846"></span></span>|
|<span data-ttu-id="4d401-847">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-848">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-848"></span></span>|
|<span data-ttu-id="4d401-849">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-850">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-850"></span></span>|
|<span data-ttu-id="4d401-851">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-851">**AIA URLs**</span></span>|
|<span data-ttu-id="4d401-852">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-852"></span></span>|
|<span data-ttu-id="4d401-853">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-853">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-854">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-854"></span></span>|
|<span data-ttu-id="4d401-855">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-856">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-856"></span></span>|
   
 <span data-ttu-id="4d401-857">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="4d401-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-858">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-858">**Subject**</span></span>|
|<span data-ttu-id="4d401-859">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-859"></span></span>|
|<span data-ttu-id="4d401-860">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-860">**Issuer**</span></span>|
|<span data-ttu-id="4d401-861">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-861"></span></span>|
|<span data-ttu-id="4d401-862">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-862">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-863">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-863"></span></span>|
|<span data-ttu-id="4d401-864">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-864">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-865">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-865"></span></span>|
|<span data-ttu-id="4d401-866">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-867">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-867"></span></span>|
|<span data-ttu-id="4d401-868">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-869">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-869"></span></span>|
|<span data-ttu-id="4d401-870">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-870">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-871">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-871"></span></span>|
|<span data-ttu-id="4d401-872">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-873">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-873"></span></span>|
|<span data-ttu-id="4d401-874">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-875">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-875"></span></span>|
|<span data-ttu-id="4d401-876">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-877">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-877"></span></span>|
|<span data-ttu-id="4d401-878">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-879">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-879"></span></span>|
|<span data-ttu-id="4d401-880">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-881">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-881"></span></span>|
|<span data-ttu-id="4d401-882">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-882">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-883">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-883"></span></span>|
   
 <span data-ttu-id="4d401-884">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="4d401-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-885">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-885">**Subject**</span></span>|
|<span data-ttu-id="4d401-886">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-886"></span></span>|
|<span data-ttu-id="4d401-887">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-887">**Issuer**</span></span>|
|<span data-ttu-id="4d401-888">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-888"></span></span>|
|<span data-ttu-id="4d401-889">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-889">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-890">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-890"></span></span>|
|<span data-ttu-id="4d401-891">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-891">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-892">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-892"></span></span>|
|<span data-ttu-id="4d401-893">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-894">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-894"></span></span>|
|<span data-ttu-id="4d401-895">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-896">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-896"></span></span>|
|<span data-ttu-id="4d401-897">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-897">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-898">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-898"></span></span>|
|<span data-ttu-id="4d401-899">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-900">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-900"></span></span>|
|<span data-ttu-id="4d401-901">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-902">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-902"></span></span>|
|<span data-ttu-id="4d401-903">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-904">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-904"></span></span>|
|<span data-ttu-id="4d401-905">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-906">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-906"></span></span>|
|<span data-ttu-id="4d401-907">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-908">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-908"></span></span>|
|<span data-ttu-id="4d401-909">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-909">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-910">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-910"></span></span>|
|<span data-ttu-id="4d401-911">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-912">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-912"></span></span>|
   
 <span data-ttu-id="4d401-913">**Microsoft IT TLS CA 1**</span><span class="sxs-lookup"><span data-stu-id="4d401-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-914">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-914">**Subject**</span></span>|
|<span data-ttu-id="4d401-915">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-915"></span></span>|
|<span data-ttu-id="4d401-916">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-916">**Issuer**</span></span>|
|<span data-ttu-id="4d401-917">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-917"></span></span>|
|<span data-ttu-id="4d401-918">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-918">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-919">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-919"></span></span>|
|<span data-ttu-id="4d401-920">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-920">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-921">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-921"></span></span>|
|<span data-ttu-id="4d401-922">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-923">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-923"></span></span>|
|<span data-ttu-id="4d401-924">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-925">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-925"></span></span>|
|<span data-ttu-id="4d401-926">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-926">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-927">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-927"></span></span>|
|<span data-ttu-id="4d401-928">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-929">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-929"></span></span>|
|<span data-ttu-id="4d401-930">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-931">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-931"></span></span>|
|<span data-ttu-id="4d401-932">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-933">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-933"></span></span>|
|<span data-ttu-id="4d401-934">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-935">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-935"></span></span>|
|<span data-ttu-id="4d401-936">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-937">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-937"></span></span>|
|<span data-ttu-id="4d401-938">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-938">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-939">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-939"></span></span>|
|<span data-ttu-id="4d401-940">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-941">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-941"></span></span>|
   
 <span data-ttu-id="4d401-942">**Microsoft IT TLS CA 2**</span><span class="sxs-lookup"><span data-stu-id="4d401-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-943">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-943">**Subject**</span></span>|
|<span data-ttu-id="4d401-944">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-944"></span></span>|
|<span data-ttu-id="4d401-945">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-945">**Issuer**</span></span>|
|<span data-ttu-id="4d401-946">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-946"></span></span>|
|<span data-ttu-id="4d401-947">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-947">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-948">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-948"></span></span>|
|<span data-ttu-id="4d401-949">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-949">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-950">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-950"></span></span>|
|<span data-ttu-id="4d401-951">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-952">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-952"></span></span>|
|<span data-ttu-id="4d401-953">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-954">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-954"></span></span>|
|<span data-ttu-id="4d401-955">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-955">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-956">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-956"></span></span>|
|<span data-ttu-id="4d401-957">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-958">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-958"></span></span>|
|<span data-ttu-id="4d401-959">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-960">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-960"></span></span>|
|<span data-ttu-id="4d401-961">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-962">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-962"></span></span>|
|<span data-ttu-id="4d401-963">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-964">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-964"></span></span>|
|<span data-ttu-id="4d401-965">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-966">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-966"></span></span>|
|<span data-ttu-id="4d401-967">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-967">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-968">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-968"></span></span>|
|<span data-ttu-id="4d401-969">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-970">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-970"></span></span>|
   
 <span data-ttu-id="4d401-971">**Microsoft IT TLS CA 4**</span><span class="sxs-lookup"><span data-stu-id="4d401-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-972">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-972">**Subject**</span></span>|
|<span data-ttu-id="4d401-973">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-973"></span></span>|
|<span data-ttu-id="4d401-974">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-974">**Issuer**</span></span>|
|<span data-ttu-id="4d401-975">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-975"></span></span>|
|<span data-ttu-id="4d401-976">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-976">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-977">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-977"></span></span>|
|<span data-ttu-id="4d401-978">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-978">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-979">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-979"></span></span>|
|<span data-ttu-id="4d401-980">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-981">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-981"></span></span>|
|<span data-ttu-id="4d401-982">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-983">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-983"></span></span>|
|<span data-ttu-id="4d401-984">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-984">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-985">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-985"></span></span>|
|<span data-ttu-id="4d401-986">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-987">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-987"></span></span>|
|<span data-ttu-id="4d401-988">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-989">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-989"></span></span>|
|<span data-ttu-id="4d401-990">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-991">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-991"></span></span>|
|<span data-ttu-id="4d401-992">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-993">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-993"></span></span>|
|<span data-ttu-id="4d401-994">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-995">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-995"></span></span>|
|<span data-ttu-id="4d401-996">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-996">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-997">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-997"></span></span>|
|<span data-ttu-id="4d401-998">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-999">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-999"></span></span>|
   
 <span data-ttu-id="4d401-1000">**Microsoft IT TLS CA 5**</span><span class="sxs-lookup"><span data-stu-id="4d401-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-1001">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-1001">**Subject**</span></span>|
|<span data-ttu-id="4d401-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1002"></span></span>|
|<span data-ttu-id="4d401-1003">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-1003">**Issuer**</span></span>|
|<span data-ttu-id="4d401-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1004"></span></span>|
|<span data-ttu-id="4d401-1005">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-1005">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1006"></span></span>|
|<span data-ttu-id="4d401-1007">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1008"></span></span>|
|<span data-ttu-id="4d401-1009">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1010"></span></span>|
|<span data-ttu-id="4d401-1011">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1012"></span></span>|
|<span data-ttu-id="4d401-1013">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1014"></span></span>|
|<span data-ttu-id="4d401-1015">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1016"></span></span>|
|<span data-ttu-id="4d401-1017">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1018"></span></span>|
|<span data-ttu-id="4d401-1019">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1020"></span></span>|
|<span data-ttu-id="4d401-1021">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1022"></span></span>|
|<span data-ttu-id="4d401-1023">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1024"></span></span>|
|<span data-ttu-id="4d401-1025">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1026"></span></span>|
|<span data-ttu-id="4d401-1027">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1028"></span></span>|
   
 <span data-ttu-id="4d401-1029">**Symantec 類別 3 EV SSL CA G3**</span><span class="sxs-lookup"><span data-stu-id="4d401-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-1030">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-1030">**Subject**</span></span>|
|<span data-ttu-id="4d401-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1031"></span></span>|
|<span data-ttu-id="4d401-1032">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-1032">**Issuer**</span></span>|
|<span data-ttu-id="4d401-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1033"></span></span>|
|<span data-ttu-id="4d401-1034">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="4d401-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="4d401-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1035"></span></span>|
|<span data-ttu-id="4d401-1036">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-1036">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1037"></span></span>|
|<span data-ttu-id="4d401-1038">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1039"></span></span>|
|<span data-ttu-id="4d401-1040">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1041"></span></span>|
|<span data-ttu-id="4d401-1042">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1043"></span></span>|
|<span data-ttu-id="4d401-1044">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1045"></span></span>|
|<span data-ttu-id="4d401-1046">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1047"></span></span>|
|<span data-ttu-id="4d401-1048">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1049"></span></span>|
|<span data-ttu-id="4d401-1050">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1051"></span></span>|
|<span data-ttu-id="4d401-1052">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1053"></span></span>|
|<span data-ttu-id="4d401-1054">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1055"></span></span>|
|<span data-ttu-id="4d401-1056">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1057"></span></span>|
|<span data-ttu-id="4d401-1058">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1059"></span></span>|
   
 <span data-ttu-id="4d401-1060">**Symantec 類別 3 保護伺服器的 CA-G4**</span><span class="sxs-lookup"><span data-stu-id="4d401-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-1061">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-1061">**Subject**</span></span>|
|<span data-ttu-id="4d401-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1062"></span></span>|
|<span data-ttu-id="4d401-1063">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-1063">**Issuer**</span></span>|
|<span data-ttu-id="4d401-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1064"></span></span>|
|<span data-ttu-id="4d401-1065">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="4d401-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="4d401-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1066"></span></span>|
|<span data-ttu-id="4d401-1067">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-1067">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1068"></span></span>|
|<span data-ttu-id="4d401-1069">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1070"></span></span>|
|<span data-ttu-id="4d401-1071">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1072"></span></span>|
|<span data-ttu-id="4d401-1073">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1074"></span></span>|
|<span data-ttu-id="4d401-1075">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1076"></span></span>|
|<span data-ttu-id="4d401-1077">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1078"></span></span>|
|<span data-ttu-id="4d401-1079">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1080"></span></span>|
|<span data-ttu-id="4d401-1081">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1082"></span></span>|
|<span data-ttu-id="4d401-1083">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1084"></span></span>|
|<span data-ttu-id="4d401-1085">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1086"></span></span>|
|<span data-ttu-id="4d401-1087">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1088"></span></span>|
|<span data-ttu-id="4d401-1089">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1090"></span></span>|
   
 <span data-ttu-id="4d401-1091">**thawte SHA256 SSL CA**</span><span class="sxs-lookup"><span data-stu-id="4d401-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-1092">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-1092">**Subject**</span></span>|
|<span data-ttu-id="4d401-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1093"></span></span>|
|<span data-ttu-id="4d401-1094">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-1094">**Issuer**</span></span>|
|<span data-ttu-id="4d401-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1095"></span></span>|
|<span data-ttu-id="4d401-1096">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="4d401-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="4d401-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1097"></span></span>|
|<span data-ttu-id="4d401-1098">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-1098">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1099"></span></span>|
|<span data-ttu-id="4d401-1100">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1101"></span></span>|
|<span data-ttu-id="4d401-1102">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1103"></span></span>|
|<span data-ttu-id="4d401-1104">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1105"></span></span>|
|<span data-ttu-id="4d401-1106">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1107"></span></span>|
|<span data-ttu-id="4d401-1108">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1109"></span></span>|
|<span data-ttu-id="4d401-1110">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1111"></span></span>|
|<span data-ttu-id="4d401-1112">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1113"></span></span>|
|<span data-ttu-id="4d401-1114">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1115"></span></span>|
|<span data-ttu-id="4d401-1116">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1117"></span></span>|
|<span data-ttu-id="4d401-1118">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1119"></span></span>|
|<span data-ttu-id="4d401-1120">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1121"></span></span>|
   
 <span data-ttu-id="4d401-1122">**Verizon Akamai SureServer CA G14 SHA2**</span><span class="sxs-lookup"><span data-stu-id="4d401-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="4d401-1123">**主體**</span><span class="sxs-lookup"><span data-stu-id="4d401-1123">**Subject**</span></span>|
|<span data-ttu-id="4d401-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1124"></span></span>|
|<span data-ttu-id="4d401-1125">**發行者**</span><span class="sxs-lookup"><span data-stu-id="4d401-1125">**Issuer**</span></span>|
|<span data-ttu-id="4d401-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1126"></span></span>|
|<span data-ttu-id="4d401-1127">**序號**</span><span class="sxs-lookup"><span data-stu-id="4d401-1127">**Serial Number**</span></span>|
|<span data-ttu-id="4d401-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1128"></span></span>|
|<span data-ttu-id="4d401-1129">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="4d401-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="4d401-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1130"></span></span>|
|<span data-ttu-id="4d401-1131">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="4d401-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="4d401-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1132"></span></span>|
|<span data-ttu-id="4d401-1133">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="4d401-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1134"></span></span>|
|<span data-ttu-id="4d401-1135">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="4d401-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="4d401-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1136"></span></span>|
|<span data-ttu-id="4d401-1137">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="4d401-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1138"></span></span>|
|<span data-ttu-id="4d401-1139">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="4d401-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="4d401-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1140"></span></span>|
|<span data-ttu-id="4d401-1141">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="4d401-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1142"></span></span>|
|<span data-ttu-id="4d401-1143">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1144"></span></span>|
|<span data-ttu-id="4d401-1145">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="4d401-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="4d401-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1146"></span></span>|
|<span data-ttu-id="4d401-1147">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="4d401-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1148"></span></span>|
|<span data-ttu-id="4d401-1149">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="4d401-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1150"></span></span>|
|<span data-ttu-id="4d401-1151">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="4d401-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="4d401-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="4d401-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="4d401-1153">其他憑證路徑</span><span class="sxs-lookup"><span data-stu-id="4d401-1153">Additional certificate paths</span></span>
<span data-ttu-id="4d401-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="4d401-1154"></span></span>

<span data-ttu-id="4d401-1155">下列包含舊版的憑證未含上方並將與上述清單合併一段時間。</span><span class="sxs-lookup"><span data-stu-id="4d401-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
```
evsecure-aia.verisign.com
sa.symcb.com
sd.symcb.com
*.omniroot.com
*.verisign.com
*.symcb.com
*.symcd.com
*.verisign.net
*.geotrust.com
*.entrust.net
*.public-trust.com
EVIntl-ocsp.verisign.com
EVSecure-ocsp.verisign.com
isrg.trustid.ocsp.identrust.com
ocsp.digicert.com
ocsp.entrust.net
ocsp.globalsign.com/ExtendedSSLSHA256CACross
ocsp.globalsign.com/rootr1
ocsp.globalsign.com/rootr2
ocsp2.globalsign.com/rootr3
ocsp.int-x3.letsencrypt.org/
ocsp.msocsp.com
ocsp.omniroot.com/baltimoreroot
ocsp2.globalsign.com/gsextendvalsha2g3r3
ocsp2.globalsign.com/gsorganizationvalsha2g2
ocsp2.globalsign.com/gsorganizationvalsha2g3
ocsp2.globalsign.com/rootr3
ocspx.digicert.com
s2.symcb.com
sr.symcd.com
su.symcd.com
vassg142.ocsp.omniroot.com
cdp1.public-trust.com/CRL/Omniroot2025.crl
crl.entrust.net/2048ca.crl
crl.entrust.net/g2ca.crl
crl.entrust.net/level1k.crl
crl.entrust.net/rootca1.crl
crl.globalsign.com/gs/gsextendvalsha2g3r3.crl
crl.globalsign.com/gs/gsorganizationvalsha2g2.crl
crl.globalsign.com/gsorganizationvalsha2g3.crl
crl.globalsign.com/root.crl
crl.globalsign.net/root-r2.crl
crl.globalsign.com/root-r3.crl
crl.globalsign.net/root.crl
crl.identrust.com/DSTROOTCAX3CRL.crl
crl.microsoft.com/pki/mscorp/crl/msitwww1.crl
crl.microsoft.com/pki/mscorp/crl/msitwww2.crl
crl3.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl3.digicert.com/DigiCertGlobalRootCA.crl
crl3.digicert.com/sha2-ev-server-g1.crl
crl3.digicert.com/sha2-ha-server-g5.crl
crl3.digicert.com/ssca-sha2-g5.crl
crl4.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl4.digicert.com/DigiCertGlobalRootCA.crl
crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl
crl4.digicert.com/sha2-ev-server-g1.crl
crl4.digicert.com/sha2-ha-server-g5.crl
crl4.digicert.com/ssca-sha2-g5.crl
EVIntl-crl.verisign.com/EVIntl2006.crl
EVSecure-crl.verisign.com/pca3-g5.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww1.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww2.crl
s1.symcb.com/pca3-g5.crl
sr.symcb.com/sr.crl
su.symcb.com/su.crl
vassg142.crl.omniroot.com/vassg142.crl
aia.entrust.net/l1k-chain256.cer
apps.identrust.com/roots/dstrootcax3.p7c
https://cacert.a.omniroot.com/vassg142.crt
https://cacert.a.omniroot.com/vassg142.der
https://cacert.omniroot.com/baltimoreroot.crt
https://cacert.omniroot.com/baltimoreroot.der
cacerts.digicert.com/DigiCertCloudServicesCA-1.crt
cacerts.digicert.com/DigiCertSHA2ExtendedValidationServerCA.crt
cacerts.digicert.com/DigiCertSHA2HighAssuranceServerCA.crt
cacerts.digicert.com/DigiCertSHA2SecureServerCA.crt
cert.int-x3.letsencrypt.org/
EVIntl-aia.verisign.com/EVIntl2006.cer
secure.globalsign.com/cacert/gsextendvalsha2g2r2.crt
secure.globalsign.com/cacert/gsextendvalsha2g3r3.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g2r1.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g3.crt
sr.symcb.com/sr.crt
su.symcb.com/su.crt
https://www.digicert.com/CACerts/DigiCertGlobalRootCA.crt
https://www.digicert.com/CACerts/DigiCertHighAssuranceEVRootCA.crt
www.microsoft.com/pki/mscorp/msitwww1.crt
www.microsoft.com/pki/mscorp/msitwww2.crt

```


