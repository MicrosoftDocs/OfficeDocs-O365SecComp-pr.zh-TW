---
title: 在 Office 365 ATP 開啟 SharePoint、 OneDrive 及 Microsoft 小組
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
description: 了解如何開啟 ATP for SharePoint、 OneDrive 及小組，包括如何設定提醒的偵測到的檔案。
ms.openlocfilehash: e9df56da5d5f1a087d4e75e0122b51933ae7b315
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706447"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="25023-103">在 Office 365 ATP 開啟 SharePoint、 OneDrive 及 Microsoft 小組</span><span class="sxs-lookup"><span data-stu-id="25023-103">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="25023-p101">[Office 365 ATP for SharePoint、 OneDrive 及 Microsoft 小組](atp-for-spo-odb-and-teams.md)提供貴組織保護不慎共用惡意的檔案。當偵測到惡意檔案時，該檔案會封鎖，讓任何人可以開啟、 複製、 移動或共用直到組織的安全性小組所採取其他動作。閱讀本篇文章以開啟 ATP for SharePoint、 OneDrive 及小組設定提醒通知關於偵測到的檔案並執行您的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="25023-p101">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files. When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team. Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span> 
  
<span data-ttu-id="25023-107">若要執行本文所述的工作，您必須指派 Office 365 及安全性的必要權限&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="25023-107">In order to perform the tasks described in this article, you must have the necessary permissions assigned in Office 365 and in the Security &amp; Compliance Center.</span></span>
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="25023-108">開啟適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="25023-108">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

 <span data-ttu-id="25023-p102">**開始此程序，確定稽核記錄已經開啟 Office 365 環境**。這通常是由某人具有 「 稽核記錄 」 角色指派 Exchange Online。如需詳細資訊，請參閱[開啟 Office 365 稽核記錄搜尋開啟或關閉](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="25023-p102">**Before you begin this procedure, make sure that audit logging is already turned on for your Office 365 environment**. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>
  
1. <span data-ttu-id="25023-112">以全域管理員或安全性管理員中，移至[https://security.microsoft.com](https://security.microsoft.com)，並登入工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="25023-112">As a global administrator or security administrator, go to [https://security.microsoft.com](https://security.microsoft.com), and sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="25023-113">Office 365 安全性&amp;規範中心的左的功能窗格的 [**威脅管理**] 下選擇**原則** \> **安全的附件**。</span><span class="sxs-lookup"><span data-stu-id="25023-113">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span> <br/><span data-ttu-id="25023-114">![安全性&amp;規範中心選擇 Threat management\>原則](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span><span class="sxs-lookup"><span data-stu-id="25023-114">![In the Security &amp; Compliance Center, choose Threat management \> Policy](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span></span>
  
3. <span data-ttu-id="25023-115">選取 [**開啟 SharePoint、 OneDrive 及 Microsoft 小組 ATP**。</span><span class="sxs-lookup"><span data-stu-id="25023-115">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span><br/><span data-ttu-id="25023-116">![開啟進階的威脅 Protection for SharePoint Online、 OneDrive for Business 和 Microsoft 小組](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span><span class="sxs-lookup"><span data-stu-id="25023-116">![Turn on Advanced Threat Protection for SharePoint Online, OneDrive for Business, and Microsoft Teams](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span></span>
  
4. <span data-ttu-id="25023-117">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="25023-117">Click **Save**.</span></span>
    
5. <span data-ttu-id="25023-118">檢閱 （和視需要編輯） 您組織的[安全附件原則](set-up-atp-safe-attachments-policies.md)和[安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="25023-118">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>
    
6. <span data-ttu-id="25023-119">（建議）以全域管理員或 SharePoint Online 管理員、 執行**[Set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet 搭配**DisallowInfectedFileDownload**參數設為*true*。</span><span class="sxs-lookup"><span data-stu-id="25023-119">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true*.</span></span> <br/>
      - <span data-ttu-id="25023-p103">設定參數，*則為 true*組塊 （除了刪除） 的所有動作的偵測到的檔案。使用者無法開啟、 移動、 複製或共用偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="25023-p103">Setting the parameter to *true* blocks all actions (except Delete) for detected files. People cannot open, move, copy, or share detected files.</span></span>
      - <span data-ttu-id="25023-p104">將此參數設定為*false*會封鎖刪除和下載以外的所有動作。使用者可以選擇接受風險和下載偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="25023-p104">Setting the parameter to *false* blocks all actions except Delete and Download. People can choose to accept the risk and download a detected file.</span></span>  
   
7. <span data-ttu-id="25023-124">可讓您的變更傳播到所有 Office 365 資料中心的最多 30 分鐘。</span><span class="sxs-lookup"><span data-stu-id="25023-124">Allow up to 30 minutes for your changes to spread to all Office 365 datacenters.</span></span>
    
8. <span data-ttu-id="25023-125">（建議）請繼續進行設定提醒的偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="25023-125">(Recommended) Proceed to set up alerts for detected files.</span></span>
    
<span data-ttu-id="25023-126">若要深入了解 Office 365 搭配使用 PowerShell，請參閱[使用 PowerShell 管理 Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="25023-126">To learn more about using PowerShell with Office 365, see [Manage Office 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span> 

<span data-ttu-id="25023-127">若要深入了解使用者經驗時已偵測到為惡意的檔案，請參閱[如何在 SharePoint Online、 OneDrive 或 Microsoft 小組中找到惡意檔案時](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。</span><span class="sxs-lookup"><span data-stu-id="25023-127">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span> 
  
## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="25023-128">設定提醒的偵測到的檔案</span><span class="sxs-lookup"><span data-stu-id="25023-128">Set up alerts for detected files</span></span>

<span data-ttu-id="25023-129">若要在 SharePoint Online、 OneDrive for Business 或 Microsoft 小組檔案被識別為 [惡意時收到通知，您可以設定提醒。</span><span class="sxs-lookup"><span data-stu-id="25023-129">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>
  
1. <span data-ttu-id="25023-130">在[Office 365 安全性&amp;規範中心](https://security.microsoft.com)，選擇**警示** \> **管理提醒**。</span><span class="sxs-lookup"><span data-stu-id="25023-130">In the [Office 365 Security &amp; Compliance Center](https://security.microsoft.com), choose **Alerts** \> **Manage alerts**.</span></span>
    
2. <span data-ttu-id="25023-131">選擇 [**新增提醒的原則**。</span><span class="sxs-lookup"><span data-stu-id="25023-131">Choose **New alert policy**.</span></span>
    
3. <span data-ttu-id="25023-p105">指定提醒的名稱。例如，您無法輸入惡意檔案庫中。</span><span class="sxs-lookup"><span data-stu-id="25023-p105">Specify a name for the alert. For example, you could type Malicious Files in Libraries.</span></span>
    
4. <span data-ttu-id="25023-p106">輸入警示的描述。例如，您無法輸入告知 admins 時 SharePoint Online、 OneDrive 或 Microsoft 小組中偵測到惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="25023-p106">Type a description for the alert. For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
    
5. <span data-ttu-id="25023-136">**傳送此提醒時...** ] 區段中執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="25023-136">In the **Send this alert when...** section, do the following:</span></span> 
    
    <span data-ttu-id="25023-p107">a.[**活動**] 清單中選擇 [**檔案中的偵測到惡意程式碼**]。</span><span class="sxs-lookup"><span data-stu-id="25023-p107">a. In the **Activities** list, choose **Detected malware in file**.</span></span>
    
    <span data-ttu-id="25023-p108">b.保留**使用者**欄位空白。</span><span class="sxs-lookup"><span data-stu-id="25023-p108">b. Leave the **Users** field empty.</span></span> 
    
6. <span data-ttu-id="25023-141">**傳送到此警示...** ] 區段中選取一或多個全域管理員、 安全性管理員或安全性讀者應該會偵測到惡意檔案時收到通知。</span><span class="sxs-lookup"><span data-stu-id="25023-141">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span> 
    
7. <span data-ttu-id="25023-142">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="25023-142">Click **Save**.</span></span>
    
<span data-ttu-id="25023-143">若要深入了解提醒，請參閱[建立 Office 365 安全性活動提醒&amp;規範中心](create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="25023-143">To learn more about alerts, see [Create activity alerts in the Office 365 Security &amp; Compliance Center](create-activity-alerts.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="25023-144">後續步驟</span><span class="sxs-lookup"><span data-stu-id="25023-144">Next steps</span></span>

1. [<span data-ttu-id="25023-145">檢視 SharePoint、 OneDrive 或 Microsoft 小組中偵測到惡意檔案的資訊</span><span class="sxs-lookup"><span data-stu-id="25023-145">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [<span data-ttu-id="25023-146">在 Office 365 系統管理員身分管理隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="25023-146">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
    

  

