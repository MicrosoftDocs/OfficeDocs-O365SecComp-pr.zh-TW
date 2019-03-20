---
title: 管理 EOP 中的群組
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: 您可以使用 Exchange Online Protection (EOP) 來建立擁有郵件功能的群組，Exchange 組織。 您也可以使用 EOP 來定義或更新指定成員資格、 電子郵件地址，以及其他方面的群組的群組內容。
ms.openlocfilehash: db649e4fd955d13e50e96007e8e38fe2c1de5b4d
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693297"
---
# <a name="manage-groups-in-eop"></a>管理 EOP 中的群組

 您可以使用 Exchange Online Protection (EOP) 來建立擁有郵件功能的群組，Exchange 組織。 您也可以使用 EOP 來定義或更新指定成員資格、 電子郵件地址，以及其他方面的群組的群組內容。 您可以建立通訊群組和安全性群組，視您的需求而定。 使用 Exchange 系統管理中心 (EAC) 或透過遠端 Windows PowerShell，可以建立這些群組。 
  
## <a name="types-of-mail-enabled-groups"></a>擁有郵件功能的群組類型

部署 Exchange 組織，您可以建立兩種類型的群組：
  
- [建立在 EAC 中的群組](manage-groups-in-eop.md)（也稱為通訊群組） 是電子郵件使用者，例如小組或其他臨機操作的群組，且需要能夠接收或傳送電子郵件有關感興趣的公共區域的集合。 通訊群組是以獨佔方式來散佈電子郵件訊息。 在 EOP 中，通訊群組是指任何擁有郵件功能的群組，不論其具有安全性內容。
    
- [編輯或移除在 EAC 中的群組](manage-groups-in-eop.md)（也稱為安全性群組） 是需要系統管理員角色的存取權限的電子郵件使用者的集合。 例如，您可能想要提供使用者特定群組系統管理員角色權限，讓他們可以設定反垃圾郵件和反惡意程式碼設定。
    
    > [!NOTE]
    > 根據預設，所有新的擁有郵件功能的安全群組會要求驗證所有寄件者。 這可防止外部寄件者傳送郵件給擁有郵件功能的安全性群組。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要的權限，請參閱[Feature permissions in EOP](feature-permissions-in-eop.md)主題中的 「 通訊群組和安全性群組 」 項目。 
    
- 請注意，在建立和管理群組使用遠端 PowerShell cmdlet，您可能會遇到節流問題。
    
- 此指令程式採用批次處理方法，因此導致幾分鐘的傳播延遲，然後才能看到指令程式的結果。
    
- 若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱＜[使用遠端 PowerShell 連線到 Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)＞。
    
- 如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。
    
> [!TIP]
> 有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="create-a-group-in-the-eac"></a>在 EAC 中建立群組

1. 在 Exchange 系統管理中心 (EAC) 中，前往 [**收件者** \> **群組**。
    
2. 按一下 [**新增**![加入圖示](../media/ITPro-EAC-AddIcon.gif)，和 [**通訊群組**或**安全性群組**，視您的需求而定。 請參閱差別[之擁有郵件功能的群組類型](manage-groups-in-eop.md)。 
    
3. 在 [**新增通訊群組**或**新的安全性群組**] 頁面上，完成下列欄位： 
    
  - **顯示名稱**輸入是唯一的您的組織且 EOP 使用者有意義的顯示名稱。 顯示名稱是必要項目。 
    
  - **別名**輸入群組的別名最多 64 個字元，是唯一的您的組織。 EOP 使用者輸入的別名中： 行的電子郵件訊息與別名解析為群組的顯示名稱。 如果您變更別名時，群組的主要 SMTP 位址也變更，並將包含新的別名。 別名為必要項目。 
    
  - **描述**使他人了解群組的用途，請輸入群組的描述。 
    
  - **擁有者**根據預設，會建立群組的人員會為擁有者。 您可以選擇 [**新增]** 新增擁有者![加入圖示](../media/ITPro-EAC-AddIcon.gif)。 所有群組都必須至少一個擁有者。
    
    > [!NOTE]
    > 擁有者不必是群組的成員。 
  
  - **成員**若要新增群組成員並指定核准是否需要使用者在加入或離開群組，請使用此區段。 若要將成員新增至群組中，按一下 [**新增**![加入圖示](../media/ITPro-EAC-AddIcon.gif)。
    
4. 按一下 **[確定]** 以返回原始頁面。 
    
5. 當您已完成，請按一下 [**儲存**] 以建立群組。 新的群組應該出現在群組清單。 
    
## <a name="edit-or-remove-a-group-in-the-eac"></a>編輯或移除在 EAC 中的群組

1. In the EAC, navigate to **Recipients** \> **Groups**.
    
2. 執行下列其中一項動作：
    
  - 若要編輯群組： 在群組清單中，按一下您要檢視或變更的 [安全性] 群組的通訊群組，然後按一下 [**編輯**![編輯圖示](../media/ITPro-EAC-EditIcon.gif)。 您可以更新的一般設定、 新增或移除群組擁有者，並新增或移除群組成員，視需要。
    
  - 若要移除群組： 選取群組，然後按一下 [**移除**![移除圖示](../media/ITPro-EAC-RemoveIcon.gif)。
    
3. 當您完成變更後時，按一下 [**儲存**]。
    
## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>建立、 編輯或移除群組使用遠端 Windows PowerShell

本節提供建立群組，並使用遠端 Windows PowerShell 來變更其內容的相關資訊。 它也會顯示如何移除現有的群組。 
  
 **若要建立群組使用遠端 Windows PowerShell**
  
本範例會使用[New-eopdistributiongroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx)指令程式來建立通訊群組別名為 itadmin 與名稱 IT 系統管理員。 它也會新增為群組的成員的使用者。 
  
```Powershell
New-EOPDistributionGroup -Type "Distribution" -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy "Member1"

```

若要建立安全性群組，而不是通訊群組，請指定`-Type "Security"`改為。 
  
若要確認您是否已成功建立 IT Administrators 群組，請執行[Get-recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx)指令程式，來顯示新群組的相關資訊： 
  
```Powershell
Get-Recipient "IT Administrators" | Format-List

```

若要取得成員的清單中的群組，請執行[Get-distributiongroupmember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx)指令程式，如下所示： 
  
```Powershell
Get-DistributionGroupMember "IT Administrators"

```

若要取得所有群組的完整清單，請執行[Get-recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx)指令程式，如下所示： 
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | FT | more

```

 **若要變更的群組使用遠端 Windows PowerShell 屬性**
  
使用[Get-recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx)和[Set-eopdistributiongroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx)指令程式來檢視和變更群組的內容。 使用遠端 PowerShell，而不 EAC 的優點是能夠變更多個群組的屬性。 
  
以下是使用遠端 Windows PowerShell 變更群組屬性的一些範例。
  
此範例使用[Set-eopdistributiongroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx)指令程式來變更為 sea.employees@contoso.com 的主要 SMTP 位址 （也稱為 「 回覆地址） 將 Seattle Employees 群組。 
  
```Powershell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"

```

若要確認您已成功變更群組的內容，請使用[Get-recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx)指令程式來驗證變更。 使用遠端 PowerShell 的其中一個優勢是，您可以檢視多個群組的多個屬性。 在前一個範例中變更主要 SMTP 地址，群組的位置，請執行下列命令，以驗證新值： 
  
```Powershell
Get-Recipient "Seattle Employees" | FL "PrimarySmtpAddress"

```

本範例會使用[更新 EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx)指令程式來更新所有將 Seattle Employees 群組的成員。 使用逗點分隔的所有成員。 
  
```Powershell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")

```

若要取得 Seattle Employees 群組中的所有成員的清單，請使用[Get-distributiongroupmember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx)指令程式，如下所示： 
  
```Powershell
Get-DistributionGroupMember "Seattle Employees"

```

 **若要移除群組使用遠端 Windows PowerShell**
  
此範例使用[Remove-eopdistributiongroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx)指令程式來移除名為 IT 系統管理員的通訊群組。 
  
```Powershell
Remove-EOPDistributionGroup -Identity "IT Administrators" 

```

若要確認已移除群組，請執行[Get-recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx)指令程式，如下所示，並確認已刪除群組 （在此情況下"It Administrators"）。 
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"

```


