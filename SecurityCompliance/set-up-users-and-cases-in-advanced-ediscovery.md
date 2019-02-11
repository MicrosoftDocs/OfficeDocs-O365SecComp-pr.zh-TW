---
title: 在 Office 365 進階電子文件探索中設定使用者與案例
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: '了解如何設定使用者角色、 建立的情況下，並將使用者指派給 Office 365 進階 ediscovery 案例。  '
ms.openlocfilehash: 4c0043b7651cc82272492e19faf01041c6f67932
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29559056"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="7ec98-103">在 Office 365 進階電子文件探索中設定使用者與案例</span><span class="sxs-lookup"><span data-stu-id="7ec98-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="7ec98-104">本主題說明如何設定使用者和 Office 365 進階 ediscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="7ec98-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7ec98-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="7ec98-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="7ec98-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="7ec98-107">Prerequisites</span></span>

<span data-ttu-id="7ec98-108">設定之前案例] 和 [進階在 eDiscovery 中的使用者，以下是需要：</span><span class="sxs-lookup"><span data-stu-id="7ec98-108">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="7ec98-p102">若要分析使用進階的 eDiscovery 的使用者資料，使用者 (資料 okay) 必須指派 Office 365 E5 授權。或者，使用 Office 365 E1 或 E3 授權的使用者可以將指派進階的 eDiscovery 獨立授權。系統管理員及法務人員對於已指派給的情況下並使用進階的 eDiscovery 分析資料不需要的 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="7ec98-p102">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="7ec98-p103">您必須是 Office 365 安全性 eDiscovery 管理員角色群組的成員&amp;規範中心建立 eDiscovery 案例及新增成員。將您新增至 eDiscovery 管理員角色群組安全性&amp;規範中心，您必須是 Office 365 組織中的全域管理員。如果您不是全域管理員，您必須要求將您新增至 eDiscovery 管理員角色群組的全域管理員。如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="7ec98-p103">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it. To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization. If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group. For more information, see:</span></span>
    
  - [<span data-ttu-id="7ec98-116">Office 365 安全性權限&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="7ec98-116">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
    
  - [<span data-ttu-id="7ec98-117">Office 365 安全性 eDiscovery 權限指派&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="7ec98-117">Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="7ec98-118">步驟 1： 將使用者指派 eDiscovery 權限</span><span class="sxs-lookup"><span data-stu-id="7ec98-118">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="7ec98-p104">第一個步驟是將使用者指派安全性需求的權限&amp;規範中心，讓他們可以我新增為 eDiscovery 案例的成員。將使用者新增為成員的安全性案例之後&amp;規範中心他們將無法存取進階 ediscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="7ec98-p104">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case. After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="7ec98-121">若要指派給使用者的必要權限讓他們可以新增為 eDiscovery 案例的成員，請參閱中的步驟 1 [Office 365 安全性的 eDiscovery 案例&amp;規範中心](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)。</span><span class="sxs-lookup"><span data-stu-id="7ec98-121">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="7ec98-122">步驟 2： 建立 eDiscovery 案例及新增成員</span><span class="sxs-lookup"><span data-stu-id="7ec98-122">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="7ec98-p105">下一步是建立新的 eDiscovery 案例安全性&amp;規範中心及新增成員。大小寫的成員能存取的進階 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="7ec98-p105">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members. Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="7ec98-125">若要建立新的 eDiscovery 案例，請參閱步驟 2 中[Office 365 安全性的 eDiscovery 案例&amp;規範中心](ediscovery-cases.md#step-2-create-a-new-case)。</span><span class="sxs-lookup"><span data-stu-id="7ec98-125">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="7ec98-126">若要將成員新增至 eDiscovery 案例，請參閱中的步驟 3 [Office 365 安全性的 eDiscovery 案例&amp;規範中心](ediscovery-cases.md#step-3-add-members-to-a-case)</span><span class="sxs-lookup"><span data-stu-id="7ec98-126">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="7ec98-127">步驟 3： 移進階 ediscovery 案例</span><span class="sxs-lookup"><span data-stu-id="7ec98-127">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="7ec98-p106">建立 eDiscovery 案例及新增成員後，您 （或大小寫的任何成員） 就可以存取進階在 eDiscovery 中相對應的大小寫。若要存取進階 ediscovery 案例，請參閱中的步驟 8 [Office 365 安全性的 eDiscovery 案例&amp;規範中心](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="7ec98-p106">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery. To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7ec98-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7ec98-130">See also</span></span>

[<span data-ttu-id="7ec98-131">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="7ec98-131">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7ec98-132">準備安裝</span><span class="sxs-lookup"><span data-stu-id="7ec98-132">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 