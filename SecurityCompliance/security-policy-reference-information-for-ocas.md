---
title: Office 365 雲端 App 安全性的安全性原則參考資訊
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aef6c88f-7f47-40ef-9503-2b400e3bc6fd
description: 取得與 Office 365 活動原則和異常偵測原則的說明。
ms.openlocfilehash: db44b6cbf5b8c2783cba9862107120d2c33c1559
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264625"
---
# <a name="security-policy-reference-information-for-office-365-cloud-app-security"></a><span data-ttu-id="2f218-103">Office 365 雲端 App 安全性的安全性原則參考資訊</span><span class="sxs-lookup"><span data-stu-id="2f218-103">Security policy reference information for Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="2f218-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="2f218-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="2f218-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="2f218-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="2f218-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="2f218-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="2f218-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="2f218-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="2f218-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="2f218-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="2f218-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="2f218-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="2f218-110">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="2f218-110">You are here!</span></span>  <br/> [<span data-ttu-id="2f218-111">下一步</span><span class="sxs-lookup"><span data-stu-id="2f218-111">Next step</span></span>](review-office-365-cas-alerts.md) <br/> |[<span data-ttu-id="2f218-112">開始使用</span><span class="sxs-lookup"><span data-stu-id="2f218-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="2f218-113">與 Office 365 雲端 App 安全性，如果您是全域系統管理員或安全性系統管理員，您可以定義或編輯原則的兩種組織：</span><span class="sxs-lookup"><span data-stu-id="2f218-113">With Office 365 Cloud App Security, if you are a global administrator or security administrator, you can define or edit two kinds of policies for your organization:</span></span>
  
- <span data-ttu-id="2f218-114">定義的**[活動原則](activity-policies-and-alerts.md)**。</span><span class="sxs-lookup"><span data-stu-id="2f218-114">**[Activity policies](activity-policies-and-alerts.md)** that you define.</span></span> <span data-ttu-id="2f218-115">這些原則乃是根據您定義為可疑，例如使用者嘗試使用在其他地區/國家/地區外什麼是一個小時內正常的組織或嘗試登入的使用者數量為極大的系統管理員認證登入活動.</span><span class="sxs-lookup"><span data-stu-id="2f218-115">These policies are based on activities that you define as suspicious, such as users attempting to sign in with admin credentials in other regions/countries outside what's normal for your organization, or an extreme number of sign-in attempts for a user within an hour.</span></span> <span data-ttu-id="2f218-116">若要深入了解，請參閱[活動原則與 Office 365 雲端 App 安全性中的警示](activity-policies-and-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="2f218-116">To learn more, see [Activity policies and alerts in Office 365 Cloud App Security](activity-policies-and-alerts.md).</span></span>
    
- <span data-ttu-id="2f218-117">**[異常偵測原則](anomaly-detection-policies-in-ocas.md)** 是可以使用 「 郵件答錄機方塊 」 與 Office 365 雲端 App 安全性。</span><span class="sxs-lookup"><span data-stu-id="2f218-117">**[Anomaly detection policies](anomaly-detection-policies-in-ocas.md)** that are available "out of the box" with Office 365 Cloud App Security.</span></span> <span data-ttu-id="2f218-118">這些原則乃是根據自動偵測到可疑活動的演算法。</span><span class="sxs-lookup"><span data-stu-id="2f218-118">These policies are based on automatic algorithms that detect suspicious activity.</span></span> <span data-ttu-id="2f218-119">這些預設原則會自動觀看異常和觸發警示。</span><span class="sxs-lookup"><span data-stu-id="2f218-119">These default policies watch for anomalies and trigger alerts automatically.</span></span> <span data-ttu-id="2f218-120">若要深入了解，請參閱 < <b0>Office 365 雲端 App 安全性中的異常偵測原則</b0>。</span><span class="sxs-lookup"><span data-stu-id="2f218-120">To learn more, see [Anomaly detection policies in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md).</span></span>
    

