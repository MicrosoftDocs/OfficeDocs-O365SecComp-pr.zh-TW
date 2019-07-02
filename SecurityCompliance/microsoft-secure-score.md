---
title: Microsoft 安全分數
description: 說明 microsoft 365 安全性中心內的 Microsoft 安全分數、如何計算詳細資料, 以及安全性系統管理員可以預期使用何種方式。
keywords: 安全性、惡意程式碼、Microsoft 365、M365、安全分數、安全性中心、改進動作
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 27a9d137bde0dd23be8824d94a25364f89706563
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852777"
---
# <a name="microsoft-secure-score"></a>Microsoft 安全分數

>[!IMPORTANT]
>某些資訊與 prereleased 產品相關, 可能會在正式發行之前充分修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

透過 microsoft 365 安全中心的 Microsoft 安全分數, 您可以更深入地瞭解及控制組織的安全性狀況。 您可以從集中式儀表板監視和改善 Microsoft 365 身分識別、資料、應用程式、裝置及基礎結構的安全性。

Microsoft 安全分數為您提供穩健的視覺效果、與其他 Microsoft 產品的整合、與其他公司的分數比較、依類別篩選, 以及更多。 透過工具, 您可以在組織內完成安全性改進動作, 並追蹤分數的歷程記錄。 分數也可以反映協力廠商解決方案如何解決建議的改進動作。  

## <a name="how-it-works"></a>運作方式

您可以指定點來設定建議的安全性功能、執行安全性相關工作 (例如查看報表), 或使用協力廠商應用程式或軟體來解決改善動作。 部分完成的某些動作會分數, 例如為您的使用者啟用多重要素驗證 (MFA)。 安全性應始終與可用性平衡, 而不是每個建議適用于您的環境。

## <a name="required-permissions"></a>必要的權限

目前, 若要查看 Microsoft 安全分數, 您必須在 Azure Active Directory 中指派下列其中一個角色:

* 全域管理員
* 安全性系統管理員
* 安全性讀取器

## <a name="rich-experiences--additional-security-recommendations"></a>豐富的體驗 & 其他安全性建議

在 Microsoft 安全分數中, 我們已新增 Azure AD、Intune 和 Cloud App 安全性的建議, 並提供來自 Azure Security Center 和 Microsoft Defender ATP 的建議。 我們也新增更多 Office 365 安全性建議。 深入瞭解更多的 Microsoft 產品和服務集合, 讓您能夠自信地報告您組織的安全性健康情況的管理。 您也可以使用[Microsoft GRAPH API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta)取得分數。

為了協助您更快速地瞭解所需的資訊, Microsoft 建議會組織成群組:

* 身分識別 (您的 Azure AD 帳戶和角色的保護狀態)
* 資料 (Office 365 檔的保護狀態)
* 裝置 (您的裝置的保護狀態;Microsoft Defender ATP 改進動作即將推出)
* 應用程式 (您的電子郵件和雲端應用程式的保護狀態)
* 基礎結構 (您的 Azure 資源的保護狀態; 即將推出)

在 [Microsoft 安全分數總覽] 頁面中, 您可以看到各群組之間的分割點, 以及可用的點數。 [總覽] 頁面也是取得整體分數、安全分數與基準比較的歷史趨勢, 以及可用於改善分數的優先順序改進動作的完整視圖的位置。 您可以使用此資料來採取動作, 並對安全性狀況產生很大的差異。  

![M365 首頁](./media/secure-score/homepage-original.png)
*圖 1: Microsoft 安全分數概覽頁面*

## <a name="take-action-to-improve-your-score"></a>採取動作以提升分數

[改進動作] 索引標籤會列出所有適用于租使用者的安全性建議及其狀態 (已完成、未完成、透過協力廠商解決, 以及被忽略)。 您可以搜尋、篩選及群組所有控制項。  排名是以 Microsoft 評估安全性價值和完成工作為基礎。

Microsoft 安全分數不會追蹤標為 [未計分] 的動作。 您仍然可以採取動作, 但完成它們不會影響您的分數。 如果在未來的 Microsoft 安全分數會追蹤某個動作, 而且您已經完成, 您的安全分數就會自動反映所做的變更。

當您按一下 [改善動作] 時, 會顯示 [飛出] 動作。 若要完成此動作, 您有幾個選項:

1. 選取 [**查看設定**], 以移至 [設定] 畫面並進行變更。 接著, 您將會看到需要採取動作的點, 會在飛出的頂端顯示。最多可能需要24小時才能更新點數。

2. 選取 [**透過協力廠商解析**], 因為已由協力廠商應用程式或軟體解決 [改善] 動作。 您可以取得該動作值得的要點, 讓您的安全分數更清楚反映整體安全性狀況。 如果協力廠商不再涵蓋該控制項, 您可以將 [改善] 動作標示為 [未完成]。 請記住, 如果 [改善] 動作被標示為透過協力廠商解決, 則 Microsoft 將無法看到分數需求是否符合。

3. 選取 [**略**過], 因為您已決定接受風險, 而不會制定改進動作。 一旦您略過 [改善] 動作, 您可以達到的安全分數點總數將會降低。 您可以在 [歷程記錄] 中查看此動作或隨時復原。

4. 選取 [**審閱**], 因為 [改善] 動作需要您定期檢查環境的一部分, 以取得和保留點數。 例如, 應每週檢查信箱轉寄規則, 以確保資料不會從您的網路進行挾帶。 您不需要進行任何變更, 但是需要執行一項動作。 如果您定期查看規則, 您會收到點數。 如果不是, 分數會降低。

![M365 首頁](./media/secure-score/secure-score1x450.png) ![M365 首頁](./media/secure-score/secure-score2x450.png)

*圖 2 & 3: 改進動作 flyouts*

## <a name="monitor-improvements-over-time"></a>監視一段時間的改進

您可以在 [歷程**記錄**] 索引標籤中, 在一段時間內, 查看組織分數的圖形。此視圖包含全域平均、行業平均和類似的座位元數目, 以及所選時間範圍內採取的所有動作。 您也可以自訂日期範圍和依類別篩選。

分數每日計算一次 (大約 1:00 AM PST)。 如果您變更已測量的動作, 分數將會自動更新到下一天。 另外請注意, 其他一些入口網站會顯示部分的 Microsoft 安全分數 (如 Microsoft Defender 安全中心)。 如果您完成改進動作, 而這些入口網站的得分增加, 最多可能需要24小時才會在 Microsoft 365 安全中心顯示更新的分數。  

## <a name="how-improvement-actions-are-scored"></a>改進動作的計分方式

大部分都是以二進位方式計分-當您執行 [改善] 動作時, 會取得 100% 的點數, 例如建立新的原則或開啟特定的設定。 對於其他改進動作, 會以占總設定的百分比來指定點數。 例如, 如果您使用多重要素驗證來保護所有使用者, 且僅有5個100的使用者受到保護, 則會有30個分數。您會獲得2點的部分分數 (5 個受保護的/100 總計 * 30 個最大值 = 2)。 分數部分分數)。

## <a name="risk-awareness"></a>風險感知

Microsoft 安全分數是根據系統設定、使用者行為及其他安全性相關測量的安全性狀況的數位摘要;這不是您的系統或資料會遭到破壞的絕對測量。 相反地, 它代表您在 Microsoft 環境中採用安全性控制的程度, 可協助抵消違反風險。 任何線上服務都無法防止安全性違規, 而且安全分數不應該解釋為以任何方式防範安全性違規。

## <a name="we-want-to-hear-from-you"></a>我們想要聽到您的來信

如果您有任何問題, 請在[安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社區中張貼, 讓我們知道。 我們正在監視社區, 並提供協助。
