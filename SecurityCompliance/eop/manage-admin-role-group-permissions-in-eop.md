---
title: 管理 EOP 中的系統管理員角色群組權限
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 在 Microsoft Exchange Online Protection (EOP) 中，您可以使用 Exchange 系統管理中心 (EAC)，讓使用者成為角色群組的成員，以為他們指派可用以執行特定管理工作的權限。您也可以使用 EAC 從角色群組中移除使用者。
ms.openlocfilehash: 5d50c77c97f2c345aa3994e7fa3ecd2eea93a13a
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026660"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="bbd49-104">管理 EOP 中的系統管理員角色群組權限</span><span class="sxs-lookup"><span data-stu-id="bbd49-104">Manage admin role group permissions in EOP</span></span>
  
<span data-ttu-id="bbd49-p102">在 Microsoft Exchange Online Protection (EOP) 中，您可以使用 Exchange 系統管理中心 (EAC)，讓使用者成為角色群組的成員，以為他們指派可用以執行特定管理工作的權限。您也可以使用 EAC 從角色群組中移除使用者。</span><span class="sxs-lookup"><span data-stu-id="bbd49-p102">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks. You can also remove a user from a role group or groups by using the EAC.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bbd49-107">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="bbd49-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bbd49-108">預估完成時間：5-10 分鐘</span><span class="sxs-lookup"><span data-stu-id="bbd49-108">Estimated time to complete: 5-10 minutes</span></span>
    
- <span data-ttu-id="bbd49-p103">您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)主題中的「使用者、連絡人及角色群組」項目。</span><span class="sxs-lookup"><span data-stu-id="bbd49-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="bbd49-p104">Office 365 中的某些權限會對映至 EOP 系統管理員角色群組權限。如需詳細資訊，請參閱[指派管理員角色](https://go.microsoft.com/fwlink/p/?LinkId=286708)中＜我的 Office 365 權限會延伸至哪些服務＞一節中的「Exchange Online 中的角色」欄。</span><span class="sxs-lookup"><span data-stu-id="bbd49-p104">Certain permissions in Office 365 map to EOP admin role group permissions. For more information, see the "Role in Exchange Online" column in the "Which services do my Office 365 permissions extend to?" section in [Assigning Admin Roles](https://go.microsoft.com/fwlink/p/?LinkId=286708).</span></span>
    
- <span data-ttu-id="bbd49-114">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。</span><span class="sxs-lookup"><span data-stu-id="bbd49-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="bbd49-p105">有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="bbd49-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="what-do-you-want-to-do"></a><span data-ttu-id="bbd49-118">您要執行的工作</span><span class="sxs-lookup"><span data-stu-id="bbd49-118">What do you want to do?</span></span>

### <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="bbd49-119">使用 EAC 將成員指派給系統管理員角色群組</span><span class="sxs-lookup"><span data-stu-id="bbd49-119">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="bbd49-120">在 EAC 中，瀏覽至 **[權限]** \> **[系統管理員角色]**，按一下您要新增使用者的角色群組，然後按一下 **[編輯]**![編輯圖示](../media/ITPro-EAC-EditIcon.png)。</span><span class="sxs-lookup"><span data-stu-id="bbd49-120">In the EAC, navigate to **Permissions** \> **Admin Roles**, click the role group that you want to add the user or users to, and then click **Edit**![Edit icon](../media/ITPro-EAC-EditIcon.png).</span></span>
    
2. <span data-ttu-id="bbd49-p106">在 [成員] 下，按一下 **[新增]**![加入圖示](../media/ITPro-EAC-AddIcon.png)。[選取成員] 視窗將會出現。</span><span class="sxs-lookup"><span data-stu-id="bbd49-p106">Under Members, click **Add**![Add Icon](../media/ITPro-EAC-AddIcon.png). The Select Members window will appear.</span></span>
    
3. <span data-ttu-id="bbd49-123">搜尋您要新增的使用者，或是從清單中加以選取。</span><span class="sxs-lookup"><span data-stu-id="bbd49-123">Search for the user or users that you wish to add, or select them from the list.</span></span>
    
4. <span data-ttu-id="bbd49-p107">選好要新增的使用者後，按一下 **[新增]**，然後按一下 **[確定]**。[選取成員] 視窗便會關閉。</span><span class="sxs-lookup"><span data-stu-id="bbd49-p107">When you have selected the user or users that you want to add, click **Add**, and then click **OK**. The Select Members window will close.</span></span>
    
5. <span data-ttu-id="bbd49-p108">您會看到使用者已新增至 **[成員]** 窗格。按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="bbd49-p108">You will see that the user has been added to the **Members** pane. Click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bbd49-128">使用者可能必須先登出再登入，才能在您於角色群組中新增或移除成員後，看到其系統管理權限的變更。</span><span class="sxs-lookup"><span data-stu-id="bbd49-128">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span> 
  
### <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="bbd49-129">使用 EAC 從系統管理員角色群組中移除成員</span><span class="sxs-lookup"><span data-stu-id="bbd49-129">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="bbd49-130">在 EAC 中，瀏覽至 **[權限]** \> **[系統管理員角色]**，按一下您要從中移除使用者的角色群組，然後按一下 **[編輯]**![編輯圖示](../media/ITPro-EAC-EditIcon.png)。</span><span class="sxs-lookup"><span data-stu-id="bbd49-130">In the EAC, navigate to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit**![Edit icon](../media/ITPro-EAC-EditIcon.png).</span></span>
    
2. <span data-ttu-id="bbd49-131">在 [成員] 下，選取您要移除的使用者，然後按一下 **[移除]**![[移除] 圖示](../media/ITPro-EAC-RemoveIcon.png)。</span><span class="sxs-lookup"><span data-stu-id="bbd49-131">Under Members, select the user or users that you want to remove and click **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.png).</span></span>
    
3. <span data-ttu-id="bbd49-p109">按一下 **[儲存]**，以儲存角色群組的變更，並回到 **[系統管理員角色]** 頁面。若要確認您是否已成功從系統管理員角色群組中移除使用者，請確定在所選角色群組的詳細資料窗格中，[成員] 下已看不到該成員。</span><span class="sxs-lookup"><span data-stu-id="bbd49-p109">Click **Save** to save the change to the role group and return to the **Admin Roles** page. To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bbd49-134">使用者可能必須先登出再登入，才能在您於角色群組中新增或移除成員後，看到其系統管理權限的變更。</span><span class="sxs-lookup"><span data-stu-id="bbd49-134">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="bbd49-135">相關資訊</span><span class="sxs-lookup"><span data-stu-id="bbd49-135">For more information</span></span>

[<span data-ttu-id="bbd49-136">EOP 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="bbd49-136">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
  

