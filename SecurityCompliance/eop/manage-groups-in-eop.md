---
title: 管理 EOP 中的群組
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: 您可以使用 Exchange Online Protection (EOP) 來建立具有郵件功能的 Exchange 組織的群組。您也可以使用 EOP 來定義或更新群組屬性指定成員資格、 電子郵件地址及其他考量的群組。
ms.openlocfilehash: 744a28d2003496650e7350108797cc5cc4eaad4f
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026340"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="f3f5b-104">管理 EOP 中的群組</span><span class="sxs-lookup"><span data-stu-id="f3f5b-104">Manage groups in EOP</span></span>

 <span data-ttu-id="f3f5b-p102">您可以使用 Exchange Online Protection (EOP) 來建立具有郵件功能的 Exchange 組織的群組。您也可以使用 EOP 來定義或更新群組屬性指定成員資格、 電子郵件地址及其他考量的群組。您可以建立通訊群組和安全性群組，視您的需求而定。使用 Exchange 系統管理中心 (EAC) 或透過遠端 Windows PowerShell 可以建立這些群組。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p102">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization. You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups. You can create distribution groups and security groups, depending on your needs. These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span> 
  
## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="f3f5b-109">擁有郵件功能的群組類型</span><span class="sxs-lookup"><span data-stu-id="f3f5b-109">Types of mail-enabled groups</span></span>

<span data-ttu-id="f3f5b-110">您可以為 Exchange 組織建立兩種類型的群組：</span><span class="sxs-lookup"><span data-stu-id="f3f5b-110">You can create two types of groups for your Exchange organization:</span></span>
  
- <span data-ttu-id="f3f5b-p103">[建立在 EAC 中的群組](manage-groups-in-eop.md)（也稱為通訊群組） 的電子郵件使用者，例如小組或其他臨機操作群組需要收到或電子郵件傳送有關感興趣的公用區的集合。通訊群組是以獨佔方式來散佈電子郵件訊息。在 EOP、 通訊群組是指任何擁有郵件功能的群組已定義的安全性內容。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p103">[Create a group in the EAC](manage-groups-in-eop.md) (also known as distribution groups) are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest. Distribution groups are exclusively for distributing email messages. In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>
    
- <span data-ttu-id="f3f5b-p104">[編輯或移除在 EAC 中的群組](manage-groups-in-eop.md)（也稱為安全性群組） 所需存取權限的系統管理員角色的電子郵件使用者的集合。例如，您可能會想要授與特定使用者群組管理員角色權限讓他們可以設定反垃圾郵件和反惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p104">[Edit or remove a group in the EAC](manage-groups-in-eop.md) (also known as security groups) are collections of email users who need access permissions for Admin roles. For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f3f5b-p105">依預設，所有啟用郵件功能的新安全性群組都會要求所有寄件者經過驗證。如此便可防止外部寄件者傳送郵件給已啟用郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p105">By default, all new mail-enabled security groups require that all senders be authenticated. This prevents external senders from sending messages to mail-enabled security groups.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="f3f5b-118">開始之前</span><span class="sxs-lookup"><span data-stu-id="f3f5b-118">Before you begin</span></span>

- <span data-ttu-id="f3f5b-p106">您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[Feature permissions in EOP](feature-permissions-in-eop.md)主題中的 「 通訊群組和安全性群組 」 項目。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p106">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="f3f5b-121">請注意，使用遠端 PowerShell 指令程式建立和管理群組時，可能會遇到節流問題。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-121">Be aware that when creating and managing groups by using remote PowerShell cmdlets, you may encounter throttling.</span></span>
    
- <span data-ttu-id="f3f5b-122">此指令程式採用批次處理方法，因此導致幾分鐘的傳播延遲，然後才能看到指令程式的結果。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-122">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
    
- <span data-ttu-id="f3f5b-123">若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱＜[使用遠端 PowerShell 連線到 Exchange Online Protection](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-123">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection Using Remote PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span></span>
    
- <span data-ttu-id="f3f5b-124">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-124">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="f3f5b-p107">有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p107">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="f3f5b-128">在 EAC 中建立群組</span><span class="sxs-lookup"><span data-stu-id="f3f5b-128">Create a group in the EAC</span></span>

1. <span data-ttu-id="f3f5b-129">在 Exchange 系統管理中心 (EAC) 中，移至 [**收件者** \> **群組**。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-129">In the Exchange admin center (EAC), go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="f3f5b-p108">按一下 [**新增**![新增圖示](../media/ITPro-EAC-AddIcon.png)、] 和 [**通訊群組**或**安全性群組**，視您的需求而定。請參閱差別[擁有郵件功能的群組類型](manage-groups-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p108">Click **New**![Add Icon](../media/ITPro-EAC-AddIcon.png), and then click **Distribution group** or **Security group**, depending on your needs. See [Types of mail-enabled groups](manage-groups-in-eop.md) for the distinction.</span></span> 
    
3. <span data-ttu-id="f3f5b-132">在 **[新增通訊群組]** 或 **[新增安全性群組]** 頁面上，完成下列欄位：</span><span class="sxs-lookup"><span data-stu-id="f3f5b-132">On the **New distribution group** or **New security group** page, complete the following fields:</span></span> 
    
  - <span data-ttu-id="f3f5b-p109">**顯示名稱**輸入您組織的唯一且有意義 EOP 使用者的顯示名稱。顯示名稱是必要的。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p109">**Display name** Type a display name that's unique to your organization and meaningful to EOP users. The display name is required.</span></span> 
    
  - <span data-ttu-id="f3f5b-p110">**別名**輸入最多 64 個字元的是唯一的您的組織群組別名。EOP 使用者輸入別名中 [收件者： 列的電子郵件訊息與別名解析為群組的顯示名稱。如果您變更別名，群組的主要 SMTP 位址也會變更並將包含新的別名。別名為必要的。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p110">**Alias** Type a group alias of up to 64 characters that's unique to your organization. EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name. If you change the alias, the primary SMTP address for the group also changes and will contain the new alias. The alias is required.</span></span> 
    
  - <span data-ttu-id="f3f5b-139">**描述**輸入群組的描述，使他人了解該群組的用途。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-139">**Description** Type a description of the group so that people will know the purpose of the group.</span></span> 
    
  - <span data-ttu-id="f3f5b-p111">**擁有者**根據預設，會建立群組的人員是擁有者。您可以選擇 [**新增]** 新增擁有者![新增圖示](../media/ITPro-EAC-AddIcon.png)。所有群組都必須至少一個擁有者。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p111">**Owners** By default, the person who creates the group is the owner. You can add an owner by choosing **Add**![Add Icon](../media/ITPro-EAC-AddIcon.png). All groups must have at least one owner.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f3f5b-143">擁有者不必是群組的成員。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-143">Owners don't have to be members of the group.</span></span> 
  
  - <span data-ttu-id="f3f5b-p112">**成員**使用此區段可新增群組成員並指定核准是否需要使用者在加入或離開群組。若要將成員新增至群組中，按一下 [**新增**![新增圖示](../media/ITPro-EAC-AddIcon.png)。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p112">**Members** Use this section to add group members and to specify whether approval is required for people to join or leave the group. To add members to the group, click **Add**![Add Icon](../media/ITPro-EAC-AddIcon.png).</span></span>
    
4. <span data-ttu-id="f3f5b-146">按一下 **[確定]**，以返回原始頁面。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-146">Click **OK** to return to the original page.</span></span> 
    
5. <span data-ttu-id="f3f5b-p113">當您已完成，請按一下 [**儲存**] 以建立群組。新的群組應該會出現在群組清單。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p113">When you've finished, click **Save** to create the group. The new group should appear in the list of groups.</span></span> 
    
## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="f3f5b-149">在 EAC 中編輯或移除群組</span><span class="sxs-lookup"><span data-stu-id="f3f5b-149">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="f3f5b-150">在 EAC 中，瀏覽至 [**收件者** \> **群組**。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-150">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="f3f5b-151">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="f3f5b-151">Do one of the following:</span></span>
    
  - <span data-ttu-id="f3f5b-p114">若要編輯群組： 在群組清單中，按一下 [通訊] 或 [您要檢視或變更的安全性群組] 和 [**編輯**![編輯圖示](../media/ITPro-EAC-EditIcon.png)。您可以更新一般設定、 新增或移除群組擁有者及新增或移除所需的群組成員。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p114">To edit a group: In the list of groups, click the distribution or security group that you want to view or change, and then click **Edit**![Edit icon](../media/ITPro-EAC-EditIcon.png). You can update general settings, add or remove group owners, and add or remove group members, as needed.</span></span>
    
  - <span data-ttu-id="f3f5b-154">若要移除群組： 選取群組，然後按一下 [**移除**![移除圖示](../media/ITPro-EAC-RemoveIcon.png)。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-154">To remove a group: Select the group and click **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.png).</span></span>
    
3. <span data-ttu-id="f3f5b-155">當您完成變更後，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-155">When you're finished making your changes, click **Save**.</span></span>
    
## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="f3f5b-156">使用遠端 Windows PowerShell 建立、編輯或移除群組</span><span class="sxs-lookup"><span data-stu-id="f3f5b-156">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="f3f5b-p115">本節提供使用遠端 Windows PowerShell 來建立群組和變更其屬性的相關資訊。其中也說明如何移除現有的群組。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p115">This section provides information about creating groups and changing their properties by using remote Windows PowerShell. It also shows how to remove an existing group.</span></span> 
  
 <span data-ttu-id="f3f5b-159">**使用遠端 Windows PowerShell 建立群組**</span><span class="sxs-lookup"><span data-stu-id="f3f5b-159">**To create a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="f3f5b-p116">此範例使用 [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) 指令程式，以別名 itadmin 和名稱 IT Administrators 建立通訊群組。它也將使用者加入為群組的成員。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p116">This example uses the [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators. It also adds users as members of the group.</span></span> 
  
```
New-EOPDistributionGroup -Type "Distribution" -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy "Member1"

```

<span data-ttu-id="f3f5b-162">若要建立安全性群組而不是通訊群組，請指定`-Type "Security"`改用。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-162">To create a security group instead of a distribution group, specify  `-Type "Security"` instead.</span></span> 
  
<span data-ttu-id="f3f5b-163">若要確認您是否已成功建立 IT Administrators 群組，請執行[Get-recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx)指令程式來顯示新群組的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="f3f5b-163">To verify that you've successfully created the IT Administrators group, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to display information about the new group:</span></span> 
  
```
Get-Recipient "IT Administrators" | Format-List

```

<span data-ttu-id="f3f5b-164">若取得群組的成員清單，請執行 [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f3f5b-164">To get a list of members in the group, run the [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet as follows:</span></span> 
  
```
Get-DistributionGroupMember "IT Administrators"

```

<span data-ttu-id="f3f5b-165">若取得所有群組的完整清單，請執行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f3f5b-165">To get a full list of all your groups, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows:</span></span> 
  
```
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | FT | more

```

 <span data-ttu-id="f3f5b-166">**使用遠端 Windows PowerShell 變更群組的屬性**</span><span class="sxs-lookup"><span data-stu-id="f3f5b-166">**To change the properties of a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="f3f5b-p117">使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) 和 [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) 指令程式來檢視和變更群組的屬性。使用遠端 PowerShell 而非 EAC 的好處，是您能夠變更多個群組的屬性。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p117">Use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) and [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlets to view and change properties for groups. An advantage of using remote PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span> 
  
<span data-ttu-id="f3f5b-169">以下是使用遠端 Windows PowerShell 來變更群組屬性的一些範例。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-169">Here are some examples of using remote Windows PowerShell to change group properties.</span></span>
  
<span data-ttu-id="f3f5b-170">此範例使用 [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) 指令程式，將 Seattle Employees 群組的主要 SMTP 位址 (又稱為回覆地址) 變更為 sea.employees@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-170">This example uses the [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlet to change the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span> 
  
```
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"

```

<span data-ttu-id="f3f5b-p118">若要確認您是否已成功變更群組的內容，請使用[Get-recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx)指令程式來確認所做的變更。使用遠端 PowerShell 的一個優點是您可以檢視針對多個群組的多個屬性。在其中變更主要的 SMTP 地址群組上一個範例中，執行下列命令來確認新的值：</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p118">To verify that you've successfully changed the properties for a group, use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to verify the changes. One advantage of using remote PowerShell is that you can view multiple properties for multiple groups. In the previous example where the primary SMTP address group was changed, run the following command to verify the new value:</span></span> 
  
```
Get-Recipient "Seattle Employees" | FL "PrimarySmtpAddress"

```

<span data-ttu-id="f3f5b-p119">此範例使用 [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) 指令程式來更新 Seattle Employees 群組的所有成員。使用逗號隔開多個成員。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-p119">This example uses the [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) cmdlet to update all the members of the Seattle Employees group. Use a comma to separate all members.</span></span> 
  
```
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")

```

<span data-ttu-id="f3f5b-176">若要取得 Seattle Employees 群組中所有成員的清單，請使用 [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f3f5b-176">To get the list of all the members in the group Seattle Employees, use the [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet as follows:</span></span> 
  
```
Get-DistributionGroupMember "Seattle Employees"

```

 <span data-ttu-id="f3f5b-177">**使用遠端 Windows PowerShell 移除群組**</span><span class="sxs-lookup"><span data-stu-id="f3f5b-177">**To remove a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="f3f5b-178">此範例使用 [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) 指令程式來移除名為 IT Administrators 的通信群組。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-178">This example uses the [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) cmdlet to remove a distribution group named IT Administrators.</span></span> 
  
```
Remove-EOPDistributionGroup -Identity "IT Administrators" 

```

<span data-ttu-id="f3f5b-179">若要確認已移除群組，請執行[Get-recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx)指令程式，如下所示，並確認已刪除的群組 （在此例"It Administrators"）。</span><span class="sxs-lookup"><span data-stu-id="f3f5b-179">To verify that the group was removed, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows, and confirm that the group (in this case "It Administrators") was deleted.</span></span> 
  
```
Get-Recipient -RecipientType "MailUniversalDistributionGroup"

```


