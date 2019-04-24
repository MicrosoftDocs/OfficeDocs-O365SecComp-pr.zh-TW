---
title: 將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: 輕鬆地找出您將您的實際辦公室 IP 位址，例如使用 Office 365 雲端 App 安全性中的 IP 位址設定您可以設定群組的 IP 位址範圍。
ms.openlocfilehash: b8f5c1dd46b2e3990d53a65881d12ca8f3961b16
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254854"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a><span data-ttu-id="1106e-103">將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理</span><span class="sxs-lookup"><span data-stu-id="1106e-103">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="1106e-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1106e-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="1106e-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1106e-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="1106e-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1106e-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="1106e-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="1106e-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="1106e-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="1106e-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="1106e-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="1106e-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="1106e-110">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="1106e-110">You are here!</span></span>  <br/> [<span data-ttu-id="1106e-111">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1106e-111">Next steps</span></span>](#next-steps) <br/> |[<span data-ttu-id="1106e-112">開始使用</span><span class="sxs-lookup"><span data-stu-id="1106e-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="1106e-113">輕鬆地找出您將您的實際辦公室 IP 位址，例如使用 Office 365 雲端 App 安全性中的 IP 位址設定您可以設定群組的 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="1106e-113">To easily identify sets of IP addresses that you'll use in Office 365 Cloud App Security, such as your physical office IP addresses, you can set up groups of IP address ranges.</span></span> <span data-ttu-id="1106e-114">定義這些範圍可讓您標記，並加以分類，則您可以使用標記並顯示及調查來自訂您的活動的記錄檔及警示的類別。</span><span class="sxs-lookup"><span data-stu-id="1106e-114">Defining these ranges lets you tag and categorize them, and then you can use tags and categories to customize how your activity logs and alerts are displayed and investigated.</span></span>
  
<span data-ttu-id="1106e-115">每個群組的 IP 範圍可以與標記的名稱，您選擇，然後將標記可分類根據預設清單的 IP 類別 （例如 Corporate、 系統管理、 Risky 和 VPN） 標記。</span><span class="sxs-lookup"><span data-stu-id="1106e-115">Each group of IP ranges can be tagged with tag names that you choose, and then the tags can be categorized based on a default list of IP categories (such as Corporate, Administrative, Risky, and VPN).</span></span> <span data-ttu-id="1106e-116">支援 IPv4 和 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="1106e-116">Both IPv4 and IPv6 addresses are supported.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1106e-117">您必須是全域系統管理員或安全性系統管理員才能執行本文中的程序。</span><span class="sxs-lookup"><span data-stu-id="1106e-117">You must be a global administrator or security administrator to perform the procedures in this article.</span></span> <span data-ttu-id="1106e-118">若要深入了解，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1106e-118">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a><span data-ttu-id="1106e-119">若要設定 Office 365 雲端 App 安全性中的 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="1106e-119">To set up an IP address range in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="1106e-120">以全域管理員或安全性管理員中，移至 Cloud App Security 入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，並登入。</span><span class="sxs-lookup"><span data-stu-id="1106e-120">As a global administrator or security administrator, go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
    
2. <span data-ttu-id="1106e-121">在右上角] 頁面上，按一下 [**設定** \> **IP 位址範圍**。</span><span class="sxs-lookup"><span data-stu-id="1106e-121">On the upper right of the page, click **Settings** \> **IP address ranges**.</span></span><br><span data-ttu-id="1106e-122">![在 O365 雲端 App 安全性中，選擇 [設定，以存取您的系統和資料設定](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)</span><span class="sxs-lookup"><span data-stu-id="1106e-122">![In O365 Cloud App Security, choose Settings to access your system and data settings](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)</span></span><br>
  
3. <span data-ttu-id="1106e-123">按一下 [新增] 按鈕，這類似於加上加號 ( **+**)。</span><span class="sxs-lookup"><span data-stu-id="1106e-123">Click the new button, which resembles a plus sign ( **+**).</span></span>
    
4. <span data-ttu-id="1106e-124">在 [**新的 IP 位址範圍**] 視窗中，指定下列值：</span><span class="sxs-lookup"><span data-stu-id="1106e-124">In the **New IP address range** window, specify the following values:</span></span> 
    
|<span data-ttu-id="1106e-125">**欄位或清單**</span><span class="sxs-lookup"><span data-stu-id="1106e-125">**Field or list**</span></span>|<span data-ttu-id="1106e-126">**要執行的動作**</span><span class="sxs-lookup"><span data-stu-id="1106e-126">**What to do**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1106e-127">**Name**</span><span class="sxs-lookup"><span data-stu-id="1106e-127">**Name**</span></span> <br/> |<span data-ttu-id="1106e-128">使用此欄位來管理您的 IP 位址範圍和設定。</span><span class="sxs-lookup"><span data-stu-id="1106e-128">Use this field to manage your IP address range and settings.</span></span> <span data-ttu-id="1106e-129">（您無法看到此活動記錄檔中的值）。</span><span class="sxs-lookup"><span data-stu-id="1106e-129">(You won't see this value in activities logs.)</span></span>  <br/> |
|<span data-ttu-id="1106e-130">**IP 位址範圍**</span><span class="sxs-lookup"><span data-stu-id="1106e-130">**IP address ranges**</span></span> <br/> |<span data-ttu-id="1106e-131">指定的範圍，使用網路前置詞表示法 （也稱為 CIDR 標記法）。</span><span class="sxs-lookup"><span data-stu-id="1106e-131">Specify a range, using network prefix notation (also known as CIDR notation).</span></span> <span data-ttu-id="1106e-132">例如，192.168.1.0/27 包含值 192.168.1.0 透過 192.168.1.31 （含） 之間的範圍。</span><span class="sxs-lookup"><span data-stu-id="1106e-132">For example, 192.168.1.0/27 includes the range of values 192.168.1.0 through 192.168.1.31 (inclusive).</span></span>  <br/> |
|<span data-ttu-id="1106e-133">**位置**和**註冊 ISP**</span><span class="sxs-lookup"><span data-stu-id="1106e-133">**Location** and **Registered ISP**</span></span> <br/> |<span data-ttu-id="1106e-134">指定的位置和網際網路服務提供者 (ISP) 的 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="1106e-134">Specify the location and Internet Service Provider (ISP) for the IP address range.</span></span> <span data-ttu-id="1106e-135">這會覆寫公用的欄位定義的地址，這是很有用的情況下，例如 IP 位址是，會被視為公開在愛爾蘭，但實際上是在美國</span><span class="sxs-lookup"><span data-stu-id="1106e-135">This overrides the public fields defined for the addresses, which is helpful for cases, such as an IP address is that is considered publicly to be in Ireland but is actually in the U.S.</span></span>  <br/> |
|<span data-ttu-id="1106e-136">**標記**</span><span class="sxs-lookup"><span data-stu-id="1106e-136">**Tags**</span></span> <br/> |<span data-ttu-id="1106e-137">使用標籤來命名您的 IP 位址的群組。</span><span class="sxs-lookup"><span data-stu-id="1106e-137">Use tags to name your groups of IP addresses.</span></span> <span data-ttu-id="1106e-138">（不同於 [名稱] 欄位中，您會看到標記活動記錄檔中）。輸入單字或片語，您想要使用標籤。</span><span class="sxs-lookup"><span data-stu-id="1106e-138">(Unlike the Name field, you will see Tags in activity logs.) Type a word or phrase that you want to use for a tag.</span></span> <span data-ttu-id="1106e-139">您可以新增多個標記為您想針對每個 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="1106e-139">You can add as many tags as you like for each IP address range.</span></span> <span data-ttu-id="1106e-140">如果您已經設定標記，並想要加入這個 IP 位址範圍，請從目前的標記，開始輸入時的清單中選擇。</span><span class="sxs-lookup"><span data-stu-id="1106e-140">And if you've already set up a tag and you want to add this IP address range to it, choose it from the list of current tags that appear as you start typing.</span></span>  <br/> |
|<span data-ttu-id="1106e-141">**類別**</span><span class="sxs-lookup"><span data-stu-id="1106e-141">**Category**</span></span> <br/> | <span data-ttu-id="1106e-142">將類別指派給您的標記若要更容易辨識來自特定 IP 位址的活動。</span><span class="sxs-lookup"><span data-stu-id="1106e-142">Assign categories to your tags to make it easier to recognize activities that come from certain IP addresses.</span></span> <span data-ttu-id="1106e-143">選擇 [從下列選項：</span><span class="sxs-lookup"><span data-stu-id="1106e-143">Choose from the following options:</span></span>  <br/> <span data-ttu-id="1106e-144">**系統管理**所有您系統管理員的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1106e-144">**Administrative** All of the IP addresses of your admins.</span></span>  <br/> <span data-ttu-id="1106e-145">**雲端提供者**您的 proxy 在雲端中的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1106e-145">**Cloud provider** The IP address of your proxy in the cloud.</span></span>  <br/> <span data-ttu-id="1106e-146">**公司**所有的 IP 位址在您的內部網路、 您的分支辦公室和 Wi-fi 漫遊地址。</span><span class="sxs-lookup"><span data-stu-id="1106e-146">**Corporate** All of the IP addresses in your internal network, your branch offices, and your Wi-Fi roaming addresses.</span></span>  <br/> <span data-ttu-id="1106e-147">**風險**您認為無法風險，例如可疑的 IP 位址您任何 IP 位址所見在過去，競爭對手網路中的 IP 位址等等。</span><span class="sxs-lookup"><span data-stu-id="1106e-147">**Risky** Any IP addresses that you consider to be risky, such as suspicious IP addresses you've seen in the past, IP addresses in your competitors' networks, and so on.</span></span> <span data-ttu-id="1106e-148">根據預設，有風險的類別包含兩個 IP 標記：**匿名 proxy**和**Tor**</span><span class="sxs-lookup"><span data-stu-id="1106e-148">By default, the Risky categories includes two IP tags: **Anonymous proxy** and **Tor**</span></span> <br/> <span data-ttu-id="1106e-149">**VPN**您的遠端工作者使用任何 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1106e-149">**VPN** Any IP addresses that your remote workers use.</span></span>  <br/> |
   
7. <span data-ttu-id="1106e-150">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1106e-150">Choose **Save**.</span></span>
    
<span data-ttu-id="1106e-151">設定您的 IP 位址範圍之後，請記住，只有日後事件受到這些變更。</span><span class="sxs-lookup"><span data-stu-id="1106e-151">After you set up your IP address ranges, keep in mind that only future events are affected by these changes.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="1106e-152">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1106e-152">Next steps</span></span>

- [<span data-ttu-id="1106e-153">活動原則和警訊</span><span class="sxs-lookup"><span data-stu-id="1106e-153">Activity policies and alerts</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="1106e-154">異常偵測原則</span><span class="sxs-lookup"><span data-stu-id="1106e-154">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="1106e-155">將 SIEM 伺服器整合</span><span class="sxs-lookup"><span data-stu-id="1106e-155">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="1106e-156">檢閱並對 Office 365 雲端 App 安全性中的警示採取動作</span><span class="sxs-lookup"><span data-stu-id="1106e-156">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    

