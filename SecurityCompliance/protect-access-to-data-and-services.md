---
title: 保護 Office 365 中的資料與服務存取權
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 保護存取 O365 資料及服務的登陸頁面
ms.openlocfilehash: 652a14c5f1f29187aeac51355e7a924c9378806f
ms.sourcegitcommit: 15dfa0c83aa88816c18e30a44a49e36e733d952c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2018
ms.locfileid: "24011275"
---
# <a name="protect-access-to-data-and-services-in-office-365"></a>保護 Office 365 中的資料與服務存取權

保護您的 Office 365 資料及服務的存取很重要防禦適當攻擊及防範資料遺失。相同的保護設定可套用至您的環境中的其他 saas 和應用程式及偶數內部應用程式發佈與 Azure Active Directory 應用程式 Proxy。
  
## <a name="step-1-review-recommendations"></a>步驟 1： 檢閱建議

推薦可用於保護身分識別和裝置的功能，其可存取 Office 365、其他 SaaS 服務，以及與 Azure AD 應用程式 Proxy 一起發佈的內部部署應用程式。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多語言](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-configure-mfa"></a>步驟 2： 設定 MFA

使用您自己的方式放置到 MFA、 決定哪個版本最適合您，這些資源，然後規劃及部署 MFA 為您的環境。
  
- [什麼是 Azure 的多重要素驗證？](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [您選擇的 Azure 的多重要素驗證解決方案](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [如何取得 Azure 的多重要素驗證](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [規劃 Office 365 部署的多重要素驗證](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [設定 Office 365 使用者的多重要素驗證](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [規劃部署 MFA、 雲端或內部部署位置](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [設定 Azure 的多重要素驗證設定](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a>步驟 3： 強制 MFA 搭配 Azure AD 條件式存取規則

如果您使用 Azure AD MFA，建立 MFA 需要存取 Office 365 和您環境中的其他 saas 和應用程式的設定格式化的條件存取規則。
  
- [Azure Active Directory 中的設定格式化的條件存取](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-privileged-access-management"></a>步驟 4： 設定權限的存取管理

特殊存取權限管理 Office 365 中讓更精細的存取權限的管理工作的控制權。 它可協助保護您的組織中可以使用現有的權限的管理員帳戶具有出位置的存取權機密資料或重要的組態設定的存取權的缺口。

- [權限的概觀存取管理](privileged-access-management-overview.md)
- [設定權限的存取管理](privileged-access-management-configuration.md)

## <a name="step-5-configure-sharepoint-device-access-policies"></a>步驟 5： 設定 SharePoint 裝置存取原則

SharePoint Online 和 OneDrive for Business 的裝置存取原則建議進行保護機密、 機密、 和規範資料。即將推出則裝置存取原則套用至個別小組網站的能力。
  
- [從未受控裝置中控制存取權](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-6-configure-app-and-data-protection-for-devices"></a>步驟 6： 設定應用程式及資料保護裝置

您可以管理不論是否將裝置註冊的行動裝置管理的行動裝置上的應用程式。這會對意外 Office 365，包括郵件和檔案中的資料外洩保護。
  
- IOS 及 android （英文）：[保護應用程式資料 Microsoft intune 的應用程式保護原則 （英文）](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
    
對於 Windows 10 設定 Windows 資訊保護 (WIP) 以避免意外的資料外洩。
  
- 受管理的裝置：[建立與註冊原則使用 Azure 入口網站的 Microsoft Intune Windows 資訊保護 (WIP)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
    
- 未受管理的裝置：[建立及部署 Windows 資訊保護 (WIP) 應用程式保護原則 intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)
    
## <a name="step-7-manage-devices-with-intune"></a>步驟 7： 管理 intune 的裝置

管理裝置可讓您以確保其皆為正常且符合標準前環境中允許資源的存取權。裝置以設定格式化條件規則可協助您確保攻擊者無法存取您的資源來自未受管理的裝置的存取。
  
- [註冊裝置管理的 Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-8-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a>步驟 8： 設定其他 Intune 原則和您環境的條件式存取規則

使用下列建議設定為起點的企業規模或複雜的存取安全使用情況。
  
- [安全的電子郵件原則及組態](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    

