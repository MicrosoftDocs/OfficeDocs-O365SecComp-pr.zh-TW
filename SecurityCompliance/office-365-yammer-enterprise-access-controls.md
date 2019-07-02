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
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="87898-103">Yammer 企業存取控制</span><span class="sxs-lookup"><span data-stu-id="87898-103">Yammer Enterprise Access Controls</span></span> 

<span data-ttu-id="87898-104">對 Yammer 實際執行環境的實體和邏輯存取權僅限於一小部分人員 (基礎結構和作業)。</span><span class="sxs-lookup"><span data-stu-id="87898-104">Physical and logical access to the Yammer production environment is restricted to a small set of people (infrastructure and operations).</span></span> <span data-ttu-id="87898-105">就像其他 Office 365 工程師一樣, Yammer 工程師也無法存取客戶資料。</span><span class="sxs-lookup"><span data-stu-id="87898-105">As with other Office 365 engineers, Yammer engineers have zero standing access to Customer Data.</span></span> <span data-ttu-id="87898-106">您必須使用受核准的即時存取控制系統要求存取, 類似于擁有者人數有限的密碼箱。</span><span class="sxs-lookup"><span data-stu-id="87898-106">Access must be requested using an approval-based just-in-time access control system similar to Lockbox with a limited number of approvers.</span></span> <span data-ttu-id="87898-107">核准者會驗證要求 (例如, 他們會根據需求、業務案例、時間等來驗證要求是否合法, 然後核准或拒絕要求。</span><span class="sxs-lookup"><span data-stu-id="87898-107">Approvers verify the request (for example, they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request.</span></span> <span data-ttu-id="87898-108">如果要求受到核准, 就會將 JIT 存取授與已定義和有限的時間。</span><span class="sxs-lookup"><span data-stu-id="87898-108">If the request is approved, JIT access is granted for a defined and limited time.</span></span> <span data-ttu-id="87898-109">超過存取時間之後, access 會自動到期。</span><span class="sxs-lookup"><span data-stu-id="87898-109">After access time is exceeded, the access automatically expires.</span></span>

<span data-ttu-id="87898-110">就像其他 Office 365 服務一樣, Yammer 實際執行環境的所有存取都使用多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="87898-110">As with other Office 365 services, all access to the Yammer production environment uses multi-factor authentication.</span></span> <span data-ttu-id="87898-111">所有存取和命令歷程記錄都是由 Yammer 安全小組所交, 並定期進行記錄和檢查。</span><span class="sxs-lookup"><span data-stu-id="87898-111">All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="87898-112">如需 Yammer 管理和管理的詳細資訊, 請參閱[Yammer 系統管理](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)說明。</span><span class="sxs-lookup"><span data-stu-id="87898-112">For more information about Yammer administration and management, see [Yammer Admin Help](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span></span>