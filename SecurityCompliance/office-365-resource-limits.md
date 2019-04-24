---
title: Office 365 資源限制
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 摘要： 資源的相關資訊的 Office 365 內的各種應用程式限制。
ms.openlocfilehash: d4315923ea1ab09e2e7651fb2fcaddb085871d4d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262405"
---
# <a name="resource-limits"></a>資源限制

使用配額 （限制） 與節流設定，會強制執行資源限制。 Azure Active Directory 和個別的 Office 365 服務使用兩者。 限制都是特定的服務，並變更經過一段時間，也會加入新功能。 如需各種服務的目前限制的詳細資訊，請參閱下列主題：
- [Azure Active Directory 服務限制及限制](https://msdn.microsoft.com/en-us/library/azure/dn764971.aspx)
- [Exchange Online 限制](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
- [Exchange Online Protection 限制](https://technet.microsoft.com/en-us/library/exchange-online-protection-limits.aspx)
- [SharePoint Online 的軟體界限及限制](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [Skype 商務限制](https://technet.microsoft.com/en-us/library/skype-for-business-online-limits.aspx)
- [Yammer REST API 和流量限制](https://developer.yammer.com/docs/rest-api-rate-limits)
- [在 Sway 中的檔案大小限制](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

除了這些限制，幾個節流機制可用整個 Azure Active Directory 和 Office 365。 在服務中的節流會特別重要，，假設在 Microsoft 資料中心的網路資源已針對廣泛使用之服務的客戶的進行最佳化。 節流機制包括：
- Azure Active Directory 和 Office 365 功能使用者層級節流，其中的交易或 （由指令碼或程式碼） 可以執行由單一使用者的並行通話數目限制。
- 此為預設節流原則的 PowerShell 被指派給在租用戶建立每個租用戶。 這些設定會影響其他項目，例如單一系統管理員所能開啟的同時 PowerShell 工作階段數目上限。
- 每個 Exchange Online 客戶已針對 EWS 用戶端作業，調整預設 Exchange Web 服務 (EWS) 原則和節流設定，套用至所有 Outlook 用戶端。
