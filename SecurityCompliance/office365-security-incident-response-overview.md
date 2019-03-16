---
title: Office 365 安全性事件回應
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 此解決方案會告訴您何種最常見網路安全性攻擊看起來會像在 Office 365 和給他們的回應方式
ms.openlocfilehash: 13e57d914138edc44d0001781459852fba994f61
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2019
ms.locfileid: "30656019"
---
# <a name="office-365-security-incident-response"></a><span data-ttu-id="3ce6d-103">Office 365 安全性事件回應</span><span class="sxs-lookup"><span data-stu-id="3ce6d-103">Office 365 Security Incident Response</span></span>

 <span data-ttu-id="3ce6d-104">**摘要：** 此解決方案會告訴您指標是針對 Office 365 中最常見的網路安全性攻擊、 如何以正面確認任何指定的攻擊，以及如何回應給它。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-104">**Summary:** This solution tells you what the indicators are for the most common cyber-security attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>
  
## <a name="overview"></a><span data-ttu-id="3ce6d-105">概觀</span><span class="sxs-lookup"><span data-stu-id="3ce6d-105">Overview</span></span>
<span data-ttu-id="3ce6d-106">可以阻撓並非所有網路攻擊。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-106">Not all cyber attacks can be thwarted.</span></span> <span data-ttu-id="3ce6d-107">攻擊者會不斷地尋找防禦策略中的新弱點或他們所利用舊的。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-107">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="3ce6d-108">藉此了解如何辨識攻擊可讓您更快速地來進行回應，縮短安全性事件的持續時間。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-108">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="3ce6d-109">這一系列的文章可協助您了解哪些特定類型的攻擊看起來會像在 Office 365 中，並讓您回應時，可採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-109">This series of article helps you understand what a particular type of attack might look like in Office 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="3ce6d-110">它們是了解快速進入點：</span><span class="sxs-lookup"><span data-stu-id="3ce6d-110">They are quick entry points to understanding:</span></span>
 
- <span data-ttu-id="3ce6d-111">查看攻擊的及其運作方式。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-111">What the attack is and how it works.</span></span>
- <span data-ttu-id="3ce6d-112">什麼簽署時，呼叫尋找危害 (IOC)，以及如何尋找的指標。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-112">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>
- <span data-ttu-id="3ce6d-113">如何將有正面確認攻擊。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-113">How to positively confirm the attack.</span></span>
- <span data-ttu-id="3ce6d-114">切斷攻擊，而且更有效率的所需步驟來保護您的組織在未來。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-114">Steps to take to cut off the attack and better protect your organization in the future.</span></span>
- <span data-ttu-id="3ce6d-115">在每個的深入資訊的連結攻擊類型。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-115">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="3ce6d-116">存回以下每月為更多文章會在新增一段時間。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-116">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="3ce6d-117">偵測並修復文章</span><span class="sxs-lookup"><span data-stu-id="3ce6d-117">Detect and remediate articles</span></span>

- [<span data-ttu-id="3ce6d-118">偵測並修復 Office 365 中的非法同意授權</span><span class="sxs-lookup"><span data-stu-id="3ce6d-118">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)
- [<span data-ttu-id="3ce6d-119">偵測並修復 Office 365 中 Outlook 規則與自訂表單資料隱碼攻擊</span><span class="sxs-lookup"><span data-stu-id="3ce6d-119">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)
 
## <a name="incident-response-articles"></a><span data-ttu-id="3ce6d-120">事件回應文章</span><span class="sxs-lookup"><span data-stu-id="3ce6d-120">Incident response articles</span></span>

- [<span data-ttu-id="3ce6d-121">對於 Office 365 遭入侵電子郵件帳戶的回覆</span><span class="sxs-lookup"><span data-stu-id="3ce6d-121">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="3ce6d-122">保護 Office 365 專業 cybersecurity 像</span><span class="sxs-lookup"><span data-stu-id="3ce6d-122">Secure Office 365 like a cybersecurity pro</span></span>
<span data-ttu-id="3ce6d-123">Office 365 訂閱隨附一組功能強大的安全性功能，可用來保護您的資料和您的使用者。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-123">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="3ce6d-124">使用[Office 365 安全性藍圖： 前的 30 天、 前 90 天及過後](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)實作 Microsoft 建議的最佳作法為保護您的 Office 365 租用戶。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-124">Use the [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>
- <span data-ttu-id="3ce6d-125">若要在第一個 30 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-125">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="3ce6d-126">這些有直接影響，而低影響您的使用者。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-126">These have immediate affect and are low-impact to your users.</span></span>
- <span data-ttu-id="3ce6d-127">若要在 90 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-127">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="3ce6d-128">這些需要較多時間規劃及實作，但是大幅改善您的安全性狀態</span><span class="sxs-lookup"><span data-stu-id="3ce6d-128">These take a bit more time to plan and implement but greatly improve your security posture</span></span>
- <span data-ttu-id="3ce6d-129">超過 90 天。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-129">Beyond 90 days.</span></span> <span data-ttu-id="3ce6d-130">這些增強功能建立您第一張 90 天的工作。</span><span class="sxs-lookup"><span data-stu-id="3ce6d-130">These enhancements build in your first 90 days work.</span></span>






