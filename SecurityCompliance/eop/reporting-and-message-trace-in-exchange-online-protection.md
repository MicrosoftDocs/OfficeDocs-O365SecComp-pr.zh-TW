---
title: Exchange Online Protection 的報告與訊息追蹤
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 12/18/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) 提供許多不同的報告，可協助您判斷貴組織的整體狀態與健全狀況。還有可協助您疑難排解特定事件 (例如郵件未抵達其預定收件者) 的工具，以及有助於符合規範需求的稽核報告。下表將說明 EOP 系統管理員可以使用的報告和疑難排解工具。
ms.openlocfilehash: 0dcacec586408bf98ad4c67c11ae3bde3a8e9315
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154615"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Exchange Online Protection 的報告與訊息追蹤

Microsoft Exchange Online Protection (EOP) 提供許多不同的報告，可協助您判斷貴組織的整體狀態與健全狀況。 還有可協助您疑難排解特定事件 (例如郵件未抵達其預定收件者) 的工具，以及有助於符合規範需求的稽核報告。 

## <a name="usage-reports"></a>使用情況報告

**Office 365 群組活動**檢視所建立和使用 Office 365 群組的數目的相關資訊。  

**電子郵件活動**檢視傳送、 接收和讀取整個組織中與特定使用者的郵件數目的相關資訊。  

**電子郵件 app 使用情況**檢視可用的電子郵件應用程式的相關資訊。 這包括每個應用程式的連線總數以及要連線的 Outlook 版本。  

**信箱使用量**檢視使用儲存的資訊、 配額使用率、 項目計數，以及信箱上次活動 （傳送或讀取的活動）。

請參閱下列資源以取得詳細資訊：

- [在系統管理中心的 Office 365 群組的 office 365 報告](https://go.microsoft.com/fwlink/p/?linkid=861610) 
- [在管理中心中的電子郵件活動的 office 365 報告](https://go.microsoft.com/fwlink/p/?linkid=859706) 
- [在管理中心中的電子郵件 app 使用情況的 office 365 報告](https://go.microsoft.com/fwlink/p/?linkid=859707)
- [在系統管理中心的 [信箱使用量的 office 365 報告](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security-amp-compliance-reports-in-the-microsoft-365-admin-center"></a>安全性&amp;Microsoft 365 系統管理中心中的規範符合性報告

這些增強型的報告可提供享有互動報告體驗若是 EOP 管理員，其中包含摘要資訊，並向下切入如需詳細資訊的能力。  

**進階威脅防護 (ATP)** 檢視安全連結和屬於 ATP 安全附件相關的資訊。  

**EOP**檢視有關惡意程式碼偵測、 詐騙的郵件、 垃圾郵件偵測和進出組織的郵件流程的資訊。  

[進階威脅防護和 Exchange Online Protection 的檢視報告](https://go.microsoft.com/fwlink/p/?linkid=852409) 

##<a name="custom-reports-using-microsoft-graph"></a>使用 Microsoft Graph 的自訂報告

以程式設計方式建立子主題的<b0>使用中 Microsoft Graph 的 Office 365 使用情況報告</b0>中可用的 Microsoft 365 系統管理中心使用 Microsoft Graph 請參閱 < 的報告 

##<a name="custom-reports-using-reporting-web-services"></a>使用報告的自訂報告 web 服務

以程式設計方式從可用 Exchange Online Protection PowerShell 報告指令程式使用 REST/ODATA2 查詢篩選來建立報告。

請參閱[Office 365 報告 Web 服務](https://go.microsoft.com/fwlink/p/?LinkId=279926) 

##<a name="message-trace"></a>訊息追蹤

在電子郵件通過 EOP 時進行追蹤。 您可以判斷服務是否接收、拒絕、延遲或傳遞電子郵件。 它也會顯示是對郵件所採取的行動之前它達到其最終狀態。  

您可以使用此資訊來有效回答使用者的問題、 疑難排解郵件流程問題、 驗證原則變更，並此舉可連絡技術支援尋求協助。  

請參閱[追蹤電子郵件](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx) 

## <a name="audit-logging"></a>稽核記錄

追蹤由系統管理員對組織所做的特定變更。 這些報告可協助您疑難排解組態問題，或找出安全性或法規遵循相關問題的原因。  請參閱[EOP 中的稽核報告](auditing-reports-in-eop.md) 


## <a name="reporting-and-message-trace-data-availability-and-latency"></a>報告和郵件追蹤資料的可用性與延遲

下表說明可使用 EOP 報告和郵件追蹤資料的時間及時間長短。
  
||||
|:-----|:-----|:-----|
|**報告類型** <br/> |**資料可用時間 (回顧期間)** <br/> |**延遲** <br/> |
|郵件保護摘要報告  <br/> |90 天  <br/> |郵件資料彙總大部分會在 24 到 48 小時內完成。部分次要的增量彙總變更最多存在 5 天。  <br/> |
|郵件保護詳細資料報告  <br/> |90 天  <br/> |針對 7 天內的詳細資料，資料應於 24 小時內出現，但可能要等到 48 小時後才完成。部分次要的增量變更最多存在 5 天。  <br/> 若要檢視超過 7 天之郵件的詳細資料報告，結果可能需要幾個小時。  <br/> |
|郵件追蹤資料  <br/> |90 天  <br/> |針對 7 天內的郵件執行郵件追蹤時，郵件應於 5 到 30 分鐘內出現。  <br/> 針對超過 7 天的郵件執行郵件追蹤時，結果可能需要幾個小時。  <br/> |
   
> [!NOTE]
> 資料可用性和延遲是相同的是否要求透過 Microsoft 365 系統管理中心或遠端 PowerShell。 
  

