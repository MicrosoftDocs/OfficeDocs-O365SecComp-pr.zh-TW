---
title: 檢視 SharePoint、 OneDrive 或 Microsoft 小組中偵測到惡意檔案的資訊
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 5/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
description: 了解移至檢視 SharePoint、 OneDrive 或小組中偵測到惡意檔案的相關資訊的位置以及如何將這些檔案採取動作。
ms.openlocfilehash: e9a68c1cee1f2f3fb7fba148365449f0136fe637
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526736"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="4af9b-103">檢視 SharePoint、 OneDrive 或 Microsoft 小組中偵測到惡意檔案的資訊</span><span class="sxs-lookup"><span data-stu-id="4af9b-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="4af9b-p101">[Office 365 ATP for SharePoint、 OneDrive 及 Microsoft 小組](atp-for-spo-odb-and-teams.md)提供貴組織保護文件庫和小組網站中的惡意檔案。當偵測到惡意檔案時，該檔案會封鎖，讓任何人可以開啟、 複製、 移動或共用直到組織的安全性小組所採取其他動作。閱讀本文以了解如何檢視偵測到的檔案的相關資訊以及要執行的動作。</span><span class="sxs-lookup"><span data-stu-id="4af9b-p101">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites. When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team. Read this article to learn how to view information about detected files and what actions to take.</span></span> 
  
> [!TIP]
> <span data-ttu-id="4af9b-107">若要執行本文所述的工作，您必須具備必要[權限指派在 Office 365 安全性&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="4af9b-107">In order to perform the tasks described in this article, you must have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="4af9b-108">檢視報告與偵測到的檔案的相關資訊</span><span class="sxs-lookup"><span data-stu-id="4af9b-108">View reports with information about detected files</span></span>

<span data-ttu-id="4af9b-109">若要檢視狀態和已偵測到的 Office 365 ATP 的檔案的詳細的資訊，您可以使用威脅保護狀態報表。</span><span class="sxs-lookup"><span data-stu-id="4af9b-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat protection status report.</span></span>
  
1. <span data-ttu-id="4af9b-110">Office 365 安全性&amp;規範中心選擇**報告** \> **儀表板** \> **威脅保護狀態**。</span><span class="sxs-lookup"><span data-stu-id="4af9b-110">In the Office 365 Security &amp; Compliance Center, choose **Reports** \> **Dashboard** \> **Threat protection status**.</span></span>
    
2. <span data-ttu-id="4af9b-111">在報表的左上角中選擇 [**檢視詳細資料表格**。</span><span class="sxs-lookup"><span data-stu-id="4af9b-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="4af9b-112">檢視報表所偵測到的檔案清單。</span><span class="sxs-lookup"><span data-stu-id="4af9b-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="4af9b-113">若要檢視的詳細的資訊，包括採取的動作、 檔案名稱、 檔案路徑及其他清單中選取項目。</span><span class="sxs-lookup"><span data-stu-id="4af9b-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="4af9b-114">選擇 [**進階分析**] 索引標籤來檢視資訊，例如觀察到的行為與分析的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4af9b-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
    
> [!TIP]
> <span data-ttu-id="4af9b-115">若要深入了解可用的報告，請參閱[Office 365 進階威脅保護的檢視報告](view-reports-for-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="4af9b-115">To learn more about available reports, see [View reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md).</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="4af9b-116">檢視及隔離區中檔案採取動作</span><span class="sxs-lookup"><span data-stu-id="4af9b-116">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="4af9b-117">Office 365 安全性&amp;規範中心選擇**Threat management** \> **檢閱** \> **隔離**。</span><span class="sxs-lookup"><span data-stu-id="4af9b-117">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span>
    
2. <span data-ttu-id="4af9b-118">在左上角，變更篩選從**電子郵件**至**內容**。</span><span class="sxs-lookup"><span data-stu-id="4af9b-118">In the upper left corner, change the filter from **Email** to **Content**.</span></span>
    
3. <span data-ttu-id="4af9b-119">若要檢視的詳細的資訊，包括檔案的 URL 清單中選取項目。</span><span class="sxs-lookup"><span data-stu-id="4af9b-119">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="4af9b-120">選擇可用的動作。</span><span class="sxs-lookup"><span data-stu-id="4af9b-120">Choose an available action.</span></span>
    
  - <span data-ttu-id="4af9b-121">選擇 [**版本&amp;報表**解除封鎖的檔案。</span><span class="sxs-lookup"><span data-stu-id="4af9b-121">Choose **Release &amp; report** to unblock the file.</span></span> 
    
    <span data-ttu-id="4af9b-122">選取 [**傳送給 Microsoft 的報表**將向 Microsoft 報告為誤判的檔案。</span><span class="sxs-lookup"><span data-stu-id="4af9b-122">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 
    
  - <span data-ttu-id="4af9b-123">選擇 [**檔案下載**檔案進一步調查。</span><span class="sxs-lookup"><span data-stu-id="4af9b-123">Choose **Download file** to investigate the file further.</span></span> 
    
  - <span data-ttu-id="4af9b-p102">選擇 [**刪除**] 以從隔離的項目清單移除檔案。如果您選擇這個選項，您必須也檔案從刪除其各自的文件庫的 SharePoint Online、 OneDrive for Business 或 Microsoft 小組。此選項不會解除封鎖來自正在檔案開啟或共用。</span><span class="sxs-lookup"><span data-stu-id="4af9b-p102">Choose **Delete** to remove the file from the list of quarantined items. If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams. This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="4af9b-127">選擇 [**關閉**] 以關閉 [選取的項目詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4af9b-127">Choose **Close** to close the details for a selected item.</span></span> 
    
> [!TIP]
> <span data-ttu-id="4af9b-128">若要深入了解管理隔離的檔案，請參閱[管理隔離郵件和 Office 365 系統管理員身分的檔案](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="4af9b-128">To learn more about managing quarantined files, see [Manage quarantined messages and files as an administrator in Office 365](manage-quarantined-messages-and-files.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="4af9b-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="4af9b-129">Related topics</span></span>

[<span data-ttu-id="4af9b-130">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="4af9b-130">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="4af9b-131">Office 365 進階威脅保護的檢視報告</span><span class="sxs-lookup"><span data-stu-id="4af9b-131">View the reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  
[<span data-ttu-id="4af9b-132">Office 365 安全性權限&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="4af9b-132">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

