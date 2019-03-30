---
title: 特殊權限存取 Office 365 中管理
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
ms.openlocfilehash: 2a464bacaa568515e470e29a0c9c45a91a79cf8e
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001246"
---
# <a name="privileged-access-management-in-office-365"></a><span data-ttu-id="1c5c8-103">特殊權限存取 Office 365 中管理</span><span class="sxs-lookup"><span data-stu-id="1c5c8-103">Privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c5c8-104">本主題涵蓋功能目前僅適用於 Office 365 E5 和進階合規性 Sku 的部署和設定指導。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="1c5c8-105">特殊權限存取管理可讓 Office 365 中的特殊權限的系統管理工作更精細的存取控制。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-105">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="1c5c8-106">它可以協助保護您的組織可能使用現有的特殊權限的系統管理員帳戶具有常設存取權的敏感資料或存取重要的組態設定的外洩。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-106">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="1c5c8-107">啟用特殊權限的存取管理之後, 使用者必須要求完成提升權限和特殊權限的工作，透過核准工作流程的高度範圍中的時間繫結的剛-時間存取權。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-107">After enabling privileged access management, users will need to request just-in-time access to complete elevated and privileged tasks through an approval workflow that is highly scoped and time-bound.</span></span> <span data-ttu-id="1c5c8-108">這可以讓使用者剛充份-存取執行工作的而不致曝露機密資料或重要的組態設定。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-108">This gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings.</span></span> <span data-ttu-id="1c5c8-109">啟用 Office 365 中的特殊權限的存取管理，可讓您的組織來操作以零常設權限，並提供一層的防禦引起因為這類常設系統管理存取權的弱點。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-109">Enabling privileged access management in Office 365 will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span>

<span data-ttu-id="1c5c8-110">整合式的客戶加密箱和特殊權限的存取管理端對端工作流程的快速概觀，請參閱此[客戶加密箱和 Office 365 影片中的特殊權限的存取管理](https://go.microsoft.com/fwlink/?linkid=2066800)。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-110">For a quick overview of the integrated Customer Lockbox and privileged access management end-to-end workflow, see this [Customer Lockbox and privileged access management in Office 365 video](https://go.microsoft.com/fwlink/?linkid=2066800).</span></span>

## <a name="layers-of-protection"></a><span data-ttu-id="1c5c8-111">保護層級</span><span class="sxs-lookup"><span data-stu-id="1c5c8-111">Layers of protection</span></span>

<span data-ttu-id="1c5c8-112">特殊權限存取管理輔助其他資料與存取權的功能保護 Office 365 安全性架構內。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-112">Privileged access management complements other data and access feature protections within the Office 365 security architecture.</span></span> <span data-ttu-id="1c5c8-113">藉由啟用安全性整合式方法的一部分的特殊權限的存取管理和保護您的組織，一種層次的安全性模型可用來最大化保護敏感資訊和 Office 365 組態設定。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-113">By enabling privileged access management as part of an integrated approach to security and protecting your organization, a layered security model can be used to maximize protection of sensitive information and Office 365 configuration settings.</span></span> <span data-ttu-id="1c5c8-114">如圖所示下方，啟用特殊權限存取管理有助於為基礎提供原生 Office 365 資料加密與 Office 365 服務角色型存取控制安全性模型的保護。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-114">As shown in the diagram below, enabling privileged access management helps builds on the protection provided with native encryption of Office 365 data and the role based access control security model of Office 365 services.</span></span> <span data-ttu-id="1c5c8-115">當[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)搭配使用，這兩項功能提供剛時間存取在不同範圍的存取控制。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-115">When used in conjunction with [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.</span></span>

![在 Office 365 中的分層的保護](media/pam-layered-protection.png)

<span data-ttu-id="1c5c8-117">特殊權限存取管理 Office 365 中的可以定義和 Azure AD Privileged Identity Management 套用**角色**層級的保護，能夠執行多個任務時，在**任務**層級範圍。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-117">Privileged access management in Office 365 can be defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.</span></span>  <span data-ttu-id="1c5c8-118">Azure AD 有權限身分識別管理主要允許管理 AD 角色和角色群組的存取，則 Office 365 中的管理特殊權限存取時套用只在任務層級。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-118">Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Office 365 is applied only at the task level.</span></span>

- <span data-ttu-id="1c5c8-119">**啟用特殊權限存取 Office 365 中的管理已使用 Azure AD Privileged Identity Management 時：** 在 Office 365 中新增特殊權限的存取管理提供另一個的細微層級的特殊權限存取 Office 365 的資料保護和稽核功能。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-119">**Enabling privileged access management in Office 365 while already using Azure AD Privileged Identity Management:** Adding privileged access management in Office 365 provides another granular layer of protection and audit capabilities for privileged access to Office 365 data.</span></span>

- <span data-ttu-id="1c5c8-120">**啟用 Azure AD Privileged Identity Management 時已經在使用特殊權限存取管理 Office 365 中：** 將 Azure AD Privileged Identity Management 新增至權限存取管理 Office 365 中的可以延伸至主要由使用者的角色或身分識別所定義的 Office 365 外部資料的特殊權限的存取。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-120">**Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management in Office 365 can extend privileged access to data outside of Office 365 that’s primarily defined by a user’s role or identity.</span></span>  

## <a name="privileged-access-management-architecture-and-process-flow"></a><span data-ttu-id="1c5c8-121">特殊權限的存取管理架構和處理程序流程</span><span class="sxs-lookup"><span data-stu-id="1c5c8-121">Privileged access management architecture and process flow</span></span>

<span data-ttu-id="1c5c8-122">下列程序流程的每個大綱架構的特殊權限的存取和 Office 365 substrate、 與 Office 365 稽核]，Exchange 管理 runspace 的互動方式。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-122">Each of the following process flows outline the architecture of privileged access and how it interacts with the Office 365 substrate, Office 365 auditing, and the Exchange Management runspace.</span></span>

### <a name="step-1-configuring-a-privileged-access-policy"></a><span data-ttu-id="1c5c8-123">步驟 1： 設定特殊權限的存取原則</span><span class="sxs-lookup"><span data-stu-id="1c5c8-123">Step 1: Configuring a privileged access policy</span></span>

<span data-ttu-id="1c5c8-124">設定時使用的[Microsoft 365 系統管理中心](https://admin.microsoft.com)或 Exchange Management PowerShell 的特殊權限的存取原則，您建立，並定義原則和特殊權限的存取功能處理 Office 365 substrate 中的原則屬性和登入 Office 365 安全性與合規性中心的活動。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-124">When configuring a privileged access policy using either the [Microsoft 365 admin center](https://admin.microsoft.com) or Exchange Management PowerShell, you create and define the policy and the privileged access feature processes the policy attributes in the Office 365 substrate and logs the activity in the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="1c5c8-125">原則現已啟用，並準備好處理傳入要求核准。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-125">The policy is now enabled and ready to handle incoming requests for approvals.</span></span>

![步驟 1-建立原則](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a><span data-ttu-id="1c5c8-127">步驟 2： 存取要求</span><span class="sxs-lookup"><span data-stu-id="1c5c8-127">Step 2: Access request</span></span>

<span data-ttu-id="1c5c8-128">使用[Microsoft 365 系統管理中心](https://admin.microsoft.com)或 Exchange Management PowerShell，使用者可以要求存取較高權限或特殊權限的工作。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-128">Using the [Microsoft 365 admin center](https://admin.microsoft.com) or Exchange Management PowerShell, users can request access to elevated or privileged tasks.</span></span> <span data-ttu-id="1c5c8-129">特殊權限的存取功能會將要求傳送至已設定特殊權限存取原則和記錄的 Office 365 安全性與合規性中心的記錄檔中的活動的處理 Office 365 substrate。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-129">The privileged access feature sends the request to the Office 365 substrate for processing against the configured privilege access policy and records the Activity in the Office 365 Security and Compliance Center logs.</span></span>

![步驟 2-存取要求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a><span data-ttu-id="1c5c8-131">步驟 3： 存取權核准</span><span class="sxs-lookup"><span data-stu-id="1c5c8-131">Step 3: Access approval</span></span>

<span data-ttu-id="1c5c8-132">產生核准要求，並核准群組通知電子郵件的擱置的要求。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-132">An approval request is generated and the approval group is notified by email of the pending request.</span></span> <span data-ttu-id="1c5c8-133">授與核准時，如果特殊權限的存取要求處理核准為且工作已完成。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-133">If approval is granted, the privileged access request is processed as an approval and the task is ready to be completed.</span></span> <span data-ttu-id="1c5c8-134">如果拒絕要求時，會封鎖工作，並沒有存取權授與給要求者。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-134">If the request is denied, task is blocked and no access is granted to the requestor.</span></span> <span data-ttu-id="1c5c8-135">要求者將會收到通知的要求核准或拒絕透過電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-135">The requestor will be notified of the request approval or denial via email message.</span></span>

![步驟 3-存取權核准](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a><span data-ttu-id="1c5c8-137">步驟 4： 存取處理</span><span class="sxs-lookup"><span data-stu-id="1c5c8-137">Step 4: Access processing</span></span>

<span data-ttu-id="1c5c8-138">核准要求，會由 Exchange 管理 runspace 處理工作。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-138">For approved requests, the task is processed by the Exchange Management runspace.</span></span> <span data-ttu-id="1c5c8-139">核准是針對特殊權限的存取原則檢查，且由 Office 365 substrate 處理。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-139">The approval is checked against the privileged access policy and processed by the Office 365 substrate.</span></span> <span data-ttu-id="1c5c8-140">任務的所有活動會都記錄在 Office 365 安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-140">All activity for the task is logged in the Office 365 Security and Compliance Center.</span></span>

![步驟 4-Access 處理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a><span data-ttu-id="1c5c8-142">常見問題集</span><span class="sxs-lookup"><span data-stu-id="1c5c8-142">Frequently asked questions</span></span>

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a><span data-ttu-id="1c5c8-143">若要使用 Office 365 的特殊權限的存取是否需要何種 Sku？</span><span class="sxs-lookup"><span data-stu-id="1c5c8-143">What SKUs do I need to use privileged access in Office 365?</span></span>
<span data-ttu-id="1c5c8-144">特殊權限存取管理目前只適用於使用 Office 365 E5 和進階合規性 Sku 的客戶。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-144">Privileged access management is currently only available for customers with Office 365 E5 and Advanced Compliance SKUs.</span></span>

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a><span data-ttu-id="1c5c8-145">何時將特殊權限的存取可供 Exchange 以外的 Office 365 工作負載？</span><span class="sxs-lookup"><span data-stu-id="1c5c8-145">When will privileged access be available for Office 365 workloads beyond Exchange?</span></span>
<span data-ttu-id="1c5c8-146">我們要推出提供此功能在其他 Office 365 工作負載。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-146">We plan to offer this feature in other Office 365 workloads soon.</span></span> <span data-ttu-id="1c5c8-147">當我們已準備好要共用的時間表時，則可透過[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-147">When we’re ready to share a timeline, it will be available through the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

### <a name="my-organization-needs-more-than-30-privileged-access-polices-will-this-limit-be-increased"></a><span data-ttu-id="1c5c8-148">我的組織需要多個 30 的特殊權限的存取原則時，會增加此限制？</span><span class="sxs-lookup"><span data-stu-id="1c5c8-148">My organization needs more than 30 privileged access polices, will this limit be increased?</span></span>

<span data-ttu-id="1c5c8-149">我們計劃來增加每個 Office 365 組織推出 30 特殊權限的存取原則的目前限制。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-149">We're planning to increase the current limit of 30 privileged access policies per Office 365 organization soon.</span></span>

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a><span data-ttu-id="1c5c8-150">是否需要是全域系統管理員來管理 Office 365 中的特殊權限的存取？</span><span class="sxs-lookup"><span data-stu-id="1c5c8-150">Do I need to be a Global Admin to manage privileged access in Office 365?</span></span>
<span data-ttu-id="1c5c8-151">否，您必須具有 Exchange 角色管理 」 角色指派給將管理特殊權限的存取 Office 365 中的帳戶。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-151">No, you need to have the Exchange Role Management role assigned to accounts that will manage privileged access in Office 365.</span></span> <span data-ttu-id="1c5c8-152">不過，全域系統管理員角色包含此角色依預設，並可用來管理特殊權限的存取，如果您不想要設定為獨立的帳戶權限的角色管理角色。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-152">However, the Global Administrator role includes this role by default and can be used to manage privileged access if you don’t want to configure the Role Management role as a stand-alone account permission.</span></span> <span data-ttu-id="1c5c8-153">包含在核准者群組的使用者不需要是全域系統管理員或具有 「 角色管理角色指派進行審核及核准要求。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-153">Users who are included in an approvers’ group don't need to be a Global Admin or have the Role Management role assigned to review and approve requests.</span></span>

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a><span data-ttu-id="1c5c8-154">如何為客戶加密箱與相關的 Office 365 中的特殊權限的存取管理？</span><span class="sxs-lookup"><span data-stu-id="1c5c8-154">How is privileged access management in Office 365 related to Customer Lockbox?</span></span>
<span data-ttu-id="1c5c8-155">[Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests)可讓組織由其服務提供者，也就是 Microsoft 的資料存取的存取控制層級。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-155">[Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) allows a level of access control for organizations for access to to data by their service provider, i.e. Microsoft.</span></span> <span data-ttu-id="1c5c8-156">特殊權限存取 Office 365 中的管理可讓更精細的存取控制組織內部的 Office 365 特殊權限的所有工作。</span><span class="sxs-lookup"><span data-stu-id="1c5c8-156">Privileged access management in Office 365 allows granular access control within an organization for all Office 365 privileged tasks.</span></span>
