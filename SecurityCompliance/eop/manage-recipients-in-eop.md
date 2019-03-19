---
title: 管理 EOP 中的收件者
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
description: Microsoft Exchange Online Protection (EOP) 提供了數種方式供您管理郵件收件者。 身為管理員，您可以執行特定的管理工作，在 Exchange 系統管理中心 (EAC) 或使用遠端 Windows PowerShell，並驗證 Microsoft 365 系統管理中心中執行的其他管理工作。
ms.openlocfilehash: 52d423960444605382bd0314a5c12114fad755a2
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670398"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="d365e-104">管理 EOP 中的收件者</span><span class="sxs-lookup"><span data-stu-id="d365e-104">Manage recipients in EOP</span></span>

<span data-ttu-id="d365e-105">Microsoft Exchange Online Protection (EOP) 提供了數種方式供您管理郵件收件者。</span><span class="sxs-lookup"><span data-stu-id="d365e-105">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients.</span></span> <span data-ttu-id="d365e-106">身為管理員，您可以執行特定的管理工作，在 Exchange 系統管理中心 (EAC) 或使用遠端 Windows PowerShell，並驗證 Microsoft 365 系統管理中心中執行的其他管理工作。</span><span class="sxs-lookup"><span data-stu-id="d365e-106">As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="d365e-107">EOP 支援下列類型的收件者：</span><span class="sxs-lookup"><span data-stu-id="d365e-107">EOP supports the following types of recipients:</span></span>
  
- <span data-ttu-id="d365e-108">**郵件使用者** 郵件使用者是 EOP 受管理網域中的收件者。</span><span class="sxs-lookup"><span data-stu-id="d365e-108">**Mail Users** Mail users are recipients in your EOP managed domains.</span></span> <span data-ttu-id="d365e-109">這些收件者在您的 Office 365 組織中具有登入認證，但擁有外部電子郵件地址，這表示他們的收件者信箱位於您的雲端組織之外。</span><span class="sxs-lookup"><span data-stu-id="d365e-109">These recipients have logon credentials in your Office 365 organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization.</span></span> <span data-ttu-id="d365e-110">您可以新增郵件使用者，讓他們能夠接收郵件，您也可以建立郵件流程規則 （也稱為傳輸規則） 針對特定使用者。</span><span class="sxs-lookup"><span data-stu-id="d365e-110">You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users.</span></span> <span data-ttu-id="d365e-111">您也可以指派角色給組織中的郵件使用者，具有管理角色群組權限的使用者可以存取 Exchange 系統管理中心 (EAC) 並執行特定的管理工作。</span><span class="sxs-lookup"><span data-stu-id="d365e-111">You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks.</span></span> <span data-ttu-id="d365e-112">若要深入了解使用者角色，以及如何將 EOP 中的使用者角色指派，請參閱[管理系統管理員角色群組權限在 EOP 中](manage-admin-role-group-permissions-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="d365e-112">To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>
    
    <span data-ttu-id="d365e-113">如需在 EOP 中管理郵件使用者的相關資訊，請參閱[管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="d365e-113">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>
    
- <span data-ttu-id="d365e-114">**群組** 郵件使用者可一起分組到通訊群組或安全性群組中。</span><span class="sxs-lookup"><span data-stu-id="d365e-114">**Groups** Mail users can be grouped together into distribution groups or security groups.</span></span> 
    
    <span data-ttu-id="d365e-115">如需在 EOP 中管理群組的相關資訊，請參閱[管理 EOP 中的群組](manage-groups-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="d365e-115">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
    
<span data-ttu-id="d365e-p104">在尋找此主題的 Exchange Online 版本？請參閱[Recipients in Exchange Online](http://technet.microsoft.com/library/50d16941-5cd7-435d-8715-e2b69f8410ab.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d365e-p104">Looking for the Exchange Online version of this topic? See [Recipients in Exchange Online](http://technet.microsoft.com/library/50d16941-5cd7-435d-8715-e2b69f8410ab.aspx).</span></span>
  
<span data-ttu-id="d365e-p105">在尋找此主題的 Exchange Server 版本？請參閱[Recipients](http://technet.microsoft.com/library/40300ed4-85a5-463d-bb3a-cf787bd44e9d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d365e-p105">Looking for the Exchange Server version of this topic? See [Recipients](http://technet.microsoft.com/library/40300ed4-85a5-463d-bb3a-cf787bd44e9d.aspx).</span></span>
  

