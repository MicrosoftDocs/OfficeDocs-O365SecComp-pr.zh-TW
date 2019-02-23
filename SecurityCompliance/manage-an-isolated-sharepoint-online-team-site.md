---
title: 管理獨立的 SharePoint Online 小組網站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 摘要： 管理隔離這些程序與 SharePoint Online 小組網站。
ms.openlocfilehash: 81a6fcd80bb3e4950eb7b783d1ad964b9bc67cc5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214483"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>管理獨立的 SharePoint Online 小組網站

 **摘要：** 管理隔離這些程序與 SharePoint Online 小組網站。
  
本文說明隔離的 SharePoint Online 小組網站的一般管理作業。
  
## <a name="add-a-new-user"></a>將新使用者

當某人新加入的網站時，您必須決定其參與網站層級：
  
- 管理： 將新的使用者帳戶新增至網站管理員存取群組
    
- 作用中的共同作業： 將使用者帳戶新增至網站成員存取群組
    
- 檢視： 將使用者帳戶新增至網站檢視者存取群組
    
如果您正在管理使用者帳戶和群組透過 Windows Server Active Directory (AD)，將適當的使用者新增至您一般 Windows Server AD 使用者和群組管理程序的適當存取群組並等候同步處理您Office 365 訂閱。
  
如果您正在管理使用者帳戶和群組透過 Office 365，您可以使用 Office 系統管理中心或 Microsoft PowerShell：
  
- 針對 Office 系統管理中心中，使用已指派之使用者帳戶系統管理員或公司管理員角色的使用者帳戶登入並使用群組將適當的使用者新增至適當的存取群組。
    
- Powershell，第一個[連接使用 Azure Active Directory V2 PowerShell 模組](https://go.microsoft.com/fwlink/?linkid=842218)。若要將使用者帳戶新增至其使用者主體名稱 (UPN) 的存取群組，使用下列 PowerShell 命令區塊：
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> 包含所有的 PowerShell 命令與 Excel 的文字檔案的 PowerShell 命令將會產生的設定工作表根據您的群組和使用者帳戶名稱、 下載[隔離 SharePoint Online 小組網站部署套件 （英文)](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907)。 

若要將使用者帳戶新增至其顯示名稱的存取群組，使用下列 PowerShell 命令區塊：

```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>新增新的群組

若要新增至整個群組的存取，您必須決定網站中的群組所有成員的參與的層級：
  
- 管理： 將群組新增至網站管理員存取群組
    
- 作用中的共同作業： 將群組新增至網站成員存取群組
    
- 檢視： 將群組新增至網站檢視者存取群組
    
如果您正在管理使用者帳戶及 Windows Server AD 透過群組，將適當的群組新增至適當的群組使用標準的 Windows Server AD 使用者和群組管理程序，並等待與您的 Office 365 訂閱進行同步處理。
  
如果您正在管理使用者帳戶和群組透過 Office 365，您可以使用 Office 系統管理中心或 PowerShell：
  
- 針對 Office 系統管理中心中，使用已指派之使用者帳戶系統管理員或公司管理員角色的使用者帳戶登入並使用群組將適當的群組新增至適當的存取群組。
    
- Powershell，第一個[連接使用 Azure Active Directory V2 PowerShell 模組](https://go.microsoft.com/fwlink/?linkid=842218)。然後，使用下列 PowerShell 命令：
 
```
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>移除使用者

當某個人的存取必須從網站移除時，您移除它們從其目前成員的根據他們參與網站的存取群組：
  
- 管理： 移除從網站管理員存取群組的使用者帳戶
    
- 作用中的共同作業： 移除從網站成員存取群組的使用者帳戶
    
- 檢視： 移除從網站檢視者存取] 群組中的使用者帳戶
    
如果您正在管理使用者帳戶和群組透過 Windows Server AD，移除使用標準的 Windows Server AD 使用者和群組管理程序的適當存取群組中的適當的使用者並等候與您的 Office 365 進行同步處理訂閱。
  
如果您正在管理使用者帳戶和群組透過 Office 365，您可以使用 Office 系統管理中心或 PowerShell：
  
- 針對 Office 系統管理中心中，使用已指派之使用者帳戶系統管理員或公司管理員角色的使用者帳戶登入並使用群組移除適當的存取群組中的適當的使用者。
    
- Powershell，第一個[連接使用 Azure Active Directory V2 PowerShell 模組](https://go.microsoft.com/fwlink/?linkid=842218)。若要從其 upn 的存取群組移除使用者帳戶，請使用下列 PowerShell 命令區塊：
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

若要從其顯示名稱的存取群組移除使用者帳戶，請使用下列 PowerShell 命令區塊：
    
```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>移除群組

若要移除整個群組存取權，您從其目前成員的根據他們參與網站存取群組中移除群組：
  
- 管理： 移除網站管理員存取群組的群組
    
- 作用中的共同作業： 移除從網站成員存取群組的群組
    
- 檢視： 移除網站檢視者存取群組的群組
    
如果您正在管理使用者帳戶及透過 Windows Server Active Directory 群組，從您一般 Windows Server AD 使用者和群組管理程序的適當存取群組中移除適當的群組，並等待同步處理您Office 365 訂閱。
  
如果您正在管理使用者帳戶和群組透過 Office 365，您可以使用 Office 系統管理中心或 PowerShell：
  
- 針對 Office 系統管理中心中，使用已指派之使用者帳戶系統管理員或公司管理員角色的使用者帳戶登入並使用群組移除適當的存取群組中的適當的群組。
    
- Powershell，第一個[連接使用 Azure Active Directory V2 PowerShell 模組](https://go.microsoft.com/fwlink/?linkid=842218)。    
若要使用其顯示名稱的存取群組中移除群組，請使用下列 PowerShell 命令區塊：
    
```
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>使用自訂權限建立文件的子資料夾

在某些情況下，使用隔離的站台內的人員的子集需要更多私人的位置進行共同作業。SharePoint Online 網站，您可以在站台的文件] 資料夾中建立子資料夾及指派自訂權限。這些權限而不會看到子資料夾。
  
若要建立的自訂權限的文件子資料夾，請執行下列動作：
  
1. 以屬於 admins 存取網站群組的成員帳戶登入 Office 365。為了協助，請參閱 ＜[登入 Office 365 的位置](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 移至隔離的小組網站並按一下 [**文件**。
    
3. 瀏覽至將包含具有自訂的權限的子資料夾、 建立資料夾，並加以開啟的文件] 資料夾中的資料夾。
    
4. 按一下 **[共用]**。
    
5. 按一下 [**與 > 進階共用**]。
    
6. 按一下 [**停止繼承權限**] 和 [**確定]**。
    
7. 按一下 **[共用]**。
    
8. 按一下 [**與 > 進階共用**]。
    
9. 按一下 [**授與權限 > 與 > 進階共用**]。
    
10. 在 [權限] 頁面上，按一下 [**\<網站清單中的 name> 成員**。
    
11. 在**\<網站 name> 成員**] 頁面上、 選取網站成員存取群組旁邊的核取記號表示、 按一下 [**動作]**、 按一下 [**移除從群組中的使用者**，然後按一下 [**確定]**。
    
12. 特定成員新增到這個子資料夾中，按一下 [**新 > 新增使用者**]。
    
13. 在 [**共用**] 對話方塊中，輸入可以共同作業的子資料夾中的檔案，然後按一下 [**共用**的使用者帳戶的名稱。
    
14. 重新整理 web 頁面才能看見新的結果。
    
15. [**群組**的左方導覽中，按一下 [**\<網站 name> 訪客**群組及使用步驟 11 14 指定可以檢視中的檔案的子資料夾 （視） 的使用者帳戶的設定。
    
16. [**群組**的左方導覽中，按一下 [**\<網站 name> 擁有者**群組及使用步驟 11 14 指定 （視） 可以管理子資料夾中的權限的使用者帳戶的設定。
    
17. 關閉瀏覽器中的 [**人員與群組**] 索引標籤。
    
## <a name="see-also"></a>另請參閱

[獨立的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)。
  
[設計獨立的 SharePoint Online 小組網站](design-an-isolated-sharepoint-online-team-site.md)

[部署獨立的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)



