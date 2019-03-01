---
title: 隔離常見問題集
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 本主題提供有關託管隔離區的常見問題與解答。
ms.openlocfilehash: 9f9b16a92b8ef8105a9439972ebed54111b227c6
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341174"
---
# <a name="quarantine-faq"></a>隔離常見問題集

本主題提供有關託管隔離區的常見問題與解答。這些解答適用於 Microsoft Exchange Online 及 Exchange Online Protection 客戶。
  
 **問： 如何管理隔離區中的惡意程式碼隔離的郵件？**
  
您必須使用安全性<b0></b0>以檢視並處理郵件已傳送至隔離區，因為它們包含惡意程式碼的合規性中心。如需詳細資訊，請參閱 < <b1>Office 365 中的隔離電子郵件</b1>。
  
 **問：如何設定服務以將因垃圾郵件而遭到隔離的郵件傳送至隔離區？**
  
答： 根據預設，內容篩選的郵件會傳送至 [收件者的垃圾郵件] 資料夾。不過，系統管理員可以設定內容篩選原則，以將垃圾郵件隔離的郵件傳送至隔離區。如需可以在內容篩選的郵件執行的不同動作的詳細資訊，請參閱 <<c0>設定垃圾郵件篩選原則。
  
 **問：此服務是否可讓系統管理員和使用者管理被當成垃圾郵件隔離的郵件？**
  
答：如果您是系統管理員，您可以在 Exchange 系統管理中心 (EAC) 中搜尋及檢視關於所有隔離電子郵件的詳細資訊。找到郵件後，您可以將該郵件釋出給特定使用者，並可選擇向 Microsoft 垃圾郵件分析小組報告該郵件為誤判 (非垃圾郵件)。如需詳細資訊，請參閱 [以系統管理員身分找到並釋放被隔離的郵件](find-and-release-quarantined-messages-as-an-administrator.md)。
  
如果您是使用者，則可以透過下列項目管理自己被當成垃圾郵件隔離的郵件： 
  
- 垃圾郵件隔離使用者介面。如需詳細資訊，請參閱 [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。
        
 **問：如何授權使用者存取垃圾郵件隔離區？**
  
答： 以存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。保護內部部署信箱的 EOP 客戶必須是有效的電子郵件使用者透過目錄同步處理或 EAC 建立。如需管理使用者的詳細資訊，EOP 系統管理員可以參閱[管理 EOP 中的郵件使用者](eop/manage-mail-users-in-eop.md)。為 EOP 獨立版客戶，我們建議使用目錄同步處理，並啟用目錄架構邊緣封鎖;如需詳細資訊，請參閱[使用 Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。
  
 **問：不是垃圾郵件的項目是否會傳送到隔離區？**
  
答： 郵件符合郵件流程規則 （也稱為傳輸規則） 也傳送至管理員隔離區，如果這是設定的動作。垃圾郵件只是使用者隔離區。
  
 **問：郵件會保留在隔離區中多久？**
  
答： 依預設，垃圾郵件隔離的郵件會保留在隔離區 30 天，而被隔離的郵件符合郵件流程規則會保留在隔離區 7 天。在這段時間後的郵件會刪除，而且而無法加以擷取。符合郵件流程規則的隔離郵件的保留期間不是可設定的。不過，可以降低垃圾郵件隔離的郵件的保留期間，透過內容篩選原則中的 [**保留垃圾郵件 （天） 的**設定。如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。
  
 **問：我可以一次釋出或報告多個隔離的郵件嗎？**
  
答： 釋出或一次報表多封郵件很不目前無法使用 EAC 或使用者垃圾郵件隔離區中。不過，系統管理員可以建立遠端 Windows PowerShell 指令碼，以完成這項工作。使用[Get-quarantinemessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx)指令程式來搜尋郵件，並釋放這些[Release-quarantinemessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx)指令程式。 
  
 **問：搜尋隔離的郵件時是否支援萬用字元？我可以搜尋特定網域的隔離郵件嗎？**
  
答：在 Exchange 系統管理中心指定搜尋準則時不支援萬用字元。例如，在搜尋寄件者時，您必須指定完整的電子郵件地址。
  
系統管理員可以使用遠端 Windows PowerShell，指定 [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) 指令程式在特定網域 (例如 contoso.com) 中搜尋隔離的郵件： 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

結果可以傳遞至 [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) 指令程式。請加上 -ReleaseToAll 參數，以將郵件釋出給所有收件者。郵件一經釋出，就無法再釋出一次。 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```


