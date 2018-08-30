---
title: Office 365 資源限制
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 在 Office 365 中的各種應用程式限制資源的相關資訊。
ms.openlocfilehash: a2e7ef42f9bf224363f3b10a5e450d6127f11585
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527418"
---
# <a name="resource-limits"></a><span data-ttu-id="5a587-103">資源限制</span><span class="sxs-lookup"><span data-stu-id="5a587-103">Resource Limits</span></span>

<span data-ttu-id="5a587-p101">使用配額 （限制） 和節流強制執行資源限制。Azure Active Directory 和個別的 Office 365 服務使用兩者。限制都是特定的服務，並變更一段時間隨著增加新功能。如需各種服務的目前限制的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="5a587-p101">Resource limits are enforced using quotas (limits) and throttling. Azure Active Directory and the individual Office 365 services use both. Limits are service-specific and change over time as new capabilities are added. For details on the current limits for the various services, see the following topics:</span></span>
- [<span data-ttu-id="5a587-108">Azure Active Directory 服務限制及限制</span><span class="sxs-lookup"><span data-stu-id="5a587-108">Azure Active Directory service limits and restrictions</span></span>](https://msdn.microsoft.com/en-us/library/azure/dn764971.aspx)
- [<span data-ttu-id="5a587-109">Exchange Online 限制</span><span class="sxs-lookup"><span data-stu-id="5a587-109">Exchange Online Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
- [<span data-ttu-id="5a587-110">Exchange Online Protection 限制</span><span class="sxs-lookup"><span data-stu-id="5a587-110">Exchange Online Protection Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-protection-limits.aspx)
- [<span data-ttu-id="5a587-111">SharePoint Online 的軟體界限和限制</span><span class="sxs-lookup"><span data-stu-id="5a587-111">SharePoint Online software boundaries and limits</span></span>](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [<span data-ttu-id="5a587-112">如需商務限制 Skype</span><span class="sxs-lookup"><span data-stu-id="5a587-112">Skype for Business Limits</span></span>](https://technet.microsoft.com/en-us/library/skype-for-business-online-limits.aspx)
- [<span data-ttu-id="5a587-113">Yammer REST API 和人數上限</span><span class="sxs-lookup"><span data-stu-id="5a587-113">Yammer REST API and Rate Limits</span></span>](https://developer.yammer.com/docs/rest-api-rate-limits)
- [<span data-ttu-id="5a587-114">Sway 的檔案大小限制</span><span class="sxs-lookup"><span data-stu-id="5a587-114">File Size Limits in Sway</span></span>](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

<span data-ttu-id="5a587-p102">除了這些限制、 數個節流機制可用整個 Azure Active Directory 與 Office 365。在服務中節流特別重要的是，假設為廣泛使用的服務的客戶的最佳化網路資源的 Microsoft 資料中心。節流機制包括：</span><span class="sxs-lookup"><span data-stu-id="5a587-p102">In addition to these limits, several throttling mechanisms are used throughout Azure Active Directory and Office 365. Throttling within the service is especially important, given that network resources in Microsoft's datacenters are optimized for the broad set of customers that use the services. Throttling mechanisms include:</span></span>
- <span data-ttu-id="5a587-118">Azure Active Directory 與 Office 365 功能使用者層級節流，以限制的交易或 （依指令碼或程式碼） 單一使用者可以執行的並行通話數目。</span><span class="sxs-lookup"><span data-stu-id="5a587-118">Azure Active Directory and Office 365 feature user-level throttling, which limit the number of transactions or concurrent calls (by script or code) that can be performed by a single user.</span></span>
- <span data-ttu-id="5a587-p103">此為預設節流原則的 PowerShell 會指派給在承租人建立每個租用戶。這些設定會影響其他項目，例如單一的系統管理員所能開啟的同時 PowerShell 工作階段數目上限。</span><span class="sxs-lookup"><span data-stu-id="5a587-p103">A default PowerShell throttling policy is assigned to each tenant at tenant creation. These settings affect other items, such as the maximum number of simultaneous PowerShell sessions that can be opened by a single administrator.</span></span>
- <span data-ttu-id="5a587-121">每個的 Exchange Online 客戶有 EWS 用戶端作業，而調整預設 Exchange Web 服務 (EWS) 原則和節流會套用至所有的 Outlook 用戶端。</span><span class="sxs-lookup"><span data-stu-id="5a587-121">Each Exchange Online customer has a default Exchange Web Services (EWS) policy that is tuned for EWS client operations, and throttling that applies to all Outlook clients.</span></span>
