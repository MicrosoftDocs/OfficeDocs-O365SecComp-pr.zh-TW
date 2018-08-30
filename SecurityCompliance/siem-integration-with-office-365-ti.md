---
title: Office 365 威脅情報的 SIEM 整合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
description: 整合您的組織 SIEM server 與 Office 365 威脅智慧使用 Office 365 活動管理 API。
ms.openlocfilehash: 82aeeea53bf87f1555fa68b2784b8fe38a435e15
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527008"
---
# <a name="siem-integration-with-office-365-threat-intelligence"></a><span data-ttu-id="f1f20-103">Office 365 威脅情報的 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="f1f20-103">SIEM integration with Office 365 Threat Intelligence</span></span>

<span data-ttu-id="f1f20-p101">如果貴組織要使用安全性事件及事件管理 (SIEM) 伺服器，您可以使用 SIEM server 整合 Office 365 威脅智慧。這可讓您檢視的資訊，例如偵測到的 Office 365 威脅智慧、 您 SIEM server 報告中的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="f1f20-p101">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Threat Intelligence with your SIEM server. This enables you to view information, such as malware detected by Office 365 Threat Intelligence, in your SIEM server reports.</span></span>
  
## <a name="use-the-office-365-activity-management-api"></a><span data-ttu-id="f1f20-106">使用 Office 365 活動管理 API</span><span class="sxs-lookup"><span data-stu-id="f1f20-106">Use the Office 365 Activity Management API</span></span>

<span data-ttu-id="f1f20-p102">若要整合 Office 365 威脅智慧 SIEM 伺服器，可以使用 Office 365 活動管理 API。此 API 貴組織的 Office 365 和 Azure AD 活動的記錄檔從擷取使用者、 管理、 系統及原則動作和事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f1f20-p102">To integrate Office 365 Threat Intelligence with your SIEM server, use the Office 365 Activity Management API. This API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure AD activity logs.</span></span> 
  
<span data-ttu-id="f1f20-109">您必須是 Office 365 全域管理員或具有安全性管理員角色指派安全性&amp;規範中心。</span><span class="sxs-lookup"><span data-stu-id="f1f20-109">You must be an Office 365 global administrator or have the security administrator role assigned in the Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="f1f20-110">請參閱[Office 365 管理活動 API 參考 （英文）](https://msdn.microsoft.com/en-us/office-365/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="f1f20-110">See [Office 365 Management Activity API reference](https://msdn.microsoft.com/en-us/office-365/office-365-management-activity-api-reference).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f1f20-111">相關主題</span><span class="sxs-lookup"><span data-stu-id="f1f20-111">Related topics</span></span>

[<span data-ttu-id="f1f20-112">Office 365 威脅情報</span><span class="sxs-lookup"><span data-stu-id="f1f20-112">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="f1f20-113">防範 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="f1f20-113">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="f1f20-114">Office 365 安全性權限&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="f1f20-114">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

