---
title: 讓使用者能夠存取 Office 365 安全規範中心
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 使用者必須獲指派 Office 365 安全性 & 合規性中心中的權限，他們可以管理其安全性或規範功能的任何之前。
ms.openlocfilehash: 7963a8c3db64e83566960abe9298b9a2d636ae53
ms.sourcegitcommit: 6302a43d947a908dd10a8e40550b806f491692fc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2019
ms.locfileid: "35645118"
---
# <a name="give-users-access-to-the-office-365-security--compliance-center"></a><span data-ttu-id="4e8fc-103">讓使用者能夠存取 Office 365 安全規範中心</span><span class="sxs-lookup"><span data-stu-id="4e8fc-103">Give users access to the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="4e8fc-104">使用者必須獲指派 Office 365 安全性 & 合規性中心中的權限，他們可以管理其安全性或規範功能的任何之前。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-104">Users need to be assigned permissions in the Office 365 Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="4e8fc-105">為 Office 365 全域系統管理員或 OrganizationManagement 角色群組的安全性 & 合規性中心中的成員，您可以授與這些權限的使用者。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-105">As an Office 365 global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="4e8fc-106">使用者只能管理您授予權利給他們的安全性或符合性功能。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span> 
  
<span data-ttu-id="4e8fc-107">如需詳細資訊的不同的權限您可以授與安全性 & 合規性中心中的使用者，請參閱[Office 365 安全性 & 合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4e8fc-108">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="4e8fc-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4e8fc-109">您必須是 Office 365 全域系統管理員或若要完成本文中的步驟安全性 & 合規性中心 OrganizationManagement 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-109">You need to be an Office 365 global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="4e8fc-110">安全性 & 合規性中心的角色群組可能會有類似的角色群組的名稱在 Exchange Online，但是兩者並不相同。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="4e8fc-111">Exchange Online 和安全性 & 合規性中心之間不會共用角色群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="4e8fc-112">使用管理代理者 」 (AOBO) 權限的委派的存取權限 (DAP) 合作夥伴無法存取安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="4e8fc-113">使用 Office 365 系統管理中心將另一個使用者存取權授與安全性 & 合規性中心</span><span class="sxs-lookup"><span data-stu-id="4e8fc-113">Use the Office 365 admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="4e8fc-114">[登入 Office 365 並移至系統管理中心](https://go.microsoft.com/fwlink/p/?LinkId=525275)。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-114">[Sign in to Office 365 and go to the Admin center](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span></span>

2. <span data-ttu-id="4e8fc-115">在 Office 365 系統管理中心中，開啟 [**系統管理中心**，然後按一下 [**安全性 & 合規性**。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-115">In the Office 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="4e8fc-116">在安全性 & 合規性中心，前往 [**權限**。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="4e8fc-117">從清單中，選擇 [角色群組，您想要新增使用者並按一下 [**編輯**![編輯圖示](media/O365-MDM-CreatePolicy-EditIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="4e8fc-118">在角色群組的 [屬性] 頁面 [**成員**] 底下，按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)選取名稱您想要新增的使用者 （或使用者）。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-118">In the role group's properties page under **Members**, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="4e8fc-119">當您已選取的所有使用者想要新增至角色群組，請按一下 [\*\*新增-\> \*\* ]，然後 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="4e8fc-120">按一下 [儲存]，將變更儲存到角色群組。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="4e8fc-121">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="4e8fc-121">How do you know this worked?</span></span>

1. <span data-ttu-id="4e8fc-122">在安全性 & 合規性中心，前往 [**權限**。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="4e8fc-123">從清單中，選取要檢視的成員的角色群組。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="4e8fc-124">在右側，在 [角色群組的詳細資訊，您可以檢視角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="4e8fc-125">使用 PowerShell 將另一個使用者存取權授與安全性 & 合規性中心</span><span class="sxs-lookup"><span data-stu-id="4e8fc-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="4e8fc-126">[連線至 Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-126">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="4e8fc-127">使用 **Add-RoleGroupMember** 命令，以將使用者新增至組織管理角色，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="4e8fc-128">**參數**：</span><span class="sxs-lookup"><span data-stu-id="4e8fc-128">**Parameters**:</span></span>
  
   - <span data-ttu-id="4e8fc-129">_身分識別_是要新增成員的角色群組。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="4e8fc-130">_成員_是要新增至角色群組的信箱、 萬用安全性群組 (USG) 或電腦。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="4e8fc-131">您一次只能指定一個成員。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="4e8fc-132">如需詳細的語法及參數的詳細資訊，請參閱[Add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510859)。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span></span>
  
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="4e8fc-133">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="4e8fc-133">How do you know this worked?</span></span>

<span data-ttu-id="4e8fc-134">若要確認您已給予使用者存取至安全性 & 合規性中心，請使用**Get-rolegroupmember**指令程式檢視成員中 「 組織管理 」 角色群組，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>
  
```
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="4e8fc-135">如需詳細的語法及參數的詳細資訊，請參閱[Get-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510860)。</span><span class="sxs-lookup"><span data-stu-id="4e8fc-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span></span>
