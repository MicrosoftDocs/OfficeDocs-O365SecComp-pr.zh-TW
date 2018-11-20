---
title: 讓使用者能夠存取 Office 365 安全性&amp;規範中心
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/18/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 使用者必須被指派 Office 365 安全性權限&amp;規範中心之前他們可以管理任一其安全性或規範功能。
ms.openlocfilehash: 976c4e21351e352672f3075d0f713e63a634ce42
ms.sourcegitcommit: da4aa7335b577148ecd61e09bbb11039b817b287
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2018
ms.locfileid: "26539105"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="34860-103">讓使用者能夠存取 Office 365 安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="34860-103">Give users access to the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="34860-p101">使用者必須被指派 Office 365 安全性權限&amp;規範中心之前他們可以管理任一其安全性或規範功能。為 Office 365 全域管理員或安全性 OrganizationManagement 角色群組的成員&amp;規範中心，您可以指定給這些權限的使用者。使用者僅能管理您授與存取權的安全性或規範功能。</span><span class="sxs-lookup"><span data-stu-id="34860-p101">Users need to be assigned permissions in the Office 365 Security &amp; Compliance Center before they can manage any of its security or compliance features. As an Office 365 global admin or member of the OrganizationManagement role group in the Security &amp; Compliance Center, you can give these permissions to users. Users will only be able to manage the security or compliance features that you give them access to.</span></span> 
  
<span data-ttu-id="34860-107">您可以針對不同的權限的詳細資訊給使用者安全性&amp;規範中心、 取出[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="34860-107">For more information about the different permissions you can give to users in the Security &amp; Compliance Center, check out [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="34860-108">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="34860-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="34860-109">您必須是 Office 365 全域管理員或安全性 OrganizationManagement 角色群組的成員&amp;規範中心，以完成本文中的步驟。</span><span class="sxs-lookup"><span data-stu-id="34860-109">You need to be an Office 365 global admin, or a member of the OrganizationManagement role group in the Security &amp; Compliance Center, to complete the steps in this article.</span></span>
    
- <span data-ttu-id="34860-110">角色群組的安全性&amp;規範中心可能會有類似給角色群組的名稱在 Exchange Online 中，但它們不相同。</span><span class="sxs-lookup"><span data-stu-id="34860-110">Role groups for the Security &amp; Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span> 
    
- <span data-ttu-id="34860-111">Exchange Online 與安全性之間不共用角色群組成員資格&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="34860-111">Role group memberships aren't shared between Exchange Online and the Security &amp; Compliance Center.</span></span>
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a><span data-ttu-id="34860-112">使用 Office 365 系統管理中心來授與其他使用者存取安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="34860-112">Use the Office 365 admin center to give another user access to the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="34860-113">[登入 Office 365 以及移至 [系統管理中心](https://go.microsoft.com/fwlink/p/?LinkId=525275)。</span><span class="sxs-lookup"><span data-stu-id="34860-113">[Sign in to Office 365 and go to the Admin center](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span></span>
    
2. <span data-ttu-id="34860-114">在 Office 365 系統管理中心中，開啟 [**系統管理置中**] 和 [**安全性&amp;規範**。</span><span class="sxs-lookup"><span data-stu-id="34860-114">In the Office 365 admin center, open **Admin centers** and then click **Security &amp; Compliance**.</span></span> 
    
3. <span data-ttu-id="34860-115">安全性&amp;規範中心，請移至 [**權限**。</span><span class="sxs-lookup"><span data-stu-id="34860-115">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
4. <span data-ttu-id="34860-116">從清單中選擇您要新增使用者並按一下 [**編輯**角色群組![編輯圖示](media/O365_MDM_CreatePolicy_EditIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="34860-116">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif).</span></span>
    
5. <span data-ttu-id="34860-117">在 [**成員**] 底下的角色群組的內容頁面上，按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)選取名稱想要新增的使用者 （或使用者）。</span><span class="sxs-lookup"><span data-stu-id="34860-117">In the role group's properties page under **Members**, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span> 
    
6. <span data-ttu-id="34860-118">當您已選取的所有使用者想要新增至角色群組，請按一下 [\*\*新增-\> \*\* ] 和 [然後 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="34860-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>
    
7. <span data-ttu-id="34860-119">按一下 [**儲存**] 以將所做的變更儲存到角色群組。</span><span class="sxs-lookup"><span data-stu-id="34860-119">Click **Save** to save the changes to the role group.</span></span> 
    
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="34860-120">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="34860-120">How do you know this worked?</span></span>

1. <span data-ttu-id="34860-121">安全性&amp;規範中心，請移至 [**權限**。</span><span class="sxs-lookup"><span data-stu-id="34860-121">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
2. <span data-ttu-id="34860-122">從清單中選取要檢視成員的角色群組。</span><span class="sxs-lookup"><span data-stu-id="34860-122">From the list, select the role group to view the members.</span></span>
    
3. <span data-ttu-id="34860-123">在向右的角色群組的詳細資訊，您可以檢視角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="34860-123">On the right, in the role group details, you can view the members of the role group.</span></span>
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a><span data-ttu-id="34860-124">使用 PowerShell 來授與其他使用者存取安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="34860-124">Use PowerShell to give another user access to the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="34860-125">[連線至 Office 365 的安全性與規範中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="34860-125">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="34860-126">使用 **Add-RoleGroupMember** 命令，以將使用者新增至組織管理角色，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="34860-126">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span> 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 <span data-ttu-id="34860-127">**參數**</span><span class="sxs-lookup"><span data-stu-id="34860-127">**Parameters**</span></span>
  
-  <span data-ttu-id="34860-128">_-Identity_ 是要新增成員的角色群組。</span><span class="sxs-lookup"><span data-stu-id="34860-128">_-Identity_ is the role group to add a member to.</span></span> 
    
- - <span data-ttu-id="34860-p102">_成員_是要新增至角色群組的信箱、 萬用安全性群組 (USG) 或電腦。您可以指定只有一個成員一次。</span><span class="sxs-lookup"><span data-stu-id="34860-p102">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group. You can specify only one member at a time.</span></span> 
    
<span data-ttu-id="34860-131">如需詳細的語法及參數的詳細資訊，請參閱[Add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510859)。</span><span class="sxs-lookup"><span data-stu-id="34860-131">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span></span>
  
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="34860-132">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="34860-132">How do you know this worked?</span></span>

<span data-ttu-id="34860-133">若要確認您已指定的使用者存取安全性&amp;規範中心使用**Get-rolegroupmember**指令程式檢視組織管理角色群組中的成員在下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="34860-133">To verify that you've given users access to the Security &amp; Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span> 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

<span data-ttu-id="34860-134">如需詳細的語法及參數的詳細資訊，請參閱[Get-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510860)。</span><span class="sxs-lookup"><span data-stu-id="34860-134">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span></span>
  

