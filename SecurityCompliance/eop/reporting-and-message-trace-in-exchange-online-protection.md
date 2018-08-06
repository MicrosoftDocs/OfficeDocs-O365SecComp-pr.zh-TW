---
title: Exchange Online Protection 的報告與訊息追蹤
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 12/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) 提供許多不同的報告，可協助您判斷貴組織的整體狀態與健全狀況。還有可協助您疑難排解特定事件 (例如郵件未抵達其預定收件者) 的工具，以及有助於符合規範需求的稽核報告。下表將說明 EOP 系統管理員可以使用的報告和疑難排解工具。
ms.openlocfilehash: 01a09b2b4b72161352af3793686c6cc888e44e29
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027140"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Exchange Online Protection 的報告與訊息追蹤

Microsoft Exchange Online Protection (EOP) 提供許多不同的報告可協助您決定的整體狀態和組織的狀況。也有工具來協助您疑難排解特定事件 （例如郵件給其預定的收件者無法到達） 和稽核報告來協助規範需求。 

## <a name="usage-reports"></a>使用情況報告

**Office 365 群組活動**檢視建立及使用 Office 365 群組數目的相關資訊。  

**電子郵件活動**檢視傳送、 接收和讀取整個組織中與特定使用者的郵件數目的相關資訊。  

**電子郵件應用程式使用狀況**檢視所使用的電子郵件應用程式的相關資訊。這包括每個應用程式的連線總數和要連線的 Outlook 版本。  

**信箱使用量**檢視所使用的儲存區的相關資訊、 配額使用率、 項目計數及信箱的最後活動 （傳送或讀取的活動）。

請參閱下列資源如需詳細資訊：

- [Office 365 系統管理中心-Office 365 中會報告群組](https://go.microsoft.com/fwlink/p/?linkid=861610) 
- [Office 365 系統管理中心報告的-電子郵件活動](https://go.microsoft.com/fwlink/p/?linkid=859706) 
- [Office 365 系統管理中心報告的-電子郵件應用程式使用狀況](https://go.microsoft.com/fwlink/p/?linkid=859707)
- [Office 365 系統管理中心報告的-信箱使用量](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security-amp-compliance-reports-in-the-office-365-admin-center"></a>安全性&amp;Office 365 系統管理中心中的規範報告

這些增強的報告提供的互動式報表體驗若是 EOP 管理員，包括摘要資訊和向下切入如需詳細資訊的能力。  

**進階威脅保護 (ATP)** 檢視資訊安全連結和安全附件因受到 ATP 的一部分。  

**EOP**檢視有關惡意程式碼偵測、 詐騙的郵件、 垃圾郵件偵測及從您的組織的郵件流程的資訊。  

[檢視進階威脅保護與 Exchange Online Protection 的報告](https://go.microsoft.com/fwlink/p/?linkid=852409) 

##<a name="custom-reports-using-microsoft-graph"></a>使用 Microsoft Graph 的自訂報告

以程式設計方式建立[使用 Microsoft Graph 中的 Office 365 流量報告](https://go.microsoft.com/fwlink/p/?linkid=865135)的副中可用的 Office 365 系統管理中心使用 Microsoft Graph 查看報告 

##<a name="custom-reports-using-reporting-web-services"></a>使用報告 Web 服務的自訂報告

以程式設計方式從可用 Exchange Online Protection PowerShell 使用 REST/ODATA2 查詢篩選報告指令程式建立報表。

請參閱[Office 365 報告 Web 服務](https://go.microsoft.com/fwlink/p/?LinkId=279926) 

##<a name="message-trace"></a>郵件追蹤

當出差經由 EOP，線段電子郵件訊息。您可以決定電子郵件訊息若已接收、 拒絕、 延遲、 或服務所傳送。它也會顯示動作所採取的郵件上之前它達到其最終狀態。  

您可以使用這項資訊來快速回答使用者的問題、 疑難排解郵件流程問題、 驗證原則的變更，並連絡技術支援人員以取得協助的必要性。  

請參閱[追蹤電子郵件](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx) 

## <a name="audit-logging"></a>稽核記錄

追蹤特定對您組織管理員所做的變更。這些報告可協助您疑難排解設定問題或尋找安全性或規範相關問題的原因。 請參閱[在 EOP 中的稽核報告](auditing-reports-in-eop.md) 


## <a name="reporting-and-message-trace-data-availability-and-latency"></a>報告和郵件追蹤資料的可用性與延遲

下表說明可使用 EOP 報告和郵件追蹤資料的時間及時間長短。
  
||||
|:-----|:-----|:-----|
|**報告類型** <br/> |**資料可用時間 (回顧期間)** <br/> |**延遲** <br/> |
|郵件保護摘要報告  <br/> |90 天  <br/> |郵件資料彙總大部分會在 24 到 48 小時內完成。部分次要的增量彙總變更最多存在 5 天。  <br/> |
|郵件保護詳細資料報告  <br/> |90 天  <br/> |針對 7 天內的詳細資料，資料應於 24 小時內出現，但可能要等到 48 小時後才完成。部分次要的增量變更最多存在 5 天。  <br/> 若要檢視超過 7 天之郵件的詳細資料報告，結果可能需要幾個小時。  <br/> |
|郵件追蹤資料  <br/> |90 天  <br/> |針對 7 天內的郵件執行郵件追蹤時，郵件應於 5 到 30 分鐘內出現。  <br/> 針對超過 7 天的郵件執行郵件追蹤時，結果可能需要幾個小時。  <br/> |
   
> [!NOTE]
> 資料可用性和延遲性都相同是否透過 Office 365 系統管理中心或遠端 PowerShell 來要求。 
  

