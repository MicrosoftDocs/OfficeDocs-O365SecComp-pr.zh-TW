---
title: 權限存取 Office 365 中的管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: 若要深入了解權限使用本主題存取 Office 365 中的管理
ms.openlocfilehash: d8b16d7dd73f99c15ec241963a58273966074318
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214923"
---
# <a name="privileged-access-management-in-office-365"></a><span data-ttu-id="203e0-103">權限存取 Office 365 中的管理</span><span class="sxs-lookup"><span data-stu-id="203e0-103">Privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="203e0-104">本主題涵蓋功能僅在 Office 365 E5 和進階規範 Sku 中目前可用的部署和設定指導。</span><span class="sxs-lookup"><span data-stu-id="203e0-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="203e0-p101">特殊存取權限管理 Office 365 中讓更精細的存取權限的管理工作的控制權。它可協助保護您的組織中可以使用現有的權限的管理員帳戶具有出位置的存取權機密資料或重要的組態設定的存取權的缺口。啟用權限的存取管理、 之後使用者需要要求剛剛-時間存取完成核准工作流程高度範圍且時間繫結到提高權限與權限工作。這提供使用者剛-充份-存取可執行工作，反之，而不致洩露機密資料或重要的組態設定。啟用 Office 365 中的權限的存取管理可讓您的組織操作以零出位置的權限，並提供一層的防禦措施弱點引起因為這類出位置管理存取。</span><span class="sxs-lookup"><span data-stu-id="203e0-p101">Privileged access management allows granular access control over privileged admin tasks in Office 365. It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings. After enabling privileged access management, users will need to request just-in-time access to complete elevated and privileged tasks through an approval workflow that is highly scoped and time-bound. This gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings. Enabling privileged access management in Office 365 will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span>

<span data-ttu-id="203e0-110">整合式的客戶 Lockbox 和權限的存取管理端對端工作流程的快速概觀，請參閱此[客戶 Lockbox 及視訊的 Office 365 中的權限的存取管理](https://go.microsoft.com/fwlink/?linkid=2066800)。</span><span class="sxs-lookup"><span data-stu-id="203e0-110">For a quick overview of the integrated Customer Lockbox and privileged access management end-to-end workflow, see this [Customer Lockbox and privileged access management in Office 365 video](https://go.microsoft.com/fwlink/?linkid=2066800).</span></span>

## <a name="layers-of-protection"></a><span data-ttu-id="203e0-111">保護層級</span><span class="sxs-lookup"><span data-stu-id="203e0-111">Layers of protection</span></span>

<span data-ttu-id="203e0-p102">特殊存取權限管理補充 Office 365 的安全性架構內其他資料和存取功能保護設定。啟用整合式安全性方法的一部分的特殊權限的存取管理並保護您的組織，由分層的安全性模型可用來將機密資訊與 Office 365 組態設定的保護最大化。如下圖所示下方啟用權限存取管理可幫助是以原生 Office 365 資料的加密和 Office 365 服務的角色型存取控制安全性模型所提供的保護為基礎。時一起使用[Azure AD 權限的身分識別管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)，這兩項功能提供在不同的範圍上的剛剛-時間存取權的存取控制。</span><span class="sxs-lookup"><span data-stu-id="203e0-p102">Privileged access management complements other data and access feature protections within the Office 365 security architecture. By enabling privileged access management as part of an integrated approach to security and protecting your organization, a layered security model can be used to maximize protection of sensitive information and Office 365 configuration settings. As shown in the diagram below, enabling privileged access management helps builds on the protection provided with native encryption of Office 365 data and the role based access control security model of Office 365 services. When used in conjunction with [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.</span></span>

![Office 365 中的分層的保護](media/pam-layered-protection.png)

<span data-ttu-id="203e0-p103">特殊權限存取 Office 365 中的管理可定義及時 Azure AD 權限的身分識別管理適用於與能夠執行多個工作的保護層級的**角色**在**任務**層級設定範圍。 Azure AD 權限的身分識別管理主要是可讓管理 AD 角色和角色群組的存取，而有權限存取 Office 365 中的管理會套用只會在任務層級。</span><span class="sxs-lookup"><span data-stu-id="203e0-p103">Privileged access management in Office 365 can be defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.  Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Office 365 is applied only at the task level.</span></span>

- <span data-ttu-id="203e0-119">**啟用權限存取 Office 365 中的管理已使用 Azure AD 權限的身分識別管理時：** 新增權限的存取管理 Office 365 中提供其他細微一層的權限存取 Office 365 的資料保護和稽核功能。</span><span class="sxs-lookup"><span data-stu-id="203e0-119">**Enabling privileged access management in Office 365 while already using Azure AD Privileged Identity Management:** Adding privileged access management in Office 365 provides another granular layer of protection and audit capabilities for privileged access to Office 365 data.</span></span>

- <span data-ttu-id="203e0-120">**已經使用時啟用 Azure AD 權限的身分識別管理特殊權限存取管理 Office 365 中：** 新增至權限的 Azure AD 權限的身分識別管理存取管理 Office 365 中的可以擴充主要使用者的角色或身分識別所定義的 Office 365 外部資料的權限的存取。</span><span class="sxs-lookup"><span data-stu-id="203e0-120">**Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management in Office 365 can extend privileged access to data outside of Office 365 that’s primarily defined by a user’s role or identity.</span></span>  

## <a name="privileged-access-management-architecture-and-process-flow"></a><span data-ttu-id="203e0-121">權限的存取管理架構和程序流程</span><span class="sxs-lookup"><span data-stu-id="203e0-121">Privileged access management architecture and process flow</span></span>

<span data-ttu-id="203e0-122">每個以下的程序流程大綱少限制存取及如何與 Office 365 substrate、 Office 365 稽核，及 Exchange 管理 runspace 互動的架構。</span><span class="sxs-lookup"><span data-stu-id="203e0-122">Each of the following process flows outline the architecture of priveleged access and how it interacts with the Office 365 substrate, Office 365 auditing, and the Exchange Management runspace.</span></span>

### <a name="step-1-configuring-a-privileged-access-policy"></a><span data-ttu-id="203e0-123">步驟 1： 設定的權限的存取原則</span><span class="sxs-lookup"><span data-stu-id="203e0-123">Step 1: Configuring a privileged access policy</span></span>

<span data-ttu-id="203e0-p104">設定時使用的 Office 365 系統管理中心或 Exchange Management PowerShell 將權限的存取原則，建立並定義原則及權限的存取功能程序中的 Office 365 substrate 和記錄檔的原則屬性Office 365 安全性和規範中心中的活動。原則現在已啟用並準備好要處理傳入要求核准。</span><span class="sxs-lookup"><span data-stu-id="203e0-p104">When configuring a privileged access policy using either the Office 365 Admin Center or Exchange Management PowerShell, you create and define the policy and the privileged access feature processes the policy attributes in the Office 365 substrate and logs the activity in the Office 365 Security and Compliance Center. The policy is now enabled and ready to handle incoming requests for approvals.</span></span>

![步驟 1-建立原則](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a><span data-ttu-id="203e0-127">步驟 2： 存取要求</span><span class="sxs-lookup"><span data-stu-id="203e0-127">Step 2: Access request</span></span>

<span data-ttu-id="203e0-p105">使用 Office 365 系統管理中心或 Exchange Management PowerShell，使用者可以要求提高權限或權限工作的存取權。權限的存取功能將要求傳送至 Office 365 substrate 處理對已設定最低權限存取原則與 Office 365 安全性記錄 sctivity 及規範中心記錄檔。</span><span class="sxs-lookup"><span data-stu-id="203e0-p105">Using the Office 365 Admin Center or Exchange Management PowerShell, users can request access to elevated or privileged tasks. The privileged access feature sends the request to the Office 365 substrate for processing against the configured privilege access policy and records the sctivity in the Office 365 Security and Compliance Center logs.</span></span>

![步驟 2-存取要求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a><span data-ttu-id="203e0-131">步驟 3： 存取權核准</span><span class="sxs-lookup"><span data-stu-id="203e0-131">Step 3: Access approval</span></span>

<span data-ttu-id="203e0-p106">產生核准要求並核准群組通知電子郵件的擱置的要求。如果核准被授與、 特殊權限的存取要求處理核准為及工作已完成。如果要求遭到拒絕，工作會封鎖並沒有存取權授與 reqeustor。要求者將收到的要求核准或拒絕透過電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="203e0-p106">An approval request is generated and the approval group is notified by email of the pending request. If approval is granted, the privileged access request is processed as an approval and the task is ready to be completed. If the request is denied, task is blocked and no access is granted to the reqeustor. The requestor will be notified of the request approval or denial via email message.</span></span>

![步驟 3-存取權核准](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a><span data-ttu-id="203e0-137">步驟 4： 存取處理</span><span class="sxs-lookup"><span data-stu-id="203e0-137">Step 4: Access processing</span></span>

<span data-ttu-id="203e0-p107">已核准要求 Exchange Management runspace 會處理工作。核准會檢查權限的存取原則與 Office 365 substrate 處理。任務的所有活動會都記錄在 「 Office 365 安全性及規範中心 」。</span><span class="sxs-lookup"><span data-stu-id="203e0-p107">For approved requests, the task is processed by the Exchange Management runspace. The approval is checked against the privileged access policy and processed by the Office 365 substrate. All activity for the task is logged in the Office 365 Security and Compliance Center.</span></span>

![步驟 4-Access 處理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a><span data-ttu-id="203e0-142">常見問題集</span><span class="sxs-lookup"><span data-stu-id="203e0-142">Frequently asked questions</span></span>

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a><span data-ttu-id="203e0-143">我需要哪些 Sku 使用特殊權限的存取 Office 365？</span><span class="sxs-lookup"><span data-stu-id="203e0-143">What SKUs do I need to use privileged access in Office 365?</span></span>
<span data-ttu-id="203e0-144">特殊存取權限管理 」 目前僅適用於 Office 365 E5 與進階規範 Sku 的客戶。</span><span class="sxs-lookup"><span data-stu-id="203e0-144">Privileged access management is currently only available for customers with Office 365 E5 and Advanced Compliance SKUs.</span></span>

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a><span data-ttu-id="203e0-145">何時將權限的存取可供使用 Office 365 工作負載超過 Exchange？</span><span class="sxs-lookup"><span data-stu-id="203e0-145">When will privileged access be available for Office 365 workloads beyond Exchange?</span></span>
<span data-ttu-id="203e0-p108">我們想要推出提供這項功能的其他 Office 365 工作負載。當我們已經準備好要共用時間表時，將可以透過[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="203e0-p108">We plan to offer this feature in other Office 365 workloads soon. When we’re ready to share a timeline, it will be available through the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

### <a name="my-organization-needs-more-than-30-privileged-access-polices-will-this-limit-be-increased"></a><span data-ttu-id="203e0-148">「 我的組織需要多個 30 權限的存取原則，可增加此限制吗？</span><span class="sxs-lookup"><span data-stu-id="203e0-148">My organization needs more than 30 privileged access polices, will this limit be increased?</span></span>

<span data-ttu-id="203e0-149">我們打算要提高目前推出的 Office 365 組織每 30 權限的存取原則的限制。</span><span class="sxs-lookup"><span data-stu-id="203e0-149">We're planning to increase the current limit of 30 privileged access policies per Office 365 organization soon.</span></span>

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a><span data-ttu-id="203e0-150">是否需要是來管理 Office 365 中的權限的存取的全域系統管理員吗？</span><span class="sxs-lookup"><span data-stu-id="203e0-150">Do I need to be a Global Admin to manage privileged access in Office 365?</span></span>
<span data-ttu-id="203e0-p109">否，您需要有 Exchange 角色管理角色指派給要管理 Office 365 中的權限的存取的帳戶。不過，全域管理員角色預設包含此角色和可用來管理特殊權限的存取如果您不想要設定的角色管理角色為獨立的帳戶權限。包含在核准者群組的使用者不需要是全域管理員或擁有 「 角色管理角色指派給檢閱和核准要求。</span><span class="sxs-lookup"><span data-stu-id="203e0-p109">No, you need to have the Exchange Role Management role assigned to accounts that will manage privileged access in Office 365. However, the Global Administrator role includes this role by default and can be used to manage privileged access if you don’t want to configure the Role Management role as a stand-alone account permission. Users who are included in an approvers’ group don't need to be a Global Admin or have the Role Management role assigned to review and approve requests.</span></span> 

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a><span data-ttu-id="203e0-154">如何為客戶 Lockbox 相關的 Office 365 中的權限的存取管理？</span><span class="sxs-lookup"><span data-stu-id="203e0-154">How is privileged access management in Office 365 related to Customer Lockbox?</span></span>
<span data-ttu-id="203e0-p110">[客戶 Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests)允許存取控制組織依其服務提供者，例如 Microsoft 資料存取層級。特殊權限存取 Office 365 中的管理允許所有的特殊權限的 Office 365 工作的組織內的更精細的存取控制。</span><span class="sxs-lookup"><span data-stu-id="203e0-p110">[Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) allows a level of access control for organizations for access to to data by their service provider, i.e. Microsoft. Privileged access management in Office 365 allows granular access control within an organization for all Office 365 privileged tasks.</span></span>
