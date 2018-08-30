---
title: 啟用或停用 Office 365 中的安全提示
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/6/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
description: 指示 Office 365 和 EOP 系統管理員如何啟用和停用的電子郵件安全性提示。
ms.openlocfilehash: 3a8257f9d34ec5def54e2b9c9e919172366d023f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526855"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a>啟用或停用 Office 365 中的安全提示

Exchange Online Protection (EOP)，或者戳記，safety 提示以它傳送的電子郵件訊息。如果郵件已標示為垃圾郵件的 Office 365 中，如果郵件包含如網路釣魚詐騙郵件可疑的某個項目或外部圖像有這些 safety 秘訣提供一個快速而 visual 方法來判斷訊息是否從安全的收件者已驗證寄件者已封鎖。Office 365 和 EOP 獨立版系統管理員可以編輯垃圾郵件原則設定啟用或停用不會顯示 Outlook 與其他桌面電子郵件用戶端中的電子郵件安全性提示。 
  
Office 365 讓組織的預設安全秘訣和建議您保留這些功能可協助戰鬥垃圾郵件和網路釣魚攻擊。您無法停用 Outlook web 上 safety 秘訣。
  
若要查看範例並了解 safety 提示中顯示的資訊，請參閱[Safety 秘訣 （英文） Office 365 中的電子郵件訊息中。](safety-tips-in-office-365.md)
  
本主題內容：
  
- [若要啟用或停用 safety 祕訣使用 Office 365 安全性&amp;規範中心](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [若要啟用或停用 safety 秘訣 （英文） 透過 PowerShell](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a>若要啟用或停用 safety 祕訣使用 Office 365 安全性&amp;規範中心
<a name="SandCCsafetytip"> </a>

1. 移至 [ [https://protection.office.com](https://protection.office.com)。
    
2. 以您的工作或學校帳戶登入 Office 365。
    
3. 選擇 [ **Threat Management** \> **原則**。 
    
4. 在 [**原則**] 頁面上選擇 [**反垃圾郵件**]。
    
    ![這個螢幕擷取畫面顯示如何取得反垃圾郵件設定] 頁面上的 [安全性]&amp;規範中心。](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. **反垃圾郵件設定**] 頁面上選擇 [**自訂**] 索引標籤。 
    
    ![這個螢幕擷取畫面顯示 [自訂] 索引標籤的位置上反垃圾郵件設定] 頁面上的 [安全性]&amp;規範中心。](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. 若有必要，請選擇 [**自訂設定**轉換到開啟的自訂設定。自訂設定參數設為**關閉**，如果您將不能夠修改垃圾郵件篩選器原則。
    
    ![這個螢幕擷取畫面顯示自訂的反垃圾郵件篩選已關閉的原則設定。](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. 展開您想要修改，然後選擇 [**編輯原則**的垃圾郵件原則。例如，選擇 [**預設垃圾郵件篩選原則**旁的向下箭號。或者，如果您想，您可以選擇 [**新增原則**建立新的原則。
    
8. 依序展開 [**垃圾郵件和大量**動作。 
    
9. 若要啟用安全秘訣、 下**Safety 秘訣**、 [**上**] 核取方塊。若要停用安全秘訣，請清除 [**上**] 核取方塊。 
    
10. 選擇 [**儲存**]。
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a>若要啟用或停用 safety 秘訣 （英文） 透過 PowerShell
<a name="pshellsafetytip"> </a>

系統管理員可以使用 Exchange Online PowerShell 啟用或停用安全秘訣。使用 Set-hostedcontentfilterpolicy 指令程式來啟用或停用垃圾郵件篩選器原則中的安全秘訣。
  
1. 連線到 Exchange Online PowerShell。資訊，請參閱[Connect to Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. 執行 Set-hostedcontentfilterpolicy 指令程式來啟用或停用安全秘訣：
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

    其中：
    
  -  *原則名稱*是您要修改，例如**預設**原則的名稱。
    
  -  `$true`可讓 safety 秘訣垃圾郵件篩選器原則。 
    
  -  `$false`停用垃圾郵件篩選器原則 safety 的秘訣。 
    
    例如，若要停用預設的垃圾郵件篩選器原則的安全秘訣，請執行下列命令：
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

    如需此 cmdlet 的詳細資訊，請參閱[Set-hostedcontentfilterpolicy](https://technet.microsoft.com/library/jj200781.aspx)。
    
## <a name="still-need-help"></a>仍然需要說明嗎？
<a name="pshellsafetytip"> </a>

如果您停用安全秘訣，但卻還是看到這些電子郵件訊息中，檢查下列事項：
  
- 您無法停用 Outlook web 上 safety 秘訣。嘗試在另一個用戶端，例如 Outlook 檢視相同的電子郵件。
    
- Safety 提示上根據預設會針對每一個使用 EOP，這包括具有 Office 365 的任何人。若要停用電子郵件中顯示來自 safety 秘訣，您必須使用停用其垃圾郵件篩選器原則本主題所述。一旦您已設定的原則，請確定已啟用。如需啟用垃圾郵件篩選器原則，請參閱[設定垃圾郵件篩選器原則](https://technet.microsoft.com/library/jj200684.aspx)。
    
更多抵禦垃圾郵件和網路釣魚的方式，請參閱[Office 365 電子郵件反垃圾郵件保護](anti-spam-protection.md)。
  

