---
title: 將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: 輕鬆地識別設定之 IP 位址的實際辦公室 IP 位址，例如您將使用 Office 365 雲端應用程式安全性您可以設定群組的 IP 位址範圍。
ms.openlocfilehash: 76cb9625a46d1f5eceaab696de5dcbb72f4d2b47
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526174"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a><span data-ttu-id="0aa44-103">將您的 IP 位址分組，以簡化 Office 365 雲端 App 安全性中的管理</span><span class="sxs-lookup"><span data-stu-id="0aa44-103">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="0aa44-104">評估 * *\>**</span><span class="sxs-lookup"><span data-stu-id="0aa44-104">****Evaluation** \>**</span></span>|<span data-ttu-id="0aa44-105">規劃 * *\>**</span><span class="sxs-lookup"><span data-stu-id="0aa44-105">****Planning** \>**</span></span>|<span data-ttu-id="0aa44-106">部署 * *\>**</span><span class="sxs-lookup"><span data-stu-id="0aa44-106">****Deployment** \>**</span></span>|<span data-ttu-id="0aa44-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="0aa44-107">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="0aa44-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="0aa44-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="0aa44-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="0aa44-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="0aa44-110">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="0aa44-110">You are here!</span></span>  <br/> [<span data-ttu-id="0aa44-111">後續步驟</span><span class="sxs-lookup"><span data-stu-id="0aa44-111">Next steps</span></span>](#next-steps) <br/> |[<span data-ttu-id="0aa44-112">開始使用</span><span class="sxs-lookup"><span data-stu-id="0aa44-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="0aa44-p101">輕鬆地識別設定之 IP 位址的實際辦公室 IP 位址，例如您將使用 Office 365 雲端應用程式安全性您可以設定群組的 IP 位址範圍。定義這些範圍可讓您標記及分類 （英文），然後您可使用標記和自訂您的活動的記錄檔及提醒的類別會顯示與調查。</span><span class="sxs-lookup"><span data-stu-id="0aa44-p101">To easily identify sets of IP addresses that you'll use in Office 365 Cloud App Security, such as your physical office IP addresses, you can set up groups of IP address ranges. Defining these ranges lets you tag and categorize them, and then you can use tags and categories to customize how your activity logs and alerts are displayed and investigated.</span></span>
  
<span data-ttu-id="0aa44-p102">IP 範圍的每個群組可以標記使用您選擇，然後將標記可以會歸類根據 IP 類別 （例如 Corporate、 系統管理、 Risky、 和 VPN） 的預設清單的標籤名稱。支援 IPv4 和 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="0aa44-p102">Each group of IP ranges can be tagged with tag names that you choose, and then the tags can be categorized based on a default list of IP categories (such as Corporate, Administrative, Risky, and VPN). Both IPv4 and IPv6 addresses are supported.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0aa44-p103">您必須是執行本文中的程序的全域管理員或安全性管理員。若要深入了解，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="0aa44-p103">You must be a global administrator or security administrator to perform the procedures in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a><span data-ttu-id="0aa44-119">若要設定 IP 位址範圍新增 Office 365 雲端應用程式安全性</span><span class="sxs-lookup"><span data-stu-id="0aa44-119">To set up an IP address range in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="0aa44-p104">以全域管理員或安全性管理員中，移至[https://protection.office.com](https://protection.office.com)並使用您工作或學校的帳戶登入。(這會引導您安全性&amp;規範中心。)</span><span class="sxs-lookup"><span data-stu-id="0aa44-p104">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="0aa44-122">安全性&amp;規範中心選擇**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="0aa44-122">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="0aa44-123">選擇 [**移至 Office 365 的雲端應用程式安全性**]。</span><span class="sxs-lookup"><span data-stu-id="0aa44-123">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    ![安全性&amp;規範中心選擇管理進階警告移至 Office 365 雲端應用程式安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. <span data-ttu-id="0aa44-125">在右上角] 頁面上，按一下 [**設定** \> **IP 位址範圍**。</span><span class="sxs-lookup"><span data-stu-id="0aa44-125">On the upper right of the page, click **Settings** \> **IP address ranges**.</span></span>
    
    ![在 O365 雲端應用程式安全性]，選擇 [設定來存取您的系統和資料的設定](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)
  
5. <span data-ttu-id="0aa44-127">按一下加號的格式類似於 [新增] 按鈕 ( **+**)。</span><span class="sxs-lookup"><span data-stu-id="0aa44-127">Click the new button, which resembles a plus sign ( **+**).</span></span>
    
6. <span data-ttu-id="0aa44-128">在 [**新的 IP 位址範圍**] 視窗中，指定下列值：</span><span class="sxs-lookup"><span data-stu-id="0aa44-128">In the **New IP address range** window, specify the following values:</span></span> 
    
|<span data-ttu-id="0aa44-129">**欄位或清單**</span><span class="sxs-lookup"><span data-stu-id="0aa44-129">**Field or list**</span></span>|<span data-ttu-id="0aa44-130">**該怎麼辦**</span><span class="sxs-lookup"><span data-stu-id="0aa44-130">**What to do**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0aa44-131">**名稱**</span><span class="sxs-lookup"><span data-stu-id="0aa44-131">**Name**</span></span> <br/> |<span data-ttu-id="0aa44-p105">使用此欄位來管理您的 IP 位址範圍與設定。（您將不會看到此值活動記錄檔中的）。</span><span class="sxs-lookup"><span data-stu-id="0aa44-p105">Use this field to manage your IP address range and settings. (You won't see this value in activities logs.)</span></span>  <br/> |
|<span data-ttu-id="0aa44-134">**IP 位址範圍**</span><span class="sxs-lookup"><span data-stu-id="0aa44-134">**IP address ranges**</span></span> <br/> |<span data-ttu-id="0aa44-p106">指定的範圍會使用網路首碼標記法 （也稱為 CIDR 表示法）。例如，192.168.1.0/27 包含值 192.168.1.0 透過 192.168.1.31 （含） 的範圍。</span><span class="sxs-lookup"><span data-stu-id="0aa44-p106">Specify a range, using network prefix notation (also known as CIDR notation). For example, 192.168.1.0/27 includes the range of values 192.168.1.0 through 192.168.1.31 (inclusive).</span></span>  <br/> |
|<span data-ttu-id="0aa44-137">**位置**和**登錄 ISP**</span><span class="sxs-lookup"><span data-stu-id="0aa44-137">**Location** and **Registered ISP**</span></span> <br/> |<span data-ttu-id="0aa44-p107">指定 IP 位址範圍的位置和網際網路服務提供者 (ISP)。這會覆寫公用欄位定義的地址，這是有用的情況下，例如 IP 位址是，會被視為公開在愛爾蘭但實際上是在美國</span><span class="sxs-lookup"><span data-stu-id="0aa44-p107">Specify the location and Internet Service Provider (ISP) for the IP address range. This overrides the public fields defined for the addresses, which is helpful for cases, such as an IP address is that is considered publicly to be in Ireland but is actually in the U.S.</span></span>  <br/> |
|<span data-ttu-id="0aa44-140">**標籤**</span><span class="sxs-lookup"><span data-stu-id="0aa44-140">**Tags**</span></span> <br/> |<span data-ttu-id="0aa44-p108">使用標籤來命名您的 IP 位址的群組。（不同於 [名稱] 欄位中，您會看到標記活動記錄檔中。）輸入的單字或片語想要使用的標籤。您可以新增任意數量的標記為您想要為每個 IP 位址範圍。如果您已經設定標籤並想要新增此 IP 位址範圍，請從目前的標記顯示當您開始輸入的清單中選擇。</span><span class="sxs-lookup"><span data-stu-id="0aa44-p108">Use tags to name your groups of IP addresses. (Unlike the Name field, you will see Tags in activity logs.) Type a word or phrase that you want to use for a tag. You can add as many tags as you like for each IP address range. And if you've already set up a tag and you want to add this IP address range to it, choose it from the list of current tags that appear as you start typing.</span></span>  <br/> |
|<span data-ttu-id="0aa44-145">**類別**</span><span class="sxs-lookup"><span data-stu-id="0aa44-145">**Category**</span></span> <br/> | <span data-ttu-id="0aa44-p109">將類別指派給您標記以方便辨識來自特定 IP 位址的活動。選擇 [從下列選項：</span><span class="sxs-lookup"><span data-stu-id="0aa44-p109">Assign categories to your tags to make it easier to recognize activities that come from certain IP addresses. Choose from the following options:  </span></span><br/> <span data-ttu-id="0aa44-148">**系統管理**所有您的系統管理員的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0aa44-148">**Administrative** All of the IP addresses of your admins.</span></span>  <br/> <span data-ttu-id="0aa44-149">**雲端提供者**您為雲端中的 proxy IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0aa44-149">**Cloud provider** The IP address of your proxy in the cloud.</span></span>  <br/> <span data-ttu-id="0aa44-150">**公司**所有的 IP 位址在內部網路、 您分公司、 和 Wi-fi 漫遊地址。</span><span class="sxs-lookup"><span data-stu-id="0aa44-150">**Corporate** All of the IP addresses in your internal network, your branch offices, and your Wi-Fi roaming addresses.</span></span>  <br/> <span data-ttu-id="0aa44-p110">**risky**您考慮要 risky，例如可疑的 IP 位址您任何 IP 位址所見過去、 競爭者的網路中的 IP 位址等等。根據預設，Risky 類別包含兩個 IP 標記：**匿名 proxy**和**Tor**</span><span class="sxs-lookup"><span data-stu-id="0aa44-p110">**Risky** Any IP addresses that you consider to be risky, such as suspicious IP addresses you've seen in the past, IP addresses in your competitors' networks, and so on. By default, the Risky categories includes two IP tags: **Anonymous proxy** and **Tor**</span></span> <br/> <span data-ttu-id="0aa44-153">**VPN**您的遠端工作者使用任何 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0aa44-153">**VPN** Any IP addresses that your remote workers use.</span></span>  <br/> |
   
7. <span data-ttu-id="0aa44-154">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="0aa44-154">Choose **Save**.</span></span>
    
<span data-ttu-id="0aa44-155">設定您的 IP 位址範圍之後，請記住僅未來事件受到這些變更。</span><span class="sxs-lookup"><span data-stu-id="0aa44-155">After you set up your IP address ranges, keep in mind that only future events are affected by these changes.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="0aa44-156">後續步驟</span><span class="sxs-lookup"><span data-stu-id="0aa44-156">Next steps</span></span>

- [<span data-ttu-id="0aa44-157">活動原則及提醒</span><span class="sxs-lookup"><span data-stu-id="0aa44-157">Activity policies and alerts</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="0aa44-158">異常偵測原則</span><span class="sxs-lookup"><span data-stu-id="0aa44-158">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="0aa44-159">整合 SIEM server</span><span class="sxs-lookup"><span data-stu-id="0aa44-159">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="0aa44-160">檢閱並對 Office 365 雲端 App 安全性中的警示採取動作</span><span class="sxs-lookup"><span data-stu-id="0aa44-160">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    

