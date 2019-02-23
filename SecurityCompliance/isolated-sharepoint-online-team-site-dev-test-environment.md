---
title: 獨立的 SharePoint Online 小組網站開發/測試環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 摘要：設定 SharePoint Online 小組網站，該網站與 Office 365 開發/測試環境中組織的其他網站隔離。
ms.openlocfilehash: a8a02c10f799b136b299801a3636820e4f64e087
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217133"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>獨立的 SharePoint Online 小組網站開發/測試環境

 **摘要：** 設定 SharePoint Online 小組網站，該網站與 Office 365 開發/測試環境中組織的其他網站隔離。
  
在 Office 365 中的 SharePoint Online 小組網站都是使用一般的文件庫、 OneNote 筆記本，以及其他服務的共同作業的位置。在許多情況下，您跨部門或組織要寬存取及共同作業。不過，在某些情況下，您想要緊密控制存取及一小群人員之間的共同作業的權限。
  
由 SharePoint 群組與權限層級控制存取 SharePoint Online 小組網站與使用者可以執行的動作。根據預設，SharePoint Online 網站會有三種存取層級：
  
- **成員**，該使用者可以檢視、建立及修改網站上的資源。
    
- **擁有者**，該使用者擁有網站的完整控制權，包括變更權限的能力。
    
- **訪客**，該使用者只能夠檢視網站上的資源。
    
本文章步驟您完成秘密研究專案隔離 SharePoint Online 小組網站的設定名為 ProjectX。存取需求是：
  
- 只有專案的成員才能夠存取網站及其內容 (文件、OneNote 筆記本、頁面)，編輯和檢視 SharePoint 權限層級是透過群組成員資格進行控制的。
    
- 只有網站建立者和網站的 Admins 群組成員可以執行網站管理，包括修改網站層級權限。
    
在您的 Office 365 開發/測試環境中設定隔離的 SharePoint Online 小組網站有三個階段：
  
1. 建立 Office 365 開發/測試環境。

    
2. 為 ProjectX 建立使用者和群組。
    
3. 建立新的 ProjectX SharePoint Online 小組網站並且隔離它。
    
> [!TIP]
> 按一下[這裡](http://aka.ms/catlgstack)，可查看 One Microsoft Cloud 測試實驗室指南堆疊中文件的所有視覺對應。
  
## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-office-365-devtest-environment"></a>階段 1：建置輕量型或模擬的企業 Office 365 開發/測試環境

如果您只是要建立的最低需求的輕量型方式隔離的 SharePoint Online 小組網站，請在階段 2 和 3 的[Office 365 開發人員/測試環境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)中遵循的指示。
  
如果您想要建立隔離的 SharePoint Online 小組網站中的模擬的企業設定，請遵循[DirSync Office 365 開發人員/測試環境](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment)中的指示。
  
> [!NOTE]
> 建立隔離的 SharePoint Online 網站不需要模擬的企業開發/測試環境，其中包括模擬的內部網路 (連線到網際網路) 和 Windows Server AD 樹系中的目錄同步處理。它在這裡提供作為選項，讓您可以在代表典型組織的環境中測試建立隔離的 SharePoint Online 網站並且進行試驗。 
  
## <a name="phase-2-create-user-accounts-and-access-groups"></a>階段 2： 建立使用者帳戶並存取群組

使用[Connect to Office 365 PowerShell](https://technet.microsoft.com/library/dn975125.aspx)中的指示來連線至您的 Office 365 軌跡訂閱與您的全域管理員帳戶從：
  
- 您的電腦 (適用於輕量型 Office 365 開發/測試環境)。
    
- CLIENT1 虛擬機器 (適用於模擬的企業 Office 365 開發/測試環境)。
    
若要建立新的存取群組 ProjectX SharePoint Online 小組網站，請在 Windows Azure Active Directory Module for Windows PowerShell 提示字元處執行下列命令：
  
```
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

> [!TIP]
> 按一下[這裡](https://gallery.technet.microsoft.com/PowerShell-commands-for-an-b2608df1)包含所有的 PowerShell 命令會在本文中的文字檔案。
  
填入您的組織名稱 (範例︰contosotoycompany)，位置的兩個字元國家/地區代碼，再從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰
  
```
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

從 **New-MsolUser** 命令的顯示畫面中，記下針對 Lead Designer 帳戶產生的密碼，並且將密碼記錄在安全的位置。
  
從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰
  
```
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

從 **New-MsolUser** 命令的顯示畫面中，記下針對 Lead Researcher 帳戶產生的密碼，並且將密碼記錄在安全的位置。
  
從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰
  
```
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

從 **New-MsolUser** 命令的顯示畫面中，記下針對 Development VP 帳戶產生的密碼，並且將密碼記錄在安全的位置。
  
下一步] 將帳戶新增至新的存取群組，請從 Windows Azure Active Directory Module for Windows PowerShell 提示字元下執行下列 PowerShell 命令：
  
```
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

結果：
  
- ProjectX 成員存取群組包含導致設計工具] 和 [導致研究者使用者帳戶
    
- ProjectX 系統管理員存取群組包含您的試用版訂閱的全域管理員帳戶
    
- ProjectX 檢視者存取群組包含開發 VP 使用者帳戶
    
圖 1 顯示的存取群組和其成員資格。
  
**圖 1**

![獨立的 SharePoint Online 群組網站的 Office 365 群組及其成員資格](media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)
  
## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>階段 3：建立新的 ProjectX SharePoint Online 小組網站並且隔離它

若要為 ProjectX 建立 SharePoint Online 小組網站，請執行下列操作：
  
1. 在 [您的本機電腦 （輕量級的設定） 使用瀏覽器或在 CLIENT1 上 （模擬的企業組態） 登入 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 使用全域管理員帳戶。
    
2. 在磚清單中，按一下 [SharePoint]****。
    
3. 在 [新增 SharePoint] 索引標籤在瀏覽器中按一下 [ **+ 建立網站**。
    
4. 在**小組網站名稱**] 中輸入**ProjectX**。**隱私權設定**] 中選取 [**私人-只有成員可以存取此站台**。
    
5. 在**小組網站描述**] 中，輸入**SharePoint 網站的 ProjectX**]，然後按 [**下一步**。
    
6. 在**您要新增誰**？] 窗格中，按一下 [**完成]**。
    
7. 在瀏覽器中的 [工具] 列中新的**ProjectX 首頁**] 索引標籤上按一下 [設定] 圖示，和 [**網站權限**。
    
8. 在 [網站權限]**** 窗格中，按一下 [進階權限設定]****。
    
9. 在新**權限： X 專案**在瀏覽器] 索引標籤中按一下 [**存取要求的設定**。
    
10. **存取要求設定**] 對話方塊中，清除 [**允許成員] 共用網站和個別的檔案及資料夾**並**允許存取權要求**（使已取消選取所有的三個核取方塊），然後按一下 [**確定]**。
    
11. 清單中的 [ **ProjectX 成員**。
    
12. 在 [人員與群組]**** 頁面上，按一下 [新增]****。
    
13. 在 [**共用**] 對話方塊中，輸入**ProjectX 成員**、 選取它，，然後按一下 [**共用**]。
    
14. 按一下瀏覽器上的 [上一頁] 按鈕。
    
15. 按一下 [ **ProjectX 擁有者**] 清單中。
    
16. 在 [人員與群組]**** 頁面上，按一下 [新增]****。
    
17. 在 [**共用**] 對話方塊中，輸入**ProjectX Admins**、 選取它，，然後按一下 [**共用**。
    
18. 按一下瀏覽器上的 [上一頁] 按鈕。
    
19. 按一下 [ **ProjectX 訪客**] 清單中。
    
20. 在 [人員與群組]**** 頁面上，按一下 [新增]****。
    
21. 在 [**共用**] 對話方塊中，輸入**ProjectX 檢視**、 選取它，，然後按一下 [**共用**。
    
22. 關閉瀏覽器中的 [**人員與群組**] 索引標籤、 按一下 [瀏覽器上**ProjectX 常用**] 索引標籤，然後關閉 [**網站權限**] 窗格。
    
以下是設定權限的結果：
  
- ProjectX 成員 SharePoint 群組包含只 ProjectX 成員存取群組 （其中包含只會導致設計工具] 和 [導致研究者使用者帳戶） 和 ProjectX 群組 （其中包含只有一個全域管理員使用者帳戶）。
    
- ProjectX 擁有者 SharePoint 群組包含只 ProjectX 系統管理員存取群組 （其中包含只有一個全域管理員使用者帳戶）。
    
- ProjectX 訪客 SharePoint 群組包含只 ProjectX 檢視者存取群組 （其中包含只有開發 VP 使用者帳戶）。
    
- 成員無法修改網站層級權限 (這個操作只能由 ProjectX-Admins 群組的成員完成)。
    
- 其他使用者帳戶無法存取網站或它的資源，或要求網站的存取權。
    
圖 2 顯示 SharePoint 群組及其成員資格。
  
**圖 2**

![獨立的 SharePoint Online 群組網站的 SharePoint Online 群組及其成員資格](media/595abff4-64f9-49de-a37a-c70c6856936b.png)
  
現在我們示範使用導致 Designer 使用者帳戶的存取：
  
1. 關閉瀏覽器上**ProjectX 常用**] 索引標籤，然後按一下 [在瀏覽器中的 [ **Microsoft Office Home** ] 索引標籤。
    
2. 按一下您的全域管理員名稱] 和 [**登出**。
    
3. 登入 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 使用導致 Designer 帳戶名稱和其密碼。
    
4. 在磚清單中，按一下 [SharePoint]****。
    
5. 在 [新**SharePoint** ] 索引標籤在瀏覽器在 [搜尋] 方塊中輸入**ProjectX**啟動搜尋] 及 [ **ProjectX**小組網站。您應該 ProjectX 小組網站的瀏覽器中看到新的索引標籤。
    
6. 按一下 [設定] 圖示。請注意是沒有**網站**權限] 選項。因為只有 ProjectX Admins 群組的成員可以修改在網站上的權限正確
    
7. 開啟 [記事本] 或您選擇的文字編輯器。
    
8. 複製 ProjectX 小組網站的 URL，並將它貼至記事本或文字編輯器中新的一行。
    
9. 在 [新**ProjectX 首頁**] 索引標籤在瀏覽器中按一下 [**文件**。
    
10. 複製 ProjectX 文件資料夾的 URL，並將它貼至記事本或文字編輯器中新的一行。
    
11. 在 [新**ProjectX 文件**] 索引標籤在瀏覽器中按一下 [**新 > Word 文件**。
    
12. **Word Online** ] 頁面中輸入一些文字、 等待以指出**儲存**] 和 [上一頁] 按鈕在瀏覽器中，然後重新整理] 頁面上的狀態。您應該會看見新**Document.docx** **文件**] 資料夾中。
    
13. 按一下 [ **Document.docx**文件的省略符號和 [**取得] 連結**。
    
14. 複製**共用 'Document.docx'** ] 對話方塊中的 URL 並將其貼上 [記事本] 或文字編輯器中，新增一行，然後關閉**共用 'Document.docx'** ] 對話方塊。
    
15. 關閉瀏覽器上的 [ **ProjectX 文件**及**SharePoint** ] 索引標籤，然後按一下 [ **Microsoft Office Home** ] 索引標籤。
    
16. 按一下 [**客戶販售 Designer**名稱] 和 [**登出**。
    
現在我們示範使用開發 VP 使用者帳戶的存取：
  
1. 登入 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 使用開發 VP 帳戶名稱和其密碼。
    
2. 在磚清單中，按一下 [SharePoint]****。
    
3. 在 [新**SharePoint** ] 索引標籤在瀏覽器在 [搜尋] 方塊中輸入**ProjectX**啟動搜尋] 及 [ **ProjectX**小組網站。您應該 ProjectX 小組網站的瀏覽器中看到新的索引標籤。
    
4. 按一下 [**文件**，然後按一下 [ **Document.docx**檔案。
    
5. 在瀏覽器中的 [ **Document.docx** ] 索引標籤中嘗試修改的文字。您應該會看到訊息表示**本文件是唯讀屬性。** 這被預期因為開發 VP 使用者帳戶只有網站檢視權限。
    
6. 關閉 [在瀏覽器中的 [ **Document.docx**、 **ProjectX 文件**和**SharePoint** ] 索引標籤。
    
7. 按一下 [ **Microsoft Office Home** ] 索引標籤、 [**開發 VP**名稱和 [**登出**。
    
現在我們示範沒有權限的使用者帳戶具有存取權：
  
1. 登入 Office 365 入口網站 ([https://portal.office.com](https://portal.office.com)) 使用的使用者 3 帳戶名稱和其密碼。
    
2. 在磚清單中，按一下 [SharePoint]****。
    
3. [新增**SharePoint** ] 索引標籤在瀏覽器中的搜尋方塊中輸入**ProjectX**並再啟動搜尋。您應該會看到郵件**Nothing 以下符合您的搜尋。**
    
4. 從 [記事本] 或文字編輯器開啟的執行個體，將 ProjectX 網站的 URL 複製到您的瀏覽器的位址列並按**Enter**。您應該會看到 **「 拒絕存取 」** 頁面。
    
5. 從 [記事本] 或文字編輯器，將 ProjectX 文件] 資料夾的 URL 複製到您的瀏覽器的位址列並按**Enter**。您應該會看到 **「 拒絕存取 」** 頁面。
    
6. 從 [記事本] 或文字編輯器，將 Documents.docx 檔案的 URL 複製到您的瀏覽器的位址列並按**Enter**。您應該會看到 **「 拒絕存取 」** 頁面。
    
7. 關閉瀏覽器中的 [ **SharePoint** ] 索引標籤、 [ **Microsoft Office Home** ] 索引標籤、 [**使用者 3**的名稱，和 [**登出**。
    
隔離的 SharePoint Online 網站現在已備妥可供您其他試驗。
  
## <a name="next-step"></a>下一步

當您準備好要在生產環境中部署獨立的 SharePoint Online 小組網站時，請參閱＜[設計獨立的 SharePoint Online 小組網站](design-an-isolated-sharepoint-online-team-site.md)＞中的逐步設計考量。
  
## <a name="see-also"></a>另請參閱

[獨立的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)。
  
[雲端採用測試實驗室指南 (TLG)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[基底組態開發/測試環境](https://docs.microsoft.com/office365/enterprise/base-configuration-dev-test-environment)
  
[Office 365 開發/測試環境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)
  
[雲端採用和混合式解決方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




