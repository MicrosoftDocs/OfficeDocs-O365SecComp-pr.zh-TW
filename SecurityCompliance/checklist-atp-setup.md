---
title: 快速入門： 設定 Office 365 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 以下是您可以使用以確保 Office 365 進階威脅防護 (ATP) 會安裝並設定您組織快速入門指南。
ms.openlocfilehash: a071c626327aa7d0055df522e8fec5ebe41d6a83
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999396"
---
# <a name="quick-start-guide-set-up-office-365-advanced-threat-protection"></a>快速入門指南：設定 Office 365 進階威脅防護

以下是您可以使用一份清單，請確定 Office 365 進階威脅防護 (ATP)，會為您的組織設定好快速入門指南。 如果您是初次使用 Office 365 中的威脅防護，或您不只是確定要開始，請使用下列指引做為起點。 

> [!IMPORTANT]
> **初始建議的設定包含每種原則; 不過，有許多選項可用，且您可以調整您的設定以符合您特定的組織需求**。 允許大約 30 分鐘，為您的原則或變更其透過您的資料中心的方式運作。

## <a name="prerequisites"></a>必要條件

- 您的組織必須包含[Office 365 進階威脅防護](office-365-atp.md)(ATP) 訂閱。

- 您必須獲指派適當的角色，才能存取 ATP 功能。 下表包含一些範例： 

    |角色或角色群組  |若要了解更多的位置  |
    |---------|---------|
    |Office 365 全域系統管理員 |[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
    |安全性系統管理員 |[在 Azure Active Directory 系統管理員角色權限](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
    |Exchange Online 組織管理 |[權限在 Exchange Online](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>與<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

    (請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。)

## <a name="part-1---anti-malware"></a>1-反惡意程式碼組件

1. 在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **反惡意程式碼**。
2. 連按兩下**預設**原則]，然後再選擇 [**設定**。
3. 指定下列設定：
    - 在 [**惡意程式碼偵測回應**] 區段中，保留預設設定 [**否]**。
    - **常見附件類型篩選**] 區段中，選擇 [**上**]。
4. 按一下 [儲存]****。

若要深入了解反惡意程式碼原則選項，請參閱 <<c0>設定反惡意程式碼原則。

## <a name="part-2---zero-day-protection"></a>組件 2-零時差保護

零時差保護是透過原則，例如 ATP 安全連結和安全附件原則設定。

### <a name="atp-safe-attachments-policies"></a>ATP 安全附件原則

1. 在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **ATP 安全附件**。
2. 選取 [**開啟 ATP SharePoint、 OneDrive 及 Microsoft Teams**] 選項。
3. 在 [**保護電子郵件附件**] 區段中，按一下加號 (**+**)。
4. 指定下列設定：
    - 在 [**名稱**] 方塊中，輸入`Block malware`。
    - 在 [回應] 區段中，選擇 [**封鎖**]。
    - 在**重新導向附件**] 區段中，選取 [**啟用重新導向**，] 選項，然後指定貴組織的安全性系統管理員或運算子會檢閱者的電子郵件地址偵測到的檔案。
    - 在 [**套用至**] 區段中，選擇 [**收件者網域是**]。 接著，選取您的網域選擇 [**新增**]，然後按一下 [**確定]**。
5. 按一下 [儲存]****。
6. （建議使用額外的步驟）以全域系統管理員或 SharePoint Online 管理員執行**[Set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** 指令程式搭配**DisallowInfectedFileDownload**參數設為*true*適用於 Office 365 環境。 （這可防止人員開啟、 移動、 複製或共用檔案，就會被視為惡意。）  

若要了解更多，請參閱[設定 Office 365 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)及[開啟 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)。

### <a name="atp-safe-links-policies"></a>ATP 安全連結原則

若要設定 ATP 安全連結，檢閱您的預設原則，並新增原則。

1. 在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **ATP 安全連結**。
2. 連按兩下**預設**原則。
3. 在**使用中的安全連結**] 區段中，選取 [ **Office 365 專業增強版、 Office for iOS 和 Android**，] 選項，然後按一下 [**儲存**。
4. 在**原則套用至特定收件者**] 區段中，按一下加號 (**+**)。
5. 指定下列設定：
    - 在 [**名稱**] 方塊中，輸入名稱，例如： `Safe Links`。
    - 在 [**選取動作**] 區段中，選擇 [**上**]。
    - 選取這些選項：
        - **使用安全附件以掃描可下載內容** 
        - **套用至組織內傳送的電子郵件的安全連結**
        - **不要讓使用者按一下原始 url 的安全連結**
    - 在 [**套用至**] 區段中，選擇 [**收件者網域是**]。 接著，選取您的網域選擇 [**新增**]，然後按一下 [**確定]**。
6. 按一下 [儲存]****。

若要深入了解，請參閱 <<c0>設定 Office 365 ATP 安全連結原則。 

## <a name="part-3---anti-phishing"></a>第 3-反網路釣魚部分 

1. 在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **ATP 防網路釣魚**。
2. 按一下 [**預設原則**。
3. 在 [**模擬**] 區段中，按一下 [**編輯**]，然後指定下列設定：
    -  在 [**新增使用者至保護**索引標籤中，開啟保護。 然後新增使用者，例如您的組織棋盤成員、 CEO、 CFO，以及其他資深領導人。 （您可以輸入個別電子郵件地址，或按一下 [顯示清單。）
    - [**新增網域，以保護**] 索引標籤中，開啟**自動包含我所擁有的網域**。 如果您有自訂網域，以及將它們新增。
    - 在 [**動作**] 索引標籤上選取 [**將郵件移至 [收件者的垃圾郵件資料夾**都要模擬使用者模擬的網域，並開啟安全提示。
    - 在**信箱智慧**] 索引標籤，請確定信箱智慧已開啟。
    - 在 [**檢閱您的設定**] 索引標籤中，檢閱您的設定之後，按一下 [**儲存**。
4. 在 [**詐騙**] 區段中，按一下 [**編輯**]，然後指定下列設定：
    - **詐騙篩選設定**索引標籤上，確定已開啟反詐騙保護。
    - 在 [**動作**] 索引標籤中，選擇 [將郵件移至 [收件者的垃圾郵件資料夾。
    - 在 [**檢閱您的設定**] 索引標籤中，檢閱您的設定之後，按一下 [**儲存**。 (如果您未進行任何變更，按一下 [**取消**。)
5. 關閉 [預設原則設定] 頁面。

若要深入了解反網路釣魚原則的選項，請參閱[Office 365 ATP 防網路釣魚和防網路釣魚原則設定](set-up-anti-phishing-policies.md)。

## <a name="part-4---anti-spam"></a>組件 4-反垃圾郵件

1. 在 [[安全性 & 合規性中心](https://protection.office.com)中，選擇 [**威脅管理** > **原則** > **反垃圾郵件**。
2. 在 [**自訂**] 索引標籤中，開啟**自訂設定**。
3. 依序展開 [**預設垃圾郵件篩選原則**，按一下 [**編輯原則**]，然後指定下列設定：
    - 在 [**垃圾郵件和大量動作**] 區段中，臨界值設為 5 或 6 的值。
    - 在 [**允許清單**] 區段中，檢閱 （和必要時，編輯） 允許寄件者和網域。
4. 按一下 [儲存]****。

若要深入了解反垃圾郵件原則的選項，請參閱[設定反垃圾郵件原則](configure-the-anti-spam-policies.md)。

## <a name="part-5---service-wide-settings"></a>組件 5-全服務設定

### <a name="zero-hour-auto-purge"></a>零時差自動清除

零時差自動清除 (ZAP) 開啟預設;不過，必須符合下列條件：
- 垃圾郵件動作會將**移至垃圾郵件] 資料夾的郵件**設定反垃圾郵件原則。
- 使用者有保留其預設的垃圾郵件設定，且已不會關閉垃圾郵件保護。

若要深入了解，請參閱[零時差自動清除-防範垃圾郵件和惡意程式碼](zero-hour-auto-purge.md)。

### <a name="audit-logging"></a>稽核記錄

若要檢視的資料在威脅保護報告，例如[安全性儀表板](security-dashboard.md)與[檔案總管](use-explorer-in-security-and-compliance.md)] 中，稽核記錄必須開啟為您的組織。

請參閱[開啟 Office 365 稽核記錄搜尋的開啟或關閉](turn-audit-log-search-on-or-off.md)。

## <a name="post-setup-tasks"></a>安裝後期工作

### <a name="watch-for-new-features-and-service-updates"></a>監看的新功能和服務更新

- [請造訪 Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [請參閱 Office 365 進階的威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)

### <a name="see-how-atp-is-working-for-your-organization"></a>請參閱 ATP 為您的組織的運作方式

- [檢視 Office 365 進階威脅防護報告](view-reports-for-atp.md)

- [使用檔案總管中的安全性&amp;合規性中心](use-explorer-in-security-and-compliance.md)

### <a name="periodically-review-and-revise-your-atp-policies"></a>定期檢閱並修改您的 ATP 原則

- [保護您的 Office 365 使用者安全與 Office 365 威脅調查及回應](keep-users-safe-with-office-365-ti.md) 

- [使用 Office 365 安全性中的智慧型報表和深入解析&amp;合規性中心](reports-and-insights-in-security-and-compliance.md) 