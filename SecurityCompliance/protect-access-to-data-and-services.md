---
title: 保護使用者和裝置存取權
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 用於保護 O365 資料與服務存取權的登陸頁面
ms.openlocfilehash: 7cddedfbb5b0b7789f370f0445be167b6d4e187d
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852737"
---
# <a name="protect-user-and-device-access"></a>保護使用者和裝置存取權

保護您的 Office 365 資料與服務的存取, 對於防禦網路攻擊和防止資料遺失至關重要。 相同的保護可套用至您環境中的其他 SaaS 應用程式, 甚至適用于使用 Azure Active Directory 應用程式 Proxy 發佈的內部部署應用程式。
  
## <a name="step-1-review-recommendations"></a>步驟 1: 審閱建議

推薦可用於保護身分識別和裝置的功能，其可存取 Office 365、其他 SaaS 服務，以及與 Azure AD 應用程式 Proxy 一起發佈的內部部署應用程式。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多語言](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>步驟 2: 保護系統管理員帳戶和存取
您用來管理 Office 365 環境的系統管理帳戶包含更高的許可權。 這些是駭客和網路罪犯的極具價值的目標。 

使用僅供管理的系統管理員帳戶開始。 系統管理員應該要有個別的使用者帳戶, 以進行一般、非系統管理的使用, 並在必要時使用其管理帳戶, 以完成與工作函相關聯的工作。

使用多重要素驗證和條件式存取, 保護您的系統管理員帳戶。 如需詳細資訊, 請參閱[保護系統管理員帳戶](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts)。 

下一步, 設定 Office 365 的特殊許可權存取管理。 「許可權存取管理」可讓您在 Office 365 中對特權系統管理工作進行精細存取控制。 它可以協助保護您的組織不會因使用現有的特權系統管理員帳戶存取敏感性資料或存取重要的設定設定而遭到破壞。

- [許可權存取管理概述](privileged-access-management-overview.md)
- [設定特殊權限存取管理](privileged-access-management-configuration.md)

另一個主要建議是使用專為管理工作設定的工作站。 這些是僅用於系統管理工作的專用裝置。 請參閱[保護許可權存取](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)。

最後, 您可以在您的租使用者中建立兩個或多個緊急存取帳戶, 以減輕無意間缺乏系統管理存取的影響。 請參閱[管理 AZURE AD 中的緊急存取帳戶](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)。 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>步驟 3: 設定建議的身分識別和裝置存取原則
多重要素驗證 (MFA) 和條件式存取原則是功能強大的工具, 可降低受到破壞的帳戶和未經授權的存取。 建議您實施一組已一起測試的原則。 如需詳細資訊, 包括部署步驟, 請參閱身分[識別和裝置存取](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations)設定。

 這些原則會實施下列功能:
- 單行因素驗證
- 條件式存取
- Intune 應用程式保護 (裝置的應用程式和資料保護)
- Intune 裝置合規性
- Azure AD Identity Protection

Implemetning Intune 裝置合規性需要裝置註冊。 管理裝置可讓您在允許存取環境中的資源之前, 先確定這些裝置的狀況良好且相容性。 請參閱[在 Intune 中註冊裝置以進行管理](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>步驟 4: 設定 SharePoint 裝置存取原則

Microsoft 建議您使用裝置存取控制來保護具有敏感和高度管制內容的 SharePoint 網站中的內容。 如需詳細資訊, 請參閱[保護 SharePoint 網站和檔案的原則建議](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。



    

