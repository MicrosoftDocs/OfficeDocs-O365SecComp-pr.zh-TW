---
title: 開啟 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
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
description: 了解如何開啟 ATP SharePoint、 OneDrive 及 microsoft Teams，包括如何設定警示，偵測到的檔案。
ms.openlocfilehash: 30eb28bfc5156664656ca1c200f9e999661b3b0c
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2019
ms.locfileid: "30242145"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7e299-103">開啟 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e299-103">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="7e299-104">[適用於 SharePoint、 OneDrive 及 Microsoft Teams 的 office 365 ATP](atp-for-spo-odb-and-teams.md)會保護您的組織不小心共用惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="7e299-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="7e299-105">偵測到惡意檔案時，該檔案被封鎖，讓任何人可以開啟、 複製、 移動或共用直到由組織的安全性小組會採取進一步的動作。</span><span class="sxs-lookup"><span data-stu-id="7e299-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="7e299-106">閱讀本篇文章以開啟 ATP SharePoint、 OneDrive 及 microsoft Teams，設定提醒通知關於偵測到的檔案，並採取接下來的步驟。</span><span class="sxs-lookup"><span data-stu-id="7e299-106">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span> 
  
<span data-ttu-id="7e299-107">若要定義 （或編輯） ATP 原則，您必須獲指派適當的角色。</span><span class="sxs-lookup"><span data-stu-id="7e299-107">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="7e299-108">下表說明一些範例：</span><span class="sxs-lookup"><span data-stu-id="7e299-108">Some examples are described in the following table:</span></span>

|<span data-ttu-id="7e299-109">角色</span><span class="sxs-lookup"><span data-stu-id="7e299-109">Role</span></span>  |<span data-ttu-id="7e299-110">位置/方式指派</span><span class="sxs-lookup"><span data-stu-id="7e299-110">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="7e299-111">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="7e299-111">Office 365 Global Administrator</span></span> |<span data-ttu-id="7e299-112">若要購買 Office 365 註冊的人員是預設的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="7e299-112">The person who signs up to buy Office 365 is a global admin by default.</span></span> <span data-ttu-id="7e299-113">（請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)，以了解更多）。</span><span class="sxs-lookup"><span data-stu-id="7e299-113">(See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="7e299-114">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="7e299-114">Security Administrator</span></span> |<span data-ttu-id="7e299-115">Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="7e299-115">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="7e299-116">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="7e299-116">Exchange Online Organization Management</span></span> |<span data-ttu-id="7e299-117">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="7e299-117">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="7e299-118">或</span><span class="sxs-lookup"><span data-stu-id="7e299-118">or</span></span> <br>  <span data-ttu-id="7e299-119">PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="7e299-119">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7e299-120">開啟適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="7e299-120">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="7e299-121">**開始此程序，請確定稽核記錄已經開啟的 Office 365 環境**。</span><span class="sxs-lookup"><span data-stu-id="7e299-121">**Before you begin this procedure, make sure that audit logging is already turned on for your Office 365 environment**.</span></span> <span data-ttu-id="7e299-122">這通常是由已指派 Exchange Online 的稽核記錄 」 角色的人員。</span><span class="sxs-lookup"><span data-stu-id="7e299-122">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="7e299-123">如需詳細資訊，請參閱[開啟 Office 365 稽核記錄搜尋的開啟或關閉](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="7e299-123">For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>
  
1. <span data-ttu-id="7e299-124">移至 [ [https://protection.office.com](https://protection.office.com)，並以您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="7e299-124">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="7e299-125">在 Office 365 安全性&amp;合規性中心，在左側的導覽窗格中，**威脅管理**] 下選擇 [**原則**] \> **安全附件**。</span><span class="sxs-lookup"><span data-stu-id="7e299-125">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span> <br/><span data-ttu-id="7e299-126">![安全性&amp;合規性中心，選擇 [威脅管理\>原則](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span><span class="sxs-lookup"><span data-stu-id="7e299-126">![In the Security &amp; Compliance Center, choose Threat management \> Policy](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span></span>
  
3. <span data-ttu-id="7e299-127">選取 [**開啟 ATP SharePoint、 OneDrive 及 Microsoft Teams**。</span><span class="sxs-lookup"><span data-stu-id="7e299-127">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span><br/><span data-ttu-id="7e299-128">![開啟進階的威脅防護的 SharePoint Online、 商務用 OneDrive 和 Microsoft Teams](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span><span class="sxs-lookup"><span data-stu-id="7e299-128">![Turn on Advanced Threat Protection for SharePoint Online, OneDrive for Business, and Microsoft Teams](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span></span>
  
4. <span data-ttu-id="7e299-129">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7e299-129">Click **Save**.</span></span>
    
5. <span data-ttu-id="7e299-130">檢閱 （並適當地編輯） 貴組織的[安全附件原則](set-up-atp-safe-attachments-policies.md)和[安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7e299-130">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>
    
6. <span data-ttu-id="7e299-131">（建議使用）以全域管理員或 SharePoint Online 系統管理員，執行**[Set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** 指令程式搭配**DisallowInfectedFileDownload**參數設為*true*。</span><span class="sxs-lookup"><span data-stu-id="7e299-131">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true*.</span></span> <br/>
      - <span data-ttu-id="7e299-132">設定的參數 *，則為 true*的區塊 （除了刪除） 的所有動作偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="7e299-132">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="7e299-133">人員無法開啟、 移動、 複製或共用偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="7e299-133">People cannot open, move, copy, or share detected files.</span></span>
      - <span data-ttu-id="7e299-134">此參數設*為 false*會封鎖刪除及下載以外的所有動作。</span><span class="sxs-lookup"><span data-stu-id="7e299-134">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="7e299-135">人員可以選擇接受的風險，並下載偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="7e299-135">People can choose to accept the risk and download a detected file.</span></span>  
   
7. <span data-ttu-id="7e299-136">允許 30 分鐘，進行您的變更，即會散佈至所有 Office 365 資料中心。</span><span class="sxs-lookup"><span data-stu-id="7e299-136">Allow up to 30 minutes for your changes to spread to all Office 365 datacenters.</span></span>
    
8. <span data-ttu-id="7e299-137">（建議使用）請繼續進行設定提醒偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="7e299-137">(Recommended) Proceed to set up alerts for detected files.</span></span>
    
<span data-ttu-id="7e299-138">若要深入了解使用 PowerShell 與 Office 365，請參閱[使用 PowerShell 管理 Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7e299-138">To learn more about using PowerShell with Office 365, see [Manage Office 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span> 

<span data-ttu-id="7e299-139">若要深入了解使用者經驗時已偵測到視為惡意的檔案，請參閱[在 SharePoint Online、 OneDrive 或 Microsoft Teams 中找到惡意檔案時，該怎麼辦](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。</span><span class="sxs-lookup"><span data-stu-id="7e299-139">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span> 
  
## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="7e299-140">偵測到檔案的提醒設定</span><span class="sxs-lookup"><span data-stu-id="7e299-140">Set up alerts for detected files</span></span>

<span data-ttu-id="7e299-141">若要收到通知，當中 SharePoint Online、 OneDrive for Business 或 Microsoft Teams 的檔案已經被識別為惡意，您可以設定警示。</span><span class="sxs-lookup"><span data-stu-id="7e299-141">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>
  
1. <span data-ttu-id="7e299-142">在[Office 365 安全性&amp;合規性中心](https://protection.office.com)，選擇 [**提醒** \> **管理警示**。</span><span class="sxs-lookup"><span data-stu-id="7e299-142">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>
    
2. <span data-ttu-id="7e299-143">選擇 [**新的警示原則**。</span><span class="sxs-lookup"><span data-stu-id="7e299-143">Choose **New alert policy**.</span></span>
    
3. <span data-ttu-id="7e299-144">指定提醒的名稱。</span><span class="sxs-lookup"><span data-stu-id="7e299-144">Specify a name for the alert.</span></span> <span data-ttu-id="7e299-145">例如，您無法在文件庫中輸入惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="7e299-145">For example, you could type Malicious Files in Libraries.</span></span>
    
4. <span data-ttu-id="7e299-146">輸入警示的描述。</span><span class="sxs-lookup"><span data-stu-id="7e299-146">Type a description for the alert.</span></span> <span data-ttu-id="7e299-147">例如，您可以輸入通知系統管理員在 SharePoint Online、 OneDrive 或 Microsoft Teams 中偵測到的惡意檔案時。</span><span class="sxs-lookup"><span data-stu-id="7e299-147">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
    
5. <span data-ttu-id="7e299-148">在 [**傳送此提醒時...** ] 區段中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7e299-148">In the **Send this alert when...** section, do the following:</span></span> 
    
    <span data-ttu-id="7e299-149">a.</span><span class="sxs-lookup"><span data-stu-id="7e299-149">a.</span></span> <span data-ttu-id="7e299-150">在 [**活動**] 清單中，選擇 [**在檔案中的偵測到惡意程式碼**]。</span><span class="sxs-lookup"><span data-stu-id="7e299-150">In the **Activities** list, choose **Detected malware in file**.</span></span>
    
    <span data-ttu-id="7e299-151">b.</span><span class="sxs-lookup"><span data-stu-id="7e299-151">b.</span></span> <span data-ttu-id="7e299-152">將 [**使用者**] 欄位保留空白。</span><span class="sxs-lookup"><span data-stu-id="7e299-152">Leave the **Users** field empty.</span></span> 
    
6. <span data-ttu-id="7e299-153">在 **...傳送到此提醒**] 區段中，選取一或多個全域系統管理員、 安全性系統管理員或安全性讀者應該會偵測到惡意檔案時收到通知。</span><span class="sxs-lookup"><span data-stu-id="7e299-153">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span> 
    
7. <span data-ttu-id="7e299-154">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7e299-154">Click **Save**.</span></span>
    
<span data-ttu-id="7e299-155">若要深入了解提醒，請參閱[建立 Office 365 安全性中的活動警訊&amp;合規性中心](create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="7e299-155">To learn more about alerts, see [Create activity alerts in the Office 365 Security &amp; Compliance Center](create-activity-alerts.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="7e299-156">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7e299-156">Next steps</span></span>

1. [<span data-ttu-id="7e299-157">檢視 SharePoint、 OneDrive 或 Microsoft Teams 中偵測到的惡意檔案的相關資訊</span><span class="sxs-lookup"><span data-stu-id="7e299-157">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [<span data-ttu-id="7e299-158">在 Office 365 中系統管理員身分管理被隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="7e299-158">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
    

  

