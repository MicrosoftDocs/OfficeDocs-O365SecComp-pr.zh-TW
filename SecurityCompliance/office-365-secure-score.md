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
description: 屬於不知道如何安全您的組織是這麼 in Office 365？安全的分數以下是可協助。安全的分數分析您的組織安全性根據規則活動和 Office 365 中的安全性設定並指派分數。
ms.openlocfilehash: dd0dc87910853eba9f2ec3ec6752e857462b46e5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220353"
---
# <a name="office-365-secure-score"></a>Office 365 安全分數

**摘要**屬於不知道如何安全您的組織是這麼 in Office 365？安全的分數以下是可協助。安全的分數分析您的組織安全性根據規則活動和 Office 365 中的安全性設定並指派分數。請閱讀本篇文章以取得安全分數和使用它的概觀。
  
## <a name="how-to-get-to-secure-score"></a>如何取得至安全的分數

如果您的組織有包含[Office 365 企業版](https://docs.microsoft.com/office365/enterprise/)、 [Microsoft 365 商務](https://docs.microsoft.com/microsoft-365/business/)或 Office 365 企業進階版訂閱且您具有[必要權限](#required-permissions)，您可以檢視您組織的安全分數造訪[https://securescore.office.com](https://securescore.office.com). 

或者，您可以瀏覽安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com)) 中，您將在此找到您目前的分數可提供安全分數 widget。

![安全的分數 widget](media/SecureScoreWidget-o365.png)

Widget 包含安全分數儀表板的連結。

![安全的分數儀表板](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a>運作方式

安全的分數會決定為何您再使用 （例如 OneDrive、 SharePoint 及 Exchange） 的 Office 365 服務比較您的設定和由 Microsoft 建立的基線的活動。您將取得如何為基礎的分數妥善對齊貴組織會使用安全性的最佳作法。您也將取得建議上以提升您的組織分數所能採取的步驟。 
  
![在 Office 365 安全分數工具動作佇列](media/SecureScore-ActionsToTake.png)
  
安全的分數計算您根據您所購買的服務的分數。例如，如果只有購買 Exchange Online 計劃，您將不會計分 SharePoint Online 的安全性功能。分數的分母為套用到您所購買的產品控制項的所有比較基準的總和。分子是的總和的所有控制項的已完成，或部分完成，以滿足該控制項的動作。

依序展開 [要了解功能所需，它將會協助保護您的威脅步驟並多少指引您分數會增加之後遵循建議的動作。
  
![在 Office 365 安全分數工具擴充巨集指令](media/SecureScore-DetailedActionToTake.png)
  
若要查看您的動作的影響在貴組織的安全性，選取 [**分數分析**] 索引標籤和檢閱您的歷程記錄。 
  
![Office 365 安全分數工具的分數分析] 索引標籤](media/SecureScore-ScoreAnalyzer-7days.png)
  
圖表下方您將了依類別排列的分數和動作的清單。 
  
![顯示所選取的資料點分數分析] 索引標籤上的圖形](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
您的組織，可以執行會標示為 **[不計分]** 是類的動作，但因為他們未連線至安全的分數，不計分。  

**分數分析器**頁面上，按一下 [資料點特定的工作日的然後向下若要深入了解應那天的已完成並不完整動作已變更，請參閱捲動。分數的計算每天一次 (筆 1:00 AM PST)。如果您變更測量巨集指令，分數會自動更新的後一天。延長最多達 48 小時變更，以便反映在您的分數。

安全的分數不 express 絕對的量值的方式有可能您所要取得達到。它來表示您要採用功能可以位移要達到的風險的程度。沒有服務可確保您將無法達到、 和安全分數不應該解譯成保證郵件以任何方法。
 
## <a name="how-secure-score-helps"></a>如何協助保護分數

使用安全的分數，有助於提高貴組織的安全性狀態 （其中有許多已附加元件購買，但可能不知道） 的 Office 365 中使用的內建的安全性功能。深入了解這些功能可協助提供和平的記住您正在進行保護您的組織從威脅右邊的步驟。
  
但是不只是我們 word 針對它。使用安全分數的客戶看過增加五次以上客戶不使用其分數。（其分數增加對應於目前用於組織的安全性功能）。
  
> [!NOTE]
> 安全的分數不 express 絕對的量值的方式有可能您所要取得達到。它來表示您要採用控制項可以位移要達到的風險的程度。沒有服務可確保您將無法達到、 和安全分數不應該解譯成保證郵件以任何方法。 
  
## <a name="required-permissions"></a>必要權限

若要檢視及使用安全分數儀表板，您必須指派一個[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)中的下列角色：
- 全域管理員
- 計費管理員
- 使用者系統管理員
- 密碼管理員
- 安全性管理員
- 安全性讀者
- Exchange 系統管理員
- SharePoint 管理員

 未指派的管理角色的使用者將無法存取 Secure 分數。

## <a name="related-topics"></a>相關主題

[安全性儀表板概觀 （英文)](security-dashboard.md)

[我有何種訂閱？](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)
