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
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>避免在垃圾郵件篩選器規則中的無效字元和垃圾郵件篩選器原則 

先前、 Office 365 系統管理員設定及使用 Exchange 系統管理中心 (EAC) 來設定垃圾郵件篩選器規則和垃圾郵件篩選器原則。現在，您可以使用安全性&amp;規範中心來管理您的反垃圾郵件設定。下列字元所支援的 EAC 中但不是支援使用安全性&amp;規範中心。  

**無效字元：**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

如果您垃圾郵件篩選器規則] 或 [您的垃圾郵件篩選器原則中包含任何的無效字元，您可能會發生任何或所有的這些問題：
- 您可能無法在 [安全性] 中尋找原則或規則&amp;規範中心。
- 您可能會在嘗試使用 Windows PowerShell 取得的規則或原則時收到錯誤。
- 您可能會發現的原則或設定請勿執行或執行如預期般運作。

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>從垃圾郵件篩選器原則和規則中移除無效的字元

一旦您識別的原則和規則包含無效字元，您可以使用 Windows PowerShell cmdlet 來變更名稱。 

1. [連線至 Exchange Online 使用遠端 PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。
    
2. 若要變更垃圾郵件篩選器原則的名稱，以下列方式執行 Set-hostedcontentfilterpolicy 指令程式：
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. 若要變更垃圾郵件篩選器規則的名稱，以下列方式執行 Set-hostedcontentfilterrule cmdlet：
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>如需詳細資訊

[威脅的安全性管理&amp;規範中心](threat-management.md)
  
[Set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[Set-hostedcontentfilterrule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)
