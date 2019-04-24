---
title: Office 365 雲端 App 安全性中的存取原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Office 365 雲端 App 安全性存取原則啟用即時監視，並根據使用者、 位置、 裝置的雲端應用程式及應用程式的存取控制。 您可以建立任何裝置，包括未網域加入，並且不會管理 Windows Intune 推行至受管理的裝置的用戶端憑證或使用現有的憑證，例如協力廠商 MDM 憑證的裝置存取的原則。 例如，您可以部署至受管理的裝置、 用戶端憑證，而然後封鎖來自不使用憑證的裝置的存取。
ms.openlocfilehash: 5e8b8fa293420bc9ff3616daf288b8e02a2eb768
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263000"
---
# <a name="access-policies-in-office-365-cloud-app-security"></a>Office 365 雲端 App 安全性中的存取原則

|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |您在此處 ！  <br/> [下一步](group-your-ip-addresses-in-ocas.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |

Office 365 雲端 App 安全性存取原則啟用即時監視，並根據使用者、 位置、 裝置的雲端應用程式及應用程式的存取控制。 您可以建立任何裝置，包括未網域加入，並且不會管理 Windows Intune 推行至受管理的裝置的用戶端憑證或使用現有的憑證，例如協力廠商 MDM 憑證的裝置存取的原則。 例如，您可以部署至受管理的裝置、 用戶端憑證，而然後封鎖來自不使用憑證的裝置的存取。

而不是允許或封鎖存取完全， [工作階段](ocas-session-policies.md)原則 您可以允許存取時監視的工作階段及/或限制特定的工作階段的活動。

## <a name="prerequisites-to-using-access-policies"></a>若要使用存取原則的必要條件

- Azure AD Premium P1 授權

- 相關的應用程式應該是 [使用條件式存取應用程式控制部署](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)

-  [Azure AD 條件式存取原則](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 應具備將使用者重新導向至 Office 365 雲端 App 安全性，如下所示。

## <a name="create-an-azure-ad-conditional-access-policy"></a>建立 Azure AD 條件式存取原則

Azure Active Directory 條件式存取原則與 Cloud App Security 工作階段原則適用於搭配檢查每個使用者工作階段，並決定每個應用程式的原則。 若要在 Azure AD 中設定的條件式存取原則，請遵循此程序：

1. 設定 [Azure AD 條件式存取原則](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 與使用者或群組的使用者與您想要與條件式存取應用程式控制項的控制項的應用程式的工作分派。<br>附註： 已 [部署與條件式存取應用程式控制項](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)僅應用程式 將會受到此原則。

2. 將使用者路由傳送至 Office 365 雲端 App 安全性藉由選取 [ **使用條件式存取應用程式控制強制執行限制** 底下 **工作階段**。

## <a name="create-a-cloud-app-security-access-policy"></a>建立雲端 App 安全性存取原則

若要建立新的存取原則，請遵循此程序：

1. 在 [入口網站中，選取 **控制項** 後面接著 **原則**。

2. 在 [ **原則** ] 頁面上，按一下 [ **建立原則** 選取 **存取原則**。

3. 在 [ **存取原則** ] 視窗中，指派原則，例如 *封鎖來自未受管理的裝置存取*的名稱。

4. 在 [ **比對下列所有的活動** ] 區段的 [ **活動來源**]，選取要套用至該原則的其他活動篩選。 篩選包含下列選項：
    
    - **裝置標記**： 使用此篩選器來識別未受管理的裝置。
    
    - **位置**： 使用此篩選器來識別不明 （並因此風險） 的位置。
    
    - **IP 位址**： 使用此篩選條件來篩選每個 IP 位址] 或 [使用先前指派的 IP 位址標記。
    
    - **使用者代理程式標記**： 使用此篩選器啟用的啟發學習法來識別行動裝置和傳統型應用程式。 此篩選器可以設定為等於或不等於。 值應該比照您每個雲端應用程式的行動裝置和傳統型應用程式。

5. 在 [ **動作**] 下選取下列選項之一：
    
    - **允許**： 設定此巨集指令，明確允許存取根據您所設定的原則篩選器。
    
    - **封鎖**： 設定此巨集指令來明確封鎖根據您所設定的原則篩選器的存取。

6. 您可以 **建立的原則嚴重性與每個比對事件警示** 設定的警示限制並選取是否要為一封電子郵件及簡訊或警示。

## <a name="next-steps"></a>後續步驟

- [將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理](group-your-ip-addresses-in-ocas.md)