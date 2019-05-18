---
title: EOP 中的郵件流程
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/13/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: 若為 Exchange Online Protection (EOP) 客戶，傳送到貴組織的所有郵件會先通過 EOP，您的背景工作才會看見這些郵件。不論透過 Exchange Online 在雲端託管所有的信箱，或將信箱託管於內部部署環境 (稱為獨立案例)，或者繼續利用現有的基礎結構，您都可以在即將通過 EOP 進行處理的郵件路由傳送到您的背景工作收件匣之前，先選擇如何路由傳送這些郵件。
ms.openlocfilehash: b19db691304efeccfffa245d61f367f7b653739a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150175"
---
# <a name="mail-flow-in-eop"></a>EOP 中的郵件流程

若為 Exchange Online Protection (EOP) 客戶，傳送到貴組織的所有郵件會先通過 EOP，您的背景工作才會看見這些郵件。不論透過 Exchange Online 在雲端託管所有的信箱，或將信箱託管於內部部署環境 (稱為獨立案例)，或者繼續利用現有的基礎結構，您都可以在即將通過 EOP 進行處理的郵件路由傳送到您的背景工作收件匣之前，先選擇如何路由傳送這些郵件。
  
您可以設定自訂郵件路由，使您的郵件傳遞方式符合業務需求。例如，您可以透過原則篩選裝置傳遞所有的輸出郵件。 
  
## <a name="working-with-messages-and-message-access-options"></a>使用郵件和郵件存取選項

EOP 對您的郵件路由傳送方式提供了很大的彈性。下列主題說明郵件流程處理序中的步驟。
  
[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx) 描述「目錄架構邊緣封鎖」功能，可讓您拒絕服務周邊網路處之無效收件者的郵件。 
  
[檢視] 或 [Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)說明如何管理與您的 EOP 服務相關聯的網域。 
  
如果您新增子網域至組織，則 EOP 服務也可以協助您管理這些子網域。若要深入了解子網域，請參閱 [Enable Mail Flow for Subdomains in Exchange Online](http://technet.microsoft.com/library/4033a30a-f506-481c-8ef0-fd9a0508ae38.aspx)。
  
[Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx)簡介連接器並說明如何使用 EOP 連結器自訂郵件路由。案例包括確保與合作夥伴組織進行安全通訊及設定智慧主機。 
  
若要確保垃圾電子郵件才能正確路由至每位使用者的垃圾郵件] 資料夾，您必須執行幾個設定步驟。 詳細說明這些[確定垃圾郵件會路由傳送至每位使用者的垃圾郵件] 資料夾](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 如果您不想要將郵件移至每位使用者的垃圾郵件] 資料夾，您可以藉由編輯您的內容篩選原則，在 Exchange 系統管理中心選擇另一個巨集指令。 如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](../configure-your-spam-filter-policies.md)。
  
## <a name="verify-mail-flow"></a>驗證郵件流程

若要驗證 EOP 設定是否正確運作，包括連接器組態，請參閱[設定 EOP 服務](set-up-your-eop-service.md)中的「如何知道這是否正常運作？」一節。 
  
[Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)提供了測試郵件流程是否設定正確的指示。 
  

