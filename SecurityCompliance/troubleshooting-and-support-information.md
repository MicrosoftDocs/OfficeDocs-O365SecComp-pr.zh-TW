---
title: 疑難排解和支援資訊
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
description: 本主題說明使用者和系統管理員可用的疑難排解步驟，並提供如何連絡技術支援人員以取得協助的相關資訊。
ms.openlocfilehash: d6168be0580175b172616b3274f2a13f36de5d57
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027630"
---
# <a name="troubleshooting-and-support-information"></a>疑難排解和支援資訊

本主題說明使用者和系統管理員可用的疑難排解步驟，並提供如何連絡技術支援人員以取得協助的相關資訊。
  
## <a name="troubleshooting-for-users"></a>使用者疑難排解

在新增「垃圾郵件回報增益集」之後，Microsoft Office Outlook 有時會發生問題。以下是可能發生的問題，以及解決這些問題的秘訣。 
  
- 按一下 **[回報垃圾郵件]** 沒有作用
    
- 選取電子郵件後，Outlook 停止回應
    
- 由於「無法傳遞」回覆，回報的垃圾郵件無法傳遞
    
### <a name="troubleshooting-tip"></a>疑難排解秘訣

1. 關閉並重新啟動 Microsoft Office Outlook。
    
2. 確認您能夠建立並傳送測試郵件。若要這麼做，您可以將測試郵件傳送至您負責的另一個電子郵件帳戶，然後驗證是否收到電子郵件。
    
如果問題持續發生，請連絡支援 IT 系統管理人員。
  
> [!TIP]
> 您也可以使用[not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com)電子郵件地址提交垃圾郵件直接向 Microsoft 使用[junk@office365.microsoft.com](mailto:junk@office365.microsoft.com)電子郵件地址和誤判的郵件。如需詳細資訊，請參閱[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件訊息給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。 
  
## <a name="troubleshooting-for-administrators"></a>系統管理員疑難排解

身為系統管理員的您，可能會遇到有使用者在使用 Microsoft Office Outlook 的垃圾郵件回報增益集時發生問題。以下是解決您可能遇到的問題的一些秘訣。 
  
 **問題：** 不斷出現錯誤訊息來要求使用者連絡系統管理員。 
  
### <a name="troubleshooting-tip"></a>疑難排解秘訣

1. 將下列登錄機碼值設為 "Verbose"：
    
  - **安裝在 32 位元作業系統上的 32 位元 Outlook：**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
  - **安裝在 64 位元作業系統上的 32 位元 Outlook：**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
  - **64 位元 Outlook (一律安裝在 64 位元作業系統上)：**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
2. 重新啟動 Microsoft Office Outlook，並要求使用者在看到錯誤訊息時回報。
    
3. 收集下列位置中的記錄資訊： 
    
    %LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt
    
4. 連絡 Exchange Online Protection 技術支援人員，並提供這項記錄資訊。 
    
 **問題：** 使用者在提交電子郵件為垃圾郵件時選擇不接收確認，但現在想要回復為此選項。 
  
### <a name="troubleshooting-tip"></a>疑難排解秘訣

1. 將下列登錄機碼值設為 "True"：HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk
    
2. 重新啟動 Microsoft Office Outlook。
    
## <a name="support-information"></a>支援資訊

如果您需要安裝的說明，請設定 」 或 「 解除安裝增益集，請連絡技術支援 Office 365 系統管理中心的 [支援] 頁面上使用新的服務要求] 連結。包括透過電話] 和 [自我支援選項的服務要求送出的其他選項，請參閱[說明和支援 eop](eop/help-and-support-for-eop.md)。
  
## <a name="for-more-information"></a>如需詳細資訊

[啟用報表訊息增益集](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)
  
[向 Microsoft 回報垃圾郵件](report-junk-email-messages-to-microsoft.md)
  

