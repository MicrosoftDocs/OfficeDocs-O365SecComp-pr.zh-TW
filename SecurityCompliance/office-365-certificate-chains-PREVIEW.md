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
# <a name="office-365-certificate-chains"></a>Office 365 憑證鏈結

Office 365 如何運用不同的憑證提供者的數目。下面會說明客戶存取 Office 365 時可能會遇到的已知 Office 365 根憑證的完整清單。在憑證上的資訊可能需要將安裝在您自己的基礎結構中，請參閱[第三方 SSL 憑證的 Office 365 計劃](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce)。下列的憑證資訊適用於所有的 Office 365 的全球和雲端執行個體。
  

|**憑證類型**|**P7b 下載 （英文）**|**CRL 端點**|**OCSP 端點**|**AIA 端點**|
|:-----|:-----|:-----|:-----|:-----|
|[公開受信任的根憑證](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[Office 365 根憑證組合 (P7B)](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |crl.globalsign.net  <br/> www.d-trust.net  <br/> |不適用  <br/> |不適用  <br/> |
|[公開信任中繼憑證](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[Office 365 中繼憑證組合 (P7B)](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |cdp1.public trust.com  <br/> crl.cnnic.cn  <br/> crl.entrust.net  <br/> crl.globalsign.com  <br/> crl.globalsign.net  <br/> crl.identrust.com  <br/> crl.thawte.com  <br/> crl3.digicert.com  <br/> crl4.digicert.com  <br/> s1.symcb.com  <br/> www.d-trust.net  <br/> |isrg.trustid.ocsp.identrust.com  <br/> ocsp.digicert.com  <br/> ocsp.entrust.net  <br/> ocsp.globalsign.com  <br/> ocsp.omniroot.com  <br/> ocsp.startssl.com  <br/> ocsp.thawte.com  <br/> ocsp2.globalsign.com  <br/> ocspcnnicroot.cnnic.cn  <br/> 根-c3-ca2-2009.ocsp.d-trust.net  <br/> root-c3-ca2-ev-2009.ocsp.d-trust.net  <br/> s2.symcb.com  <br/> |aia.startssl.com  <br/> apps.identrust.com  <br/> cacert.omniroot.com  <br/> www.cnnic.cn  <br/> |
   
展開根目錄與以下以查看憑證提供者相關的其他詳細資料的中階章節。
  
## <a name="office-365-root-certificate-details"></a>Office 365 根憑證的詳細資訊
<a name="RootCerts"> </a>

 **Baltimore CyberTrust Root**
  
|:-----|
|**主體**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
   
 **CNNIC 根目錄**
  
||
|:-----|
|**主體**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
   
 **DigiCert 通用的根 CA**
  
||
|:-----|
|**主體**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
   
 **DigiCert 高保證 EV 根 CA**
  
||
|:-----|
|**主體**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
   
 **D 信任根類別 3 CA 2 2009**
  
||
|:-----|
|**主體**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
   
 **D 信任根類別 3 CA 2 EV 2009**
  
||
|:-----|
|**主體**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
   
 **DST 根 CA X3**
  
||
|:-----|
|**主體**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
   
 **過程錄影根憑證授權單位-G2**
  
||
|:-----|
|**主體**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
   
 **Entrust.net Certification Authority (2048)**
  
||
|:-----|
|**主體**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
   
 **GlobalSign**
  
||
|:-----|
|**主體**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
   
 **GlobalSign Root CA**
  
||
|:-----|
|**主體**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
   
 **thawte 主要的根 CA-G3**
  
||
|:-----|
|**主體**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
   
 **VeriSign 類別 3 主要的公用憑證授權單位-G5**
  
||
|:-----|
|**主體**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
   
## <a name="office-365-intermediate-certificate-details"></a>Office 365 中繼憑證的詳細資訊
<a name="IntermediateCerts"> </a>

 **CNNIC SHA256 SSL**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**AIA Url**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **D 信任 SSL 類別 3 CA 1 2009**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**主體替代名稱**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **D 信任 SSL 類別 3 CA 1 EV 2009**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**主體替代名稱**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **DigiCert 雲端服務 CA-1**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **DigiCert SHA2 高保證伺服器 CA**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **DigiCert SHA2 保護伺服器的 CA**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **過程錄影憑證授權單位-L1C**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **過程錄影憑證授權單位-L1K**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **GlobalSign**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **GlobalSign 擴充驗證 CA-SHA256-G2**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **GlobalSign 擴充驗證 CA-SHA256-G3**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **GlobalSign 組織驗證 CA-SHA256-G2**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **GlobalSign 組織驗證 CA-SHA256-G2**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **我們加密授權 X3**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**AIA Url**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Microsoft IT SSL SHA2**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
   
 **Microsoft IT SSL SHA2**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Microsoft IT TLS CA 1**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Microsoft IT TLS CA 2**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Microsoft IT TLS CA 4**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Microsoft IT TLS CA 5**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Symantec 類別 3 EV SSL CA G3**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**主體替代名稱**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Symantec 類別 3 保護伺服器的 CA-G4**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**主體替代名稱**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **thawte SHA256 SSL CA**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**主體替代名稱**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Verizon Akamai SureServer CA G14 SHA2**
  
||
|:-----|
|**主體**|
|:-----|
|**發行者**|
|:-----|
|**序號**|
|:-----|
|**公用金鑰長度**|
|:-----|
|**簽章演算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**未完成的有效性**|
|:-----|
|**主體金鑰識別碼**|
|:-----|
|**授權金鑰識別碼**|
|:-----|
|**憑證指紋 (sha-1)**|
|:-----|
|**憑證指紋 (SHA-1 256)**|
|:-----|
|**Pin (SHA-1 256)**|
|:-----|
|**AIA Url**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
## <a name="additional-certificate-paths"></a>其他憑證路徑
<a name="IntermediateCerts"> </a>

下列包含舊版的憑證未含上方並將與上述清單合併一段時間。
  
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


