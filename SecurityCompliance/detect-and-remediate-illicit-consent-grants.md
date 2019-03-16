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
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 了解如何識別並修復 Office 365 中的非法同意授權攻擊。
ms.openlocfilehash: 454b1b0dcf7a6182895dcc97889286f3000c9626
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2019
ms.locfileid: "30656069"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a>偵測並修復 Office 365 中的非法同意授權

**摘要** 了解如何識別並修復 Office 365 中的非法同意授權攻擊。

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>什麼是 Office 365 中的非法同意授與攻擊？
非法同意授權攻擊，攻擊者就會建立 Azure 註冊的應用程式要求存取資料，例如連絡人的資訊，電子郵件，或文件。 攻擊者然後技巧到授與該應用程式同意才能透過網路釣魚攻擊，或將插入的受信任的網站，以便非法程式碼來存取其資料的使用者。 非法應用程式授與同意之後，它會有不需組織帳戶進行資料存取帳戶層級。 一般的補救步驟，例如重設受到破壞帳戶的密碼或帳戶，需要多重要素驗證 (MFA) 不對此類的攻擊，有效，因為這些是協力廠商應用程式，而組織外部的。 這些攻擊利用假定為呼叫資訊的實體是自動化，並不 human 互動模型。

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>項目並未非法同意授與攻擊的外觀在 Office 365？
您要搜尋 Office 365**稽核記錄，** 以尋找符號，也稱為 「 標記的危害 (IOC) 這類攻擊。 對許多 Azure 註冊應用程式與大型使用者基底的組織而言，最佳作法是檢閱您的組織同意授與每週為基礎。
### <a name="steps-for-finding-signs-of-this-attack"></a>步驟來尋找此類攻擊的跡象
1. Office 365 租用戶中開啟的**安全性與合規性中心**。
2. 瀏覽至 [**搜尋 & 和調查**] 節點，然後選取 [**稽核記錄**搜尋。
3. 建立 「 搜尋 」 （所有活動和所有的使用者） 篩選結果的同意，應用程式，並新增 OAuth2PermissionGrant。
4. 檢查郵件的延伸內容並檢查看看是否 IsAdminContent 設為 True。


如果此值為 true，就表示，以全域系統管理員存取權的人員可能會有廣泛存取權授與資料。 如果這是未預期，請執行下列步驟[確認攻擊](detect-and-remediate-illicit-consent-grants.md#confirmattack)。

<a name="confirmattack"> </a>
## <a name="how-to-confirm-an-attack"></a>如何確認攻擊
如果您有一或多個執行個體的 IOCs 上述，您需要進行進一步調查正面確認 [攻擊的發生。 您可以使用任何下列三種方法來確認攻擊。
- 庫存應用程式並使用 Azure Active Directory 入口網站及其權限。 這個方法是徹底，但您只能用來檢查一位使用者一次可以是相當耗時如果您有許多使用者檢查。
- 庫存應用程式並使用 PowerShell 及其權限。 這是最快和最完整的方法，以最少的額外負荷量。
- 讓使用者個別檢查其應用程式和權限，並將結果回報修復的管理員。

## <a name="inventory-apps-with-access-in-your-organization"></a>與您組織中存取的庫存應用程式
您可以這麼做為您的使用者與 Azure Active Directory 入口網站或 PowerShell，或讓使用者個別列舉其應用程式的存取。

### <a name="steps-for-using-the-azure-active-directory-portal"></a>使用 Azure Active Directory 入口網站的步驟
您可以查閱的任何個別的使用者已授與權限使用[Azure Active Directory 入口網站](https://portal.azure.com/)的應用程式。 
1. 登入 Azure 入口網站，具有系統管理權限。
2. 選取 [Azure Active Directory] 刀鋒視窗。
3. 選取 [**使用者**]。
4. 選取您想要檢閱的使用者。
5. 選取 [**應用程式**。

如此將會顯示指派給使用者和功能的應用程式 applcations 具有的權限。

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>讓您的使用者的步驟列舉其應用程式的存取
讓使用者移至https://myapps.microsoft.com並檢閱那里自己的應用程式存取。 他們應該可以看到具有存取權的所有應用程式，檢視它們 （包括的存取範圍） 的詳細資料，而且無法撤銷可疑或非法應用程式的權限。

### <a name="steps-for-doing-this-with-powershell"></a>執行此動作使用 PowerShell 的步驟
若要確認非法同意授與攻擊的最簡單方式是執行[Get AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)，這會將傾印所有 OAuth 同意授與和 OAuth 應用程式的所有使用者在您的租用成一個.csv 檔案。 

#### <a name="pre-requisites"></a>先決條件
- 安裝 Azure AD PowerShell 程式庫。
- 指令碼會執行對租用戶的全域系統管理員權限。
- 從其電腦上的本機系統管理員會執行指令碼。

> [!IMPORTANT]
> 我們強烈建議您在您的系統管理帳戶需要多重要素驗證。  此指令碼支援 MFA 驗證。

1. 登入您要執行的指令碼以本機系統管理員權限的電腦。
2. 下載或從 GitHub [Get AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)指令碼複製到您要從中執行 scruipt 資料夾。  這會將寫入輸出"permissions.csv 」 檔案的相同資料夾。
3. 開啟身為系統管理員的 PowerShell 執行個體，然後開啟至您儲存指令碼的資料夾。
4. 連線至您使用[Connect AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0)指令程式的目錄。
5. 執行此 PowerShell 命令列如下所示：`Get-AzureADPSPermissions.ps1 | Export-csv -path "Permissions.csv" -NoTypeInformation`

指令碼會產生一個名為 Permissions.csv 的檔案。 請遵循下列步驟來尋找非法應用程式的權限授與： 
1. ConsentType 欄 （欄 G） 中搜尋 「 AllPrinciples 」 的值。 AllPrincipals 權限可讓用戶端應用程式存取租用戶中的每個人的內容。 原生 Office 365 應用程式需要此權限正常運作。 與此權限的每一個非 Microsoft 應用程式應該仔細檢閱。
2.  在權限] 欄 （F 欄） 檢閱每個委派應用程式的權限有內容。 尋找 「 讀取 」 及 「 寫入 」 權限或 「 *。所有 「 權限，並檢閱這些仔細因為它們可能不是適當的。
3.  檢閱已同意授與特定使用者。 如果高設定檔] 或 [高影響使用者授與的不當同意，您應該在進一步調查。
4.  ClientDisplayName 欄 （C 欄） 中看起來好像可疑的應用程式。 應該仔細檢閱應用程式的拼字錯誤的名稱、 super 乏味名稱或駭客發音名稱。

## <a name="determine-the-scope-of-the-attack"></a>判斷攻擊的範圍
當您完成清查應用程式存取之後，請先檢閱 Office 365**稽核記錄**來判斷資料外洩的完整範圍。  搜尋受影響的使用者，在時間圖文框的非法應用程式具有存取您的組織，以及應用程式具有的權限。 您可以搜尋**稽核記錄**中的[Office 365 安全性與合規性中心](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。 

> [!IMPORTANT]
> [信箱稽核](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918)和[活動的稽核系統管理員和使用者](https://support.office.com/article/turn-office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)必須已啟用之前，以取得這項資訊攻擊。

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant--attack"></a>如何停止並修復非法同意授與攻擊
識別具有非法權限的應用程式之後，您會有幾種方式可以移除權限。
- 您可以撤銷由 Azure Active Directory 入口網站中的應用程式的權限：
    - 瀏覽至 [ **Azure Active Directory 使用者**] 刀鋒視窗中的受影響使用者。
    - 選取 [**應用程式**。
    - 選取非法應用程式。
    - 按一下 [**移除**]，讓向下切入中。
- 您可以依照下列步驟中[移除 AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant?view=azureadps-2.0)撤銷 OAuth 同意授與使用 PowerShell。
- 您可以依照下列步驟中[移除 AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment?view=azureadps-2.0)撤銷服務應用程式角色指派，使用 PowerShell。
- 您也可以停用受影響的帳戶完全，這會依次停用應用程式資料的存取權的帳戶中的登入。 這不適合使用者產能，當然，但如果您正在快速限制影響，它可以是可行的短期修復。
- 您可以關閉整合式應用程式為您的租用。 這是極端的步驟，停用使用者授與同意全租用戶為基礎的能力。 這可防止您的使用者不小心授與存取權的惡意的應用程式。 這不建議您為嚴重會妨礙您的使用者即可發揮生產力與協力廠商應用程式。  您可以[開啟整合式應用程式](https://support.office.com/article/Turning-Integrated-Apps-on-or-off-7e453a40-66df-44ab-92a1-96786cb7fb34)中開啟或關閉的步驟。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>保護 Office 365 專業 cybersecurity 像
Office 365 訂閱隨附一組功能強大的安全性功能，可用來保護您的資料和您的使用者。  使用[Office 365 安全性藍圖： 前的 30 天、 前 90 天及過後](https://support.office.com/article/office-365-security-roadmap-top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)實作 Microsoft 建議的最佳作法為保護您的 Office 365 租用戶。
- 若要在第一個 30 天內完成的工作。  這些有直接影響，而低影響您的使用者。
- 若要在 90 天內完成的工作。 這些較多要花時間規劃及實作，但是大幅改善您的安全性狀態。
- 超過 90 天。 這些增強功能建立您第一張 90 天的工作。

## <a name="see-also"></a>另請參閱：
- [未預期的應用程式的應用程式] 清單中](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)會逐步引導管理員透過各種動作，他們可能會想要採取之後實現有非預期的應用程式存取資料。
- [Azure Active directory 整合應用程式] (https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent)是同意和權限的高階概觀。  請特別注意[同意架構概觀](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#overview-of-the-consent-framework)區段。
- [問題開發我的應用程式](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)提供連結至各種同意相關的文章。
- [應用程式和 Azure Active Directory (Azure AD) 中的服務主體物件](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)提供應用程式和服務主體物件的核心應用程式模型的概觀。
- [應用程式的管理存取](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)是系統管理員具有管理應用程式的使用者存取的功能概觀。
