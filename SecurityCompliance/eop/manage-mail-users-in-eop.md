---
title: 管理 EOP 中的郵件使用者
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 定義郵件使用者是管理 Exchange Online Protection (EOP) 的重要環節。
ms.openlocfilehash: e985adf5659b50cf567ea798a092f809d77ca470
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027390"
---
# <a name="manage-mail-users-in-eop"></a>管理 EOP 中的郵件使用者

定義郵件使用者是管理 Exchange Online Protection (EOP) 的重要環節。在 EOP 中，您可以透過數種方式來管理使用者：
  
- 使用目錄同步處理來管理郵件使用者： 如果您的公司內部部署 Active Directory 環境中現有的使用者帳戶，您可以同步處理至 Azure Active Directory (AD)，其中之帳戶的複本儲存在雲端那些帳戶。當您同步處理至 Azure Active Directory 現有的使用者帳戶時，您可以檢視這些使用者的 Exchange 系統管理中心 (EAC) 的 [**收件者**] 窗格中。建議使用目錄同步處理。 
    
- 使用 EAC 管理郵件使用者：在 EAC 中直接新增及管理郵件使用者。這是新增郵件使用者最簡單的方法，也很適合一次新增一位使用者。
    
- 使用遠端 Windows PowerShell 管理郵件使用者：執行遠端 Windows PowerShell 來新增和管理郵件使用者。這個方法適合用來新增多筆記錄和建立指令碼。
    
> [!NOTE]
> 您可以在 Office 365 系統管理中心新增使用者，不過，這些使用者不能做為郵件收件者。 
  
## <a name="before-you-begin"></a>開始之前

- 本主題中的程序需要特定權限。請查看每個程序以取得權限資訊。
    
- 如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。
    
> [!TIP]
> 有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a>使用目錄同步處理來管理郵件使用者

本節提供使用目錄同步處理來管理電子郵件使用者的相關資訊。
  
> [!IMPORTANT]
> 如果您使用目錄同步作業來管理收件者，您仍可在 Office 365 系統管理中心 中新增和管理使用者，但這些使用者不會和您的內部部署 Active Directory 同步處理。這是因為目錄同步作業只會從內部部署 Active Directory 同步收件者至雲端。 
  
> [!TIP]
>  建議搭配下列功能一起使用目錄同步處理： > **Outlook 安全的寄件者和封鎖的寄件者清單** - 同步處理至服務時，這些清單優先於服務的垃圾郵件篩選。這可讓使用者針對個別使用者或個別網域，管理他們自己的安全寄件者和封鎖的寄件者清單。 > **目錄架構邊緣封鎖 (DBEB)** - 如需 DBEB 的詳細資訊，請參閱＜ [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)＞。 > **使用者垃圾郵件隔離** - 若要存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。保護內部部署信箱的 EOP 客戶必須是有效的電子郵件使用者。 > **傳輸規則** -當您使用目錄同步作業時，您的現有 Active Directory 使用者和群組會自動上傳到雲端，然後您可以建立以特定使用者及/或群組為目標的傳輸規則，而不必透過 EAC 或遠端 Windows PowerShell 手動新增它們。請注意， [動態通訊群組](https://go.microsoft.com/fwlink/?LinkId=507569)無法透過目錄同步作業進行同步處理。 
  
 **開始之前**
  
取得必要權限，並做好目錄同步處理的準備工作，如[為目錄同步作業做好準備](https://go.microsoft.com/fwlink/p/?LinkId=308908)所說明。
  
### <a name="to-synchronize-user-directories"></a>同步處理使用者目錄

1. 啟動目錄同步處理，如[啟動目錄同步處理](https://go.microsoft.com/fwlink/p/?LinkId=308909)所說明。
    
2. 設定目錄同步處理電腦，如[設定您的目錄同步處理電腦](http://go.microsoft.com/fwlink/p/?LinkId=308911)所說明。
    
3. 同步處理您的目錄，如[使用設定精靈同步處理您的目錄](http://go.microsoft.com/fwlink/?LinkId=308912)所說明。
    
    > [!IMPORTANT]
    > 完成 Azure Active Directory 同步處理工具設定精靈 之後，您的 Active Directory 樹系中會建立 **MSOL_AD_SYNC** 帳戶。此帳戶將用來讀取和同步處理您的內部部署 Active Directory 資訊。為了讓目錄同步作業能夠正確運作，請確定有開啟您的本機目錄同步作業伺服器上的 TCP 443。 
  
4. 啟動已同步處理的使用者，如[啟用同步處理的使用者](http://go.microsoft.com/fwlink/p/?LinkId=308913)所說明。
    
5. 管理目錄同步處理，如[管理目錄同步作業](http://go.microsoft.com/fwlink/p/?LinkId=308915)所說明。
    
6. 確認 EOP 的正確同步處理。在 EAC 中，移至 [**收件者** \> **連絡人**並檢視使用者清單從內部部署環境正確同步處理。 
    
## <a name="use-the-eac-to-manage-mail-users"></a>使用 EAC 管理郵件使用者

本節提供直接在 EAC 中新增及管理電子郵件使用者的相關資訊。
  
 **開始之前**
  
您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)中的「使用者、連絡人和角色群組」項目。
  
### <a name="to-add-a-mail-user-in-the-eac"></a>在 EAC 中新增郵件使用者

1. 移至 EAC 中的 [ **收件者**] \> [ **連絡人**]，然後按一下 [ **新增 +**]，以建立電子郵件使用者。
    
2. 在 [ **新增郵件使用者**] 頁面上，輸入使用者的資訊，包括下列項目： 
    
   ****

|**郵件使用者內容**|**描述**|
|:-----|:-----|
|**名字**、 **縮寫**和 **姓氏** <br/> |在適當的方塊中輸入使用者的完整名稱。  <br/> |
|**顯示名稱** <br/> |輸入名稱，最多 64 個字元。根據預設，此方塊會顯示 [**名字**]、[**縮寫**] 和 [**姓氏**] 方塊中的名稱 (如果有的話)。顯示名稱是必要項目。  <br/> |
|**別名** <br/> |輸入使用者的唯一別名，最多 64 個字元。別名是必要項目。  <br/> |
|**外部電子郵件地址** <br/> |輸入使用者的外部電子郵件地址。  <br/> |
|**使用者識別碼** <br/> |輸入郵件使用者將用來登入服務的名稱。使用者登入名稱由 @ 符號左側的使用者名稱和右側的尾碼所組成。一般來說，尾碼是使用者帳戶所在的網域名稱。  <br/> |
|**新密碼** <br/> |輸入郵件使用者將用來登入服務的密碼。請確定您提供的密碼符合您正在其中建立使用者帳戶之網域的密碼長度、複雜性和歷程記錄需求。  <br/> |
|**確認密碼** <br/> |重新輸入密碼加以確認。  <br/> |
   
3. 按一下 [ **儲存**]，以建立新的郵件使用者。新的使用者應會出現在使用者清單中。 
    
### <a name="to-edit-or-remove-a-mail-user-in-the-eac"></a>在 EAC 中編輯或移除郵件使用者

- 在 EAC 中，移至 [**收件者** \> **連絡人**。在使用者清單中，按一下您要檢視或變更的使用者，然後選取 [**編輯**![編輯圖示](../media/ITPro-EAC-EditIcon.png)以視需要更新使用者設定。您可以變更使用者的名稱、 別名或連絡人資訊，以及您可以在組織中記錄於使用者角色的詳細的資訊。您可以也選取使用者，然後選擇 [**移除**![移除圖示](../media/ITPro-EAC-RemoveIcon.png)將它刪除。 
    
## <a name="use-remote-windows-powershell-to-manage-mail-users"></a>使用遠端 Windows PowerShell 管理郵件使用者

本節提供使用遠端 Windows PowerShell 來新增和管理郵件使用者的相關資訊。
  
 **開始之前**
  
- 您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)中的「使用者、連絡人和角色群組」項目。
    
- 請注意，使用遠端 PowerShell 指令程式建立郵件使用者時，可能會遇到節流問題。
    
- 此指令程式採用批次處理方法，因此導致幾分鐘的傳播延遲，然後才能看到指令程式的結果。
    
- 若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱＜[使用遠端 PowerShell 連線到 Exchange Online Protection](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx)＞。
    
 **使用遠端 PowerShell 新增郵件使用者**
  
此範例使用 [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) 在 EOP 中為 Jeffrey Zeng 建立具有郵件功能的使用者帳戶，詳細資料如下： 
  
- 名字為 Jeffrey，姓氏為 Zeng。
    
- 名稱是 Jeffrey，而顯示名稱是 Jeffrey Zeng。
    
- 別名為 jeffreyz。
    
- 外部電子郵件地址為 jzeng@tailspintoys.com。
    
- Office 365 登入名稱是 jeffreyz@contoso.onmicrosoft.com。
    
- 密碼為 Pa$$word1。
    
```
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

 **確認此作業正常運作**
  
依下列方式執行 [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) 指令程式，以顯示新郵件使用者 Jeffrey Zeng 的相關資訊： 
  
```
Get-User "Jeffrey Zeng"

```

 **使用遠端 PowerShell 編輯郵件使用者的屬性**
  
使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) 和 [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) 指令程式來檢視或變更郵件使用者的屬性。 
  
此範例會設定 Pilar Pinilla 的外部電子郵件地址。
  
```
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

此範例會將所有郵件使用者的 [公司] 內容設定為 [Contoso]。
  
```
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}

```

 **確認此作業正常運作**
  
上述範例中我們變更郵件使用者 Pilar Pinella 的屬性，請使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) 指令程式來驗證變更(請注意，您可以檢視多個郵件連絡人的多個屬性)。 
  
```
Get-Recipient -Identity "Pilar Pinilla" | Format-List 

```

在上述範例中，所有郵件使用者的 [公司] 屬性設為 [Contoso]，請執行下列命令來驗證變更：
  
```
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> 此指令程式採用批次處理方法，因此導致幾分鐘的傳播延遲，然後才能看到指令程式的結果。 
  
 **使用遠端 PowerShell 移除郵件使用者**
  
此範例使用 [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) 指令程式來刪除使用者 Jeffrey Zeng： 
  
```
Remove-EOPMailUser -Identity Jeffrey
```

 **確認此作業正常運作**
  
依下列方式執行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) 指令程式。應該會出現錯誤訊息，因為使用者已不存在。 
  
```
Get-Recipient Jeffrey | fl
```


