---
title: 使用進階電子文件 （預覽） 中的通訊
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 916691e1f2470ef9e9e54d9dfe06c5277a92ba53
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241250"
---
# <a name="work-with-communications-in-advanced-ediscovery-preview"></a>使用進階電子文件 （預覽） 中的通訊

進階電子文件 （預覽） 可讓法務部門，以簡化繞追蹤和散佈合法持有通知其處理程序。 Custodian 通訊功能可讓法務部門來管理及自動化其整個合法持有的程序-通知、 提醒和呈報-全部在同一個位置。

## <a name="what-is-a-legal-hold-notification"></a>合法持有通知是什麼？

合法持有 （也稱為*訴訟資料暫留*） 通知是寄送給從組織的法務部門的員工、 臨時員工、 或其他資料 custodians 通知。 這些通知指示 custodians 來保留電子儲存的資訊 (ESI)，以及任何可能會與使用中或即將發生的法律專家相關的材料。 法律小組必須知道每個 custodian 已接收、 讀取、 並瞭解並同意遵守的特定指示。

## <a name="the-legal-hold-notification-process"></a>法律保留通知程序

組織有責任保留的相關資訊，當它了解即將發生訴訟資料暫留或法規的調查。 為了遵守其保留需求，組織應該立即通知潛在 custodians 其陪審團来保留的相關資訊。 

使用進階電子文件 （預覽），法務小組可以建立並自訂其合法持有通知工作流程。 Custodian 通訊功能可以讓法務小組設定下列通知及工作流程：

1. **發行請注意**： 合法持有通知是發出 （或起始） 從法務部門通知給 custodians 可能擁有案例專家的相關資訊。 此通知會指示這些 custodians 保留探索，可能需要的任何資訊。 
   
2.  **重新發行請注意**： 期間情況下，custodians 可能需要保留其他或較少的資訊比已之前的指示。 此案例中，您可以更新現有的保留通知，並重新發出到您 custodians。

3.  **版本請注意**： 以便資訊已不再保留如果不需要一旦專家會解析，並保留陪審團不再受到 custodian，可釋放 custodian。 此外，您 custodian 將會收到通知他們，而不會再下保留陪審團待處理的指示，需如何繼續他們的活動。

4. **提醒和呈報**： 在某些情況下，只發出通知不足以滿足法律需求。 與每個通知法務小組可以排程提醒和呈報工作流程，以自動停止回應 custodians 的待處理一組。

    - **提醒**： 已發出或重新發行給一群 custodians 合法持有通知之後，組織可能會設定提醒，提醒回應 custodians。 

    - **擴大**： 在某些情況下，如果 custodian 保持為一組的提醒，即使後沒有回應法律小組可以設定呈報流程通知 custodian 和其主管。

## <a name="role-groups-and-permissions"></a>角色群組和權限 

法律小組可以控制和分割他們使用安全性 & 合規性中心的 eDiscovery 相關的角色群組和權限的案例活動。 

若要建立及管理合法持有通知，使用者必須是下列角色群組的一部分：

- **eDiscovery 管理員**這個角色群組的成員可以建立及管理 eDiscovery 案例。 他們可以新增和移除成員，放置 custodians 及內容的位置上保留、 管理合法持有通知、 建立及編輯與案例相關聯的內容搜尋、 匯出內容搜尋結果，以及準備進階中分析的搜尋結果eDiscovery （預覽）。 有兩個此角色群組中的子群組。 這些子群組之間的差異根據範圍。

  - **eDiscovery 管理員**-可檢視及管理 eDiscovery 案例他們建立或成員。 如果其他 eDiscovery 管理員會建立案例，但不會將第二個 eDiscovery 管理員新增為該案例的成員，第二個 eDiscovery 管理員無法檢視或在安全性 & 合規性中心中開啟 [eDiscovery] 頁面上的案例。 eDiscovery 管理員也可以存取其進階電子文件 （預覽） 來執行分析工作中的案例。

  - **eDiscovery 系統管理員**-可以執行 eDiscovery 管理員可以執行的所有案例的管理工作。 此外，eDiscovery 系統管理員可以：
    
    - 檢視 [eDiscovery] 頁面上列出的所有案例。
    - 在自行新增為案例的成員之後管理組織中的任何案例。
    - 存取進階電子文件 （預覽） 的組織中任何案例中的案例資料。

如需詳細資訊，請參閱[指派 Office 365 安全性 & 合規性中心中的 eDiscovery 權限](../assign-ediscovery-permissions.md)。