---
title: Office 365 Yammer Enterprise 存取控制
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 摘要： 簡短摘要有關 Yammer Enterprise 存取控制項實際執行環境中。
ms.openlocfilehash: 33126ee6acf42a97148c12917855535a8578e8cf
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090725"
---
# <a name="yammer-enterprise-access-controls"></a>Yammer 企業存取控制 

Yammer 實際執行環境的實體和邏輯存取僅限於到非常小的一段人員 （基礎結構和作業）。與其他 Office 365 工程師，Yammer 工程師有零出位置的存取權的客戶資料。必須使用類似 Lockbox、 核准型剛剛-時間存取控制系統要求存取和核准者數目有限。核准者確認要求 （例如，其驗證要求是合法根據需要、 業務案例、 時間、 等），再核准或拒絕要求。如果核准要求、 JIT 存取會授與定義及有限的時間之後, 自動過期。 

與其他 Office 365 服務，Yammer 實際執行環境的所有存取如何都運用多重要素驗證。所有存取和命令歷程記錄是對應到的使用者記錄和定期檢閱 Yammer 安全性小組。

如需 Yammer 系統管理與管理的詳細資訊，請參閱[Yammer 系統說明](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)。