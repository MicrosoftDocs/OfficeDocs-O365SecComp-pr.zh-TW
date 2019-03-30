---
title: 開啟或關閉 Office 365 稽核記錄搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: 您可以開啟安全性 & 合規性中心中的稽核記錄搜尋功能。 如果您變更您記住，您可以啟動隨時如果 off。 關閉稽核記錄搜尋時，系統管理員無法在組織中搜尋使用者和系統管理員活動的 Office 365 稽核記錄檔。
ms.openlocfilehash: a77114ac9b5de18d4718a543983f7a1f94ebc41f
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000926"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="cc673-105">開啟或關閉 Office 365 稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="cc673-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="cc673-106">您 （或另一個系統管理員） 必須開啟稽核記錄，才能開始搜尋 Office 365 稽核記錄檔。</span><span class="sxs-lookup"><span data-stu-id="cc673-106">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log.</span></span> <span data-ttu-id="cc673-107">安全性 & 合規性中心中的稽核記錄搜尋開啟時，從您的組織的使用者和系統管理員活動是記錄在稽核記錄檔，並保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="cc673-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days.</span></span> <span data-ttu-id="cc673-108">不過，您的組織可能不希望筆記錄，並保留稽核記錄資料。</span><span class="sxs-lookup"><span data-stu-id="cc673-108">However, your organization might not want to record and retain audit log data.</span></span> <span data-ttu-id="cc673-109">或者，您可能要存取您的稽核資料使用的協力廠商安全性資訊和事件管理 (SIEM) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cc673-109">Or you might be using a third-party security information and event management (SIEM) application to access your auditing data.</span></span> <span data-ttu-id="cc673-110">在這些情況下，全域系統管理員可以關閉在 Office 365 中的稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="cc673-110">In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="cc673-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="cc673-111">Before you begin</span></span>

- <span data-ttu-id="cc673-112">您必須被指派 「 稽核記錄 」 角色在 Exchange Online 在 Office 365 組織中開啟或關閉開啟稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="cc673-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization.</span></span> <span data-ttu-id="cc673-113">根據預設，此角色被指派給在 Exchange 系統管理中心中的**權限**] 頁面上相符性管理] 和 [組織管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="cc673-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="cc673-114">在 Office 365 中的全域系統管理員是 「 組織管理 」 角色群組的成員在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="cc673-114">Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="cc673-115">使用者必須被指派權限在 Exchange Online 若要開啟或關閉稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="cc673-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="cc673-116">如果您將使用者指派 「 稽核記錄 」 角色中安全性 & 合規性中心的**權限**] 頁面上，他們將無法開啟或關閉稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="cc673-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="cc673-117">這是因為基礎指令程式是 Exchange Online cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cc673-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="cc673-118">如果您關閉 Office 365 中的稽核記錄搜尋時，您仍然可以使用 Office 365 管理活動 API 來存取組織的稽核資料。</span><span class="sxs-lookup"><span data-stu-id="cc673-118">If you turn off audit log search in Office 365, you can still use the Office 365 Management Activity API to access auditing data for your organization.</span></span> <span data-ttu-id="cc673-119">遵循本文中的稽核記錄搜尋關閉表示當您搜尋使用安全性 & 合規性中心的稽核記錄檔或 Exchange Online 中執行**Search-unifiedauditlog**指令程式，將會傳回任何結果PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cc673-119">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="cc673-120">不過，如果您已獲授權存取貴組織的稽核資料透過 Office 365 管理活動 API 的任何應用程式，這些應用程式將繼續運作。</span><span class="sxs-lookup"><span data-stu-id="cc673-120">However, if you've authorized any application to access your organization's auditing data via the Office 365 Management Activity API , those applications will continue to work.</span></span> 
    
- <span data-ttu-id="cc673-121">如需搜尋 Office 365 稽核記錄的逐步指示，請參閱 <<c0>的搜尋稽核記錄中的安全性 &amp; 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="cc673-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="cc673-122">開啟稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="cc673-122">Turn on audit log search</span></span>

<span data-ttu-id="cc673-123">您可以使用安全性 & 合規性管理中心或 PowerShell 將開啟 Office 365 中的稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="cc673-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Office 365.</span></span> <span data-ttu-id="cc673-124">它可能需要數小時之後您開啟稽核記錄搜尋之前搜尋稽核記錄時，可以傳回的結果。</span><span class="sxs-lookup"><span data-stu-id="cc673-124">It might take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="cc673-125">您必須被指派 「 稽核記錄 」 角色在 Exchange Online 開啟稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="cc673-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="cc673-126">使用安全性 & 合規性中心來開啟稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="cc673-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="cc673-127">在 [安全性 & 合規性中心，移至**搜尋** \> **稽核記錄搜尋**。</span><span class="sxs-lookup"><span data-stu-id="cc673-127">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
2. <span data-ttu-id="cc673-128">按一下 [**開始錄製使用者和系統管理員活動**]。</span><span class="sxs-lookup"><span data-stu-id="cc673-128">Click **Start recording user and admin activities**.</span></span>
    
    ![按一下 [開始錄製使用者和系統管理員活動來開啟稽核](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="cc673-130">指出使用者和組織中的系統管理員活動，將會錄製到 Office 365 稽核記錄，並可供檢視報表中會顯示對話方塊。</span><span class="sxs-lookup"><span data-stu-id="cc673-130">A dialog box is displayed saying that user and admin activity in your organization will be recorded to the Office 365 audit log and available to view in a report.</span></span> 
    
3. <span data-ttu-id="cc673-131">按一下 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc673-131">Click **Turn on**.</span></span>
    
    <span data-ttu-id="cc673-132">會顯示訊息，指出準備稽核記錄檔以及您可以在幾個小時後準備已完成執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="cc673-132">A message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="cc673-133">使用 PowerShell 來開啟稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="cc673-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="cc673-134">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc673-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="cc673-135">執行下列 PowerShell 命令，以開啟 [Office 365 中的稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="cc673-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="cc673-136">會顯示一則訊息，指出它可能需要 60 分鐘的時間，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="cc673-136">A message is displayed saying that it might take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="cc673-137">關閉稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="cc673-137">Turn off audit log search</span></span>

<span data-ttu-id="cc673-138">您必須使用遠端 PowerShell 連線至 Exchange Online 組織來關閉稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="cc673-138">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="cc673-139">類似於開啟稽核記錄搜尋，您必須被指派 「 稽核記錄 」 角色在 Exchange Online 關閉稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="cc673-139">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="cc673-140">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc673-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="cc673-141">執行下列 PowerShell 命令，以關閉 [Office 365 中的稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="cc673-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="cc673-142">在一段時間之後, 確認稽核記錄搜尋已關閉 (disabled)。</span><span class="sxs-lookup"><span data-stu-id="cc673-142">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="cc673-143">方法有兩種：</span><span class="sxs-lookup"><span data-stu-id="cc673-143">There are two ways to do this:</span></span>
    
    - <span data-ttu-id="cc673-144">在 PowerShell 中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="cc673-144">In PowerShell, run the following command:</span></span>

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        <span data-ttu-id="cc673-145">值`False` _UnifiedAuditLogIngestionEnabled_屬性表示該稽核記錄搜尋已關閉。</span><span class="sxs-lookup"><span data-stu-id="cc673-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="cc673-146">在 [安全性 & 合規性中心，移至**搜尋** \> **稽核記錄搜尋**]，然後按一下 [**搜尋**。</span><span class="sxs-lookup"><span data-stu-id="cc673-146">In the Security & Compliance Center, go to **Search** \> **Audit log search**, and then click **Search**.</span></span>
    
      <span data-ttu-id="cc673-147">會顯示一則訊息，指出尚未開啟稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="cc673-147">A message is displayed saying that audit log search isn't turned on.</span></span> 
    
      ![如果稽核已關閉，會顯示一則訊息](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
