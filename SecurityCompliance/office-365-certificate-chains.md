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
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526636"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="df44f-106">Office 365 憑證鏈結</span><span class="sxs-lookup"><span data-stu-id="df44f-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="df44f-p102">Office 365 如何運用不同的憑證提供者的數目。下面會說明客戶存取 Office 365 時可能會遇到的已知 Office 365 根憑證的完整清單。在憑證上的資訊可能需要將安裝在您自己的基礎結構中，請參閱[第三方 SSL 憑證的 Office 365 計劃](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce)。下列的憑證資訊適用於所有的 Office 365 的全球和雲端執行個體。</span><span class="sxs-lookup"><span data-stu-id="df44f-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="df44f-111">**憑證類型**</span><span class="sxs-lookup"><span data-stu-id="df44f-111">**Certificate type**</span></span>|<span data-ttu-id="df44f-112">**P7b 下載 （英文）**</span><span class="sxs-lookup"><span data-stu-id="df44f-112">**P7b download**</span></span>|<span data-ttu-id="df44f-113">**CRL 端點**</span><span class="sxs-lookup"><span data-stu-id="df44f-113">**CRL Endpoints**</span></span>|<span data-ttu-id="df44f-114">**OCSP 端點**</span><span class="sxs-lookup"><span data-stu-id="df44f-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="df44f-115">**AIA 端點**</span><span class="sxs-lookup"><span data-stu-id="df44f-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="df44f-116">公開受信任的根憑證</span><span class="sxs-lookup"><span data-stu-id="df44f-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="df44f-117">Office 365 根憑證組合 (P7B)</span><span class="sxs-lookup"><span data-stu-id="df44f-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="df44f-118">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="df44f-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="df44f-119">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="df44f-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="df44f-120">不適用</span><span class="sxs-lookup"><span data-stu-id="df44f-120">N/A</span></span>  <br/> |<span data-ttu-id="df44f-121">不適用</span><span class="sxs-lookup"><span data-stu-id="df44f-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="df44f-122">公開信任中繼憑證</span><span class="sxs-lookup"><span data-stu-id="df44f-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="df44f-123">Office 365 中繼憑證組合 (P7B)</span><span class="sxs-lookup"><span data-stu-id="df44f-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="df44f-124">cdp1.public trust.com</span><span class="sxs-lookup"><span data-stu-id="df44f-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="df44f-125">crl.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="df44f-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="df44f-126">crl.entrust.net</span><span class="sxs-lookup"><span data-stu-id="df44f-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="df44f-127">crl.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="df44f-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="df44f-128">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="df44f-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="df44f-129">crl.identrust.com</span><span class="sxs-lookup"><span data-stu-id="df44f-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="df44f-130">crl.thawte.com</span><span class="sxs-lookup"><span data-stu-id="df44f-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="df44f-131">crl3.digicert.com</span><span class="sxs-lookup"><span data-stu-id="df44f-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="df44f-132">crl4.digicert.com</span><span class="sxs-lookup"><span data-stu-id="df44f-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="df44f-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="df44f-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="df44f-134">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="df44f-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="df44f-135">isrg.trustid.ocsp.identrust.com</span><span class="sxs-lookup"><span data-stu-id="df44f-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="df44f-136">ocsp.digicert.com</span><span class="sxs-lookup"><span data-stu-id="df44f-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="df44f-137">ocsp.entrust.net</span><span class="sxs-lookup"><span data-stu-id="df44f-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="df44f-138">ocsp.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="df44f-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="df44f-139">ocsp.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="df44f-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="df44f-140">ocsp.startssl.com</span><span class="sxs-lookup"><span data-stu-id="df44f-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="df44f-141">ocsp.thawte.com</span><span class="sxs-lookup"><span data-stu-id="df44f-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="df44f-142">ocsp2.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="df44f-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="df44f-143">ocspcnnicroot.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="df44f-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="df44f-144">根-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="df44f-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="df44f-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="df44f-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="df44f-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="df44f-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="df44f-147">aia.startssl.com</span><span class="sxs-lookup"><span data-stu-id="df44f-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="df44f-148">apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="df44f-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="df44f-149">cacert.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="df44f-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="df44f-150">www.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="df44f-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="df44f-151">展開根目錄與以下以查看憑證提供者相關的其他詳細資料的中階章節。</span><span class="sxs-lookup"><span data-stu-id="df44f-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="df44f-152">Office 365 根憑證的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="df44f-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="df44f-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="df44f-153"></span></span>

 <span data-ttu-id="df44f-154">**Baltimore CyberTrust Root**</span><span class="sxs-lookup"><span data-stu-id="df44f-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="df44f-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="df44f-155">|:-----|</span></span>
|<span data-ttu-id="df44f-156">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="df44f-157">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-157">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-158">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-158"></span></span>|
|<span data-ttu-id="df44f-159">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-159">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-160">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-160"></span></span>|
|<span data-ttu-id="df44f-161">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-162">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-162"></span></span>|
|<span data-ttu-id="df44f-163">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-164">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-164"></span></span>|
|<span data-ttu-id="df44f-165">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-165">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-166">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-166"></span></span>|
|<span data-ttu-id="df44f-167">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-168">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-168"></span></span>|
|<span data-ttu-id="df44f-169">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-170">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-170"></span></span>|
|<span data-ttu-id="df44f-171">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-172">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-172"></span></span>|
|<span data-ttu-id="df44f-173">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-174">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-174"></span></span>|
   
 <span data-ttu-id="df44f-175">**CNNIC 根目錄**</span><span class="sxs-lookup"><span data-stu-id="df44f-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-176">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-176">**Subject**</span></span>|
|<span data-ttu-id="df44f-177">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-177"></span></span>|
|<span data-ttu-id="df44f-178">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-178">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-179">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-179"></span></span>|
|<span data-ttu-id="df44f-180">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-180">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-181">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-181"></span></span>|
|<span data-ttu-id="df44f-182">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-183">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-183"></span></span>|
|<span data-ttu-id="df44f-184">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-185">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-185"></span></span>|
|<span data-ttu-id="df44f-186">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-186">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-187">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-187"></span></span>|
|<span data-ttu-id="df44f-188">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-189">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-189"></span></span>|
|<span data-ttu-id="df44f-190">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-191">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-191"></span></span>|
|<span data-ttu-id="df44f-192">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-193">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-193"></span></span>|
|<span data-ttu-id="df44f-194">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-195">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-195"></span></span>|
|<span data-ttu-id="df44f-196">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-197">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-197"></span></span>|
   
 <span data-ttu-id="df44f-198">**DigiCert 通用的根 CA**</span><span class="sxs-lookup"><span data-stu-id="df44f-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-199">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-199">**Subject**</span></span>|
|<span data-ttu-id="df44f-200">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-200"></span></span>|
|<span data-ttu-id="df44f-201">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-201">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-202">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-202"></span></span>|
|<span data-ttu-id="df44f-203">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-203">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-204">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-204"></span></span>|
|<span data-ttu-id="df44f-205">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-206">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-206"></span></span>|
|<span data-ttu-id="df44f-207">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-208">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-208"></span></span>|
|<span data-ttu-id="df44f-209">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-209">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-210">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-210"></span></span>|
|<span data-ttu-id="df44f-211">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-212">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-212"></span></span>|
|<span data-ttu-id="df44f-213">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-214">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-214"></span></span>|
|<span data-ttu-id="df44f-215">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-216">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-216"></span></span>|
|<span data-ttu-id="df44f-217">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-218">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-218"></span></span>|
|<span data-ttu-id="df44f-219">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-220">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-220"></span></span>|
   
 <span data-ttu-id="df44f-221">**DigiCert 高保證 EV 根 CA**</span><span class="sxs-lookup"><span data-stu-id="df44f-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-222">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-222">**Subject**</span></span>|
|<span data-ttu-id="df44f-223">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-223"></span></span>|
|<span data-ttu-id="df44f-224">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-224">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-225">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-225"></span></span>|
|<span data-ttu-id="df44f-226">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-226">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-227">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-227"></span></span>|
|<span data-ttu-id="df44f-228">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-229">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-229"></span></span>|
|<span data-ttu-id="df44f-230">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-231">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-231"></span></span>|
|<span data-ttu-id="df44f-232">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-232">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-233">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-233"></span></span>|
|<span data-ttu-id="df44f-234">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-235">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-235"></span></span>|
|<span data-ttu-id="df44f-236">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-237">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-237"></span></span>|
|<span data-ttu-id="df44f-238">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-239">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-239"></span></span>|
|<span data-ttu-id="df44f-240">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-241">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-241"></span></span>|
|<span data-ttu-id="df44f-242">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-243">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-243"></span></span>|
   
 <span data-ttu-id="df44f-244">**D 信任根類別 3 CA 2 2009**</span><span class="sxs-lookup"><span data-stu-id="df44f-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-245">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-245">**Subject**</span></span>|
|<span data-ttu-id="df44f-246">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-246"></span></span>|
|<span data-ttu-id="df44f-247">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-247">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-248">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-248"></span></span>|
|<span data-ttu-id="df44f-249">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-249">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-250">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-250"></span></span>|
|<span data-ttu-id="df44f-251">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-252">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-252"></span></span>|
|<span data-ttu-id="df44f-253">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-254">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-254"></span></span>|
|<span data-ttu-id="df44f-255">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-255">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-256">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-256"></span></span>|
|<span data-ttu-id="df44f-257">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-258">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-258"></span></span>|
|<span data-ttu-id="df44f-259">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-260">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-260"></span></span>|
|<span data-ttu-id="df44f-261">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-262">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-262"></span></span>|
|<span data-ttu-id="df44f-263">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-264">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-264"></span></span>|
|<span data-ttu-id="df44f-265">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-265">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-266">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-266"></span></span>|
   
 <span data-ttu-id="df44f-267">**D 信任根類別 3 CA 2 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="df44f-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-268">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-268">**Subject**</span></span>|
|<span data-ttu-id="df44f-269">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-269"></span></span>|
|<span data-ttu-id="df44f-270">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-270">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-271">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-271"></span></span>|
|<span data-ttu-id="df44f-272">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-272">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-273">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-273"></span></span>|
|<span data-ttu-id="df44f-274">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-275">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-275"></span></span>|
|<span data-ttu-id="df44f-276">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-277">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-277"></span></span>|
|<span data-ttu-id="df44f-278">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-278">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-279">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-279"></span></span>|
|<span data-ttu-id="df44f-280">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-281">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-281"></span></span>|
|<span data-ttu-id="df44f-282">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-283">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-283"></span></span>|
|<span data-ttu-id="df44f-284">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-285">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-285"></span></span>|
|<span data-ttu-id="df44f-286">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-287">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-287"></span></span>|
|<span data-ttu-id="df44f-288">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-288">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-289">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-289"></span></span>|
   
 <span data-ttu-id="df44f-290">**DST 根 CA X3**</span><span class="sxs-lookup"><span data-stu-id="df44f-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-291">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-291">**Subject**</span></span>|
|<span data-ttu-id="df44f-292">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-292"></span></span>|
|<span data-ttu-id="df44f-293">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-293">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-294">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-294"></span></span>|
|<span data-ttu-id="df44f-295">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-295">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-296">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-296"></span></span>|
|<span data-ttu-id="df44f-297">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-298">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-298"></span></span>|
|<span data-ttu-id="df44f-299">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-300">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-300"></span></span>|
|<span data-ttu-id="df44f-301">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-301">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-302">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-302"></span></span>|
|<span data-ttu-id="df44f-303">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-304">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-304"></span></span>|
|<span data-ttu-id="df44f-305">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-306">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-306"></span></span>|
|<span data-ttu-id="df44f-307">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-308">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-308"></span></span>|
|<span data-ttu-id="df44f-309">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-310">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-310"></span></span>|
   
 <span data-ttu-id="df44f-311">**過程錄影根憑證授權單位-G2**</span><span class="sxs-lookup"><span data-stu-id="df44f-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-312">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-312">**Subject**</span></span>|
|<span data-ttu-id="df44f-313">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-313"></span></span>|
|<span data-ttu-id="df44f-314">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-314">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-315">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-315"></span></span>|
|<span data-ttu-id="df44f-316">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-316">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-317">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-317"></span></span>|
|<span data-ttu-id="df44f-318">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-319">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-319"></span></span>|
|<span data-ttu-id="df44f-320">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-321">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-321"></span></span>|
|<span data-ttu-id="df44f-322">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-322">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-323">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-323"></span></span>|
|<span data-ttu-id="df44f-324">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-325">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-325"></span></span>|
|<span data-ttu-id="df44f-326">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-327">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-327"></span></span>|
|<span data-ttu-id="df44f-328">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-329">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-329"></span></span>|
|<span data-ttu-id="df44f-330">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-331">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-331"></span></span>|
   
 <span data-ttu-id="df44f-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="df44f-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-333">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-333">**Subject**</span></span>|
|<span data-ttu-id="df44f-334">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-334"></span></span>|
|<span data-ttu-id="df44f-335">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-335">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-336">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-336"></span></span>|
|<span data-ttu-id="df44f-337">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-337">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-338">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-338"></span></span>|
|<span data-ttu-id="df44f-339">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-340">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-340"></span></span>|
|<span data-ttu-id="df44f-341">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-342">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-342"></span></span>|
|<span data-ttu-id="df44f-343">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-343">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-344">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-344"></span></span>|
|<span data-ttu-id="df44f-345">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-346">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-346"></span></span>|
|<span data-ttu-id="df44f-347">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-348">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-348"></span></span>|
|<span data-ttu-id="df44f-349">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-350">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-350"></span></span>|
|<span data-ttu-id="df44f-351">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-352">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-352"></span></span>|
   
 <span data-ttu-id="df44f-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="df44f-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-354">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-354">**Subject**</span></span>|
|<span data-ttu-id="df44f-355">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-355"></span></span>|
|<span data-ttu-id="df44f-356">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-356">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-357">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-357"></span></span>|
|<span data-ttu-id="df44f-358">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-358">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-359">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-359"></span></span>|
|<span data-ttu-id="df44f-360">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-361">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-361"></span></span>|
|<span data-ttu-id="df44f-362">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-363">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-363"></span></span>|
|<span data-ttu-id="df44f-364">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-364">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-365">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-365"></span></span>|
|<span data-ttu-id="df44f-366">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-367">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-367"></span></span>|
|<span data-ttu-id="df44f-368">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-369">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-369"></span></span>|
|<span data-ttu-id="df44f-370">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-371">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-371"></span></span>|
|<span data-ttu-id="df44f-372">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-373">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-373"></span></span>|
|<span data-ttu-id="df44f-374">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-375">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-375"></span></span>|
|<span data-ttu-id="df44f-376">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-376">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-377">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-377"></span></span>|
   
 <span data-ttu-id="df44f-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="df44f-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-379">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-379">**Subject**</span></span>|
|<span data-ttu-id="df44f-380">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-380"></span></span>|
|<span data-ttu-id="df44f-381">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-381">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-382">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-382"></span></span>|
|<span data-ttu-id="df44f-383">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-383">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-384">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-384"></span></span>|
|<span data-ttu-id="df44f-385">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-386">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-386"></span></span>|
|<span data-ttu-id="df44f-387">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-388">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-388"></span></span>|
|<span data-ttu-id="df44f-389">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-389">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-390">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-390"></span></span>|
|<span data-ttu-id="df44f-391">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-392">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-392"></span></span>|
|<span data-ttu-id="df44f-393">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-394">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-394"></span></span>|
|<span data-ttu-id="df44f-395">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-396">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-396"></span></span>|
|<span data-ttu-id="df44f-397">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-398">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-398"></span></span>|
   
 <span data-ttu-id="df44f-399">**thawte 主要的根 CA-G3**</span><span class="sxs-lookup"><span data-stu-id="df44f-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-400">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-400">**Subject**</span></span>|
|<span data-ttu-id="df44f-401">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-401"></span></span>|
|<span data-ttu-id="df44f-402">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-402">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-403">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-403"></span></span>|
|<span data-ttu-id="df44f-404">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-404">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-405">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-405"></span></span>|
|<span data-ttu-id="df44f-406">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-407">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-407"></span></span>|
|<span data-ttu-id="df44f-408">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-409">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-409"></span></span>|
|<span data-ttu-id="df44f-410">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-410">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-411">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-411"></span></span>|
|<span data-ttu-id="df44f-412">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-413">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-413"></span></span>|
|<span data-ttu-id="df44f-414">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-415">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-415"></span></span>|
|<span data-ttu-id="df44f-416">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-417">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-417"></span></span>|
|<span data-ttu-id="df44f-418">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-419">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-419"></span></span>|
   
 <span data-ttu-id="df44f-420">**VeriSign 類別 3 主要的公用憑證授權單位-G5**</span><span class="sxs-lookup"><span data-stu-id="df44f-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-421">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-421">**Subject**</span></span>|
|<span data-ttu-id="df44f-422">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-422"></span></span>|
|<span data-ttu-id="df44f-423">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-423">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-424">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-424"></span></span>|
|<span data-ttu-id="df44f-425">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-425">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-426">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-426"></span></span>|
|<span data-ttu-id="df44f-427">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-428">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-428"></span></span>|
|<span data-ttu-id="df44f-429">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-430">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-430"></span></span>|
|<span data-ttu-id="df44f-431">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-431">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-432">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-432"></span></span>|
|<span data-ttu-id="df44f-433">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-434">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-434"></span></span>|
|<span data-ttu-id="df44f-435">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-436">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-436"></span></span>|
|<span data-ttu-id="df44f-437">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-438">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-438"></span></span>|
|<span data-ttu-id="df44f-439">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-440">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="df44f-441">Office 365 中繼憑證的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="df44f-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="df44f-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="df44f-442"></span></span>

 <span data-ttu-id="df44f-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="df44f-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-444">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-444">**Subject**</span></span>|
|<span data-ttu-id="df44f-445">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-445"></span></span>|
|<span data-ttu-id="df44f-446">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-446">**Issuer**</span></span>|
|<span data-ttu-id="df44f-447">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-447"></span></span>|
|<span data-ttu-id="df44f-448">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-448">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-449">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-449"></span></span>|
|<span data-ttu-id="df44f-450">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-450">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-451">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-451"></span></span>|
|<span data-ttu-id="df44f-452">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-453">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-453"></span></span>|
|<span data-ttu-id="df44f-454">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-455">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-455"></span></span>|
|<span data-ttu-id="df44f-456">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-456">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-457">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-457"></span></span>|
|<span data-ttu-id="df44f-458">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-459">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-459"></span></span>|
|<span data-ttu-id="df44f-460">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-461">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-461"></span></span>|
|<span data-ttu-id="df44f-462">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-463">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-463"></span></span>|
|<span data-ttu-id="df44f-464">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-465">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-465"></span></span>|
|<span data-ttu-id="df44f-466">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-467">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-467"></span></span>|
|<span data-ttu-id="df44f-468">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-468">**AIA URLs**</span></span>|
|<span data-ttu-id="df44f-469">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-469"></span></span>|
|<span data-ttu-id="df44f-470">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-470">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-471">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-471"></span></span>|
|<span data-ttu-id="df44f-472">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-473">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-473"></span></span>|
   
 <span data-ttu-id="df44f-474">**D 信任 SSL 類別 3 CA 1 2009**</span><span class="sxs-lookup"><span data-stu-id="df44f-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-475">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-475">**Subject**</span></span>|
|<span data-ttu-id="df44f-476">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-476"></span></span>|
|<span data-ttu-id="df44f-477">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-477">**Issuer**</span></span>|
|<span data-ttu-id="df44f-478">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-478"></span></span>|
|<span data-ttu-id="df44f-479">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="df44f-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="df44f-480">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-480"></span></span>|
|<span data-ttu-id="df44f-481">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-481">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-482">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-482"></span></span>|
|<span data-ttu-id="df44f-483">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-483">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-484">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-484"></span></span>|
|<span data-ttu-id="df44f-485">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-486">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-486"></span></span>|
|<span data-ttu-id="df44f-487">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-488">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-488"></span></span>|
|<span data-ttu-id="df44f-489">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-489">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-490">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-490"></span></span>|
|<span data-ttu-id="df44f-491">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-492">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-492"></span></span>|
|<span data-ttu-id="df44f-493">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-494">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-494"></span></span>|
|<span data-ttu-id="df44f-495">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-496">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-496"></span></span>|
|<span data-ttu-id="df44f-497">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-498">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-498"></span></span>|
|<span data-ttu-id="df44f-499">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-500">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-500"></span></span>|
|<span data-ttu-id="df44f-501">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-501">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-502">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-502"></span></span>|
|<span data-ttu-id="df44f-503">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-504">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-504"></span></span>|
   
 <span data-ttu-id="df44f-505">**D 信任 SSL 類別 3 CA 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="df44f-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-506">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-506">**Subject**</span></span>|
|<span data-ttu-id="df44f-507">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-507"></span></span>|
|<span data-ttu-id="df44f-508">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-508">**Issuer**</span></span>|
|<span data-ttu-id="df44f-509">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-509"></span></span>|
|<span data-ttu-id="df44f-510">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="df44f-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="df44f-511">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-511"></span></span>|
|<span data-ttu-id="df44f-512">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-512">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-513">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-513"></span></span>|
|<span data-ttu-id="df44f-514">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-514">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-515">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-515"></span></span>|
|<span data-ttu-id="df44f-516">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-517">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-517"></span></span>|
|<span data-ttu-id="df44f-518">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-519">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-519"></span></span>|
|<span data-ttu-id="df44f-520">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-520">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-521">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-521"></span></span>|
|<span data-ttu-id="df44f-522">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-523">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-523"></span></span>|
|<span data-ttu-id="df44f-524">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-525">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-525"></span></span>|
|<span data-ttu-id="df44f-526">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-527">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-527"></span></span>|
|<span data-ttu-id="df44f-528">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-529">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-529"></span></span>|
|<span data-ttu-id="df44f-530">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-531">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-531"></span></span>|
|<span data-ttu-id="df44f-532">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-532">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-533">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-533"></span></span>|
|<span data-ttu-id="df44f-534">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-535">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-535"></span></span>|
   
 <span data-ttu-id="df44f-536">**DigiCert 雲端服務 CA-1**</span><span class="sxs-lookup"><span data-stu-id="df44f-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-537">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-537">**Subject**</span></span>|
|<span data-ttu-id="df44f-538">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-538"></span></span>|
|<span data-ttu-id="df44f-539">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-539">**Issuer**</span></span>|
|<span data-ttu-id="df44f-540">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-540"></span></span>|
|<span data-ttu-id="df44f-541">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-541">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-542">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-542"></span></span>|
|<span data-ttu-id="df44f-543">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-543">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-544">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-544"></span></span>|
|<span data-ttu-id="df44f-545">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-546">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-546"></span></span>|
|<span data-ttu-id="df44f-547">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-548">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-548"></span></span>|
|<span data-ttu-id="df44f-549">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-549">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-550">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-550"></span></span>|
|<span data-ttu-id="df44f-551">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-552">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-552"></span></span>|
|<span data-ttu-id="df44f-553">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-554">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-554"></span></span>|
|<span data-ttu-id="df44f-555">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-556">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-556"></span></span>|
|<span data-ttu-id="df44f-557">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-558">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-558"></span></span>|
|<span data-ttu-id="df44f-559">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-560">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-560"></span></span>|
|<span data-ttu-id="df44f-561">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-561">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-562">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-562"></span></span>|
|<span data-ttu-id="df44f-563">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-564">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-564"></span></span>|
   
 <span data-ttu-id="df44f-565">**DigiCert SHA2 高保證伺服器 CA**</span><span class="sxs-lookup"><span data-stu-id="df44f-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-566">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-566">**Subject**</span></span>|
|<span data-ttu-id="df44f-567">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-567"></span></span>|
|<span data-ttu-id="df44f-568">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-568">**Issuer**</span></span>|
|<span data-ttu-id="df44f-569">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-569"></span></span>|
|<span data-ttu-id="df44f-570">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-570">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-571">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-571"></span></span>|
|<span data-ttu-id="df44f-572">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-572">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-573">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-573"></span></span>|
|<span data-ttu-id="df44f-574">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-575">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-575"></span></span>|
|<span data-ttu-id="df44f-576">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-577">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-577"></span></span>|
|<span data-ttu-id="df44f-578">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-578">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-579">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-579"></span></span>|
|<span data-ttu-id="df44f-580">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-581">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-581"></span></span>|
|<span data-ttu-id="df44f-582">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-583">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-583"></span></span>|
|<span data-ttu-id="df44f-584">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-585">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-585"></span></span>|
|<span data-ttu-id="df44f-586">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-587">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-587"></span></span>|
|<span data-ttu-id="df44f-588">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-589">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-589"></span></span>|
|<span data-ttu-id="df44f-590">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-590">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-591">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-591"></span></span>|
|<span data-ttu-id="df44f-592">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-593">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-593"></span></span>|
   
 <span data-ttu-id="df44f-594">**DigiCert SHA2 保護伺服器的 CA**</span><span class="sxs-lookup"><span data-stu-id="df44f-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-595">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-595">**Subject**</span></span>|
|<span data-ttu-id="df44f-596">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-596"></span></span>|
|<span data-ttu-id="df44f-597">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-597">**Issuer**</span></span>|
|<span data-ttu-id="df44f-598">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-598"></span></span>|
|<span data-ttu-id="df44f-599">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-599">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-600">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-600"></span></span>|
|<span data-ttu-id="df44f-601">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-601">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-602">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-602"></span></span>|
|<span data-ttu-id="df44f-603">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-604">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-604"></span></span>|
|<span data-ttu-id="df44f-605">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-606">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-606"></span></span>|
|<span data-ttu-id="df44f-607">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-607">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-608">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-608"></span></span>|
|<span data-ttu-id="df44f-609">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-610">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-610"></span></span>|
|<span data-ttu-id="df44f-611">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-612">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-612"></span></span>|
|<span data-ttu-id="df44f-613">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-614">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-614"></span></span>|
|<span data-ttu-id="df44f-615">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-616">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-616"></span></span>|
|<span data-ttu-id="df44f-617">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-618">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-618"></span></span>|
|<span data-ttu-id="df44f-619">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-619">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-620">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-620"></span></span>|
|<span data-ttu-id="df44f-621">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-622">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-622"></span></span>|
   
 <span data-ttu-id="df44f-623">**過程錄影憑證授權單位-L1C**</span><span class="sxs-lookup"><span data-stu-id="df44f-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-624">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-624">**Subject**</span></span>|
|<span data-ttu-id="df44f-625">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-625"></span></span>|
|<span data-ttu-id="df44f-626">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-626">**Issuer**</span></span>|
|<span data-ttu-id="df44f-627">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-627"></span></span>|
|<span data-ttu-id="df44f-628">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-628">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-629">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-629"></span></span>|
|<span data-ttu-id="df44f-630">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-630">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-631">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-631"></span></span>|
|<span data-ttu-id="df44f-632">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-633">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-633"></span></span>|
|<span data-ttu-id="df44f-634">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-635">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-635"></span></span>|
|<span data-ttu-id="df44f-636">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-636">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-637">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-637"></span></span>|
|<span data-ttu-id="df44f-638">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-639">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-639"></span></span>|
|<span data-ttu-id="df44f-640">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-641">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-641"></span></span>|
|<span data-ttu-id="df44f-642">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-643">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-643"></span></span>|
|<span data-ttu-id="df44f-644">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-645">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-645"></span></span>|
|<span data-ttu-id="df44f-646">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-647">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-647"></span></span>|
|<span data-ttu-id="df44f-648">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-648">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-649">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-649"></span></span>|
|<span data-ttu-id="df44f-650">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-651">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-651"></span></span>|
   
 <span data-ttu-id="df44f-652">**過程錄影憑證授權單位-L1K**</span><span class="sxs-lookup"><span data-stu-id="df44f-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-653">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-653">**Subject**</span></span>|
|<span data-ttu-id="df44f-654">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-654"></span></span>|
|<span data-ttu-id="df44f-655">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-655">**Issuer**</span></span>|
|<span data-ttu-id="df44f-656">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-656"></span></span>|
|<span data-ttu-id="df44f-657">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-657">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-658">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-658"></span></span>|
|<span data-ttu-id="df44f-659">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-659">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-660">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-660"></span></span>|
|<span data-ttu-id="df44f-661">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-662">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-662"></span></span>|
|<span data-ttu-id="df44f-663">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-664">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-664"></span></span>|
|<span data-ttu-id="df44f-665">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-665">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-666">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-666"></span></span>|
|<span data-ttu-id="df44f-667">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-668">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-668"></span></span>|
|<span data-ttu-id="df44f-669">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-670">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-670"></span></span>|
|<span data-ttu-id="df44f-671">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-672">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-672"></span></span>|
|<span data-ttu-id="df44f-673">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-674">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-674"></span></span>|
|<span data-ttu-id="df44f-675">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-676">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-676"></span></span>|
|<span data-ttu-id="df44f-677">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-677">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-678">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-678"></span></span>|
|<span data-ttu-id="df44f-679">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-680">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-680"></span></span>|
   
 <span data-ttu-id="df44f-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="df44f-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-682">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-682">**Subject**</span></span>|
|<span data-ttu-id="df44f-683">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-683"></span></span>|
|<span data-ttu-id="df44f-684">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-684">**Issuer**</span></span>|
|<span data-ttu-id="df44f-685">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-685"></span></span>|
|<span data-ttu-id="df44f-686">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-686">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-687">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-687"></span></span>|
|<span data-ttu-id="df44f-688">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-688">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-689">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-689"></span></span>|
|<span data-ttu-id="df44f-690">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-691">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-691"></span></span>|
|<span data-ttu-id="df44f-692">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-693">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-693"></span></span>|
|<span data-ttu-id="df44f-694">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-694">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-695">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-695"></span></span>|
|<span data-ttu-id="df44f-696">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-697">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-697"></span></span>|
|<span data-ttu-id="df44f-698">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-699">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-699"></span></span>|
|<span data-ttu-id="df44f-700">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-701">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-701"></span></span>|
|<span data-ttu-id="df44f-702">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-703">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-703"></span></span>|
|<span data-ttu-id="df44f-704">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-705">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-705"></span></span>|
|<span data-ttu-id="df44f-706">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-706">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-707">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-707"></span></span>|
|<span data-ttu-id="df44f-708">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-709">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-709"></span></span>|
   
 <span data-ttu-id="df44f-710">**GlobalSign 擴充驗證 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="df44f-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-711">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-711">**Subject**</span></span>|
|<span data-ttu-id="df44f-712">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-712"></span></span>|
|<span data-ttu-id="df44f-713">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-713">**Issuer**</span></span>|
|<span data-ttu-id="df44f-714">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-714"></span></span>|
|<span data-ttu-id="df44f-715">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-715">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-716">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-716"></span></span>|
|<span data-ttu-id="df44f-717">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-717">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-718">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-718"></span></span>|
|<span data-ttu-id="df44f-719">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-720">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-720"></span></span>|
|<span data-ttu-id="df44f-721">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-722">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-722"></span></span>|
|<span data-ttu-id="df44f-723">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-723">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-724">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-724"></span></span>|
|<span data-ttu-id="df44f-725">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-726">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-726"></span></span>|
|<span data-ttu-id="df44f-727">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-728">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-728"></span></span>|
|<span data-ttu-id="df44f-729">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-730">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-730"></span></span>|
|<span data-ttu-id="df44f-731">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-732">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-732"></span></span>|
|<span data-ttu-id="df44f-733">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-734">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-734"></span></span>|
|<span data-ttu-id="df44f-735">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-735">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-736">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-736"></span></span>|
|<span data-ttu-id="df44f-737">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-738">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-738"></span></span>|
   
 <span data-ttu-id="df44f-739">**GlobalSign 擴充驗證 CA-SHA256-G3**</span><span class="sxs-lookup"><span data-stu-id="df44f-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-740">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-740">**Subject**</span></span>|
|<span data-ttu-id="df44f-741">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-741"></span></span>|
|<span data-ttu-id="df44f-742">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-742">**Issuer**</span></span>|
|<span data-ttu-id="df44f-743">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-743"></span></span>|
|<span data-ttu-id="df44f-744">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-744">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-745">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-745"></span></span>|
|<span data-ttu-id="df44f-746">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-746">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-747">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-747"></span></span>|
|<span data-ttu-id="df44f-748">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-749">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-749"></span></span>|
|<span data-ttu-id="df44f-750">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-751">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-751"></span></span>|
|<span data-ttu-id="df44f-752">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-752">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-753">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-753"></span></span>|
|<span data-ttu-id="df44f-754">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-755">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-755"></span></span>|
|<span data-ttu-id="df44f-756">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-757">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-757"></span></span>|
|<span data-ttu-id="df44f-758">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-759">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-759"></span></span>|
|<span data-ttu-id="df44f-760">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-761">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-761"></span></span>|
|<span data-ttu-id="df44f-762">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-763">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-763"></span></span>|
|<span data-ttu-id="df44f-764">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-764">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-765">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-765"></span></span>|
|<span data-ttu-id="df44f-766">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-767">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-767"></span></span>|
   
 <span data-ttu-id="df44f-768">**GlobalSign 組織驗證 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="df44f-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-769">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-769">**Subject**</span></span>|
|<span data-ttu-id="df44f-770">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-770"></span></span>|
|<span data-ttu-id="df44f-771">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-771">**Issuer**</span></span>|
|<span data-ttu-id="df44f-772">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-772"></span></span>|
|<span data-ttu-id="df44f-773">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-773">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-774">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-774"></span></span>|
|<span data-ttu-id="df44f-775">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-775">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-776">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-776"></span></span>|
|<span data-ttu-id="df44f-777">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-778">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-778"></span></span>|
|<span data-ttu-id="df44f-779">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-780">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-780"></span></span>|
|<span data-ttu-id="df44f-781">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-781">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-782">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-782"></span></span>|
|<span data-ttu-id="df44f-783">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-784">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-784"></span></span>|
|<span data-ttu-id="df44f-785">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-786">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-786"></span></span>|
|<span data-ttu-id="df44f-787">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-788">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-788"></span></span>|
|<span data-ttu-id="df44f-789">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-790">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-790"></span></span>|
|<span data-ttu-id="df44f-791">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-792">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-792"></span></span>|
|<span data-ttu-id="df44f-793">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-793">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-794">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-794"></span></span>|
|<span data-ttu-id="df44f-795">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-796">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-796"></span></span>|
   
 <span data-ttu-id="df44f-797">**GlobalSign 組織驗證 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="df44f-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-798">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-798">**Subject**</span></span>|
|<span data-ttu-id="df44f-799">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-799"></span></span>|
|<span data-ttu-id="df44f-800">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-800">**Issuer**</span></span>|
|<span data-ttu-id="df44f-801">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-801"></span></span>|
|<span data-ttu-id="df44f-802">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-802">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-803">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-803"></span></span>|
|<span data-ttu-id="df44f-804">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-804">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-805">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-805"></span></span>|
|<span data-ttu-id="df44f-806">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-807">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-807"></span></span>|
|<span data-ttu-id="df44f-808">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-809">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-809"></span></span>|
|<span data-ttu-id="df44f-810">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-810">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-811">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-811"></span></span>|
|<span data-ttu-id="df44f-812">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-813">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-813"></span></span>|
|<span data-ttu-id="df44f-814">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-815">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-815"></span></span>|
|<span data-ttu-id="df44f-816">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-817">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-817"></span></span>|
|<span data-ttu-id="df44f-818">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-819">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-819"></span></span>|
|<span data-ttu-id="df44f-820">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-821">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-821"></span></span>|
|<span data-ttu-id="df44f-822">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-822">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-823">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-823"></span></span>|
|<span data-ttu-id="df44f-824">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-825">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-825"></span></span>|
   
 <span data-ttu-id="df44f-826">**我們加密授權 X3**</span><span class="sxs-lookup"><span data-stu-id="df44f-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-827">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-827">**Subject**</span></span>|
|<span data-ttu-id="df44f-828">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-828"></span></span>|
|<span data-ttu-id="df44f-829">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-829">**Issuer**</span></span>|
|<span data-ttu-id="df44f-830">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-830"></span></span>|
|<span data-ttu-id="df44f-831">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-831">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-832">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-832"></span></span>|
|<span data-ttu-id="df44f-833">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-833">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-834">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-834"></span></span>|
|<span data-ttu-id="df44f-835">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-836">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-836"></span></span>|
|<span data-ttu-id="df44f-837">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-838">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-838"></span></span>|
|<span data-ttu-id="df44f-839">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-839">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-840">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-840"></span></span>|
|<span data-ttu-id="df44f-841">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-842">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-842"></span></span>|
|<span data-ttu-id="df44f-843">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-844">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-844"></span></span>|
|<span data-ttu-id="df44f-845">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-846">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-846"></span></span>|
|<span data-ttu-id="df44f-847">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-848">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-848"></span></span>|
|<span data-ttu-id="df44f-849">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-850">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-850"></span></span>|
|<span data-ttu-id="df44f-851">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-851">**AIA URLs**</span></span>|
|<span data-ttu-id="df44f-852">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-852"></span></span>|
|<span data-ttu-id="df44f-853">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-853">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-854">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-854"></span></span>|
|<span data-ttu-id="df44f-855">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-856">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-856"></span></span>|
   
 <span data-ttu-id="df44f-857">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="df44f-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-858">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-858">**Subject**</span></span>|
|<span data-ttu-id="df44f-859">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-859"></span></span>|
|<span data-ttu-id="df44f-860">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-860">**Issuer**</span></span>|
|<span data-ttu-id="df44f-861">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-861"></span></span>|
|<span data-ttu-id="df44f-862">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-862">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-863">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-863"></span></span>|
|<span data-ttu-id="df44f-864">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-864">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-865">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-865"></span></span>|
|<span data-ttu-id="df44f-866">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-867">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-867"></span></span>|
|<span data-ttu-id="df44f-868">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-869">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-869"></span></span>|
|<span data-ttu-id="df44f-870">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-870">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-871">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-871"></span></span>|
|<span data-ttu-id="df44f-872">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-873">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-873"></span></span>|
|<span data-ttu-id="df44f-874">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-875">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-875"></span></span>|
|<span data-ttu-id="df44f-876">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-877">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-877"></span></span>|
|<span data-ttu-id="df44f-878">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-879">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-879"></span></span>|
|<span data-ttu-id="df44f-880">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-881">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-881"></span></span>|
|<span data-ttu-id="df44f-882">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-882">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-883">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-883"></span></span>|
   
 <span data-ttu-id="df44f-884">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="df44f-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-885">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-885">**Subject**</span></span>|
|<span data-ttu-id="df44f-886">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-886"></span></span>|
|<span data-ttu-id="df44f-887">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-887">**Issuer**</span></span>|
|<span data-ttu-id="df44f-888">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-888"></span></span>|
|<span data-ttu-id="df44f-889">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-889">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-890">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-890"></span></span>|
|<span data-ttu-id="df44f-891">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-891">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-892">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-892"></span></span>|
|<span data-ttu-id="df44f-893">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-894">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-894"></span></span>|
|<span data-ttu-id="df44f-895">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-896">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-896"></span></span>|
|<span data-ttu-id="df44f-897">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-897">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-898">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-898"></span></span>|
|<span data-ttu-id="df44f-899">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-900">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-900"></span></span>|
|<span data-ttu-id="df44f-901">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-902">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-902"></span></span>|
|<span data-ttu-id="df44f-903">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-904">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-904"></span></span>|
|<span data-ttu-id="df44f-905">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-906">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-906"></span></span>|
|<span data-ttu-id="df44f-907">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-908">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-908"></span></span>|
|<span data-ttu-id="df44f-909">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-909">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-910">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-910"></span></span>|
|<span data-ttu-id="df44f-911">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-912">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-912"></span></span>|
   
 <span data-ttu-id="df44f-913">**Microsoft IT TLS CA 1**</span><span class="sxs-lookup"><span data-stu-id="df44f-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-914">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-914">**Subject**</span></span>|
|<span data-ttu-id="df44f-915">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-915"></span></span>|
|<span data-ttu-id="df44f-916">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-916">**Issuer**</span></span>|
|<span data-ttu-id="df44f-917">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-917"></span></span>|
|<span data-ttu-id="df44f-918">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-918">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-919">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-919"></span></span>|
|<span data-ttu-id="df44f-920">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-920">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-921">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-921"></span></span>|
|<span data-ttu-id="df44f-922">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-923">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-923"></span></span>|
|<span data-ttu-id="df44f-924">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-925">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-925"></span></span>|
|<span data-ttu-id="df44f-926">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-926">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-927">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-927"></span></span>|
|<span data-ttu-id="df44f-928">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-929">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-929"></span></span>|
|<span data-ttu-id="df44f-930">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-931">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-931"></span></span>|
|<span data-ttu-id="df44f-932">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-933">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-933"></span></span>|
|<span data-ttu-id="df44f-934">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-935">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-935"></span></span>|
|<span data-ttu-id="df44f-936">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-937">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-937"></span></span>|
|<span data-ttu-id="df44f-938">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-938">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-939">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-939"></span></span>|
|<span data-ttu-id="df44f-940">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-941">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-941"></span></span>|
   
 <span data-ttu-id="df44f-942">**Microsoft IT TLS CA 2**</span><span class="sxs-lookup"><span data-stu-id="df44f-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-943">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-943">**Subject**</span></span>|
|<span data-ttu-id="df44f-944">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-944"></span></span>|
|<span data-ttu-id="df44f-945">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-945">**Issuer**</span></span>|
|<span data-ttu-id="df44f-946">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-946"></span></span>|
|<span data-ttu-id="df44f-947">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-947">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-948">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-948"></span></span>|
|<span data-ttu-id="df44f-949">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-949">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-950">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-950"></span></span>|
|<span data-ttu-id="df44f-951">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-952">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-952"></span></span>|
|<span data-ttu-id="df44f-953">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-954">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-954"></span></span>|
|<span data-ttu-id="df44f-955">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-955">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-956">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-956"></span></span>|
|<span data-ttu-id="df44f-957">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-958">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-958"></span></span>|
|<span data-ttu-id="df44f-959">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-960">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-960"></span></span>|
|<span data-ttu-id="df44f-961">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-962">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-962"></span></span>|
|<span data-ttu-id="df44f-963">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-964">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-964"></span></span>|
|<span data-ttu-id="df44f-965">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-966">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-966"></span></span>|
|<span data-ttu-id="df44f-967">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-967">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-968">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-968"></span></span>|
|<span data-ttu-id="df44f-969">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-970">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-970"></span></span>|
   
 <span data-ttu-id="df44f-971">**Microsoft IT TLS CA 4**</span><span class="sxs-lookup"><span data-stu-id="df44f-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-972">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-972">**Subject**</span></span>|
|<span data-ttu-id="df44f-973">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-973"></span></span>|
|<span data-ttu-id="df44f-974">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-974">**Issuer**</span></span>|
|<span data-ttu-id="df44f-975">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-975"></span></span>|
|<span data-ttu-id="df44f-976">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-976">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-977">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-977"></span></span>|
|<span data-ttu-id="df44f-978">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-978">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-979">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-979"></span></span>|
|<span data-ttu-id="df44f-980">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-981">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-981"></span></span>|
|<span data-ttu-id="df44f-982">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-983">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-983"></span></span>|
|<span data-ttu-id="df44f-984">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-984">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-985">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-985"></span></span>|
|<span data-ttu-id="df44f-986">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-987">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-987"></span></span>|
|<span data-ttu-id="df44f-988">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-989">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-989"></span></span>|
|<span data-ttu-id="df44f-990">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-991">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-991"></span></span>|
|<span data-ttu-id="df44f-992">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-993">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-993"></span></span>|
|<span data-ttu-id="df44f-994">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-995">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-995"></span></span>|
|<span data-ttu-id="df44f-996">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-996">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-997">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-997"></span></span>|
|<span data-ttu-id="df44f-998">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-999">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-999"></span></span>|
   
 <span data-ttu-id="df44f-1000">**Microsoft IT TLS CA 5**</span><span class="sxs-lookup"><span data-stu-id="df44f-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-1001">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-1001">**Subject**</span></span>|
|<span data-ttu-id="df44f-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1002"></span></span>|
|<span data-ttu-id="df44f-1003">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-1003">**Issuer**</span></span>|
|<span data-ttu-id="df44f-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1004"></span></span>|
|<span data-ttu-id="df44f-1005">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-1005">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1006"></span></span>|
|<span data-ttu-id="df44f-1007">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1008"></span></span>|
|<span data-ttu-id="df44f-1009">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1010"></span></span>|
|<span data-ttu-id="df44f-1011">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1012"></span></span>|
|<span data-ttu-id="df44f-1013">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1014"></span></span>|
|<span data-ttu-id="df44f-1015">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1016"></span></span>|
|<span data-ttu-id="df44f-1017">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1018"></span></span>|
|<span data-ttu-id="df44f-1019">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1020"></span></span>|
|<span data-ttu-id="df44f-1021">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1022"></span></span>|
|<span data-ttu-id="df44f-1023">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1024"></span></span>|
|<span data-ttu-id="df44f-1025">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1026"></span></span>|
|<span data-ttu-id="df44f-1027">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1028"></span></span>|
   
 <span data-ttu-id="df44f-1029">**Symantec 類別 3 EV SSL CA G3**</span><span class="sxs-lookup"><span data-stu-id="df44f-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-1030">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-1030">**Subject**</span></span>|
|<span data-ttu-id="df44f-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1031"></span></span>|
|<span data-ttu-id="df44f-1032">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-1032">**Issuer**</span></span>|
|<span data-ttu-id="df44f-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1033"></span></span>|
|<span data-ttu-id="df44f-1034">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="df44f-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="df44f-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1035"></span></span>|
|<span data-ttu-id="df44f-1036">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-1036">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1037"></span></span>|
|<span data-ttu-id="df44f-1038">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1039"></span></span>|
|<span data-ttu-id="df44f-1040">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1041"></span></span>|
|<span data-ttu-id="df44f-1042">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1043"></span></span>|
|<span data-ttu-id="df44f-1044">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1045"></span></span>|
|<span data-ttu-id="df44f-1046">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1047"></span></span>|
|<span data-ttu-id="df44f-1048">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1049"></span></span>|
|<span data-ttu-id="df44f-1050">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1051"></span></span>|
|<span data-ttu-id="df44f-1052">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1053"></span></span>|
|<span data-ttu-id="df44f-1054">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1055"></span></span>|
|<span data-ttu-id="df44f-1056">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1057"></span></span>|
|<span data-ttu-id="df44f-1058">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1059"></span></span>|
   
 <span data-ttu-id="df44f-1060">**Symantec 類別 3 保護伺服器的 CA-G4**</span><span class="sxs-lookup"><span data-stu-id="df44f-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-1061">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-1061">**Subject**</span></span>|
|<span data-ttu-id="df44f-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1062"></span></span>|
|<span data-ttu-id="df44f-1063">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-1063">**Issuer**</span></span>|
|<span data-ttu-id="df44f-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1064"></span></span>|
|<span data-ttu-id="df44f-1065">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="df44f-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="df44f-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1066"></span></span>|
|<span data-ttu-id="df44f-1067">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-1067">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1068"></span></span>|
|<span data-ttu-id="df44f-1069">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1070"></span></span>|
|<span data-ttu-id="df44f-1071">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1072"></span></span>|
|<span data-ttu-id="df44f-1073">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1074"></span></span>|
|<span data-ttu-id="df44f-1075">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1076"></span></span>|
|<span data-ttu-id="df44f-1077">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1078"></span></span>|
|<span data-ttu-id="df44f-1079">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1080"></span></span>|
|<span data-ttu-id="df44f-1081">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1082"></span></span>|
|<span data-ttu-id="df44f-1083">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1084"></span></span>|
|<span data-ttu-id="df44f-1085">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1086"></span></span>|
|<span data-ttu-id="df44f-1087">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1088"></span></span>|
|<span data-ttu-id="df44f-1089">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1090"></span></span>|
   
 <span data-ttu-id="df44f-1091">**thawte SHA256 SSL CA**</span><span class="sxs-lookup"><span data-stu-id="df44f-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-1092">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-1092">**Subject**</span></span>|
|<span data-ttu-id="df44f-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1093"></span></span>|
|<span data-ttu-id="df44f-1094">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-1094">**Issuer**</span></span>|
|<span data-ttu-id="df44f-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1095"></span></span>|
|<span data-ttu-id="df44f-1096">**主體替代名稱**</span><span class="sxs-lookup"><span data-stu-id="df44f-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="df44f-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1097"></span></span>|
|<span data-ttu-id="df44f-1098">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-1098">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1099"></span></span>|
|<span data-ttu-id="df44f-1100">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1101"></span></span>|
|<span data-ttu-id="df44f-1102">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1103"></span></span>|
|<span data-ttu-id="df44f-1104">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1105"></span></span>|
|<span data-ttu-id="df44f-1106">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1107"></span></span>|
|<span data-ttu-id="df44f-1108">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1109"></span></span>|
|<span data-ttu-id="df44f-1110">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1111"></span></span>|
|<span data-ttu-id="df44f-1112">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1113"></span></span>|
|<span data-ttu-id="df44f-1114">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1115"></span></span>|
|<span data-ttu-id="df44f-1116">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1117"></span></span>|
|<span data-ttu-id="df44f-1118">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1119"></span></span>|
|<span data-ttu-id="df44f-1120">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1121"></span></span>|
   
 <span data-ttu-id="df44f-1122">**Verizon Akamai SureServer CA G14 SHA2**</span><span class="sxs-lookup"><span data-stu-id="df44f-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="df44f-1123">**主體**</span><span class="sxs-lookup"><span data-stu-id="df44f-1123">**Subject**</span></span>|
|<span data-ttu-id="df44f-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1124"></span></span>|
|<span data-ttu-id="df44f-1125">**發行者**</span><span class="sxs-lookup"><span data-stu-id="df44f-1125">**Issuer**</span></span>|
|<span data-ttu-id="df44f-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1126"></span></span>|
|<span data-ttu-id="df44f-1127">**序號**</span><span class="sxs-lookup"><span data-stu-id="df44f-1127">**Serial Number**</span></span>|
|<span data-ttu-id="df44f-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1128"></span></span>|
|<span data-ttu-id="df44f-1129">**公用金鑰長度**</span><span class="sxs-lookup"><span data-stu-id="df44f-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="df44f-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1130"></span></span>|
|<span data-ttu-id="df44f-1131">**簽章演算法**</span><span class="sxs-lookup"><span data-stu-id="df44f-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="df44f-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1132"></span></span>|
|<span data-ttu-id="df44f-1133">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="df44f-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1134"></span></span>|
|<span data-ttu-id="df44f-1135">**未完成的有效性**</span><span class="sxs-lookup"><span data-stu-id="df44f-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="df44f-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1136"></span></span>|
|<span data-ttu-id="df44f-1137">**主體金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="df44f-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1138"></span></span>|
|<span data-ttu-id="df44f-1139">**授權金鑰識別碼**</span><span class="sxs-lookup"><span data-stu-id="df44f-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="df44f-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1140"></span></span>|
|<span data-ttu-id="df44f-1141">**憑證指紋 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="df44f-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1142"></span></span>|
|<span data-ttu-id="df44f-1143">**憑證指紋 (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1144"></span></span>|
|<span data-ttu-id="df44f-1145">**Pin (SHA-1 256)**</span><span class="sxs-lookup"><span data-stu-id="df44f-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="df44f-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1146"></span></span>|
|<span data-ttu-id="df44f-1147">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="df44f-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1148"></span></span>|
|<span data-ttu-id="df44f-1149">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="df44f-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1150"></span></span>|
|<span data-ttu-id="df44f-1151">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="df44f-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="df44f-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="df44f-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="df44f-1153">其他憑證路徑</span><span class="sxs-lookup"><span data-stu-id="df44f-1153">Additional certificate paths</span></span>
<span data-ttu-id="df44f-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="df44f-1154"></span></span>

<span data-ttu-id="df44f-1155">下列包含舊版的憑證未含上方並將與上述清單合併一段時間。</span><span class="sxs-lookup"><span data-stu-id="df44f-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
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


