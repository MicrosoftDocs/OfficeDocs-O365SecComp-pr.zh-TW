---
title: 部署獨立的 SharePoint Online 小組網站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 摘要： 部署新隔離的 SharePoint Online 小組網站與這些逐步指示。
ms.openlocfilehash: 4cb60cd55f526592cb469d80a061375a4f556afe
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257000"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>部署獨立的 SharePoint Online 小組網站

 **摘要：** 部署新隔離的 SharePoint Online 小組網站，這些逐步指示。
  
本文適用於建立與 Microsoft Office 365 中設定隔離的 SharePoint Online 小組網站的逐步部署指南 》。 這些步驟假設使用三個預設 SharePoint 群組和對應的權限層級，與每個層級的存取權的單一的 Azure Active Directory AD 存取群組。
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>階段 1： 建立並填入小組網站存取群組

在這個階段，您會建立三個預設 SharePoint 群組的三個 Azure AD 為基礎的存取群組，並填入適當的使用者帳戶。
  
> [!NOTE]
> 下列步驟假設所有必要的使用者帳戶已存在，並指派適當的授權。 如果沒有，請將它們新增，並指派授權，繼續進行步驟 1。 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>步驟 1： 將網站的 SharePoint Online 系統管理員

決定的使用者帳戶對應至隔離的小組網站的 SharePoint Online 系統管理員。
  
如果您正在管理使用者帳戶和透過 Office 365 群組，並想要使用 Windows PowerShell，建立一份其使用者主體名稱 (Upn) (範例 UPN: belindan@contoso.com)。
  
### <a name="step-2-list-the-members-for-the-site"></a>步驟 2： 將網站成員

決定一組使用者帳戶對應至隔離的小組網站，使用者將會儲存在網站內的資源上共同作業的成員。
  
如果您正在管理使用者帳戶和透過 Office 365 群組，而且想要使用 PowerShell，請他們的 Upn 清單。 如果有很多網站成員，您可以在文字檔中儲存的 Upn 清單，並將其新增所有與單一 PowerShell 命令。
  
### <a name="step-3-list-the-viewers-for-the-site"></a>步驟 3： 將網站檢視者

決定對應至檢視隔離的小組網站，使用者可以檢視儲存在網站中的資源，但不是需要修改或直接在其內容進行共同作業的使用者帳戶的集合。
  
如果您正在管理使用者帳戶和透過 Office 365 群組，而且想要使用 PowerShell，請他們的 Upn 清單。 如果有很多網站成員，您可以在文字檔中儲存的 Upn 清單，並將其新增所有與單一 PowerShell 命令。
  
行政人員管理、 法律顧問或是 inter-departmental 專案關係人，可能包含網站檢視者。
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>步驟 4： 在 Azure AD 中建立三個存取群組網站

您必須在 Azure AD 中建立下列存取群組：
  
- 網站管理員 （其會包含從步驟 1 的清單）
    
- 網站成員 （其會包含在步驟 2 的清單）
    
- 網站檢視者 （其會包含清單中的，從步驟 3）
    
1. 在瀏覽器中，移至 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)並以已指派使用者管理系統管理員或公司系統管理員角色與帳戶的認證登入。
    
2. 在 Azure 入口網站中，按一下 [Azure Active Directory] > [群組]****。
    
3. 在 [群組 - 所有群組]**** 刀鋒視窗中，按一下 [+ 新增群組]****。
    
4. 在 [群組]**** 刀鋒視窗中：
    
  - 選取 [群組類型]**** 中的 [Office 365]****。
    
  - 在 [**名稱]** 中輸入群組名稱。
    
  - 在 [**群組描述**輸入群組的描述。
    
  - 在 [成員資格類型]**** 中選取 [已指派]****。
    
5. 按一下 [建立]****，然後關閉 [群組]**** 刀鋒視窗。
    
6. 針對其他群組重複步驟 3-5。
    
> [!NOTE]
> 您需要使用 Azure 入口網站來建立群組，以便他們有啟用 Office 功能。 如果 SharePoint Online 隔離的網站稍後再設定為具有加密檔案並將權限指派給特定群組的 Azure 資訊保護標籤的高度機密網站時，必須允許的群組已建立啟用 Office 功能。 已建立之後，您無法變更的 Azure AD 群組的 Office 功能設定。 
  
以下是三個網站存取群組與您產生的組態。
  
![三個存取群組的隔離 SharePoint Online 網站部署。](media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>步驟 5。 將使用者帳戶新增至 access 群組

在此步驟中，執行下列動作：
  
1. 步驟 1 中的使用者清單新增至網站系統管理員存取群組
    
2. 步驟 2 中加入網站成員存取群組的使用者清單
    
3. 步驟 3 中的使用者清單新增至網站檢視者存取群組
    
如果您要管理使用者帳戶和透過 Windows Server AD 群組，將使用者新增至適當的存取群組使用標準的 Windows Server AD 使用者和群組管理程序，並等待同步處理您的 Office 365 訂閱。
  
如果您要管理使用者帳戶和群組透過 Office 365，您可以使用 Office 系統管理中心或 PowerShell。 如果您有任何一個存取群組重複群組名稱，您應該使用 Office 系統管理中心。
  
針對 Office 系統管理中心中，使用已被指派的使用者帳戶系統管理員或公司系統管理員角色的使用者帳戶登入並使用群組，以新增適當的使用者帳戶和群組，以適當的存取群組。
  
Powershell 中，第一個[與 PowerShell 的 Azure Active Directory 針對 Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
接下來，使用下列命令區塊，將個別使用者帳戶新增至 access 群組：
  
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> 文字檔案，其中包含所有 PowerShell 命令和 Excel PowerShell 命令將會產生的組態工作表的群組和使用者帳戶名稱，請下載[隔離 SharePoint Online 小組網站部署套件](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907)。 
  
如果您儲存 upn 的任何一個存取群組的使用者帳戶，請在文字檔案中，您可以使用下列 PowerShell 命令區塊，將它們新增一次：
  
```
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

PowerShell 中，使用下列命令區塊，將個別的群組新增至 access 群組：
  
```
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

結果應為下列各項：
  
- 網站管理員 Azure AD 群組包含網站系統管理員使用者帳戶或群組
    
- 網站成員 Azure AD 群組包含網站成員的使用者帳戶或群組
    
- 網站檢視者 Azure AD 群組包含使用者帳戶或群組，僅可檢視網站內容
    
驗證與 Office 系統管理中心或使用下列 PowerShell 命令區塊，每個存取群組的群組成員的清單：
  
```
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

以下是三個網站存取群組填寫了使用者帳戶或群組具有您產生的組態。
  
![三個存取群組填寫了使用者帳戶。](media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>階段 2： 建立及設定隔離的小組網站

在這個階段，您可以建立隔離的 SharePoint Online 網站，並設定以使用新的 Azure AD 為基礎的存取群組的預設 SharePoint Online 權限層級的權限。
  
首先，使用下列步驟建立 SharePoint Online 小組網站。
  
1. 使用也可用來管理 SharePoint Online 小組網站的帳戶 (SharePoint Online 系統管理員) 登入系統管理中心。 如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 在磚清單中，按一下 [SharePoint]****。
    
3. 在新的 [SharePoint] **** 瀏覽器索引標籤中，按一下 [+ 建立網站]****。
    
4. 在 [建立網站]**** 頁面上，按一下 [小組網站]****。
    
5. 在 [**網站名稱**] 中，輸入小組網站的名稱。 
    
6. 在 [**小組網站描述] 中，** 鍵入網站用途的選用描述。
    
7. 在 [隱私權設定]**** 中，選取 [私人 - 只有成員可以存取此網站]****，然後按一下 [下一步]****。
    
8. 在 [您想要新增誰?]**** 窗格上，按一下 [完成]****。
    
接下來，從新的 SharePoint Online 小組網站，設定權限。
  
1. 在工具列中，按一下設定圖示，然後按一下 [網站權限]****。
    
2. 在 [網站權限]**** 窗格中，按一下 [進階權限設定]****。
    
3. 在新的 [權限]**** 瀏覽器索引標籤中，按一下 [存取要求設定]****。
    
4. 在 [**存取要求設定**] 對話方塊中，清除 [**允許成員共用網站以及個別檔案和資料夾**，以及**允許存取權要求**（使所有三個核取方塊皆已取消），然後按一下 [**確定]**。
    
5. 在瀏覽器的 [**權限**] 索引標籤中，按一下 [**\<網站 name> 成員**清單中。
    
6. 在 [人員與群組]**** 中，按一下 [新增]****。
    
7. 在 [**共用**] 對話方塊中，輸入網站成員存取群組的名稱、 選取它，，然後按一下 [**共用**。
    
8. 按一下瀏覽器上的 [上一頁] 按鈕。
    
9. 按一下 [**\<網站 name> 擁有者**清單中。
    
10. 在 [人員與群組]**** 中，按一下 [新增]****。
    
11. 在 [**共用**] 對話方塊中，輸入網站系統管理員存取群組的名稱、 加以選取，，然後按一下 [**共用**]。
    
12. 按一下瀏覽器上的 [上一頁] 按鈕。
    
13. 按一下 [**\<網站 name> 訪客**清單中。
    
14. 在 [人員與群組]**** 中，按一下 [新增]****。
    
15. 在 [**共用**] 對話方塊中，輸入網站檢視者存取群組的名稱、 加以選取，，然後按一下 [**共用**]。
    
16. 關閉 [權限]**** 瀏覽器索引標籤。
    
這些權限設定的結果是：
  
- **\<網站 name> 擁有者**SharePoint 群組包含網站管理員存取群組，所有成員都具有 [**完全控制**」 權限等級。
    
- **\<網站 name> 成員**SharePoint 群組包含網站成員存取群組，其中的所有成員都具有 [**編輯**權限等級。
    
- **\<網站 name> 訪客**SharePoint 群組包含網站檢視者存取群組，其中的所有成員都具有 [**讀取**權限等級。
    
- 成員邀請其他成員或非成員要求存取的功能已停用。
    
以下是您產生的組態與設定成使用三個存取群組，填寫了使用者帳戶或 Azure AD 群組網站的三個 SharePoint 群組。
  
![最終組態的隔離 SharePoint Online 網站的存取群組與使用者帳戶。](media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
您和網站，透過在存取群組，其中的群組成員資格的成員可以立即共同作業網站的資源。
  
## <a name="next-step"></a>下一步

當您需要變更站台存取群組成員資格，或建立具有自訂權限的文件資料夾時，請參閱 <<c0>管理隔離的 SharePoint Online 小組網站。
  
## <a name="see-also"></a>另請參閱

[獨立的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)。
  
[設計獨立的 SharePoint Online 小組網站](design-an-isolated-sharepoint-online-team-site.md)
  
[管理獨立的 SharePoint Online 小組網站](manage-an-isolated-sharepoint-online-team-site.md)
  



