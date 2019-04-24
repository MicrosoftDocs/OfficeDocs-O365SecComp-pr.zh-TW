---
title: 適用於 Project Server 的 GDPR
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: 深入了解如何在內部部署 Project Server 中解決 GDPR 需求。
ms.openlocfilehash: 67097cdab4fdab31537cf4b6dd27ce17234c2bdc
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255281"
---
# <a name="gdpr-for-project-server"></a><span data-ttu-id="5aaf0-103">適用於 Project Server 的 GDPR</span><span class="sxs-lookup"><span data-stu-id="5aaf0-103">GDPR for Project Server</span></span>

<span data-ttu-id="5aaf0-p101">Project Server 會使用自訂指令碼來匯出及編輯 Project Web App 中的使用者資料。基本程序為：</span><span class="sxs-lookup"><span data-stu-id="5aaf0-p101">Project Server uses custom scripts to export and redact user data in Project Web App. The basic process is:</span></span>

1.  <span data-ttu-id="5aaf0-106">在您的伺服器陣列中尋找 Project Web App 網站。</span><span class="sxs-lookup"><span data-stu-id="5aaf0-106">Find the Project Web App sites in your farm.</span></span>

2.  <span data-ttu-id="5aaf0-107">在包含使用者的每個網站中尋找專案。</span><span class="sxs-lookup"><span data-stu-id="5aaf0-107">Find the projects in each site that contain the user.</span></span>

3.  <span data-ttu-id="5aaf0-108">匯出及檢閱您想要檢閱的資料類型。</span><span class="sxs-lookup"><span data-stu-id="5aaf0-108">Export and review the types of data that you want to review.</span></span>

4.  <span data-ttu-id="5aaf0-109">視需要編輯資料。</span><span class="sxs-lookup"><span data-stu-id="5aaf0-109">Redact data as needed.</span></span>

<span data-ttu-id="5aaf0-110">下列文章會詳細說明這些步驟：</span><span class="sxs-lookup"><span data-stu-id="5aaf0-110">These steps are covered in detail in the following articles:</span></span>

- [<span data-ttu-id="5aaf0-111">從 Project Server 匯出使用者資料</span><span class="sxs-lookup"><span data-stu-id="5aaf0-111">Export user data from Project Server</span></span>](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [<span data-ttu-id="5aaf0-112">從 Project Server 刪除使用者資料</span><span class="sxs-lookup"><span data-stu-id="5aaf0-112">Delete user data from Project Server</span></span>](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


<span data-ttu-id="5aaf0-p102">請注意，Project Server 是以 SharePoint Server 為基礎來建置的，並且會將事件記錄到 SharePoint ULS 記錄和使用狀況資料庫。如需詳細資訊，請參閱 [SharePoint Server 的 GDPR](gdpr-for-sharepoint-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5aaf0-p102">Note that Project Server is built on top of SharePoint Server and logs events to the SharePoint ULS logs and Usage database. See [GDPR for SharePoint Server](gdpr-for-sharepoint-server.md) for more information.</span></span>
