---
title: 檢閱 Office 365 雲端 App 安全性中的 App 探索結果
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: 檢閱 Office 365 雲端 App 安全性中的應用程式探索報表可協助您深入了解如何在組織中的人員使用雲端應用程式。 您已建立使用記錄檔，從您的防火牆和 proxy 的 app 探索報表之後，請檢閱應用程式探索儀表板中的結果。
ms.openlocfilehash: f50ad372450b2a1404829eeb6f6964c1d954dccd
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264957"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a><span data-ttu-id="20e93-104">檢閱 Office 365 雲端 App 安全性中的 App 探索結果</span><span class="sxs-lookup"><span data-stu-id="20e93-104">Review app discovery findings in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="20e93-105">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="20e93-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="20e93-106">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="20e93-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="20e93-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="20e93-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="20e93-108">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="20e93-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="20e93-109">啟動評估</span><span class="sxs-lookup"><span data-stu-id="20e93-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="20e93-110">開始規劃</span><span class="sxs-lookup"><span data-stu-id="20e93-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="20e93-111">開始部署</span><span class="sxs-lookup"><span data-stu-id="20e93-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="20e93-112">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="20e93-112">You are here!</span></span>  <br/> [<span data-ttu-id="20e93-113">後續步驟</span><span class="sxs-lookup"><span data-stu-id="20e93-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="20e93-114">在雲端探索儀表板的運作方式與您的組織 web 流量記錄檔，以提供雲端應用程式使用狀況的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="20e93-114">The Cloud Discovery dashboard works with your organization's web traffic logs to provide detailed information about cloud app usage.</span></span> <span data-ttu-id="20e93-115">如果您是全域系統管理員、 安全性系統管理員或安全性讀取者，而且您的組織有[建立 Office 365 雲端 App 安全性中的應用程式探索報表](create-app-discovery-reports-in-ocas.md)，您可以使用雲端探索儀表板來掌握如何人員在您Office 365 和其他雲端應用程式所使用的組織。</span><span class="sxs-lookup"><span data-stu-id="20e93-115">If you're a global administrator, security administrator, or security reader, and your organization has [created app discovery reports in Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md), you can use the Cloud Discovery dashboard to gain insight into how people in your organization are using Office 365 and other cloud apps.</span></span> <span data-ttu-id="20e93-116">（雲端探索儀表板也稱為是產能應用程式探索）。</span><span class="sxs-lookup"><span data-stu-id="20e93-116">(The Cloud Discovery dashboard is also known as Productivity App Discovery.)</span></span>
  
 <span data-ttu-id="20e93-117">在雲端探索儀表板可讓您檢視您組織中的人員如何使用 Office 365 和其他應用程式的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="20e93-117">The Cloud Discovery dashboard enables you to view detailed information about how people in your organization are using Office 365 and other apps.</span></span> 
  
![已更新，在雲端探索儀表板](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a><span data-ttu-id="20e93-119">移至雲端探索儀表板</span><span class="sxs-lookup"><span data-stu-id="20e93-119">Go to the Cloud Discovery dashboard</span></span>

1. <span data-ttu-id="20e93-120">移至 Cloud App Security 入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，並登入。</span><span class="sxs-lookup"><span data-stu-id="20e93-120">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
    
2. <span data-ttu-id="20e93-121">前往**探索** \> **雲端探索儀表板**。</span><span class="sxs-lookup"><span data-stu-id="20e93-121">Go to **Discover** \> **Cloud Discovery dashboard**.</span></span>
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a><span data-ttu-id="20e93-122">請參閱您的主要使用者、 IP 位址、 應用程式] 和風險層級</span><span class="sxs-lookup"><span data-stu-id="20e93-122">See your top users, IP addresses, apps, and risk levels</span></span>

<span data-ttu-id="20e93-123">在雲端探索儀表板提供與 Office 365 用於您的組織、 任何開啟的提醒、 最上層的使用者和風險層級中的應用程式在快速概觀。</span><span class="sxs-lookup"><span data-stu-id="20e93-123">The Cloud Discovery dashboard gives you an at-a-glance overview of apps that are used with Office 365 in your organization, any open alerts, top users, and risk levels.</span></span>
  
![雲端探索 dashboaard](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. <span data-ttu-id="20e93-125">在 [**儀表板**] 索引標籤上查看貴組織的 [概觀] 區段中的整體雲端應用程式使用間的螢幕頂端。</span><span class="sxs-lookup"><span data-stu-id="20e93-125">On the **Dashboard** tab, look at the overall cloud app use in your organization in the overview section across the top of the screen.</span></span> 
    
2. <span data-ttu-id="20e93-126">請參閱**Office 365 類別**的組織內所使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="20e93-126">See the **Office 365 categories** for apps that are used in your organization.</span></span> 
    
3. <span data-ttu-id="20e93-127">查看**Discovered 應用程式**] 小工具以查看 Office 365 和其他應用程式，在此檢視中的使用狀況。</span><span class="sxs-lookup"><span data-stu-id="20e93-127">Look at the **Discovered apps** widget to see usage of Office 365 and other apps in this view.</span></span> 
    
4. <span data-ttu-id="20e93-128">看看**主要使用者**和**頂端 IP 位址**] 小工具以識別的使用者使用 Office 365 部署及雲端組織中最多的應用程式。</span><span class="sxs-lookup"><span data-stu-id="20e93-128">Look at the **Top users** and **Top IP addresses** widget to identify those who use Office 365 and cloud apps the most in your organization.</span></span> 
    
5. <span data-ttu-id="20e93-129">請參閱依地理位置的人員會使用這些應用程式可使用的**應用程式總部位置**對應其中。</span><span class="sxs-lookup"><span data-stu-id="20e93-129">See where the apps people are using are by geographical location by using the **Apps headquarters location** map.</span></span> 
    
6. <span data-ttu-id="20e93-130">上方地圖] 區域中，看看的**風險層級**概觀中所找到的應用程式的風險分數。</span><span class="sxs-lookup"><span data-stu-id="20e93-130">Above the maps area, take a look at the risk score of the discovered apps in the **Risk levels** overview.</span></span> <span data-ttu-id="20e93-131">您可以查看由同一個群組及類別**Discovered 應用程式**區域中所用的風險。</span><span class="sxs-lookup"><span data-stu-id="20e93-131">You can look at risks by the same groups and categories that you used in the **Discovered apps** area.</span></span> <span data-ttu-id="20e93-132">例如，您可以看到每個群組多少流量是來自高、 中或低風險應用程式。</span><span class="sxs-lookup"><span data-stu-id="20e93-132">For example, you can see how much traffic in each grouping is from high, medium, or low risk apps.</span></span> 
    
## <a name="dive-deeper-into-the-information"></a><span data-ttu-id="20e93-133">深入分析資訊</span><span class="sxs-lookup"><span data-stu-id="20e93-133">Dive deeper into the information</span></span>

<span data-ttu-id="20e93-134">您可以使用雲端探索才會探討應用程式、 子網域、 IP 位址和使用者。</span><span class="sxs-lookup"><span data-stu-id="20e93-134">You can use Cloud Discovery to take a deeper look at apps, subdomains, IP addresses, and users.</span></span>
  
1. <span data-ttu-id="20e93-135">在雲端探索儀表板中，選擇 [ **Discovered 應用程式**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="20e93-135">In the Cloud Discovery dashboard, choose the **Discovered apps** tab.</span></span> 
    
2. <span data-ttu-id="20e93-136">使用 [篩選] 區段中檢視應用程式的名稱、 類別、 使用量層級或上次看到的日期。</span><span class="sxs-lookup"><span data-stu-id="20e93-136">Use the filters section to view apps by name, category, usage level, or last seen date.</span></span>
    
3. <span data-ttu-id="20e93-137">在結果清單中，將游標依應用程式名稱，以顯示 [**檢視子網域**] 連結。</span><span class="sxs-lookup"><span data-stu-id="20e93-137">In the list of results, hover by an app name to reveal the **View sub-domains** link.</span></span><br/> <span data-ttu-id="20e93-138">![將游標暫留旁邊，顯示連結，以檢視子網域的詳細資訊的應用程式](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span><span class="sxs-lookup"><span data-stu-id="20e93-138">![Hover next to an app to reveal a link to view subdomain details](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span></span><br/><span data-ttu-id="20e93-139">會顯示所選應用程式的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="20e93-139">Detailed information about the selected app will appear.</span></span>
    
4. <span data-ttu-id="20e93-140">若要檢視關於 IP 位址的詳細資訊，請選擇 [ **IP 位址**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="20e93-140">To view details about IP addresses, choose the **IP addresses** tab.</span></span><br/><span data-ttu-id="20e93-141">![雲端探索顯示的 IP 位址的詳細的資訊](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span><span class="sxs-lookup"><span data-stu-id="20e93-141">![Cloud Discovery shows detailed information about IP addresses](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span></span><br/><span data-ttu-id="20e93-142">在結果清單中，選取 [個別 IP 位址來檢視更詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="20e93-142">In the list of results, select an individual IP address to view more detailed information.</span></span>
    
5. <span data-ttu-id="20e93-143">若要檢視關於組織內的 Office 365 使用者的詳細資訊，請選擇 [**使用者**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="20e93-143">To view details about Office 365 users within your organization, choose the **Users** tab.</span></span><br/><span data-ttu-id="20e93-144">![雲端探索-使用者資訊](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span><span class="sxs-lookup"><span data-stu-id="20e93-144">![Cloud Discovery - users info](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span></span>
  
## <a name="exclude-entities"></a><span data-ttu-id="20e93-145">排除實體</span><span class="sxs-lookup"><span data-stu-id="20e93-145">Exclude entities</span></span>

<span data-ttu-id="20e93-146">您可以排除特定系統的使用者或 IP 位址，以專注於更特定的資訊。</span><span class="sxs-lookup"><span data-stu-id="20e93-146">You can exclude certain system users or IP addresses in order to focus on more specific information.</span></span>
  
1. <span data-ttu-id="20e93-147">選擇 [**設定** \> **雲端探索設定**。</span><span class="sxs-lookup"><span data-stu-id="20e93-147">Choose **Settings** \> **Cloud Discovery settings**.</span></span>
    
2. <span data-ttu-id="20e93-148">選擇 [**排除項目**。</span><span class="sxs-lookup"><span data-stu-id="20e93-148">Choose **Exclude entities**.</span></span>
    
3. <span data-ttu-id="20e93-149">選擇 [**排除的使用者**或**排除的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="20e93-149">Choose either **Excluded users** or **Excluded IP addresses**.</span></span>
    
4. <span data-ttu-id="20e93-150">指定使用者或 IP 位址，並在 [**註解**] 方塊中，輸入為什麼您會排除那些使用者或 IP 位址的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="20e93-150">Specify the users or IP addresses, and in the **Comments** box, type information about why you are excluding those users or IP addresses.</span></span> 
    
5. <span data-ttu-id="20e93-151">選擇 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="20e93-151">Choose **Add**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="20e93-152">後續步驟</span><span class="sxs-lookup"><span data-stu-id="20e93-152">Next steps</span></span>

- [<span data-ttu-id="20e93-153">檢閱並採取相應動作提醒</span><span class="sxs-lookup"><span data-stu-id="20e93-153">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="20e93-154">建立 app 探索報表</span><span class="sxs-lookup"><span data-stu-id="20e93-154">Create app discovery reports</span></span>](create-app-discovery-reports-in-ocas.md)
    
- <span data-ttu-id="20e93-155">檢閱您[的 Office 365 雲端 App 安全性的使用率活動](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="20e93-155">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

