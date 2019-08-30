---
title: 管理 EOP 中的郵件使用者
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 定義郵件使用者是管理 Exchange Online Protection (EOP) 的重要環節。
ms.openlocfilehash: 48d530be17a7e75f6e179a50067b1b9526606cb0
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676713"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="a0cd5-103">管理 EOP 中的郵件使用者</span><span class="sxs-lookup"><span data-stu-id="a0cd5-103">Manage mail users in EOP</span></span>

<span data-ttu-id="a0cd5-p101">定義郵件使用者是管理 Exchange Online Protection (EOP) 的重要環節。在 EOP 中，您可以透過數種方式來管理使用者：</span><span class="sxs-lookup"><span data-stu-id="a0cd5-p101">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service. There are several ways that you can manage users in EOP:</span></span>
  
- <span data-ttu-id="a0cd5-106">使用目錄同步處理來管理郵件使用者：如果您的公司在內部部署 Active Directory 環境中有現有的使用者帳戶，您可將這些帳戶同步處理至 Azure Active Directory (AD)，此工具會將這些帳戶的複本儲存至雲端。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-106">Use directory synchronization to manage mail users: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud.</span></span> <span data-ttu-id="a0cd5-107">將現有的使用者帳戶同步處理至 Azure Active Directory 時，您可以在 Exchange 系統管理中心 (EAC) 的 [**收件者**] 窗格中檢視這些使用者。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-107">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC).</span></span> <span data-ttu-id="a0cd5-108">建議使用目錄同步作業。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-108">Using directory synchronization is recommended.</span></span> 

- <span data-ttu-id="a0cd5-109">使用 EAC 管理郵件使用者：在 EAC 中直接新增及管理郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-109">Use the EAC to manage mail users: Add and manage mail users directly in the EAC.</span></span> <span data-ttu-id="a0cd5-110">這是新增郵件使用者最簡單的方法，也很適合一次新增一位使用者。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-110">This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>

- <span data-ttu-id="a0cd5-111">使用遠端 Windows PowerShell 管理郵件使用者：執行遠端 Windows PowerShell 來新增和管理郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-111">Use remote Windows PowerShell to manage mail users: Add and manage mail users by running remote Windows PowerShell.</span></span> <span data-ttu-id="a0cd5-112">這個方法適合用來新增多筆記錄和建立指令碼。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-112">This method is useful for adding multiple records and creating scripts.</span></span>

> [!NOTE]
> <span data-ttu-id="a0cd5-113">您可以在 Microsoft 365 系統管理中心中，新增使用者，不過，這些使用者不能當成郵件收件者。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-113">You can add users in the Microsoft 365 admin center, however these users can't be used as mail recipients.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="a0cd5-114">開始之前</span><span class="sxs-lookup"><span data-stu-id="a0cd5-114">Before you begin</span></span>

- <span data-ttu-id="a0cd5-115">若要開啟 Exchange 系統管理中心，請參閱[Exchange 系統管理中心在 Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-115">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="a0cd5-p105">您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)中的「使用者、連絡人和角色群組」項目。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>

- <span data-ttu-id="a0cd5-118">請注意，當使用 Exchange Online Protection PowerShell cmdlet 建立郵件使用者，您可能會遇到節流問題。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-118">Be aware that when creating mail users by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="a0cd5-119">本主題中的命令使用批次處理方法會導致前一個命令的結果數分鐘的傳播延遲的 PowerShell 是可見。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-119">The PowerShell commands in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="a0cd5-120">若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱[Connect to Exchange Online Protection PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-120">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span></span>

- <span data-ttu-id="a0cd5-121">適用於此主題中程序的鍵盤快速鍵相關資訊，請參閱[Exchange 系統管理員的鍵盤快速鍵置在 Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="a0cd5-122">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="a0cd5-122">Having problems?</span></span> <span data-ttu-id="a0cd5-123">要求在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)論壇中的協助。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="a0cd5-124">使用目錄同步處理來管理郵件使用者</span><span class="sxs-lookup"><span data-stu-id="a0cd5-124">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="a0cd5-125">本節提供使用目錄同步處理來管理電子郵件使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-125">This section provides information about managing email users by using directory synchronization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0cd5-126">如果您使用目錄同步作業管理收件者時，您仍然可以新增及管理使用者在 Microsoft 365 系統管理中心中，但它們不會與您在內部部署 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-126">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="a0cd5-127">這是因為目錄同步作業只會從內部部署 Active Directory 同步收件者至雲端。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-127">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span> <br/><br/> <span data-ttu-id="a0cd5-128">目錄同步作業被建議使用下列功能：</span><span class="sxs-lookup"><span data-stu-id="a0cd5-128">Directory synchronization is recommended for use with the following features:</span></span> <br/><br/><span data-ttu-id="a0cd5-129">• **Outlook 安全寄件者和封鎖寄件者清單**： 這些清單時進行同步處理至服務，將會優先於垃圾郵件篩選服務中。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-129">• **Outlook safe sender and blocked sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="a0cd5-130">這可讓使用者針對個別使用者或個別網域，管理他們自己的安全寄件者和封鎖的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-130">This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis.</span></span> <br/><br/><span data-ttu-id="a0cd5-131">•**目錄架構邊緣封鎖 (DBEB)**: 如需 DBEB 的詳細資訊，請參閱[使用 Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-131">• **Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span> <br/><br/><span data-ttu-id="a0cd5-132">•**使用者垃圾郵件隔離區**： 若要存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-132">• **End user spam quarantine**: In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="a0cd5-133">保護內部部署信箱的 EOP 客戶必須是有效的電子郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-133">EOP customers protecting on-premises mailboxes must be valid email users.</span></span> <br/><br/><span data-ttu-id="a0cd5-134">•**郵件流程規則**： 當您使用目錄同步處理，您現有的 Active Directory 使用者和群組會自動上傳至雲端，您可以再建立郵件流程規則 （也稱為傳輸規則），針對特定的使用者及 （或)群組，而不必手動新增他們透過 EAC 或 Exchange Online Protection PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-134">• **Mail flow rules**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules (also known as transport rules) that target specific users and/or groups without having to manually add them via the the EAC or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="a0cd5-135">請注意， [動態通訊群組](https://go.microsoft.com/fwlink/?LinkId=507569)無法透過目錄同步作業進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-135">Note that [dynamic distribution groups](https://go.microsoft.com/fwlink/?LinkId=507569) can't be synchronized via directory synchronization.</span></span>
  
<span data-ttu-id="a0cd5-136">取得必要權限，並做好目錄同步處理的準備工作，如[為目錄同步作業做好準備](https://go.microsoft.com/fwlink/p/?LinkId=308908)所說明。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-136">Get the necessary permissions and prepare for directory synchronization, as described in [Prepare for directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span></span>
  
### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="a0cd5-137">若要同步處理使用者目錄與 Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="a0cd5-137">To synchronize user directories with Azure Active Directory Connect (AAD Connect)</span></span>

<span data-ttu-id="a0cd5-138">若要同步處理至 Azure Active Directory (AAD) 的使用者第一次必須**啟動目錄同步處理**，如[啟動目錄同步處理](https://go.microsoft.com/fwlink/p/?LinkId=308909)所述。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-138">To synchronize users to Azure Active Directory (AAD) you first have to **activate directory synchronization**, as described in [Activate directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span></span>

<span data-ttu-id="a0cd5-139">下一步是安裝及設定的內部電腦執行 AAD Connect （如果您還沒有一個--一些值得檢查事先）。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-139">Next is the installation and configuration of an on-premises computer to run AAD Connect (if you don't already have one -- something worth checking ahead of time).</span></span> <span data-ttu-id="a0cd5-140">[設定 AAD Connect，快速方式](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)主題會告訴您如何安裝及與 AAD 連線同步到 Azure AD 從內部部署帳戶。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-140">The [Setting up AAD Connect, the express way](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) topic tells you how to setup and synchronize your accounts from on-premises to Azure AD with AAD Connect.</span></span>

<span data-ttu-id="a0cd5-141">但在執行該工作之前，讓某些[您符合必要條件](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)，然後[選擇 [安裝類型](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-141">But before you do that work, make certain [you meet prerequisites](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites), and [choose your installation type](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span></span> <span data-ttu-id="a0cd5-142">快速安裝簡短文章是前面的連結。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-142">The earlier link is to a short article for express installs.</span></span> <span data-ttu-id="a0cd5-143">如果時需要這些，您也可以找到[自訂的安裝](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)或[通過驗證](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)的文章。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-143">You can also find articles on [custom installations](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom), or [pass-through authentication](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) if they're needed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0cd5-p114">完成 Azure Active Directory 同步處理工具設定精靈 之後，您的 Active Directory 樹系中會建立 **MSOL_AD_SYNC** 帳戶。此帳戶將用來讀取和同步處理您的內部部署 Active Directory 資訊。為了讓目錄同步作業能夠正確運作，請確定有開啟您的本機目錄同步作業伺服器上的 TCP 443。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-p114">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="a0cd5-147">設定後您同步處理，請務必確認，則 EOP 會正確同步處理。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-147">After configuring your sync, be sure to verify that EOP is synchronizing correctly.</span></span> <span data-ttu-id="a0cd5-148">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span><span class="sxs-lookup"><span data-stu-id="a0cd5-148">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>

## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="a0cd5-149">使用 EAC 管理郵件使用者</span><span class="sxs-lookup"><span data-stu-id="a0cd5-149">Use the EAC to manage mail users</span></span>

<span data-ttu-id="a0cd5-150">本節提供直接在 EAC 中新增及管理電子郵件使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-150">This section provides information about adding and managing email users directly in the EAC.</span></span>
  
### <a name="use-the-eac-to-add-a-mail-user"></a><span data-ttu-id="a0cd5-151">使用 EAC 來新增郵件使用者</span><span class="sxs-lookup"><span data-stu-id="a0cd5-151">Use the EAC to add a mail user</span></span>

1. <span data-ttu-id="a0cd5-152">移至 EAC 中的 [ **收件者**] \> [ **連絡人**]，然後按一下 [ **新增 +**]，以建立電子郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-152">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>

2. <span data-ttu-id="a0cd5-153">在 [ **新增郵件使用者**] 頁面上，輸入使用者的資訊，包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="a0cd5-153">On the **New mail user** page, enter the user's information, including the following:</span></span> 

   ****

   |<span data-ttu-id="a0cd5-154">**郵件使用者內容**</span><span class="sxs-lookup"><span data-stu-id="a0cd5-154">**Mail user property**</span></span>|<span data-ttu-id="a0cd5-155">**描述**</span><span class="sxs-lookup"><span data-stu-id="a0cd5-155">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="a0cd5-156">**名字**、 **縮寫**和 **姓氏**</span><span class="sxs-lookup"><span data-stu-id="a0cd5-156">**First name**, **Initials**, and **Last name**</span></span>|<span data-ttu-id="a0cd5-157">在適當的方塊中輸入使用者的完整名稱。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-157">Type the user's full name in the appropriate boxes.</span></span>|
   |<span data-ttu-id="a0cd5-158">**顯示名稱**</span><span class="sxs-lookup"><span data-stu-id="a0cd5-158">**Display name**</span></span>|<span data-ttu-id="a0cd5-p116">輸入名稱，最多 64 個字元。根據預設，此方塊會顯示 [**名字**]、[**縮寫**] 和 [**姓氏**] 方塊中的名稱 (如果有的話)。顯示名稱是必要項目。  </span><span class="sxs-lookup"><span data-stu-id="a0cd5-p116">Type a name, using up to 64 characters. By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any. The display name is required.</span></span>|
   |<span data-ttu-id="a0cd5-162">**別名**</span><span class="sxs-lookup"><span data-stu-id="a0cd5-162">**Alias**</span></span>|<span data-ttu-id="a0cd5-p117">輸入使用者的唯一別名，最多 64 個字元。別名是必要項目。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-p117">Type a unique alias, using up to 64 characters, for the user. The alias is required.</span></span>|
   |<span data-ttu-id="a0cd5-165">**外部電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="a0cd5-165">**External email address**</span></span>|<span data-ttu-id="a0cd5-166">輸入使用者的外部電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-166">Type the external email address of the user.</span></span>|
   |<span data-ttu-id="a0cd5-167">**使用者識別碼**</span><span class="sxs-lookup"><span data-stu-id="a0cd5-167">**User id**</span></span>|<span data-ttu-id="a0cd5-p118">輸入郵件使用者將用來登入服務的名稱。使用者登入名稱由 @ 符號左側的使用者名稱和右側的尾碼所組成。一般來說，尾碼是使用者帳戶所在的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-p118">Type the name that the mail user will use to sign in to the service. The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side. Typically, the suffix is the domain name in which the user account resides.</span></span>|
   |<span data-ttu-id="a0cd5-171">**新密碼**</span><span class="sxs-lookup"><span data-stu-id="a0cd5-171">**New password**</span></span>|<span data-ttu-id="a0cd5-p119">輸入郵件使用者將用來登入服務的密碼。請確定您提供的密碼符合您正在其中建立使用者帳戶之網域的密碼長度、複雜性和歷程記錄需求。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-p119">Type the password that the mail user will use to sign in to the service. Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>|
   |<span data-ttu-id="a0cd5-174">**確認密碼**</span><span class="sxs-lookup"><span data-stu-id="a0cd5-174">**Confirm password**</span></span>|<span data-ttu-id="a0cd5-175">重新輸入密碼加以確認。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-175">Retype the password to confirm it.</span></span>|

3. <span data-ttu-id="a0cd5-p120">按一下 [ **儲存**]，以建立新的郵件使用者。新的使用者應會出現在使用者清單中。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-p120">Click **Save** to create the new email user. The new user should appear in the list of users.</span></span>

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a><span data-ttu-id="a0cd5-178">使用 EAC 來編輯或移除郵件使用者</span><span class="sxs-lookup"><span data-stu-id="a0cd5-178">Use the EAC to edit or remove a mail user</span></span>

- <span data-ttu-id="a0cd5-179">In the EAC, go to **Recipients** \> **Contacts**.</span><span class="sxs-lookup"><span data-stu-id="a0cd5-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="a0cd5-180">在使用者清單中，按一下您要檢視或變更的使用者，然後選取 [**編輯**![編輯圖示](../media/ITPro-EAC-EditIcon.gif)以視需要更新使用者設定。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-180">In the list of users, click the user that you want to view or change, and then select **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif) to update the user settings as needed.</span></span> <span data-ttu-id="a0cd5-181">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span><span class="sxs-lookup"><span data-stu-id="a0cd5-181">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span></span> <span data-ttu-id="a0cd5-182">您可以也選取使用者，然後選擇 [**移除**![移除圖示](../media/ITPro-EAC-RemoveIcon.gif)將它刪除。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-182">You can also select a user and then choose **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span></span> 

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a><span data-ttu-id="a0cd5-183">使用 Exchange Online Protection PowerShell 來管理郵件使用者</span><span class="sxs-lookup"><span data-stu-id="a0cd5-183">Use Exchange Online Protection PowerShell to manage mail users</span></span>

<span data-ttu-id="a0cd5-184">本節提供使用遠端 Windows PowerShell 來新增和管理郵件使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-184">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>
  
### <a name="use-eop-powershell-to-add-a-mail-user"></a><span data-ttu-id="a0cd5-185">使用 EOP PowerShell 來新增郵件使用者</span><span class="sxs-lookup"><span data-stu-id="a0cd5-185">Use EOP PowerShell to add a mail user</span></span>
  
<span data-ttu-id="a0cd5-186">此範例使用 [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) 在 EOP 中為 Jeffrey Zeng 建立具有郵件功能的使用者帳戶，詳細資料如下：</span><span class="sxs-lookup"><span data-stu-id="a0cd5-186">This example uses the [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span>
  
- <span data-ttu-id="a0cd5-187">名字為 Jeffrey，姓氏為 Zeng。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-187">The first name is Jeffrey and the last name is Zeng.</span></span>

- <span data-ttu-id="a0cd5-188">名稱是 Jeffrey，而顯示名稱是 Jeffrey Zeng。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-188">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>

- <span data-ttu-id="a0cd5-189">別名為 jeffreyz。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-189">The alias is jeffreyz.</span></span>

- <span data-ttu-id="a0cd5-190">外部電子郵件地址為 jzeng@tailspintoys.com。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-190">The external email address is jzeng@tailspintoys.com.</span></span>

- <span data-ttu-id="a0cd5-191">Office 365 登入名稱是 jeffreyz@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-191">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>

- <span data-ttu-id="a0cd5-192">密碼為 Pa$$word1。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-192">The password is Pa$$word1.</span></span>

```Powershell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

<span data-ttu-id="a0cd5-193">若要確認此作業正常運作，請執行下列命令，以顯示新郵件使用者 Jeffrey Zeng 的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="a0cd5-193">To verify that this worked, run the following command to display information about new mail user Jeffrey Zeng:</span></span>
  
```Powershell
Get-User -Identity "Jeffrey Zeng"
```

<span data-ttu-id="a0cd5-194">如需詳細的語法及參數資訊，請參閱[Get-user](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-194">For detailed syntax and parameter information, see [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span></span>

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a><span data-ttu-id="a0cd5-195">使用 EOP PowerShell 編輯郵件使用者的屬性</span><span class="sxs-lookup"><span data-stu-id="a0cd5-195">Use EOP PowerShell to edit the properties of a mail user</span></span>
  
<span data-ttu-id="a0cd5-196">使用 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) 和 [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) 指令程式來檢視或變更郵件使用者的屬性。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-196">Use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) cmdlets to view or change properties for mail users.</span></span>
  
<span data-ttu-id="a0cd5-197">此範例會設定 Pilar Pinilla 的外部電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-197">This example sets the external email address for Pilar Pinilla.</span></span>
  
```Powershell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="a0cd5-198">此範例會將所有郵件使用者的 [公司] 內容設定為 [Contoso]。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-198">This example sets the Company property for all mail users to Contoso.</span></span>
  
```Powershell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```
  
<span data-ttu-id="a0cd5-199">若要確認此作業正常運作，請使用[Get-recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)指令程式來驗證變更。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-199">To verify that this worked, use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify the changes.</span></span> <span data-ttu-id="a0cd5-200">（請注意，您可以檢視多個郵件連絡人的多個屬性）。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-200">(Note that you can view multiple properties for multiple mail contacts.)</span></span>
  
```Powershell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

<span data-ttu-id="a0cd5-201">在上述範例中，所有郵件使用者的 [公司] 屬性設為 [Contoso]，請執行下列命令來驗證變更：</span><span class="sxs-lookup"><span data-stu-id="a0cd5-201">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>
  
```Powershell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="a0cd5-202">此指令程式採用批次處理方法，因此導致幾分鐘的傳播延遲，然後才能看到指令程式的結果。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-202">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
  
### <a name="use-eop-powershell-to-remove-a-mail-user"></a><span data-ttu-id="a0cd5-203">使用 EOP PowerShell 移除郵件使用者</span><span class="sxs-lookup"><span data-stu-id="a0cd5-203">Use EOP PowerShell to remove a mail user</span></span>
  
<span data-ttu-id="a0cd5-204">此範例使用 [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) 指令程式來刪除使用者 Jeffrey Zeng：</span><span class="sxs-lookup"><span data-stu-id="a0cd5-204">This example uses the [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) cmdlet to delete user Jeffrey Zeng:</span></span>
  
```Powershell
Remove-EOPMailUser -Identity Jeffrey
```

 <span data-ttu-id="a0cd5-205">**確認此作業正常運作**</span><span class="sxs-lookup"><span data-stu-id="a0cd5-205">**To verify that this worked**</span></span>
  
<span data-ttu-id="a0cd5-206">若要確認此作業正常運作，請執行[Get-recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)指令程式，來確認郵件使用者不再存在。</span><span class="sxs-lookup"><span data-stu-id="a0cd5-206">To verify that this worked, run the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify that the mail user no longer exists.</span></span>
  
```Powershell
Get-Recipient Jeffrey | Format-List
```
