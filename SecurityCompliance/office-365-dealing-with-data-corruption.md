---
title: Office 365 處理資料損毀
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
description: 在 Office 365 和 Microsoft 的努力防護和復原的資料損毀的說明。
ms.openlocfilehash: 4997ec0efb60d4e62e3a385af8bbd1a610c5290a
ms.sourcegitcommit: f0d23e57b00f07cef5b1b2d366eaeeeacda37e3e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "35786698"
---
# <a name="dealing-with-data-corruption-in-office-365"></a><span data-ttu-id="65edf-103">處理 Office 365 中的資料損毀</span><span class="sxs-lookup"><span data-stu-id="65edf-103">Dealing with Data Corruption in Office 365</span></span>

<span data-ttu-id="65edf-104">下列其中一個執行大規模的雲端服務的一項挑戰層面是如何處理資料損毀，提供大量資料且獨立的系統。</span><span class="sxs-lookup"><span data-stu-id="65edf-104">One of the challenging aspects of running a large-scale cloud service is how to handle data corruption, given the large volume of data and independent systems.</span></span> <span data-ttu-id="65edf-105">可能會因資料損毀：</span><span class="sxs-lookup"><span data-stu-id="65edf-105">Data corruption can be caused by:</span></span>

- <span data-ttu-id="65edf-106">應用程式或基礎結構的錯誤，損毀部分或全部的應用程式的狀態</span><span class="sxs-lookup"><span data-stu-id="65edf-106">Application or infrastructure bugs, corrupting some or all of the application state</span></span>
- <span data-ttu-id="65edf-107">硬體問題，導致資料遺失或無法讀取資料</span><span class="sxs-lookup"><span data-stu-id="65edf-107">Hardware issues that result in lost data or an inability to read data</span></span>
- <span data-ttu-id="65edf-108">人類的作業錯誤</span><span class="sxs-lookup"><span data-stu-id="65edf-108">Human operational errors</span></span>
- <span data-ttu-id="65edf-109">惡意的駭客和挾的員工</span><span class="sxs-lookup"><span data-stu-id="65edf-109">Malicious hackers and disgruntled employees</span></span>
- <span data-ttu-id="65edf-110">在 [外部服務導致部分資料遺失的事件</span><span class="sxs-lookup"><span data-stu-id="65edf-110">Incidents in external services that result in some loss of data</span></span>

<span data-ttu-id="65edf-111">更高的恢復功能資料完整性表示較少的資料損毀事件，因為 Microsoft 已內建 Office 365 保護機制，以避免發生，以及系統及程序，讓我們如果是的話，復原資料損毀。</span><span class="sxs-lookup"><span data-stu-id="65edf-111">Because greater resiliency in data integrity means fewer data corruption incidents, Microsoft has built into Office 365 protection mechanisms to prevent corruption from happening, as well as systems and processes that enable us to recover data if it does.</span></span> <span data-ttu-id="65edf-112">檢查和處理程序存在於內工程發行程序增加對資料損毀的恢復能力的各種階段包括：</span><span class="sxs-lookup"><span data-stu-id="65edf-112">Checks and processes exist within the various stages of the engineering release process to increase resiliency against data corruption, including:</span></span>

- <span data-ttu-id="65edf-113">系統設計</span><span class="sxs-lookup"><span data-stu-id="65edf-113">System Design</span></span>
- <span data-ttu-id="65edf-114">程式碼部署組織與結構</span><span class="sxs-lookup"><span data-stu-id="65edf-114">Code organization and structure</span></span>
- <span data-ttu-id="65edf-115">程式碼檢閱</span><span class="sxs-lookup"><span data-stu-id="65edf-115">Code review</span></span>
- <span data-ttu-id="65edf-116">單元測試、 整合測試，以及系統測試</span><span class="sxs-lookup"><span data-stu-id="65edf-116">Unit tests, integration tests, and system tests</span></span>
- <span data-ttu-id="65edf-117">行程線路測試/門</span><span class="sxs-lookup"><span data-stu-id="65edf-117">Trip wires tests/gates</span></span>

<span data-ttu-id="65edf-118">在 Office 365 實際執行環境中，資料中心之間的對等網路複寫可確保有多份 live 的任何資料。</span><span class="sxs-lookup"><span data-stu-id="65edf-118">Within Office 365 production environments, peer replication between datacenters ensures that there are always multiple live copies of any data.</span></span> <span data-ttu-id="65edf-119">標準影像和指令碼可用來復原遺失的伺服器，並用來還原客戶資料複寫的資料。</span><span class="sxs-lookup"><span data-stu-id="65edf-119">Standard images and scripts are used to recover lost servers, and replicated data is used to restore customer data.</span></span> <span data-ttu-id="65edf-120">內建資料恢復檢查及處理程序，因為 Microsoft 的維護備份僅限 Office 365 資訊系統文件 （包括安全性相關的文件），使用 SharePoint Online 和內部程式碼中的內建複寫來源軍火庫存放庫工具。</span><span class="sxs-lookup"><span data-stu-id="65edf-120">Because of the built-in data resiliency checks and processes, Microsoft maintains backups only of Office 365 information system documentation (including security-related documentation), using built-in replication in SharePoint Online and our internal code repository tool, Source Depot.</span></span> <span data-ttu-id="65edf-121">系統文件儲存在 SharePoint Online 中，而且來源軍火庫包含系統和應用程式的影像。</span><span class="sxs-lookup"><span data-stu-id="65edf-121">System documentation is stored in SharePoint Online, and Source Depot contains system and application images.</span></span> <span data-ttu-id="65edf-122">SharePoint Online 與來源軍火庫使用版本設定，並且會複寫幾近即時。</span><span class="sxs-lookup"><span data-stu-id="65edf-122">Both SharePoint Online and Source Depot use versioning and are replicated in near real time.</span></span>
