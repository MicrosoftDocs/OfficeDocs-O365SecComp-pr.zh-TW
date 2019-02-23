---
title: 使用進階的 eDiscovery (Preview) 中的通訊
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 92ad9179d5d62fdf25c1ae78e9c367f509bf6ccf
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214253"
---
# <a name="work-with-communications-in-advanced-ediscovery-preview"></a>使用進階的 eDiscovery (Preview) 中的通訊

進階的 eDiscovery （預覽） 可讓法務部門簡化追蹤和散佈合法持有通知繞其程序。Okay 通訊功能可讓管理及自動化其整個合法持有程序-從通知、 提醒、 和呈報-所有集中一處法務部門。

## <a name="what-is-a-legal-hold-notification"></a>什麼是合法持有通知？

合法持有 （也稱為*訴訟保留*） 的注意事項是從組織的法務部門傳送至員工、 臨時員工、 或其他資料 custodians 的通知。這些通知指示 custodians 来保留可儲存的資訊 (ESI) 時可能會與使用中或即將法律專家相關的任何資料。法律小組必須知道每個 okay 已收到、 讀取、 及瞭解並同意遵守的特定指示。

## <a name="the-legal-hold-notification-process"></a>法律保留通知程序

組織有陪審團来保留當它可學習有關即將進行的訴訟暫止或法規調查的相關資訊。為了遵守其保留需求，組織應立即通知潛在 custodians 有關其陪審團来保留相關資訊。 

使用進階的 eDiscovery （預覽）、 法律小組可以建立和自訂其合法持有通知工作流程。Okay 通訊功能可讓法律小組來設定下列通知及工作流程：

1. **發行請注意**： 的合法持有通知會發出 （或起始） 從法務部門通知給 custodians 可能會有區分大小相關的專家的相關資訊。此通知會指示那些 custodians 来保留的探索可能需要的任何資訊。 
   
2.  **回覆發行請注意**： 期間案例 custodians 可能需要保留其他或更少的資訊多於先前所指示。針對此案例，您可以更新現有的保留通知並重新發出至您 custodians。

3.  **請注意版本**： 使資訊已不再保留如果不需要專家已解決且 okay 不再受限於保留陪審團、 後可釋放 okay。此外，您 okay 將會收到通知他們不再下保留陪審團以及如何繼續他們的活動的未完成的指示。

4. **提醒和呈報**： 在某些情況下，只會核發明不足以滿足法律調查需求。每個通知、 法律小組可以排程提醒和呈報自動回應 custodians 的待處理的工作流程的一組。

    - **提醒**： 已核發給或重新發行給一群 custodians 的合法持有通知後，組織可能會設定提醒，提醒在沒有回應 custodians。 

    - **呈報**： 在某些情況下，如果 okay 之後仍留回應甚至是一組的提醒，法律小組可以設定呈報流程通知 okay 和位管理員。

## <a name="role-groups-and-permissions"></a>角色群組和權限 

法律小組可以控制與分割中安全性 & 規範中心使用 eDiscovery 相關的角色群組和權限與其 case 活動。 

若要建立及管理合法持有通知，使用者必須是下列角色群組的一部分：

- **eDiscovery 管理員**此角色群組的成員可以建立與管理 eDiscovery 案例。他們可以新增和移除成員、 放置 custodians 及上的內容位置保留、 管理合法持有通知、 建立及編輯與案例相關聯的內容搜尋、 內容搜尋結果匯出及準備進階的分析中的搜尋結果eDiscovery （預覽）。有兩個此角色群組中的子群組。這些子群組之間的差異根據範圍。

  - **eDiscovery 管理員**-可檢視與管理 eDiscovery 案例所建立或成員。如果另一個 eDiscovery 管理員會建立案例，但不會將第二個 eDiscovery 管理員新增為該案例的成員，第二個 eDiscovery 管理員將無法檢視或在安全性 & 規範中心中開啟 [eDiscovery] 頁面上的大小寫。eDiscovery 管理員也可以存取其進階 eDiscovery (Preview) 執行分析工作中的情況。

  - **eDiscovery 管理員**-可以執行 eDiscovery 管理員可以執行的所有管理工作。此外，eDiscovery 管理員可以：
    
    - 檢視 [eDiscovery] 頁面上列出的所有案例。
    - 管理組織中的任何案例之後他們將自己新增為大小寫的成員。
    - 針對在組織中任何案例的進階 eDiscovery (Preview) 中存取區分大小資料。

如需詳細資訊，請參閱[指派 Office 365 安全性 & 規範中心中的 eDiscovery 權限](../assign-ediscovery-permissions.md)。