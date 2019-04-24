---
title: Office 365 安全分數
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: 屬於不知道如何保護您的組織確實是在 Office 365？ 安全分數以下是可幫助。 安全分數分析根據您的日常活動和 Office 365 中的安全性設定貴組織的安全性，並為其打分數。
ms.openlocfilehash: dd0dc87910853eba9f2ec3ec6752e857462b46e5
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262443"
---
# <a name="office-365-secure-score"></a>Office 365 安全分數

**摘要**屬於不知道如何保護您的組織確實是在 Office 365？ 安全分數以下是可幫助。 安全分數分析根據您的日常活動和 Office 365 中的安全性設定貴組織的安全性，並為其打分數。 閱讀本篇文章以取得安全分數，以及您如何使用它的概觀。
  
## <a name="how-to-get-to-secure-score"></a>如何取得安全分數

如果您的組織有包含[Office 365 企業版](https://docs.microsoft.com/office365/enterprise/)、 [Microsoft 365 商務版](https://docs.microsoft.com/microsoft-365/business/)或 Office 365 商務進階版訂閱，且您具有[必要權限](#required-permissions)，您可以造訪檢視貴組織的安全分數[https://securescore.office.com](https://securescore.office.com). 

或者，您可以造訪安全性 & 合規性中心 ([https://protection.office.com](https://protection.office.com))，您可以在其中找到您目前的分數為您提供安全分數小工具。

![安全分數小工具](media/SecureScoreWidget-o365.png)

[] 小工具包括安全分數儀表板的連結。

![安全分數儀表板](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a>運作方式

安全分數會決定您接著使用 （例如 OneDrive、 SharePoint 和 Exchange） 哪些 Office 365 服務比較您的設定與 Microsoft 所建立的基線的活動。 您會看到如何為基礎的分數也對齊您的組織是安全性最佳做法。 您也會收到建議改善貴組織的分數時可採取的步驟。 
  
![在 Office 365 安全分數工具中的動作佇列](media/SecureScore-ActionsToTake.png)
  
安全分數會計算您根據您購買服務的分數。 例如，如果您只是購買 Exchange Online 計劃，您將不會計分 SharePoint Online 的安全性功能。 分數的分母是適用於您購買的產品的控制項的所有基準線的總和。 分數之分子是加總的所有控制項的已完成，或部分完成，以滿足該控制項的動作。

依序展開 [要深入了解哪些步驟來執行，它將會協助保護您的潛在威脅及多少指向您的分數會增加一旦您遵循建議的動作。
  
![Office 365 安全分數工具展開巨集指令](media/SecureScore-DetailedActionToTake.png)
  
若要查看您的動作影響貴組織的安全性，選取 [**分數 Analyzer** ] 索引標籤，檢閱您的歷程記錄。 
  
![Office 365 安全分數工具分數 Analyzer] 索引標籤](media/SecureScore-ScoreAnalyzer-7days.png)
  
下方圖表中，您會看到分數和動作的清單依類別。 
  
![圖形顯示所選取的資料點分數 Analyzer] 索引標籤上](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
您可以執行動作，會標示為 **[不計分]** 的和為您的組織，但未連線到安全分數，因為它們不會被記錄。  

在**分數分析器**] 頁面上，按一下 [資料點的特定一天，然後向下若要找出該日的已完成且未完成動作變更，請參閱捲動。 分數的計算一次每日 (大約 1:00 AM PST)。 如果您變更測量的巨集指令，分數會自動更新的下一天。 花費最多在 48 小時內的變更會反映在您的分數。

安全分數不 express 絕對的量值的方式可能您是要取得外洩。 它來表示您要採用可以位移正在外洩的風險的功能範圍。 您將不會外洩，以及安全分數不應該解譯成保證郵件可以以任何方法，可確保沒有任何服務。
 
## <a name="how-secure-score-helps"></a>安全分數如何協助

安全分數，您可以協助提升貴組織的安全性狀態 （其中有許多您已購買，但可能不知道） 的 Office 365 中使用的內建安全性功能。 深入了解這些功能可協助讓您和平您要將正確的步驟來防止威脅保護您的組織的想法。
  
但不只需要為其我們 word。 使用安全分數客戶過增加共進行五次超過不使用它的客戶其分數。 （其分數增加對應於其組織中正在使用的安全性功能）。
  
> [!NOTE]
> 安全分數不 express 絕對的量值的方式可能您是要取得外洩。 它來表示您要採用可以位移正在外洩的風險的控制項的程度。 您將不會外洩，以及安全分數不應該解譯成保證郵件可以以任何方法，可確保沒有任何服務。 
  
## <a name="required-permissions"></a>必要的權限

若要檢視和使用安全分數儀表板，您必須獲指派其中一個[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)中的下列角色：
- 全域管理員
- 計費系統管理員
- 使用者系統管理員
- 密碼管理員
- 安全性系統管理員
- 安全性讀取者
- Exchange 系統管理員
- SharePoint 系統管理員

 不會被指派系統管理員角色的使用者將無法存取安全分數。

## <a name="related-topics"></a>相關主題

[安全性儀表板概觀](security-dashboard.md)

[我有何種訂閱？](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)
