---
title: 管理 EOP 中的郵件使用者
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 定義郵件使用者是管理 Exchange Online Protection (EOP) 的重要環節。
ms.openlocfilehash: 9ab4420dd9fcf6c056bc661b5f3646672a89a683
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670638"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="a9ca8-103">管理 EOP 中的郵件使用者</span><span class="sxs-lookup"><span data-stu-id="a9ca8-103">Manage mail users in EOP</span></span>

<span data-ttu-id="a9ca8-p101">定義郵件使用者是管理 Exchange Online Protection (EOP) 的重要環節。在 EOP 中，您可以透過數種方式來管理使用者：</span><span class="sxs-lookup"><span data-stu-id="a9ca8-p101">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service. There are several ways that you can manage users in EOP:</span></span>
  
- <span data-ttu-id="a9ca8-106">使用目錄同步處理來管理郵件使用者：如果您的公司在內部部署 Active Directory 環境中有現有的使用者帳戶，您可將這些帳戶同步處理至 Azure Active Directory (AD)，此工具會將這些帳戶的複本儲存至雲端。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-106">Use directory synchronization to manage mail users: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud.</span></span> <span data-ttu-id="a9ca8-107">將現有的使用者帳戶同步處理至 Azure Active Directory 時，您可以在 Exchange 系統管理中心 (EAC) 的 [**收件者**] 窗格中檢視這些使用者。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-107">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC).</span></span> <span data-ttu-id="a9ca8-108">建議使用目錄同步作業。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-108">Using directory synchronization is recommended.</span></span> 
    
- <span data-ttu-id="a9ca8-109">使用 EAC 管理郵件使用者：在 EAC 中直接新增及管理郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-109">Use the EAC to manage mail users: Add and manage mail users directly in the EAC.</span></span> <span data-ttu-id="a9ca8-110">這是新增郵件使用者最簡單的方法，也很適合一次新增一位使用者。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-110">This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>
    
- <span data-ttu-id="a9ca8-111">使用遠端 Windows PowerShell 管理郵件使用者：執行遠端 Windows PowerShell 來新增和管理郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-111">Use remote Windows PowerShell to manage mail users: Add and manage mail users by running remote Windows PowerShell.</span></span> <span data-ttu-id="a9ca8-112">這個方法適合用來新增多筆記錄和建立指令碼。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-112">This method is useful for adding multiple records and creating scripts.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a9ca8-113">您可以在 Microsoft 365 系統管理中心中，新增使用者，不過，這些使用者不能當成郵件收件者。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-113">You can add users in the Microsoft 365 admin center, however these users can't be used as mail recipients.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="a9ca8-114">開始之前</span><span class="sxs-lookup"><span data-stu-id="a9ca8-114">Before you begin</span></span>

- <span data-ttu-id="a9ca8-p105">本主題中的程序需要特定權限。請查看每個程序以取得權限資訊。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-p105">Procedures in this topic require specific permissions. See each procedure for its permissions information.</span></span>
    
- <span data-ttu-id="a9ca8-117">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="a9ca8-p106">有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-p106">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="a9ca8-121">使用目錄同步處理來管理郵件使用者</span><span class="sxs-lookup"><span data-stu-id="a9ca8-121">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="a9ca8-122">本節提供使用目錄同步處理來管理電子郵件使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-122">This section provides information about managing email users by using directory synchronization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a9ca8-123">如果您使用目錄同步作業管理收件者時，您仍然可以新增及管理使用者在 Microsoft 365 系統管理中心中，但它們不會與您在內部部署 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-123">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="a9ca8-124">這是因為目錄同步作業只會從內部部署 Active Directory 同步收件者至雲端。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-124">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span> 
  
> [!TIP]
>  <span data-ttu-id="a9ca8-125">建議搭配下列功能一起使用目錄同步處理： > **Outlook 安全的寄件者和封鎖的寄件者清單** - 同步處理至服務時，這些清單優先於服務的垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-125">Using directory synchronization is recommended for use with the following features: > **Outlook safe sender and blocked sender lists** - When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="a9ca8-126">這可讓使用者針對個別使用者或個別網域，管理他們自己的安全寄件者和封鎖的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-126">This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis.</span></span><span data-ttu-id="a9ca8-127"> > *\*目錄架構邊緣封鎖 (DBEB)** - 如需 DBEB 的詳細資訊，請參閱＜ [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-127"> > *\*Directory Based Edge Blocking (DBEB)** - For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span><span data-ttu-id="a9ca8-128"> > *\*使用者垃圾郵件隔離** - 若要存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-128"> > *\*End user spam quarantine** - In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="a9ca8-129">保護內部部署信箱的 EOP 客戶必須是有效的電子郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-129">EOP customers protecting on-premises mailboxes must be valid email users.</span></span><span data-ttu-id="a9ca8-130"> > *\*郵件流程規則*\*-當您使用目錄同步處理，您現有的 Active Directory 使用者和群組會自動上傳至雲端，您可以再建立郵件流程規則 （也稱為傳輸規則），針對特定的使用者及 （或)群組，而不必手動新增他們透過 EAC 或 Exchange Online Protection PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-130"> > *\*Mail flow rules** - When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules (also known as transport rules) that target specific users and/or groups without having to manually add them via the the EAC or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="a9ca8-131">請注意， [動態通訊群組](https://go.microsoft.com/fwlink/?LinkId=507569)無法透過目錄同步作業進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-131">Note that [dynamic distribution groups](https://go.microsoft.com/fwlink/?LinkId=507569) can't be synchronized via directory synchronization.</span></span> 
  
 <span data-ttu-id="a9ca8-132">**開始之前**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-132">**Before you begin**</span></span>
  
<span data-ttu-id="a9ca8-133">取得必要權限，並做好目錄同步處理的準備工作，如[為目錄同步作業做好準備](https://go.microsoft.com/fwlink/p/?LinkId=308908)所說明。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-133">Get the necessary permissions and prepare for directory synchronization, as described in [Prepare for directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span></span>
  
### <a name="to-synchronize-user-directories"></a><span data-ttu-id="a9ca8-134">同步處理使用者目錄</span><span class="sxs-lookup"><span data-stu-id="a9ca8-134">To synchronize user directories</span></span>

1. <span data-ttu-id="a9ca8-135">啟動目錄同步處理，如[啟動目錄同步處理](https://go.microsoft.com/fwlink/p/?LinkId=308909)所說明。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-135">Activate directory synchronization, as described in [Activate directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span></span>
    
2. <span data-ttu-id="a9ca8-136">設定目錄同步處理電腦，如[設定您的目錄同步處理電腦](http://go.microsoft.com/fwlink/p/?LinkId=308911)所說明。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-136">Set up your directory synchronization computer, as described in [Set up your directory sync computer](http://go.microsoft.com/fwlink/p/?LinkId=308911).</span></span>
    
3. <span data-ttu-id="a9ca8-137">同步處理您的目錄，如[使用設定精靈同步處理您的目錄](http://go.microsoft.com/fwlink/?LinkId=308912)所說明。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-137">Synchronize your directories, as described in [Use the Configuration Wizard to sync your directories](http://go.microsoft.com/fwlink/?LinkId=308912).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a9ca8-p109">完成 Azure Active Directory 同步處理工具設定精靈 之後，您的 Active Directory 樹系中會建立 **MSOL_AD_SYNC** 帳戶。此帳戶將用來讀取和同步處理您的內部部署 Active Directory 資訊。為了讓目錄同步作業能夠正確運作，請確定有開啟您的本機目錄同步作業伺服器上的 TCP 443。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-p109">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span> 
  
4. <span data-ttu-id="a9ca8-141">啟動已同步處理的使用者，如[啟用同步處理的使用者](http://go.microsoft.com/fwlink/p/?LinkId=308913)所說明。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-141">Activate synced users, as described in [Activate synced users](http://go.microsoft.com/fwlink/p/?LinkId=308913).</span></span>
    
5. <span data-ttu-id="a9ca8-142">管理目錄同步處理，如[管理目錄同步作業](http://go.microsoft.com/fwlink/p/?LinkId=308915)所說明。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-142">Manage directory synchronization, as described in [Manage directory synchronization](http://go.microsoft.com/fwlink/p/?LinkId=308915).</span></span>
    
6. <span data-ttu-id="a9ca8-p110">Verify that EOP is synchronizing correctly. In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span><span class="sxs-lookup"><span data-stu-id="a9ca8-p110">Verify that EOP is synchronizing correctly. In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span> 
    
## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="a9ca8-145">使用 EAC 管理郵件使用者</span><span class="sxs-lookup"><span data-stu-id="a9ca8-145">Use the EAC to manage mail users</span></span>

<span data-ttu-id="a9ca8-146">本節提供直接在 EAC 中新增及管理電子郵件使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-146">This section provides information about adding and managing email users directly in the EAC.</span></span>
  
 <span data-ttu-id="a9ca8-147">**開始之前**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-147">**Before you begin**</span></span>
  
<span data-ttu-id="a9ca8-p111">您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)中的「使用者、連絡人和角色群組」項目。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-p111">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>
  
### <a name="to-add-a-mail-user-in-the-eac"></a><span data-ttu-id="a9ca8-150">在 EAC 中新增郵件使用者</span><span class="sxs-lookup"><span data-stu-id="a9ca8-150">To add a mail user in the EAC</span></span>

1. <span data-ttu-id="a9ca8-151">移至 EAC 中的 [ **收件者**] \> [ **連絡人**]，然後按一下 [ **新增 +**]，以建立電子郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-151">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>
    
2. <span data-ttu-id="a9ca8-152">在 [ **新增郵件使用者**] 頁面上，輸入使用者的資訊，包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="a9ca8-152">On the **New mail user** page, enter the user's information, including the following:</span></span> 
    
   ****

|<span data-ttu-id="a9ca8-153">**郵件使用者內容**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-153">**Mail user property**</span></span>|<span data-ttu-id="a9ca8-154">**描述**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9ca8-155">**名字**、 **縮寫**和 **姓氏**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-155">**First name**, **Initials**, and **Last name**</span></span> <br/> |<span data-ttu-id="a9ca8-156">在適當的方塊中輸入使用者的完整名稱。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-156">Type the user's full name in the appropriate boxes.</span></span>  <br/> |
|<span data-ttu-id="a9ca8-157">**顯示名稱**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-157">**Display name**</span></span> <br/> |<span data-ttu-id="a9ca8-p112">輸入名稱，最多 64 個字元。根據預設，此方塊會顯示 [**名字**]、[**縮寫**] 和 [**姓氏**] 方塊中的名稱 (如果有的話)。顯示名稱是必要項目。  </span><span class="sxs-lookup"><span data-stu-id="a9ca8-p112">Type a name, using up to 64 characters. By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any. The display name is required.  </span></span><br/> |
|<span data-ttu-id="a9ca8-161">**別名**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-161">**Alias**</span></span> <br/> |<span data-ttu-id="a9ca8-p113">輸入使用者的唯一別名，最多 64 個字元。別名是必要項目。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-p113">Type a unique alias, using up to 64 characters, for the user. The alias is required.</span></span>  <br/> |
|<span data-ttu-id="a9ca8-164">**外部電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-164">**External email address**</span></span> <br/> |<span data-ttu-id="a9ca8-165">輸入使用者的外部電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-165">Type the external email address of the user.</span></span>  <br/> |
|<span data-ttu-id="a9ca8-166">**使用者識別碼**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-166">**User id**</span></span> <br/> |<span data-ttu-id="a9ca8-p114">輸入郵件使用者將用來登入服務的名稱。使用者登入名稱由 @ 符號左側的使用者名稱和右側的尾碼所組成。一般來說，尾碼是使用者帳戶所在的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-p114">Type the name that the mail user will use to sign in to the service. The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side. Typically, the suffix is the domain name in which the user account resides.</span></span>  <br/> |
|<span data-ttu-id="a9ca8-170">**新密碼**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-170">**New password**</span></span> <br/> |<span data-ttu-id="a9ca8-p115">輸入郵件使用者將用來登入服務的密碼。請確定您提供的密碼符合您正在其中建立使用者帳戶之網域的密碼長度、複雜性和歷程記錄需求。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-p115">Type the password that the mail user will use to sign in to the service. Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>  <br/> |
|<span data-ttu-id="a9ca8-173">**確認密碼**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-173">**Confirm password**</span></span> <br/> |<span data-ttu-id="a9ca8-174">重新輸入密碼加以確認。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-174">Retype the password to confirm it.</span></span>  <br/> |
   
3. <span data-ttu-id="a9ca8-p116">按一下 [**儲存**]，以建立新的郵件使用者。新的使用者應會出現在使用者清單中。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-p116">Click **Save** to create the new email user. The new user should appear in the list of users.</span></span> 
    
### <a name="to-edit-or-remove-a-mail-user-in-the-eac"></a><span data-ttu-id="a9ca8-177">在 EAC 中編輯或移除郵件使用者</span><span class="sxs-lookup"><span data-stu-id="a9ca8-177">To edit or remove a mail user in the EAC</span></span>

- <span data-ttu-id="a9ca8-178">In the EAC, go to **Recipients** \> **Contacts**.</span><span class="sxs-lookup"><span data-stu-id="a9ca8-178">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="a9ca8-179">在使用者清單中，按一下您要檢視或變更的使用者，然後選取 [**編輯**![編輯圖示](../media/ITPro-EAC-EditIcon.gif)以視需要更新使用者設定。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-179">In the list of users, click the user that you want to view or change, and then select **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif) to update the user settings as needed.</span></span> <span data-ttu-id="a9ca8-180">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span><span class="sxs-lookup"><span data-stu-id="a9ca8-180">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span></span> <span data-ttu-id="a9ca8-181">You can also select a user and then choose **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span><span class="sxs-lookup"><span data-stu-id="a9ca8-181">You can also select a user and then choose **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span></span> 
    
## <a name="use-remote-windows-powershell-to-manage-mail-users"></a><span data-ttu-id="a9ca8-182">使用遠端 Windows PowerShell 管理郵件使用者</span><span class="sxs-lookup"><span data-stu-id="a9ca8-182">Use remote Windows PowerShell to manage mail users</span></span>

<span data-ttu-id="a9ca8-183">本節提供使用遠端 Windows PowerShell 來新增和管理郵件使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-183">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>
  
 <span data-ttu-id="a9ca8-184">**開始之前**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-184">**Before you begin**</span></span>
  
- <span data-ttu-id="a9ca8-p118">您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)中的「使用者、連絡人和角色群組」項目。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-p118">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>
    
- <span data-ttu-id="a9ca8-187">請注意，使用遠端 PowerShell 指令程式建立郵件使用者時，可能會遇到節流問題。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-187">Be aware that when creating mail users by using remote PowerShell cmdlets, you may encounter throttling.</span></span>
    
- <span data-ttu-id="a9ca8-188">此指令程式採用批次處理方法，因此導致幾分鐘的傳播延遲，然後才能看到指令程式的結果。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-188">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
    
- <span data-ttu-id="a9ca8-189">若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱＜[使用遠端 PowerShell 連線到 Exchange Online Protection](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-189">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection Using Remote PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span></span>
    
 <span data-ttu-id="a9ca8-190">**使用遠端 PowerShell 新增郵件使用者**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-190">**To add a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="a9ca8-191">此範例使用 [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) 在 EOP 中為 Jeffrey Zeng 建立具有郵件功能的使用者帳戶，詳細資料如下：</span><span class="sxs-lookup"><span data-stu-id="a9ca8-191">This example uses the [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span> 
  
- <span data-ttu-id="a9ca8-192">名字為 Jeffrey，姓氏為 Zeng。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-192">The first name is Jeffrey and the last name is Zeng.</span></span>
    
- <span data-ttu-id="a9ca8-193">名稱是 Jeffrey，而顯示名稱是 Jeffrey Zeng。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-193">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>
    
- <span data-ttu-id="a9ca8-194">別名為 jeffreyz。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-194">The alias is jeffreyz.</span></span>
    
- <span data-ttu-id="a9ca8-195">外部電子郵件地址為 jzeng@tailspintoys.com。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-195">The external email address is jzeng@tailspintoys.com.</span></span>
    
- <span data-ttu-id="a9ca8-196">Office 365 登入名稱是 jeffreyz@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-196">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>
    
- <span data-ttu-id="a9ca8-197">密碼為 Pa$$word1。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-197">The password is Pa$$word1.</span></span>
    
```Powershell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

 <span data-ttu-id="a9ca8-198">**確認此作業正常運作**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-198">**To verify that this worked**</span></span>
  
<span data-ttu-id="a9ca8-199">依下列方式執行 [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) 指令程式，以顯示新郵件使用者 Jeffrey Zeng 的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="a9ca8-199">Run the [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) cmdlet as follows to display information about new mail user Jeffrey Zeng:</span></span> 
  
```Powershell
Get-User "Jeffrey Zeng"

```

 <span data-ttu-id="a9ca8-200">**使用遠端 PowerShell 編輯郵件使用者的屬性**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-200">**To edit the properties of a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="a9ca8-201">使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) 和 [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) 指令程式來檢視或變更郵件使用者的屬性。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-201">Use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) and [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) cmdlets to view or change properties for mail users.</span></span> 
  
<span data-ttu-id="a9ca8-202">此範例會設定 Pilar Pinilla 的外部電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-202">This example sets the external email address for Pilar Pinilla.</span></span>
  
```Powershell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="a9ca8-203">此範例會將所有郵件使用者的 [公司] 內容設定為 [Contoso]。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-203">This example sets the Company property for all mail users to Contoso.</span></span>
  
```Powershell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}

```

 <span data-ttu-id="a9ca8-204">**確認此作業正常運作**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-204">**To verify that this worked**</span></span>
  
<span data-ttu-id="a9ca8-p119">上述範例中我們變更郵件使用者 Pilar Pinella 的屬性，請使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) 指令程式來驗證變更(請注意，您可以檢視多個郵件連絡人的多個屬性)。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-p119">In the previous example where we changed the properties for mail user Pilar Pinella, use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to verify the changes. (Note that you can view multiple properties for multiple mail contacts.)</span></span> 
  
```Powershell
Get-Recipient -Identity "Pilar Pinilla" | Format-List 

```

<span data-ttu-id="a9ca8-207">在上述範例中，所有郵件使用者的 [公司] 屬性設為 [Contoso]，請執行下列命令來驗證變更：</span><span class="sxs-lookup"><span data-stu-id="a9ca8-207">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>
  
```Powershell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="a9ca8-208">此指令程式採用批次處理方法，因此導致幾分鐘的傳播延遲，然後才能看到指令程式的結果。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-208">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span> 
  
 <span data-ttu-id="a9ca8-209">**使用遠端 PowerShell 移除郵件使用者**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-209">**To remove a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="a9ca8-210">此範例使用 [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) 指令程式來刪除使用者 Jeffrey Zeng：</span><span class="sxs-lookup"><span data-stu-id="a9ca8-210">This example uses the [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) cmdlet to delete user Jeffrey Zeng:</span></span> 
  
```Powershell
Remove-EOPMailUser -Identity Jeffrey
```

 <span data-ttu-id="a9ca8-211">**確認此作業正常運作**</span><span class="sxs-lookup"><span data-stu-id="a9ca8-211">**To verify that this worked**</span></span>
  
<span data-ttu-id="a9ca8-p120">依下列方式執行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) 指令程式。應該會出現錯誤訊息，因為使用者已不存在。</span><span class="sxs-lookup"><span data-stu-id="a9ca8-p120">Run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows. You should get an error message since the user no longer exists.</span></span> 
  
```Powershell
Get-Recipient Jeffrey | fl
```


