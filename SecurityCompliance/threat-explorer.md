---
title: 威脅瀏覽器 (和即時偵測)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/20/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: 深入瞭解安全性&amp;與規範中心中的 Explorer (和即時偵測)。
ms.openlocfilehash: 3d2eab30b97655b692ed1bfe089b6a79834fd110
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394348"
---
# <a name="threat-explorer-and-real-time-detections"></a>威脅瀏覽器 (和即時偵測)

如果您的組織有[office 365 高級威脅防護](office-365-atp.md)(OFFICE 365 ATP), 而且您有[必要的許可權](#required-licenses-and-permissions), 您可以使用**Explorer**或**即時**偵測 (先前稱為*即時報告*),[請參閱新功能](#new-features-in-real-time-detections)! 在 [安全性 & 規範中心] 中, 移至 [**威脅管理**], 然後選擇 [ **Explorer** ] 或 [**即時**偵測]。 

|使用 ATP 方案2時, 您會看到:  |使用 ATP 方案1時, 您會看到:  |
|---------|---------|
|![威脅瀏覽器](media/threatmgmt-explorer.png)      |![即時偵測](media/threatmgmt-realtimedetections.png)         |

使用 Explorer (或即時偵測) 時, 您有一個功能強大的報告, 可讓您的安全性作業小組有效且有效地調查和回應威脅, 其方式如下: 

![移至 [威脅\>管理瀏覽器]](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

您可以使用此報告, 進行下列作業:
- [查看 Office 365 安全性功能偵測到的惡意程式碼](#see-malware-detected-in-email-by-technology)
- [查看仿冒 Url 的資料, 然後按一下 [判定]](#view-data-about-phishing-urls-and-click-verdict)
- [從瀏覽器中的視圖開始自動調查和回應](#start-automated-investigation-and-response)程式(僅限 ATP 方案 2)
- ...[調查惡意電子郵件和更多內容](#more-ways-to-use-explorer-or-real-time-detections)!

## <a name="new-features-in-real-time-detections"></a>即時偵測中的新功能

Explorer/即時偵測會新增新的新欄位, 以提供更完整的電子郵件領域。 此變更的其中一部分是讓搜尋更容易進行安全性操作人員, 但是 net 結果是一眼就知道問題電子郵件的位置。

這是如何完成？ 傳遞狀態現在會分成兩欄:

- 傳遞動作-此電子郵件的狀態為何？
- 傳遞位置-這封電子郵件會做為結果的路由？

傳遞動作是由於現有的原則或偵測而對電子郵件採取的動作。 以下是電子郵件可能採取的動作:

|送貨  |Junked  |凍結  |代替  |
|---------|---------|---------|---------|
|電子郵件已傳遞至使用者的收件匣或資料夾, 而且使用者可以直接存取它。    | 電子郵件已傳送至使用者的垃圾郵件資料夾或已刪除的資料夾, 且使用者可以存取這些資料夾中的電子郵件。       | 任何被隔離、失敗或被捨棄的電子郵件。 使用者完全無法存取此功能!     | 任何電子郵件, 其中惡意附件會由指出附件惡意的 .txt 檔案所取代。     |

以下是使用者可以看到的內容, 以及無法執行的動作:

|可供使用者存取  |無法存取使用者  |
|---------|---------|
|送貨     | 凍結        |
|Junked     | 代替        |

[傳遞位置] 顯示執行傳遞後的原則和偵測結果。 它會連結至傳遞動作。 新增此欄位是為了深入瞭解當發現問題郵件時所採取的動作。 以下是 [傳遞位置] 的 possilbe 值:

1. 收件匣或資料夾-電子郵件位於 [收件匣] 或 [資料夾 (根據您的電子郵件規則)。
2. 部署或外部–信箱不存在於雲端上, 但在內部部署。
3. 垃圾郵件資料夾–在使用者的 [垃圾郵件] 資料夾中的電子郵件。
4. [刪除的郵件] 資料夾–使用者的 [刪除的郵件] 資料夾中的電子郵件。
5. 隔離–隔離中的電子郵件, 且不在使用者的信箱中。
6. 失敗–電子郵件無法送達信箱。
7. 捨棄–電子郵件會在郵件流程中的某處遺失。

## <a name="see-malware-detected-in-email-by-technology"></a>查看透過技術在電子郵件中偵測到的惡意程式碼

假設您想要查看以 Office 365 技術在電子郵件中偵測到惡意程式碼的情況。 若要執行這項操作, 請使用瀏覽器 (或即時偵測) 的[電子郵件 > 惡意](threat-explorer-views.md#email--malware)代碼視圖。

1. 在 [安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com))] 中, 選擇 [**威脅管理** > **瀏覽器**] (或 [**即時**偵測])。 (此範例會使用 Explorer)。

2. 在 [**視圖**] 功能表中, 選擇 [**電子郵件** > **惡意**代碼]。<br/>![瀏覽器的 [視圖] 功能表](media/ExplorerViewEmailMalwareMenu.png)<br/>

3. 按一下 [**寄件者**], 然後選擇 [**基本** > **偵測技術**]。<br/>您的偵測技術現在可做為報告的篩選器。<br/>![惡意軟體偵測技術](media/ExplorerEmailMalwareDetectionTech.png)<br/> 

4. 選取 [選項], 然後按一下 [ **** 重新整理] 按鈕套用該篩選。<br/>![選取偵測技術](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

報表會重新整理以顯示使用您選取的技術選項, 在電子郵件中偵測到惡意程式碼的結果。 您可以從這裡進行進一步的分析。

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>查看仿冒 Url 的資料, 然後按一下 [判定]

假設您想要透過電子郵件中的 Url 查看網路釣魚嘗試, 包括允許、封鎖及覆寫的 Url 清單。 識別所按一下的 Url 需要設定[ATP 安全連結](atp-safe-links.md)。 請確定您已設定[Atp 安全連結原則](set-up-atp-safe-links-policies.md), 以在按一下 [保護] 和 [記錄] 時, 按一下 [Atp 安全連結] 的 [verdicts]。 

若要查看郵件中的釣魚程式 Url, 並按一下網路釣魚郵件中的 Url, 請使用瀏覽器 (或即時偵測) 的[電子郵件 > 釣魚](threat-explorer-views.md#email--phish)者視圖。

1. 在 [安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com))] 中, 選擇 [**威脅管理** > **瀏覽器**] (或 [**即時**偵測])。 (此範例會使用 Explorer)。

2. 在 [**視圖**] 功能表中, 選擇 [**電子郵件** > **釣魚詐騙**]。<br/>![瀏覽器的 [視圖] 功能表](media/ExplorerViewEmailPhishMenu.png)<br/>

3. 按一下 [**寄件者**], 然後選擇 [ **url** > ]**按一下 [判定**]。

4. 選取一或多個選項, 例如 [**封鎖**] 和 [封鎖已覆**寫**], 然後按一下位於同一行上的 [重新整理] 按鈕, 作為套用該篩選的選項。 **** (不要重新整理瀏覽器視窗。)<br/>![Url, 然後按一下 [verdicts]](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

    報表會重新整理, 以在報表下的 [URL] 索引標籤上顯示兩個不同的 URL 表格:

   1. **Top url**是所篩選郵件中所包含的 url, 以及每個 URL 的電子郵件傳遞動作計數。 在 [詐騙者電子郵件] 視圖中, 此清單通常會包含合法的 Url。 攻擊者會在其郵件中混合使用良好且不良的 Url, 以嘗試傳遞這些 Url, 但他們會讓使用者更感興趣的惡意連結。 Url 的資料表是依電子郵件總數排序 (注意: 此欄不會顯示以簡化視圖)。

   2. [**上一次按一下**] 是所按一下的安全連結包裝的 url, 依總按一下次數排序 (此欄也不會顯示以簡化視圖)。 [總計依據] 欄表示安全連結按一下每個按下 URL 的 [判定計數]。 在 [詐騙器電子郵件] 視圖中, 這些是較常見的可疑 Url, 但可能包含網路釣魚郵件中的清除 Url。 在此處不會顯示已開啟連結的 URL。
   
   這兩個 Url 表格會透過傳遞動作和位置來顯示網路釣魚電子郵件中的主要 Url, 並顯示已封鎖的 URL 按一下 (無論是在警告情況下進行存取), 以便您瞭解使用者所收到的潛在不良連結, 以及使用者所進行的互動。 您可以從這裡進行進一步的分析。 例如, 在圖表下方, 您可以在組織的環境中看到已封鎖的電子郵件中的最高 Url。
   
   ![已封鎖的 Explorer Url](media/ExplorerPhishClickVerdictURLs.png)
   
   選取 URL 以查看更詳細的資訊。 請注意, 在 [URL 飛入] 對話方塊中, 會移除在電子郵件上的篩選, 以顯示您的環境中 URL 公開的完整視圖。 這可讓您將瀏覽器中的電子郵件篩選為您關心的問題、找出潛在威脅的特定 Url, 然後展開您對環境中 URL 曝露的瞭解 (透過 URL 詳細資料對話方塊), 而不需要將 URL 篩選新增至資源管理器視圖本身。

## <a name="review-email-messages-reported-by-users"></a>查看使用者所報告的電子郵件訊息

假設您想要查看組織中的使用者已報告為垃圾郵件、非垃圾郵件或網路釣魚的電子郵件, 方法是使用[Outlook 和 outlook 網頁版的報告訊息增益集](enable-the-report-message-add-in.md)。 若要這麼做, 請使用瀏覽器 (或即時偵測) 的[使用者報告 > 的電子郵件](threat-explorer-views.md#email--user-reported)。

1. 在 [安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com))] 中, 選擇 [**威脅管理** > **瀏覽器**] (或 [**即時**偵測])。 (此範例會使用 Explorer)。

2. 在 [**視圖**] 功能表中, 選擇 [**電子郵件** > **使用者-已報告**]。<br/>![瀏覽器的 [視圖] 功能表](media/ExplorerViewMenuEmailUserReported.png)<br/>

3. 按一下 [**寄件者**], 然後選擇 [**基本** > **報告類型**]。

4. 選取一個選項, 例如 [**網路釣魚**者], 然後**** 按一下 [重新整理] 按鈕。 <br/>![使用者報告的網路釣魚](media/EmailUserReportedReportType.png)<br/> 

報表會重新整理, 以顯示組織中的人員已報告為網路釣魚嘗試的電子郵件訊息相關資料。 您可以使用此資訊進行進一步的分析, 並視需要調整[ATP 反網路釣魚原則](set-up-anti-phishing-policies.md)。

## <a name="start-automated-investigation-and-response"></a>啟動自動調查和回應

> [!NOTE]
> **Office 365 ATP Plan 2**和**Office 365 E5**提供自動化的調查和回應功能。

(新!)[自動化調查和回應](automated-investigation-response-office.md)可將您的安全性作業小組儲存在調查和降低網路攻擊的時間和精力。 除了設定可觸發安全性行動手冊的警示之外, 您還可以從瀏覽器中的視圖開始自動調查和回應程式。 

如需這種情況的詳細資訊, 請參閱[範例: 安全性系統管理員會觸發從瀏覽器進行的調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>更多使用瀏覽器的方法 (或即時偵測)

除了本文所述的案例之外, 您還可以使用瀏覽器 (或即時偵測) 提供的更多報告選項。 
- [尋找並調查傳送的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)
- [查看 SharePoint Online、OneDrive 和 Microsoft 團隊中偵測到的惡意檔案](malicious-files-detected-in-spo-odb-or-teams.md)
- [取得威脅瀏覽器中的視圖 (和即時偵測) 的總覽](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a>必要的授權和許可權

您必須擁有[Office 365 ATP](office-365-atp.md) , 才能取得 Explorer 或即時偵測。
- Explorer 包含在 Office 365 ATP 方案2中。 
- 即時偵測報告包含在 Office 365 ATP 方案1中。
- 規劃為應由 ATP 保護的所有使用者指派授權。 (Explorer 或即時偵測會顯示已授權使用者的偵測資料。)

若要查看和使用瀏覽器或即時偵測, 您必須具有適當的許可權, 例如授與安全性系統管理員或安全性讀取者的許可權。 

- 針對安全性&amp;合規性中心, 您必須已指派下列其中一個角色:
    - 組織管理
    - 安全性系統管理員 (可在 Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com)) 中指派)
    - 安全性讀取器

- 若為 Exchange Online, 您必須在 Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell Cmdlet 中指派下列其中一個角色 (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):
    - 組織管理
    - 僅檢視組織管理
    - 僅檢視收件者角色
    - 合規性管理

若要深入瞭解角色和許可權, 請參閱下列資源:

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
- [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
