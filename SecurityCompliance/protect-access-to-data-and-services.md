---
title: 保護使用者和裝置存取
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 保護 O365 資料與服務存取權的登陸頁面
ms.openlocfilehash: e1b529a641d25f82521c40d0df9d091e0ebb5d90
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32265225"
---
# <a name="protect-user-and-device-access"></a>保護使用者和裝置存取

保護您的 Office 365 資料與服務存取權是防禦網路攻擊與防止資料遺失而言很重要的。 同一種保護方式可套用至環境中的其他 SaaS 應用程式，甚至可在內部應用程式發佈與 Azure Active Directory 應用程式 Proxy。
  
## <a name="step-1-review-recommendations"></a>步驟 1： 檢閱建議

推薦可用於保護身分識別和裝置的功能，其可存取 Office 365、其他 SaaS 服務，以及與 Azure AD 應用程式 Proxy 一起發佈的內部部署應用程式。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多語言](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>步驟 2： 保護系統管理員帳戶和存取
您用於管理 Office 365 環境的管理帳戶包括提升的權限。 這些是有價值的目標的駭客和網路罪犯。 

開始使用系統管理員帳戶僅適用於管理。 系統管理員應該有個別的使用者帳戶一般，非系統管理員使用與僅使用其管理的帳戶時所需完成其工作職責相關聯的工作。

保護您的系統管理員帳戶具有多重要素驗證和條件式存取。 如需詳細資訊，請參閱[ Protecting 系統管理員帳戶](https://docs.microsoft.com/en-us/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts)。 

接下來，在 Office 365 中設定特殊權限的存取管理。 特殊權限存取管理可讓 Office 365 中的特殊權限的系統管理工作更精細的存取控制。 它可以協助保護您的組織可能使用現有的特殊權限的系統管理員帳戶具有常設存取權的敏感資料或存取重要的組態設定的外洩。

- [概觀權限存取管理](privileged-access-management-overview.md)
- [設定特殊權限存取管理](privileged-access-management-configuration.md)

其他上方的建議是使用工作站特別針對系統管理工作。 這些是僅適用於系統管理工作的專用的裝置。 請參閱[保護特殊存取權限](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access)。

最後，您可以在您的租用戶中建立兩個或多個緊急存取帳戶來降低不慎缺乏系統管理存取權的影響。 請參閱[在 Azure AD 中的管理緊急存取帳戶](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-emergency-access)。 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>步驟 3： 設定建議身分識別與裝置存取原則
多重要素驗證 (MFA) 和條件式存取原則是功能強大的工具針對遭入侵帳戶減輕和未經授權的存取。 我們建議您實作一群一起經過測試的原則。 如需詳細資訊，包括部署步驟，請參閱[身分識別與裝置存取設定](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations)。

 這些原則實作下列功能：
- 單行雙因素驗證
- 條件式存取
- Intune 應用程式防護 （應用程式和資料保護，裝置）
- Intune 裝置合規性
- Azure AD Identity Protection

Implemetning Intune 裝置合規性需要裝置註冊。 管理裝置，可讓您以確保它們的狀況良好且符合標準前環境中允許存取資源。 請參閱 <<c0>管理在 Intune 中註冊裝置

## <a name="step-4-configure-sharepoint-device-access-policies"></a>步驟 4： 設定 SharePoint 的裝置存取原則

Microsoft 建議您保護機密和高管制與裝置存取控制內容的 SharePoint 網站內容。 如需詳細資訊，請參閱 <<c0>保護 SharePoint 網站與檔案的原則建議。



    

