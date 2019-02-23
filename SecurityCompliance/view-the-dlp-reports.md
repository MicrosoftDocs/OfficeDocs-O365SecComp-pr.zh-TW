---
title: 檢視資料外洩防護報告
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 41eb4324-c513-4fa5-91c8-8fbd8aaba83b
description: 與 Office 365 的 DLP 報告，您可以快速檢視 DLP 原則比對、 覆寫或誤判; 的數目請參閱是否他們正在趨勢向上或向下一段時間 ；以不同方式 ； 篩選報表與其他詳細資料檢視中選取圖形上線條上的一點。
ms.openlocfilehash: 4e9e5405b5c35719c1b14efca91cdf87f416e7bd
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217573"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="ebd16-103">檢視資料外洩防護報告</span><span class="sxs-lookup"><span data-stu-id="ebd16-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="ebd16-p101">建立資料遺失防護 (DLP) 原則之後，您將想要確認他們正在運作時適用對象和協助您保持相容。使用 DLP 報告中的 Office 365 安全性&amp;規範中心，您可以快速檢視：</span><span class="sxs-lookup"><span data-stu-id="ebd16-p101">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant. With the DLP reports in the Office 365 Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="ebd16-p102">**DLP 原則比對**這份報告顯示一段時間的 DLP 原則相符項目計數。您可以依日期、 位置、 原則或巨集指令來篩選報告。您可以使用這份報告：</span><span class="sxs-lookup"><span data-stu-id="ebd16-p102">**DLP policy matches** This report shows the count of DLP policy matches over time. You can filter the report by date, location, policy, or action. You can use this report to:</span></span> 
    
  - <span data-ttu-id="ebd16-p103">調整或調整為您在測試模式中執行的 DLP 原則。您可以檢視特定的規則相符的內容。</span><span class="sxs-lookup"><span data-stu-id="ebd16-p103">Tune or refine your DLP policies as you run them in test mode. You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="ebd16-111">將重點放在特定時段，以了解尖峰和趨勢的原因。</span><span class="sxs-lookup"><span data-stu-id="ebd16-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="ebd16-112">探索違反組織的 DLP 原則的商務程序。</span><span class="sxs-lookup"><span data-stu-id="ebd16-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="ebd16-113">了解 DLP 原則的任何業務影響所看到的動作要套用至內容。</span><span class="sxs-lookup"><span data-stu-id="ebd16-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="ebd16-114">顯示該原則的任何符合項目來驗證是否符合特定 DLP 原則的規範。</span><span class="sxs-lookup"><span data-stu-id="ebd16-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="ebd16-115">檢視的主要使用者清單，然後重複至組織中的事件所提供的使用者。</span><span class="sxs-lookup"><span data-stu-id="ebd16-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="ebd16-116">在組織中檢視上方的敏感資訊類型的清單。</span><span class="sxs-lookup"><span data-stu-id="ebd16-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="ebd16-p104">**DLP 事件**這份報告也會顯示原則符合項目的一段時間，像是原則會比對報表。但是，該原則會比對報表顯示相符項目層級規則 ；例如，如果電子郵件符合三個不同的規則，原則比對報表顯示三個不同列項目。相反地，事件 」 報告顯示相符項目層級項目 ；例如，如果電子郵件符合三個不同的規則，事件報表會顯示單一列項目內容的項目所。</span><span class="sxs-lookup"><span data-stu-id="ebd16-p104">**DLP incidents** This report also shows policy matches over time, like the policy matches report. However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items. By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="ebd16-p105">因為報告計數會以不同方式彙總，原則相符項目報告是識別與特定規則的相符項目及可正常調整 DLP 原則。事件報表是內容的較佳的識別會有問題的 DLP 原則的特定部分。</span><span class="sxs-lookup"><span data-stu-id="ebd16-p105">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies. The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="ebd16-p106">**DLP 誤判和覆寫**如果 DLP 原則可讓使用者可覆寫它或報告為誤判，則這份報告顯示一段時間這類的執行個體計數。您可以依日期、 位置或原則篩選報告。您可以使用這份報告：</span><span class="sxs-lookup"><span data-stu-id="ebd16-p106">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time. You can filter the report by date, location, or policy. You can use this report to:</span></span> 
    
  - <span data-ttu-id="ebd16-125">調整或減少 DLP 原則來查看哪些原則可能會形成誤判高數目。</span><span class="sxs-lookup"><span data-stu-id="ebd16-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="ebd16-126">檢視只要有當他們解決的覆寫原則的原則提示使用者送出。</span><span class="sxs-lookup"><span data-stu-id="ebd16-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="ebd16-127">探索其中具有有效的商務程序所產生使用者過多的 DLP 原則衝突會覆寫。</span><span class="sxs-lookup"><span data-stu-id="ebd16-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="ebd16-p107">所有的 DLP 報告可以顯示資料的最新的四個月的時間週期。最新資料可能需要 24 小時的時間會出現在報表中。</span><span class="sxs-lookup"><span data-stu-id="ebd16-p107">All DLP reports can show data from the most recent four-month time period. The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="ebd16-130">您可以在 [安全性] 中找到這些報告&amp;規範中心\>**報告** \> **儀表板**。</span><span class="sxs-lookup"><span data-stu-id="ebd16-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![DLP 原則比對報告](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="ebd16-132">檢視遭到覆寫使用者送出的對齊</span><span class="sxs-lookup"><span data-stu-id="ebd16-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="ebd16-133">如果您的 DLP 原則允許使用者覆寫它，您可以使用誤判並覆寫報告檢視中的原則提示使用者所送出的文字。</span><span class="sxs-lookup"><span data-stu-id="ebd16-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![對齊] 欄位中的 「 DLP 誤判和覆寫報告詳細資料](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="ebd16-135">採取動作的見解與建議</span><span class="sxs-lookup"><span data-stu-id="ebd16-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="ebd16-136">報告可以顯示的見解與建議您將可以按一下 [查看潛在的問題的詳細資料並採取可能補救措施紅色的 [警告] 圖示。</span><span class="sxs-lookup"><span data-stu-id="ebd16-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![按一下 [詳細資料，並採取動作的見解圖示](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="ebd16-138">尋找 DLP 報告 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ebd16-138">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="ebd16-139">若要使用大部分的指令程式以安全性&amp;規範中心，您必須：</span><span class="sxs-lookup"><span data-stu-id="ebd16-139">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="ebd16-140">使用遠端 PowerShell 連線到 Office 365 安全性與合規性中心</span><span class="sxs-lookup"><span data-stu-id="ebd16-140">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="ebd16-141">使用下列任何一這些[Office 365 安全性&amp;規範中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="ebd16-141">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="ebd16-p108">不過，DLP 報告需要跨 Office 365，包括 Exchange Online 提取資料。有此原因的 DLP 報告指令程式可用在 Exchange Online Powershell — 不在安全性&amp;規範中心 Powershell。因此，若要使用 DLP 報告指令程式，您需要：</span><span class="sxs-lookup"><span data-stu-id="ebd16-p108">However, DLP reports need pull data from across Office 365, including Exchange Online. For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell. Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="ebd16-145">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ebd16-145">Connect to Exchange Online using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="ebd16-146">使用這些 cmdlet 的任何 DLP 報告：</span><span class="sxs-lookup"><span data-stu-id="ebd16-146">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="ebd16-147">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="ebd16-147">Get-DlpDetectionsReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [<span data-ttu-id="ebd16-148">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="ebd16-148">Get-DlpDetailReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

