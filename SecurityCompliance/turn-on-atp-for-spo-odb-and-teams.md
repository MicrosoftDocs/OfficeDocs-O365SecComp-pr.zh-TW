---
title: 開啟 Office 365 ATP for SharePoint、OneDrive 及 Microsoft 小組
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
description: 瞭解如何為 SharePoint、OneDrive 及小組開啟 ATP, 包括如何設定偵測到之檔案的警示。
ms.openlocfilehash: f3be5b3cf73a04de10185428b84b5862906c3db7
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652666"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7fa6a-103">開啟 Office 365 ATP for SharePoint、OneDrive 及 Microsoft 小組</span><span class="sxs-lookup"><span data-stu-id="7fa6a-103">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7fa6a-104">本文適用于擁有[Office 365 高級威脅防護](office-365-atp.md)的商務客戶。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="7fa6a-105">如果您是尋找 Outlook 中安全連結相關資訊的家庭使用者, 請參閱[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="7fa6a-106">[Office 365 ATP For SharePoint、OneDrive 及 Microsoft 團隊](atp-for-spo-odb-and-teams.md)可防止您的組織不慎共用惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-106">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="7fa6a-107">偵測到惡意檔案時, 該檔案會遭到封鎖, 讓任何人都無法開啟、複製、移動或共用該檔案, 直到組織的安全小組採取進一步的動作為止。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-107">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="7fa6a-108">請閱讀本文以開啟 ATP for SharePoint、OneDrive 及小組、設定通知, 以獲得偵測到的檔案通知, 並採取下一步。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-108">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span> 
  
<span data-ttu-id="7fa6a-109">若要定義 (或編輯) ATP 原則, 您必須獲指派適當的角色。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-109">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="7fa6a-110">下表說明一些範例:</span><span class="sxs-lookup"><span data-stu-id="7fa6a-110">Some examples are described in the following table:</span></span>

|<span data-ttu-id="7fa6a-111">角色</span><span class="sxs-lookup"><span data-stu-id="7fa6a-111">Role</span></span>  |<span data-ttu-id="7fa6a-112">指派的位置/方式</span><span class="sxs-lookup"><span data-stu-id="7fa6a-112">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="7fa6a-113">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="7fa6a-113">Office 365 Global Administrator</span></span> |<span data-ttu-id="7fa6a-114">註冊購買 Office 365 的人員預設為全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-114">The person who signs up to buy Office 365 is a global admin by default.</span></span> <span data-ttu-id="7fa6a-115">(請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以深入瞭解。)</span><span class="sxs-lookup"><span data-stu-id="7fa6a-115">(See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="7fa6a-116">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="7fa6a-116">Security Administrator</span></span> |<span data-ttu-id="7fa6a-117">Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="7fa6a-117">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="7fa6a-118">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="7fa6a-118">Exchange Online Organization Management</span></span> |<span data-ttu-id="7fa6a-119">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="7fa6a-119">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="7fa6a-120">或</span><span class="sxs-lookup"><span data-stu-id="7fa6a-120">or</span></span> <br>  <span data-ttu-id="7fa6a-121">PowerShell Cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="7fa6a-121">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7fa6a-122">開啟適用於 SharePoint、OneDrive 和 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="7fa6a-122">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="7fa6a-123">**開始此程式之前, 請確定已開啟 Office 365 環境的審核記錄**功能。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-123">**Before you begin this procedure, make sure that audit logging is already turned on for your Office 365 environment**.</span></span> <span data-ttu-id="7fa6a-124">這通常是由已在 Exchange Online 中指派「Audit 記錄」角色的人員所完成。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-124">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="7fa6a-125">如需詳細資訊, 請參閱[開啟或關閉 Office 365 audit log search](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-125">For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>
  
1. <span data-ttu-id="7fa6a-126">移至[https://protection.office.com](https://protection.office.com), 然後使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-126">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="7fa6a-127">在 [Office 365 安全性&amp;規範中心] 的左功能窗格中, 選擇 [**威脅管理**] 下的 [**原則** \> **安全附件**]。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-127">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span> <br/><span data-ttu-id="7fa6a-128">![在安全性&amp;與合規性中心, 選擇 [ \>威脅管理原則]](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span><span class="sxs-lookup"><span data-stu-id="7fa6a-128">![In the Security &amp; Compliance Center, choose Threat management \> Policy](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span></span>
  
3. <span data-ttu-id="7fa6a-129">選取 [**開啟適用于 SharePoint、OneDrive 及 Microsoft 團隊的 ATP**]。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-129">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span><br/><span data-ttu-id="7fa6a-130">![開啟適用于 SharePoint Online、商務用 OneDrive 和 Microsoft 小組的高級威脅防護](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span><span class="sxs-lookup"><span data-stu-id="7fa6a-130">![Turn on Advanced Threat Protection for SharePoint Online, OneDrive for Business, and Microsoft Teams](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span></span>
  
4. <span data-ttu-id="7fa6a-131">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-131">Click **Save**.</span></span>
    
5. <span data-ttu-id="7fa6a-132">請查看 (並視需要編輯) 您組織的[安全附件原則](set-up-atp-safe-attachments-policies.md)和[安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-132">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>
    
6. <span data-ttu-id="7fa6a-133">採取以全域管理員或 SharePoint Online 系統管理員身分執行 Set-spotenant 指令**[程式](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)**, 並將**DisallowInfectedFileDownload**參數設為*true*。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-133">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true*.</span></span> <br/>
      - <span data-ttu-id="7fa6a-134">將參數設定為*true*會封鎖偵測到之檔案的所有動作 (刪除除外)。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-134">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="7fa6a-135">使用者無法開啟、移動、複製或共用偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-135">People cannot open, move, copy, or share detected files.</span></span>
      - <span data-ttu-id="7fa6a-136">將參數設定為*false*會封鎖除了 Delete 和下載以外的所有動作。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-136">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="7fa6a-137">使用者可以選擇接受風險並下載偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-137">People can choose to accept the risk and download a detected file.</span></span>  
   
7. <span data-ttu-id="7fa6a-138">允許最多30分鐘, 以將您的變更傳播至所有 Office 365 資料中心。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-138">Allow up to 30 minutes for your changes to spread to all Office 365 datacenters.</span></span>
    
8. <span data-ttu-id="7fa6a-139">採取繼續設定偵測到之檔案的警示。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-139">(Recommended) Proceed to set up alerts for detected files.</span></span>
    
<span data-ttu-id="7fa6a-140">若要深入瞭解如何搭配使用 PowerShell 與 Office 365, 請參閱使用[Powershell 管理 Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-140">To learn more about using PowerShell with Office 365, see [Manage Office 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span> 

<span data-ttu-id="7fa6a-141">若要深入瞭解在檔案被偵測到有惡意時的使用者經驗, 請參閱在[SharePoint Online、OneDrive 或 Microsoft 團隊中找到惡意檔案時, 要採取的](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)動作。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-141">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span> 
  
## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="7fa6a-142">設定偵測到檔案的警示</span><span class="sxs-lookup"><span data-stu-id="7fa6a-142">Set up alerts for detected files</span></span>

<span data-ttu-id="7fa6a-143">若要在 SharePoint Online、商務用 OneDrive 或 Microsoft 團隊中的檔案被識別為惡意時收到通知, 您可以設定警示。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-143">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>
  
1. <span data-ttu-id="7fa6a-144">在 [ [Office 365 安全性&amp;與規範中心](https://protection.office.com)] 中, 選擇 [**警示** \> ] [**管理提醒**]。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-144">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>
    
2. <span data-ttu-id="7fa6a-145">選擇 [**新增警示原則**]。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-145">Choose **New alert policy**.</span></span>
    
3. <span data-ttu-id="7fa6a-146">指定警示的名稱。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-146">Specify a name for the alert.</span></span> <span data-ttu-id="7fa6a-147">例如, 您可以在文件庫中輸入惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-147">For example, you could type Malicious Files in Libraries.</span></span>
    
4. <span data-ttu-id="7fa6a-148">輸入警示的描述。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-148">Type a description for the alert.</span></span> <span data-ttu-id="7fa6a-149">例如, 您可以在 SharePoint Online、OneDrive 或 Microsoft 團隊中偵測到惡意檔案時, 輸入通知系統管理員。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-149">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
    
5. <span data-ttu-id="7fa6a-150">在 [**傳送此提醒的時間**...] 區段中, 執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="7fa6a-150">In the **Send this alert when...** section, do the following:</span></span> 
    
    <span data-ttu-id="7fa6a-151">a.</span><span class="sxs-lookup"><span data-stu-id="7fa6a-151">a.</span></span> <span data-ttu-id="7fa6a-152">在 [**活動**] 清單中, 選擇 [檔案**中偵測到惡意**代碼]。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-152">In the **Activities** list, choose **Detected malware in file**.</span></span>
    
    <span data-ttu-id="7fa6a-153">b.</span><span class="sxs-lookup"><span data-stu-id="7fa6a-153">b.</span></span> <span data-ttu-id="7fa6a-154">將 [**使用者**] 欄位保留空白。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-154">Leave the **Users** field empty.</span></span> 
    
6. <span data-ttu-id="7fa6a-155">在 [**傳送此提醒 ...** ] 區段中, 選取一或多個全域系統管理員、安全性系統管理員, 或在偵測到惡意檔案時會收到通知的安全性讀取者。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-155">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span> 
    
7. <span data-ttu-id="7fa6a-156">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-156">Click **Save**.</span></span>
    
<span data-ttu-id="7fa6a-157">若要深入瞭解提醒, 請參閱[在 Office 365 安全性&amp;與合規性中心建立活動警示](create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="7fa6a-157">To learn more about alerts, see [Create activity alerts in the Office 365 Security &amp; Compliance Center](create-activity-alerts.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="7fa6a-158">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7fa6a-158">Next steps</span></span>

1. [<span data-ttu-id="7fa6a-159">查看 SharePoint、OneDrive 或 Microsoft 團隊中偵測到之惡意檔案的相關資訊</span><span class="sxs-lookup"><span data-stu-id="7fa6a-159">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [<span data-ttu-id="7fa6a-160">以 Office 365 的系統管理員身分管理隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="7fa6a-160">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
    

  

