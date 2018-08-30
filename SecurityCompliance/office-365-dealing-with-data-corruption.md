---
title: Office 365 處理資料損毀
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
description: 在 Office 365，以及 Microsoft 致力保護及復原資料損毀的說明。
ms.openlocfilehash: 087be23ce5dad1daf62357cb08e27c0a15962792
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526845"
---
# <a name="dealing-with-data-corruption-in-office-365"></a><span data-ttu-id="53d84-103">處理 Office 365 中的資料損毀</span><span class="sxs-lookup"><span data-stu-id="53d84-103">Dealing with Data Corruption in Office 365</span></span>

<span data-ttu-id="53d84-p101">執行大型雲端服務的面對方面的其中一個是如何處理資料損毀授與大量資料和獨立的系統。資料損毀可以所造成：</span><span class="sxs-lookup"><span data-stu-id="53d84-p101">One of the challenging aspects of running a large-scale cloud service is how to handle data corruption, given the large volume of data and independent systems. Data corruption can be caused by:</span></span>
- <span data-ttu-id="53d84-106">應用程式或基礎結構的錯誤、 損毀某些或所有的應用程式狀態</span><span class="sxs-lookup"><span data-stu-id="53d84-106">Application or infrastructure bugs, corrupting some or all of the application state</span></span> 
- <span data-ttu-id="53d84-107">硬體問題的結果中的資料遺失或無法讀取資料</span><span class="sxs-lookup"><span data-stu-id="53d84-107">Hardware issues that result in lost data or an inability to read data</span></span> 
- <span data-ttu-id="53d84-108">人工作業錯誤</span><span class="sxs-lookup"><span data-stu-id="53d84-108">Human operational errors</span></span> 
- <span data-ttu-id="53d84-109">惡意駭客和挾名員工</span><span class="sxs-lookup"><span data-stu-id="53d84-109">Malicious hackers and disgruntled employees</span></span> 
- <span data-ttu-id="53d84-110">在 [外部服務導致部分資料遺失的事件</span><span class="sxs-lookup"><span data-stu-id="53d84-110">Incidents in external services that result in some loss of data</span></span> 

<span data-ttu-id="53d84-p102">在資料完整性更彈性表示較少資料損毀事件，因為 Microsoft 具有內建以避免發生，以及系統及程序可讓我們若是如此復原資料從損毀的 Office 365 保護機制。檢查和處理程序存在於內不同增加對資料損毀恢復工程版本程序的階段包括：</span><span class="sxs-lookup"><span data-stu-id="53d84-p102">Because greater resiliency in data integrity means fewer data corruption incidents, Microsoft has built into Office 365 protection mechanisms to prevent corruption from happening, as well as systems and processes that enable us to recover data if it does. Checks and processes exist within the various stages of the engineering release process to increase resiliency against data corruption, including:</span></span>
- <span data-ttu-id="53d84-113">系統設計</span><span class="sxs-lookup"><span data-stu-id="53d84-113">System Design</span></span>
- <span data-ttu-id="53d84-114">程式碼組織與結構</span><span class="sxs-lookup"><span data-stu-id="53d84-114">Code organization and structure</span></span> 
- <span data-ttu-id="53d84-115">程式碼檢閱</span><span class="sxs-lookup"><span data-stu-id="53d84-115">Code review</span></span> 
- <span data-ttu-id="53d84-116">單元測試、 整合測試及系統測試</span><span class="sxs-lookup"><span data-stu-id="53d84-116">Unit tests, integration tests, and system tests</span></span>
- <span data-ttu-id="53d84-117">來回線路測試/閘道</span><span class="sxs-lookup"><span data-stu-id="53d84-117">Trip wires tests/gates</span></span> 

<span data-ttu-id="53d84-p103">Office 365 的實際執行環境中資料中心之間的對等複寫可確保該一律多份 live 任何資料。標準圖像和指令碼可用來復原遺失的伺服器和複寫的資料用來還原客戶資料。內建資料恢復檢查和程序，因為 Microsoft 維護備份僅限 Office 365 資訊系統文件 （包括安全性相關的文件） 使用 SharePoint Online 和我們內部的程式碼中的內建複寫來源軍火庫儲存機制工具。系統文件儲存在 SharePoint Online 和來源軍火庫包含系統和應用程式的圖像。SharePoint Online 和來源軍火庫使用版本設定與中複寫幾近即時地。</span><span class="sxs-lookup"><span data-stu-id="53d84-p103">Within Office 365 production environments, peer replication between datacenters ensures that there are always multiple live copies of any data. Standard images and scripts are used to recover lost servers, and replicated data is used to restore customer data. Because of the built-in data resiliency checks and processes, Microsoft maintains backups only of Office 365 information system documentation (including security-related documentation), using built-in replication in SharePoint Online and our internal code repository tool, Source Depot. System documentation is stored in SharePoint Online, and Source Depot contains system and application images. Both SharePoint Online and Source Depot use versioning and are replicated in near real-time.</span></span> 