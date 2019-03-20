---
title: 隔離常見問題集
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 本主題提供有關託管隔離區的常見問題與解答。
ms.openlocfilehash: 9a9673b3360a9a8b6bf837e09b49aca7a38e2172
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693262"
---
# <a name="quarantine-faq"></a>隔離常見問題集

本主題提供有關託管隔離區的常見問題與解答。這些解答適用於 Microsoft Exchange Online 及 Exchange Online Protection 客戶。
  
 **問： 如何管理隔離區中的惡意程式碼隔離的郵件？**
  
您必須使用安全性&amp;以檢視並處理郵件已傳送至隔離區，因為它們包含惡意程式碼的合規性中心。 如需詳細資訊，請參閱 < <b0>Office 365 中的隔離電子郵件</b0>。
  
 **問：如何設定服務以將因垃圾郵件而遭到隔離的郵件傳送至隔離區？**
  
答：是。 根據預設，內容篩選的郵件會傳送至 [收件者的垃圾郵件] 資料夾。 不過，系統管理員可以設定內容篩選原則，以將垃圾郵件隔離的郵件傳送至隔離區。 如需可以在內容篩選的郵件執行的不同動作的詳細資訊，請參閱 <<c0>設定垃圾郵件篩選原則。
  
 **問：此服務是否可讓系統管理員和使用者管理被當成垃圾郵件隔離的郵件？**
  
答：如果您是系統管理員，您可以在 Exchange 系統管理中心 (EAC) 中搜尋及檢視關於所有隔離電子郵件的詳細資訊。找到郵件後，您可以將該郵件釋出給特定使用者，並可選擇向 Microsoft 垃圾郵件分析小組報告該郵件為誤判 (非垃圾郵件)。如需詳細資訊，請參閱 [以系統管理員身分找到並釋放被隔離的郵件](find-and-release-quarantined-messages-as-an-administrator.md)。
  
如果您是使用者，則可以透過下列項目管理自己被當成垃圾郵件隔離的郵件： 
  
- 垃圾郵件隔離使用者介面。 如需詳細資訊，請參閱 [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。
        
 **問：如何授權使用者存取垃圾郵件隔離區？**
  
答：是。 若要存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。 保護內部部署信箱的 EOP 客戶必須是透過目錄同步處理或 EAC 建立的有效電子郵件使用者。 如需管理使用者的詳細資訊，EOP 系統管理員可以參閱[管理 EOP 中的郵件使用者](eop/manage-mail-users-in-eop.md)。 對於 EOP 獨立客戶，則建議使用目錄同步處理並啟用目錄架構邊緣封鎖；如需詳細資訊，請參閱[使用目錄架構邊緣封鎖以拒絕傳送至無效收件者的郵件](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。
  
 **問：不是垃圾郵件的項目是否會傳送到隔離區？**
  
答：是。 符合郵件流程規則 （也稱為傳輸規則） 的郵件也傳送至管理員隔離區，如果是設定的動作。 垃圾郵件只是使用者隔離區。
  
 **問：郵件會保留在隔離區中多久？**
  
答：是。 根據預設，垃圾郵件隔離的郵件會保留在隔離區 30 天，而被隔離的郵件符合郵件流程規則會保留在隔離區 7 天。 超過這段時間後，郵件就會遭到刪除，而無法加以擷取。 符合郵件流程規則的隔離郵件的保留期間不是可設定的。 不過，您可以透過內容篩選原則的 **[保留垃圾郵件的天數]** 設定，縮短垃圾郵件隔離郵件的保留期限。 如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。
  
 **問：我可以一次釋出或報告多個隔離的郵件嗎？**
  
答：是。 無法在 EAC 中或使用者垃圾郵件隔離區中目前可用版本或一次回報多封郵件的能力。 不過，系統管理員可以建立遠端 Windows PowerShell 指令碼，以完成這項工作。 使用[Get-quarantinemessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx)指令程式來搜尋郵件，並釋放這些[Release-quarantinemessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx)指令程式。 
  
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


