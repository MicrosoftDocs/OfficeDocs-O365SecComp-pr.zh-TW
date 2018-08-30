---
title: '安裝 Outlook 電腦版的監督增益集 '
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/19/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- ZOL160
ms.assetid: 6c5620e6-aba3-4910-8f3a-b55451656ff7
description: 安裝 Office 365 監督增益集的桌面的 Outlook 版本
ms.openlocfilehash: 0bddf305087bf0d9552c7671da5306db8352143f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526265"
---
# <a name="install-the-supervision-add-in-for-outlook-desktop"></a><span data-ttu-id="500bc-103">安裝 Outlook 電腦版的監督增益集 </span><span class="sxs-lookup"><span data-stu-id="500bc-103">Install the Supervision add-in for Outlook desktop</span></span>

<span data-ttu-id="500bc-p101">若要檢閱監督原則所識別的通訊，請檢閱者使用的監督增益集 Outlook 和 Outlook web app。增益集會自動安裝 Outlook web app 中所指定之原則的所有檢閱者的。不過，檢閱者必須執行完成某些步驟，以安裝在桌面的 Outlook 版本。</span><span class="sxs-lookup"><span data-stu-id="500bc-p101">To review communications identified by a supervision policy, reviewers use the Supervision add-in for Outlook and Outlook web app. The add-in is installed automatically in Outlook web app for all reviewers you specified in the policy. However, reviewers must run through some steps to install it in the desktop version of Outlook.</span></span>
  
> [!NOTE]
> <span data-ttu-id="500bc-p102">使用監督原則您的組織需要的 Office 365 E5 訂閱。如果您不具有該對應並想要嘗試監督，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="500bc-p102">Using supervision policies requires an Office 365 E5 subscription for your organization. If you don't have that plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a><span data-ttu-id="500bc-109">步驟 1： 將複製的監督信箱的地址</span><span class="sxs-lookup"><span data-stu-id="500bc-109">Step 1: Copy the address for the supervision mailbox</span></span>

<span data-ttu-id="500bc-110">若要安裝的 Outlook 桌面增益集，您將需要位址監督信箱建立為監督原則安裝程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="500bc-110">To install the add-in for Outlook desktop, you'll need the address for the supervision mailbox that was created as part of the supervision policy setup.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="500bc-111">如果別人建立原則，您需要從其安裝增益集取得此位址。</span><span class="sxs-lookup"><span data-stu-id="500bc-111">If someone else created the policy, you'll need to get this address from them to install the add-in.</span></span> 
  
 <span data-ttu-id="500bc-112">**若要尋找的監督信箱地址**</span><span class="sxs-lookup"><span data-stu-id="500bc-112">**To find the supervision mailbox address**</span></span>
  
1. <span data-ttu-id="500bc-113">登入[安全性&amp;規範中心](https://protection.office.com)使用 Office 365 組織中的管理帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="500bc-113">Sign into the [Security &amp; Compliance Center](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="500bc-114">移至 [**資料控管** \> **監督**。</span><span class="sxs-lookup"><span data-stu-id="500bc-114">Go to **Data governance** \> **Supervision**.</span></span>
    
3. <span data-ttu-id="500bc-115">按一下 [收集您想要檢閱的通訊的監督原則。</span><span class="sxs-lookup"><span data-stu-id="500bc-115">Click the supervision policy that's gathering the communications you want to review.</span></span>
    
4. <span data-ttu-id="500bc-116">在原則中詳述彈出式、 底下 * * 監督信箱 * *、 複製的位址。</span><span class="sxs-lookup"><span data-stu-id="500bc-116">In the policy details flyout, under ** Supervision mailbox **, copy the address.</span></span> 
    
    !['監督信箱'] 區段中的監督原則的詳細資訊彈出式顯示醒目提示的監督信箱地址](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
## <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a><span data-ttu-id="500bc-118">步驟 2： 設定 Outlook 桌面 access 監督信箱</span><span class="sxs-lookup"><span data-stu-id="500bc-118">Step 2: Configure the supervision mailbox for Outlook desktop access</span></span>

<span data-ttu-id="500bc-119">接下來，檢閱者需要讓他們可以將 Outlook 連接到監督信箱執行幾個的 Exchange Online PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="500bc-119">Next, reviewers will need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.</span></span>
  
1. <span data-ttu-id="500bc-p103">連線到 Exchange Online PowerShell。[如何執行這？](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="500bc-p103">Connect to Exchange Online PowerShell. [How do I do this?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span></span>
    
2. <span data-ttu-id="500bc-122">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="500bc-122">Run the following commands.</span></span>
    
  ```
  Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccessSet-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false
  ```

    <span data-ttu-id="500bc-123">其中*SupervisoryReview{GUID}@domain.onmicrosoft.com*是您在上述步驟 1 中複製的地址和*使用者*是檢閱者都要連線至下一個步驟中的監督信箱的名稱。</span><span class="sxs-lookup"><span data-stu-id="500bc-123">Where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will be connecting to the supervision mailbox in the next step.</span></span> 
    
3. <span data-ttu-id="500bc-124">等待至少一小時前將移至下的步驟 3。</span><span class="sxs-lookup"><span data-stu-id="500bc-124">Wait at least an hour before moving on to Step 3 below.</span></span>
    
## <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a><span data-ttu-id="500bc-125">步驟 3： 建立 Outlook 設定檔連線至監督信箱</span><span class="sxs-lookup"><span data-stu-id="500bc-125">Step 3: Create an Outlook profile to connect to the supervision mailbox</span></span>

<span data-ttu-id="500bc-126">最後一個步驟中，檢閱者必須建立 Outlook 設定檔連線至監督信箱。</span><span class="sxs-lookup"><span data-stu-id="500bc-126">For the final step, reviewers will need to create an Outlook profile to connect to the supervision mailbox.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="500bc-p104">若要建立新的 Outlook 設定檔，您將在 Windows 控制台中使用 [郵件設定。您需要以取得這些設定的路徑可能會取決於您正在使用的 Windows 作業系統 （Windows 7、 Windows 8 或 Windows 10） 及安裝的 Outlook 版本。</span><span class="sxs-lookup"><span data-stu-id="500bc-p104">To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel. The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using and which version of Outlook is installed.</span></span> 
  
1. <span data-ttu-id="500bc-129">開啟 [控制台] 中，並在視窗頂端的 [**搜尋**] 方塊中輸入**郵件**。</span><span class="sxs-lookup"><span data-stu-id="500bc-129">Open the Control Panel, and in the **Search** box at the top of the window, type **Mail**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="500bc-p105">不確定如何取得 Control panel？請參閱[所在控制台吗？](https://support.microsoft.com/help/13764/windows-where-is-control-panel)</span><span class="sxs-lookup"><span data-stu-id="500bc-p105">Not sure how to get to the Control Panel? See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel)</span></span>
  
2. <span data-ttu-id="500bc-132">開啟**郵件**應用程式。</span><span class="sxs-lookup"><span data-stu-id="500bc-132">Open the **Mail** app.</span></span> 
    
3. <span data-ttu-id="500bc-133">在 [**郵件設定-Outlook**中，按一下 [**顯示設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="500bc-133">In **Mail Setup - Outlook**, click **Show Profiles**.</span></span>
    
    !['郵件安裝-Outlook'' 顯示設定檔 」 按鈕醒目提示] 對話方塊](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. <span data-ttu-id="500bc-p106">在 [**郵件**] 按一下 [**新增**]。然後，在**新的設定檔**、 輸入的名稱 （例如**監督**） 監督信箱。</span><span class="sxs-lookup"><span data-stu-id="500bc-p106">In **Mail**, click **Add**. Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).</span></span>
    
    ![在 [設定檔名稱] 方塊中顯示名稱 '監督' ' 新設定檔 」 對話方塊](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. <span data-ttu-id="500bc-138">在 [**連線至 Office 365 的 Outlook**中，按一下 [**連接到不同的帳戶**。</span><span class="sxs-lookup"><span data-stu-id="500bc-138">In **Connect Outlook to Office 365**, click **Connect to a different account**.</span></span>
    
    ![' 連線至 Office 365 Outlook' 郵件與反白顯示 「 連接至不同的帳戶' 連結](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. <span data-ttu-id="500bc-140">在 [**自動帳戶設定**] 選擇**手動安裝程式] 或 [其他伺服器類型**，並再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="500bc-140">In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="500bc-p107">在 [**選擇您的帳戶類型**，選擇 [ **Office 365**]。然後，在 [**電子郵件地址**] 方塊中輸入您在先前複製監督信箱的地址。</span><span class="sxs-lookup"><span data-stu-id="500bc-p107">In **Choose Your Account Type**, choose **Office 365**. Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously.</span></span> 
    
    ![Outlook 顯示醒目提示 [' 電子郵件地址 」] 方塊中的 [新增帳戶] 對話方塊的 「 選擇您的帳戶類型 」 頁面。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. <span data-ttu-id="500bc-144">出現提示時，輸入您的 Office 365 認證。</span><span class="sxs-lookup"><span data-stu-id="500bc-144">When prompted, enter your Office 365 credentials.</span></span>
    
9. <span data-ttu-id="500bc-145">如果成功，您會看見**監督-\<原則名稱\>** 在 Outlook 中的資料夾清單檢視中列出的資料夾。</span><span class="sxs-lookup"><span data-stu-id="500bc-145">If successful, you'll see the **Supervision - \<policy name\>** folder listed in the Folder List view in Outlook.</span></span> 
    

