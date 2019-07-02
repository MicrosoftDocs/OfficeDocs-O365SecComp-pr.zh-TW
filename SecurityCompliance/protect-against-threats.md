---
title: 防止 Office 365 中的威脅
ms.author: tracyp
author: msfttracyp
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 05/09/2019
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 請立即使用本文做為設定威脅防護功能的指南。
ms.openlocfilehash: 6700e2714ea607f675b487204404d53c1d51db93
ms.sourcegitcommit: 424a614141c1f19a1c84a67ec2d71dd3d7ef6694
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/30/2019
ms.locfileid: "34590576"
---
# <a name="protect-against-threats-in-office-365"></a>防止 Office 365 中的威脅

Office 365 包含各種威脅防護功能。 以下是快速入門手冊, 您可以用來做為檢查清單, 以確保您的組織已設定威脅防護功能。 如果您是 Office 365 中威脅防護功能的新功能, 或您不確定要開始的位置, 請使用下列指引做為起點。 

> [!IMPORTANT]
> **每種原則都包含初始建議設定, 不過, 有許多選項可供使用, 而且您可以調整您的設定以符合特定組織的需求**。 針對您的原則, 允許大約30分鐘, 或變更以透過您的資料中心來運作。

## <a name="requirements"></a>需求

### <a name="subscriptions"></a>訂閱

威脅防護功能包含在所有的 Office 365 訂閱中。不過, 有些訂閱包含更多的高級功能。 下表列出本文隨附的保護功能, 以及最基本的訂閱需求。<br/>

|保護類型  |訂閱需求  |
|---------|---------|
|反惡意程式碼保護    | [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)EOP        |
|保護電子郵件和 Office 檔中的惡意 Url 和檔案    | [Office 365 高級威脅防護](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)ATP       |
|反網路釣魚保護    | [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)      |
|高級反網路釣魚保護    | [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)   |
|反垃圾郵件保護     | [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)       |
|零小時自動清除 (電子郵件)    | [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)        |
|審核記錄 (這是用於報告目的)    | [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)        |

### <a name="roles-and-permissions"></a>角色及權限

您必須獲指派適當的角色, 才能設定[安全性 & 規範中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)中的原則。 下表包含一些範例: 

|角色或角色群組  |深入瞭解  |
|---------|---------|
|Office 365 全域系統管理員 |[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|安全性系統管理員 |[Azure Active Directory 中的系統管理員角色許可權](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織管理 |[Exchange Online 中的許可權](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>與<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

若要深入瞭解, 請參閱[Office 365 安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。

## <a name="part-1---anti-malware-protection"></a>第1部分-反惡意程式碼保護

您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中使用[反惡意程式碼保護](anti-malware-protection.md)。 

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中, 選擇 [**威脅管理** > **原則** > **反惡意**代碼]。

2. 按兩下**預設**原則, 然後選擇 [**設定**]。

3. 指定下列設定:

    - 在 [**惡意程式碼偵測回應**] 區段中, 保留預設設定 [**否**]。

    - 在 [**通用附件類型篩選**] 區段中, 選擇 [**開啟**]。

4. 按一下 [儲存]****。

若要深入瞭解反惡意程式碼原則選項, 請參閱[設定反惡意程式碼原則](configure-anti-malware-policies.md)。

## <a name="part-2---protection-from-malicious-urls-and-files"></a>第2部分-防護惡意 Url 和檔案

在包含[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) 的訂閱中, 可以使用 [從惡意 url 和檔案進行防護], 並透過[atp 安全附件](atp-safe-attachments.md)和[atp 安全連結](atp-safe-links.md)原則設定。

### <a name="atp-safe-attachments-policies"></a>ATP 安全附件原則

若要設定[Atp 安全附件](atp-safe-attachments.md), 您必須至少定義一個 ATP 安全附件原則。 

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中, 選擇 [**威脅管理** > **原則** > **ATP 安全附件**]。

2. 選取 [**開啟 SharePoint、OneDrive 及 Microsoft 團隊的 ATP**] 選項。

3. 在 [**保護電子郵件附件**] 區段中, 按一下加號**+**()。

4. 指定下列設定:

    - 在 [**名稱**] 方塊中`Block malware`, 輸入。

    - 在 [回應] 區段中, 選擇 [**區塊**]。

    - 在 [重新**導向附件**] 區段中, 選取 [**啟用重新導向**] 選項, 然後指定組織的安全性系統管理員或操作員的電子郵件地址, 以查看偵測到的檔案。

    - 在 [套用**至**] 區段中, 選擇 [**收件**者] 網域。 然後, 選取您的網域, 選擇 [**新增**], 然後按一下 **[確定]**。

5. 按一下 [儲存]****。

6. (**建議的其他步驟**)在全域系統管理員或 SharePoint Online 系統管理員對您的 Office 365 環境執行**[set-spotenant 指令程式](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)**, 並將**DisallowInfectedFileDownload**參數設為*true* 。 (這可防止使用者開啟、移動、複製或共用偵測到惡意的檔案)。  

若要深入瞭解, 請參閱[設定 office 365 Atp 安全附件原則](set-up-atp-safe-attachments-policies.md)和[開啟 office 365 atp For SharePoint、OneDrive 及 Microsoft 團隊](turn-on-atp-for-spo-odb-and-teams.md)。

### <a name="atp-safe-links-policies"></a>ATP 安全連結原則

若要設定[ATP 安全連結](atp-safe-links.md), 請查看和編輯您的預設原則, 並新增特定使用者的原則。

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中, 選擇 [**威脅管理** > **原則** > **ATP 安全連結**]。

2. 按兩下**預設**原則。

3. 在 [**使用安全連結**] 區段中, 選取 [ **office 365 專業增強版]、[office for iOS] 和 [Android**] 選項, 然後按一下 [**儲存**]。

4. 在 [套用**至特定**收件者的原則] 區段中, 按一下**+** 加號 ()。

5. 指定下列設定:

    - 在 [**名稱**] 方塊中, 輸入名稱, 例如`Safe Links`。

    - 在 [**選取動作**] 區段中, 選擇 [**開啟**]。

    - 選取下列選項:

        - **使用安全附件掃描可下載的內容** 

        - **將安全連結套用至組織內傳送的電子郵件**

        - **不要讓使用者點擊至原始 URL 的安全連結**

    - 在 [套用**至**] 區段中, 選擇 [**收件**者] 網域。 然後, 選取您的網域, 選擇 [**新增**], 然後按一下 **[確定]**。

6. 按一下 [儲存]****。

若要深入瞭解, 請參閱[設定 Office 365 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。 

## <a name="part-3---anti-phishing-protection"></a>第3部分-反網路釣魚保護

您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中使用[反網路釣魚保護](anti-phishing-protection.md)。 您可以在[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中使用高級的反網路釣魚防護。 下列程式說明如何設定 ATP 反網路釣魚原則。 設定反網路釣魚原則 (不含 ATP) 的步驟類似。

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中, 選擇 [**威脅管理** > **原則** > **ATP 反網路釣魚**]。

2. 按一下 [**預設原則**]。

3. 在 [ **** 模擬] 區段中, 按一下 [**編輯**], 然後指定下列設定:

    - 在 [**新增要保護的使用者**] 索引標籤上開啟 [保護]。 然後新增使用者, 例如您組織的董事會成員、CEO、CFO 和其他資深負責人。 (您可以輸入個別的電子郵件地址, 或按一下以顯示清單)。

    - 在 [**新增要保護的網域**] 索引標籤上, 開啟 [**自動包含我擁有的網域**]。 如果您有自訂網域, 也請新增這些網域。

    - 在 [**動作**] 索引標籤上, 選取 [**將郵件移至收件者的垃圾郵件資料夾**中的模擬的使用者和模擬的網域], 然後開啟 [安全提示]。

    - 在 [**信箱智慧**] 索引標籤上, 確定已開啟 [信箱智慧]。

    - 在 [**檢查您的設定**] 索引標籤上, 檢查您的設定後, 按一下 [**儲存**]。

4. 在 [**哄騙**] 區段中, 按一下 [**編輯**], 然後指定下列設定:

    - 在 [**哄騙篩選器設定**] 索引標籤上, 確定已開啟反欺詐保護。

    - 在 [**動作**] 索引標籤上, 選擇 [將郵件移至收件者的垃圾郵件資料夾]。

    - 在 [**檢查您的設定**] 索引標籤上, 檢查您的設定後, 按一下 [**儲存**]。 (如果您沒有進行任何變更, 請按一下 [**取消**]。)

5. 關閉 [預設原則設定] 頁面。

若要深入瞭解您的反網路釣魚原則選項, 請參閱[設定反網路釣魚原則](set-up-anti-phishing-policies.md)。

## <a name="part-4---anti-spam-protection"></a>第4部分-反垃圾郵件保護

您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中使用[反垃圾郵件保護](anti-spam-protection.md)。

1. 在 [[安全性 & 規範中心](https://protection.office.com)] 中, 選擇 [**威脅管理** > **原則** > **反垃圾郵件**]。

2. 在 [**自訂**] 索引標籤上開啟**自訂設定**。

3. 展開 [**預設垃圾郵件篩選原則**], 按一下 [**編輯原則**], 然後指定下列設定:

    - 在 [**垃圾郵件和大量動作**] 區段中, 將臨界值設為5或6。

    - 在 [**允許清單**] 區段中, 複查 (並在必要時編輯) 您允許的寄件者和網域。

4. 按一下 [儲存]****。

若要深入瞭解您的反垃圾郵件原則選項, 請參閱[設定反垃圾郵件原則](configure-the-anti-spam-policies.md)。

## <a name="part-5---additional-settings-to-configure"></a>第5部分-要設定的其他設定

除了設定惡意程式碼、惡意 Url 和檔案、網路釣魚和垃圾郵件的防護之外, 建議您設定零時自動清除和審核記錄設定。

### <a name="zero-hour-auto-purge-for-email"></a>電子郵件的零時自動清除

[零小時自動清除](zero-hour-auto-purge.md)(ZAP) 可在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中使用。 此保護預設為開啟。不過, 若要使保護生效, 必須符合下列條件:

- 在[反垃圾郵件原則](anti-spam-protection.md)中, 垃圾郵件動作會設定為**將郵件移至垃圾郵件資料夾**。

- 使用者保留其預設的[垃圾郵件設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), 且未關閉垃圾郵件保護。

若要深入瞭解, 請參閱[零時自動清除防護垃圾郵件和惡意](zero-hour-auto-purge.md)代碼。

### <a name="audit-logging-for-reporting-and-investigation"></a>報告和調查的審核記錄

您可以在包含[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)的訂閱中取得審核記錄。 若要在威脅防護報告中查看資料, 例如[安全性儀表板](security-dashboard.md)、[電子郵件安全性報告](view-email-security-reports.md)和[Explorer](use-explorer-in-security-and-compliance.md), 您的組織必須開啟審核記錄。 若要深入瞭解, 請參閱[開啟或關閉 Office 365 audit log search](turn-audit-log-search-on-or-off.md)。

## <a name="post-setup-tasks"></a>安裝後的工作

設定威脅防護功能之後, 請務必監視這些功能的運作方式、視需要查看和修訂原則, 以及查看新功能和服務更新。

|待辦事項  |要深入瞭解的資源  |
|---------|---------|
|透過查看報告, 查看您組織的威脅防護功能的運作方式    |[安全性儀表板](security-dashboard.md)<br/>[電子郵件安全性報告](view-email-security-reports.md)<br/>[Office 365 ATP 的報告](view-reports-for-atp.md)<br/>[威脅總管](use-explorer-in-security-and-compliance.md)    |
|視需要定期檢查和修訂威脅防護原則    |[安全分數](microsoft-secure-score.md)<br/>[智慧報表和深入資訊](reports-and-insights-in-security-and-compliance.md)<br/>[Office 365 威脅調查和回應功能](keep-users-safe-with-office-365-ti.md)          |
|監視新功能和服務更新     |[標準和目標發行選項](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[訊息中心](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)         |
