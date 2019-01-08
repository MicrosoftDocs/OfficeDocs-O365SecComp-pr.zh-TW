---
title: 在 [安全性] 中檢視電子郵件安全性報表&amp;規範中心
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/07/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
description: 了解如何尋找並使用您的組織與 Office 365 企業版的電子郵件安全性報告。安全性中有電子郵件安全性報告&amp;規範中心。
ms.openlocfilehash: 670317707c5695161f23615fb87fe93258e8d95b
ms.sourcegitcommit: 30faa3ba91cab4c36e3d8d8ed5858d5269ea8a56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2019
ms.locfileid: "27749327"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="13923-104">在 [安全性] 中檢視電子郵件安全性報表&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="13923-104">View email security reports in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="13923-p102">提供各種電子郵件安全性報告所[安全性&amp;規範中心](https://security.microsoft.com)可協助您查看如何在 Office 365 中的反垃圾郵件和反惡意程式碼功能會保護您的組織。如果您有[必要的權限](#what-permissions-are-needed-to-view-these-reports)，您可以檢視這些報告安全性&amp;移至**報表**的規範中心\>**儀表板**。</span><span class="sxs-lookup"><span data-stu-id="13923-p102">A variety of email security reports are available in the [Security &amp; Compliance Center](https://security.microsoft.com) to help you see how anti-spam and anti-malware features in Office 365 are protecting your organization. If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.</span></span>
  
![安全性&amp;規範中心儀表板可協助您看到其用於進階威脅保護](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="13923-108">您的電子郵件安全性報告包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="13923-108">Your email security reports include the following:</span></span>
  
- [<span data-ttu-id="13923-109">威脅保護狀態報表</span><span class="sxs-lookup"><span data-stu-id="13923-109">Threat Protection Status report</span></span>](view-email-security-reports.md#tps) 
    
- <span data-ttu-id="13923-110">[惡意程式碼偵測] 報告](view-email-security-reports.md#maldet)</span><span class="sxs-lookup"><span data-stu-id="13923-110">[Malware Detections report](view-email-security-reports.md#maldet)</span></span>
    
- [<span data-ttu-id="13923-111">最常用的惡意程式碼報告</span><span class="sxs-lookup"><span data-stu-id="13923-111">Top Malware report</span></span>](#top-malware-report)
    
- [<span data-ttu-id="13923-112">上方的寄件者和收件者的報表</span><span class="sxs-lookup"><span data-stu-id="13923-112">Top Senders and Recipients report</span></span>](view-email-security-reports.md#topsenders)
    
- [<span data-ttu-id="13923-113">詐騙郵件報告</span><span class="sxs-lookup"><span data-stu-id="13923-113">Spoof Mail report</span></span>](#spoof-mail-report)
    
- <span data-ttu-id="13923-114">[垃圾郵件偵測] 報告](#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="13923-114">[Spam Detections report](#spam-detections-report)</span></span>
    
- [<span data-ttu-id="13923-115">傳送和接收的電子郵件報告</span><span class="sxs-lookup"><span data-stu-id="13923-115">Sent and received email report</span></span>](view-email-security-reports.md#sentreceivedemail)
    
- <span data-ttu-id="13923-116">[使用者報告的郵件報告](view-email-security-reports.md#userreported)（新增 ！）</span><span class="sxs-lookup"><span data-stu-id="13923-116">[User-reported messages report](view-email-security-reports.md#userreported) (new!)</span></span> 
    
## <a name="threat-protection-status-report"></a><span data-ttu-id="13923-117">威脅保護狀態報表</span><span class="sxs-lookup"><span data-stu-id="13923-117">Threat Protection Status report</span></span>

<span data-ttu-id="13923-p103">新的**威脅保護狀態**報表是智慧顯示已偵測到並封鎖的 Exchange Online Protection 的惡意電子郵件。這份報告顯示電子郵件會被識別為惡意程式碼或網路釣魚嘗試的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="13923-p103">The new **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection. This report shows information about email identified as malware or a phishing attempt.</span></span> 

> [!NOTE]
> <span data-ttu-id="13923-p104">威脅保護狀態報表是供使用者具有[Office 365 ATP](office-365-atp.md)或[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP);不過，ATP 客戶的威脅保護狀態報表中所顯示的資訊可能會包含超過 EOP 客戶可以看到不同的資料。例如，EOP 客戶可以檢視電子郵件、 但不是[在 SharePoint Online、 OneDrive 或 Microsoft 小組中偵測到惡意檔案](atp-for-spo-odb-and-teams.md)的相關資訊、 ATP 特定功能中偵測到惡意程式碼的相關資訊。（[解更多關於 ATP 報告](view-reports-for-atp.md)）。</span><span class="sxs-lookup"><span data-stu-id="13923-p104">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see. For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md), an ATP-specific capability. ([Learn more about ATP reports](view-reports-for-atp.md).)</span></span>
  
<span data-ttu-id="13923-123">若要檢視中的這份報告，[安全性&amp;規範中心](https://security.microsoft.com)、 移至 [**報表** \> **儀表板** \> **威脅保護狀態**。</span><span class="sxs-lookup"><span data-stu-id="13923-123">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![威脅保護狀態報表](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
<span data-ttu-id="13923-p105">當您首次開啟威脅保護狀態報告時，報告會顯示資料過去 7 天預設;不過，您可以按一下 [**篩選**及多達 90 天的詳細資料變更的日期範圍。這份報告 」 很適合用來檢視的效益與您組織的 Exchange Online Protection 功能的影響長期趨勢。</span><span class="sxs-lookup"><span data-stu-id="13923-p105">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail. This report is useful for viewing the effectiveness and impact of your organization's Exchange Online Protection features, and for longer-term trending.</span></span> 
  
![威脅保護狀態報告的篩選器](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
<span data-ttu-id="13923-128">您也可以選擇是否要檢視的電子郵件會被識別為惡意的資料，識別為網路釣魚嘗試、 電子郵件或電子郵件被識別為包含惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="13923-128">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>
  
![威脅保護狀態報表檢視選項](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a><span data-ttu-id="13923-130">惡意程式碼偵測] 報告</span><span class="sxs-lookup"><span data-stu-id="13923-130">Malware Detections report</span></span>

<span data-ttu-id="13923-131">**惡意程式碼偵測**] 報告顯示為包含您的組織的惡意程式碼偵測多少的內送和外寄郵件。</span><span class="sxs-lookup"><span data-stu-id="13923-131">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span> 
  
<span data-ttu-id="13923-132">若要檢視中的這份報告，[安全性&amp;規範中心](https://security.microsoft.com)、 移至 [**報表** \> **儀表板** \> **惡意程式碼偵測**。</span><span class="sxs-lookup"><span data-stu-id="13923-132">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>
  
![惡意程式碼偵測] 報告範例](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
<span data-ttu-id="13923-p106">類似像威脅保護狀態報表的其他報表會顯示資料過去 7 天的預設。不過，您可以選擇要變更的日期範圍**篩選器**。</span><span class="sxs-lookup"><span data-stu-id="13923-p106">Similar to other reports, like the Threat Protection Status report, the report displays data for the past seven days by default. However, you can choose **Filters** to change the date range.</span></span> 
  
## <a name="top-malware-report"></a><span data-ttu-id="13923-136">最常用的惡意程式碼報告</span><span class="sxs-lookup"><span data-stu-id="13923-136">Top Malware report</span></span>

<span data-ttu-id="13923-137">**前惡意程式碼**」 報告顯示各種類型的 Exchange Online 會利用偵測到惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="13923-137">The **Top Malware** report shows the various kinds of malware that was detected by Exchange Online.</span></span> 
  
<span data-ttu-id="13923-138">若要檢視中的這份報告，[安全性&amp;規範中心](https://security.microsoft.com)、 移至 [**報表** \> **儀表板** \> **前惡意程式碼**。</span><span class="sxs-lookup"><span data-stu-id="13923-138">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>
  
![SCC-EOP 上方惡意程式碼](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
<span data-ttu-id="13923-140">當您將滑鼠停留在圓形圖扇形擴展時，您可以看到種類的惡意程式碼和多少訊息所偵測到為具有該惡意程式碼的名稱。</span><span class="sxs-lookup"><span data-stu-id="13923-140">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>
  
<span data-ttu-id="13923-141">按一下 （或點選） 以新的瀏覽器視窗，可取得更詳細的報表檢視中開啟報表。</span><span class="sxs-lookup"><span data-stu-id="13923-141">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![這份報告顯示上方的惡意程式碼偵測到您的組織](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
<span data-ttu-id="13923-143">圖表下方您會看到偵測到惡意程式碼和多少訊息所偵測到為具有該惡意程式碼的清單。</span><span class="sxs-lookup"><span data-stu-id="13923-143">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>
  
## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="13923-144">上方的寄件者和收件者的報表</span><span class="sxs-lookup"><span data-stu-id="13923-144">Top Senders and Recipients report</span></span>

<span data-ttu-id="13923-145">**Top 寄件者和收件者**報表是顯示在上方的電子郵件寄件者的圓形圖。</span><span class="sxs-lookup"><span data-stu-id="13923-145">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span> 
  
<span data-ttu-id="13923-146">若要檢視中的這份報告，[安全性&amp;規範中心](https://security.microsoft.com)、 移至 [**報表** \> **儀表板** \> **頂端的寄件者和收件者**。</span><span class="sxs-lookup"><span data-stu-id="13923-146">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>
  
![若要檢視這份報告，安全性&amp;規範管理中心，移至報表\>儀表板\>頂端的寄件者和收件者](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
<span data-ttu-id="13923-148">當您將滑鼠停留在圓形圖扇形擴展時，您可以看到傳送或接收的郵件計數。</span><span class="sxs-lookup"><span data-stu-id="13923-148">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>
  
<span data-ttu-id="13923-149">按一下 （或點選） 以新的瀏覽器視窗，可取得更詳細的報表檢視中開啟報表。</span><span class="sxs-lookup"><span data-stu-id="13923-149">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="13923-p107">用於**顯示資料的**清單中選擇是否要檢視的主要寄件者、 接收器、 垃圾郵件收件者] 及惡意程式碼收件者的資料。您也可以參閱者接收到的進階威脅保護偵測到惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="13923-p107">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients. You can also see who received malware that was detected by Advanced Threat Protection.</span></span> 
  
![用於顯示資料的清單檢視的特定資訊](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
<span data-ttu-id="13923-153">圖表下方您會看見誰上方的電子郵件的寄件者或收件者已，以及郵件傳送或接收特定的時段進行計數。</span><span class="sxs-lookup"><span data-stu-id="13923-153">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>
  
## <a name="spoof-mail-report"></a><span data-ttu-id="13923-154">詐騙郵件報告</span><span class="sxs-lookup"><span data-stu-id="13923-154">Spoof Mail report</span></span>

<span data-ttu-id="13923-155">**詐騙郵件**報告顯示偵測多少詐騙郵件訊息，並的那些、 哪些已被視為 「 良好 」 （完成所需的合法的商業原因詐騙郵件）。</span><span class="sxs-lookup"><span data-stu-id="13923-155">The **Spoof Mail** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> 
  
<span data-ttu-id="13923-156">若要檢視中的這份報告，[安全性&amp;規範中心](https://security.microsoft.com)、 移至 [**報表** \> **儀表板** \> **詐騙郵件**。</span><span class="sxs-lookup"><span data-stu-id="13923-156">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>
  
![若要檢視這份報告，安全性&amp;規範管理中心，移至報表\>儀表板\>詐騙郵件](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
<span data-ttu-id="13923-158">當您將滑鼠停留在一天圖表中，您可以看到哪個多少詐騙郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="13923-158">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>
  
<span data-ttu-id="13923-159">按一下 （或點選） 以新的瀏覽器視窗，可取得更詳細的報表檢視中開啟報表。</span><span class="sxs-lookup"><span data-stu-id="13923-159">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
## <a name="spam-detections-report"></a><span data-ttu-id="13923-160">垃圾郵件偵測] 報告</span><span class="sxs-lookup"><span data-stu-id="13923-160">Spam Detections report</span></span>

<span data-ttu-id="13923-161">[**垃圾郵件偵測**] 報告顯示封鎖的 Exchange Online 中的垃圾郵件內容。</span><span class="sxs-lookup"><span data-stu-id="13923-161">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> 
  
<span data-ttu-id="13923-162">若要檢視中的這份報告，[安全性&amp;規範中心](https://security.microsoft.com)、 移至 [**報表** \> **儀表板** \> **垃圾郵件偵測**。</span><span class="sxs-lookup"><span data-stu-id="13923-162">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>
  
![若要檢視這份報告，安全性&amp;規範管理中心，移至報表\>儀表板\>EOP 垃圾郵件偵測](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
<span data-ttu-id="13923-p108">當您將滑鼠停留在一天圖表中，您可以看到多少個項目已封鎖那天，以及如何分類的項目。例如，您可以看到多少垃圾郵件已篩選，而且多少個項目來自封鎖的網際網路通訊協定 (IP) 位址。</span><span class="sxs-lookup"><span data-stu-id="13923-p108">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized. For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>
  
<span data-ttu-id="13923-166">按一下 （或點選） 以新的瀏覽器視窗，可取得更詳細的報表檢視中開啟報表。</span><span class="sxs-lookup"><span data-stu-id="13923-166">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![[垃圾郵件偵測] 報告會告訴您如何許多垃圾郵件被封鎖或篩選掉](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
<span data-ttu-id="13923-p109">圖表下方您會看到所偵測到的垃圾郵件項目清單。選取要檢視其他資訊，例如垃圾郵件項目已輸入或輸出、 其訊息識別碼，以及其收件者的項目。</span><span class="sxs-lookup"><span data-stu-id="13923-p109">Below the chart, you'll see a list of spam items that were detected. Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span>
  
## <a name="sent-and-received-email-report"></a><span data-ttu-id="13923-170">傳送和接收的電子郵件報告</span><span class="sxs-lookup"><span data-stu-id="13923-170">Sent and received email report</span></span>

<span data-ttu-id="13923-171">**已傳送及接收之電子郵件**報表是智慧來顯示資訊關於內送和外寄電子郵件，包括垃圾郵件偵測和惡意程式碼、 電子郵件會被識別為 [好]。</span><span class="sxs-lookup"><span data-stu-id="13923-171">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> 
  
<span data-ttu-id="13923-172">若要檢視中的這份報告，[安全性&amp;規範中心](https://security.microsoft.com)、 移至 [**報表** \> **儀表板** \> **傳送與接收之電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="13923-172">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>
  
![若要檢視這份報告，安全性&amp;規範管理中心，移至報表\>儀表板\>傳送與接收之電子郵件](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
<span data-ttu-id="13923-p110">當您將滑鼠停留在一天圖表中，您會看見多少訊息哪個，及其那些郵件分類的方式。例如，您會看見多少訊息所偵測到為包含惡意程式碼、 及其多少已識別為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="13923-p110">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized. For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>
  
<span data-ttu-id="13923-176">按一下 （或點選） 以新的瀏覽器視窗，可取得更詳細的報表檢視中開啟報表。</span><span class="sxs-lookup"><span data-stu-id="13923-176">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="13923-177">您可以使用**會自動換行向下的**清單檢視類型或方向 （內送和外寄） 的資訊。</span><span class="sxs-lookup"><span data-stu-id="13923-177">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span> 
  
![使用自動換行向下的清單檢視類型或方向的資訊](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
<span data-ttu-id="13923-p111">圖表下方您會看到的電子郵件類別，例如**GoodMail**、 **SpamContentFiltered**、 等等的清單。選取要檢視其他資訊，例如的惡意程式碼、 所採取的動作和是否電子郵件類別是傳入或傳出。</span><span class="sxs-lookup"><span data-stu-id="13923-p111">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on. Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>
  
![此報表會告訴您在反惡意程式碼、 反垃圾郵件及其他郵件偵測](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)
  
## <a name="user-reported-messages-report-new"></a><span data-ttu-id="13923-182">使用者報告的郵件報告 （新增 ！）</span><span class="sxs-lookup"><span data-stu-id="13923-182">User-reported messages report (new!)</span></span>

<span data-ttu-id="13923-183">**使用者報告的郵件**報告顯示使用者具有回報為垃圾郵件、 網路釣魚嘗試或良好郵件使用[報告郵件增益集](enable-the-report-message-add-in.md)的電子郵件訊息的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="13923-183">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>
  
<span data-ttu-id="13923-p112">詳細資料可供每則訊息，包括傳遞原因、 這類垃圾郵件原則例外狀況或設定您的組織的郵件流程規則。若要檢視的詳細資訊，請在使用者報告] 清單中選取項目，然後**摘要**及**詳細資料**] 索引標籤上檢視的資訊。</span><span class="sxs-lookup"><span data-stu-id="13923-p112">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization. To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span> 
  
![User-Reported 郵件報告顯示標示為垃圾郵件、 未垃圾郵件或網路釣魚嘗試的郵件使用者。](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
<span data-ttu-id="13923-187">若要檢視中的這份報告，[安全性&amp;規範中心](https://security.microsoft.com)，執行下列其中一個動作：</span><span class="sxs-lookup"><span data-stu-id="13923-187">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), do one of the following:</span></span>
  
- <span data-ttu-id="13923-188">移至 [ **Threat management** \> **儀表板** \> **使用者報告的郵件**。</span><span class="sxs-lookup"><span data-stu-id="13923-188">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>
    
- <span data-ttu-id="13923-189">移至 [ **Threat management** \> **檢閱** \> **使用者報告的郵件**。</span><span class="sxs-lookup"><span data-stu-id="13923-189">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>
    
![安全性&amp;規範中心選擇 Threat management\>檢閱\>使用者報告的郵件](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> <span data-ttu-id="13923-p113">在順序使用者報告的郵件報告正確運作，**必須開啟稽核記錄功能**會針對 Office 365 環境。這通常是由某人具有 「 稽核記錄 」 角色指派 Exchange Online。如需詳細資訊，請參閱[開啟 Office 365 稽核記錄搜尋開啟或關閉](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="13923-p113">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="13923-194">若要檢視這些報告需要哪些權限？</span><span class="sxs-lookup"><span data-stu-id="13923-194">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="13923-195">若要檢視和使用本文所述的報告**您必須具有適當的角色指派兩個安全性&amp;規範中心及 Exchange 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="13923-195">In order to view and use the reports described in this article, **you must have an appropriate role assigned in both the Security &amp; Compliance Center and the Exchange Admin Center**.</span></span>

- <span data-ttu-id="13923-196">Security&amp;規範中心，您必須具備一個指派的下列角色：</span><span class="sxs-lookup"><span data-stu-id="13923-196">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="13923-197">組織管理</span><span class="sxs-lookup"><span data-stu-id="13923-197">Organization Management</span></span>
    - <span data-ttu-id="13923-198">安全性管理員</span><span class="sxs-lookup"><span data-stu-id="13923-198">Security Administrator</span></span>
    - <span data-ttu-id="13923-199">安全性讀者</span><span class="sxs-lookup"><span data-stu-id="13923-199">Security Reader</span></span>

- <span data-ttu-id="13923-200">Exchange Online 的您必須具備下列角色指派其中一項：</span><span class="sxs-lookup"><span data-stu-id="13923-200">For Exchange Online, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="13923-201">組織管理</span><span class="sxs-lookup"><span data-stu-id="13923-201">Organization Management</span></span>
    - <span data-ttu-id="13923-202">僅檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="13923-202">View-only Organization Management</span></span>
    - <span data-ttu-id="13923-203">僅檢視收件者角色</span><span class="sxs-lookup"><span data-stu-id="13923-203">View-Only Recipients role</span></span>
    - <span data-ttu-id="13923-204">合規性管理</span><span class="sxs-lookup"><span data-stu-id="13923-204">Compliance Management</span></span>

<span data-ttu-id="13923-205">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="13923-205">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="13923-206">Office 365 安全性權限&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="13923-206">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="13923-207">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="13923-207">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="13923-208">如果報表不顯示資料吗？</span><span class="sxs-lookup"><span data-stu-id="13923-208">What if the reports aren't showing data?</span></span>

<span data-ttu-id="13923-p114">如果您看不見的資料在報告中，再次檢查您的原則已正確設定。若要深入了解，請參閱[Office 365 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="13923-p114">If you are not seeing data in your reports, double-check that your policies are set up correctly. To learn more, see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="13923-211">相關主題</span><span class="sxs-lookup"><span data-stu-id="13923-211">Related topics</span></span>

[<span data-ttu-id="13923-212">Office 365 電子郵件的反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="13923-212">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="13923-213">報告與 Office 365 安全性前瞻&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="13923-213">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
<span data-ttu-id="13923-214">[在 [安全性] 中建立報表的排程&amp;規範中心](create-a-schedule-for-a-report.md)</span><span class="sxs-lookup"><span data-stu-id="13923-214">[Create a schedule for a report in the Security &amp; Compliance Center](create-a-schedule-for-a-report.md)</span></span>
  
[<span data-ttu-id="13923-215">設定並下載安全性的自訂報告&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="13923-215">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

