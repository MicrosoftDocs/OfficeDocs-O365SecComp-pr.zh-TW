---
title: 當寄件者被封鎖無法傳送輸出垃圾郵件的範例通知
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: 當服務，因為傳送輸出垃圾郵件，會封鎖寄件者時，網域系統管理員會指定當您設定輸出垃圾郵件原則將會收到類似下列的通知電子郵件：
ms.openlocfilehash: 04d8bde8e9cadd3525191a5bee7d368229e85056
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30691804"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a>當寄件者被封鎖無法傳送輸出垃圾郵件的範例通知

當寄件者封鎖從服務，因為傳送輸出垃圾郵件，指定當您[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)將會收到類似下列的通知電子郵件的網域系統管理員： 
  
 **寄件者地址：** spamalerts@microsoft.com 
  
 **Subject:** 輸出垃圾郵件通知- \<*帳戶名稱*\>封鎖而無法傳送輸出郵件     
  
 **內文：** 這是從 Exchange Online Protection 垃圾郵件分析系統自動的回覆。 
  
因為我們已偵測到大量電子郵件標示為垃圾郵件或其他可疑的行為，來自您的組織，您是正在連絡。 下列的電子郵件帳戶被封鎖無法傳送電子郵件 （他們仍然可以收到電子郵件）：
  
\<*帳戶名稱*  \> 
  
很可能此電子郵件帳戶已遭洩露。 請遵循下列步驟：
  
1. 解決由您一邊此問題：
    
  - 變更帳戶的密碼。
    
  - 決定如何帳戶遭到盜用了。
    
  - 採取預防措施以確保不會在一次利用此弱點。
    
  - 確認所有違規郵件已清除 [外寄郵件佇列。
    
2. 使用一般連絡人管道連絡 Microsoft 支援服務。
    
3. 說明您必須封鎖而無法傳送郵件的使用者，以及已處理的問題。
    
4. 代理程式會使用您提供的資訊，提升其電子郵件地址或解除封鎖的網域建立支援票證。
    
5. 地址已解除鎖定的狀態之後和擱置的任何其他問題，您將連接並發出警示，解除封鎖。
    
感謝您協助我們中控制垃圾電子郵件。
  
Exchange Online Protection。
  
\*\*請注意-請不要回應這封電子郵件時傳送來自不受監控的地址\*\*
  
> [!TIP]
> 您也可以連絡支援透過記載在[說明及支援 eop](eop/help-and-support-for-eop.md)的選項。 
  

