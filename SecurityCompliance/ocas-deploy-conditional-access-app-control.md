---
title: 為 Office 365 應用程式部署條件式存取應用程式控制
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: 請遵循下列步驟來設定 Azure AD Office 365 應用程式連接至 Office 365 雲端 App 安全性條件式存取應用程式控制加以控制。
ms.openlocfilehash: 72be95b3213b90cfe60d851d0852d465cdbe6ef9
ms.sourcegitcommit: 866d8cab6bcfdd124516a8369e47ec797bc7cf8a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/27/2019
ms.locfileid: "30312070"
---
# <a name="deploy-conditional-access-app-control-for-office-365-apps"></a>為 Office 365 應用程式部署條件式存取應用程式控制

|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |您在此處 ！  <br/> [下一步](ocas-session-policies.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |

請遵循下列步驟來設定 Azure AD Office 365 應用程式連接至 Office 365 雲端 App 安全性條件式存取應用程式控制加以控制。

**步驟 1： [建立 Azure AD 條件式存取測試原則](#step-1-create-an-azure-ad-conditional-access-test-policy)**

**步驟 2： [使用中應用程式的原則的範圍限定在使用者登入。](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**

**步驟 3： 如果您未在 Azure AD 中選取的內建的雲端 App 安全性原則，或如果您想要將原則套用至非精選應用程式， [設定進階 Cloud App Security 入口網站中的控制項](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)**

**步驟 4：[測試部署](#step-4-test-the-deployment)**

> [!IMPORTANT]
> 若要部署條件式存取應用程式控制 Office 365 應用程式，您需要有效的 [授權 Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) 以及 Office 365 雲端 App 安全性授權。

## <a name="step-1-create-an-azure-ad-conditional-access-test-policy"></a>步驟 1： 建立 Azure AD 條件式存取測試原則 

1. 在 Azure Active Directory，在 [ **安全性**] 下按一下 [ **條件式**存取]。

2. 按一下 [ **新增原則** 並建立新的原則。

3. 在測試原則] 之下 **的使用者**，將指派的測試使用者或使用者可以用於初始登入和驗證。

4. 在測試原則] 之下 **雲端應用程式**，請將您想要的應用程式指派給與條件式存取應用程式控制項的控制項。

5. [ **工作階段**中，將原則設定為使用其中一個內建的原則， **只有監視器** 或 **封鎖下載**。 或選取 [ **使用自訂原則** Cloud App Security 入口網站中設定的進階的原則。

6. 新增任何適用的 **條件指派** 或 **授與控制項** （選用）。

> ![Azure AD 條件式存取](media/image1.png)

## <a name="step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps"></a>步驟 2： 使用中應用程式的原則的範圍限定在使用者登入 

您建立原則之後，登入該原則中設定每個應用程式。 請確定您使用登入的原則中設定的使用者。 請確定第一個現有的工作階段登出。

Cloud App Security 會同步處理原則的詳細資訊，其伺服器的登入每個新的應用程式。 這可能需要長達 1 分鐘。

## <a name="step-3-configure-advanced-controls-in-the-cloud-app-security-portal"></a>步驟 3： 設定進階 Cloud App Security 入口網站中的控制項 

上述的指示可以幫助您直接在 Azure AD 中建立內建 Cloud App Security 原則精選應用程式。

若要設定的進階的原則，請建立 [存取原則](ocas-access-policies.md) 或 [工作階段原則](ocas-session-policies.md) 在 Office 365 雲端 App 安全性入口網站中。

### <a name="to-identify-devices-using-client-certificates-this-is-optional"></a>若要識別裝置使用 （這是選用的） 的用戶端憑證：

1. 移至設定商旅，然後選擇 [ **裝置識別碼**。

2. 上傳一或多個根 ca 或中繼憑證。

3. 憑證上傳之後，您可以建立存取原則和工作階段的原則，根據 **裝置標記**及 **有效的用戶端憑證]**。

![條件式存取應用程式控制項的裝置識別碼](media/image2.png)

> [!NOTE]
> 只有，從使用者來要求憑證，如果工作階段符合使用有效的用戶端憑證篩選器原則。
> 
## <a name="step-4-test-the-deployment"></a>步驟 4： 測試部署 

1. 任何現有的工作階段中第一個登出。 然後，嘗試登入已成功部署每個應用程式。 使用以符合設定 Azure AD 中的原則的使用者登入。

2. 在 Cloud App Security 入口網站中，[ **調查]**，選取 **活動記錄檔**，並確定每個應用程式擷取登入活動。

3. 您可以篩選上的 [ **進階**]，然後使用 **來源等於存取控制**進行篩選。

4. 建議您登入從 managed 和 unmanaged 裝置的行動裝置和傳統型應用程式。 這是為了確保活動會正確擷取活動記錄檔中。 若要確認正確擷取活動，請按一下單一登入功能登入活動，讓它會開啟活動抽屜。 請確定 **使用者代理程式標記** 正確地反映 [裝置是否 （亦即行動裝置或桌面應用程式） 的原生用戶端或裝置是受管理的裝置 （相容，網域加入，或有效的用戶端憑證）。

> [!NOTE]
> 部署之後，您無法移除應用程式，從 [條件式存取應用程式控制] 頁面。 只要您不需要在應用程式上設定工作階段或存取原則，條件式存取應用程式控制也不會變更任何應用程式的行為。

## <a name="next-steps"></a>後續步驟

- [了解 Office 365 雲端 App 安全性中的工作階段原則](ocas-session-policies.md)

- [了解 Office 365 雲端 App 安全性中的存取原則](ocas-access-policies.md) 

- [將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理](group-your-ip-addresses-in-ocas.md)