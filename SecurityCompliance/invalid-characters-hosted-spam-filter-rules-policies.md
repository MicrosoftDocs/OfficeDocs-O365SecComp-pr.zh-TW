---
title: 避免在垃圾郵件篩選器規則和垃圾郵件篩選器原則中的字元無效
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 提供系統管理員其反垃圾郵件組態中有無效的字元，並嘗試使用安全性執行發生問題的說明&amp;規範中心。
ms.openlocfilehash: ca409b4daa7bec01417adb7cbfdfa2a128929e81
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018732"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="2e8b1-103">避免在垃圾郵件篩選器規則中的無效字元和垃圾郵件篩選器原則</span><span class="sxs-lookup"><span data-stu-id="2e8b1-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="2e8b1-p101">先前、 Office 365 系統管理員設定及使用 Exchange 系統管理中心 (EAC) 來設定垃圾郵件篩選器規則和垃圾郵件篩選器原則。現在，您可以使用安全性&amp;規範中心來管理您的反垃圾郵件設定。下列字元所支援的 EAC 中但不是支援使用安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="2e8b1-p101">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange Admin Center (EAC). Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration. The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="2e8b1-107">**無效字元：**</span><span class="sxs-lookup"><span data-stu-id="2e8b1-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="2e8b1-108">如果您垃圾郵件篩選器規則] 或 [您的垃圾郵件篩選器原則中包含任何的無效字元，您可能會發生任何或所有的這些問題：</span><span class="sxs-lookup"><span data-stu-id="2e8b1-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="2e8b1-109">您可能無法在 [安全性] 中尋找原則或規則&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="2e8b1-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="2e8b1-110">您可能會在嘗試使用 Windows PowerShell 取得的規則或原則時收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="2e8b1-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="2e8b1-111">您可能會發現的原則或設定請勿執行或執行如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="2e8b1-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="2e8b1-112">從垃圾郵件篩選器原則和規則中移除無效的字元</span><span class="sxs-lookup"><span data-stu-id="2e8b1-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="2e8b1-113">一旦您識別的原則和規則包含無效字元，您可以使用 Windows PowerShell cmdlet 來變更名稱。</span><span class="sxs-lookup"><span data-stu-id="2e8b1-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="2e8b1-114">[連線至 Exchange Online 使用遠端 PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="2e8b1-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="2e8b1-115">若要變更垃圾郵件篩選器原則的名稱，以下列方式執行 Set-hostedcontentfilterpolicy 指令程式：</span><span class="sxs-lookup"><span data-stu-id="2e8b1-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="2e8b1-116">若要變更垃圾郵件篩選器規則的名稱，以下列方式執行 Set-hostedcontentfilterrule cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2e8b1-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="2e8b1-117">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="2e8b1-117">For more information</span></span>

[<span data-ttu-id="2e8b1-118">威脅的安全性管理&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="2e8b1-118">Threat management in the Security &amp; Compliance Center</span></span>](threat-management.md)
  
[<span data-ttu-id="2e8b1-119">Set-hostedcontentfilterpolicy</span><span class="sxs-lookup"><span data-stu-id="2e8b1-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[<span data-ttu-id="2e8b1-120">Set-hostedcontentfilterrule</span><span class="sxs-lookup"><span data-stu-id="2e8b1-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)
