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
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: 您可以在 Office 365 安全性稽核記錄搜尋功能中開啟&amp;規範中心。如果您變更您注意，您可以開啟時關閉任何時候。關閉稽核記錄搜尋時，系統管理員無法在組織中搜尋使用者與系統管理活動的 Office 365 稽核記錄。
ms.openlocfilehash: f0532ae7ba205001d89164ac3f00822d14aa81cd
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218003"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="dc97f-105">開啟或關閉 Office 365 稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="dc97f-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="dc97f-p102">您 （或另一個系統管理員） 必須開啟稽核記錄才能開始搜尋的 Office 365 稽核記錄。當稽核記錄搜尋 Office 365 安全性&amp;規範中心已開啟、 從您的組織的使用者和系統活動會記錄在稽核記錄檔和保留期為 90 天。不過，您的組織可能不要記錄保留稽核記錄資料。或可能會使用第三方安全性資訊和事件管理 (SIEM) 應用程式存取稽核資料。在這些案例中的全域系統管理員可以關閉在 Office 365 中的稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="dc97f-p102">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log. When audit log search in the Office 365 Security &amp; Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days. However, your organization might not want to record and retain audit log data. Or you might be using a third-party security information and event management (SIEM) application to access your auditing data. In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="dc97f-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="dc97f-111">Before you begin</span></span>

- <span data-ttu-id="dc97f-p103">您必須指派稽核記錄 」 角色在 Exchange Online 在 Office 365 組織中開啟或關閉開啟稽核記錄搜尋。根據預設，此角色指派給 Exchange 系統管理中心的 [**權限**] 頁面上相符性管理] 和 [組織管理角色群組。Office 365 中的全域系統管理員為組織管理角色群組的成員在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="dc97f-p103">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization. By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="dc97f-p104">使用者必須獲得權限在 Exchange Online 以開啟或關閉的稽核記錄搜尋。如果您在 [安全性]**權限**] 頁面上的稽核記錄 」 角色指派使用者&amp;規範中心他們將無法開啟或關閉的稽核記錄搜尋。這是因為基礎指令程式是 Exchange Online 指令程式。</span><span class="sxs-lookup"><span data-stu-id="dc97f-p104">Users have to be assigned permissions in Exchange Online to turn audit log search on or off. If you assign users the Audit Logs role on the **Permissions** page in the Security &amp; Compliance Center, they won't be able to turn audit log search on or off. This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="dc97f-p105">如果您關閉 Office 365 中的稽核記錄搜尋時，您仍可用 Office 365 管理活動 API 來存取稽核資料的組織。關閉 [透過遵循本文中的 [稽核記錄搜尋表示當您使用安全性稽核記錄檔中搜尋將會傳回任何結果&amp;規範中心或 Exchange Online 中執行**搜尋 UnifiedAuditLog**指令程式時間PowerShell。不過，如果您已獲得授權存取您的組織稽核資料透過 Office 365 管理活動 API 任何應用程式，這些應用程式會繼續運作。</span><span class="sxs-lookup"><span data-stu-id="dc97f-p105">If you turn off audit log search in Office 365, you can still use the Office 365 Management Activity API to access auditing data for your organization. Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security &amp; Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell. However, if you've authorized any application to access your organization's auditing data via the Office 365 Management Activity API , those applications will continue to work.</span></span> 
    
- <span data-ttu-id="dc97f-121">如需搜尋 Office 365 的逐步指示稽核記錄，請參閱[Office 365 安全性搜尋稽核記錄&amp;規範中心](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="dc97f-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="dc97f-122">開啟稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="dc97f-122">Turn on audit log search</span></span>

<span data-ttu-id="dc97f-p106">您可以使用安全性&amp;規範中心或 PowerShell 開啟 Office 365 中的稽核記錄搜尋。可能需要數小時後才可以傳回結果搜尋稽核記錄時開啟稽核記錄搜尋。您必須指派稽核記錄 」 角色在 Exchange Online 開啟稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="dc97f-p106">You can use the Security &amp; Compliance Center or PowerShell to turn on audit log search in Office 365. It might take several hours after you turn on audit log search before you can return results when you search the audit log. You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security-amp-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="dc97f-126">使用安全性&amp;規範中心開啟稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="dc97f-126">Use the Security &amp; Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="dc97f-127">安全性&amp;規範管理中心，移至**搜尋&amp;調查** \> **稽核記錄搜尋**。</span><span class="sxs-lookup"><span data-stu-id="dc97f-127">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Audit log search**.</span></span>
    
2. <span data-ttu-id="dc97f-128">按一下 [**開始錄製使用者與系統活動**。</span><span class="sxs-lookup"><span data-stu-id="dc97f-128">Click **Start recording user and admin activities**.</span></span>
    
    ![按一下 [開始錄製使用者和系統管理員活動]，來開啟稽核](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="dc97f-130">說明使用者及組織中的系統活動會錄製到 Office 365 稽核記錄，適用於報表中檢視被顯示的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="dc97f-130">A dialog box is displayed saying that user and admin activity in your organization will be recorded to the Office 365 audit log and available to view in a report.</span></span> 
    
3. <span data-ttu-id="dc97f-131">按一下 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc97f-131">Click **Turn on**.</span></span>
    
    <span data-ttu-id="dc97f-132">顯示訊息指出做準備的稽核記錄及您可在幾小時準備完成後執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="dc97f-132">A message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="dc97f-133">使用 PowerShell 來開啟稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="dc97f-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="dc97f-134">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dc97f-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="dc97f-135">執行下列 PowerShell 命令，以開啟 [Office 365 中的稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="dc97f-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="dc97f-136">會顯示訊息指出它可能需要最多 60 分鐘，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="dc97f-136">A message is displayed saying that it might take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="dc97f-137">關閉 [稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="dc97f-137">Turn off audit log search</span></span>

<span data-ttu-id="dc97f-p107">您必須使用遠端 PowerShell 連線至 Exchange Online 組織來關閉 [稽核記錄搜尋。類似於開啟稽核記錄搜尋，您必須指派稽核記錄 」 角色在 Exchange Online，即可關閉稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="dc97f-p107">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search. Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="dc97f-140">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dc97f-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="dc97f-141">執行下列 PowerShell 命令，以關閉 [Office 365 中的稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="dc97f-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="dc97f-p108">之後 while 確認稽核記錄搜尋已關機 （停用）。有兩種方式可以執行這項作業：</span><span class="sxs-lookup"><span data-stu-id="dc97f-p108">After a while, verify that audit log search is turned off (disabled). There are two ways to do this:</span></span>
    
    - <span data-ttu-id="dc97f-144">在 PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="dc97f-144">In PowerShell, run the following command:</span></span>

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        <span data-ttu-id="dc97f-145">值`False`的_UnifiedAuditLogIngestionEnabled_屬性會指出稽核記錄搜尋已關閉。</span><span class="sxs-lookup"><span data-stu-id="dc97f-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="dc97f-146">安全性&amp;規範管理中心，移至**搜尋&amp;調查** \> **稽核記錄搜尋**，然後按一下 [**搜尋**。</span><span class="sxs-lookup"><span data-stu-id="dc97f-146">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Audit log search**, and then click **Search**.</span></span>
    
      <span data-ttu-id="dc97f-147">預警開啟稽核記錄搜尋不會顯示訊息。</span><span class="sxs-lookup"><span data-stu-id="dc97f-147">A message is displayed saying that audit log search isn't turned on.</span></span> 
    
      ![一則訊息，則 dispayed 稽核已關閉](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
