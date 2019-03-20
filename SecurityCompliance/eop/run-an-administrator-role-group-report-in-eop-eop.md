---
title: '執行 EOP 中的系統管理員角色群組報告 '
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: 當系統管理員在系統管理員角色群組新增或移除成員時，Microsoft Exchange Online Protection (EOP) 會記錄每次發生的事件。
ms.openlocfilehash: 752def771d95fcfbb3f7cbe0bc86a33b3967716d
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692712"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="8976e-103">執行 EOP 中的系統管理員角色群組報告</span><span class="sxs-lookup"><span data-stu-id="8976e-103">Run an administrator role group report in EOP</span></span> 

 <span data-ttu-id="8976e-p101">當系統管理員在系統管理員角色群組新增或移除成員時，Microsoft Exchange Online Protection (EOP) 會記錄每次發生的事件。當您在 Exchange 系統管理中心執行系統管理員角色群組報告時，項目會顯示為搜尋結果，並包括受影響的角色群組、變更角色群組成員資格的人員和時間，以及做了什麼成員資格更新。使用此報告可監視指派給組織使用者的系統管理權限變更。</span><span class="sxs-lookup"><span data-stu-id="8976e-p101">When an administrator adds members to or removes members from administrator role groups, Microsoft Exchange Online Protection (EOP) logs each occurrence. When you run an administrator role group report in the Exchange admin center, entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made. Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8976e-107">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="8976e-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8976e-108">預估完成時間：2 分鐘</span><span class="sxs-lookup"><span data-stu-id="8976e-108">Estimated time to complete: 2 minutes</span></span>
    
- <span data-ttu-id="8976e-p102">您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)主題的「報告」一節。</span><span class="sxs-lookup"><span data-stu-id="8976e-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="8976e-111">如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Keyboard shortcuts in Exchange 2013**。</span><span class="sxs-lookup"><span data-stu-id="8976e-111">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="8976e-p103">有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="8976e-p103">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="8976e-115">使用 EAC 執行系統管理員角色群組報告</span><span class="sxs-lookup"><span data-stu-id="8976e-115">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="8976e-116">執行系統管理員角色群組報告，以尋找在特定時間範圍內，對您組織中管理角色群組所進行的變更。</span><span class="sxs-lookup"><span data-stu-id="8976e-116">Run the administrator role group report to find the changes to management role groups in your organization within a particular timeframe.</span></span>
  
1. <span data-ttu-id="8976e-117">在 EAC 中，瀏覽至 **[相符性管理]** \> **[稽核]**，然後選擇 **[執行系統管理員角色群組報告]**。</span><span class="sxs-lookup"><span data-stu-id="8976e-117">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>
    
2. <span data-ttu-id="8976e-p104">選擇 **[開始日期]** 和 **[結束日期]**。依預設，報告會搜尋過去兩週以來對系統管理員角色群組所做的變更。</span><span class="sxs-lookup"><span data-stu-id="8976e-p104">Choose the **Start date** and **End date**. By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>
    
3. <span data-ttu-id="8976e-p105">若要檢視特定角色群組的變更，請按一下 **[選取角色群組]**。在後續的對話方塊中選取一或多個角色群組，然後按一下 **[確定]**。您也可以將欄位留白，以尋找所有變更的角色群組。</span><span class="sxs-lookup"><span data-stu-id="8976e-p105">To view the changes for a specific role group, click **Select role groups**. Select the role group (or groups) in the subsequent dialog box, and click **OK**. You can also leave the field blank to find all changed role groups.</span></span>
    
4. <span data-ttu-id="8976e-123">Click **Search**.</span><span class="sxs-lookup"><span data-stu-id="8976e-123">Click **Search**.</span></span>
    
<span data-ttu-id="8976e-p106">如果使用您指定的準則找到任何變更，它們會出現在結果窗格中。按一下搜尋結果中的角色群組，即可在詳細資料窗格中查看變更。</span><span class="sxs-lookup"><span data-stu-id="8976e-p106">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8976e-126">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="8976e-126">How do you know this worked?</span></span>

<span data-ttu-id="8976e-p107">如果您已經成功執行系統管理員角色群組報告，已在日期範圍內變更的角色群組會顯示在搜尋結果窗格中。如果沒有任何結果，則表示在指定的日期範圍內，沒有對角色群組進行任何變更。如果您認為應該有結果，請變更日期範圍，然後重新執行報告。</span><span class="sxs-lookup"><span data-stu-id="8976e-p107">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>
  
## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="8976e-130">監視角色群組成員資格的變更</span><span class="sxs-lookup"><span data-stu-id="8976e-130">Monitor changes to role group membership</span></span>

<span data-ttu-id="8976e-p108">在角色群組中新增或移除成員時，搜尋結果會顯示在詳細資料窗格中，指出角色群組成員資格已經更新，並列出目前的成員。結果不會明確表示已新增或移除哪一位使用者。</span><span class="sxs-lookup"><span data-stu-id="8976e-p108">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>
  
<span data-ttu-id="8976e-p109">若要判斷是否已新增或移除某位使用者，您必須比較報告中的兩個個別項目。例如，以下是 **HelpDesk** 角色群組的記錄項目：</span><span class="sxs-lookup"><span data-stu-id="8976e-p109">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span> 
  
 <span data-ttu-id="8976e-135">**27.01.13 16:43:00 AM**</span><span class="sxs-lookup"><span data-stu-id="8976e-135">**1/27/2013 4:43 PM**</span></span>
  
 <span data-ttu-id="8976e-136">**Administrator**</span><span class="sxs-lookup"><span data-stu-id="8976e-136">**Administrator**</span></span>
  
 <span data-ttu-id="8976e-137">**Updated members:Administrator;annb,florencef;pilarp**</span><span class="sxs-lookup"><span data-stu-id="8976e-137">**Updated members: Administrator;annb,florencef;pilarp**</span></span>
  
 <span data-ttu-id="8976e-138">**06.02.13 10:09 AM**</span><span class="sxs-lookup"><span data-stu-id="8976e-138">**2/06/2013 10:09 AM**</span></span>
  
 <span data-ttu-id="8976e-139">**Administrator**</span><span class="sxs-lookup"><span data-stu-id="8976e-139">**Administrator**</span></span>
  
 <span data-ttu-id="8976e-140">**Updated members:Administrator;annb;florencef;pilarp;tonip**</span><span class="sxs-lookup"><span data-stu-id="8976e-140">**Updated members: Administrator;annb;florencef;pilarp;tonip**</span></span>
  
 <span data-ttu-id="8976e-141">**19.02.13 14:12:00 AM**</span><span class="sxs-lookup"><span data-stu-id="8976e-141">**2/19/2013 2:12 PM**</span></span>
  
 <span data-ttu-id="8976e-142">**Administrator**</span><span class="sxs-lookup"><span data-stu-id="8976e-142">**Administrator**</span></span>
  
 <span data-ttu-id="8976e-143">**Updated members:Administrator;annb;florencef;tonip**</span><span class="sxs-lookup"><span data-stu-id="8976e-143">**Updated members: Administrator;annb;florencef;tonip**</span></span>
  
<span data-ttu-id="8976e-144">在此範例中，系統管理員使用者帳戶做了以下變更：</span><span class="sxs-lookup"><span data-stu-id="8976e-144">In this example, the Administrator user account made the following changes:</span></span>
  
- <span data-ttu-id="8976e-145">他在 06.02.13 新增使用者 tonip。</span><span class="sxs-lookup"><span data-stu-id="8976e-145">On 2/06/2013, it added the user tonip.</span></span>
    
- <span data-ttu-id="8976e-146">他在 19.02.13 移除使用者 pilarp。</span><span class="sxs-lookup"><span data-stu-id="8976e-146">On 2/19/2013, it removed the user pilarp.</span></span>
    

