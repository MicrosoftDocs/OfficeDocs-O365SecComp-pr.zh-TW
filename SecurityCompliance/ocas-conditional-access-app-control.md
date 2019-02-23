---
title: 使用 Office 365 雲端 App 安全性條件式存取應用程式控制來保護應用程式
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: O365-seccomp
localization_priority: Normal
description: 停止缺口和遺漏即時與 Office 365 雲端應用程式的安全性設定格式化的條件存取應用程式的控制項。
ms.openlocfilehash: 23c4b29e86eb8ba92cfa8a544d6484965ec6372b
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217083"
---
# <a name="protect-apps-with-office-365-cloud-app-security-conditional-access-app-control"></a>使用 Office 365 雲端 App 安全性條件式存取應用程式控制來保護應用程式

|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](ocas-deploy-conditional-access-app-control.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |

在今天的工作場所不常足夠知道有什麼新鮮事雲端環境中的事實之後。您想要停止缺口和即時，遺漏之前員工有意或無意放入您的資料與您組織在風險。請務必讓使用者在組織中的最大的服務和工具提供給他們的雲端應用程式]，讓它們將他們自己的裝置能夠運作。同時，您需要的工具來協助保護您的組織從資料外洩和資料竊取、 即時。Azure Active Directory 與 Office 365 雲端應用程式安全性會將這些功能全面性及整合經驗中具有設定格式化的條件的 Access 應用程式控制項。

> [!IMPORTANT]
> 若要使用雲端應用程式的安全性設定格式化的條件存取應用程式的控制項，您需要 [Azure Active Directory P1 授權](https://azure.microsoft.com/pricing/details/active-directory/) 和使用中的[Office 365 雲端應用程式安全性](office-365-cas-overview.md)訂閱。

## <a name="how-it-works"></a>運作方式

設定格式化的條件的 Access 應用程式控制項使用反向 proxy 架構及唯一整合 Azure AD 設定格式化的條件的存取權。Azure AD 的設定格式化的條件存取可讓您強制執行在您的組織根據特定條件的應用程式的存取控制。條件定義 *誰* （使用者群組) 與 *何種* （雲端應用程式） 和 *位置* （哪一個位置和網路） 的設定格式化的條件存取原則套用至。判斷條件之後，您可路由使用者給 Office 365 雲端應用程式安全性您可以在其中保護套用存取及工作階段控制項具有設定格式化的條件的 Access 應用程式控制項的資料。

設定格式化的條件的 Access 應用程式控制可讓使用者應用程式存取及監視及控制存取及工作階段的原則為基礎的即時工作階段。存取及工作階段的原則可用的雲端應用程式安全性入口網站中進一步調整篩選器並設定在使用者要採取的動作。Access 與工作階段的原則，您可以進行下列作業：

- **在下載區塊**： 您可以封鎖機密文件下載。例如，在未受管理的裝置。

- **下載保護**： 而不是封鎖下載 （英文） 的機密文件，您可能需要透過下載加密保護的文件]。此加密可確保受保護的文件與使用者存取通過驗證如果資料下載到不受信任的裝置。

- **監視低信任層級使用者工作階段**： Risky 使用者登入應用程式和其動作會從記錄在工作階段時受監控。您可以調查並分析使用者了解，以及哪些的情況下工作階段原則應套用未來的行為。

- **封鎖存取**： 您可以完全封鎖使用者即將從未受管理的裝置或非公司網路的特定應用程式的存取權。

- **建立唯讀模式**： 監視與封鎖自訂應用程式中的活動，您可建立的特定使用者的特定應用程式以唯讀模式。

- **Restrict 來自非公司網路的使用者工作階段**： 允許使用者存取的受保護的應用程式不屬於您公司的網路位置的限制] 存取權。下載 （英文） 的機密運送已封鎖或受保護。

### <a name="how-session-control-works"></a>工作階段控制的運作方式

建立工作階段原則與設定格式化的條件的 Access 應用程式控制項可讓您控制使用者工作階段所透過反向 proxy 而不是將使用者重新導向直接給應用程式。然後起使用者要求和回應移到 Office 365 雲端應用程式安全性而不是直接以應用程式。

若要讓使用者在工作階段，所有相關的 Url、 Java 指令碼和應用程式工作階段中的 cookie 已取代為 Office 365 雲端應用程式安全性 Url。例如，如果應用程式會傳回具有以 myapp.com 結尾之網域的連結] 頁面上，連結會取代以類似如下的網域： myapp.com.us.cas.ms

此方法不需要您在裝置上安裝任何項目。監視研討會未受管理裝置時理想此方法。

工作階段導向到 Office 365 雲端應用程式安全性之後，您可以選擇下列動作：

1. 檢查使用者活動的流量

2. Office 365 雲端應用程式安全性活動記錄檔中顯示的已識別的活動

3. 儲存流量記錄及分析它們

4. 讓管理員可以將匯出的流量記錄檔

5. 在工作階段強制施行原則

## <a name="managed-device-identification"></a>受管理的裝置識別碼

設定格式化的條件的 Access 應用程式控制項可讓您建立或不受管理的裝置是否必須考量事項的原則。若要識別是否或不受管理的裝置，會使用此功能：

- 相容的裝置

- 已加入網域的裝置

- 用戶端憑證部署

### <a name="compliant-and-domain-joined-devices"></a>符合且已加入網域的裝置

Azure AD 的設定格式化的條件存取讓符合且已加入網域的裝置資訊直接傳遞至 Office 365 雲端應用程式安全性。如此，存取原則] 或 [工作階段原則可以被開發篩選器所使用的裝置狀態。如需詳細資訊，請參閱 [在 Azure Active Directory 中的裝置管理的簡介](https://docs.microsoft.com/azure/active-directory/device-management-introduction)。

### <a name="client-certificate-authenticated-devices"></a>用戶端憑證驗證裝置

裝置識別碼機制可從相關裝置使用用戶端憑證要求驗證。您也可以使用現有的用戶端憑證已經進行了部署在您的組織或聯播 （英文） 新的用戶端憑證以受管理的裝置。然後您使用這些憑證的顯示狀態設定存取與工作階段的原則。如需如何部署用戶端憑證請參閱 [部署設定格式化的條件應用程式的存取控制 Office 365 應用程式](ocas-deploy-conditional-access-app-control.md)。

## <a name="supported-apps-and-clients"></a>支援的應用程式及用戶端

Office 365 的設定格式化的條件 Access 應用程式控制項支援下列精選應用程式：

- Exchange Online （預覽）

- OneDrive for Business （預覽）

- Power BI （預覽）

- SharePoint Online （預覽）

- （預覽） 的 Microsoft 小組

- Yammer （預覽）

其他應用程式均已持續在-boarded 工作階段控制。

## <a name="next-steps"></a>後續步驟

- [為 Office 365 應用程式部署條件式存取應用程式控制](ocas-deploy-conditional-access-app-control.md)

- [深入了解 Office 365 雲端應用程式安全性的工作階段原則](ocas-session-policies.md)

- [深入了解 Office 365 雲端應用程式安全性存取原則](ocas-access-policies.md) 