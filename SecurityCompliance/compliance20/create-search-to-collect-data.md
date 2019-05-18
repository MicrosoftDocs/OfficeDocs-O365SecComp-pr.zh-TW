---
title: 建立搜尋以收集資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 360ba6a67d43a0b78b1104ae64885697009bb222
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155105"
---
# <a name="create-a-search-to-collect-data"></a><span data-ttu-id="915ec-102">建立搜尋以收集資料</span><span class="sxs-lookup"><span data-stu-id="915ec-102">Create a search to collect data</span></span>

<span data-ttu-id="915ec-103">在您的情況下的 [**搜尋**] 索引標籤上您可以按一下 [**新增搜尋**，並遵循精靈建立新的搜尋。</span><span class="sxs-lookup"><span data-stu-id="915ec-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

## <a name="name-your-search-and-give-description"></a><span data-ttu-id="915ec-104">命名您的搜尋，並提供說明</span><span class="sxs-lookup"><span data-stu-id="915ec-104">Name your search and give description</span></span>

<span data-ttu-id="915ec-105">每個搜尋與案例應該有唯一的名稱。</span><span class="sxs-lookup"><span data-stu-id="915ec-105">Each search with a case should have a unique name.</span></span> <span data-ttu-id="915ec-106">（選用） 您可以提供的描述您的搜尋。</span><span class="sxs-lookup"><span data-stu-id="915ec-106">You can optionally provide a description for your search.</span></span> 

## <a name="define-your-conditions"></a><span data-ttu-id="915ec-107">定義您的條件</span><span class="sxs-lookup"><span data-stu-id="915ec-107">Define your conditions</span></span>

<span data-ttu-id="915ec-108">您可以定義用於搜尋使用預先內建的條件卡或使用關鍵字查詢語言 (KQL) 條件。</span><span class="sxs-lookup"><span data-stu-id="915ec-108">You can define the conditions for your search using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="915ec-109">如需詳細資訊，請參閱 <<c0>建立搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="915ec-109">For more information, see [Build search queries](building-search-queries.md).</span></span>

## <a name="choose-the-custodians-to-search-from"></a><span data-ttu-id="915ec-110">選擇 [從搜尋 custodians</span><span class="sxs-lookup"><span data-stu-id="915ec-110">Choose the custodians to search from</span></span>

<span data-ttu-id="915ec-111">一旦您已經定義您的條件，您必須選擇您想要搜尋的位置。</span><span class="sxs-lookup"><span data-stu-id="915ec-111">Once you have defined your conditions, you need to choose which locations you want to search.</span></span> <span data-ttu-id="915ec-112">若要這樣做的其中一個方法是藉由指定您想要搜尋您已經新增至案例哪些 custodians。</span><span class="sxs-lookup"><span data-stu-id="915ec-112">One way to do it is by specifying which custodians you have already added to the case you want to search.</span></span> <span data-ttu-id="915ec-113">藉由選取 custodian，您將針對所有的資料來源對應至 custodian 執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="915ec-113">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="915ec-114">如需如何將 custodians 新增至您的案例及管理其資料來源詳細資訊，請參閱[Work with custodians](managing-custodians.md) 。</span><span class="sxs-lookup"><span data-stu-id="915ec-114">See [Work with custodians](managing-custodians.md) for more information on how to add custodians to your case and manage their data sources.</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="915ec-115">選擇 [非 custodial 位置</span><span class="sxs-lookup"><span data-stu-id="915ec-115">Choose non-custodial locations</span></span>

<span data-ttu-id="915ec-116">在某些情況下，您可能想要搜尋不會對應到 custodian 的資料來源。</span><span class="sxs-lookup"><span data-stu-id="915ec-116">In some cases, you may wish to search data sources that are not mapped to a custodian.</span></span> <span data-ttu-id="915ec-117">在此情況下，您可以指定您想要搜尋，或選擇搜尋特定的 Office 365 服務 （例如搜尋所有 Exchange 信箱或所有 SharePoint 和 OneDrive for Business 網站） 的所有內容位置的位置。</span><span class="sxs-lookup"><span data-stu-id="915ec-117">In this case, you can specify the locations you would like to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint and OneDrive for Business sites).</span></span>