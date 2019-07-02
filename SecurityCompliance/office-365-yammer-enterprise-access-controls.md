---
title: Office 365 Yammer 企業版存取控制
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '摘要: 在實際執行環境中, Yammer 企業存取控制的簡短摘要。'
ms.openlocfilehash: ec1a5767495b6b183ceda2af558cbec0c479e956
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622313"
---
# <a name="yammer-enterprise-access-controls"></a>Yammer 企業存取控制 

對 Yammer 實際執行環境的實體和邏輯存取權僅限於一小部分人員 (基礎結構和作業)。 就像其他 Office 365 工程師一樣, Yammer 工程師也無法存取客戶資料。 您必須使用受核准的即時存取控制系統要求存取, 類似于擁有者人數有限的密碼箱。 核准者會驗證要求 (例如, 他們會根據需求、業務案例、時間等來驗證要求是否合法, 然後核准或拒絕要求。 如果要求受到核准, 就會將 JIT 存取授與已定義和有限的時間。 超過存取時間之後, access 會自動到期。

就像其他 Office 365 服務一樣, Yammer 實際執行環境的所有存取都使用多重要素驗證。 所有存取和命令歷程記錄都是由 Yammer 安全小組所交, 並定期進行記錄和檢查。

如需 Yammer 管理和管理的詳細資訊, 請參閱[Yammer 系統管理](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)說明。