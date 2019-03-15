---
title: 在安全性 & 合規性中心中的郵件追蹤
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
description: 系統管理員可以使用郵件追蹤安全性 & 合規性中心中找出的郵件發生了什麼事。
ms.openlocfilehash: ebfc8d5e19bbc45c32ad65451f3f850662f358b4
ms.sourcegitcommit: f86383dcb9c52352661d51b22617f1809445beaa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/14/2019
ms.locfileid: "30573547"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="d5427-103">在安全性 & 合規性中心中的郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="d5427-103">Message trace in the Security & Compliance Center</span></span>

## <a name="overview"></a><span data-ttu-id="d5427-104">概觀</span><span class="sxs-lookup"><span data-stu-id="d5427-104">Overview</span></span>

<span data-ttu-id="d5427-105">遊歷 Exchange Online 組織，安全性 & 合規性中心中的郵件追蹤會遵循電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="d5427-105">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="d5427-106">您可以判斷郵件是否已接收、 拒絕、 延遲或傳遞服務。</span><span class="sxs-lookup"><span data-stu-id="d5427-106">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="d5427-107">它也會顯示是對郵件所採取的行動之前它達到其最終狀態。</span><span class="sxs-lookup"><span data-stu-id="d5427-107">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="d5427-108">在 Exchange 系統管理中心 (EAC) 中所使用的郵件追蹤時，改善安全性 & 合規性中心中的郵件追蹤。</span><span class="sxs-lookup"><span data-stu-id="d5427-108">Message trace in the Security & Compliance Center improves upon message trace that was available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="d5427-109">您可以使用郵件追蹤資訊有效率地回答關於他們的郵件發生了什麼事使用者問題、 疑難排解郵件流程問題，並驗證原則變更。</span><span class="sxs-lookup"><span data-stu-id="d5427-109">You can use the information from message trace to efficiently answer user questions about what happened to their messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="d5427-110">開啟的郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="d5427-110">Open message trace</span></span>

1. <span data-ttu-id="d5427-111">使用您的 公司或學校帳戶[登入 Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="d5427-111">[Sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="d5427-112">選取 [應用程式啟動器圖示![Office 365 應用程式啟動器圖示](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png)中左上角，然後選擇 [**系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="d5427-112">Select the app launcher icon ![Office 365 app launcher icon](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="d5427-113">左下導覽中，依序展開 [**系統管理中心**，選取 [**安全性 & 合規性**。</span><span class="sxs-lookup"><span data-stu-id="d5427-113">In the lower-left navigation, expand **Admin centers** and select **Security & Compliance**.</span></span>

4. <span data-ttu-id="d5427-114">在開啟**安全性 & 合規性**] 頁面中，依序展開 [**郵件流程**]，然後選取 [**郵件追蹤**。</span><span class="sxs-lookup"><span data-stu-id="d5427-114">In the **Security & Compliance** page that opens, expand **Mail flow**, and select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="d5427-115">郵件追蹤] 頁面</span><span class="sxs-lookup"><span data-stu-id="d5427-115">Message trace page</span></span>

<span data-ttu-id="d5427-116">您可以從這裡**開始追蹤**] 按鈕上的 [開始新的預設追蹤。</span><span class="sxs-lookup"><span data-stu-id="d5427-116">From here you can start a new default trace by clicking on the **Start a trace** button.</span></span> <span data-ttu-id="d5427-117">這會搜尋所有郵件的所有寄件者和收件者在過去兩天。</span><span class="sxs-lookup"><span data-stu-id="d5427-117">This will search for all messages for all senders and recipients for the last two days.</span></span> <span data-ttu-id="d5427-118">或您可以使用下列其中一個可用的查詢分類預存查詢，並執行其作為-是或作為起點為您自己的查詢：</span><span class="sxs-lookup"><span data-stu-id="d5427-118">Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="d5427-119">**預設查詢**： 由 Office 365 提供的內建查詢。</span><span class="sxs-lookup"><span data-stu-id="d5427-119">**Default queries**: Built-in queries provided by Office 365.</span></span>

- <span data-ttu-id="d5427-120">**自訂查詢**： 查詢儲存供日後使用您組織中的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="d5427-120">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="d5427-121">**Autosaved 查詢**： 最後一個十最近執行查詢。</span><span class="sxs-lookup"><span data-stu-id="d5427-121">**Autosaved queries**: The last ten most recently run queries.</span></span> <span data-ttu-id="d5427-122">這份清單可讓您更簡單，挑選您離開的。</span><span class="sxs-lookup"><span data-stu-id="d5427-122">This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="d5427-123">在此頁面上也**Downloadable 報告**] 區段中的已提交要求，以及他們自己的報告時可供下載。</span><span class="sxs-lookup"><span data-stu-id="d5427-123">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="d5427-124">新的郵件追蹤選項</span><span class="sxs-lookup"><span data-stu-id="d5427-124">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="d5427-125">依寄件者和收件者篩選</span><span class="sxs-lookup"><span data-stu-id="d5427-125">Filter by senders and recipients</span></span>

<span data-ttu-id="d5427-126">預設值為**所有寄件者**及**所有收件者**，但您可以使用下列欄位來篩選結果：</span><span class="sxs-lookup"><span data-stu-id="d5427-126">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="d5427-127">**這些人**： 按一下 [從您的組織中選取一或多個寄件者此欄位中。</span><span class="sxs-lookup"><span data-stu-id="d5427-127">**By these people**: Click in this field to select one or more senders from your organization.</span></span> <span data-ttu-id="d5427-128">您也可以開始輸入的名稱，並會依您已輸入的內容，遠像搜尋] 頁面上的行為方式篩選清單中的項目。</span><span class="sxs-lookup"><span data-stu-id="d5427-128">You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="d5427-129">**這些人**： 按一下 [在組織中選取一或多個收件者此欄位中。</span><span class="sxs-lookup"><span data-stu-id="d5427-129">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="d5427-130">您也可以輸入外部寄件者和收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d5427-130">You can also type the email addresses of external senders and recipients.</span></span> <span data-ttu-id="d5427-131">支援萬用字元 (`*@contoso.com`或`scot?@contoso.com`)，但您無法在相同的欄位中使用多個的萬用字元項目，在同一時間。</span><span class="sxs-lookup"><span data-stu-id="d5427-131">Wildcards are supported (`*@contoso.com` or `scot?@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span><br/><span data-ttu-id="d5427-132">您可以貼上以分號分隔的多個寄件者或收件者清單 (`;`)。</span><span class="sxs-lookup"><span data-stu-id="d5427-132">You can paste multiple senders or recipients list separated with semicolon (`;`).</span></span> <span data-ttu-id="d5427-133">空格 (`\s`)、 歸位換行 (`\r`) 或下一行 (`\n`) 允許的符號。</span><span class="sxs-lookup"><span data-stu-id="d5427-133">Spaces (`\s`), carriage return (`\r`) or next lines (`\n`) symbols are allowed.</span></span>

### <a name="time-range"></a><span data-ttu-id="d5427-134">時間範圍</span><span class="sxs-lookup"><span data-stu-id="d5427-134">Time range</span></span>

<span data-ttu-id="d5427-135">預設值為**2 天**，但您可以指定多達 90 天的日期/時間範圍。</span><span class="sxs-lookup"><span data-stu-id="d5427-135">The default value is **2 days**, but you can specify date/time ranges of up to 90 days.</span></span> <span data-ttu-id="d5427-136">當您使用日期/時間範圍時，請考量下列問題：</span><span class="sxs-lookup"><span data-stu-id="d5427-136">When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="d5427-137">根據預設，您會使用時間列的**滑桿**檢視中選取的時間範圍。</span><span class="sxs-lookup"><span data-stu-id="d5427-137">By default, you select the time range in **Slider** view using a time line.</span></span> <span data-ttu-id="d5427-138">您只能選取日期或時間所顯示的設定。</span><span class="sxs-lookup"><span data-stu-id="d5427-138">You can only select the day or time settings that are displayed.</span></span> <span data-ttu-id="d5427-139">嘗試選取中間值將會貼齊開始/結束泡泡至最接近顯示設定。</span><span class="sxs-lookup"><span data-stu-id="d5427-139">Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

   ![在 [安全性 & 合規性中心中新的郵件追蹤滑桿時間範圍](media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

   <span data-ttu-id="d5427-141">但是，您也可以切換到**自訂**檢視，其中您可以指定的**開始日期**和**結束日期**值 （包括時間），而您也可以選取日期/時間範圍內的**時區**。</span><span class="sxs-lookup"><span data-stu-id="d5427-141">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range.</span></span> <span data-ttu-id="d5427-142">請注意，**時間的時區**設定適用於您的查詢輸入和您的查詢結果。</span><span class="sxs-lookup"><span data-stu-id="d5427-142">Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

   ![安全性 & 合規性中心中新的郵件追蹤中的自訂時間範圍](media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

   <span data-ttu-id="d5427-144">代表 10 天或更少，結果可立即為**摘要**報告。</span><span class="sxs-lookup"><span data-stu-id="d5427-144">For 10 days or less, the results are available instantly as a **Summary** report.</span></span> <span data-ttu-id="d5427-145">如果您指定即使稍微高於 10 天的時間範圍，因為它們是只可作為可下載的 CSV 檔案 （**增強摘要**或**延伸**報告），將會延遲結果。</span><span class="sxs-lookup"><span data-stu-id="d5427-145">If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

   <span data-ttu-id="d5427-146">如需不同的報告類型的詳細資訊，請參閱本主題中的 [[選擇報表類型](#choose-report-type)] 區段。</span><span class="sxs-lookup"><span data-stu-id="d5427-146">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this topic.</span></span>

   <span data-ttu-id="d5427-147">**附註**： 增強型的摘要和延伸報告準備使用已封存的郵件追蹤資料，並可能會耗費數小時的時間之前您的報表會提供下載。</span><span class="sxs-lookup"><span data-stu-id="d5427-147">**Note**: Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download.</span></span> <span data-ttu-id="d5427-148">根據多少其他系統管理員也已提交報告要求周圍的同一時間，您可能也會注意到延遲之前處理啟動時您已排入佇列的要求。</span><span class="sxs-lookup"><span data-stu-id="d5427-148">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="d5427-149">儲存查詢**滑桿**檢視中儲存的相對時間範圍 （例如，從今天 3 天）。</span><span class="sxs-lookup"><span data-stu-id="d5427-149">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today).</span></span> <span data-ttu-id="d5427-150">在**自訂**檢視中儲存的查詢會儲存絕對的日期/時間範圍 (例如，2018年-05-06 13:00 到 2018年-05-08 18:00)。</span><span class="sxs-lookup"><span data-stu-id="d5427-150">Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="d5427-151">更多搜尋選項</span><span class="sxs-lookup"><span data-stu-id="d5427-151">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="d5427-152">傳遞狀態</span><span class="sxs-lookup"><span data-stu-id="d5427-152">Delivery status</span></span>

<span data-ttu-id="d5427-153">您可以保留預設值 [**全部**選取]，或者您可以選取下列其中一個下列值來篩選結果：</span><span class="sxs-lookup"><span data-stu-id="d5427-153">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="d5427-154">**已傳遞**： 郵件已成功傳遞至預定目的地。</span><span class="sxs-lookup"><span data-stu-id="d5427-154">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="d5427-155">**擱置**： 正在將郵件傳遞嘗試或重新嘗試。</span><span class="sxs-lookup"><span data-stu-id="d5427-155">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="d5427-156">**Expanded**： 已展開通訊群組收件者，再傳遞給該群組中的個別成員。</span><span class="sxs-lookup"><span data-stu-id="d5427-156">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="d5427-157">**失敗**： 無法傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-157">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="d5427-158">**隔離**： 郵件遭隔離 （做為垃圾郵件、 大量郵件或網路釣魚）。</span><span class="sxs-lookup"><span data-stu-id="d5427-158">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing).</span></span> <span data-ttu-id="d5427-159">如需詳細資訊，請參閱 < <b0>Office 365 中的隔離電子郵件</b0>。</span><span class="sxs-lookup"><span data-stu-id="d5427-159">For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).</span></span>

- <span data-ttu-id="d5427-160">**篩選為垃圾郵件**： 郵件已識別垃圾郵件，並已拒絕或封鎖 （未被隔離）。</span><span class="sxs-lookup"><span data-stu-id="d5427-160">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="d5427-161">**取得狀態：** Office 365 最近接收到郵件，但仍無其他狀態資料。</span><span class="sxs-lookup"><span data-stu-id="d5427-161">**Getting status:** The message was recently received by Office 365, but no other status data is yet available.</span></span> <span data-ttu-id="d5427-162">存回回幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="d5427-162">Check back in a few minutes.</span></span>

<span data-ttu-id="d5427-163">**附註**：**暫止，** **隔離**，並**為垃圾郵件篩選**的值只適用於搜尋小於 10 天。</span><span class="sxs-lookup"><span data-stu-id="d5427-163">**Note**: The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days.</span></span> <span data-ttu-id="d5427-164">此外，有可能介於 5 到 10 分鐘的延遲的實際和報告的傳遞狀態。</span><span class="sxs-lookup"><span data-stu-id="d5427-164">Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="d5427-165">訊息識別碼</span><span class="sxs-lookup"><span data-stu-id="d5427-165">Message ID</span></span>

<span data-ttu-id="d5427-166">這是網際網路郵件識別碼 (也稱為 「 用戶端 ID 」) 中找到**訊息識別碼：** 標頭欄位中的郵件標頭。</span><span class="sxs-lookup"><span data-stu-id="d5427-166">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header.</span></span> <span data-ttu-id="d5427-167">使用者可以提供此值設為調查特定郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-167">Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="d5427-168">此值是郵件存留時間的常數。</span><span class="sxs-lookup"><span data-stu-id="d5427-168">This value is constant for the lifetime of the message.</span></span> <span data-ttu-id="d5427-169">在 Office 365 或 Exchange 中建立的郵件，此值會採用格式`<GUID@ServerFQDN>`，包括角括弧 (\< \>)。</span><span class="sxs-lookup"><span data-stu-id="d5427-169">For messages created in Office 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>).</span></span> <span data-ttu-id="d5427-170">例如 `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="d5427-170">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span> <span data-ttu-id="d5427-171">其他郵件系統可能使用不同的語法或值。</span><span class="sxs-lookup"><span data-stu-id="d5427-171">Other messaging systems might use different syntax or values.</span></span> <span data-ttu-id="d5427-172">這個值應該是唯一的但並非所有的電子郵件系統嚴格遵守這項要求。</span><span class="sxs-lookup"><span data-stu-id="d5427-172">This value is supposed to be unique, but not all email systems strictly follow this requirement.</span></span> <span data-ttu-id="d5427-173">如果**訊息識別碼：** 標頭欄位不存在或空白從外部來源的內送郵件，會指派任意值。</span><span class="sxs-lookup"><span data-stu-id="d5427-173">If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="d5427-174">當您使用**訊息識別碼**來篩選結果時，請務必包括完整的字串，包括任何角括弧。</span><span class="sxs-lookup"><span data-stu-id="d5427-174">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="d5427-175">方向</span><span class="sxs-lookup"><span data-stu-id="d5427-175">Direction</span></span>

<span data-ttu-id="d5427-176">您可以保留預設值 [**全部**選取]，或者，您可以選取**輸入**（傳送給組織中的收件者的郵件） 或**輸出**（從您組織中的使用者傳送的訊息） 來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="d5427-176">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="d5427-177">原始用戶端 IP 位址</span><span class="sxs-lookup"><span data-stu-id="d5427-177">Original client IP address</span></span>

<span data-ttu-id="d5427-178">您可以 filer 結果調查破解會傳送大量的垃圾郵件或惡意程式碼的電腦用戶端 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d5427-178">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware.</span></span> <span data-ttu-id="d5427-179">雖然郵件似乎來自多個寄件者，則可能在同一部電腦產生的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-179">Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

<span data-ttu-id="d5427-180">**附註**： 用戶端 IP 位址資訊只有代表 10 天，並只能供**增強摘要**或**延伸**的報告 （可下載 CSV 檔案） 中。</span><span class="sxs-lookup"><span data-stu-id="d5427-180">**Note**: The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="d5427-181">選擇 [報告類型</span><span class="sxs-lookup"><span data-stu-id="d5427-181">Choose report type</span></span>

<span data-ttu-id="d5427-182">可用的報告類型如下：</span><span class="sxs-lookup"><span data-stu-id="d5427-182">The available report types are:</span></span>

- <span data-ttu-id="d5427-183">**摘要**： 提供如果的時間範圍是小於 10 天，且需要任何其他的篩選選項。</span><span class="sxs-lookup"><span data-stu-id="d5427-183">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options.</span></span> <span data-ttu-id="d5427-184">幾乎立即您按一下 [**搜尋**] 之後，是可用的結果。</span><span class="sxs-lookup"><span data-stu-id="d5427-184">The results are available almost immediately after you click **Search**.</span></span>

- <span data-ttu-id="d5427-185">**增強摘要**或**延伸**： 這些報告只可作為可下載的 CSV 檔案，且需要一或多個下列的篩選選項，不論時間範圍內：**這些人**，**給這些人**，或**郵件 ID**。</span><span class="sxs-lookup"><span data-stu-id="d5427-185">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**.</span></span> <span data-ttu-id="d5427-186">您可以使用萬用字元的寄件者或收件者 (例如， \*@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="d5427-186">You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span>

<span data-ttu-id="d5427-187">**附註**：</span><span class="sxs-lookup"><span data-stu-id="d5427-187">**Notes**:</span></span>

- <span data-ttu-id="d5427-188">增強型的摘要和延伸報告準備使用已封存的郵件追蹤資料，並可能會耗費數小時之前您的報表可供下載的時間。</span><span class="sxs-lookup"><span data-stu-id="d5427-188">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download.</span></span> <span data-ttu-id="d5427-189">您已排入佇列的要求開始處理之前，視多少其他系統管理員也已提交報告要求周圍的同一時間，可能需要注意的延遲。</span><span class="sxs-lookup"><span data-stu-id="d5427-189">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>

- <span data-ttu-id="d5427-190">雖然您可以選取任何增強摘要或擴充報告日期/時間範圍、 常封存資料的前四個小時不會尚未為可供這兩種類型的報告。</span><span class="sxs-lookup"><span data-stu-id="d5427-190">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="d5427-191">當您按一下 [**下一步**] 時，您正在出現摘要] 頁面，列出您選取的篩選選項報表，以及當郵件追蹤完成時 （也可供編輯，會收到通知的電子郵件地址的唯一 （編輯） 標題和必須是下列其中一個貴組織的公認的網域）。</span><span class="sxs-lookup"><span data-stu-id="d5427-191">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains).</span></span> <span data-ttu-id="d5427-192">按一下 [**準備報表**送出的郵件追蹤。</span><span class="sxs-lookup"><span data-stu-id="d5427-192">Click **Prepare report** to submit the message trace.</span></span> <span data-ttu-id="d5427-193">在 [主要**郵件追蹤**] 頁面上，您可以查看 [ **Downloadable 報告**] 區段中的報表的狀態。</span><span class="sxs-lookup"><span data-stu-id="d5427-193">On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="d5427-194">如需在不同的報表類型中傳回的資訊的詳細資訊，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="d5427-194">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="d5427-195">郵件追蹤結果</span><span class="sxs-lookup"><span data-stu-id="d5427-195">Message trace results</span></span>

<span data-ttu-id="d5427-196">不同的報表類型，傳回資訊的不同層的級。</span><span class="sxs-lookup"><span data-stu-id="d5427-196">The different report types return different levels of information.</span></span> <span data-ttu-id="d5427-197">下列各節說明可用於不同的報告的資訊。</span><span class="sxs-lookup"><span data-stu-id="d5427-197">The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="d5427-198">摘要報告輸出</span><span class="sxs-lookup"><span data-stu-id="d5427-198">Summary report output</span></span>

<span data-ttu-id="d5427-199">之後執行郵件追蹤，結果會列出，排序依遞減日期/時間 （最新的第一個）。</span><span class="sxs-lookup"><span data-stu-id="d5427-199">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![在安全性 & 合規性中心中的郵件追蹤的摘要報告結果](media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="d5427-201">摘要報告包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d5427-201">The summary report contains the following information:</span></span>

- <span data-ttu-id="d5427-202">**日期**： 速率藉由使用設定的 UTC 時區的服務收到郵件的時間與日期。</span><span class="sxs-lookup"><span data-stu-id="d5427-202">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="d5427-203">**寄件者**： 寄件者的電子郵件地址 (*別名*@*網域*)。</span><span class="sxs-lookup"><span data-stu-id="d5427-203">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="d5427-204">**收件者**： 收件者或收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d5427-204">**Recipient**: The email address of the recipient or recipients.</span></span> <span data-ttu-id="d5427-205">傳送給多位收件者的郵件，沒有個別寄件者的一列。</span><span class="sxs-lookup"><span data-stu-id="d5427-205">For a message sent to multiple recipients, there's one line per recipient.</span></span> <span data-ttu-id="d5427-206">如果收件者是通訊群組、 動態通訊群組或擁有郵件功能的安全性群組，群組將會在第一個收件者，且然後每個群組成員的個別行上。</span><span class="sxs-lookup"><span data-stu-id="d5427-206">If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="d5427-207">**主旨**： 郵件的前 256 個字元**主旨：** ] 欄位。</span><span class="sxs-lookup"><span data-stu-id="d5427-207">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="d5427-208">**狀態**： 這些值會[傳遞狀態](#delivery-status)] 區段中所述。</span><span class="sxs-lookup"><span data-stu-id="d5427-208">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="d5427-209">根據預設前, 250 結果會載入並隨時可用。</span><span class="sxs-lookup"><span data-stu-id="d5427-209">By default, the first 250 results are loaded and readily available.</span></span> <span data-ttu-id="d5427-210">當您向下捲動時，就會稍微暫停，為下一個批次的結果會載入。</span><span class="sxs-lookup"><span data-stu-id="d5427-210">When you scroll down, there's a slight pause as the next batch of results are loaded.</span></span> <span data-ttu-id="d5427-211">而不是向下捲動，您可以按一下 [**載入所有**載入的所有最多 10000 個結果。</span><span class="sxs-lookup"><span data-stu-id="d5427-211">Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="d5427-212">您可以按一下欄標題以遞增或遞減順序該資料行中的值來排序結果。</span><span class="sxs-lookup"><span data-stu-id="d5427-212">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="d5427-213">您可以按一下 [**篩選結果**，以一或多個資料行來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="d5427-213">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="d5427-214">您已選取一或多個資料列，藉由按一下 [**匯出結果**，然後選擇 [**匯出所有的結果**、**匯出載入結果**，或**選取 [匯出**之後，您可以匯出結果。</span><span class="sxs-lookup"><span data-stu-id="d5427-214">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="d5427-215">此郵件中尋找相關的記錄</span><span class="sxs-lookup"><span data-stu-id="d5427-215">Find related records for this message</span></span>

<span data-ttu-id="d5427-216">相關的訊息記錄會記錄共用相同的郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="d5427-216">Related message records are records that shared the same Message ID.</span></span> <span data-ttu-id="d5427-217">請記住，即使兩個人員之間傳送的單一郵件可能會產生多筆記錄。</span><span class="sxs-lookup"><span data-stu-id="d5427-217">Remember, even a single message sent between two people can generate multiple records.</span></span> <span data-ttu-id="d5427-218">當郵件會受到通訊群組擴充、 轉寄、 郵件流程規則 （也稱為傳輸規則）、 等時，就會增加的記錄數目。</span><span class="sxs-lookup"><span data-stu-id="d5427-218">The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="d5427-219">您選取的資料列] 核取方塊之後，您可以找到相關的記錄訊息出現，請**尋找相關**的按鈕，即可或選取 [**更多選項**![詳細](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **找出此郵件相關的記錄**)。</span><span class="sxs-lookup"><span data-stu-id="d5427-219">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="d5427-220">如需郵件識別碼的詳細資訊，請參閱 < 稍早在本主題中的 [訊息識別碼] 區段。</span><span class="sxs-lookup"><span data-stu-id="d5427-220">For more information about the Message ID, see the Message ID section earlier in this topic.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="d5427-221">郵件追蹤詳細資料</span><span class="sxs-lookup"><span data-stu-id="d5427-221">Message trace details</span></span>

<span data-ttu-id="d5427-222">在摘要報告輸出中，您可以使用下列方法之一來檢視郵件的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="d5427-222">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="d5427-223">選取的列 (按一下 [中] 核取方塊以外的資料列的任何位置)。</span><span class="sxs-lookup"><span data-stu-id="d5427-223">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="d5427-224">選取列] 核取方塊，然後按一下 [**更多選項**![詳細](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **檢視訊息詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="d5427-224">Select the row's check box and click **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![之後，按兩下安全性 & 合規性中心中的摘要報告郵件追蹤結果集中的列的詳細資料](media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="d5427-226">郵件追蹤詳細資料包含不存在於摘要報告中的下列其他資訊：</span><span class="sxs-lookup"><span data-stu-id="d5427-226">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="d5427-227">**郵件事件**： 此區段包含分類，幫助分類服務對郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="d5427-227">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages.</span></span> <span data-ttu-id="d5427-228">您可能會遇到更有趣事件如下：</span><span class="sxs-lookup"><span data-stu-id="d5427-228">Some of the more interesting events that you might encounter are:</span></span>

   - <span data-ttu-id="d5427-229">**接收**： 服務已接收到郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-229">**Receive**: The message was received by the service.</span></span>

   - <span data-ttu-id="d5427-230">**傳送**： 郵件已由服務所傳送。</span><span class="sxs-lookup"><span data-stu-id="d5427-230">**Send**: The message was sent by the service.</span></span>

   - <span data-ttu-id="d5427-231">**失敗**： 無法傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-231">**Fail**: The message failed to be delivered.</span></span>

   - <span data-ttu-id="d5427-232">**傳遞**： 郵件已傳遞至信箱。</span><span class="sxs-lookup"><span data-stu-id="d5427-232">**Deliver**: The message was delivered to a mailbox.</span></span>

   - <span data-ttu-id="d5427-233">**展開**： 郵件已傳送至已展開通訊群組。</span><span class="sxs-lookup"><span data-stu-id="d5427-233">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

   - <span data-ttu-id="d5427-234">**傳送**： 收件者已移至緣故郵件由於內容轉換、 郵件收件者限制或代理程式。</span><span class="sxs-lookup"><span data-stu-id="d5427-234">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

   - <span data-ttu-id="d5427-235">**Defer**： 在郵件傳遞已延遲，且可能稍後再試。</span><span class="sxs-lookup"><span data-stu-id="d5427-235">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

   - <span data-ttu-id="d5427-236">**已解決**： 將郵件重新導向至新的收件者地址，以根據 Active Directory 查閱。</span><span class="sxs-lookup"><span data-stu-id="d5427-236">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up.</span></span> <span data-ttu-id="d5427-237">發生此情況時，原始收件者地址會伴隨著郵件的最終傳遞狀態，出現在郵件追蹤裡的另一列。</span><span class="sxs-lookup"><span data-stu-id="d5427-237">When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

   <span data-ttu-id="d5427-238">請注意，即使已順利傳遞未引發事件的郵件在郵件追蹤會產生多個**事件**項目。</span><span class="sxs-lookup"><span data-stu-id="d5427-238">Note that even an uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>

- <span data-ttu-id="d5427-239">**更多資訊**： 此區段包含下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="d5427-239">**More information**: This section contains the following details:</span></span>

   - <span data-ttu-id="d5427-240">**訊息識別碼**： 這個值稍早在本主題中的 [[訊息識別碼](#message-id)] 區段中所述。</span><span class="sxs-lookup"><span data-stu-id="d5427-240">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this topic.</span></span> <span data-ttu-id="d5427-241">例如 `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="d5427-241">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

   - <span data-ttu-id="d5427-242">**郵件大小**</span><span class="sxs-lookup"><span data-stu-id="d5427-242">**Message size**</span></span>

   - <span data-ttu-id="d5427-243">**從 IP**： 傳送訊息之電腦的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d5427-243">**From IP**: The IP address of the computer that sent the message.</span></span> <span data-ttu-id="d5427-244">對於從 Exchange Online 傳送的輸出郵件，此值為空白。</span><span class="sxs-lookup"><span data-stu-id="d5427-244">For outbound messages sent from Exchange Online, this value is blank.</span></span>

   - <span data-ttu-id="d5427-245">**若要 IP**: IP 位址或位址服務嘗試傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-245">**To IP**: The IP address or addresses where the service attempted to deliver the message.</span></span> <span data-ttu-id="d5427-246">如果郵件有多個收件者，則會顯示這些。</span><span class="sxs-lookup"><span data-stu-id="d5427-246">If the message has multiple recipients, these are displayed.</span></span> <span data-ttu-id="d5427-247">對於傳送至 Exchange Online 的輸入郵件，此值為空白。</span><span class="sxs-lookup"><span data-stu-id="d5427-247">For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="d5427-248">增強型的摘要報告</span><span class="sxs-lookup"><span data-stu-id="d5427-248">Enhanced summary reports</span></span>

<span data-ttu-id="d5427-249">在開頭郵件追蹤**Downloadable 報告**] 區段中有可用 （完成） 的增強摘要報告。</span><span class="sxs-lookup"><span data-stu-id="d5427-249">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace.</span></span> <span data-ttu-id="d5427-250">有可用報告中的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d5427-250">The following information is available in the report:</span></span>

- <span data-ttu-id="d5427-251">**origin_timestamp**<sup>\*</sup>： 的日期和時間時一開始接收到郵件的服務，使用設定的 UTC 時區。</span><span class="sxs-lookup"><span data-stu-id="d5427-251">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="d5427-252">**sender_address 採用**： 寄件者的電子郵件地址 (*別名*@*網域*)。</span><span class="sxs-lookup"><span data-stu-id="d5427-252">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="d5427-253">**Recipient_status**： 將郵件傳遞至收件者的狀態。</span><span class="sxs-lookup"><span data-stu-id="d5427-253">**Recipient_status**: The status of the delivery of the message to the recipient.</span></span> <span data-ttu-id="d5427-254">如果郵件已傳送給多位收件者，它會顯示所有收件者和對應的狀態為每個格式： \<*電子郵件地址*\>##\<*狀態*\>。</span><span class="sxs-lookup"><span data-stu-id="d5427-254">If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>.</span></span> <span data-ttu-id="d5427-255">例如：</span><span class="sxs-lookup"><span data-stu-id="d5427-255">For example:</span></span>

   - <span data-ttu-id="d5427-256">**##Receive，傳送**表示服務已接收到郵件，並已傳送至預定目的地。</span><span class="sxs-lookup"><span data-stu-id="d5427-256">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

   - <span data-ttu-id="d5427-257">**##Receive，失敗**表示服務，但傳遞至預定目的地失敗已收到郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-257">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

   - <span data-ttu-id="d5427-258">**##Receive，傳遞**表示服務已接收到郵件，並已傳遞至收件者的信箱。</span><span class="sxs-lookup"><span data-stu-id="d5427-258">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="d5427-259">**message_subject**： 郵件的**主旨**] 欄位的前 256 個字元。</span><span class="sxs-lookup"><span data-stu-id="d5427-259">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="d5427-260">**total_bytes**： 以位元組為單位，包括附件的郵件大小。</span><span class="sxs-lookup"><span data-stu-id="d5427-260">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="d5427-261">**message_id**： 這個值稍早在本主題中的 [[訊息識別碼](#message-id)] 區段中所述。</span><span class="sxs-lookup"><span data-stu-id="d5427-261">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this topic.</span></span> <span data-ttu-id="d5427-262">例如 `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="d5427-262">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="d5427-263">**network_message_id**： 保存跨所有複本的訊息，可能因為複本發送或通訊群組擴充建立唯一的郵件識別碼值。</span><span class="sxs-lookup"><span data-stu-id="d5427-263">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion.</span></span> <span data-ttu-id="d5427-264">例如，此值是`1341ac7b13fb42ab4d4408cf7f55890f`。</span><span class="sxs-lookup"><span data-stu-id="d5427-264">An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="d5427-265">**original_client_ip**： 寄件者用戶端的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d5427-265">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="d5427-266">**directionality**： 指出是否將郵件已傳送輸入 （1） 至您的組織，或是否送出 （2） 從您的組織。</span><span class="sxs-lookup"><span data-stu-id="d5427-266">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="d5427-267">**connector_id**： 來源或目的地連接器的名稱。</span><span class="sxs-lookup"><span data-stu-id="d5427-267">**connector_id**: The name of the source or destination connector.</span></span> <span data-ttu-id="d5427-268">如需有關 Exchange Online 中的連接器的詳細資訊，請參閱 <<c0>使用 Office 365 中的連接器設定郵件流程。</span><span class="sxs-lookup"><span data-stu-id="d5427-268">For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="d5427-269">**delivery_priority**<sup>\*</sup>： 是否將郵件已傳送**高**]、 [**低**] 或 [**一般**優先順序。</span><span class="sxs-lookup"><span data-stu-id="d5427-269">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="d5427-270"><sup>\*</sup>這些屬性僅可增強摘要報告中。</span><span class="sxs-lookup"><span data-stu-id="d5427-270"><sup>\*</sup>These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="d5427-271">延伸的報告</span><span class="sxs-lookup"><span data-stu-id="d5427-271">Extended reports</span></span>

<span data-ttu-id="d5427-272">可用 （完成） 的延伸報告可在**Downloadable 報告**] 區段中的開頭的郵件追蹤。</span><span class="sxs-lookup"><span data-stu-id="d5427-272">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace.</span></span> <span data-ttu-id="d5427-273">幾乎所有來自增強摘要報告是資訊的在 （除了**origin_timestamp**和**delivery_priority**） 延伸報表。</span><span class="sxs-lookup"><span data-stu-id="d5427-273">Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**).</span></span> <span data-ttu-id="d5427-274">下列的額外資訊只有在延伸報告：</span><span class="sxs-lookup"><span data-stu-id="d5427-274">The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="d5427-275">**client_ip**： 電子郵件伺服器或郵件用戶端提交之郵件的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d5427-275">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="d5427-276">**client_hostname**： 主機名稱或電子郵件伺服器或郵件用戶端提交之郵件的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d5427-276">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="d5427-277">**server_ip**： 來源或目的地伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d5427-277">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="d5427-278">**server_hostname**： 主機名稱或目的地伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d5427-278">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="d5427-279">**source_context**: **source**欄位相關聯的額外資訊。</span><span class="sxs-lookup"><span data-stu-id="d5427-279">**source_context**: Extra information associated with the **source** field.</span></span> <span data-ttu-id="d5427-280">例如：</span><span class="sxs-lookup"><span data-stu-id="d5427-280">For example:</span></span>

   - `Protocol Filter Agent`

   - `3489061114359050000`

- <span data-ttu-id="d5427-281">**來源**： 負責事件的 Exchange Online 元件。</span><span class="sxs-lookup"><span data-stu-id="d5427-281">**source**: The Exchange Online component that's responsible for the event.</span></span> <span data-ttu-id="d5427-282">例如：</span><span class="sxs-lookup"><span data-stu-id="d5427-282">For example:</span></span>

   - `AGENT`

   - `MAILBOXRULE`

   - `SMTP`

- <span data-ttu-id="d5427-283">**event_id**： 這些對應至說明在[尋找此郵件的相關的記錄](#find-related-records-for-this-message)] 區段中的**郵件事件**值。</span><span class="sxs-lookup"><span data-stu-id="d5427-283">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="d5427-284">**internal_message_id**： 指派 Exchange Online 伺服器目前正在處理郵件的郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="d5427-284">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="d5427-285">**recipient_address**： 郵件的收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d5427-285">**recipient_address**: The email addresses of the message's recipients.</span></span> <span data-ttu-id="d5427-286">多個電子郵件地址會以分號字元 (;) 隔開。</span><span class="sxs-lookup"><span data-stu-id="d5427-286">Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="d5427-287">**recipient_count**： 收件者的郵件總數。</span><span class="sxs-lookup"><span data-stu-id="d5427-287">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="d5427-288">**related_recipient_address**： 搭配`EXPAND`、 `REDIRECT`，和`RESOLVE`事件，以顯示其他收件者電子郵件與郵件相關聯的地址。</span><span class="sxs-lookup"><span data-stu-id="d5427-288">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="d5427-289">**參考**： 此欄位包含特定事件類型的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="d5427-289">**reference**: This field contains additional information for specific types of events.</span></span> <span data-ttu-id="d5427-290">例如：</span><span class="sxs-lookup"><span data-stu-id="d5427-290">For example:</span></span>

   - <span data-ttu-id="d5427-291">**DSN**： 包含報告連結，也就是**message_id**值相關聯的傳遞狀態通知 （也稱為 DSN、 未傳遞回報、 NDR 或退回的郵件），如果 message-id 此事件會產生 DSN。</span><span class="sxs-lookup"><span data-stu-id="d5427-291">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event.</span></span> <span data-ttu-id="d5427-292">如果這是 DSN 郵件，此欄位會包含原始郵件 DSN 所產生的**message_id**值。</span><span class="sxs-lookup"><span data-stu-id="d5427-292">If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

   - <span data-ttu-id="d5427-293">**展開**： 包含相關郵件的**related_recipient_address**值。</span><span class="sxs-lookup"><span data-stu-id="d5427-293">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

   - <span data-ttu-id="d5427-294">**接收**： 可能會包含相關郵件的**message_id**值，如果郵件由其他程序 （例如，收件匣規則） 所產生。</span><span class="sxs-lookup"><span data-stu-id="d5427-294">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

   - <span data-ttu-id="d5427-295">**傳送**： 包含任何 DSN 郵件的**internal_message_id**值。</span><span class="sxs-lookup"><span data-stu-id="d5427-295">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

   - <span data-ttu-id="d5427-296">**傳送**： 包含**internal_message_id**值之郵件的 internet-message-id （例如，藉由內容轉換、 郵件收件者限制或代理程式）。</span><span class="sxs-lookup"><span data-stu-id="d5427-296">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

   - <span data-ttu-id="d5427-297">**MAILBOXRULE**： 包含當初導致收件匣規則產生輸出郵件的輸入郵件的**internal_message_id**值。</span><span class="sxs-lookup"><span data-stu-id="d5427-297">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

   <span data-ttu-id="d5427-298">對於其他類型的事件，此欄位通常為空白。</span><span class="sxs-lookup"><span data-stu-id="d5427-298">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="d5427-299">**return_path**： 傳送訊息的**MAIL FROM**命令所指定的退回電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d5427-299">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message.</span></span> <span data-ttu-id="d5427-300">雖然此欄位不會是空的但會以來表示以 null 寄件者地址值`<>`。</span><span class="sxs-lookup"><span data-stu-id="d5427-300">Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="d5427-301">**message_info**： 郵件的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="d5427-301">**message_info**: Additional information about the message.</span></span> <span data-ttu-id="d5427-302">例如：</span><span class="sxs-lookup"><span data-stu-id="d5427-302">For example:</span></span>

   - <span data-ttu-id="d5427-303">訊息起始日期-時間 UTC 的`DELIVER`和`SEND`事件。</span><span class="sxs-lookup"><span data-stu-id="d5427-303">The message origination date-time in UTC for `DELIVER` and `SEND` events.</span></span> <span data-ttu-id="d5427-304">原始日期時間是當郵件最初進入 Exchange Online 組織的時間。</span><span class="sxs-lookup"><span data-stu-id="d5427-304">The origination date-time is the time when the message first entered the Exchange Online organization.</span></span> <span data-ttu-id="d5427-305">以 ISO 8601 日期時間格式表示 UTC 日期及時間： `yyyy-mm-ddThh:mm:ss.fffZ`，其中`yyyy`= 年、 `mm` = 月、 `dd` = 日，`T`表示時間元件，開頭`hh`= 小時、 `mm` = 分鐘、 `ss` = 秒， `fff` =一秒的分數和`Z`代表`Zulu`，也就是另一種指出 UTC 的方法。</span><span class="sxs-lookup"><span data-stu-id="d5427-305">The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

   - <span data-ttu-id="d5427-306">驗證錯誤。</span><span class="sxs-lookup"><span data-stu-id="d5427-306">Authentication errors.</span></span> <span data-ttu-id="d5427-307">例如，您可能會看到值`11a`，以及發生驗證錯誤時所用的驗證的類型。</span><span class="sxs-lookup"><span data-stu-id="d5427-307">For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="d5427-308">**tenant_id**: GUID 值，代表在 Exchange Online 組織 (例如`39238e87-b5ab-4ef6-a559-af54c6b07b42`)。</span><span class="sxs-lookup"><span data-stu-id="d5427-308">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="d5427-309">**original_server_ip**： 在原始伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d5427-309">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="d5427-310">**custom_data**： 包含特定事件類型相關的資料。</span><span class="sxs-lookup"><span data-stu-id="d5427-310">**custom_data**: Contains data related to specific event types.</span></span> <span data-ttu-id="d5427-311">如需詳細資訊，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="d5427-311">For more information, see the following sections.</span></span>

#### <a name="customdata-values"></a><span data-ttu-id="d5427-312">custom_data 值</span><span class="sxs-lookup"><span data-stu-id="d5427-312">custom_data values</span></span>

<span data-ttu-id="d5427-313">**Custom_data**欄位`AGENTINFO`事件由不同的 Exchange Online 的代理程式用於記錄郵件處理的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d5427-313">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details.</span></span> <span data-ttu-id="d5427-314">下列各節說明一些有趣的代理程式。</span><span class="sxs-lookup"><span data-stu-id="d5427-314">Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="d5427-315">垃圾郵件篩選器代理程式</span><span class="sxs-lookup"><span data-stu-id="d5427-315">Spam filter agent</span></span>

<span data-ttu-id="d5427-316">**Custom_data**值的開頭，`S:SFA`是來自垃圾郵件篩選器代理程式。</span><span class="sxs-lookup"><span data-stu-id="d5427-316">A **custom_data** value that starts with `S:SFA` is from the spam filter agent.</span></span> <span data-ttu-id="d5427-317">下表說明重要詳細資料：</span><span class="sxs-lookup"><span data-stu-id="d5427-317">The key details are described in the following table:</span></span>

|<span data-ttu-id="d5427-318">**值**</span><span class="sxs-lookup"><span data-stu-id="d5427-318">**Value**</span></span>|<span data-ttu-id="d5427-319">**描述**</span><span class="sxs-lookup"><span data-stu-id="d5427-319">**Description**</span></span>|
|:-----|:-----|
|`SFV=NSPM`|<span data-ttu-id="d5427-320">郵件標記為非垃圾郵件，並傳送給預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="d5427-320">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="d5427-321">內容篩選已將郵件標記為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-321">The message was marked as spam by the content filter.</span></span>|
|`SFV=BLK`|<span data-ttu-id="d5427-322">已略過篩選，且郵件來自封鎖的寄件者，所以封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-322">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="d5427-p151">內容篩選在處理郵件前，已將郵件標記為垃圾郵件。這包括符合傳輸規則因此自動標記為垃圾郵件，因而略過所有其他篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-p151">The message was marked as spam prior to being processed by the content filter. This includes messages where the message matched a Transport rule to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="d5427-325">如需不同 SCL 值及其意義的詳細資訊，請參閱 <<c0>垃圾郵件信賴等級。</span><span class="sxs-lookup"><span data-stu-id="d5427-325">For more information about the different SCL values and what they mean, see [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`PCL=<number>`|<span data-ttu-id="d5427-326">郵件的網路釣魚信賴等級 (PCL) 值。</span><span class="sxs-lookup"><span data-stu-id="d5427-326">The Phishing Confidence Level (PCL) value of the message.</span></span> <span data-ttu-id="d5427-327">這些可以解譯一樣 SCL[垃圾郵件信賴等級](https://technet.microsoft.com/library/jj200686.aspx)所記載的值。</span><span class="sxs-lookup"><span data-stu-id="d5427-327">These can be interpreted the same way as the SCL values documented in [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`DI=SB`|<span data-ttu-id="d5427-328">已封鎖郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="d5427-328">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="d5427-329">已隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-329">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="d5427-330">已刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-330">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="d5427-331">郵件已傳送至收件者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d5427-331">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="d5427-332">已透過較高風險傳遞集區路由傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-332">The message was routed through the higher risk delivery pool.</span></span> <span data-ttu-id="d5427-333">如需詳細資訊，請參閱 <<c0>高風險傳遞集區的外寄郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-333">For more information, see [High-risk delivery pool for outbound messages](https://technet.microsoft.com/library/jj200746.aspx).</span></span>|
|`DI=SO`|<span data-ttu-id="d5427-334">已透過標準輸出傳遞集區路由傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-334">The message was routed through the normal outbound delivery pool.</span></span>|
|`SFS=[a]|SFS=[b]`|<span data-ttu-id="d5427-335">這表示已符合垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="d5427-335">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="d5427-336">因為 IP 位址指定於連線篩選的 [IP 允許] 清單中，所以已透過垃圾郵件篩選允許郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-336">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="d5427-337">連線的電子郵件伺服器的 HELO 或 EHLO 字串。</span><span class="sxs-lookup"><span data-stu-id="d5427-337">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="d5427-338">傳送 IP 位址 (也稱為反向 DNS 位址) 的 PTR 記錄。</span><span class="sxs-lookup"><span data-stu-id="d5427-338">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|

<span data-ttu-id="d5427-339">就像這樣的垃圾郵件篩選的郵件範例**custom_data**值：</span><span class="sxs-lookup"><span data-stu-id="d5427-339">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="d5427-340">惡意程式碼篩選器代理程式</span><span class="sxs-lookup"><span data-stu-id="d5427-340">Malware filter agent</span></span>

<span data-ttu-id="d5427-341">**Custom_data**值的開頭，`S:AMA`是來自惡意程式碼篩選器代理程式。</span><span class="sxs-lookup"><span data-stu-id="d5427-341">A **custom_data** value that starts with `S:AMA` is from the malware filter agent.</span></span> <span data-ttu-id="d5427-342">下表說明重要詳細資料：</span><span class="sxs-lookup"><span data-stu-id="d5427-342">The key details are described in the following table:</span></span>

|<span data-ttu-id="d5427-343">**值**</span><span class="sxs-lookup"><span data-stu-id="d5427-343">**Value**</span></span>|<span data-ttu-id="d5427-344">**描述**</span><span class="sxs-lookup"><span data-stu-id="d5427-344">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d5427-345">`AMA=SUM|v=1|` 或 `AMA=EV|v=1`</span><span class="sxs-lookup"><span data-stu-id="d5427-345">`AMA=SUM|v=1|` or `AMA=EV|v=1`</span></span>|<span data-ttu-id="d5427-346">郵件已判定為包含惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="d5427-346">The message was determined to contain malware.</span></span> <span data-ttu-id="d5427-347">`SUM`會指出惡意程式碼可能已偵測到的任何數字的引擎。</span><span class="sxs-lookup"><span data-stu-id="d5427-347">`SUM` indicates the malware could've been detected by any number of engines.</span></span> <span data-ttu-id="d5427-348">`EV`會指出特定引擎所偵測到惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="d5427-348">`EV` indicates the malware was detected by a specific engine.</span></span> <span data-ttu-id="d5427-349">引擎偵測到惡意程式碼時，這會觸發後續動作。</span><span class="sxs-lookup"><span data-stu-id="d5427-349">When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="d5427-350">已取代郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-350">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="d5427-351">已略過郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-351">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="d5427-352">已延遲郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-352">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="d5427-353">已刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-353">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="d5427-354">已略過郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-354">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="d5427-355">已略過郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-355">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="d5427-356">已拒絕郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-356">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="d5427-357">已拒絕郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-357">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="d5427-358">已封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="d5427-358">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="d5427-359">偵測到之惡意程式碼的名稱。</span><span class="sxs-lookup"><span data-stu-id="d5427-359">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="d5427-360">含有惡意程式碼之檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="d5427-360">The name of the file that contained the malware.</span></span>|

<span data-ttu-id="d5427-361">郵件包含惡意程式碼範例**custom_data**值看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="d5427-361">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="d5427-362">傳輸規則代理程式</span><span class="sxs-lookup"><span data-stu-id="d5427-362">Transport Rule agent</span></span>

<span data-ttu-id="d5427-363">**Custom_data**值的開頭，`S:TRA`是從郵件流程規則 （也稱為傳輸規則） 的傳輸規則代理程式。</span><span class="sxs-lookup"><span data-stu-id="d5427-363">A **custom_data** value that starts with`S:TRA` is from the Transport Rule agent for mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="d5427-364">下表說明重要詳細資料：</span><span class="sxs-lookup"><span data-stu-id="d5427-364">The key details are described in the following table:</span></span>

|<span data-ttu-id="d5427-365">**值**</span><span class="sxs-lookup"><span data-stu-id="d5427-365">**Value**</span></span>|<span data-ttu-id="d5427-366">**描述**</span><span class="sxs-lookup"><span data-stu-id="d5427-366">**Description**</span></span>|
|:-----|:-----|
|`ETR|ruleId=<guid>`|<span data-ttu-id="d5427-367">已符合的規則 ID。</span><span class="sxs-lookup"><span data-stu-id="d5427-367">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="d5427-368">日期和時間 UTC 規則相符項目發生時。</span><span class="sxs-lookup"><span data-stu-id="d5427-368">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="d5427-369">已套用的動作。</span><span class="sxs-lookup"><span data-stu-id="d5427-369">The action that was applied.</span></span> <span data-ttu-id="d5427-370">如需可用動作的清單，請參閱[郵件流程規則動作在 Exchange Online](https://technet.microsoft.com/library/jj919237.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d5427-370">For a list of available actions, see [Mail flow rule actions in Exchange Online](https://technet.microsoft.com/library/jj919237.aspx).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="d5427-371">規則的模式。</span><span class="sxs-lookup"><span data-stu-id="d5427-371">The mode of the rule.</span></span> <span data-ttu-id="d5427-372">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="d5427-372">Valid values are:</span></span> <br/><span data-ttu-id="d5427-373">• **Enforce**： 將強制執行規則上的所有動作。</span><span class="sxs-lookup"><span data-stu-id="d5427-373">• **Enforce**: All actions on the rule will be enforced.</span></span> <br/><span data-ttu-id="d5427-374">•**搭配原則提示來測試：**： 將會傳送任何 「 原則提示 」 動作，但不是會在處理其他強制執行動作。</span><span class="sxs-lookup"><span data-stu-id="d5427-374">• **Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span> <br/><span data-ttu-id="d5427-375">•**不搭配原則提示就測試**： 動作將會列在記錄檔中，但不是會以任何方法通知寄件者和上不會處理強制執行動作。</span><span class="sxs-lookup"><span data-stu-id="d5427-375">• **Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span>|

<span data-ttu-id="d5427-376">符合條件的郵件流程規則，範例**custom_data**值的郵件看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="d5427-376">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
