---
title: 威脅總管檢視
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/18/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
description: 了解各種不同的 （也稱為威脅總管） 的 Office 365 進階威脅防護計劃 2 的一部分的總管中可用的檢視。
ms.openlocfilehash: bcfa044db6844d9459b3dd62d9ced1cd37a999ec
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260515"
---
# <a name="threat-explorer-views"></a><span data-ttu-id="1b43f-103">威脅總管檢視</span><span class="sxs-lookup"><span data-stu-id="1b43f-103">Threat Explorer views</span></span>

<span data-ttu-id="1b43f-104">[威脅總管](use-explorer-in-security-and-compliance.md)是功能強大，接近即時的工具，以協助調查及回應安全性威脅的安全性作業小組&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="1b43f-104">[Threat Explorer](use-explorer-in-security-and-compliance.md) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="1b43f-105">檔案總管] 會顯示組織資訊可疑的惡意軟體和電子郵件中的釣魚程式和 Office 365 中的檔案，以及其他安全性威脅及風險。</span><span class="sxs-lookup"><span data-stu-id="1b43f-105">Explorer displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span> 

<span data-ttu-id="1b43f-106">當您首次開啟檔案總管時的預設檢視中顯示電子郵件惡意程式碼偵測在過去 7 天。</span><span class="sxs-lookup"><span data-stu-id="1b43f-106">When you first open Explorer, the default view shows email malware detections for the past 7 days.</span></span> 

![威脅總管](media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="1b43f-108">瀏覽器也可以顯示安全性保護功能在 Office 365 中，包括[安全連結](atp-safe-links.md)和[安全附件](atp-safe-attachments.md)，您可以修改顯示過去 30 天的資料。</span><span class="sxs-lookup"><span data-stu-id="1b43f-108">Explorer can also show security protection features in Office 365, including [Safe Links](atp-safe-links.md) and [Safe Attachments](atp-safe-attachments.md) and can be modified to show data for the past 30 days.</span></span> 

> [!NOTE]
> <span data-ttu-id="1b43f-109">如果您有 Office 365 進階威脅防護方案 2 或 Office 365 E5 試用訂閱，只會針對在過去 7 天看到偵測和電子郵件資料。</span><span class="sxs-lookup"><span data-stu-id="1b43f-109">If you have a trial subscription for Office 365 Advanced Threat Protection Plan 2 or Office 365 E5, you will only see detections and email data for the past 7 days.</span></span>
  
<span data-ttu-id="1b43f-110">使用 [**檢視**] 功能表變更顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="1b43f-110">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="1b43f-111">工具提示協助您決定使用哪一種檢視。</span><span class="sxs-lookup"><span data-stu-id="1b43f-111">Tooltips help you determine which view to use.</span></span>
  
![威脅總管檢視] 功能表](media/ThreatExplorerViewMenu.png)

<span data-ttu-id="1b43f-113">一旦您已選取檢視，您可以套用篩選器，並設定查詢，以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="1b43f-113">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="1b43f-114">下列各節提供瀏覽器中可用的不同檢視的簡要概觀。</span><span class="sxs-lookup"><span data-stu-id="1b43f-114">The following sections provide a brief overview of the various views available in Explorer.</span></span>  

## <a name="email--malware"></a><span data-ttu-id="1b43f-115">電子郵件 > 惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="1b43f-115">Email > Malware</span></span>

<span data-ttu-id="1b43f-116">若要檢視此報告中，在檔案總管中，選擇 [**檢視** > **電子郵件** > **惡意程式碼**。</span><span class="sxs-lookup"><span data-stu-id="1b43f-116">To view this report, in Explorer, choose **View** > **Email** > **Malware**.</span></span> <span data-ttu-id="1b43f-117">這個檢視顯示已識別為包含惡意程式碼的電子郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1b43f-117">This view shows information about email messages that were identified as containing malware.</span></span>  

![檢視關於電子郵件被識別為惡意程式碼的資料](media/ExplorerEmailMalwareMenu.png) 

<span data-ttu-id="1b43f-119">按一下 [**寄件者**若要開啟的檢視選項]。</span><span class="sxs-lookup"><span data-stu-id="1b43f-119">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="1b43f-120">使用此清單來檢視由寄件者、 收件者、 寄件者網域、 主旨、 偵測技術、 保護狀態，以及更多資料。</span><span class="sxs-lookup"><span data-stu-id="1b43f-120">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span> 

<span data-ttu-id="1b43f-121">例如，若要查看哪些動作是在偵測到的電子郵件訊息上，選擇清單中的 [**保護狀態**]。</span><span class="sxs-lookup"><span data-stu-id="1b43f-121">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="1b43f-122">選取一個選項，然後按一下 [重新整理] 按鈕，該篩選條件套用至您的報表。</span><span class="sxs-lookup"><span data-stu-id="1b43f-122">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![威脅總管] 中的威脅保護狀態選項](media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="1b43f-124">下方圖表，檢視特定郵件的相關詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1b43f-124">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="1b43f-125">當您在清單中選取項目時，會開啟的飛出視窗窗格，其中您可以深入了解您所選取的項目。</span><span class="sxs-lookup"><span data-stu-id="1b43f-125">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![與開啟的彈出式威脅總管](media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="1b43f-127">電子郵件 > Phish</span><span class="sxs-lookup"><span data-stu-id="1b43f-127">Email > Phish</span></span>

<span data-ttu-id="1b43f-128">若要檢視此報告中，在檔案總管中，選擇 [**檢視** > **電子郵件** > **釣魚程式**。</span><span class="sxs-lookup"><span data-stu-id="1b43f-128">To view this report, in Explorer, choose **View** > **Email** > **Phish**.</span></span> <span data-ttu-id="1b43f-129">這個檢視顯示電子郵件識別為網路釣魚嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="1b43f-129">This view shows email messages identified as phishing attempts.</span></span>  

![關於電子郵件被識別為網路釣魚嘗試檢視資料](media/ThreatExplorerEmailPhish.png) 

<span data-ttu-id="1b43f-131">按一下 [**寄件者**若要開啟的檢視選項]。</span><span class="sxs-lookup"><span data-stu-id="1b43f-131">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="1b43f-132">使用此清單來檢視由寄件者、 收件者、 寄件者網域，寄件者 IP 資料的 URL 網域上，按一下 [verdict，等等。</span><span class="sxs-lookup"><span data-stu-id="1b43f-132">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span> 

<span data-ttu-id="1b43f-133">例如，若要查看哪些動作是人員按一下已識別為網路釣魚嘗試的 Url 時，選擇清單中的 [**按一下 verdict** 、 選取一或多個選項，然後按一下 [重新整理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1b43f-133">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![按一下 [Phish 報表 verdict 選項](media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="1b43f-135">下方圖表中，檢視更多詳細資料特定郵件、 URL 點選、 Url 和電子郵件來源。</span><span class="sxs-lookup"><span data-stu-id="1b43f-135">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span> 

![偵測為電子郵件訊息中的釣魚程式的 Url](media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="1b43f-137">當您選取的項目在清單中，例如已偵測到的 URL 會開啟的飛出視窗窗格，其中您可以深入了解您所選取的項目。</span><span class="sxs-lookup"><span data-stu-id="1b43f-137">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![關於偵測到 URL 的詳細資料](media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--user-reported"></a><span data-ttu-id="1b43f-139">電子郵件 > 使用者報告</span><span class="sxs-lookup"><span data-stu-id="1b43f-139">Email > User-reported</span></span>

<span data-ttu-id="1b43f-140">若要檢視此報告中，在檔案總管中，選擇 [**檢視** > **電子郵件** > **使用者報告**。</span><span class="sxs-lookup"><span data-stu-id="1b43f-140">To view this report, in Explorer, choose **View** > **Email** > **User-reported**.</span></span> <span data-ttu-id="1b43f-141">這個檢視顯示電子郵件使用者會回報為垃圾郵件、 非垃圾郵件或網路釣魚電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1b43f-141">This view shows email that users have reported as junk, not junk, or phishing email.</span></span> 

![使用者所回報的電子郵件](media/ThreatExplorerEmailUserReportedViewOptions.png) 

<span data-ttu-id="1b43f-143">按一下 [**寄件者**若要開啟的檢視選項]。</span><span class="sxs-lookup"><span data-stu-id="1b43f-143">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="1b43f-144">使用此清單來檢視由寄件者、 收件者、 報表類型 （使用者的決定電子郵件是垃圾郵件、 非垃圾郵件或釣魚程式，） 和更多的資訊。</span><span class="sxs-lookup"><span data-stu-id="1b43f-144">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span> 

<span data-ttu-id="1b43f-145">例如，若要檢視已回報為網路釣魚嘗試的電子郵件的相關資訊，請按一下 [**寄件者** > **報表類型**，選取**釣魚程式**，然後再按一下 [重新整理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1b43f-145">For example, to view information about email messages that were reported as phishing attempts, click **Sender** > **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![選取 [報告類型的篩選器的釣魚程式](media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="1b43f-147">下方圖表，檢視關於特定電子郵件，如主旨、 寄件者的 IP 位址、 回報郵件為垃圾郵件、 非垃圾郵件，或釣魚程式，等等的使用者詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1b43f-147">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

![回報為網路釣魚嘗試次數的郵件](media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="1b43f-149">若要檢視其他詳細資料] 清單中選取項目。</span><span class="sxs-lookup"><span data-stu-id="1b43f-149">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="1b43f-150">所有電子郵件的電子郵件 ></span><span class="sxs-lookup"><span data-stu-id="1b43f-150">Email > All email</span></span>

<span data-ttu-id="1b43f-151">若要檢視此報告中，在檔案總管中，選擇 [**檢視** > **電子郵件** > **所有郵件**。</span><span class="sxs-lookup"><span data-stu-id="1b43f-151">To view this report, in Explorer, choose **View** > **Email** > **All mail**.</span></span> <span data-ttu-id="1b43f-152">此檢視全面檢視顯示的電子郵件活動，包括電子郵件識別為惡意由於網路釣魚或惡意程式碼，以及所有非惡意的郵件 （一般的電子郵件、 垃圾郵件，以及大量郵件）。</span><span class="sxs-lookup"><span data-stu-id="1b43f-152">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="1b43f-153">如果您收到錯誤，可讀取**太多要顯示的資料**、 新增篩選器，如有必要，縮小您要檢視的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="1b43f-153">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="1b43f-154">若要套用篩選器，選擇 [**寄件者**、 在清單中，選取項目，然後按一下 [重新整理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1b43f-154">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="1b43f-155">在我們的範例中，我們使用**偵測技術**作為篩選器 （有幾個選項可以使用）。</span><span class="sxs-lookup"><span data-stu-id="1b43f-155">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="1b43f-156">檢視依寄件者、 寄件者的網域、 收件者、 主旨、 附件檔名、 惡意程式碼系列、 保護狀態 （威脅保護功能和 Office 365 中的原則所採取的動作）、 （如何惡意程式碼偵測到），偵測技術的資訊和更多。</span><span class="sxs-lookup"><span data-stu-id="1b43f-156">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![關於偵測技術所偵測到電子郵件的檢視資料](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="1b43f-158">下方圖表，檢視更多詳細資料特定的電子郵件，例如主旨行、 收件者、 寄件者、 狀態、 等等。</span><span class="sxs-lookup"><span data-stu-id="1b43f-158">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="1b43f-159">內容 > 惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="1b43f-159">Content > Malware</span></span>

<span data-ttu-id="1b43f-160">若要檢視此報告中，在檔案總管中，選擇 [**檢視** > **內容** > **惡意程式碼**。</span><span class="sxs-lookup"><span data-stu-id="1b43f-160">To view this report, in Explorer, choose **View** > **Content** > **Malware**.</span></span> <span data-ttu-id="1b43f-161">這個檢視顯示[Office 365 進階威脅](atp-for-spo-odb-and-teams.md)防護中 SharePoint Online、 商務用 OneDrive 和 Microsoft Teams 已識別為惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="1b43f-161">This view shows files that were identified as malicious by [Office 365 Advanced Threat Protection in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="1b43f-162">檢視惡意程式碼 （如何惡意程式碼偵測到），家長監護，偵測技術的資訊和工作負載 （OneDrive、 SharePoint 或小組）。</span><span class="sxs-lookup"><span data-stu-id="1b43f-162">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![檢視有關偵測到惡意程式碼](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="1b43f-164">下方圖表中，檢視需有關特定的檔案，例如附件檔名，工作負載，檔案大小，最後修改的檔案，以及更多詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1b43f-164">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="click-to-filter-capabilities"></a><span data-ttu-id="1b43f-165">按一下 [以篩選功能</span><span class="sxs-lookup"><span data-stu-id="1b43f-165">Click-to-filter capabilities</span></span>

<span data-ttu-id="1b43f-166">使用檔案總管中，您可以套用中按一下 [篩選器。</span><span class="sxs-lookup"><span data-stu-id="1b43f-166">With Explorer, you can apply a filter in a click.</span></span> <span data-ttu-id="1b43f-167">按一下圖例中的項目，該項目會成為報表的篩選器。</span><span class="sxs-lookup"><span data-stu-id="1b43f-167">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="1b43f-168">例如，假設我們要尋找在檔案總管中的惡意程式碼檢視：</span><span class="sxs-lookup"><span data-stu-id="1b43f-168">For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![移至威脅管理，\>總管](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="1b43f-170">在此圖表中的結果就像這樣的檢視中，按一下 [ **ATP 爆炸**：</span><span class="sxs-lookup"><span data-stu-id="1b43f-170">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![篩選只 ATP 爆炸結果顯示的瀏覽器](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="1b43f-172">在此檢視中，我們現在要尋找在[Office 365 ATP Safe Attachments](atp-safe-attachments.md)已引爆的檔案的資料。</span><span class="sxs-lookup"><span data-stu-id="1b43f-172">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="1b43f-173">下方圖表中，我們可以看到關於有已偵測到由 ATP 安全附件的附件的特定電子郵件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1b43f-173">Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![關於偵測到的附件的電子郵件的特定詳細資料](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="1b43f-175">選取一或多個項目會啟動 [**動作**] 功能表，它提供了數個選項可供選擇為選取的項目。</span><span class="sxs-lookup"><span data-stu-id="1b43f-175">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![選取項目會啟動 [動作] 功能表](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="1b43f-177">在按一下篩選及瀏覽至特定的詳細資訊的能力可讓您節省大量時間中調查潛在威脅。</span><span class="sxs-lookup"><span data-stu-id="1b43f-177">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="1b43f-178">查詢及篩選</span><span class="sxs-lookup"><span data-stu-id="1b43f-178">Queries and filters</span></span>

<span data-ttu-id="1b43f-179">Explorer 有數個功能強大的篩選器和查詢功能可讓您切入詳細資訊，例如頂端的目標使用者、 上方的惡意程式碼系列、 偵測技術等等。</span><span class="sxs-lookup"><span data-stu-id="1b43f-179">Explorer has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="1b43f-180">每一種報表提供了許多方式可檢視和瀏覽資料。</span><span class="sxs-lookup"><span data-stu-id="1b43f-180">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b43f-181">請勿使用萬用字元，例如星號 （\*） 或問號 （？），在瀏覽器的 [查詢] 列中。</span><span class="sxs-lookup"><span data-stu-id="1b43f-181">Do not use wildcard characters, such as an asterisk (\*) or a question mark (?), in the query bar for Explorer.</span></span> <span data-ttu-id="1b43f-182">當您搜尋電子郵件的主旨欄位時，Explorer 便會執行部分符合及收益結果類似萬用字元搜尋。</span><span class="sxs-lookup"><span data-stu-id="1b43f-182">When you search on the Subject field for email messages, Explorer will perform partial matching and yield results similar to a wildcard search.</span></span>
