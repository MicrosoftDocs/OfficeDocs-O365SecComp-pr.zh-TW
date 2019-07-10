---
title: 管理 EOP 中的群組
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: 您可以使用 Exchange Online Protection (EOP) 來建立擁有郵件功能的群組，Exchange 組織。 您也可以使用 EOP 來定義或更新指定成員資格、 電子郵件地址，以及其他方面的群組的群組內容。
ms.openlocfilehash: 2763ca35456bb40b5b11e38eb2e7497934115d5f
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599639"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="c4514-104">管理 EOP 中的群組</span><span class="sxs-lookup"><span data-stu-id="c4514-104">Manage groups in EOP</span></span>

 <span data-ttu-id="c4514-105">您可以使用 Exchange Online Protection (EOP) 來建立擁有郵件功能的群組，Exchange 組織。</span><span class="sxs-lookup"><span data-stu-id="c4514-105">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization.</span></span> <span data-ttu-id="c4514-106">您也可以使用 EOP 來定義或更新指定成員資格、 電子郵件地址，以及其他方面的群組的群組內容。</span><span class="sxs-lookup"><span data-stu-id="c4514-106">You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups.</span></span> <span data-ttu-id="c4514-107">您可以建立通訊群組和安全性群組，視您的需求而定。</span><span class="sxs-lookup"><span data-stu-id="c4514-107">You can create distribution groups and security groups, depending on your needs.</span></span> <span data-ttu-id="c4514-108">使用 Exchange 系統管理中心 (EAC) 或透過遠端 Windows PowerShell，可以建立這些群組。</span><span class="sxs-lookup"><span data-stu-id="c4514-108">These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span> 
  
## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="c4514-109">擁有郵件功能的群組類型</span><span class="sxs-lookup"><span data-stu-id="c4514-109">Types of mail-enabled groups</span></span>

<span data-ttu-id="c4514-110">部署 Exchange 組織，您可以建立兩種類型的群組：</span><span class="sxs-lookup"><span data-stu-id="c4514-110">You can create two types of groups for your Exchange organization:</span></span>
  
- <span data-ttu-id="c4514-111">[建立在 EAC 中的群組](manage-groups-in-eop.md)（也稱為通訊群組） 是電子郵件使用者，例如小組或其他臨機操作的群組，且需要能夠接收或傳送電子郵件有關感興趣的公共區域的集合。</span><span class="sxs-lookup"><span data-stu-id="c4514-111">[Create a group in the EAC](manage-groups-in-eop.md) (also known as distribution groups) are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest.</span></span> <span data-ttu-id="c4514-112">通訊群組是以獨佔方式來散佈電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="c4514-112">Distribution groups are exclusively for distributing email messages.</span></span> <span data-ttu-id="c4514-113">在 EOP 中，通訊群組是指任何擁有郵件功能的群組，不論其具有安全性內容。</span><span class="sxs-lookup"><span data-stu-id="c4514-113">In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>
    
- <span data-ttu-id="c4514-114">[編輯或移除在 EAC 中的群組](manage-groups-in-eop.md)（也稱為安全性群組） 是需要系統管理員角色的存取權限的電子郵件使用者的集合。</span><span class="sxs-lookup"><span data-stu-id="c4514-114">[Edit or remove a group in the EAC](manage-groups-in-eop.md) (also known as security groups) are collections of email users who need access permissions for Admin roles.</span></span> <span data-ttu-id="c4514-115">例如，您可能想要提供使用者特定群組系統管理員角色權限，讓他們可以設定反垃圾郵件和反惡意程式碼設定。</span><span class="sxs-lookup"><span data-stu-id="c4514-115">For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c4514-116">根據預設，所有新的擁有郵件功能的安全群組會要求驗證所有寄件者。</span><span class="sxs-lookup"><span data-stu-id="c4514-116">By default, all new mail-enabled security groups require that all senders be authenticated.</span></span> <span data-ttu-id="c4514-117">這可防止外部寄件者傳送郵件給擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="c4514-117">This prevents external senders from sending messages to mail-enabled security groups.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="c4514-118">開始之前</span><span class="sxs-lookup"><span data-stu-id="c4514-118">Before you begin</span></span>

- <span data-ttu-id="c4514-119">您必須已獲指派權限，才能執行此程序或這些程序。</span><span class="sxs-lookup"><span data-stu-id="c4514-119">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="c4514-120">若要查看您需要的權限，請參閱[Feature permissions in EOP](feature-permissions-in-eop.md)主題中的 「 通訊群組和安全性群組 」 項目。</span><span class="sxs-lookup"><span data-stu-id="c4514-120">To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="c4514-121">請注意，在建立和管理群組使用遠端 PowerShell cmdlet，您可能會遇到節流問題。</span><span class="sxs-lookup"><span data-stu-id="c4514-121">Be aware that when creating and managing groups by using remote PowerShell cmdlets, you may encounter throttling.</span></span>
    
- <span data-ttu-id="c4514-122">此指令程式採用批次處理方法，因此導致幾分鐘的傳播延遲，然後才能看到指令程式的結果。</span><span class="sxs-lookup"><span data-stu-id="c4514-122">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
    
- <span data-ttu-id="c4514-123">若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱＜[使用遠端 PowerShell 連線到 Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)＞。</span><span class="sxs-lookup"><span data-stu-id="c4514-123">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
    
- <span data-ttu-id="c4514-124">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。</span><span class="sxs-lookup"><span data-stu-id="c4514-124">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="c4514-p107">有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="c4514-p107">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="c4514-128">在 EAC 中建立群組</span><span class="sxs-lookup"><span data-stu-id="c4514-128">Create a group in the EAC</span></span>

1. <span data-ttu-id="c4514-129">在 Exchange 系統管理中心 (EAC) 中，前往 [**收件者** \> **群組**。</span><span class="sxs-lookup"><span data-stu-id="c4514-129">In the Exchange admin center (EAC), go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="c4514-130">按一下 [**新增**![加入圖示](../media/ITPro-EAC-AddIcon.gif)，和 [**通訊群組**或**安全性群組**，視您的需求而定。</span><span class="sxs-lookup"><span data-stu-id="c4514-130">Click **New**![Add Icon](../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span> <span data-ttu-id="c4514-131">請參閱差別[之擁有郵件功能的群組類型](manage-groups-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="c4514-131">See [Types of mail-enabled groups](manage-groups-in-eop.md) for the distinction.</span></span> 
    
3. <span data-ttu-id="c4514-132">在 [**新增通訊群組**或**新的安全性群組**] 頁面上，完成下列欄位：</span><span class="sxs-lookup"><span data-stu-id="c4514-132">On the **New distribution group** or **New security group** page, complete the following fields:</span></span> 
    
  - <span data-ttu-id="c4514-133">**顯示名稱**輸入是唯一的您的組織且 EOP 使用者有意義的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="c4514-133">**Display name** Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="c4514-134">顯示名稱是必要項目。</span><span class="sxs-lookup"><span data-stu-id="c4514-134">The display name is required.</span></span> 
    
  - <span data-ttu-id="c4514-135">**別名**輸入群組的別名最多 64 個字元，是唯一的您的組織。</span><span class="sxs-lookup"><span data-stu-id="c4514-135">**Alias** Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="c4514-136">EOP 使用者輸入的別名中： 行的電子郵件訊息與別名解析為群組的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="c4514-136">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="c4514-137">如果您變更別名時，群組的主要 SMTP 位址也變更，並將包含新的別名。</span><span class="sxs-lookup"><span data-stu-id="c4514-137">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="c4514-138">別名為必要項目。</span><span class="sxs-lookup"><span data-stu-id="c4514-138">The alias is required.</span></span> 
    
  - <span data-ttu-id="c4514-139">**描述**使他人了解群組的用途，請輸入群組的描述。</span><span class="sxs-lookup"><span data-stu-id="c4514-139">**Description** Type a description of the group so that people will know the purpose of the group.</span></span> 
    
  - <span data-ttu-id="c4514-140">**擁有者**根據預設，會建立群組的人員會為擁有者。</span><span class="sxs-lookup"><span data-stu-id="c4514-140">**Owners** By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="c4514-141">您可以選擇 [**新增]** 新增擁有者![加入圖示](../media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="c4514-141">You can add an owner by choosing **Add**![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="c4514-142">所有群組都必須至少一個擁有者。</span><span class="sxs-lookup"><span data-stu-id="c4514-142">All groups must have at least one owner.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c4514-143">擁有者不必是群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c4514-143">Owners don't have to be members of the group.</span></span> 
  
  - <span data-ttu-id="c4514-144">**成員**若要新增群組成員並指定核准是否需要使用者在加入或離開群組，請使用此區段。</span><span class="sxs-lookup"><span data-stu-id="c4514-144">**Members** Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="c4514-145">若要將成員新增至群組中，按一下 [**新增**![加入圖示](../media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="c4514-145">To add members to the group, click **Add**![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="c4514-146">按一下 **[確定]** 以返回原始頁面。</span><span class="sxs-lookup"><span data-stu-id="c4514-146">Click **OK** to return to the original page.</span></span> 
    
5. <span data-ttu-id="c4514-147">當您已完成，請按一下 [**儲存**] 以建立群組。</span><span class="sxs-lookup"><span data-stu-id="c4514-147">When you've finished, click **Save** to create the group.</span></span> <span data-ttu-id="c4514-148">新的群組應該出現在群組清單。</span><span class="sxs-lookup"><span data-stu-id="c4514-148">The new group should appear in the list of groups.</span></span> 
    
## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="c4514-149">編輯或移除在 EAC 中的群組</span><span class="sxs-lookup"><span data-stu-id="c4514-149">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="c4514-150">In the EAC, navigate to **Recipients** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="c4514-150">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="c4514-151">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="c4514-151">Do one of the following:</span></span>
    
  - <span data-ttu-id="c4514-152">若要編輯群組： 在群組清單中，按一下您要檢視或變更的 [安全性] 群組的通訊群組，然後按一下 [**編輯**![編輯圖示](../media/ITPro-EAC-EditIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="c4514-152">To edit a group: In the list of groups, click the distribution or security group that you want to view or change, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="c4514-153">您可以更新的一般設定、 新增或移除群組擁有者，並新增或移除群組成員，視需要。</span><span class="sxs-lookup"><span data-stu-id="c4514-153">You can update general settings, add or remove group owners, and add or remove group members, as needed.</span></span>
    
  - <span data-ttu-id="c4514-154">若要移除群組： 選取群組，然後按一下 [**移除**![移除圖示](../media/ITPro-EAC-RemoveIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="c4514-154">To remove a group: Select the group and click **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>
    
3. <span data-ttu-id="c4514-155">當您完成變更後時，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="c4514-155">When you're finished making your changes, click **Save**.</span></span>
    
## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="c4514-156">建立、 編輯或移除群組使用遠端 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4514-156">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="c4514-157">本節提供建立群組，並使用遠端 Windows PowerShell 來變更其內容的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c4514-157">This section provides information about creating groups and changing their properties by using remote Windows PowerShell.</span></span> <span data-ttu-id="c4514-158">它也會顯示如何移除現有的群組。</span><span class="sxs-lookup"><span data-stu-id="c4514-158">It also shows how to remove an existing group.</span></span> 
  
 <span data-ttu-id="c4514-159">**若要建立群組使用遠端 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c4514-159">**To create a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="c4514-160">本範例會使用[New-eopdistributiongroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx)指令程式來建立通訊群組別名為 itadmin 與名稱 IT 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c4514-160">This example uses the [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators.</span></span> <span data-ttu-id="c4514-161">它也會新增為群組的成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="c4514-161">It also adds users as members of the group.</span></span> 
  
```Powershell
New-EOPDistributionGroup -Type "Distribution" -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy "Member1"

```

<span data-ttu-id="c4514-162">若要建立安全性群組，而不是通訊群組，請指定`-Type "Security"`改為。</span><span class="sxs-lookup"><span data-stu-id="c4514-162">To create a security group instead of a distribution group, specify  `-Type "Security"` instead.</span></span> 
  
<span data-ttu-id="c4514-163">若要確認您是否已成功建立 IT Administrators 群組，請執行[Get-recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx)指令程式，來顯示新群組的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="c4514-163">To verify that you've successfully created the IT Administrators group, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to display information about the new group:</span></span> 
  
```Powershell
Get-Recipient "IT Administrators" | Format-List

```

<span data-ttu-id="c4514-164">若要取得成員的清單中的群組，請執行[Get-distributiongroupmember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx)指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c4514-164">To get a list of members in the group, run the [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet as follows:</span></span> 
  
```Powershell
Get-DistributionGroupMember "IT Administrators"

```

<span data-ttu-id="c4514-165">若要取得所有群組的完整清單，請執行[Get-recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx)指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c4514-165">To get a full list of all your groups, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows:</span></span> 
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | FT | more

```

 <span data-ttu-id="c4514-166">**若要變更的群組使用遠端 Windows PowerShell 屬性**</span><span class="sxs-lookup"><span data-stu-id="c4514-166">**To change the properties of a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="c4514-167">使用[Get-recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx)和[Set-eopdistributiongroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx)指令程式來檢視和變更群組的內容。</span><span class="sxs-lookup"><span data-stu-id="c4514-167">Use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) and [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlets to view and change properties for groups.</span></span> <span data-ttu-id="c4514-168">使用遠端 PowerShell，而不 EAC 的優點是能夠變更多個群組的屬性。</span><span class="sxs-lookup"><span data-stu-id="c4514-168">An advantage of using remote PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span> 
  
<span data-ttu-id="c4514-169">以下是使用遠端 Windows PowerShell 變更群組屬性的一些範例。</span><span class="sxs-lookup"><span data-stu-id="c4514-169">Here are some examples of using remote Windows PowerShell to change group properties.</span></span>
  
<span data-ttu-id="c4514-170">此範例使用[Set-eopdistributiongroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx)指令程式來變更為 sea.employees@contoso.com 的主要 SMTP 位址 （也稱為 「 回覆地址） 將 Seattle Employees 群組。</span><span class="sxs-lookup"><span data-stu-id="c4514-170">This example uses the [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlet to change the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span> 
  
```Powershell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"

```

<span data-ttu-id="c4514-171">若要確認您已成功變更群組的內容，請使用[Get-recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx)指令程式來驗證變更。</span><span class="sxs-lookup"><span data-stu-id="c4514-171">To verify that you've successfully changed the properties for a group, use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to verify the changes.</span></span> <span data-ttu-id="c4514-172">使用遠端 PowerShell 的其中一個優勢是，您可以檢視多個群組的多個屬性。</span><span class="sxs-lookup"><span data-stu-id="c4514-172">One advantage of using remote PowerShell is that you can view multiple properties for multiple groups.</span></span> <span data-ttu-id="c4514-173">在前一個範例中變更主要 SMTP 地址，群組的位置，請執行下列命令，以驗證新值：</span><span class="sxs-lookup"><span data-stu-id="c4514-173">In the previous example where the primary SMTP address group was changed, run the following command to verify the new value:</span></span> 
  
```Powershell
Get-Recipient "Seattle Employees" | FL "PrimarySmtpAddress"

```

<span data-ttu-id="c4514-174">本範例會使用[更新 EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx)指令程式來更新所有將 Seattle Employees 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c4514-174">This example uses the [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) cmdlet to update all the members of the Seattle Employees group.</span></span> <span data-ttu-id="c4514-175">使用逗點分隔的所有成員。</span><span class="sxs-lookup"><span data-stu-id="c4514-175">Use a comma to separate all members.</span></span> 
  
```Powershell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")

```

<span data-ttu-id="c4514-176">若要取得 Seattle Employees 群組中的所有成員的清單，請使用[Get-distributiongroupmember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx)指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c4514-176">To get the list of all the members in the group Seattle Employees, use the [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet as follows:</span></span> 
  
```Powershell
Get-DistributionGroupMember "Seattle Employees"

```

 <span data-ttu-id="c4514-177">**若要移除群組使用遠端 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c4514-177">**To remove a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="c4514-178">此範例使用[Remove-eopdistributiongroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx)指令程式來移除名為 IT 系統管理員的通訊群組。</span><span class="sxs-lookup"><span data-stu-id="c4514-178">This example uses the [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) cmdlet to remove a distribution group named IT Administrators.</span></span> 
  
```Powershell
Remove-EOPDistributionGroup -Identity "IT Administrators" 

```

<span data-ttu-id="c4514-179">若要確認已移除群組，請執行[Get-recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx)指令程式，如下所示，並確認已刪除群組 （在此情況下"It Administrators"）。</span><span class="sxs-lookup"><span data-stu-id="c4514-179">To verify that the group was removed, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows, and confirm that the group (in this case "It Administrators") was deleted.</span></span> 
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"

```


