---
title: 部署 Office 365 應用程式的設定格式化的條件的 Access 應用程式控制項
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: o365-administration
localization_priority: Normal
description: 請遵循下列步驟來設定 Office 365 雲端應用程式的安全性設定格式化的條件 Access 應用程式控制項所控制的 Azure AD Office 365 應用程式。
ms.openlocfilehash: ba3980615815fa45b1385a67560cc635506e2c22
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2019
ms.locfileid: "30103288"
---
# <a name="deploy-conditional-access-app-control-for-office-365-apps"></a>部署 Office 365 應用程式的設定格式化的條件的 Access 應用程式控制項

|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |您在此處 ！  <br/> [下一步](ocas-session-policies.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |

請遵循下列步驟來設定 Office 365 雲端應用程式的安全性設定格式化的條件 Access 應用程式控制項所控制的 Azure AD Office 365 應用程式。

**步驟 1： [建立 Azure AD 條件式存取測試原則](#step-1-create-an-azure-ad-conditional-access-test-policy)**

**步驟 2： [使用中應用程式的原則範圍內的使用者登入](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**

**步驟 3： 如果您沒有在 Azure AD 中選取的內建的雲端應用程式安全性原則或您想要將原則套用至非精選應用程式 [設定進階的雲端應用程式安全性入口網站中的控制項](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)**

**步驟 4：[測試部署](#step-4-test-the-deployment)**

> [!IMPORTANT]
> 若要部署設定格式化的條件的 Access 應用程式控制項 for Office 365 應用程式，您需要有效 [的 Azure AD Premium P1 授權](https://docs.microsoft.com/azure/active-directory/license-users-groups) 以及 Office 365 雲端應用程式安全性授權。

## <a name="step-1-create-an-azure-ad-conditional-access-test-policy"></a>步驟 1： 建立 Azure AD 條件式存取測試原則 

1. 在 Azure Active Directory、 [ **安全性**] 下按一下 [ **設定格式化的條件**的存取。

2. 按一下 [ **新原則** 並建立新的原則。

3. 在 [測試原則、 **使用者**] 底下指派一個測試使用者或可用於初始登入和驗證的使用者。

4. 在測試原則、 **雲端應用程式**中指定您想要的應用程式到控制項具有設定格式化的條件的 Access 應用程式控制項。

5. [ **工作階段**，將原則設定為使用其中一個內建的原則 **只監視** 或 **封鎖下載**。選取 [ **使用自訂原則**或者 設定進階的原則中的雲端應用程式安全性入口網站。

6. 新增任何適用的 **條件指派** 或 **授與控制項** （選用）。

> ![Azure AD 條件式存取](media/image1.png)

## <a name="step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps"></a>步驟 2： 使用者登入的範圍設為應用程式中的原則 

您已建立原則之後，請登入該原則中設定每個應用程式。請確定您使用登入的原則中設定的使用者。確定至現有的工作階段的第一個正負號。

雲端應用程式安全性將同步處理原則的詳細資訊到其伺服器進行登入每個新的應用程式。這可能需要多達一分鐘。

## <a name="step-3-configure-advanced-controls-in-the-cloud-app-security-portal"></a>步驟 3： 設定進階的雲端應用程式安全性入口網站中的控制項 

上述的指示幫助您建立直接在 Azure AD 的內建的雲端應用程式安全性原則精選的應用程式。

若要設定的進階的原則，請建立 [存取原則](ocas-access-policies.md) 或 [工作階段原則](ocas-session-policies.md) Office 365 雲端應用程式安全性入口網站中。

### <a name="to-identify-devices-using-client-certificates-this-is-optional"></a>識別裝置使用 （這是選用的） 的用戶端憑證：

1. 移至 [設定商旅並選擇 [ **裝置識別碼**。

2. 上傳一或多個根或中繼憑證。

3. 憑證上傳之後，您可以建立存取原則及工作階段的原則根據 **裝置標記**及 **有效的用戶端憑證**。

![設定格式化的條件的 access 應用程式控制項裝置識別碼](media/image2.png)

> [!NOTE]
> 憑證只是來自使用者要求的工作階段符合使用有效的用戶端憑證篩選器原則。
> 
## <a name="step-4-test-the-deployment"></a>步驟 4： 測試部署 

1. 先登出任何現有的工作階段。然後，嘗試登入已成功部署每個應用程式。使用 Azure AD 中所設定的原則會比對的使用者登入。

2. 雲端應用程式安全性入口網站、 **調查**、 底下選取 [ **活動記錄檔**，並確定登入活動擷取每個應用程式。

3. 您可以依序按一下 [ **進階**] 上再使用 **來源相當於 [存取控制**來篩選篩選。

4. 建議您登入來自 managed 和 unmanaged 裝置的行動電話和桌面應用程式。這是確定活動會適當地擷取活動記錄檔中。若要確認已正確擷取活動，按一下 [單一登入登入活動上以便開啟活動抽屜。請確定 **使用者代理程式標記** 正確反映 [裝置是否 （這表示行動裝置或桌面應用程式） 的原生用戶端或裝置是否在受管理的裝置 （相容，網域加入，或有效的用戶端憑證）。

> [!NOTE]
> 部署之後，您無法移除應用程式的 [設定格式化的條件的 Access 應用程式 Control] 頁面。只要您不需要在應用程式設定的工作階段或存取原則，設定格式化的條件的 Access 應用程式控制項將不會變更任何應用程式的行為。

## <a name="next-steps"></a>後續步驟

- [深入了解 Office 365 雲端應用程式安全性的工作階段原則](ocas-session-policies.md)

- [深入了解 Office 365 雲端應用程式安全性存取原則](ocas-access-policies.md) 

- [將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理](group-your-ip-addresses-in-ocas.md)