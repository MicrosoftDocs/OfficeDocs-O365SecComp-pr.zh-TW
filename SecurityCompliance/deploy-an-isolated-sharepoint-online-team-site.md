---
title: 部署隔離的 SharePoint Online 小組網站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 摘要： 部署新隔離的 SharePoint Online 小組網站與這些逐步指示。
ms.openlocfilehash: d233ec46b1e7257a92451c781afd6c61312f44b8
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345975"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>部署隔離的 SharePoint Online 小組網站

 **摘要：** 部署新隔離的 SharePoint Online 小組網站與這些逐步指示。
  
本文是建立及設定 Microsoft Office 365 中隔離的 SharePoint Online 小組網站的逐步說明部署指南 》。這些步驟假設使用三個預設 SharePoint 群組及對應的權限層級、 與每個存取層級單一 Azure Active Directory AD 型的存取群組。
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>階段 1： 建立並填入小組網站的存取群組

在此階段中，您建立三個 Azure AD 式存取群組之三個預設 SharePoint 群組，並填入適當的使用者帳戶。
  
> [!NOTE]
> 下列步驟假設的所有必要的使用者帳戶已存在且已指派適當的授權。如果不使用，請將其新增並指派授權再繼續進行至步驟 1。 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>步驟 1： 列出網站的 SharePoint Online 系統管理員

決定的使用者帳戶對應至隔離的小組網站的 SharePoint Online 系統管理員。
  
如果您正在管理使用者帳戶和群組透過 Office 365 並想要使用 Windows PowerShell，使其使用者清單主體名稱 (Upn) (範例 UPN: belindan@contoso.com)。
  
### <a name="step-2-list-the-members-for-the-site"></a>步驟 2： 列出網站的成員

決定一組使用者帳戶對應至將儲存在網站中的資源上共同作業的使用者可以隔離的小組網站的成員。
  
如果您正在管理使用者帳戶和群組透過 Office 365 並想要使用 PowerShell，使其 Upn 的清單。如果有許多網站成員的您可以儲存的 Upn 清單中的文字檔案並將其新增所有與單一 PowerShell 命令。
  
### <a name="step-3-list-the-viewers-for-the-site"></a>步驟 3： 列出之網站的檢視器

決定對應至隔離的小組網站的檢視器的使用者可以檢視儲存在網站中的資源，但不是修改其或直接在其內容進行共同作業的使用者帳戶的設定。
  
如果您正在管理使用者帳戶和群組透過 Office 365 並想要使用 PowerShell，使其 Upn 的清單。如果有許多網站成員的您可以儲存的 Upn 清單中的文字檔案並將其新增所有與單一 PowerShell 命令。
  
網站檢視者可能會包含 executive 管理、 法律顧問或是 inter-departmental 專案關係人。
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>步驟 4： 在 Azure AD 中建立網站的三種存取群組

您需要在 Azure AD 中建立下列存取群組：
  
- 網站管理員 （其中將包含從步驟 1 的清單）
    
- 網站成員 （其中將包含步驟 2 的清單）
    
- 網站檢視器 （其中將包含從步驟 3 的清單）
    
1. 在瀏覽器中移至 Azure 入口網站[https://portal.azure.com](https://portal.azure.com)並簽署的已指派與使用者管理管理員或公司管理員角色的帳戶認證。
    
2. 在 Azure 入口網站中，按一下 [Azure Active Directory] > [群組]****。
    
3. 在 [群組 - 所有群組]**** 刀鋒視窗中，按一下 [+ 新增群組]****。
    
4. 在 [群組]**** 刀鋒視窗中：
    
  - 選取 [群組類型]**** 中的 [Office 365]****。
    
  - **名稱**] 中輸入群組名稱。
    
  - 在 [**群組描述**輸入群組的描述。
    
  - 在 [成員資格類型]**** 中選取 [已指派]****。
    
5. 按一下 [建立]****，然後關閉 [群組]**** 刀鋒視窗。
    
6. 針對您的其他群組重複步驟 3-5。
    
> [!NOTE]
> 您需要使用 Azure 入口網站來建立的群組，讓他們有啟用 Office 功能。SharePoint Online 的隔離的網站稍後會設定為具有加密檔案並將權限指派給特定群組 Azure 資訊保護 (AIP) 標籤的高度機密網站中，如果允許的群組必須已建立以 Office 功能啟用。您不能變更 Office 功能的設定 Azure AD 群組之後已建立。 
  
以下是三個網站存取群組與您所產生的設定。
  
![用於部署隔離之 SharePoint Online 網站的三個存取群組。](media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>步驟 5。將使用者帳戶新增至 access 群組

在此步驟中，執行下列動作：
  
1. 步驟 1 的使用者清單新增至網站管理員存取群組
    
2. 步驟 2 的使用者清單新增至網站成員存取群組
    
3. 步驟 3 中的使用者清單新增至網站檢視者存取群組
    
如果您正在管理使用者帳戶及 Windows Server AD 透過群組，將使用者新增到適當的存取群組使用標準的 Windows Server AD 使用者和群組管理程序，並等待與您的 Office 365 訂閱進行同步處理。
  
如果您正在管理使用者帳戶和群組透過 Office 365，您可以使用 Office 系統管理中心或 PowerShell。如果您有任何存取群組重複的群組名稱，您應該使用在 Office 系統管理中心。
  
針對 Office 系統管理中心中，使用已指派之使用者帳戶系統管理員或公司管理員角色的使用者帳戶登入並使用將適當的使用者帳戶新增群組和適當的存取群組的群組。
  
Powershell，第一個[連接使用 Azure Active Directory V2 PowerShell 模組](https://go.microsoft.com/fwlink/?linkid=842218)。
  
接下來，使用下列的命令區塊將個別使用者帳戶新增至 access 群組：
  
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> 包含所有的 PowerShell 命令與 Excel 的文字檔案的 PowerShell 命令將會產生的設定工作表根據您的群組和使用者帳戶名稱、 下載[隔離 SharePoint Online 小組網站部署套件 （英文)](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907)。 
  
如果您儲存的任何存取群組的使用者帳戶的 Upn 中的文字檔案時，您可以使用下列 PowerShell 命令區塊以將其新增到一次：
  
```
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

PowerShell 中使用下列的命令區塊將個別群組新增至 access 群組：
  
```
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

結果應該為下列各項：
  
- 網站管理員 Azure AD 群組包含的網站管理員的使用者帳戶或群組
    
- 網站成員 Azure AD 群組包含的網站成員使用者帳戶或群組
    
- 網站檢視者 Azure AD 群組包含使用者帳戶或僅可檢視網站內容的群組
    
驗證每個存取群組與 Office 系統管理中心和下列 PowerShell 命令區塊的群組成員的清單：
  
```
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

以下是您所產生的設定與三個網站存取群組填入使用者帳戶或群組。
  
![三個存取群組填寫了使用者帳戶。](media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>階段 2： 建立及設定隔離的小組網站

在此階段中，您可以建立的隔離的 SharePoint Online 網站及設定的預設 SharePoint Online 權限等級以使用新的 Azure AD 式存取群組的權限。
  
首先，建立 SharePoint Online 小組網站進行這些步驟。
  
1. 使用也可用來管理 SharePoint Online 小組網站的帳戶 (SharePoint Online 系統管理員) 登入 Office 365 入口網站。 如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 在磚清單中，按一下 [SharePoint]****。
    
3. 在新的 [SharePoint] **** 瀏覽器索引標籤中，按一下 [+ 建立網站]****。
    
4. 在 [建立網站]**** 頁面上，按一下 [小組網站]****。
    
5. 在**站台名稱**] 中輸入小組網站的名稱。 
    
6. 在**小組網站描述] 中，** 輸入網站的用途的選用描述。
    
7. 在 [隱私權設定]**** 中，選取 [私人 - 只有成員可以存取此網站]****，然後按一下 [下一步]****。
    
8. 在 [您想要新增誰?]**** 窗格上，按一下 [完成]****。
    
新的 SharePoint Online 小組網站下, 一步] 設定的權限。
  
1. 在工具列中，按一下設定圖示，然後按一下 [網站權限]****。
    
2. 在 [網站權限]**** 窗格中，按一下 [進階權限設定]****。
    
3. 在新的 [權限]**** 瀏覽器索引標籤中，按一下 [存取要求設定]****。
    
4. **存取要求設定**] 對話方塊中，清除 [**允許成員共用網站和個別的檔案及資料夾**，以及**允許存取權要求**（使已取消選取所有的三個核取方塊），然後按一下 [**確定]**。
    
5. 在瀏覽器中的 [**權限**] 索引標籤中，按一下 [**\<站台名稱 > 成員**清單中。
    
6. 在 [人員與群組]**** 中，按一下 [新增]****。
    
7. 在 [**共用**] 對話方塊中，輸入網站成員存取群組的名稱、 選取它，，然後按一下 [**共用**。
    
8. 按一下瀏覽器上的 [上一頁] 按鈕。
    
9. 按一下 [**\<站台名稱 > 擁有者**清單中。
    
10. 在 [人員與群組]**** 中，按一下 [新增]****。
    
11. 在 [**共用**] 對話方塊中，輸入網站管理員存取群組的名稱、 選取它，，然後按一下 [**共用**。
    
12. 按一下瀏覽器上的 [上一頁] 按鈕。
    
13. 按一下 [**\<站台名稱 > 訪客**清單中。
    
14. 在 [人員與群組]**** 中，按一下 [新增]****。
    
15. 在 [**共用**] 對話方塊中，輸入網站檢視者存取群組的名稱、 選取它，，然後按一下 [**共用**。
    
16. 關閉 [權限]**** 瀏覽器索引標籤。
    
這些權限設定的結果是：
  
- **\<站台名稱 > 擁有者**SharePoint 群組包含網站管理員存取群組中的所有成員具有 [**完全控制**」 權限層級。
    
- **\<站台名稱 > 成員**SharePoint 群組包含網站成員存取群組，其中的所有成員擁有 「**編輯**」 權限層級。
    
- **\<站台名稱 > 訪客**SharePoint 群組包含網站檢視者存取群組中的所有成員具有 「**讀取**」 權限等級。
    
- 若要邀請其他成員的成員或非成員要求存取的功能已停用。
    
以下是您所產生的設定與網站設定成使用三個會填入使用者帳戶的存取群組或 Azure AD 群組的三種 SharePoint 群組。
  
![具有存取群組與使用者帳戶之隔離 SharePoint Online 網站的最後設定](media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
您與網站，透過群組成員資格之一的存取群組的成員可以立即共同作業網站的資源。
  
## <a name="next-step"></a>下一步

當您需要變更網站的存取群組成員資格或建立自訂的權限的文件資料夾時，請參閱[管理隔離的 SharePoint Online 小組網站](manage-an-isolated-sharepoint-online-team-site.md)。
  
## <a name="see-also"></a>另請參閱

[隔離的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)。
  
[設計獨立的 SharePoint Online 小組網站](design-an-isolated-sharepoint-online-team-site.md)
  
[管理獨立的 SharePoint Online 小組網站](manage-an-isolated-sharepoint-online-team-site.md)
  



