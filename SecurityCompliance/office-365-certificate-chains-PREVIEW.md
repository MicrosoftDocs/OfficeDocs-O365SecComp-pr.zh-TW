---
title: Office 365 憑證鏈結
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.assetid: 0c03e6b3-e73f-4316-9e2b-bf4091ae96bb
description: Office 365 如何運用不同的憑證提供者的數目。下面會說明客戶存取 Office 365 時可能會遇到的已知 Office 365 根憑證的完整清單。如需憑證的資訊可能必須安裝在您自己的基礎結構，請參閱 Office 365 的規劃第三方 SSL 憑證。下列的憑證資訊適用於所有的 Office 365 的全球和雲端執行個體。
ms.openlocfilehash: 97e00833e57f8f6b7352650b0efdef51ddba77fa
ms.sourcegitcommit: 659b5f5b38ef7e838cdb44eaa38c18e48d922768
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2018
ms.locfileid: "25575357"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="73140-106">Office 365 憑證鏈結</span><span class="sxs-lookup"><span data-stu-id="73140-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="73140-p102">Office 365 如何運用不同的憑證提供者的數目。下面會說明客戶存取 Office 365 時可能會遇到的已知 Office 365 根憑證的完整清單。在憑證上的資訊可能需要將安裝在您自己的基礎結構中，請參閱[第三方 SSL 憑證的 Office 365 計劃](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce)。下列的憑證資訊適用於所有的 Office 365 的全球和雲端執行個體。</span><span class="sxs-lookup"><span data-stu-id="73140-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="73140-111">**憑證類型**</span><span class="sxs-lookup"><span data-stu-id="73140-111">**Certificate type**</span></span>|<span data-ttu-id="73140-112">**P7b 下載 （英文）**</span><span class="sxs-lookup"><span data-stu-id="73140-112">**P7b download**</span></span>|<span data-ttu-id="73140-113">**CRL 端點**</span><span class="sxs-lookup"><span data-stu-id="73140-113">**CRL Endpoints**</span></span>|<span data-ttu-id="73140-114">**OCSP 端點**</span><span class="sxs-lookup"><span data-stu-id="73140-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="73140-115">**AIA 端點**</span><span class="sxs-lookup"><span data-stu-id="73140-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="73140-116">公開受信任的根憑證</span><span class="sxs-lookup"><span data-stu-id="73140-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="73140-117">Office 365 根憑證組合 (P7B)</span><span class="sxs-lookup"><span data-stu-id="73140-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="73140-118">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="73140-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="73140-119">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="73140-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="73140-120">不適用</span><span class="sxs-lookup"><span data-stu-id="73140-120">N/A</span></span>  <br/> |<span data-ttu-id="73140-121">不適用</span><span class="sxs-lookup"><span data-stu-id="73140-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="73140-122">公開信任中繼憑證</span><span class="sxs-lookup"><span data-stu-id="73140-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="73140-123">Office 365 中繼憑證組合 (P7B)</span><span class="sxs-lookup"><span data-stu-id="73140-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="73140-124">cdp1.public trust.com</span><span class="sxs-lookup"><span data-stu-id="73140-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="73140-125">crl.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="73140-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="73140-126">crl.entrust.net</span><span class="sxs-lookup"><span data-stu-id="73140-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="73140-127">crl.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="73140-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="73140-128">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="73140-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="73140-129">crl.identrust.com</span><span class="sxs-lookup"><span data-stu-id="73140-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="73140-130">crl.thawte.com</span><span class="sxs-lookup"><span data-stu-id="73140-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="73140-131">crl3.digicert.com</span><span class="sxs-lookup"><span data-stu-id="73140-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="73140-132">crl4.digicert.com</span><span class="sxs-lookup"><span data-stu-id="73140-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="73140-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="73140-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="73140-134">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="73140-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="73140-135">isrg.trustid.ocsp.identrust.com</span><span class="sxs-lookup"><span data-stu-id="73140-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="73140-136">ocsp.digicert.com</span><span class="sxs-lookup"><span data-stu-id="73140-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="73140-137">ocsp.entrust.net</span><span class="sxs-lookup"><span data-stu-id="73140-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="73140-138">ocsp.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="73140-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="73140-139">ocsp.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="73140-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="73140-140">ocsp.startssl.com</span><span class="sxs-lookup"><span data-stu-id="73140-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="73140-141">ocsp.thawte.com</span><span class="sxs-lookup"><span data-stu-id="73140-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="73140-142">ocsp2.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="73140-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="73140-143">ocspcnnicroot.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="73140-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="73140-144">根-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="73140-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="73140-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="73140-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="73140-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="73140-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="73140-147">aia.startssl.com</span><span class="sxs-lookup"><span data-stu-id="73140-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="73140-148">apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="73140-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="73140-149">cacert.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="73140-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="73140-150">www.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="73140-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="73140-151">展開根目錄與以下以查看憑證提供者相關的其他詳細資料的中階章節。</span><span class="sxs-lookup"><span data-stu-id="73140-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="73140-152">Office 365 根憑證的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="73140-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="73140-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="73140-153"></span></span>

 <span data-ttu-id="73140-154">**Baltimore CyberTrust Root**</span><span class="sxs-lookup"><span data-stu-id="73140-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="73140-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="73140-155">|:-----|</span></span>
|<span data-ttu-id="73140-156">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="73140-157">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-157">**Serial Number**</span></span>|
|<span data-ttu-id="73140-158">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-158"></span></span>|
|<span data-ttu-id="73140-159">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-159">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-160">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-160"></span></span>|
|<span data-ttu-id="73140-161">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-162">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-162"></span></span>|
|<span data-ttu-id="73140-163">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-164">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-164"></span></span>|
|<span data-ttu-id="73140-165">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-165">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-166">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-166"></span></span>|
|<span data-ttu-id="73140-167">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-168">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-168"></span></span>|
|<span data-ttu-id="73140-169">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-170">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-170"></span></span>|
|<span data-ttu-id="73140-171">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-172">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-172"></span></span>|
|<span data-ttu-id="73140-173">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-174">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-174"></span></span>|
   
 <span data-ttu-id="73140-175">**CNNIC 根目錄**</span><span class="sxs-lookup"><span data-stu-id="73140-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-176">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-176">**Subject**</span></span>|
|<span data-ttu-id="73140-177">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-177"></span></span>|
|<span data-ttu-id="73140-178">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-178">**Serial Number**</span></span>|
|<span data-ttu-id="73140-179">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-179"></span></span>|
|<span data-ttu-id="73140-180">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-180">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-181">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-181"></span></span>|
|<span data-ttu-id="73140-182">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-183">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-183"></span></span>|
|<span data-ttu-id="73140-184">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-185">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-185"></span></span>|
|<span data-ttu-id="73140-186">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-186">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-187">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-187"></span></span>|
|<span data-ttu-id="73140-188">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-189">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-189"></span></span>|
|<span data-ttu-id="73140-190">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-191">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-191"></span></span>|
|<span data-ttu-id="73140-192">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-193">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-193"></span></span>|
|<span data-ttu-id="73140-194">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-195">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-195"></span></span>|
|<span data-ttu-id="73140-196">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-197">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-197"></span></span>|
   
 <span data-ttu-id="73140-198">**DigiCert 通用的根 CA**</span><span class="sxs-lookup"><span data-stu-id="73140-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-199">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-199">**Subject**</span></span>|
|<span data-ttu-id="73140-200">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-200"></span></span>|
|<span data-ttu-id="73140-201">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-201">**Serial Number**</span></span>|
|<span data-ttu-id="73140-202">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-202"></span></span>|
|<span data-ttu-id="73140-203">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-203">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-204">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-204"></span></span>|
|<span data-ttu-id="73140-205">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-206">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-206"></span></span>|
|<span data-ttu-id="73140-207">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-208">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-208"></span></span>|
|<span data-ttu-id="73140-209">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-209">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-210">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-210"></span></span>|
|<span data-ttu-id="73140-211">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-212">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-212"></span></span>|
|<span data-ttu-id="73140-213">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-214">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-214"></span></span>|
|<span data-ttu-id="73140-215">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-216">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-216"></span></span>|
|<span data-ttu-id="73140-217">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-218">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-218"></span></span>|
|<span data-ttu-id="73140-219">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-220">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-220"></span></span>|
   
 <span data-ttu-id="73140-221">**DigiCert 高保證 EV 根 CA**</span><span class="sxs-lookup"><span data-stu-id="73140-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-222">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-222">**Subject**</span></span>|
|<span data-ttu-id="73140-223">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-223"></span></span>|
|<span data-ttu-id="73140-224">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-224">**Serial Number**</span></span>|
|<span data-ttu-id="73140-225">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-225"></span></span>|
|<span data-ttu-id="73140-226">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-226">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-227">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-227"></span></span>|
|<span data-ttu-id="73140-228">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-229">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-229"></span></span>|
|<span data-ttu-id="73140-230">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-231">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-231"></span></span>|
|<span data-ttu-id="73140-232">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-232">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-233">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-233"></span></span>|
|<span data-ttu-id="73140-234">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-235">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-235"></span></span>|
|<span data-ttu-id="73140-236">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-237">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-237"></span></span>|
|<span data-ttu-id="73140-238">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-239">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-239"></span></span>|
|<span data-ttu-id="73140-240">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-241">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-241"></span></span>|
|<span data-ttu-id="73140-242">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-243">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-243"></span></span>|
   
 <span data-ttu-id="73140-244">**D 信任根類別 3 CA 2 2009**</span><span class="sxs-lookup"><span data-stu-id="73140-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-245">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-245">**Subject**</span></span>|
|<span data-ttu-id="73140-246">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-246"></span></span>|
|<span data-ttu-id="73140-247">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-247">**Serial Number**</span></span>|
|<span data-ttu-id="73140-248">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-248"></span></span>|
|<span data-ttu-id="73140-249">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-249">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-250">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-250"></span></span>|
|<span data-ttu-id="73140-251">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-252">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-252"></span></span>|
|<span data-ttu-id="73140-253">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-254">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-254"></span></span>|
|<span data-ttu-id="73140-255">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-255">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-256">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-256"></span></span>|
|<span data-ttu-id="73140-257">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-258">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-258"></span></span>|
|<span data-ttu-id="73140-259">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-260">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-260"></span></span>|
|<span data-ttu-id="73140-261">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-262">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-262"></span></span>|
|<span data-ttu-id="73140-263">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-264">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-264"></span></span>|
|<span data-ttu-id="73140-265">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-265">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-266">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-266"></span></span>|
   
 <span data-ttu-id="73140-267">**D 信任根類別 3 CA 2 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="73140-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-268">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-268">**Subject**</span></span>|
|<span data-ttu-id="73140-269">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-269"></span></span>|
|<span data-ttu-id="73140-270">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-270">**Serial Number**</span></span>|
|<span data-ttu-id="73140-271">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-271"></span></span>|
|<span data-ttu-id="73140-272">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-272">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-273">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-273"></span></span>|
|<span data-ttu-id="73140-274">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-275">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-275"></span></span>|
|<span data-ttu-id="73140-276">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-277">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-277"></span></span>|
|<span data-ttu-id="73140-278">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-278">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-279">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-279"></span></span>|
|<span data-ttu-id="73140-280">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-281">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-281"></span></span>|
|<span data-ttu-id="73140-282">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-283">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-283"></span></span>|
|<span data-ttu-id="73140-284">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-285">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-285"></span></span>|
|<span data-ttu-id="73140-286">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-287">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-287"></span></span>|
|<span data-ttu-id="73140-288">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-288">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-289">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-289"></span></span>|
   
 <span data-ttu-id="73140-290">**DST 根 CA X3**</span><span class="sxs-lookup"><span data-stu-id="73140-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-291">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-291">**Subject**</span></span>|
|<span data-ttu-id="73140-292">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-292"></span></span>|
|<span data-ttu-id="73140-293">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-293">**Serial Number**</span></span>|
|<span data-ttu-id="73140-294">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-294"></span></span>|
|<span data-ttu-id="73140-295">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-295">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-296">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-296"></span></span>|
|<span data-ttu-id="73140-297">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-298">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-298"></span></span>|
|<span data-ttu-id="73140-299">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-300">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-300"></span></span>|
|<span data-ttu-id="73140-301">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-301">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-302">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-302"></span></span>|
|<span data-ttu-id="73140-303">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-304">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-304"></span></span>|
|<span data-ttu-id="73140-305">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-306">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-306"></span></span>|
|<span data-ttu-id="73140-307">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-308">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-308"></span></span>|
|<span data-ttu-id="73140-309">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-310">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-310"></span></span>|
   
 <span data-ttu-id="73140-311">**過程錄影根憑證授權單位-G2**</span><span class="sxs-lookup"><span data-stu-id="73140-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-312">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-312">**Subject**</span></span>|
|<span data-ttu-id="73140-313">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-313"></span></span>|
|<span data-ttu-id="73140-314">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-314">**Serial Number**</span></span>|
|<span data-ttu-id="73140-315">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-315"></span></span>|
|<span data-ttu-id="73140-316">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-316">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-317">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-317"></span></span>|
|<span data-ttu-id="73140-318">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-319">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-319"></span></span>|
|<span data-ttu-id="73140-320">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-321">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-321"></span></span>|
|<span data-ttu-id="73140-322">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-322">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-323">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-323"></span></span>|
|<span data-ttu-id="73140-324">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-325">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-325"></span></span>|
|<span data-ttu-id="73140-326">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-327">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-327"></span></span>|
|<span data-ttu-id="73140-328">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-329">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-329"></span></span>|
|<span data-ttu-id="73140-330">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-331">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-331"></span></span>|
   
 <span data-ttu-id="73140-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="73140-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-333">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-333">**Subject**</span></span>|
|<span data-ttu-id="73140-334">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-334"></span></span>|
|<span data-ttu-id="73140-335">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-335">**Serial Number**</span></span>|
|<span data-ttu-id="73140-336">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-336"></span></span>|
|<span data-ttu-id="73140-337">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-337">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-338">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-338"></span></span>|
|<span data-ttu-id="73140-339">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-340">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-340"></span></span>|
|<span data-ttu-id="73140-341">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-342">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-342"></span></span>|
|<span data-ttu-id="73140-343">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-343">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-344">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-344"></span></span>|
|<span data-ttu-id="73140-345">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-346">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-346"></span></span>|
|<span data-ttu-id="73140-347">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-348">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-348"></span></span>|
|<span data-ttu-id="73140-349">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-350">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-350"></span></span>|
|<span data-ttu-id="73140-351">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-352">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-352"></span></span>|
   
 <span data-ttu-id="73140-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="73140-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-354">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-354">**Subject**</span></span>|
|<span data-ttu-id="73140-355">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-355"></span></span>|
|<span data-ttu-id="73140-356">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-356">**Serial Number**</span></span>|
|<span data-ttu-id="73140-357">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-357"></span></span>|
|<span data-ttu-id="73140-358">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-358">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-359">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-359"></span></span>|
|<span data-ttu-id="73140-360">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-361">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-361"></span></span>|
|<span data-ttu-id="73140-362">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-363">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-363"></span></span>|
|<span data-ttu-id="73140-364">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-364">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-365">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-365"></span></span>|
|<span data-ttu-id="73140-366">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-367">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-367"></span></span>|
|<span data-ttu-id="73140-368">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-369">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-369"></span></span>|
|<span data-ttu-id="73140-370">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-371">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-371"></span></span>|
|<span data-ttu-id="73140-372">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-373">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-373"></span></span>|
|<span data-ttu-id="73140-374">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-375">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-375"></span></span>|
|<span data-ttu-id="73140-376">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-376">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-377">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-377"></span></span>|
   
 <span data-ttu-id="73140-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="73140-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-379">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-379">**Subject**</span></span>|
|<span data-ttu-id="73140-380">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-380"></span></span>|
|<span data-ttu-id="73140-381">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-381">**Serial Number**</span></span>|
|<span data-ttu-id="73140-382">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-382"></span></span>|
|<span data-ttu-id="73140-383">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-383">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-384">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-384"></span></span>|
|<span data-ttu-id="73140-385">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-386">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-386"></span></span>|
|<span data-ttu-id="73140-387">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-388">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-388"></span></span>|
|<span data-ttu-id="73140-389">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-389">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-390">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-390"></span></span>|
|<span data-ttu-id="73140-391">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-392">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-392"></span></span>|
|<span data-ttu-id="73140-393">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-394">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-394"></span></span>|
|<span data-ttu-id="73140-395">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-396">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-396"></span></span>|
|<span data-ttu-id="73140-397">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-398">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-398"></span></span>|
   
 <span data-ttu-id="73140-399">**thawte 主要的根 CA-G3**</span><span class="sxs-lookup"><span data-stu-id="73140-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-400">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-400">**Subject**</span></span>|
|<span data-ttu-id="73140-401">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-401"></span></span>|
|<span data-ttu-id="73140-402">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-402">**Serial Number**</span></span>|
|<span data-ttu-id="73140-403">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-403"></span></span>|
|<span data-ttu-id="73140-404">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-404">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-405">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-405"></span></span>|
|<span data-ttu-id="73140-406">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-407">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-407"></span></span>|
|<span data-ttu-id="73140-408">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-409">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-409"></span></span>|
|<span data-ttu-id="73140-410">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-410">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-411">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-411"></span></span>|
|<span data-ttu-id="73140-412">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-413">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-413"></span></span>|
|<span data-ttu-id="73140-414">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-415">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-415"></span></span>|
|<span data-ttu-id="73140-416">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-417">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-417"></span></span>|
|<span data-ttu-id="73140-418">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-419">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-419"></span></span>|
   
 <span data-ttu-id="73140-420">**VeriSign 類別 3 主要的公用憑證授權單位-G5**</span><span class="sxs-lookup"><span data-stu-id="73140-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-421">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-421">**Subject**</span></span>|
|<span data-ttu-id="73140-422">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-422"></span></span>|
|<span data-ttu-id="73140-423">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-423">**Serial Number**</span></span>|
|<span data-ttu-id="73140-424">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-424"></span></span>|
|<span data-ttu-id="73140-425">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-425">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-426">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-426"></span></span>|
|<span data-ttu-id="73140-427">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-428">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-428"></span></span>|
|<span data-ttu-id="73140-429">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-430">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-430"></span></span>|
|<span data-ttu-id="73140-431">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-431">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-432">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-432"></span></span>|
|<span data-ttu-id="73140-433">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-434">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-434"></span></span>|
|<span data-ttu-id="73140-435">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-436">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-436"></span></span>|
|<span data-ttu-id="73140-437">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-438">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-438"></span></span>|
|<span data-ttu-id="73140-439">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-440">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="73140-441">Office 365 中繼憑證的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="73140-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="73140-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="73140-442"></span></span>

 <span data-ttu-id="73140-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="73140-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-444">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-444">**Subject**</span></span>|
|<span data-ttu-id="73140-445">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-445"></span></span>|
|<span data-ttu-id="73140-446">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-446">**Issuer**</span></span>|
|<span data-ttu-id="73140-447">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-447"></span></span>|
|<span data-ttu-id="73140-448">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-448">**Serial Number**</span></span>|
|<span data-ttu-id="73140-449">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-449"></span></span>|
|<span data-ttu-id="73140-450">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-450">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-451">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-451"></span></span>|
|<span data-ttu-id="73140-452">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-453">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-453"></span></span>|
|<span data-ttu-id="73140-454">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-455">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-455"></span></span>|
|<span data-ttu-id="73140-456">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-456">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-457">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-457"></span></span>|
|<span data-ttu-id="73140-458">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-459">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-459"></span></span>|
|<span data-ttu-id="73140-460">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-461">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-461"></span></span>|
|<span data-ttu-id="73140-462">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-463">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-463"></span></span>|
|<span data-ttu-id="73140-464">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-465">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-465"></span></span>|
|<span data-ttu-id="73140-466">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-467">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-467"></span></span>|
|<span data-ttu-id="73140-468">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="73140-468">**AIA URLs**</span></span>|
|<span data-ttu-id="73140-469">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-469"></span></span>|
|<span data-ttu-id="73140-470">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-470">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-471">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-471"></span></span>|
|<span data-ttu-id="73140-472">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-473">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-473"></span></span>|
   
 <span data-ttu-id="73140-474">**D 信任 SSL 類別 3 CA 1 2009**</span><span class="sxs-lookup"><span data-stu-id="73140-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-475">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-475">**Subject**</span></span>|
|<span data-ttu-id="73140-476">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-476"></span></span>|
|<span data-ttu-id="73140-477">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-477">**Issuer**</span></span>|
|<span data-ttu-id="73140-478">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-478"></span></span>|
|<span data-ttu-id="73140-479">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="73140-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="73140-480">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-480"></span></span>|
|<span data-ttu-id="73140-481">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-481">**Serial Number**</span></span>|
|<span data-ttu-id="73140-482">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-482"></span></span>|
|<span data-ttu-id="73140-483">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-483">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-484">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-484"></span></span>|
|<span data-ttu-id="73140-485">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-486">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-486"></span></span>|
|<span data-ttu-id="73140-487">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-488">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-488"></span></span>|
|<span data-ttu-id="73140-489">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-489">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-490">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-490"></span></span>|
|<span data-ttu-id="73140-491">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-492">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-492"></span></span>|
|<span data-ttu-id="73140-493">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-494">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-494"></span></span>|
|<span data-ttu-id="73140-495">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-496">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-496"></span></span>|
|<span data-ttu-id="73140-497">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-498">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-498"></span></span>|
|<span data-ttu-id="73140-499">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-500">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-500"></span></span>|
|<span data-ttu-id="73140-501">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-501">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-502">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-502"></span></span>|
|<span data-ttu-id="73140-503">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-504">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-504"></span></span>|
   
 <span data-ttu-id="73140-505">**D 信任 SSL 類別 3 CA 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="73140-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-506">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-506">**Subject**</span></span>|
|<span data-ttu-id="73140-507">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-507"></span></span>|
|<span data-ttu-id="73140-508">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-508">**Issuer**</span></span>|
|<span data-ttu-id="73140-509">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-509"></span></span>|
|<span data-ttu-id="73140-510">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="73140-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="73140-511">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-511"></span></span>|
|<span data-ttu-id="73140-512">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-512">**Serial Number**</span></span>|
|<span data-ttu-id="73140-513">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-513"></span></span>|
|<span data-ttu-id="73140-514">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-514">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-515">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-515"></span></span>|
|<span data-ttu-id="73140-516">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-517">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-517"></span></span>|
|<span data-ttu-id="73140-518">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-519">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-519"></span></span>|
|<span data-ttu-id="73140-520">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-520">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-521">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-521"></span></span>|
|<span data-ttu-id="73140-522">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-523">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-523"></span></span>|
|<span data-ttu-id="73140-524">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-525">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-525"></span></span>|
|<span data-ttu-id="73140-526">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-527">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-527"></span></span>|
|<span data-ttu-id="73140-528">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-529">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-529"></span></span>|
|<span data-ttu-id="73140-530">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-531">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-531"></span></span>|
|<span data-ttu-id="73140-532">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-532">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-533">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-533"></span></span>|
|<span data-ttu-id="73140-534">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-535">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-535"></span></span>|
   
 <span data-ttu-id="73140-536">**DigiCert 雲端服務 CA-1**</span><span class="sxs-lookup"><span data-stu-id="73140-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-537">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-537">**Subject**</span></span>|
|<span data-ttu-id="73140-538">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-538"></span></span>|
|<span data-ttu-id="73140-539">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-539">**Issuer**</span></span>|
|<span data-ttu-id="73140-540">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-540"></span></span>|
|<span data-ttu-id="73140-541">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-541">**Serial Number**</span></span>|
|<span data-ttu-id="73140-542">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-542"></span></span>|
|<span data-ttu-id="73140-543">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-543">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-544">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-544"></span></span>|
|<span data-ttu-id="73140-545">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-546">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-546"></span></span>|
|<span data-ttu-id="73140-547">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-548">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-548"></span></span>|
|<span data-ttu-id="73140-549">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-549">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-550">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-550"></span></span>|
|<span data-ttu-id="73140-551">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-552">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-552"></span></span>|
|<span data-ttu-id="73140-553">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-554">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-554"></span></span>|
|<span data-ttu-id="73140-555">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-556">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-556"></span></span>|
|<span data-ttu-id="73140-557">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-558">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-558"></span></span>|
|<span data-ttu-id="73140-559">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-560">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-560"></span></span>|
|<span data-ttu-id="73140-561">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-561">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-562">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-562"></span></span>|
|<span data-ttu-id="73140-563">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-564">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-564"></span></span>|
   
 <span data-ttu-id="73140-565">**DigiCert SHA2 高保證伺服器 CA**</span><span class="sxs-lookup"><span data-stu-id="73140-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-566">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-566">**Subject**</span></span>|
|<span data-ttu-id="73140-567">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-567"></span></span>|
|<span data-ttu-id="73140-568">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-568">**Issuer**</span></span>|
|<span data-ttu-id="73140-569">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-569"></span></span>|
|<span data-ttu-id="73140-570">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-570">**Serial Number**</span></span>|
|<span data-ttu-id="73140-571">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-571"></span></span>|
|<span data-ttu-id="73140-572">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-572">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-573">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-573"></span></span>|
|<span data-ttu-id="73140-574">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-575">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-575"></span></span>|
|<span data-ttu-id="73140-576">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-577">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-577"></span></span>|
|<span data-ttu-id="73140-578">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-578">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-579">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-579"></span></span>|
|<span data-ttu-id="73140-580">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-581">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-581"></span></span>|
|<span data-ttu-id="73140-582">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-583">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-583"></span></span>|
|<span data-ttu-id="73140-584">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-585">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-585"></span></span>|
|<span data-ttu-id="73140-586">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-587">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-587"></span></span>|
|<span data-ttu-id="73140-588">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-589">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-589"></span></span>|
|<span data-ttu-id="73140-590">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-590">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-591">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-591"></span></span>|
|<span data-ttu-id="73140-592">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-593">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-593"></span></span>|
   
 <span data-ttu-id="73140-594">**DigiCert SHA2 保護伺服器的 CA**</span><span class="sxs-lookup"><span data-stu-id="73140-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-595">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-595">**Subject**</span></span>|
|<span data-ttu-id="73140-596">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-596"></span></span>|
|<span data-ttu-id="73140-597">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-597">**Issuer**</span></span>|
|<span data-ttu-id="73140-598">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-598"></span></span>|
|<span data-ttu-id="73140-599">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-599">**Serial Number**</span></span>|
|<span data-ttu-id="73140-600">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-600"></span></span>|
|<span data-ttu-id="73140-601">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-601">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-602">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-602"></span></span>|
|<span data-ttu-id="73140-603">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-604">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-604"></span></span>|
|<span data-ttu-id="73140-605">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-606">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-606"></span></span>|
|<span data-ttu-id="73140-607">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-607">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-608">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-608"></span></span>|
|<span data-ttu-id="73140-609">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-610">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-610"></span></span>|
|<span data-ttu-id="73140-611">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-612">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-612"></span></span>|
|<span data-ttu-id="73140-613">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-614">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-614"></span></span>|
|<span data-ttu-id="73140-615">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-616">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-616"></span></span>|
|<span data-ttu-id="73140-617">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-618">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-618"></span></span>|
|<span data-ttu-id="73140-619">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-619">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-620">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-620"></span></span>|
|<span data-ttu-id="73140-621">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-622">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-622"></span></span>|
   
 <span data-ttu-id="73140-623">**過程錄影憑證授權單位-L1C**</span><span class="sxs-lookup"><span data-stu-id="73140-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-624">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-624">**Subject**</span></span>|
|<span data-ttu-id="73140-625">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-625"></span></span>|
|<span data-ttu-id="73140-626">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-626">**Issuer**</span></span>|
|<span data-ttu-id="73140-627">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-627"></span></span>|
|<span data-ttu-id="73140-628">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-628">**Serial Number**</span></span>|
|<span data-ttu-id="73140-629">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-629"></span></span>|
|<span data-ttu-id="73140-630">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-630">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-631">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-631"></span></span>|
|<span data-ttu-id="73140-632">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-633">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-633"></span></span>|
|<span data-ttu-id="73140-634">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-635">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-635"></span></span>|
|<span data-ttu-id="73140-636">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-636">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-637">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-637"></span></span>|
|<span data-ttu-id="73140-638">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-639">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-639"></span></span>|
|<span data-ttu-id="73140-640">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-641">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-641"></span></span>|
|<span data-ttu-id="73140-642">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-643">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-643"></span></span>|
|<span data-ttu-id="73140-644">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-645">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-645"></span></span>|
|<span data-ttu-id="73140-646">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-647">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-647"></span></span>|
|<span data-ttu-id="73140-648">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-648">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-649">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-649"></span></span>|
|<span data-ttu-id="73140-650">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-651">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-651"></span></span>|
   
 <span data-ttu-id="73140-652">**過程錄影憑證授權單位-L1K**</span><span class="sxs-lookup"><span data-stu-id="73140-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-653">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-653">**Subject**</span></span>|
|<span data-ttu-id="73140-654">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-654"></span></span>|
|<span data-ttu-id="73140-655">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-655">**Issuer**</span></span>|
|<span data-ttu-id="73140-656">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-656"></span></span>|
|<span data-ttu-id="73140-657">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-657">**Serial Number**</span></span>|
|<span data-ttu-id="73140-658">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-658"></span></span>|
|<span data-ttu-id="73140-659">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-659">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-660">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-660"></span></span>|
|<span data-ttu-id="73140-661">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-662">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-662"></span></span>|
|<span data-ttu-id="73140-663">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-664">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-664"></span></span>|
|<span data-ttu-id="73140-665">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-665">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-666">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-666"></span></span>|
|<span data-ttu-id="73140-667">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-668">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-668"></span></span>|
|<span data-ttu-id="73140-669">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-670">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-670"></span></span>|
|<span data-ttu-id="73140-671">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-672">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-672"></span></span>|
|<span data-ttu-id="73140-673">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-674">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-674"></span></span>|
|<span data-ttu-id="73140-675">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-676">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-676"></span></span>|
|<span data-ttu-id="73140-677">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-677">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-678">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-678"></span></span>|
|<span data-ttu-id="73140-679">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-680">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-680"></span></span>|
   
 <span data-ttu-id="73140-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="73140-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-682">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-682">**Subject**</span></span>|
|<span data-ttu-id="73140-683">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-683"></span></span>|
|<span data-ttu-id="73140-684">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-684">**Issuer**</span></span>|
|<span data-ttu-id="73140-685">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-685"></span></span>|
|<span data-ttu-id="73140-686">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-686">**Serial Number**</span></span>|
|<span data-ttu-id="73140-687">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-687"></span></span>|
|<span data-ttu-id="73140-688">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-688">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-689">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-689"></span></span>|
|<span data-ttu-id="73140-690">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-691">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-691"></span></span>|
|<span data-ttu-id="73140-692">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-693">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-693"></span></span>|
|<span data-ttu-id="73140-694">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-694">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-695">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-695"></span></span>|
|<span data-ttu-id="73140-696">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-697">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-697"></span></span>|
|<span data-ttu-id="73140-698">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-699">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-699"></span></span>|
|<span data-ttu-id="73140-700">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-701">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-701"></span></span>|
|<span data-ttu-id="73140-702">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-703">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-703"></span></span>|
|<span data-ttu-id="73140-704">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-705">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-705"></span></span>|
|<span data-ttu-id="73140-706">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-706">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-707">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-707"></span></span>|
|<span data-ttu-id="73140-708">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-709">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-709"></span></span>|
   
 <span data-ttu-id="73140-710">**GlobalSign 擴充驗證 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="73140-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-711">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-711">**Subject**</span></span>|
|<span data-ttu-id="73140-712">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-712"></span></span>|
|<span data-ttu-id="73140-713">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-713">**Issuer**</span></span>|
|<span data-ttu-id="73140-714">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-714"></span></span>|
|<span data-ttu-id="73140-715">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-715">**Serial Number**</span></span>|
|<span data-ttu-id="73140-716">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-716"></span></span>|
|<span data-ttu-id="73140-717">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-717">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-718">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-718"></span></span>|
|<span data-ttu-id="73140-719">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-720">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-720"></span></span>|
|<span data-ttu-id="73140-721">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-722">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-722"></span></span>|
|<span data-ttu-id="73140-723">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-723">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-724">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-724"></span></span>|
|<span data-ttu-id="73140-725">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-726">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-726"></span></span>|
|<span data-ttu-id="73140-727">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-728">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-728"></span></span>|
|<span data-ttu-id="73140-729">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-730">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-730"></span></span>|
|<span data-ttu-id="73140-731">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-732">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-732"></span></span>|
|<span data-ttu-id="73140-733">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-734">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-734"></span></span>|
|<span data-ttu-id="73140-735">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-735">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-736">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-736"></span></span>|
|<span data-ttu-id="73140-737">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-738">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-738"></span></span>|
   
 <span data-ttu-id="73140-739">**GlobalSign 擴充驗證 CA-SHA256-G3**</span><span class="sxs-lookup"><span data-stu-id="73140-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-740">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-740">**Subject**</span></span>|
|<span data-ttu-id="73140-741">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-741"></span></span>|
|<span data-ttu-id="73140-742">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-742">**Issuer**</span></span>|
|<span data-ttu-id="73140-743">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-743"></span></span>|
|<span data-ttu-id="73140-744">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-744">**Serial Number**</span></span>|
|<span data-ttu-id="73140-745">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-745"></span></span>|
|<span data-ttu-id="73140-746">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-746">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-747">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-747"></span></span>|
|<span data-ttu-id="73140-748">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-749">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-749"></span></span>|
|<span data-ttu-id="73140-750">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-751">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-751"></span></span>|
|<span data-ttu-id="73140-752">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-752">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-753">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-753"></span></span>|
|<span data-ttu-id="73140-754">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-755">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-755"></span></span>|
|<span data-ttu-id="73140-756">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-757">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-757"></span></span>|
|<span data-ttu-id="73140-758">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-759">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-759"></span></span>|
|<span data-ttu-id="73140-760">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-761">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-761"></span></span>|
|<span data-ttu-id="73140-762">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-763">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-763"></span></span>|
|<span data-ttu-id="73140-764">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-764">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-765">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-765"></span></span>|
|<span data-ttu-id="73140-766">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-767">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-767"></span></span>|
   
 <span data-ttu-id="73140-768">**GlobalSign 組織驗證 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="73140-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-769">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-769">**Subject**</span></span>|
|<span data-ttu-id="73140-770">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-770"></span></span>|
|<span data-ttu-id="73140-771">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-771">**Issuer**</span></span>|
|<span data-ttu-id="73140-772">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-772"></span></span>|
|<span data-ttu-id="73140-773">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-773">**Serial Number**</span></span>|
|<span data-ttu-id="73140-774">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-774"></span></span>|
|<span data-ttu-id="73140-775">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-775">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-776">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-776"></span></span>|
|<span data-ttu-id="73140-777">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-778">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-778"></span></span>|
|<span data-ttu-id="73140-779">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-780">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-780"></span></span>|
|<span data-ttu-id="73140-781">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-781">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-782">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-782"></span></span>|
|<span data-ttu-id="73140-783">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-784">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-784"></span></span>|
|<span data-ttu-id="73140-785">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-786">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-786"></span></span>|
|<span data-ttu-id="73140-787">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-788">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-788"></span></span>|
|<span data-ttu-id="73140-789">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-790">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-790"></span></span>|
|<span data-ttu-id="73140-791">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-792">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-792"></span></span>|
|<span data-ttu-id="73140-793">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-793">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-794">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-794"></span></span>|
|<span data-ttu-id="73140-795">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-796">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-796"></span></span>|
   
 <span data-ttu-id="73140-797">**GlobalSign 組織驗證 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="73140-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-798">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-798">**Subject**</span></span>|
|<span data-ttu-id="73140-799">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-799"></span></span>|
|<span data-ttu-id="73140-800">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-800">**Issuer**</span></span>|
|<span data-ttu-id="73140-801">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-801"></span></span>|
|<span data-ttu-id="73140-802">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-802">**Serial Number**</span></span>|
|<span data-ttu-id="73140-803">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-803"></span></span>|
|<span data-ttu-id="73140-804">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-804">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-805">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-805"></span></span>|
|<span data-ttu-id="73140-806">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-807">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-807"></span></span>|
|<span data-ttu-id="73140-808">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-809">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-809"></span></span>|
|<span data-ttu-id="73140-810">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-810">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-811">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-811"></span></span>|
|<span data-ttu-id="73140-812">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-813">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-813"></span></span>|
|<span data-ttu-id="73140-814">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-815">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-815"></span></span>|
|<span data-ttu-id="73140-816">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-817">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-817"></span></span>|
|<span data-ttu-id="73140-818">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-819">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-819"></span></span>|
|<span data-ttu-id="73140-820">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-821">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-821"></span></span>|
|<span data-ttu-id="73140-822">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-822">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-823">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-823"></span></span>|
|<span data-ttu-id="73140-824">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-825">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-825"></span></span>|
   
 <span data-ttu-id="73140-826">**我們加密授權 X3**</span><span class="sxs-lookup"><span data-stu-id="73140-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-827">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-827">**Subject**</span></span>|
|<span data-ttu-id="73140-828">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-828"></span></span>|
|<span data-ttu-id="73140-829">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-829">**Issuer**</span></span>|
|<span data-ttu-id="73140-830">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-830"></span></span>|
|<span data-ttu-id="73140-831">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-831">**Serial Number**</span></span>|
|<span data-ttu-id="73140-832">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-832"></span></span>|
|<span data-ttu-id="73140-833">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-833">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-834">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-834"></span></span>|
|<span data-ttu-id="73140-835">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-836">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-836"></span></span>|
|<span data-ttu-id="73140-837">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-838">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-838"></span></span>|
|<span data-ttu-id="73140-839">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-839">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-840">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-840"></span></span>|
|<span data-ttu-id="73140-841">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-842">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-842"></span></span>|
|<span data-ttu-id="73140-843">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-844">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-844"></span></span>|
|<span data-ttu-id="73140-845">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-846">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-846"></span></span>|
|<span data-ttu-id="73140-847">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-848">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-848"></span></span>|
|<span data-ttu-id="73140-849">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-850">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-850"></span></span>|
|<span data-ttu-id="73140-851">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="73140-851">**AIA URLs**</span></span>|
|<span data-ttu-id="73140-852">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-852"></span></span>|
|<span data-ttu-id="73140-853">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-853">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-854">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-854"></span></span>|
|<span data-ttu-id="73140-855">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-856">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-856"></span></span>|
   
 <span data-ttu-id="73140-857">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="73140-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-858">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-858">**Subject**</span></span>|
|<span data-ttu-id="73140-859">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-859"></span></span>|
|<span data-ttu-id="73140-860">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-860">**Issuer**</span></span>|
|<span data-ttu-id="73140-861">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-861"></span></span>|
|<span data-ttu-id="73140-862">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-862">**Serial Number**</span></span>|
|<span data-ttu-id="73140-863">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-863"></span></span>|
|<span data-ttu-id="73140-864">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-864">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-865">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-865"></span></span>|
|<span data-ttu-id="73140-866">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-867">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-867"></span></span>|
|<span data-ttu-id="73140-868">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-869">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-869"></span></span>|
|<span data-ttu-id="73140-870">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-870">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-871">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-871"></span></span>|
|<span data-ttu-id="73140-872">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-873">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-873"></span></span>|
|<span data-ttu-id="73140-874">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-875">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-875"></span></span>|
|<span data-ttu-id="73140-876">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-877">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-877"></span></span>|
|<span data-ttu-id="73140-878">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-879">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-879"></span></span>|
|<span data-ttu-id="73140-880">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-881">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-881"></span></span>|
|<span data-ttu-id="73140-882">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-882">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-883">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-883"></span></span>|
   
 <span data-ttu-id="73140-884">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="73140-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-885">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-885">**Subject**</span></span>|
|<span data-ttu-id="73140-886">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-886"></span></span>|
|<span data-ttu-id="73140-887">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-887">**Issuer**</span></span>|
|<span data-ttu-id="73140-888">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-888"></span></span>|
|<span data-ttu-id="73140-889">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-889">**Serial Number**</span></span>|
|<span data-ttu-id="73140-890">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-890"></span></span>|
|<span data-ttu-id="73140-891">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-891">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-892">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-892"></span></span>|
|<span data-ttu-id="73140-893">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-894">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-894"></span></span>|
|<span data-ttu-id="73140-895">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-896">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-896"></span></span>|
|<span data-ttu-id="73140-897">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-897">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-898">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-898"></span></span>|
|<span data-ttu-id="73140-899">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-900">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-900"></span></span>|
|<span data-ttu-id="73140-901">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-902">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-902"></span></span>|
|<span data-ttu-id="73140-903">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-904">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-904"></span></span>|
|<span data-ttu-id="73140-905">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-906">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-906"></span></span>|
|<span data-ttu-id="73140-907">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-908">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-908"></span></span>|
|<span data-ttu-id="73140-909">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-909">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-910">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-910"></span></span>|
|<span data-ttu-id="73140-911">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-912">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-912"></span></span>|
   
 <span data-ttu-id="73140-913">**Microsoft IT TLS CA 1**</span><span class="sxs-lookup"><span data-stu-id="73140-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-914">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-914">**Subject**</span></span>|
|<span data-ttu-id="73140-915">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-915"></span></span>|
|<span data-ttu-id="73140-916">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-916">**Issuer**</span></span>|
|<span data-ttu-id="73140-917">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-917"></span></span>|
|<span data-ttu-id="73140-918">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-918">**Serial Number**</span></span>|
|<span data-ttu-id="73140-919">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-919"></span></span>|
|<span data-ttu-id="73140-920">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-920">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-921">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-921"></span></span>|
|<span data-ttu-id="73140-922">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-923">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-923"></span></span>|
|<span data-ttu-id="73140-924">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-925">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-925"></span></span>|
|<span data-ttu-id="73140-926">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-926">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-927">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-927"></span></span>|
|<span data-ttu-id="73140-928">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-929">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-929"></span></span>|
|<span data-ttu-id="73140-930">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-931">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-931"></span></span>|
|<span data-ttu-id="73140-932">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-933">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-933"></span></span>|
|<span data-ttu-id="73140-934">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-935">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-935"></span></span>|
|<span data-ttu-id="73140-936">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-937">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-937"></span></span>|
|<span data-ttu-id="73140-938">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-938">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-939">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-939"></span></span>|
|<span data-ttu-id="73140-940">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-941">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-941"></span></span>|
   
 <span data-ttu-id="73140-942">**Microsoft IT TLS CA 2**</span><span class="sxs-lookup"><span data-stu-id="73140-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-943">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-943">**Subject**</span></span>|
|<span data-ttu-id="73140-944">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-944"></span></span>|
|<span data-ttu-id="73140-945">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-945">**Issuer**</span></span>|
|<span data-ttu-id="73140-946">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-946"></span></span>|
|<span data-ttu-id="73140-947">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-947">**Serial Number**</span></span>|
|<span data-ttu-id="73140-948">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-948"></span></span>|
|<span data-ttu-id="73140-949">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-949">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-950">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-950"></span></span>|
|<span data-ttu-id="73140-951">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-952">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-952"></span></span>|
|<span data-ttu-id="73140-953">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-954">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-954"></span></span>|
|<span data-ttu-id="73140-955">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-955">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-956">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-956"></span></span>|
|<span data-ttu-id="73140-957">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-958">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-958"></span></span>|
|<span data-ttu-id="73140-959">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-960">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-960"></span></span>|
|<span data-ttu-id="73140-961">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-962">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-962"></span></span>|
|<span data-ttu-id="73140-963">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-964">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-964"></span></span>|
|<span data-ttu-id="73140-965">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-966">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-966"></span></span>|
|<span data-ttu-id="73140-967">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-967">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-968">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-968"></span></span>|
|<span data-ttu-id="73140-969">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-970">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-970"></span></span>|
   
 <span data-ttu-id="73140-971">**Microsoft IT TLS CA 4**</span><span class="sxs-lookup"><span data-stu-id="73140-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-972">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-972">**Subject**</span></span>|
|<span data-ttu-id="73140-973">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-973"></span></span>|
|<span data-ttu-id="73140-974">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-974">**Issuer**</span></span>|
|<span data-ttu-id="73140-975">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-975"></span></span>|
|<span data-ttu-id="73140-976">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-976">**Serial Number**</span></span>|
|<span data-ttu-id="73140-977">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-977"></span></span>|
|<span data-ttu-id="73140-978">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-978">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-979">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-979"></span></span>|
|<span data-ttu-id="73140-980">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-981">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-981"></span></span>|
|<span data-ttu-id="73140-982">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-983">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-983"></span></span>|
|<span data-ttu-id="73140-984">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-984">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-985">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-985"></span></span>|
|<span data-ttu-id="73140-986">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-987">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-987"></span></span>|
|<span data-ttu-id="73140-988">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-989">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-989"></span></span>|
|<span data-ttu-id="73140-990">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-991">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-991"></span></span>|
|<span data-ttu-id="73140-992">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-993">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-993"></span></span>|
|<span data-ttu-id="73140-994">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-995">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-995"></span></span>|
|<span data-ttu-id="73140-996">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-996">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-997">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-997"></span></span>|
|<span data-ttu-id="73140-998">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-999">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-999"></span></span>|
   
 <span data-ttu-id="73140-1000">**Microsoft IT TLS CA 5**</span><span class="sxs-lookup"><span data-stu-id="73140-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-1001">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-1001">**Subject**</span></span>|
|<span data-ttu-id="73140-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1002"></span></span>|
|<span data-ttu-id="73140-1003">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-1003">**Issuer**</span></span>|
|<span data-ttu-id="73140-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1004"></span></span>|
|<span data-ttu-id="73140-1005">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-1005">**Serial Number**</span></span>|
|<span data-ttu-id="73140-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1006"></span></span>|
|<span data-ttu-id="73140-1007">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1008"></span></span>|
|<span data-ttu-id="73140-1009">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1010"></span></span>|
|<span data-ttu-id="73140-1011">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1012"></span></span>|
|<span data-ttu-id="73140-1013">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1014"></span></span>|
|<span data-ttu-id="73140-1015">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1016"></span></span>|
|<span data-ttu-id="73140-1017">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1018"></span></span>|
|<span data-ttu-id="73140-1019">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1020"></span></span>|
|<span data-ttu-id="73140-1021">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1022"></span></span>|
|<span data-ttu-id="73140-1023">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1024"></span></span>|
|<span data-ttu-id="73140-1025">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1026"></span></span>|
|<span data-ttu-id="73140-1027">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1028"></span></span>|
   
 <span data-ttu-id="73140-1029">**Symantec 類別 3 EV SSL CA G3**</span><span class="sxs-lookup"><span data-stu-id="73140-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-1030">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-1030">**Subject**</span></span>|
|<span data-ttu-id="73140-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1031"></span></span>|
|<span data-ttu-id="73140-1032">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-1032">**Issuer**</span></span>|
|<span data-ttu-id="73140-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1033"></span></span>|
|<span data-ttu-id="73140-1034">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="73140-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="73140-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1035"></span></span>|
|<span data-ttu-id="73140-1036">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-1036">**Serial Number**</span></span>|
|<span data-ttu-id="73140-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1037"></span></span>|
|<span data-ttu-id="73140-1038">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1039"></span></span>|
|<span data-ttu-id="73140-1040">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1041"></span></span>|
|<span data-ttu-id="73140-1042">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1043"></span></span>|
|<span data-ttu-id="73140-1044">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1045"></span></span>|
|<span data-ttu-id="73140-1046">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1047"></span></span>|
|<span data-ttu-id="73140-1048">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1049"></span></span>|
|<span data-ttu-id="73140-1050">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1051"></span></span>|
|<span data-ttu-id="73140-1052">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1053"></span></span>|
|<span data-ttu-id="73140-1054">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1055"></span></span>|
|<span data-ttu-id="73140-1056">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1057"></span></span>|
|<span data-ttu-id="73140-1058">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1059"></span></span>|
   
 <span data-ttu-id="73140-1060">**Symantec 類別 3 保護伺服器的 CA-G4**</span><span class="sxs-lookup"><span data-stu-id="73140-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-1061">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-1061">**Subject**</span></span>|
|<span data-ttu-id="73140-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1062"></span></span>|
|<span data-ttu-id="73140-1063">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-1063">**Issuer**</span></span>|
|<span data-ttu-id="73140-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1064"></span></span>|
|<span data-ttu-id="73140-1065">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="73140-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="73140-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1066"></span></span>|
|<span data-ttu-id="73140-1067">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-1067">**Serial Number**</span></span>|
|<span data-ttu-id="73140-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1068"></span></span>|
|<span data-ttu-id="73140-1069">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1070"></span></span>|
|<span data-ttu-id="73140-1071">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1072"></span></span>|
|<span data-ttu-id="73140-1073">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1074"></span></span>|
|<span data-ttu-id="73140-1075">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1076"></span></span>|
|<span data-ttu-id="73140-1077">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1078"></span></span>|
|<span data-ttu-id="73140-1079">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1080"></span></span>|
|<span data-ttu-id="73140-1081">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1082"></span></span>|
|<span data-ttu-id="73140-1083">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1084"></span></span>|
|<span data-ttu-id="73140-1085">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1086"></span></span>|
|<span data-ttu-id="73140-1087">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1088"></span></span>|
|<span data-ttu-id="73140-1089">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1090"></span></span>|
   
 <span data-ttu-id="73140-1091">**thawte SHA256 SSL CA**</span><span class="sxs-lookup"><span data-stu-id="73140-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-1092">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-1092">**Subject**</span></span>|
|<span data-ttu-id="73140-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1093"></span></span>|
|<span data-ttu-id="73140-1094">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-1094">**Issuer**</span></span>|
|<span data-ttu-id="73140-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1095"></span></span>|
|<span data-ttu-id="73140-1096">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="73140-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="73140-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1097"></span></span>|
|<span data-ttu-id="73140-1098">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-1098">**Serial Number**</span></span>|
|<span data-ttu-id="73140-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1099"></span></span>|
|<span data-ttu-id="73140-1100">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1101"></span></span>|
|<span data-ttu-id="73140-1102">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1103"></span></span>|
|<span data-ttu-id="73140-1104">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1105"></span></span>|
|<span data-ttu-id="73140-1106">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1107"></span></span>|
|<span data-ttu-id="73140-1108">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1109"></span></span>|
|<span data-ttu-id="73140-1110">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1111"></span></span>|
|<span data-ttu-id="73140-1112">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1113"></span></span>|
|<span data-ttu-id="73140-1114">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1115"></span></span>|
|<span data-ttu-id="73140-1116">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1117"></span></span>|
|<span data-ttu-id="73140-1118">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1119"></span></span>|
|<span data-ttu-id="73140-1120">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1121"></span></span>|
   
 <span data-ttu-id="73140-1122">**Verizon Akamai SureServer CA G14 SHA2**</span><span class="sxs-lookup"><span data-stu-id="73140-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="73140-1123">**主體**</span><span class="sxs-lookup"><span data-stu-id="73140-1123">**Subject**</span></span>|
|<span data-ttu-id="73140-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1124"></span></span>|
|<span data-ttu-id="73140-1125">**發行者**</span><span class="sxs-lookup"><span data-stu-id="73140-1125">**Issuer**</span></span>|
|<span data-ttu-id="73140-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1126"></span></span>|
|<span data-ttu-id="73140-1127">**序號**</span><span class="sxs-lookup"><span data-stu-id="73140-1127">**Serial Number**</span></span>|
|<span data-ttu-id="73140-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1128"></span></span>|
|<span data-ttu-id="73140-1129">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="73140-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="73140-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1130"></span></span>|
|<span data-ttu-id="73140-1131">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="73140-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="73140-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1132"></span></span>|
|<span data-ttu-id="73140-1133">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="73140-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1134"></span></span>|
|<span data-ttu-id="73140-1135">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="73140-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="73140-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1136"></span></span>|
|<span data-ttu-id="73140-1137">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="73140-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1138"></span></span>|
|<span data-ttu-id="73140-1139">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="73140-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="73140-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1140"></span></span>|
|<span data-ttu-id="73140-1141">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="73140-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="73140-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1142"></span></span>|
|<span data-ttu-id="73140-1143">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="73140-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1144"></span></span>|
|<span data-ttu-id="73140-1145">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="73140-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="73140-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1146"></span></span>|
|<span data-ttu-id="73140-1147">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="73140-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="73140-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1148"></span></span>|
|<span data-ttu-id="73140-1149">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="73140-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="73140-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1150"></span></span>|
|<span data-ttu-id="73140-1151">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="73140-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="73140-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="73140-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="73140-1153">其他憑證路徑</span><span class="sxs-lookup"><span data-stu-id="73140-1153">Additional certificate paths</span></span>
<span data-ttu-id="73140-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="73140-1154"></span></span>

<span data-ttu-id="73140-1155">下列包含舊版的憑證未含上方並將與上述清單合併一段時間。</span><span class="sxs-lookup"><span data-stu-id="73140-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
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


