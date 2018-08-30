---
title: 垃圾郵件和大量電子郵件有什麼不同?
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/7/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
description: 客戶 askwhat 有時的垃圾郵件與大量電子郵件的差異吗？本主題的目的是以說明的差異並提供兩者在 Exchange Online 和 Exchange Online Protection (EOP) 中的不同選項的相關資訊。
ms.openlocfilehash: 87f946c7309589595efd3e11e998e0a9f503b651
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003152"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>垃圾郵件和大量電子郵件有什麼不同?

客戶有時會問「垃圾郵件和大量電子郵件有什麼不同?」。本主題旨在說明其中差異，並提供關於 Exchange Online 和 Exchange Online Protection (EOP) 中針對這兩種郵件而提供之不同選項的資訊。
  
 **什麼是垃圾郵件？**
  
垃圾郵件是一種「垃圾」郵件，即服務所篩選的來路不明 (通常是不想要的) 電子郵件。服務預設會根據傳送端 IP 位址的信譽來拒絕垃圾郵件。不過，郵件如果通過 IP 檢查、但被內容篩選分類為垃圾郵件，則會傳送至預定收件者的 [垃圾郵件] 資料夾。 
  
> [!NOTE]
> 在經過內容篩選的郵件上執行的動作所述[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)是可透過 Exchange 系統管理中心 (EAC) 中的內容篩選原則設定。此外，如果您使用的垃圾郵件分類不同意，您可以報告您考慮為垃圾郵件或非垃圾郵件給 Microsoft 的數種方式[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件訊息給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)中所述的郵件。 
  
 **什麼是大量電子郵件？**
  
大量電子郵件 (也稱為灰色郵件) 是一種較難分類出來的電子郵件類型。不像垃圾郵件是一種持續性威脅，大量電子郵件通常不太包含會重傳的廣告或行銷訊息。有些使用者想要大量電子郵件 (事實上，他們可能刻意登記要收到這些郵件)，有些使用者則認為這類郵件是垃圾郵件。例如，有些使用者想要收到 Contoso Corporation 寄來的廣告電子郵件或未來某個網路安全大會的邀請，有些使用者則認為這類電子郵件是垃圾郵件。
  
## <a name="how-to-manage-bulk-email"></a>如何管理大量電子郵件

要如何管理大量電子郵件，這並不是個非黑即白的決策，因為如果將所有大量電子郵件都分類為垃圾郵件，則想要它的使用者可能會抱怨並將它提交成誤標記為垃圾郵件的誤判 (非垃圾郵件) 郵件。另一方面，如果讓所有大量電子郵件都通過，則不想要它的使用者可能會抱怨並將它提交成誤進收件匣的漏擋垃圾郵件 (誤判正常)。
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a>啟用大量郵件敏感度控制項中的內容篩選原則

根據大量電子郵件訊息的公司的原則，系統管理員可以選取要指派大量電子郵件的閾值。設定為可透過在 EAC 中的內容篩選原則設定。請參閱[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)） 的步驟。您可以從 1-9，其中 1 會標示為垃圾郵件，大部分的大量電子郵件和 9 允許大部分的大量電子郵件傳遞選擇臨界值設定。服務再執行設定的動作，例如將郵件傳送給收件者的垃圾郵件] 資料夾。 
  

