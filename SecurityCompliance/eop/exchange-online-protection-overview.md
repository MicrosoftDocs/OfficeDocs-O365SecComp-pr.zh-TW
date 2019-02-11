---
title: Exchange Online Protection 概觀
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 01/31/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: Microsoft Exchange Online Protection (EOP) 是雲端式的電子郵件篩選服務，它能協助組織抵禦垃圾郵件和惡意軟體，同時也包括預防組織發生訊息原則違規的功能。
ms.openlocfilehash: 16f2f423b6e517cf204e4b4f6a2949baebfd6223
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29686362"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection 概觀

Microsoft Exchange Online Protection (EOP) 是雲端式的電子郵件篩選服務，它能協助組織抵禦垃圾郵件和惡意程式碼，同時也包括預防組織發生訊息原則違規的功能。EOP 能簡化訊息環境的管理，減輕維護內部部署硬體和軟體所衍生的繁重負擔。
  
下列是您可以使用 EOP 來保護郵件的主要方法：
  
- **在獨立案例**EOP 提供雲端式電子郵件保護您的內部部署 Microsoft Exchange Server 2013 環境、 舊式 Exchange Server 版本，或任何其他內部部署 SMTP 電子郵件解決方案。 
    
- **作為 Microsoft Exchange Online 的一部分** 根據預設，EOP 會保護 Microsoft Exchange Online 雲端託管信箱。 
    
- **在混合部署中** EOP 可以設定為保護您的郵件環境，並在您混合使用內部部署及雲端信箱時控制郵件路由傳送。 
    
## <a name="how-eop-works"></a>EOP 的運作方式

若要了解 EOP 的運作方式，查看它如何處理傳入電子郵件很有幫助：
  
![EOP 電子郵件處理](../media/EOP-email-processing.png)
  
內送郵件一開始會通過連線篩選，以檢查寄件者信譽，並會檢查惡意程式碼的郵件。大部分的垃圾郵件此時停止然後由刪除 EOP。郵件延續到原則篩選根據您建立或範本中強制執行自訂的傳輸規則進行計算的郵件。例如，您可以從特定的寄件者的郵件送達時而傳送通知給管理員的規則。（資料遺失防護檢查也會發生此時，如果您有功能 ； 功能可用性的相關資訊，請參閱[Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619)。）接下來，郵件通過內容篩選出內容中檢查有專門用語或一般內容垃圾郵件。是內容篩選的垃圾郵件可傳送至使用者的垃圾郵件] 資料夾或隔離區之間其他選項，根據您的設定決定一則訊息。郵件通過這些保護層級的所有成功後，它會傳送到收件者。
  
### <a name="eop-datacenters"></a>EOP 資料中心

EOP 會在用於提供最佳可用性的全球資料中心網路上執行。例如，如果資料中心變成無法使用，則會將電子郵件自動路由傳送至其他資料中心，而不會中斷服務。每一個資料中心的伺服器都會代表您接受郵件，在您的組織與網際網路之間提供隔離層，進而減少伺服器上的負載。透過這個高可用性的網路，Microsoft 可以確保電子郵件及時送達您的組織。 
  
EOP 會在資料中心之間執行負載平衡，但只在一個區域內。如果您佈建在一個區域中，則會以該區域的郵件路由來處理您的所有郵件。下列清單顯示 EOP 資料中心的地區郵件路由運作方式：
  
    
- 在歐洲、中東和非洲 (EMEA)，所有 Exchange Online 信箱都位於 EMEA 資料中心，且所有郵件都透過 EMEA 資料中心傳送供 EOP 篩選。
    
- 在亞太地區 (APAC)，所有的 Exchange Online 信箱都位於 APAC 資料中心，但郵件目前都透過 EOP 篩選 APAC 資料中心。
=======
- 美洲中所有的 Exchange Online 信箱位於 US 資料中心，除了南美洲可用巴西和智利中的資料中心及加拿大可用資料中心來 Canada 中。所有的電子郵件訊息的客戶南美洲和加拿大包括訊息都被透過 EOP 篩選; 本機資料中心quaratined 電子郵件會儲存在用戶所在的資料中心。
    
- 在歐洲、中東和非洲 (EMEA)，所有 Exchange Online 信箱都位於 EMEA 資料中心，且所有郵件都透過 EMEA 資料中心傳送供 EOP 篩選。
    
- 在亞太地區 (APAC)，所有的 Exchange Online 信箱都位於 APAC 資料中心和訊息目前都透過 EOP 篩選 APAC 資料中心。
    
- 至於政府社群雲端 (GCC)，所有 Exchange Online 信箱都位於美國資料中心，且所有郵件都透過美國資料中心傳送供 EOP 篩選。
    
## <a name="eop-plans-and-features"></a>EOP 方案和功能

以下是可用的 EOP 訂閱方案：
  
- **EOP 獨立** EOP 會保護您的內部部署信箱。 
    
- **Exchange Online 中的 EOP 功能** EOP 會保護您的 Exchange Online 雲端託管信箱。 
    
- **Exchange Enterprise CAL with Services** EOP 會保護您的內部部署信箱 (如 EOP 獨立版)，並包含資料外洩防護 (DLP) 和使用 Web 服務的報告。 
    
如需所有 EOP 訂閱方案之需求、重要限制和功能可用性的相關資訊，請參閱 [Exchange Online Protection 服務描述](https://go.microsoft.com/fwlink/p/?LinkId=320619)。
  
## <a name="setting-up-eop"></a>設定 EOP

設定 EOP 可以很簡單，對於具有一些符合性規則的小型組織來說，更是如此。不過，如果您的組織是具有多個網域、自訂符合性規則或混合郵件流程的大型組織，則在進行設定時可能需要更加詳盡的規劃及更多的時間。
  
如果已購買 EOP，請參閱[設定 EOP 服務](set-up-your-eop-service.md)，以確保完成所有必要的 EOP 設定步驟，來保護郵件環境。 
  
## <a name="for-more-information"></a>相關資訊

[EOP 功能](eop-features.md)
  
[EOP 快速入門影片](videos-for-getting-started-with-eop.md)
  
[EOP 一般常見問題集](eop-general-faq.md)
  
[EOP 排入佇列、延後和退回的訊息常見問題集](eop-queued-deferred-and-bounced-messages-faq.md)
  
[委派管理常見問題集](delegated-administration-faq.md)
  
[將網域及設定從某個 EOP 組織移到另一個 EOP 組織](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
  

