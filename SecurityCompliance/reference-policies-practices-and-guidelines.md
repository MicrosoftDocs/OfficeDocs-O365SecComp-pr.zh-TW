---
title: 參考 （英文） 原則、 做法，以及指導方針
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
description: Microsoft 開發各種原則、 程序，而且採用數個業界最佳作法，協助保護我們使用者從粗俗、 不想要或惡意的電子郵件。
ms.openlocfilehash: 436f564f20d579c56197563c7bfac3ef903be750
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026270"
---
# <a name="reference-policies-practices-and-guidelines"></a>參照： 原則、 做法，以及指導方針
  
Microsoft 致力於協助網路上提供的最受信任的使用者經驗。因此，Microsoft 開發各種原則、 程序，而且採用數個業界最佳作法，協助保護我們使用者從粗俗、 不想要或惡意的電子郵件。嘗試傳送至 Office 365 使用者的電子郵件的寄件者應確保它們完全了解，而且會遵循本文以協助在此工作，並協助避免潛在的傳遞問題的指導。
  
如果您不符合這些原則和指導方針，它不可能的可協助您 「 支援小組。如果您您依照準則、 做法，以及本文所述的原則，仍然發生傳送的 IP 位址為基礎的傳遞問題，請遵循的步驟來送出 delisting 要求。指示，請參閱[使用 delist 入口網站來將自己從 Office 365 封鎖的寄件者清單中移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。
  
## <a name="general-microsoft-policies"></a>一般 Microsoft 原則
<a name="GenMsftPolicies"> </a>

電子郵件傳送至 Office 365 使用者必須符合管理電子郵件傳輸和 Office 365 使用的所有 Microsoft 原則。
  
- 適用於 Office 365; 服務中的條款特別是針對使用垃圾郵件或散佈惡意程式碼服務禁止
    
- [Microsoft 服務合約](https://www.microsoft.com/servicesagreement/)
    
## <a name="governmental-regulations"></a>政府法規
<a name="GovtRegulations"> </a>

電子郵件傳送至 Office 365 使用者必須遵守所有適用的法律與管理適用於管轄中的電子郵件通訊的規定。
  
- [可以垃圾郵件 Act: 規範 Guide for Business](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)
    
- [「 移除我 」 回應及職責： 電子郵件上月必須受限於"取消訂閱"的宣告](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)
    
## <a name="technical-guidelines"></a>技術指導方針
<a name="TechGuidelines"> </a>

適用的建議下列文件中所列 （部分連結是只適用於英文版） 均應遵循電子郵件傳送給 Office 365。
  
- [SMTP Mta RFC 2505： 反垃圾郵件建議](https://www.ietf.org/rfc/rfc2505.txt)
    
- [為命令管線 RFC 2920： SMTP 服務延伸模組](https://www.ietf.org/rfc/rfc2920.txt)
    
此外，連線至 Office 365 的電子郵件伺服器必須遵守下列需求：
  
- 寄件者預期會符合所有技術的網際網路電子郵件傳輸標準發佈的網際網路協會的網際網路工程工作強制 (IETF)，包括 RFC 5321、 RFC 5322 及其他。 
    
- 授與 500 與 599 （也稱為永久性的未傳遞回應或 NDR） 之間數值 SMTP 錯誤回應程式碼後，請寄件者必須不嘗試重新傳輸到該收件者的郵件。
    
- 多個非傳遞回應後，寄件者必須停止進一步嘗試傳送電子郵件給該收件者。
    
- 郵件未必須傳送到不安全的電子郵件轉送或 proxy 伺服器。
    
- 取消訂閱，從個別清單或寄件者所主控的所有清單的機制必須清楚記載並更容易尋找及使用的收件者。
    
- 不會接受來自動態 IP 空間的連線。
    
- 電子郵件伺服器必須具備有效的反向 DNS 記錄。
    
## <a name="reputation-management"></a>信譽管理
<a name="RepManagement"> </a>

寄件者、 ISP，與其他服務提供者應主動管理信譽的輸出的 IP 位址。
  
## <a name="office-365-limits"></a>Office 365 的限制
<a name="sectionSection4"> </a>

[Exchange Online Protection Limits](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx)中所列的 Office 365 限制必須依照寄件者。
  
## <a name="email-delivery-resources-and-organizations"></a>電子郵件傳遞資源和組織
<a name="sectionSection5"> </a>

Microsoft 主動搭配產業本文和服務提供者以改善網際網路和電子郵件生態系統。這些組織已發佈之我們支援和建議的寄件者遵守最佳作法是文件。這可改善能夠全球各地傳遞數個電子郵件服務提供者之間的電子郵件。
  
- [郵件的惡意程式碼 Mobile 反不當使用的工作群組](https://www.m3aawg.org/)
    
- [線上信任的同盟關係](https://www.otalliance.org/resources)
    
- [寄件者的電子郵件&amp;提供者聯盟](http://www.espcoalition.org/)
    
## <a name="abuse-and-spam-reporting"></a>不當使用和垃圾郵件報告
<a name="AbuseSpamReports"> </a>

報告非法、 粗俗、 不想要或惡意的電子郵件，請[垃圾郵件和網路釣魚詐騙在網路上的 Outlook 中的報表](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)。傳送這些類型的通訊是 Microsoft 原則的違規與適當的動作會採取確認報表上。
  
## <a name="law-enforcement"></a>執法機構
<a name="sectionSection7"> </a>

如果您是執法機構的成員，且想要提供有關 Office 365 的法律文件與 Microsoft Corporation 或如果您有法律文件的相關問題已提交給 Microsoft，請呼叫 (1) (425) 722-1299。
  

