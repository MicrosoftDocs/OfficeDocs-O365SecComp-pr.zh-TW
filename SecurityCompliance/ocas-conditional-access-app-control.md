---
title: 使用 Office 365 雲端 App 安全性條件式存取應用程式控制來保護應用程式
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: 停止外洩和即時與 Office 365 雲端 App 安全性條件式存取應用程式控制項的外洩。
ms.openlocfilehash: d8370b1e02866db8f92ab7f6a46b06ddc3ed1055
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262985"
---
# <a name="protect-apps-with-office-365-cloud-app-security-conditional-access-app-control"></a>使用 Office 365 雲端 App 安全性條件式存取應用程式控制來保護應用程式

|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |您在此處 ！  <br/> [下一步](ocas-deploy-conditional-access-app-control.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |

在現今的工作場所，它是通常不不足，無法知道發生了什麼雲端環境中的事實之後。 您要停止外洩和外的洩即時，員工是刻意或出自放之前您的資料和貴組織的風險。 請務必讓雲端應用程式中進行大部分的工具與服務提供給他們，並讓他們將自己的裝置能夠在您的組織中使用者。 在此同時，您需要工具，以協助保護組織免於資料外洩，以及資料遭竊，即時。 Azure Active Directory，以及 Office 365 雲端 App 安全性會將這些功能傳遞全面性及整合的經驗與條件式存取應用程式控制項中。

> [!IMPORTANT]
> 若要使用雲端 App 安全性條件式存取應用程式控制，您需要 [Azure Active Directory P1 授權](https://azure.microsoft.com/pricing/details/active-directory/) 和作用中的[Office 365 雲端 App 安全性](office-365-cas-overview.md)訂閱。

## <a name="how-it-works"></a>運作方式

條件式存取應用程式控制使用反向 proxy 架構，且唯一整合與 Azure AD 條件式存取。 Azure AD 條件式存取可讓您以強制執行根據特定條件的貴組織的應用程式的存取控制。 條件定義 *誰* （使用者或群組的使用者） 和 *哪些* （雲端應用程式）， *其中* 條件式存取原則 （哪一個位置和網路） 套用至。 您已決定條件之後，您可以將使用者路由傳送至 Office 365 雲端 App 安全性可讓您保護資料的條件式存取應用程式控制藉由套用存取及工作階段的控制項。

條件式存取應用程式控制可讓使用者應用程式存取及監視和控制存取及工作階段的原則為基礎的即時工作階段。 存取及工作階段的原則可用內 Cloud App Security 入口網站來進一步調整篩選器及設定要對使用者採取的動作。 存取及工作階段的原則，您可以進行下列作業：

- **下載區塊**： 您可以封鎖的機密文件下載。 例如，在未受管理的裝置。

- **保護下載**： 而不是封鎖的機密文件下載，您可能需要透過加密下載受保護的文件]。 此加密可確保文件受到保護，如果資料已下載至不受信任裝置通過驗證使用者的存取。

- **監視低信任層級使用者工作階段**： 當他們登入應用程式和其動作會從記錄在工作階段中，會監視有風險的使用者。 您可以調查並分析使用者了解，並在哪些條件下工作階段應該將原則套用在未來的行為。

- **封鎖存取**： 您完全可以封鎖特定應用程式為使用者即將從受管理的裝置或非公司網路的存取。

- **建立唯讀模式**： 藉由監視及封鎖自訂應用程式內的活動，您可以建立針對特定使用者的特定應用程式以唯讀模式。

- **從非公司網路的限制使用者工作階段**： 允許使用者從不屬於您公司的網路位置存取受保護的應用程式限制] 存取權。 封鎖或受保護的敏感資料的下載。

### <a name="how-session-control-works"></a>工作階段控制的運作方式

使用條件式存取應用程式控制建立工作階段原則可讓您控制使用者工作階段所透過反向 proxy 而不是將使用者重新導向直接對應用程式。 之後，請於使用者要求和回應移到 Office 365 雲端 App 安全性，而不是直接對應用程式。

若要保留使用者的工作階段，所有相關的 Url，Java 指令碼，以及在應用程式工作階段中的 cookie 會取代與 Office 365 雲端 App 安全性 Url。 例如，如果應用程式會傳回其網域結尾 myapp.com 的連結] 頁面上，連結會取代以類似的網域： myapp.com.us.cas.ms

此方法不需要您安裝在裝置上的任何項目。 監視從未受控裝置的工作階段時，這個方法是理想。

工作階段會導向到 Office 365 雲端 App 安全性後，可以執行下列動作：

1. 檢查使用者活動的流量

2. 在 Office 365 雲端 App 安全性活動記錄檔中顯示的已識別的活動

3. 儲存流量記錄檔和分析

4. 啟用流量記錄匯出系統管理員

5. 在 [工作階段上強制執行原則

## <a name="managed-device-identification"></a>受管理的裝置識別碼

條件式存取應用程式控制可讓您建立原則，請考量是否或不受管理的裝置。 若要識別是否或不受管理的裝置，功能會使用：

- 符合規範的裝置

- 已加入網域的裝置

- 用戶端憑證部署

### <a name="compliant-and-domain-joined-devices"></a>相容] 和 [已加入網域的裝置

Azure AD 條件式存取讓相容和已加入網域的裝置資訊直接傳遞至 Office 365 雲端 App 安全性。 從那裡，存取原則或工作階段的原則可以開發做為篩選條件所使用的裝置狀態。 如需詳細資訊，請參閱 <<c0>Azure Active Directory 中的裝置管理的簡介。

### <a name="client-certificate-authenticated-devices"></a>用戶端憑證驗證裝置

裝置識別碼機制可要求從相關裝置使用用戶端憑證驗證。 您可以使用現有的用戶端憑證已部署在您的組織或首度發行新的用戶端憑證至受管理的裝置。 然後，您會使用這些憑證的目前狀態設定存取和工作階段的原則。 如需如何部署用戶端憑證的詳細資訊請參閱 <<c0>部署條件式應用程式的存取控制 Office 365 應用程式。

## <a name="supported-apps-and-clients"></a>支援的應用程式和用戶端

條件式存取應用程式控制項的 Office 365 支援下列精選的應用程式：

- Exchange Online （預覽）

- OneDrive for Business （預覽）

- Power BI （預覽）

- SharePoint Online （預覽）

- Microsoft Teams （預覽）

- Yammer （預覽）

其他應用程式正在持續在-boarded 工作階段控制。

## <a name="next-steps"></a>後續步驟

- [為 Office 365 應用程式部署條件式存取應用程式控制](ocas-deploy-conditional-access-app-control.md)

- [了解 Office 365 雲端 App 安全性中的工作階段原則](ocas-session-policies.md)

- [了解 Office 365 雲端 App 安全性中的存取原則](ocas-access-policies.md) 