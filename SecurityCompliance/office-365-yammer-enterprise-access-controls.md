---
title: Office 365 Yammer Enterprise 存取控制
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 摘要： 簡短摘要有關 Yammer Enterprise 存取控制項實際執行環境中。
ms.openlocfilehash: 76b62e7ea026a52d822e5a213461e930b1d595e3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217883"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="1d759-103">Yammer 企業存取控制</span><span class="sxs-lookup"><span data-stu-id="1d759-103">Yammer Enterprise Access Controls</span></span> 

<span data-ttu-id="1d759-p101">Yammer 實際執行環境的實體和邏輯存取僅限於到非常小的一段人員 （基礎結構和作業）。與其他 Office 365 工程師，Yammer 工程師有零出位置的存取權的客戶資料。必須使用類似 Lockbox、 核准型剛剛-時間存取控制系統要求存取和核准者數目有限。核准者確認要求 （例如，其驗證要求是合法根據需要、 業務案例、 時間、 等），再核准或拒絕要求。如果核准要求、 JIT 存取會授與定義及有限的時間之後, 自動過期。</span><span class="sxs-lookup"><span data-stu-id="1d759-p101">Both physical and logical access to the Yammer production environment is restricted to a very small set of people (infrastructure and operations). As with other Office 365 engineers, Yammer engineers have zero standing access to Customer Data. Access must be requested using an approval-based just-in-time access control system similar to Lockbox, and there is a limited number of approvers. Approvers verify the request (e.g., they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request. If the request is approved, JIT access is granted for a defined and limited time, after which it automatically expires.</span></span> 

<span data-ttu-id="1d759-p102">與其他 Office 365 服務，Yammer 實際執行環境的所有存取如何都運用多重要素驗證。所有存取和命令歷程記錄是對應到的使用者記錄和定期檢閱 Yammer 安全性小組。</span><span class="sxs-lookup"><span data-stu-id="1d759-p102">As with other Office 365 services, all access to the Yammer production environment leverages multi-factor authentication. All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="1d759-111">如需 Yammer 系統管理與管理的詳細資訊，請參閱[Yammer 系統說明](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)。</span><span class="sxs-lookup"><span data-stu-id="1d759-111">For more information about Yammer administration and management, see [Yammer Admin Help](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span></span>