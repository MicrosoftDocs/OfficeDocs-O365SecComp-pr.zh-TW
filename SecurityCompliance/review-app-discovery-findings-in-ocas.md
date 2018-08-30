---
title: 檢閱 Office 365 雲端 App 安全性中的 App 探索結果
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: 檢閱在 [進階安全性管理應用程式探索報告可協助您深入了解如何在組織中的人員使用雲端應用程式。您已建立應用程式探索報告使用來自防火牆及 proxy 記錄檔之後，請檢閱應用程式探索儀表板中的結果。
ms.openlocfilehash: 188ef87920b26069e7d99057662b3812be22e46c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526159"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a><span data-ttu-id="8a89a-104">檢閱 Office 365 雲端 App 安全性中的 App 探索結果</span><span class="sxs-lookup"><span data-stu-id="8a89a-104">Review app discovery findings in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="8a89a-105">評估 * *\>**</span><span class="sxs-lookup"><span data-stu-id="8a89a-105">****Evaluation** \>**</span></span>|<span data-ttu-id="8a89a-106">規劃 * *\>**</span><span class="sxs-lookup"><span data-stu-id="8a89a-106">****Planning** \>**</span></span>|<span data-ttu-id="8a89a-107">部署 * *\>**</span><span class="sxs-lookup"><span data-stu-id="8a89a-107">****Deployment** \>**</span></span>|<span data-ttu-id="8a89a-108">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="8a89a-108">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="8a89a-109">啟動評估</span><span class="sxs-lookup"><span data-stu-id="8a89a-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="8a89a-110">開始規劃</span><span class="sxs-lookup"><span data-stu-id="8a89a-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="8a89a-111">開始部署</span><span class="sxs-lookup"><span data-stu-id="8a89a-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="8a89a-112">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="8a89a-112">You are here!</span></span>  <br/> [<span data-ttu-id="8a89a-113">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8a89a-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="8a89a-p102">雲端探索儀表板適用於您組織的網頁流量記錄以提供雲端應用程式使用方式的詳細的資訊。如果您正在全域管理員、 安全性管理員或安全性讀者和您的組織有[建立 Office 365 雲端應用程式安全性的應用程式探索報告](create-app-discovery-reports-in-ocas.md)、 您可以使用雲端探索儀表板的入侵深入了解如何人員在您組織使用 Office 365 及其他雲端應用程式。（雲端探索儀表板也稱為是產能應用程式探索）。</span><span class="sxs-lookup"><span data-stu-id="8a89a-p102">The Cloud Discovery dashboard works with your organization's web traffic logs to provide detailed information about cloud app usage. If you're a global administrator, security administrator, or security reader, and your organization has [created app discovery reports in Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md), you can use the Cloud Discovery dashboard to gain insight into how people in your organization are using Office 365 and other cloud apps. (The Cloud Discovery dashboard is also known as Productivity App Discovery.)</span></span>
  
 <span data-ttu-id="8a89a-117">**年 3 月 2018年雲端探索儀表板有新的功能**可讓您輕鬆將檢視您組織中的人員如何使用 Office 365 及其他應用程式的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="8a89a-117">**As of March 2018, the Cloud Discovery dashboard has new features** that make it easier to view detailed information about how people in your organization are using Office 365 and other apps.</span></span> 
  
![已更新雲端探索儀表板](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a><span data-ttu-id="8a89a-119">移至雲端探索儀表板</span><span class="sxs-lookup"><span data-stu-id="8a89a-119">Go to the Cloud Discovery dashboard</span></span>

1. <span data-ttu-id="8a89a-p103">移至 [[https://protection.office.com](https://protection.office.com)及使用 Office 365 工作或學校帳戶登入。(這會引導您安全性&amp;規範中心。)</span><span class="sxs-lookup"><span data-stu-id="8a89a-p103">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="8a89a-122">安全性&amp;規範中心選擇**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="8a89a-122">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
    <span data-ttu-id="8a89a-123">（如果尚未未啟用 Office 365 雲端應用程式安全性，而且會[開啟 [Office 365 雲端應用程式安全性](turn-on-office-365-cas.md)全域系統管理員）。</span><span class="sxs-lookup"><span data-stu-id="8a89a-123">(If Office 365 Cloud App Security is not yet enabled, and you are a global administrator, [turn on Office 365 Cloud App Security](turn-on-office-365-cas.md).)</span></span>
    
3. <span data-ttu-id="8a89a-124">選擇 [**移至 Office 365 的雲端應用程式安全性**]。</span><span class="sxs-lookup"><span data-stu-id="8a89a-124">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
4. <span data-ttu-id="8a89a-125">移至 [**搜索** \> **雲端探索儀表板**。</span><span class="sxs-lookup"><span data-stu-id="8a89a-125">Go to **Discover** \> **Cloud Discovery dashboard**.</span></span>
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a><span data-ttu-id="8a89a-126">請參閱您的主要使用者、 IP 位址、 應用程式] 及風險層級</span><span class="sxs-lookup"><span data-stu-id="8a89a-126">See your top users, IP addresses, apps, and risk levels</span></span>

<span data-ttu-id="8a89a-127">雲端探索儀表板可讓您的組織、 任何開啟的提醒、 主要使用者及風險層級中搭配 Office 365 的應用程式 a glance 在-概觀 （英文）。</span><span class="sxs-lookup"><span data-stu-id="8a89a-127">The Cloud Discovery dashboard gives you an at-a-glance overview of apps that are used with Office 365 in your organization, any open alerts, top users, and risk levels.</span></span>
  
![雲端探索 dashboaard](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. <span data-ttu-id="8a89a-129">在 [**儀表板**] 索引標籤上查看您組織的 [概觀] 區段中的整體雲端應用程式使用螢幕頂端之間。</span><span class="sxs-lookup"><span data-stu-id="8a89a-129">On the **Dashboard** tab, look at the overall cloud app use in your organization in the overview section across the top of the screen.</span></span> 
    
2. <span data-ttu-id="8a89a-130">請參閱**Office 365 類別**您組織中使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8a89a-130">See the **Office 365 categories** for apps that are used in your organization.</span></span> 
    
3. <span data-ttu-id="8a89a-131">查看**Discovered apps** widget 查看 Office 365 與此檢視中的其他應用程式的流量。</span><span class="sxs-lookup"><span data-stu-id="8a89a-131">Look at the **Discovered apps** widget to see usage of Office 365 and other apps in this view.</span></span> 
    
4. <span data-ttu-id="8a89a-132">查看來識別使用者可以使用 Office 365 部署及雲端組織中最多的應用程式的**主要使用者**和**頂端 IP 位址**widget。</span><span class="sxs-lookup"><span data-stu-id="8a89a-132">Look at the **Top users** and **Top IP addresses** widget to identify those who use Office 365 and cloud apps the most in your organization.</span></span> 
    
5. <span data-ttu-id="8a89a-133">請參閱依地理位置人員所使用的應用程式所使用的**應用程式 headquarters 位置**對應位置。</span><span class="sxs-lookup"><span data-stu-id="8a89a-133">See where the apps people are using are by geographical location by using the **Apps headquarters location** map.</span></span> 
    
6. <span data-ttu-id="8a89a-p104">高於地圖] 區域中，看看探索到中的應用程式**的風險層級**概觀 （英文） 的風險分數。您可以查看由同一個群組和**Discovered 應用程式**] 區域中所使用的類別的風險。例如，您可以看到流量多寡中每個群組是從高、 中型或低風險應用程式。</span><span class="sxs-lookup"><span data-stu-id="8a89a-p104">Above the maps area, take a look at the risk score of the discovered apps in the **Risk levels** overview. You can look at risks by the same groups and categories that you used in the **Discovered apps** area. For example, you can see how much traffic in each grouping is from high, medium, or low risk apps.</span></span> 
    
## <a name="dive-deeper-into-the-information"></a><span data-ttu-id="8a89a-137">深入分析資訊</span><span class="sxs-lookup"><span data-stu-id="8a89a-137">Dive deeper into the information</span></span>

<span data-ttu-id="8a89a-138">您可以使用雲端探索採取深入的應用程式、 子網域、 IP 位址及使用者。</span><span class="sxs-lookup"><span data-stu-id="8a89a-138">You can use Cloud Discovery to take a deeper look at apps, subdomains, IP addresses, and users.</span></span>
  
1. <span data-ttu-id="8a89a-139">雲端探索儀表板中選擇 [ **Discovered 應用程式**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8a89a-139">In the Cloud Discovery dashboard, choose the **Discovered apps** tab.</span></span> 
    
2. <span data-ttu-id="8a89a-140">使用 [篩選] 區段中檢視應用程式的名稱、 類別、 使用量層級或看到的日期。</span><span class="sxs-lookup"><span data-stu-id="8a89a-140">Use the filters section to view apps by name, category, usage level, or last seen date.</span></span>
    
3. <span data-ttu-id="8a89a-141">在結果清單中，將游標移所顯示的**檢視子網域**的連結應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="8a89a-141">In the list of results, hover by an app name to reveal the **View sub-domains** link.</span></span> 
    
    ![將滑鼠指標移至顯示檢視子網域的詳細資訊連結的應用程式旁](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)
  
    <span data-ttu-id="8a89a-143">會顯示所選的應用程式的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="8a89a-143">Detailed information about the selected app will appear.</span></span>
    
4. <span data-ttu-id="8a89a-144">若要檢視有關的 IP 位址的詳細資訊，請選擇 [ **IP 位址**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8a89a-144">To view details about IP addresses, choose the **IP addresses** tab.</span></span> 
    
    ![雲端探索顯示 IP 位址的詳細的資訊](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)
  
    <span data-ttu-id="8a89a-146">在結果清單中，選取 [個別 IP 位址來檢視的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="8a89a-146">In the list of results, select an individual IP address to view more detailed information.</span></span>
    
5. <span data-ttu-id="8a89a-147">若要檢視您組織中的 Office 365 使用者相關的詳細資訊，請選擇 [**使用者**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8a89a-147">To view details about Office 365 users within your organization, choose the **Users** tab.</span></span> 
    
    ![雲端探索-使用者資訊](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)
  
## <a name="exclude-entities"></a><span data-ttu-id="8a89a-149">排除實體</span><span class="sxs-lookup"><span data-stu-id="8a89a-149">Exclude entities</span></span>

<span data-ttu-id="8a89a-150">您可以排除特定系統的使用者或 IP 位址以專注於更特定的資訊。</span><span class="sxs-lookup"><span data-stu-id="8a89a-150">You can exclude certain system users or IP addresses in order to focus on more specific information.</span></span>
  
1. <span data-ttu-id="8a89a-151">選擇 [**設定** \> **雲端探索設定**。</span><span class="sxs-lookup"><span data-stu-id="8a89a-151">Choose **Settings** \> **Cloud Discovery settings**.</span></span>
    
2. <span data-ttu-id="8a89a-152">選擇 [**排除實體**。</span><span class="sxs-lookup"><span data-stu-id="8a89a-152">Choose **Exclude entities**.</span></span>
    
3. <span data-ttu-id="8a89a-153">選擇 [**排除的使用者**或**排除的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="8a89a-153">Choose either **Excluded users** or **Excluded IP addresses**.</span></span>
    
4. <span data-ttu-id="8a89a-154">指定的使用者或 IP 位址並在 [**註解**] 方塊中輸入為什麼會排除這些使用者或 IP 位址資訊。</span><span class="sxs-lookup"><span data-stu-id="8a89a-154">Specify the users or IP addresses, and in the **Comments** box, type information about why you are excluding those users or IP addresses.</span></span> 
    
5. <span data-ttu-id="8a89a-155">選擇 [新增]****。</span><span class="sxs-lookup"><span data-stu-id="8a89a-155">Choose **Add**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="8a89a-156">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8a89a-156">Next steps</span></span>

- [<span data-ttu-id="8a89a-157">檢閱並採取行動提醒</span><span class="sxs-lookup"><span data-stu-id="8a89a-157">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="8a89a-158">建立應用程式探索報告</span><span class="sxs-lookup"><span data-stu-id="8a89a-158">Create app discovery reports</span></span>](create-app-discovery-reports-in-ocas.md)
    
- <span data-ttu-id="8a89a-159">檢閱您[的 Office 365 雲端應用程式安全性使用率活動](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="8a89a-159">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

