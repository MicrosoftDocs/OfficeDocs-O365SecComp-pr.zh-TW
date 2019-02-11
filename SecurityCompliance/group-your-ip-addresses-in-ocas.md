---
title: 將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: 輕鬆地識別設定之 IP 位址的實際辦公室 IP 位址，例如您將使用 Office 365 雲端應用程式安全性您可以設定群組的 IP 位址範圍。
ms.openlocfilehash: 42a62d2dd9771fb7d3ac992f4e0f8b5f6826efe3
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603734"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a><span data-ttu-id="db795-103">將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理</span><span class="sxs-lookup"><span data-stu-id="db795-103">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="db795-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="db795-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="db795-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="db795-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="db795-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="db795-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="db795-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="db795-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="db795-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="db795-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="db795-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="db795-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="db795-110">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="db795-110">You are here!</span></span>  <br/> [<span data-ttu-id="db795-111">後續步驟</span><span class="sxs-lookup"><span data-stu-id="db795-111">Next steps</span></span>](#next-steps) <br/> |[<span data-ttu-id="db795-112">開始使用</span><span class="sxs-lookup"><span data-stu-id="db795-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="db795-p101">輕鬆地識別設定之 IP 位址的實際辦公室 IP 位址，例如您將使用 Office 365 雲端應用程式安全性您可以設定群組的 IP 位址範圍。定義這些範圍可讓您標記及分類 （英文），然後您可使用標記和自訂您的活動的記錄檔及提醒的類別會顯示與調查。</span><span class="sxs-lookup"><span data-stu-id="db795-p101">To easily identify sets of IP addresses that you'll use in Office 365 Cloud App Security, such as your physical office IP addresses, you can set up groups of IP address ranges. Defining these ranges lets you tag and categorize them, and then you can use tags and categories to customize how your activity logs and alerts are displayed and investigated.</span></span>
  
<span data-ttu-id="db795-p102">IP 範圍的每個群組可以標記使用您選擇，然後將標記可以會歸類根據 IP 類別 （例如 Corporate、 系統管理、 Risky、 和 VPN） 的預設清單的標籤名稱。支援 IPv4 和 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="db795-p102">Each group of IP ranges can be tagged with tag names that you choose, and then the tags can be categorized based on a default list of IP categories (such as Corporate, Administrative, Risky, and VPN). Both IPv4 and IPv6 addresses are supported.</span></span>
  
> [!NOTE]
> <span data-ttu-id="db795-p103">您必須是執行本文中的程序的全域管理員或安全性管理員。若要深入了解，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="db795-p103">You must be a global administrator or security administrator to perform the procedures in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a><span data-ttu-id="db795-119">若要設定 IP 位址範圍新增 Office 365 雲端應用程式安全性</span><span class="sxs-lookup"><span data-stu-id="db795-119">To set up an IP address range in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="db795-120">以全域管理員或安全性管理員中，移至雲端應用程式安全性入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="db795-120">As a global administrator or security administrator, go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
    
2. <span data-ttu-id="db795-121">在右上角] 頁面上，按一下 [**設定** \> **IP 位址範圍**。</span><span class="sxs-lookup"><span data-stu-id="db795-121">On the upper right of the page, click **Settings** \> **IP address ranges**.</span></span><br><span data-ttu-id="db795-122">![在 O365 雲端應用程式安全性]，選擇 [設定來存取您的系統和資料的設定](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)</span><span class="sxs-lookup"><span data-stu-id="db795-122">![In O365 Cloud App Security, choose Settings to access your system and data settings](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)</span></span><br>
  
3. <span data-ttu-id="db795-123">按一下加號的格式類似於 [新增] 按鈕 ( **+**)。</span><span class="sxs-lookup"><span data-stu-id="db795-123">Click the new button, which resembles a plus sign ( **+**).</span></span>
    
4. <span data-ttu-id="db795-124">在 [**新的 IP 位址範圍**] 視窗中，指定下列值：</span><span class="sxs-lookup"><span data-stu-id="db795-124">In the **New IP address range** window, specify the following values:</span></span> 
    
|<span data-ttu-id="db795-125">**欄位或清單**</span><span class="sxs-lookup"><span data-stu-id="db795-125">**Field or list**</span></span>|<span data-ttu-id="db795-126">**該怎麼辦**</span><span class="sxs-lookup"><span data-stu-id="db795-126">**What to do**</span></span>|
|:-----|:-----|
|<span data-ttu-id="db795-127">**名稱**</span><span class="sxs-lookup"><span data-stu-id="db795-127">**Name**</span></span> <br/> |<span data-ttu-id="db795-p104">使用此欄位來管理您的 IP 位址範圍與設定。（您將不會看到此值活動記錄檔中的）。</span><span class="sxs-lookup"><span data-stu-id="db795-p104">Use this field to manage your IP address range and settings. (You won't see this value in activities logs.)</span></span>  <br/> |
|<span data-ttu-id="db795-130">**IP 位址範圍**</span><span class="sxs-lookup"><span data-stu-id="db795-130">**IP address ranges**</span></span> <br/> |<span data-ttu-id="db795-p105">指定的範圍會使用網路首碼標記法 （也稱為 CIDR 表示法）。例如，192.168.1.0/27 包含值 192.168.1.0 透過 192.168.1.31 （含） 的範圍。</span><span class="sxs-lookup"><span data-stu-id="db795-p105">Specify a range, using network prefix notation (also known as CIDR notation). For example, 192.168.1.0/27 includes the range of values 192.168.1.0 through 192.168.1.31 (inclusive).</span></span>  <br/> |
|<span data-ttu-id="db795-133">**位置**和**登錄 ISP**</span><span class="sxs-lookup"><span data-stu-id="db795-133">**Location** and **Registered ISP**</span></span> <br/> |<span data-ttu-id="db795-p106">指定 IP 位址範圍的位置和網際網路服務提供者 (ISP)。這會覆寫公用欄位定義的地址，這是有用的情況下，例如 IP 位址是，會被視為公開在愛爾蘭但實際上是在美國</span><span class="sxs-lookup"><span data-stu-id="db795-p106">Specify the location and Internet Service Provider (ISP) for the IP address range. This overrides the public fields defined for the addresses, which is helpful for cases, such as an IP address is that is considered publicly to be in Ireland but is actually in the U.S.</span></span>  <br/> |
|<span data-ttu-id="db795-136">**標籤**</span><span class="sxs-lookup"><span data-stu-id="db795-136">**Tags**</span></span> <br/> |<span data-ttu-id="db795-p107">使用標籤來命名您的 IP 位址的群組。（不同於 [名稱] 欄位中，您會看到標記活動記錄檔中。）輸入的單字或片語想要使用的標籤。您可以新增任意數量的標記為您想要為每個 IP 位址範圍。如果您已經設定標籤並想要新增此 IP 位址範圍，請從目前的標記顯示當您開始輸入的清單中選擇。</span><span class="sxs-lookup"><span data-stu-id="db795-p107">Use tags to name your groups of IP addresses. (Unlike the Name field, you will see Tags in activity logs.) Type a word or phrase that you want to use for a tag. You can add as many tags as you like for each IP address range. And if you've already set up a tag and you want to add this IP address range to it, choose it from the list of current tags that appear as you start typing.</span></span>  <br/> |
|<span data-ttu-id="db795-141">**類別**</span><span class="sxs-lookup"><span data-stu-id="db795-141">**Category**</span></span> <br/> | <span data-ttu-id="db795-p108">將類別指派給您標記以方便辨識來自特定 IP 位址的活動。選擇 [從下列選項：</span><span class="sxs-lookup"><span data-stu-id="db795-p108">Assign categories to your tags to make it easier to recognize activities that come from certain IP addresses. Choose from the following options:  </span></span><br/> <span data-ttu-id="db795-144">**系統管理**所有您的系統管理員的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="db795-144">**Administrative** All of the IP addresses of your admins.</span></span>  <br/> <span data-ttu-id="db795-145">**雲端提供者**您為雲端中的 proxy IP 位址。</span><span class="sxs-lookup"><span data-stu-id="db795-145">**Cloud provider** The IP address of your proxy in the cloud.</span></span>  <br/> <span data-ttu-id="db795-146">**公司**所有的 IP 位址在內部網路、 您分公司、 和 Wi-fi 漫遊地址。</span><span class="sxs-lookup"><span data-stu-id="db795-146">**Corporate** All of the IP addresses in your internal network, your branch offices, and your Wi-Fi roaming addresses.</span></span>  <br/> <span data-ttu-id="db795-p109">**risky**您考慮要 risky，例如可疑的 IP 位址您任何 IP 位址所見過去、 競爭者的網路中的 IP 位址等等。根據預設，Risky 類別包含兩個 IP 標記：**匿名 proxy**和**Tor**</span><span class="sxs-lookup"><span data-stu-id="db795-p109">**Risky** Any IP addresses that you consider to be risky, such as suspicious IP addresses you've seen in the past, IP addresses in your competitors' networks, and so on. By default, the Risky categories includes two IP tags: **Anonymous proxy** and **Tor**</span></span> <br/> <span data-ttu-id="db795-149">**VPN**您的遠端工作者使用任何 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="db795-149">**VPN** Any IP addresses that your remote workers use.</span></span>  <br/> |
   
7. <span data-ttu-id="db795-150">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="db795-150">Choose **Save**.</span></span>
    
<span data-ttu-id="db795-151">設定您的 IP 位址範圍之後，請記住僅未來事件受到這些變更。</span><span class="sxs-lookup"><span data-stu-id="db795-151">After you set up your IP address ranges, keep in mind that only future events are affected by these changes.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="db795-152">後續步驟</span><span class="sxs-lookup"><span data-stu-id="db795-152">Next steps</span></span>

- [<span data-ttu-id="db795-153">活動原則及提醒</span><span class="sxs-lookup"><span data-stu-id="db795-153">Activity policies and alerts</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="db795-154">異常偵測原則</span><span class="sxs-lookup"><span data-stu-id="db795-154">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="db795-155">整合 SIEM server</span><span class="sxs-lookup"><span data-stu-id="db795-155">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="db795-156">檢閱並對 Office 365 雲端 App 安全性中的警示採取動作</span><span class="sxs-lookup"><span data-stu-id="db795-156">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    

