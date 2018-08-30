---
title: 如何關閉 Office 365 中的行動裝置管理
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- GPA150
- MET150
ms.assetid: 2709cafb-0a8b-44bc-8494-7e2fccfa2b19
description: 請遵循下列步驟來停止 MDM 原則與 Office 365 組織中的行動裝置要強制執行。
ms.openlocfilehash: 6b8f0036ed999b10263f5cc074df27175769e604
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272218"
---
# <a name="how-to-turn-off-mobile-device-management-in-office-365"></a><span data-ttu-id="053b2-103">如何關閉 Office 365 中的行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="053b2-103">How to turn off Mobile Device Management in Office 365</span></span>

<span data-ttu-id="053b2-104">有效地關閉 MDM for Office 365，您可以組群的人 （安全性群組所定義） 移除裝置管理原則，或移除自己的原則。</span><span class="sxs-lookup"><span data-stu-id="053b2-104">To effectively turn off MDM for Office 365, you remove groups of people (defined by security groups) from the device management policies, or remove the policies themselves.</span></span> 
  
- <span data-ttu-id="053b2-105">透過從您已建立的裝置原則移除使用者安全性群組中移除使用者的群組。</span><span class="sxs-lookup"><span data-stu-id="053b2-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span> 
    
- <span data-ttu-id="053b2-106">停用 MDM 所有人來移除所有 MDM 裝置原則。</span><span class="sxs-lookup"><span data-stu-id="053b2-106">Disable MDM for everyone by removing all MDM device policies.</span></span> 
    
<span data-ttu-id="053b2-p101">這些選項會在您的組織中移除 MDM 強制執行裝置。然而，您不能只是"解除佈建"MDM for Office 365 後您已設定它。</span><span class="sxs-lookup"><span data-stu-id="053b2-p101">These options will remove MDM enforcement for devices in your organization. Unfortunately, you can't simply "unprovision" MDM for Office 365 after you've set it up.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="053b2-p102">請注意在使用者的裝置上的影響當您從原則中移除使用者安全性群組或移除自己的原則。例如，電子郵件設定檔和快取的電子郵件可能會移除，根據裝置。請參閱：[功能的不同的裝置類型上的安全性原則影響吗？](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)</span><span class="sxs-lookup"><span data-stu-id="053b2-p102">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves. For example, email profiles and cached emails may be removed, depending on the device. See: [What is the impact of security policies on different device types?](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)</span></span>
  
## <a name="remove-user-security-groups-from-mdm-device-policies"></a><span data-ttu-id="053b2-112">從 MDM 裝置原則中移除使用者安全性群組</span><span class="sxs-lookup"><span data-stu-id="053b2-112">Remove user security groups from MDM device policies</span></span>

1. <span data-ttu-id="053b2-113">移至 [**安全性&amp;規範中心**\> **資料外洩防護** \> **裝置安全性原則**。</span><span class="sxs-lookup"><span data-stu-id="053b2-113">Go to **Security &amp; Compliance Center**\> **Data loss prevention** \> **Device security polices**.</span></span>
    
2. <span data-ttu-id="053b2-114">選取裝置原則]，然後按一下 [![編輯圖示](media/O365-MDM-CreatePolicy-EditIcon.gif)**編輯原則**。</span><span class="sxs-lookup"><span data-stu-id="053b2-114">Select a device policy, and click ![Edit icon](media/O365-MDM-CreatePolicy-EditIcon.gif) **Edit policy**.</span></span>
    
3. <span data-ttu-id="053b2-115">[**部署**中，按一下 [ **-移除**。</span><span class="sxs-lookup"><span data-stu-id="053b2-115">Under **Deployment**, click **- Remove**.</span></span>
    
    <span data-ttu-id="053b2-116">在 [**群組**] 選取 [安全性] 群組。</span><span class="sxs-lookup"><span data-stu-id="053b2-116">Under **Groups**, select a security group.</span></span>
    
4.  <span data-ttu-id="053b2-117">按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="053b2-117">Click **Remove**.</span></span>
    
5. <span data-ttu-id="053b2-118">按一下 [儲存]****。</span><span class="sxs-lookup"><span data-stu-id="053b2-118">Click **Save**.</span></span>
    
## <a name="remove-mdm-device-policies"></a><span data-ttu-id="053b2-119">移除 MDM 裝置原則</span><span class="sxs-lookup"><span data-stu-id="053b2-119">Remove MDM device policies</span></span>

1. <span data-ttu-id="053b2-120">移至 [**安全性&amp;規範中心**\> **安全性原則** \> **裝置安全性原則**。</span><span class="sxs-lookup"><span data-stu-id="053b2-120">Go to **Security &amp; Compliance Center**\> **Security policies** \> **Device security policies**.</span></span>
    
2. <span data-ttu-id="053b2-p103">選取裝置原則]，然後再按一下![映像的資源回收筒可圖示。](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **刪除原則**。</span><span class="sxs-lookup"><span data-stu-id="053b2-p103">Select a device policy, and then click ![Image of the trash can icon.](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **Delete policy**.</span></span>
    
3. <span data-ttu-id="053b2-123">在 [**警告**] 對話方塊中按一下 [**是**]。</span><span class="sxs-lookup"><span data-stu-id="053b2-123">In the **Warning** dialog, click **Yes**.</span></span> 
    

