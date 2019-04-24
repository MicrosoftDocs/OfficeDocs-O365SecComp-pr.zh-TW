---
title: 使用 Office 365 雲端 App 安全性建立 App 探索報告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: 使用 Office 365 雲端 App 安全性，可讓您了解您組織中的人員如何使用 Office 365 和其他應用程式來建立報告。
ms.openlocfilehash: 23165a52a09e5bcde46ee3ab2110dc17d0faf7f4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259634"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a><span data-ttu-id="eab84-103">使用 Office 365 雲端 App 安全性建立 App 探索報告</span><span class="sxs-lookup"><span data-stu-id="eab84-103">Create app discovery reports using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="eab84-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="eab84-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="eab84-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="eab84-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="eab84-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="eab84-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="eab84-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="eab84-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="eab84-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="eab84-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="eab84-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="eab84-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="eab84-110">開始部署</span><span class="sxs-lookup"><span data-stu-id="eab84-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="eab84-111">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="eab84-111">You are here!</span></span>  <br/> [<span data-ttu-id="eab84-112">後續步驟</span><span class="sxs-lookup"><span data-stu-id="eab84-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="eab84-113">Office 365 雲端 App 安全性，有助於全域系統管理員、 安全性系統管理員，並深入了解到組織中的人員所使用的雲端服務安全性讀取者。</span><span class="sxs-lookup"><span data-stu-id="eab84-113">Office 365 Cloud App Security helps global administrators, security administrators, and security readers gain insight into the cloud services people in an organization are using.</span></span> <span data-ttu-id="eab84-114">例如，您可以看到其中使用者會儲存在文件上共同作業並多少資料上傳至應用程式或外部 Office 365 的服務。</span><span class="sxs-lookup"><span data-stu-id="eab84-114">For example, you can see where users are storing and collaborating on documents and how much data is being uploaded to apps or services that are outside of Office 365.</span></span>
  
<span data-ttu-id="eab84-115">若要產生應用程式探索報表，您手動上傳您的網頁流量記錄檔案，從您的防火牆和 proxy，然後並 Office 365 雲端 App 安全性剖析分析您的報表那些檔案。</span><span class="sxs-lookup"><span data-stu-id="eab84-115">To generate an app discovery report, you manually upload your web traffic log files from your firewalls and proxies, and then Office 365 Cloud App Security parses and analyzes those files for your report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eab84-116">您必須是全域系統管理員、 安全性系統管理員或安全性讀取者若要執行本文所述的工作。</span><span class="sxs-lookup"><span data-stu-id="eab84-116">You must be a global administrator, security administrator, or security reader to perform the tasks described in this article.</span></span> <span data-ttu-id="eab84-117">若要深入了解，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="eab84-117">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="create-a-report-with-app-discovery"></a><span data-ttu-id="eab84-118">建立 app 探索報表</span><span class="sxs-lookup"><span data-stu-id="eab84-118">Create a report with app discovery</span></span>

<span data-ttu-id="eab84-119">若要建立 app 探索報表，您可以識別您想要有分析，請選取記錄檔，然後再要求報告的記錄檔的廠商資料來源。</span><span class="sxs-lookup"><span data-stu-id="eab84-119">To create an app discovery report, you identify the vendor data source for the log files that you want to have analyzed, select the log files, and then request the report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eab84-120">使用包含尖峰流量期間，若要使用的最佳表示法取得貴組織中的 web 流量記錄檔。</span><span class="sxs-lookup"><span data-stu-id="eab84-120">Use web traffic log files that include peak traffic periods to get the best representation of usage in your organization.</span></span> 
  
1. <span data-ttu-id="eab84-121">收集[web 流量記錄檔和 Office 365 雲端 App 安全性的資料來源](web-traffic-logs-and-data-sources-for-ocas.md)。</span><span class="sxs-lookup"><span data-stu-id="eab84-121">Collect your [web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md).</span></span>
    
2. <span data-ttu-id="eab84-122">移至 Cloud App Security 入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，並登入。</span><span class="sxs-lookup"><span data-stu-id="eab84-122">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span> 
       
3. <span data-ttu-id="eab84-123">選擇 [**探索** \> **建立新的報表**。</span><span class="sxs-lookup"><span data-stu-id="eab84-123">Choose **Discover** \> **Create new report**.</span></span> <br><span data-ttu-id="eab84-124">![在 Office 365 CAS 入口網站中，選擇 [探索](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)</span><span class="sxs-lookup"><span data-stu-id="eab84-124">![In the Office 365 CAS portal, choose Discover](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)</span></span><br>
  
4. <span data-ttu-id="eab84-125">指定的名稱和描述您的報表，，然後選取 [**資料來源**] 清單中的 [web 流量記錄檔的資料來源。</span><span class="sxs-lookup"><span data-stu-id="eab84-125">Specify a name and description for your report, and then select the data source for your web traffic logs in the **Data source** list.</span></span> <br><span data-ttu-id="eab84-126">![O365 CAS 中選擇 [探索\>建立新的報表](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)</span><span class="sxs-lookup"><span data-stu-id="eab84-126">![In O365 CAS, choose Discover \> Create new report](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)</span></span><br><span data-ttu-id="eab84-127">如果未列出您想要使用的資料來源，您可以要求，將它加入。</span><span class="sxs-lookup"><span data-stu-id="eab84-127">If a data source that you'd like to use is not listed, you can request that it be added.</span></span> <span data-ttu-id="eab84-128">選取 [**其他\*\*\*\*資料來源**，，，然後輸入您想要上傳的資料來源的名稱。</span><span class="sxs-lookup"><span data-stu-id="eab84-128">Select **Other** for **Data source**, and then type the name of the data source that you're trying to upload.</span></span> <span data-ttu-id="eab84-129">我們將檢閱記錄檔，並可讓您知道是否我們新增它產生的資料來源的支援。</span><span class="sxs-lookup"><span data-stu-id="eab84-129">We'll review the log, and let you know if we add support for the data source that generated it.</span></span> 
  
5. <span data-ttu-id="eab84-130">瀏覽至您收集記錄檔的位置，並選取的檔案。</span><span class="sxs-lookup"><span data-stu-id="eab84-130">Browse to the location of the log files you collected and select the files.</span></span> <span data-ttu-id="eab84-131">您所選擇的報告的資料來源必須已產生的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="eab84-131">The log files must have been generated by the data source that you chose for the report.</span></span>
    
6. <span data-ttu-id="eab84-132">按一下 [**建立**] 以啟動報表建立程序]。</span><span class="sxs-lookup"><span data-stu-id="eab84-132">Click **Create** to start the report creation process.</span></span> 
    
7. <span data-ttu-id="eab84-133">若要查看報告的狀態，請按一下 [**管理快照報告**。</span><span class="sxs-lookup"><span data-stu-id="eab84-133">To see the status of the report, click **Manage snapshot reports**.</span></span> <span data-ttu-id="eab84-134">準備報表時，您會看到 [**檢視報告**] 選項。</span><span class="sxs-lookup"><span data-stu-id="eab84-134">When a report is ready, you'll see the **View report** option.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="eab84-135">後續步驟</span><span class="sxs-lookup"><span data-stu-id="eab84-135">Next steps</span></span>

- [<span data-ttu-id="eab84-136">檢閱並採取相應動作提醒</span><span class="sxs-lookup"><span data-stu-id="eab84-136">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="eab84-137">檢閱 Office 365 雲端 App 安全性中的 App 探索結果</span><span class="sxs-lookup"><span data-stu-id="eab84-137">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="eab84-138">檢閱您[的 Office 365 雲端 App 安全性的使用率活動](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="eab84-138">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

