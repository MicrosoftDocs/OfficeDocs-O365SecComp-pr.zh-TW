---
title: 使用 Office 365 雲端 App 安全性建立 App 探索報表
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: 建立報表與 Office 365 雲端應用程式安全性可讓您了解如何在組織中的人員會使用 Office 365 和其他應用程式。
ms.openlocfilehash: f801c70e839a62b5bbb5423ff5e7c513dd1f09b4
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706297"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a><span data-ttu-id="2d717-103">使用 Office 365 雲端 App 安全性建立 App 探索報表</span><span class="sxs-lookup"><span data-stu-id="2d717-103">Create app discovery reports using Office 365 Cloud App Security</span></span>

<span data-ttu-id="2d717-104">Office 365 進階安全性管理現在是 Office 365 雲端應用程式安全性。</span><span class="sxs-lookup"><span data-stu-id="2d717-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="2d717-105">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="2d717-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="2d717-106">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="2d717-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="2d717-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="2d717-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="2d717-108">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="2d717-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="2d717-109">啟動評估</span><span class="sxs-lookup"><span data-stu-id="2d717-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="2d717-110">開始規劃</span><span class="sxs-lookup"><span data-stu-id="2d717-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="2d717-111">開始部署</span><span class="sxs-lookup"><span data-stu-id="2d717-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="2d717-112">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="2d717-112">You are here!</span></span>  <br/> [<span data-ttu-id="2d717-113">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2d717-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="2d717-p101">Office 365 雲端應用程式安全性協助全域管理員、 安全性管理員及安全性讀者掌握人員在組織中的使用的雲端服務。例如，您可以看到其中使用者會儲存在文件上共同作業和資料量要上傳至應用程式或 Office 365 外部的服務。</span><span class="sxs-lookup"><span data-stu-id="2d717-p101">Office 365 Cloud App Security helps global administrators, security administrators, and security readers gain insight into the cloud services people in an organization are using. For example, you can see where users are storing and collaborating on documents and how much data is being uploaded to apps or services that are outside of Office 365.</span></span>
  
<span data-ttu-id="2d717-116">若要產生的應用程式探索報表，您手動上傳您的網頁流量記錄檔案從防火牆及 proxy，並再 Office 365 雲端應用程式安全性會剖析分析報表這些檔案。</span><span class="sxs-lookup"><span data-stu-id="2d717-116">To generate an app discovery report, you manually upload your web traffic log files from your firewalls and proxies, and then Office 365 Cloud App Security parses and analyzes those files for your report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d717-p102">您必須是執行本文所述的工作的全域管理員、 安全性管理員或安全性讀者。若要深入了解，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2d717-p102">You must be a global administrator, security administrator, or security reader to perform the tasks described in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="create-a-report-with-app-discovery"></a><span data-ttu-id="2d717-119">應用程式探索與建立報告</span><span class="sxs-lookup"><span data-stu-id="2d717-119">Create a report with app discovery</span></span>

<span data-ttu-id="2d717-120">若要建立的應用程式探索報表，您可以識別您想要有分析、 選取 [記錄檔，並請求報表的記錄檔的廠商資料來源。</span><span class="sxs-lookup"><span data-stu-id="2d717-120">To create an app discovery report, you identify the vendor data source for the log files that you want to have analyzed, select the log files, and then request the report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d717-121">使用包含尖峰流量期間取得最佳的使用方式代表您組織中的網頁流量記錄檔案。</span><span class="sxs-lookup"><span data-stu-id="2d717-121">Use web traffic log files that include peak traffic periods to get the best representation of usage in your organization.</span></span> 
  
1. <span data-ttu-id="2d717-122">收集您的[網頁流量記錄檔與資料來源為 Office 365 雲端應用程式安全性](web-traffic-logs-and-data-sources-for-ocas.md)。</span><span class="sxs-lookup"><span data-stu-id="2d717-122">Collect your [web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md).</span></span>
    
2. <span data-ttu-id="2d717-123">移至 [[https://security.microsoft.com](https://security.microsoft.com)並使用您工作或學校的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="2d717-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in using your work or school account.</span></span> 
    
3. <span data-ttu-id="2d717-124">安全性&amp;規範中心選擇**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="2d717-124">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
4. <span data-ttu-id="2d717-125">選擇 [**移至 Office 365 的雲端應用程式安全性**]。</span><span class="sxs-lookup"><span data-stu-id="2d717-125">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
5. <span data-ttu-id="2d717-126">選擇 [**搜索** \> **建立新的報表**。</span><span class="sxs-lookup"><span data-stu-id="2d717-126">Choose **Discover** \> **Create new report**.</span></span>
    
    ![在 Office 365 CAS 入口網站中選擇 [搜索](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
6. <span data-ttu-id="2d717-128">指定的名稱和描述您的報表，並在 [**資料來源**] 清單中選取 web 流量記錄檔的資料來源。</span><span class="sxs-lookup"><span data-stu-id="2d717-128">Specify a name and description for your report, and then select the data source for your web traffic logs in the **Data source** list.</span></span> 
    
    ![O365 CAS 中選擇 [搜索\>建立新的報表](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)
  
    > [!NOTE]
    > <span data-ttu-id="2d717-p103">如果未列出您想要使用的資料來源，您可以要求要新增。選取 [**其他\*\*\*\*資料來源**，然後輸入 [您嘗試將上傳的資料來源的名稱。我們將檢閱記錄檔，並且可讓您知道是否我們將新增其產生的資料來源的支援。</span><span class="sxs-lookup"><span data-stu-id="2d717-p103">If a data source that you'd like to use is not listed, you can request that it be added. Select **Other** for **Data source**, and then type the name of the data source that you're trying to upload. We'll review the log, and let you know if we add support for the data source that generated it.</span></span> 
  
7. <span data-ttu-id="2d717-p104">瀏覽至您收集記錄檔的位置及選取的檔案。您選擇的報告的資料來源必須已產生記錄檔。</span><span class="sxs-lookup"><span data-stu-id="2d717-p104">Browse to the location of the log files you collected and select the files. The log files must have been generated by the data source that you chose for the report.</span></span>
    
8. <span data-ttu-id="2d717-135">按一下 [**建立**] 以啟動報表建立程序。</span><span class="sxs-lookup"><span data-stu-id="2d717-135">Click **Create** to start the report creation process.</span></span> 
    
9. <span data-ttu-id="2d717-p105">若要查看報告的狀態，請按一下 [**管理快照報告**]。準備報表時，您會看到 [**檢視報告**] 選項。</span><span class="sxs-lookup"><span data-stu-id="2d717-p105">To see the status of the report, click **Manage snapshot reports**. When a report is ready, you'll see the **View report** option.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="2d717-138">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2d717-138">Next steps</span></span>

- [<span data-ttu-id="2d717-139">檢閱並採取行動提醒</span><span class="sxs-lookup"><span data-stu-id="2d717-139">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="2d717-140">檢閱 Office 365 雲端 App 安全性中的 App 探索結果</span><span class="sxs-lookup"><span data-stu-id="2d717-140">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="2d717-141">檢閱您[的 Office 365 雲端應用程式安全性使用率活動](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="2d717-141">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

