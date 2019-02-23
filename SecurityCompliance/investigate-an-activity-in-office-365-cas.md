---
title: 調查 Office 365 雲端 App 安全性中的活動
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
ms.assetid: 15fa4545-28b4-4dd4-bf85-88e0926bd5fc
description: '與 Office 365 雲端應用程式安全性]，您可以查看有什麼新鮮事 Office 365 環境中所要尋找一段與調查活動和帳戶。 '
ms.openlocfilehash: 0cc3860d953b40b0b0c247af6fb2b157d1abb235
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218963"
---
# <a name="investigate-an-activity-in-office-365-cloud-app-security"></a><span data-ttu-id="325d4-103">調查 Office 365 雲端 App 安全性中的活動</span><span class="sxs-lookup"><span data-stu-id="325d4-103">Investigate an activity in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="325d4-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="325d4-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="325d4-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="325d4-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="325d4-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="325d4-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="325d4-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="325d4-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="325d4-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="325d4-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="325d4-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="325d4-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="325d4-110">開始部署</span><span class="sxs-lookup"><span data-stu-id="325d4-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="325d4-111">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="325d4-111">You are here!</span></span>  <br/> [<span data-ttu-id="325d4-112">後續步驟</span><span class="sxs-lookup"><span data-stu-id="325d4-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="325d4-p101">Office 365 雲端應用程式安全性適用於您的[Office 365 稽核記錄](detailed-properties-in-the-office-365-audit-log.md)。與 Office 365 雲端應用程式安全性] 以全域管理員或安全性管理員，您可以使用 [活動記錄檔] 頁面上查看您的組織如何使用 Office 365 中的潛在問題。</span><span class="sxs-lookup"><span data-stu-id="325d4-p101">Office 365 Cloud App Security works with your [Office 365 audit log](detailed-properties-in-the-office-365-audit-log.md). With Office 365 Cloud App Security, as a global administrator or security administrator, you can use the Activity log page to see potential issues in how your organization is using Office 365.</span></span>
  
## <a name="how-to-get-to-the-activity-log-page"></a><span data-ttu-id="325d4-115">如何取得活動記錄檔] 頁面上</span><span class="sxs-lookup"><span data-stu-id="325d4-115">How to get to the Activity log page</span></span>

1. <span data-ttu-id="325d4-116">移至雲端應用程式安全性入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="325d4-116">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="325d4-117">在不同螢幕頂端導覽列中，選擇 [**調查** \> **活動記錄檔**。</span><span class="sxs-lookup"><span data-stu-id="325d4-117">In the navigation bar across the top of the screen, choose **Investigate** \> **Activity log**.</span></span><br/><span data-ttu-id="325d4-118">![在 O365 CAS 入口網站中選擇 [調查]。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span><span class="sxs-lookup"><span data-stu-id="325d4-118">![In the O365 CAS portal, choose Investigate.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span></span>
  
## <a name="review-and-investigate-activities"></a><span data-ttu-id="325d4-119">檢閱並調查活動</span><span class="sxs-lookup"><span data-stu-id="325d4-119">Review and investigate activities</span></span>

<span data-ttu-id="325d4-p102">在活動記錄檔] 頁面上，您可以看到發生使用 Office 365 組織內的各種活動清單。您可以使用不同螢幕頂端的篩選器以專注於特定類型的活動或特定使用者。例如，下列圖像顯示組織的 Office 365 管理員帳戶的密碼變更的詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="325d4-p102">On the Activity log page, you can see a list of various activities that are taking place within your organization using Office 365. You can use filters across the top of the screen to focus on a specific type of activity or a specific user. For example, the following image shows information about an organization's Office 365 admin account's password change:</span></span>
  
![在 Office 365 雲端應用程式安全性]，選擇 [調查\>活動記錄檔。](media/5d54600c-59cd-4f33-b4f0-29b75c37baae.png)
  
<span data-ttu-id="325d4-p103">當您在查看活動記錄檔中的每個項目，您可以按一下省略符號尋找其他相關的活動。例如，您可以檢視其他相同的類型，從相同的 IP 位址，或從相同的國家/地區的活動。</span><span class="sxs-lookup"><span data-stu-id="325d4-p103">As you look at each item in the Activity log, you can click the ellipses to find other related activities. For example, you can view other activities of the same type, from the same IP address, or from the same country/region.</span></span>
  
<span data-ttu-id="325d4-p104">您可以太檢視許多其他種類的活動的相關資訊。例如，以下是一些您可以檢視活動記錄檔中的活動：</span><span class="sxs-lookup"><span data-stu-id="325d4-p104">You can view information about many other kinds of activities, too. For example, here are some of the activities you can view in the Activity log:</span></span>
  
- <span data-ttu-id="325d4-128">若要新增或移除群組的成員</span><span class="sxs-lookup"><span data-stu-id="325d4-128">Members added to or removed from groups</span></span>
    
- <span data-ttu-id="325d4-129">在 [使用者授權的變更</span><span class="sxs-lookup"><span data-stu-id="325d4-129">Changes in user licenses</span></span>
    
- <span data-ttu-id="325d4-130">檔案或資料夾共用內部或外部</span><span class="sxs-lookup"><span data-stu-id="325d4-130">Files or folders shared internally or externally</span></span>
    
- <span data-ttu-id="325d4-131">建立或刪除網站或網站集合</span><span class="sxs-lookup"><span data-stu-id="325d4-131">Created or deleted sites or site collections</span></span>
    
- <span data-ttu-id="325d4-132">電子郵件轉接規則</span><span class="sxs-lookup"><span data-stu-id="325d4-132">Email forwarding rules</span></span>
    
<span data-ttu-id="325d4-133">使用 [活動記錄檔] 頁面上取得熟悉您組織中的人員如何使用 Office 365 及什麼問題時可能會隨時擁有。</span><span class="sxs-lookup"><span data-stu-id="325d4-133">Use the Activity log page to get acquainted with how people in your organization are using Office 365 and what issues they might be having along the way.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="325d4-134">後續步驟</span><span class="sxs-lookup"><span data-stu-id="325d4-134">Next steps</span></span>

- [<span data-ttu-id="325d4-135">檢閱並對 Office 365 雲端 App 安全性中的警示採取動作</span><span class="sxs-lookup"><span data-stu-id="325d4-135">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="325d4-136">檢閱您[的 Office 365 雲端應用程式安全性使用率活動](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="325d4-136">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

