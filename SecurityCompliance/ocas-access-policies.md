---
title: Office 365 雲端 App 安全性中的存取原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Office 365 雲端應用程式安全性存取原則啟用即時監視和存取使用者、 位置、 裝置為基礎的雲端應用程式及應用程式的控制權。您可以建立任何裝置，包括不網域加入，並啟用受管理的裝置的用戶端憑證或使用現有的憑證，例如協力廠商 MDM 憑證未受 Windows Intune 的裝置存取的原則。例如，您可以部署用戶端憑證以受管理的裝置，然後封鎖來自沒有憑證的裝置存取。
ms.openlocfilehash: a8651cb51419c93998f2ce6e176fab7c1651b6ea
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219773"
---
# <a name="access-policies-in-office-365-cloud-app-security"></a>Office 365 雲端 App 安全性中的存取原則

|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](group-your-ip-addresses-in-ocas.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |

Office 365 雲端應用程式安全性存取原則啟用即時監視和存取使用者、 位置、 裝置為基礎的雲端應用程式及應用程式的控制權。您可以建立任何裝置，包括不網域加入，並啟用受管理的裝置的用戶端憑證或使用現有的憑證，例如協力廠商 MDM 憑證未受 Windows Intune 的裝置存取的原則。例如，您可以部署用戶端憑證以受管理的裝置，然後封鎖來自沒有憑證的裝置存取。

而不是允許或封鎖存取完全、 [工作階段的原則](ocas-session-policies.md)與 您可以監視工作階段和/或限制特定的工作階段活動時允許存取。

## <a name="prerequisites-to-using-access-policies"></a>若要使用存取原則的必要條件

- Azure AD Premium P1 授權

- 相關的應用程式應該是 [部署與設定格式化的條件的 Access 應用程式控制項](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)

-  [Azure AD 條件式存取原則](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 應該將使用者重新導向至 Office 365 雲端應用程式安全性] 的位置如下所示。

## <a name="create-an-azure-ad-conditional-access-policy"></a>建立 Azure AD 條件式存取原則

Azure Active Directory 設定格式化的條件存取原則與雲端應用程式安全性工作階段的原則中運作 tandem 檢查每個使用者工作階段並決定每個應用程式的原則。若要在 Azure AD 設定條件式存取原則，請遵循此程序：

1. 設定 [Azure AD 條件式存取原則](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 使用者或群組的使用者與您想要使用設定格式化的條件的 Access 應用程式控制項的控制項的應用程式的工作分派。<br>請注意： 唯一的應用程式已 [部署與設定格式化的條件的 Access 應用程式控制項](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad) 將會受到此原則。

2. 選取 [ **使用設定格式化的條件存取應用程式控制強制執行限制**路由使用者傳送至 Office 365 雲端應用程式安全性 下 **工作階段**。

## <a name="create-a-cloud-app-security-access-policy"></a>建立雲端應用程式安全性存取原則

若要建立新的存取原則，請遵循此程序：

1. 在 [入口網站中，選取 **控制項** 後面 **的原則**。

2. 在 [ **原則** ] 頁面上，按一下 [ **建立原則** 並選取 [ **存取原則**。

3. 在 [ **存取原則** ] 視窗中，指派為您的原則，例如 *封鎖從未受管理的裝置存取*的名稱。

4. 在 **符合下列所有的活動** ] 區段的 [ **活動來源**，請選取要套用至原則的其他活動篩選器。篩選包含下列選項：
    
    - **裝置標記**： 使用此篩選器來識別未受管理的裝置。
    
    - **位置**： 使用此篩選器來識別不明 （與因此 risky） 的位置。
    
    - **IP 位址**： 使用此篩選來篩選每個 IP 位址] 或 [使用先前指派的 IP 位址標記。
    
    - **使用者代理程式 tag**： 使用此篩選器以啟用大概識別行動裝置與桌面應用程式。此篩選器可以設定為等於或不等於。值應比照您各個雲端應用程式的行動電話和桌面應用程式。

5. [ **動作**] 下選取下列選項之一：
    
    - **允許**： 設定為明確允許根據您所設定的原則篩選器來存取此巨集指令。
    
    - **封鎖**： 設定為明確封鎖根據您所設定的原則篩選器來存取此巨集指令。

6. 您可以 **建立原則的嚴重性與每個相符的事件通知** 設定提醒的限制並選取您要做為電子郵件、 文字訊息或這兩者的警示。

## <a name="next-steps"></a>後續步驟

- [將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理](group-your-ip-addresses-in-ocas.md)