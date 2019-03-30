---
title: 設定使用者和 Office 365 進階電子文件探索中的案例
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: '了解如何設定使用者角色、 建立的情況下，並將使用者指派給 Office 365 進階電子文件探索中的案例。  '
ms.openlocfilehash: 5a22e0683e49ebdaf8391e092aeb101386e0636b
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999266"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="9248c-103">設定使用者和 Office 365 進階電子文件探索中的案例</span><span class="sxs-lookup"><span data-stu-id="9248c-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="9248c-104">本主題說明如何設定使用者和 Office 365 進階電子文件探索案例。</span><span class="sxs-lookup"><span data-stu-id="9248c-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9248c-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="9248c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="9248c-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="9248c-107">Prerequisites</span></span>

<span data-ttu-id="9248c-108">然後再設定案例] 和 [進階電子文件中的使用者，就必須進行下列：</span><span class="sxs-lookup"><span data-stu-id="9248c-108">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="9248c-109">若要分析使用進階電子文件的使用者資料，使用者 (資料的 custodian) 必須被指派 Office 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="9248c-109">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="9248c-110">或者，使用 Office 365 E1 或 E3 授權的使用者可被指派的進階電子文件獨立授權。</span><span class="sxs-lookup"><span data-stu-id="9248c-110">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="9248c-111">系統管理員和法務人員對於已指派給的情況下，並使用進階電子文件探索分析資料不需要 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="9248c-111">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="9248c-112">您必須是 Office 365 安全性中的 eDiscovery 管理員角色群組的成員&amp;合規性中心建立 eDiscovery 案例，並將成員新增到它。</span><span class="sxs-lookup"><span data-stu-id="9248c-112">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="9248c-113">若要將自己新增至 eDiscovery 管理員角色群組中的安全性&amp;合規性中心，您必須是 Office 365 組織中的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="9248c-113">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization.</span></span> <span data-ttu-id="9248c-114">如果您不是全域系統管理員，您必須要求的全域管理員，才能將您新增至 「 eDiscovery 管理員 」 角色群組。</span><span class="sxs-lookup"><span data-stu-id="9248c-114">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="9248c-115">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="9248c-115">For more information, see:</span></span>
    
  - [<span data-ttu-id="9248c-116">Microsoft 365 安全性中的權限&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="9248c-116">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
    
  - [<span data-ttu-id="9248c-117">指派 eDiscovery 權限，在 Microsoft 365 安全性&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="9248c-117">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="9248c-118">步驟 1： 將使用者指派 eDiscovery 權限</span><span class="sxs-lookup"><span data-stu-id="9248c-118">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="9248c-119">第一個步驟是安全性需求權限指派給使用者&amp;合規性中心，讓他們可以自己新增為 eDiscovery 案例的成員。</span><span class="sxs-lookup"><span data-stu-id="9248c-119">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="9248c-120">將使用者新增為安全性案例的成員之後&amp;合規性中心，他們就可以存取進階電子文件中的情況。</span><span class="sxs-lookup"><span data-stu-id="9248c-120">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="9248c-121">若要將使用者指派的必要權限，讓他們可以新增為 eDiscovery 案例的成員，請參閱中的步驟 1 [Microsoft 365 安全性中的 eDiscovery 案例&amp;合規性中心](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)。</span><span class="sxs-lookup"><span data-stu-id="9248c-121">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="9248c-122">步驟 2： 建立 eDiscovery 案例和新增成員</span><span class="sxs-lookup"><span data-stu-id="9248c-122">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="9248c-123">下一步是建立新的 eDiscovery 案例安全性&amp;規範中心和新增成員。</span><span class="sxs-lookup"><span data-stu-id="9248c-123">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members.</span></span> <span data-ttu-id="9248c-124">案例的成員能存取進階電子文件中的情況。</span><span class="sxs-lookup"><span data-stu-id="9248c-124">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="9248c-125">若要建立新的 eDiscovery 案例，請參閱 < 步驟 2 中<b0>Microsoft 365 安全性中的 eDiscovery 案例<b1></b1>合規性中心</b0>。</span><span class="sxs-lookup"><span data-stu-id="9248c-125">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="9248c-126">若要將成員新增至 eDiscovery 案例，請參閱中的步驟 3 [Microsoft 365 安全性中的 eDiscovery 案例&amp;合規性中心](ediscovery-cases.md#step-3-add-members-to-a-case)</span><span class="sxs-lookup"><span data-stu-id="9248c-126">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="9248c-127">步驟 3： 移進階電子文件中的案例</span><span class="sxs-lookup"><span data-stu-id="9248c-127">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="9248c-128">建立 eDiscovery 案例和新增成員之後，您 （或案例的任何成員） 可以存取進階電子文件中的對應案例。</span><span class="sxs-lookup"><span data-stu-id="9248c-128">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="9248c-129">若要存取進階電子文件中的案例，請參閱中的步驟 8 [Microsoft 365 安全性中的 eDiscovery 案例&amp;合規性中心](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="9248c-129">To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9248c-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9248c-130">See also</span></span>

[<span data-ttu-id="9248c-131">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="9248c-131">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="9248c-132">準備安裝</span><span class="sxs-lookup"><span data-stu-id="9248c-132">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 