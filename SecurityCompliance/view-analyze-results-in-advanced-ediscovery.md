---
title: 在 Office 365 進階電子文件探索中檢視分析結果
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: '了解 Office 365 進階 eDiscovery，包括定義顯示的任務的選項以檢視分析程序的結果的位置。  '
ms.openlocfilehash: 8f1de53e5548c8721f8fbfdb83374edb18379114
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527139"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="1dcb5-103">在 Office 365 進階電子文件探索中檢視分析結果</span><span class="sxs-lookup"><span data-stu-id="1dcb5-103">View Analyze results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="1dcb5-p101">進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="1dcb5-106">進階 eDiscovery 中進行中及結果分析程序可檢視中顯示各種如下所示。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="1dcb5-107">檢視分析任務狀態</span><span class="sxs-lookup"><span data-stu-id="1dcb5-107">View Analyze task status</span></span>

<span data-ttu-id="1dcb5-108">在**準備\>分析\>結果\>任務狀態**、 期間和之後分析程序執行顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![分析工作狀態](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="1dcb5-110">顯示的工作會根據選取的選項而異。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="1dcb5-111">**ND/ET： 安裝程式**： 例如準備執行、 設定執行與案例的參數。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="1dcb5-112">**ND/ET: ND 計算**： 檔案的程序接近重複分析。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="1dcb5-113">**ND/ET: ET 計算**： 執行電子郵件執行緒分析在整個電子郵件設定。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="1dcb5-114">**ND/ET： 樞紐分析表和相似之處**： 執行 [樞紐分析表和檔案相似性處理。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="1dcb5-115">**ND/ET： 中繼資料更新**： 完成新資料庫中的檔案上收集的資料。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="1dcb5-p102">**佈景主題： 佈景主題計算**： 執行佈景主題分析。（顯示唯有在選取了）。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-p102">**Themes: themes calculation**: Runs themes analysis. (Displayed only if selected.)</span></span>
    
- <span data-ttu-id="1dcb5-p103">**工作狀態**： 這一行會顯示在工作完成之後。執行工作時，會顯示執行持續時間。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-p103">**Task status**: This line is displayed after task completion. While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1dcb5-p104">分析的結果接近重複項目和電子郵件執行緒 （ND 和 ED） 適用於處理的文件數。它不包括完全重複的檔案。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-p104">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed. It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="1dcb5-122">檢視接近重複項目和電子郵件執行緒狀態</span><span class="sxs-lookup"><span data-stu-id="1dcb5-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="1dcb5-123">**目標**母體結果在目標母體中顯示文件、 電子郵件、 附件及錯誤的數目。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="1dcb5-124">**文件**結果顯示樞紐分析表、 唯一附近-重複項目及完全重複的檔案的數目。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="1dcb5-p105">**電子郵件**結果會顯示 （含）、 減去唯一 （含） 的副本 （含） 的數目與其餘的電子郵件訊息。不同類型的電子郵件結果是：</span><span class="sxs-lookup"><span data-stu-id="1dcb5-p105">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages. The different types of email results are:</span></span> 
  
- <span data-ttu-id="1dcb5-p106">**Inclusive**: （含） 的電子郵件是在電子郵件執行緒 [終止] 節點並包含該執行緒的所有先前的歷程記錄。因此，檢閱者可以安全地聚焦 （含） 的電子郵件，而不需要讀取執行緒中先前的訊息。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-p106">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread. As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="1dcb5-p107">**減去 Inclusive**： 如果沒有聯 （含） 郵件的父系的一或多個不同的附件 （含） 的電子郵件指定為 （含） 減號。在這個 context、 向上位於電子郵件執行緒或交談的郵件都使用父項的字詞包含在該特定 （含） 的電子郵件。檢閱者可以使用減去指示做訊號但它不需要檢閱的 （含） 的電子郵件父系的內容，它可能會很有用檢閱 （含） 的路徑父系相關聯的附件 （含）。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-p107">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message. In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email. A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="1dcb5-p108">**（含） 的複本**： （含） 的電子郵件指定為 （含） 的複本時之複本的另一則訊息標示為 （含） 或減去 （含）。換句話說，此訊息有相同的主旨和當成另一個 （含） 的訊息本文並因此、 共同位於相同的節點。因為 （含） 複製郵件包含相同的內容，他們可以通常略過檢閱程序。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-p108">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus. In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node. Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="1dcb5-p109">**其他**： 這表示不包含任何唯一的內容與因此不屬於任何舊的三種類別的電子郵件。不需要檢閱這些電子郵件訊息。如果郵件含有不在稍後 （含） 電子郵件的附件，附件可能需要檢閱。這會指定存在減去執行緒內的電子郵件 （含）。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-p109">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories. These email messages don't need to be reviewed. If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed. This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="1dcb5-139">**附件**結果顯示附件，根據這類為唯一的類型和重複項目的數目。</span><span class="sxs-lookup"><span data-stu-id="1dcb5-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![近似重複項目和電子郵件執行緒](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="1dcb5-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1dcb5-141">See also</span></span>

[<span data-ttu-id="1dcb5-142">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="1dcb5-142">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="1dcb5-143">了解文件相似性</span><span class="sxs-lookup"><span data-stu-id="1dcb5-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1dcb5-144">設定分析選項</span><span class="sxs-lookup"><span data-stu-id="1dcb5-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1dcb5-145">設定搜尋時忽略的文字</span><span class="sxs-lookup"><span data-stu-id="1dcb5-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1dcb5-146">設定分析進階設定</span><span class="sxs-lookup"><span data-stu-id="1dcb5-146">Setting Analyze advanced settings</span></span>](view-analyze-results-in-advanced-ediscovery.md)

