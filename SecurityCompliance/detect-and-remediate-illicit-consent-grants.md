---
title: 偵測並修復 Office 365 中的非法同意授權
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 4/23/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 了解如何辨識及修復 Office 365 中的非法同意授與攻擊。
ms.openlocfilehash: 1d8df4db94129bcdcb6ecf4859f9f89a1974edbe
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223352"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a>偵測並修復 Office 365 中的非法同意授權

**摘要** 了解如何辨識及修復 Office 365 中的非法同意授與攻擊。

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>什麼是 Office 365 中的非法同意授與攻擊？
非法同意中授與攻擊、 攻擊者會建立 Azure 登錄的應用程式的要求存取連絡人資訊、 電子郵件，例如資料或文件。攻擊者然後技巧 （英文) 使用者將授與該應用程式的同意存取其資料透過網路釣魚攻擊，或將非法程式碼插入的受信任的網站。非法應用程式已授與同意之後，它可以不需要組織帳戶的資料存取帳戶層級。由於這些是協力廠商應用程式與組織外部的破壞帳戶的密碼重設或需要多重要素驗證 (MFA) 上的帳戶的標準的補救步驟不這種類型的攻擊，有成效。這些攻擊利用假定為呼叫資訊的實體是自動化和不人力資源互動模型。

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>非法同意授與攻擊的外觀為何在 Office 365？
您需要搜尋 Office 365**稽核記錄**來尋找告示牌，也稱為指標的危害 (IOC) 這類攻擊。對於組織中具有許多 Azure 登錄的應用程式及大型使用者群、 最佳做法是檢閱您的組織同意授與每週為基礎。
### <a name="steps-for-finding-signs-of-this-attack"></a>用於搜尋的此跡象的步驟
1. 在您的 Office 365 租用戶中開啟的**安全性和規範中心 」** 。
2. 瀏覽至 [**搜尋 & 調查**] 節點並選取 [**稽核記錄**搜尋。
3. 建立搜尋 （所有活動和所有的使用者） 及篩選結果的同意應用程式，並新增 OAuth2PermissionGrant。
4. 檢查擴充屬性和] 核取以查看 IsAdminContent 是否設為 True。


如果這個值是 true，則表示某人全域管理員的存取權可能已授予廣泛存取資料。如果這是未預期，請執行步驟以[確認攻擊](detect-and-remediate-illicit-consent-grants.md#confirmattack)。

<a name="confirmattack"> </a>
## <a name="how-to-confirm-an-attack"></a>如何確認攻擊
如果您有一或多個執行個體 IOCs 上述，您需要執行動作進一步調查正面確認攻擊發生。您可以使用下列三種方法的任何確認攻擊。
- 庫存應用程式並使用 Azure Active Directory 入口網站及其權限。這個方法是充分的認知，但只能用來檢查一位使用者每次可以是很耗時如果您有許多使用者檢查。
- 庫存應用程式及使用 PowerShell 及其權限。這是最快和最徹底方法，以最少量的額外負荷。
- 讓您可以個別檢查其應用程式與的權限及結果回報修復的系統管理員的使用者。

## <a name="inventory-apps-with-access-in-your-organization"></a>在組織中的存取權的庫存應用程式
您可以執行這項作業的 Azure Active Directory 入口網站或 PowerShell 使用者或擁有個別列舉其應用程式存取您的使用者。

### <a name="steps-for-using-the-azure-active-directory-portal"></a>使用 Azure Active Directory 入口網站的步驟
您可以查詢的任何個別使用者授與權限使用[Azure Active Directory 入口網站](https://portal.azure.com/)的應用程式。 
1. 以系統管理權限 Azure 入口網站登入。
2. 選取 [Azure Active Directory blade。
3. 選取 [**使用者**]。
4. 選取您要檢閱的使用者。
5. 選取 [**應用程式**。

這會顯示指派給使用者和新的應用程式 applcations 具備的權限。

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>讓您的使用者的步驟列舉其應用程式的存取
讓您的使用者移至https://myapps.microsoft.com並檢閱那里其專屬應用程式存取。應該可以看到的存取權的所有應用程式、 檢視關於這些 （包括 access 的範圍） 的詳細資訊，且能夠撤銷可疑或非法應用程式的權限。

### <a name="steps-for-doing-this-with-powershell"></a>使用 PowerShell 中執行此步驟
若要確認非法同意授與攻擊的最簡單方式是執行[Get AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)，這會將傾印所有 OAuth 同意授與和 OAuth 應用程式的所有使用者在租用成一個.csv 檔案。 

#### <a name="pre-requisites"></a>先決條件
- Azure AD PowerShell 文件庫安裝。
- 將針對執行指令碼租用戶的全域系統管理員權限。
- 所在之電腦上的本機系統管理員會執行指令碼。

> [!IMPORTANT]
> 我們強烈建議您在您的系統管理帳戶需要多重要素驗證。 此指令碼支援 MFA 驗證。

1. 登入您要執行指令碼從本機系統管理員的權限的電腦。
2. 下載或從 GitHub[取得 AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)指令碼複製到您要從中執行 scruipt 資料夾。 這是將會寫入輸出"permissions.csv"檔案的相同資料夾。
3. 開啟 [以系統管理員身分的 PowerShell 執行個體，並開啟至儲存指令碼的資料夾。
4. 連線至您的目錄[連線 AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0)指令程式。
5. 執行此 PowerShell 命令列如下所示：`Get-AzureADPSPermissions.ps1 | Export-csv -path "Permissions.csv" -NoTypeInformation`

指令碼會產生一個名為 Permissions.csv 的檔案。請遵循下列步驟來尋找非法應用程式的權限授與： 
1. ConsentType 欄 （欄 G） 中搜尋"AllPrinciples"的值。AllPrincipals 權限可讓所有人的內容存取租用中的用戶端應用程式。原生 Office 365 應用程式需要此權限才能正常運作。具有此權限的每一個非 Microsoft 應用程式應該謹慎檢閱。
2.  在權限的資料行 （資料行 F） 檢閱每個委派應用程式的權限有內容。尋找 「 讀取 」 及 「 寫入 」 權限或"*。所有 「 權限及檢閱這些謹慎因為可能不是適當的。
3.  檢閱已同意授與特定使用者。如果高設定檔] 或 [高影響使用者授與不適當的同意，您應該進一步調查。
4.  ClientDisplayName 欄 （C 欄） 中尋找似乎可疑的應用程式。應用程式與拼錯的名稱、 super 乏味名稱或駭客發音名稱應該謹慎檢閱。

## <a name="determine-the-scope-of-the-attack"></a>決定攻擊的範圍
完成清查應用程式存取之後，請先檢閱 Office 365**稽核記錄檔**來判斷完整破壞的範圍。 搜尋在受影響的使用者，非法應用程式有時間範圍的存取您的組織和應用程式有權限。您可以搜尋**稽核記錄**中的[Office 365 安全性和規範中心 」](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。 

> [!IMPORTANT]
> [信箱稽核](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918)及[活動的稽核系統管理員和使用者](https://support.office.com/article/turn-office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)必須已啟用之前為您要取得此資訊攻擊。

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant--attack"></a>如何停止及修復非法同意授與攻擊
識別具有非法權限的應用程式之後，您有數種方式移除該 access。
- 您可以撤銷的 Azure Active Directory 入口網站中的應用程式的權限：
    - 瀏覽至**Azure Active Directory 使用者**blade 受影響使用者。
    - 選取 [**應用程式**。
    - 選取非法應用程式。
    - 按一下 [**移除**向下切入中向下。
- 您可以遵循下列步驟中[移除 AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant?view=azureadps-2.0)撤銷 powershell OAuth 同意授與。
- 您可以遵循下列步驟中[移除 AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment?view=azureadps-2.0)撤銷 PowerShell 與服務應用程式角色指派。
- 您也可以停用的受影響的帳戶完全，如此將會停用應用程式資料的存取權的帳戶的登入。這不是適用於使用者的產能當然，但如果您正在快速限制影響，它可以是可行的短期補救方法。
- 您可以關閉整合式應用程式的租用。這是極端的步驟，停用使用者授與租用戶全為基礎的同意的能力。這可防止使用者不慎授與存取權的惡意的應用程式。這不是強烈建議為其造成嚴重不但您的使用者能夠提高工作效率與協力廠商應用程式。 您可以遵循忘記整合在[應用程式](https://support.office.com/article/Turning-Integrated-Apps-on-or-off-7e453a40-66df-44ab-92a1-96786cb7fb34)中開啟或關閉。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>安全 like cybersecurity 專業人員的 Office 365
您的 Office 365 訂閱隨附一組功能強大的安全性功能可用來保護您的資料與您的使用者。 使用[Office 365 安全性藍圖： 最常用的優先順序的前 30 天 90 天和超過](https://support.office.com/article/office-365-security-roadmap-top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)實作 Microsoft 建議的最佳作法保護您的 Office 365 租用戶。
- 若要完成工作前 30 天的工作。 這些包含立即影響且為 low 影響您的使用者。
- 若要完成 90 天的工作。這些需要規劃和實作但大幅改善了安全性狀態的更多時間。
- 超過 90 天。您在第一個 90 天工作建立這些增強功能。

## <a name="see-also"></a>另請參閱：
- [我的應用程式] 清單中未預期的應用程式](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)會引導管理員透過各種他們可能會想要之後實現有未預期的應用程式的存取權以資料採取的動作。
- [與 Azure Active Directory 的整合應用程式] (https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent)是同意和權限的整體概觀。 請特別注意[同意架構的概觀](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#overview-of-the-consent-framework)＞ 一節。
- [問題開發我應用程式](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)提供連結至各種同意的相關的文章。
- [應用程式及服務主體物件在 Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)提供之應用程式及服務主體物件的核心應用程式模型概觀。
- [管理存取權的應用程式](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)為系統管理員可以管理應用程式的使用者存取功能的概觀。
