---
title: 特殊權限存取 Office 365 中管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: 若要深入了解權限使用本主題存取 Office 365 中的管理
ms.openlocfilehash: 2a464bacaa568515e470e29a0c9c45a91a79cf8e
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001246"
---
# <a name="privileged-access-management-in-office-365"></a>特殊權限存取 Office 365 中管理

> [!IMPORTANT]
> 本主題涵蓋功能目前僅適用於 Office 365 E5 和進階合規性 Sku 的部署和設定指導。

特殊權限存取管理可讓 Office 365 中的特殊權限的系統管理工作更精細的存取控制。 它可以協助保護您的組織可能使用現有的特殊權限的系統管理員帳戶具有常設存取權的敏感資料或存取重要的組態設定的外洩。 啟用特殊權限的存取管理之後, 使用者必須要求完成提升權限和特殊權限的工作，透過核准工作流程的高度範圍中的時間繫結的剛-時間存取權。 這可以讓使用者剛充份-存取執行工作的而不致曝露機密資料或重要的組態設定。 啟用 Office 365 中的特殊權限的存取管理，可讓您的組織來操作以零常設權限，並提供一層的防禦引起因為這類常設系統管理存取權的弱點。

整合式的客戶加密箱和特殊權限的存取管理端對端工作流程的快速概觀，請參閱此[客戶加密箱和 Office 365 影片中的特殊權限的存取管理](https://go.microsoft.com/fwlink/?linkid=2066800)。

## <a name="layers-of-protection"></a>保護層級

特殊權限存取管理輔助其他資料與存取權的功能保護 Office 365 安全性架構內。 藉由啟用安全性整合式方法的一部分的特殊權限的存取管理和保護您的組織，一種層次的安全性模型可用來最大化保護敏感資訊和 Office 365 組態設定。 如圖所示下方，啟用特殊權限存取管理有助於為基礎提供原生 Office 365 資料加密與 Office 365 服務角色型存取控制安全性模型的保護。 當[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)搭配使用，這兩項功能提供剛時間存取在不同範圍的存取控制。

![在 Office 365 中的分層的保護](media/pam-layered-protection.png)

特殊權限存取管理 Office 365 中的可以定義和 Azure AD Privileged Identity Management 套用**角色**層級的保護，能夠執行多個任務時，在**任務**層級範圍。  Azure AD 有權限身分識別管理主要允許管理 AD 角色和角色群組的存取，則 Office 365 中的管理特殊權限存取時套用只在任務層級。

- **啟用特殊權限存取 Office 365 中的管理已使用 Azure AD Privileged Identity Management 時：** 在 Office 365 中新增特殊權限的存取管理提供另一個的細微層級的特殊權限存取 Office 365 的資料保護和稽核功能。

- **啟用 Azure AD Privileged Identity Management 時已經在使用特殊權限存取管理 Office 365 中：** 將 Azure AD Privileged Identity Management 新增至權限存取管理 Office 365 中的可以延伸至主要由使用者的角色或身分識別所定義的 Office 365 外部資料的特殊權限的存取。  

## <a name="privileged-access-management-architecture-and-process-flow"></a>特殊權限的存取管理架構和處理程序流程

下列程序流程的每個大綱架構的特殊權限的存取和 Office 365 substrate、 與 Office 365 稽核]，Exchange 管理 runspace 的互動方式。

### <a name="step-1-configuring-a-privileged-access-policy"></a>步驟 1： 設定特殊權限的存取原則

設定時使用的[Microsoft 365 系統管理中心](https://admin.microsoft.com)或 Exchange Management PowerShell 的特殊權限的存取原則，您建立，並定義原則和特殊權限的存取功能處理 Office 365 substrate 中的原則屬性和登入 Office 365 安全性與合規性中心的活動。 原則現已啟用，並準備好處理傳入要求核准。

![步驟 1-建立原則](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>步驟 2： 存取要求

使用[Microsoft 365 系統管理中心](https://admin.microsoft.com)或 Exchange Management PowerShell，使用者可以要求存取較高權限或特殊權限的工作。 特殊權限的存取功能會將要求傳送至已設定特殊權限存取原則和記錄的 Office 365 安全性與合規性中心的記錄檔中的活動的處理 Office 365 substrate。

![步驟 2-存取要求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>步驟 3： 存取權核准

產生核准要求，並核准群組通知電子郵件的擱置的要求。 授與核准時，如果特殊權限的存取要求處理核准為且工作已完成。 如果拒絕要求時，會封鎖工作，並沒有存取權授與給要求者。 要求者將會收到通知的要求核准或拒絕透過電子郵件訊息。

![步驟 3-存取權核准](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>步驟 4： 存取處理

核准要求，會由 Exchange 管理 runspace 處理工作。 核准是針對特殊權限的存取原則檢查，且由 Office 365 substrate 處理。 任務的所有活動會都記錄在 Office 365 安全性與合規性中心。

![步驟 4-Access 處理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a>若要使用 Office 365 的特殊權限的存取是否需要何種 Sku？
特殊權限存取管理目前只適用於使用 Office 365 E5 和進階合規性 Sku 的客戶。

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a>何時將特殊權限的存取可供 Exchange 以外的 Office 365 工作負載？
我們要推出提供此功能在其他 Office 365 工作負載。 當我們已準備好要共用的時間表時，則可透過[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。

### <a name="my-organization-needs-more-than-30-privileged-access-polices-will-this-limit-be-increased"></a>我的組織需要多個 30 的特殊權限的存取原則時，會增加此限制？

我們計劃來增加每個 Office 365 組織推出 30 特殊權限的存取原則的目前限制。

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>是否需要是全域系統管理員來管理 Office 365 中的特殊權限的存取？
否，您必須具有 Exchange 角色管理 」 角色指派給將管理特殊權限的存取 Office 365 中的帳戶。 不過，全域系統管理員角色包含此角色依預設，並可用來管理特殊權限的存取，如果您不想要設定為獨立的帳戶權限的角色管理角色。 包含在核准者群組的使用者不需要是全域系統管理員或具有 「 角色管理角色指派進行審核及核准要求。

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>如何為客戶加密箱與相關的 Office 365 中的特殊權限的存取管理？
[Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests)可讓組織由其服務提供者，也就是 Microsoft 的資料存取的存取控制層級。 特殊權限存取 Office 365 中的管理可讓更精細的存取控制組織內部的 Office 365 特殊權限的所有工作。
