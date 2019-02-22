---
title: Microsoft 安全分數
description: 說明 Microsoft 365 安全分數、 詳細資料的計算方式，以及哪些安全性管理員可預期使用它。
keywords: 安全性、 惡意程式碼、 Microsoft 365、 M365、 安全分數、 安全性中心、 改進動作
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: de3abe7ca0e84efd2412984e172202d8f3962476
ms.sourcegitcommit: 9d48b656406e916e93651352692c5c6bcbbd645f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2019
ms.locfileid: "30203711"
---
# <a name="microsoft-secure-score-preview"></a>Microsoft 安全分數 （預覽）

與 Microsoft 安全分數 Microsoft 365 安全性中心] 中，您可以有增加可見性與控制能力貴組織的安全性狀態。您可以從集中式儀表板來監視及提升您的 Microsoft 365 身分識別、 資料、 應用程式、 裝置和基礎結構的安全性。

Microsoft 安全分數提供強大的視覺效果、 整合與其他 Microsoft 產品，您與其他公司、 類別及其他眾多功能所篩選的分數的比較。與工具]，您可以在組織內完成安全性改進動作及追蹤您的分數的歷程記錄。分數也可反映協力廠商解決方案時已解決建議的改進動作。  

## <a name="how-it-works"></a>運作方式

您所指定點設定建議的安全性功能執行安全性相關工作 （例如檢視報表），或處理與協力廠商應用程式或軟體的改進巨集指令。有些動作被計分的部分完成時，例如啟用使用者的多重要素驗證 (MFA)。安全性應一律平衡搭配和可用性，並不是每個建議可讓您環境的運作。

## <a name="required-permissions"></a>必要權限

目前檢視 Microsoft 安全分數，您必須被指派給其中一個 Azure Active Directory 中的下列角色：

* 全域管理員
* 安全性管理員
* 安全性讀者

## <a name="rich-experiences--additional-security-recommendations"></a>Rtf 經驗 & 其他安全性建議

Microsoft 安全分數，我們已新增建議從 Azure AD Intune，與雲端應用程式安全性]，從 Azure 安全性中心和 Windows 防禦者 ATP 即將推出的建議。我們也已新增更多 Office 365 安全性建議。額外的見解與多個可見性廣泛的 Microsoft 產品和服務，您可以信心最多個管理組織的安全性狀況詳細報告。您也可以取得您使用[Microsoft Graph API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta)的分數。

為了協助您更快速地所需的資訊，Microsoft 建議來組織成群組：

* 身分識別 （保護狀態的 Azure AD 的帳戶和角色）
* 資料 （Office 365 文件的保護狀態）
* 裝置的 [您的裝置 ； （保護狀態Windows 防禦者 ATP 改進動作即將推出）
* 應用程式 （您的電子郵件和雲端應用程式中的保護狀態）
* 基礎結構 （Azure 資源的保護狀態 ； 即將推出）

在 Microsoft 安全分數概觀] 頁面上，您可以看到如何分割點是這些群組與何種點可用之間。[概觀] 頁面上也是要取得的總分數的基準比較與您安全分數歷史趨勢全部向上檢視的位置及排列優先順序改進可以改善您分數採取的動作。您可以使用此資料採取動作並進行的安全性狀態的重大差異。  

![M365 首頁](./media/secure-score/homepage-original.png)
*圖 1： Microsoft 安全分數概觀] 頁面上*

## <a name="take-action-to-improve-your-score"></a>執行動作以提升您的分數

改進動作] 索引標籤列出所有的安全性建議適用於您的租用戶 （完成、 未完成、 解析透過協力廠商和略過） 及其狀態。您可以搜尋、 篩選和群組的所有控制項。 排名根據 Microsoft 的評估安全性值及完成的工作。

標示為 [不計分] 動作並不會追蹤由 Microsoft 安全分數。您仍然可以採取動作，但完成其不會影響您的分數。如果巨集指令會變成未來追蹤由 Microsoft 安全分數，您已經完成其安全的分數會自動反映變更。

當您按一下 [改進巨集指令時，會出現飛入]。若要完成動作，您有幾個選項：

1. 選取 [**檢視設定**移 [設定] 畫面並進行變更。然後將會如何因應動作是值得、 上方的飛入可見的點。點可能需要 24 小時的時間來更新。

2. 選取 [**透過協力廠商解決**因為由協力廠商應用程式或軟體的改進動作已解決。您會讓您安全分數更妥善地反映您的整體安全性狀況的入侵動作是值得、 點。如果第三方不再涵蓋控制項，您可以標示為未完成的改進巨集指令。請記住，Microsoft 會有任何可見性如果改進巨集指令會標示成解析透過協力廠商是否符合分數需求。

3. 因為您已決定要接受風險和不制訂改進巨集指令選取**略過**。一旦您搜尋時忽略改進巨集指令，總數安全可獲得分數點會降低。您可以在歷程記錄中檢視此巨集指令或復原任何時候。

4. 選取 [**檢閱**因為改進動作要求您定期檢閱您的環境以獲得除點的一部分。例如，轉接規則的信箱應檢閱可確保資料不已從您的網路 exfiltrated 每週為基礎。您不需要進行任何變更，但巨集指令將需要執行。如果您定期檢閱的規則，您會收到資料點。如果不是，會降低分數。

![M365 首頁](./media/secure-score/secure-score1x450.png) ![M365 首頁](./media/secure-score/secure-score2x450.png)

*圖表 2 & 3： 改進動作延伸顯示*

## <a name="monitor-improvements-over-time"></a>一段時間的監視器增強功能

您可以在一段時間**歷程記錄**] 索引標籤中檢視您組織的分數的圖形。此檢視包含全域平均、 產業平均和類似的基座計數，以及在所選的時間範圍內所採取的所有動作。您也可以自訂日期範圍及篩選依類別排列。

分數的計算每天一次 (筆 1:00 AM PST)。如果您變更測量巨集指令，分數會自動更新的後一天。它也務必注意其他入口網站的顯示 （例如 Windows 防禦者安全性中心） 的 Microsoft 安全分數部分。如果您完成改進巨集指令與分數增加這些入口網站中，可能需要 24 小時的時間的 Microsoft 365 安全性中心中顯示的更新分數。  

## <a name="risk-awareness"></a>風險傳達方式

Microsoft 安全分數為數值摘要安全性狀況根據系統設定、 使用者的行為與其他安全性相關的測量值 ；它不是將會如何可能達到系統或資料絕對測量。而是它所代表之您採用安全性控制 Microsoft 環境中可協助位移要達到的風險程度。沒有線上服務已完全免於安全性缺口和安全分數不應該解譯成保證郵件可以針對任何方式的安全性缺口。

## <a name="we-want-to-hear-from-you"></a>我們想要從您聽到

如果您有任何問題，請我們知道[安全性、 隱私權 & 規範](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社群中的張貼。我們正在監視社群，並將提供協助。