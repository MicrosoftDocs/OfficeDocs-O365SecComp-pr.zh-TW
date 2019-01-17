---
title: 安全性 & 規範中心中的郵件追蹤
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
description: 系統管理員可以使用郵件追蹤安全性 & 規範中心中找出郵件有何。
ms.openlocfilehash: 9dfdab4adc5caba55664e93b49c8428791670ab3
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685393"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="983fa-103">安全性 & 規範中心中的郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="983fa-103">Message trace in the Security & Compliance Center</span></span>

<span data-ttu-id="983fa-p101">安全性 & 規範中心中的郵件追蹤遵循出差透過 Exchange Online 組織的電子郵件。您可以決定如果已收到、 拒絕、 延遲、 或郵件傳遞服務。它也會顯示動作所採取的郵件上之前它達到其最終狀態。</span><span class="sxs-lookup"><span data-stu-id="983fa-p101">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization. You can determine if a message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="983fa-p102">在 Exchange 系統管理中心 (EAC) 中所提供的郵件追蹤時改善安全性 & 規範中心中的郵件追蹤。您可以使用郵件追蹤資訊有效率地回答關於何其訊息的使用者問題、 進行疑難排解郵件流程，及驗證原則的變更。</span><span class="sxs-lookup"><span data-stu-id="983fa-p102">Message trace in the Security & Compliance Center improves upon message trace that was available in the Exchange admin center (EAC). You can use the information from message trace to efficiently answer user questions about what happened to their messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="983fa-109">開啟郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="983fa-109">Open message trace</span></span>

1. <span data-ttu-id="983fa-110">使用您的 公司或學校帳戶[登入 Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="983fa-110">[Sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="983fa-111">，然後選擇 [系統管理]。</span><span class="sxs-lookup"><span data-stu-id="983fa-111">Select the app launcher icon ![Office 365 app launcher icon](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="983fa-112">在左下導覽列中，依序展開 [**系統管理置中**並選取**安全性 & 規範**。</span><span class="sxs-lookup"><span data-stu-id="983fa-112">In the lower-left navigation, expand **Admin centers** and select **Security & Compliance**.</span></span>

4. <span data-ttu-id="983fa-113">在開啟的**安全性 & 規範**頁面上，依序展開 [**郵件流程**，並選取**郵件追蹤**。</span><span class="sxs-lookup"><span data-stu-id="983fa-113">In the **Security & Compliance** page that opens, expand **Mail flow**, and select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="983fa-114">郵件追蹤] 頁面</span><span class="sxs-lookup"><span data-stu-id="983fa-114">Message trace page</span></span>

<span data-ttu-id="983fa-p103">從以下是您可以按一下 [**啟動追蹤**] 按鈕上的 [啟動新的預設追蹤。這將搜尋所有郵件的所有寄件者和收件者的最後兩天。或您可以使用其中一個可用查詢類別的預存查詢和 [執行這些做為-或作為起始點您自己的查詢：</span><span class="sxs-lookup"><span data-stu-id="983fa-p103">From here you can start a new default trace by clicking on the **Start a trace** button. This will search for all messages for all senders and recipients for the last two days. Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="983fa-118">**預設查詢**： Office 365 提供的內建的查詢。</span><span class="sxs-lookup"><span data-stu-id="983fa-118">**Default queries**: Built-in queries provided by Office 365.</span></span>

- <span data-ttu-id="983fa-119">**自訂查詢**： 查詢儲存供日後使用您組織中的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="983fa-119">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="983fa-p104">**Autosaved 查詢**： 最後一個 10 個最近執行查詢。這份清單會簡單挑選維持。</span><span class="sxs-lookup"><span data-stu-id="983fa-p104">**Autosaved queries**: The last ten most recently run queries. This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="983fa-122">也在此頁面時**Downloadable 報告**] 區段中的要求您已送出、 為其本身的報表有可用的下載 （英文）。</span><span class="sxs-lookup"><span data-stu-id="983fa-122">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="983fa-123">新的郵件追蹤選項</span><span class="sxs-lookup"><span data-stu-id="983fa-123">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="983fa-124">依寄件者和收件者篩選</span><span class="sxs-lookup"><span data-stu-id="983fa-124">Filter by senders and recipients</span></span>

<span data-ttu-id="983fa-125">預設值是**所有寄件者**和**所有收件者**，但您可以使用下列欄位來篩選結果：</span><span class="sxs-lookup"><span data-stu-id="983fa-125">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="983fa-p105">**由下列人員**： 按一下 [從您的組織中選取一或多個寄件者此欄位中。您也可以開始輸入的名稱及由您已輸入的內容、 更加類似的搜尋頁面的行為會篩選清單中的項目。</span><span class="sxs-lookup"><span data-stu-id="983fa-p105">**By these people**: Click in this field to select one or more senders from your organization. You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="983fa-128">**以這些人員**： 按一下 [在組織中選取一或多個收件者此欄位。</span><span class="sxs-lookup"><span data-stu-id="983fa-128">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

<span data-ttu-id="983fa-p106">您也可以輸入外部寄件者和收件者的電子郵件地址。支援萬用字元 (`*@contoso.com`或`scot?@contoso.com`)，但您無法同時在相同欄位中使用多個萬用字元項目。</span><span class="sxs-lookup"><span data-stu-id="983fa-p106">You can also type the email addresses of external senders and recipients. Wildcards are supported (`*@contoso.com` or `scot?@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span>

### <a name="time-range"></a><span data-ttu-id="983fa-131">時間範圍</span><span class="sxs-lookup"><span data-stu-id="983fa-131">Time range</span></span>

<span data-ttu-id="983fa-p107">預設值為**2 天**，但您可以指定多達 90 天的日期/時間範圍。當您使用日期/時間範圍時，請考量下列問題：</span><span class="sxs-lookup"><span data-stu-id="983fa-p107">The default value is **2 days**, but you can specify date/time ranges of up to 90 days. When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="983fa-p108">根據預設，您要使用時間列的**滑動軸**檢視中選取時間範圍。您只可以選取一天或時間顯示的設定。嘗試選取中間值會貼齊開始/結束泡泡至最接近顯示設定。</span><span class="sxs-lookup"><span data-stu-id="983fa-p108">By default, you select the time range in **Slider** view using a time line. You can only select the day or time settings that are displayed. Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

   ![在新的郵件追蹤中安全性 & 規範中心滑桿時間範圍](media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

   <span data-ttu-id="983fa-p109">但是，您也可以切換至**自訂**檢視其中您可以指定的**開始日期**和**結束日期**值 （包括時間），而您也可以選取日期/時間範圍內的**時區**。請注意，**時區**設定會套用到您的查詢輸入與查詢結果。</span><span class="sxs-lookup"><span data-stu-id="983fa-p109">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range. Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

   ![自訂時間範圍中的安全性 & 規範中心新郵件追蹤](media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

   <span data-ttu-id="983fa-p110">代表 10 天或更少，結果可用立即為**摘要**報告。如果您指定即使稍微超過 10 天的時間範圍，結果將只會提供可下載的 CSV 檔案 （**增強摘要**或**延伸**適用報表） 延遲。</span><span class="sxs-lookup"><span data-stu-id="983fa-p110">For 10 days or less, the results are available instantly as a **Summary** report. If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

   <span data-ttu-id="983fa-143">如需不同的報告類型的詳細資訊，請參閱本主題中的 [[選擇報表類型](#choose-report-type)] 區段。</span><span class="sxs-lookup"><span data-stu-id="983fa-143">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this topic.</span></span>

   <span data-ttu-id="983fa-p111">**請注意**： 增強摘要與延伸報告已準備使用已封存的郵件追蹤資料，以及它可能需要數小時才能報表是可供下載。已排入佇列的要求開始處理之前，根據多少其他系統管理員也已提交報表要求周圍的同一時間，可能會需要注意的延遲。</span><span class="sxs-lookup"><span data-stu-id="983fa-p111">**Note**: Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download. Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="983fa-p112">在**滑桿**檢視中儲存的查詢會儲存相對的時間範圍 （例如，從今天 3 天）。在**自訂**檢視中儲存的查詢會儲存絕對日期/時間範圍 (例如 2018年-05-06 13:00 到 2018年-05-08 18:00)。</span><span class="sxs-lookup"><span data-stu-id="983fa-p112">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today). Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="983fa-148">更多搜尋選項</span><span class="sxs-lookup"><span data-stu-id="983fa-148">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="983fa-149">傳遞狀態</span><span class="sxs-lookup"><span data-stu-id="983fa-149">Delivery status</span></span>

<span data-ttu-id="983fa-150">您可以將保留**所有**選取的預設值或您可以選取其中一個來篩選結果的下列值：</span><span class="sxs-lookup"><span data-stu-id="983fa-150">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="983fa-151">**已傳遞**： 郵件已成功傳遞至預定目的地。</span><span class="sxs-lookup"><span data-stu-id="983fa-151">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="983fa-152">**擱置**： 正在郵件的傳送嘗試或重新嘗試。</span><span class="sxs-lookup"><span data-stu-id="983fa-152">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="983fa-153">**Expanded**： 個別群組的成員在傳遞之前已展開的通訊群組收件者。</span><span class="sxs-lookup"><span data-stu-id="983fa-153">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="983fa-154">**失敗**： 無法傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-154">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="983fa-p113">**隔離**： 郵件遭隔離時 （做為垃圾郵件、 大量郵件或網路釣魚）。如需詳細資訊，請參閱[Office 365 中的隔離電子郵件訊息](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="983fa-p113">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing). For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).</span></span>

- <span data-ttu-id="983fa-157">**為垃圾郵件篩選**： 郵件已識別垃圾郵件和已拒絕或封鎖的 （未隔離）。</span><span class="sxs-lookup"><span data-stu-id="983fa-157">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="983fa-p114">**取得狀態：** Office 365 最近接收到郵件但尚未可以使用任何其他狀態資料。存回幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="983fa-p114">**Getting status:** The message was recently received by Office 365, but no other status data is yet available. Check back in a few minutes.</span></span>

<span data-ttu-id="983fa-p115">**請注意**：**擱置、** **隔離**，並**為垃圾郵件篩選**的值只適用於搜尋少於 10 天。此外，可能會有 5 到 10 分鐘的延遲之間的實際和報告的傳遞狀態。</span><span class="sxs-lookup"><span data-stu-id="983fa-p115">**Note**: The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days. Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="983fa-162">郵件識別碼</span><span class="sxs-lookup"><span data-stu-id="983fa-162">Message ID</span></span>

<span data-ttu-id="983fa-p116">這是中找到的網際網路郵件識別碼 （也稱為用戶端識別碼）**訊息識別碼：** 郵件標頭中的標頭] 欄位。使用者可以提供此值設為調查特定的郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-p116">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header. Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="983fa-p117">這個值是郵件的存留期的常數。建立 Office 365 或 Exchange 中的郵件，值為格式`<GUID@ServerFQDN>`，包括角括弧 (\< \>)。例如， `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。其他郵件系統可能會使用不同的語法或值。此值應該是唯一的但不是所有的電子郵件系統嚴格遵守下列需求。如果**訊息識別碼：** 、 標頭欄位不存在或是空白的內送郵件從外部來源的指派為任意值。</span><span class="sxs-lookup"><span data-stu-id="983fa-p117">This value is constant for the lifetime of the message. For messages created in Office 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>). For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Other messaging systems might use different syntax or values. This value is supposed to be unique, but not all email systems strictly follow this requirement. If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="983fa-171">當您使用**訊息識別碼**來篩選結果時，請務必包含完整的字串，包括任何角括弧。</span><span class="sxs-lookup"><span data-stu-id="983fa-171">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="983fa-172">方向</span><span class="sxs-lookup"><span data-stu-id="983fa-172">Direction</span></span>

<span data-ttu-id="983fa-173">您可以將保留**所有**選取的預設值或您可以選取**輸入**（傳送給組織中的收件者的郵件） 或**輸出**（從您組織中使用者傳送的訊息） 來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="983fa-173">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="983fa-174">原始用戶端 IP 位址</span><span class="sxs-lookup"><span data-stu-id="983fa-174">Original client IP address</span></span>

<span data-ttu-id="983fa-p118">您可以風格結果依調查破解的電腦所傳送的垃圾郵件或惡意程式碼建立大量的用戶端 IP 位址。雖然訊息可能會出現來自多個寄件者，則可能是同一部電腦會產生的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-p118">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware. Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

<span data-ttu-id="983fa-177">**請注意**： 用戶端 IP 位址資訊才有 10 天，並只能供**增強摘要**或**延伸**報告 （可下載的 CSV 檔案） 中。</span><span class="sxs-lookup"><span data-stu-id="983fa-177">**Note**: The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="983fa-178">選擇 [報告類型</span><span class="sxs-lookup"><span data-stu-id="983fa-178">Choose report type</span></span>

<span data-ttu-id="983fa-179">可用的報告類型如下：</span><span class="sxs-lookup"><span data-stu-id="983fa-179">The available report types are:</span></span>

- <span data-ttu-id="983fa-p119">**摘要**： 提供如果時間範圍少於 10 天，而需要額外的篩選選項。幾乎立即之後按一下 [**搜尋**結果可用。</span><span class="sxs-lookup"><span data-stu-id="983fa-p119">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options. The results are available almost immediately after you click **Search**.</span></span>

- <span data-ttu-id="983fa-p120">**增強摘要**或**延伸**： 這些報告只可使用成可下載的 CSV 檔案，且需要一或多個不論時間範圍內的下列篩選選項：**這些人員**、**給這些人員**、 或是**訊息識別碼**。您可以使用萬用字元寄件者或收件者 (例如\*@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="983fa-p120">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**. You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span>

<span data-ttu-id="983fa-184">**附註**：</span><span class="sxs-lookup"><span data-stu-id="983fa-184">**Notes**:</span></span>

- <span data-ttu-id="983fa-p121">增強的摘要與延伸報告已準備使用已封存的郵件追蹤資料，以及它可能需要數小時才能報告可供下載。您已排入佇列的要求開始處理之前，根據多少其他系統管理員也已提交報表要求的同一時間周圍，可能會需要注意的延遲。</span><span class="sxs-lookup"><span data-stu-id="983fa-p121">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download. Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>

- <span data-ttu-id="983fa-187">雖然您可以選取任何增強摘要或延伸報告日期/時間範圍、 常封存的資料前四個小時不會尚未提供下列兩種類型的報告。</span><span class="sxs-lookup"><span data-stu-id="983fa-187">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="983fa-p122">提供當您按一下 [**下一步**時] 與 [摘要] 頁面上列出您選取的篩選選項的報告和郵件追蹤完成 （也可編輯、 時收到通知的電子郵件地址的唯一 （編輯） 標題必須在其中一個貴組織的公認的網域)。按一下 [**準備報表**送出的郵件追蹤]。在 [主要**郵件追蹤**] 頁面上，您可以看到 [ **Downloadable 報告**] 區段中報告的狀態。</span><span class="sxs-lookup"><span data-stu-id="983fa-p122">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains). Click **Prepare report** to submit the message trace. On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="983fa-191">如需會傳回在不同的報告類型的資訊的詳細資訊，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="983fa-191">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="983fa-192">郵件追蹤結果</span><span class="sxs-lookup"><span data-stu-id="983fa-192">Message trace results</span></span>

<span data-ttu-id="983fa-p123">不同的報告類型傳回不同的層級的資訊。下列各節說明不同的報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="983fa-p123">The different report types return different levels of information. The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="983fa-195">摘要報告輸出</span><span class="sxs-lookup"><span data-stu-id="983fa-195">Summary report output</span></span>

<span data-ttu-id="983fa-196">執行郵件追蹤、 之後結果都會列、 依日期/時間 （最新的第一個） 的遞減排序。</span><span class="sxs-lookup"><span data-stu-id="983fa-196">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![安全性 & 規範中心中的郵件追蹤結果摘要報告](media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="983fa-198">摘要報告包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="983fa-198">The summary report contains the following information:</span></span>

- <span data-ttu-id="983fa-199">**日期**： 的日期和時間的收到郵件服務，使用設定的 UTC 時區。</span><span class="sxs-lookup"><span data-stu-id="983fa-199">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="983fa-200">**寄件者**： 寄件者的電子郵件地址 (*別名*@*網域*)。</span><span class="sxs-lookup"><span data-stu-id="983fa-200">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="983fa-p124">**收件者**： 收件者或收件者的電子郵件地址。傳送給多個收件者的訊息，有收件者每一列。如果收件者是通訊群組、 動態通訊群組或擁有郵件功能的安全性群組，群組會為第一個收件者和每個群組的成員則分列一行。</span><span class="sxs-lookup"><span data-stu-id="983fa-p124">**Recipient**: The email address of the recipient or recipients. For a message sent to multiple recipients, there's one line per recipient. If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="983fa-204">**主旨**： 郵件的前 256 個字元**Subject:** ] 欄位。</span><span class="sxs-lookup"><span data-stu-id="983fa-204">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="983fa-205">**狀態**： 這些值會[傳遞狀態](#delivery-status)] 區段中所述。</span><span class="sxs-lookup"><span data-stu-id="983fa-205">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="983fa-p125">依預設前, 250 結果會載入並備妥。當您向下捲動時，有稍微暫停為下一個批次的結果會載入。而非捲動，您可以按一下 [**載入所有**載入的所有最多 10000 的結果。</span><span class="sxs-lookup"><span data-stu-id="983fa-p125">By default, the first 250 results are loaded and readily available. When you scroll down, there's a slight pause as the next batch of results are loaded. Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="983fa-209">您可以用來排序結果遞增排序還是遞減排序的資料行中值的欄標題上按一下。</span><span class="sxs-lookup"><span data-stu-id="983fa-209">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="983fa-210">您可以按一下 [**篩選結果**至一或多個欄來篩選結果。</span><span class="sxs-lookup"><span data-stu-id="983fa-210">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="983fa-211">您可以將結果匯出之後您已按一下 [**匯出結果**，再選取 [**匯出所有結果**、**都匯出載入結果**，或**選取 [都匯出**選取一或多個資料列。</span><span class="sxs-lookup"><span data-stu-id="983fa-211">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="983fa-212">此郵件尋找相關的記錄</span><span class="sxs-lookup"><span data-stu-id="983fa-212">Find related records for this message</span></span>

<span data-ttu-id="983fa-p126">相關的訊息記錄所記錄的共用相同的訊息識別碼。請記住，即使兩個人之間傳送單一郵件可以產生多筆記錄。記錄數目增加時的郵件會影響通訊群組擴充、 轉接、 郵件流程規則 （也稱為傳輸規則） 等。</span><span class="sxs-lookup"><span data-stu-id="983fa-p126">Related message records are records that shared the same Message ID. Remember, even a single message sent between two people can generate multiple records. The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="983fa-216">您選取的資料列] 核取方塊之後，您可以找到相關的記錄訊息透過按一下 [**尋找相關**的] 按鈕出現，或選取**更多選項**![詳細](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **尋找此郵件的相關的記錄**)。</span><span class="sxs-lookup"><span data-stu-id="983fa-216">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="983fa-217">如需訊息識別碼的詳細資訊，請參閱本主題中前面訊息識別碼] 區段。</span><span class="sxs-lookup"><span data-stu-id="983fa-217">For more information about the Message ID, see the Message ID section earlier in this topic.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="983fa-218">郵件追蹤詳細資料</span><span class="sxs-lookup"><span data-stu-id="983fa-218">Message trace details</span></span>

<span data-ttu-id="983fa-219">摘要報告輸出中，您可以使用下列方法之一檢視郵件詳細資料：</span><span class="sxs-lookup"><span data-stu-id="983fa-219">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="983fa-220">選取的列 (按一下 [中] 核取方塊以外的列的任何位置)。</span><span class="sxs-lookup"><span data-stu-id="983fa-220">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="983fa-221">選取列] 核取方塊並按一下 [**更多選項**![詳細](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **檢視郵件詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="983fa-221">Select the row's check box and click **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![按兩下安全性 & 規範中心中的摘要報告郵件追蹤結果集中的列之後的詳細資訊](media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="983fa-223">郵件追蹤詳細資料包含下列摘要報告中不存在的其他資訊：</span><span class="sxs-lookup"><span data-stu-id="983fa-223">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="983fa-p127">**郵件事件**： 本節包含協助分類 （英文） 服務的郵件採取的動作的分類。某些可能遇到之更有趣但事件是：</span><span class="sxs-lookup"><span data-stu-id="983fa-p127">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages. Some of the more interesting events that you might encounter are:</span></span>

   - <span data-ttu-id="983fa-226">**接收**： 服務所收到郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-226">**Receive**: The message was received by the service.</span></span>

   - <span data-ttu-id="983fa-227">**傳送**： 服務傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-227">**Send**: The message was sent by the service.</span></span>

   - <span data-ttu-id="983fa-228">**失敗**： 無法傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-228">**Fail**: The message failed to be delivered.</span></span>

   - <span data-ttu-id="983fa-229">**傳送**： 郵件已傳遞至信箱。</span><span class="sxs-lookup"><span data-stu-id="983fa-229">**Deliver**: The message was delivered to a mailbox.</span></span>

   - <span data-ttu-id="983fa-230">**展開**： 至展開的通訊群組傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-230">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

   - <span data-ttu-id="983fa-231">**傳輸**： 收件者已移至緣故郵件由於內容轉換、 郵件收件者限制或代理程式。</span><span class="sxs-lookup"><span data-stu-id="983fa-231">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

   - <span data-ttu-id="983fa-232">**Defer**： 郵件傳遞已延遲，且可能稍後再試。</span><span class="sxs-lookup"><span data-stu-id="983fa-232">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

   - <span data-ttu-id="983fa-p128">**已解決**： 郵件已重新導向至新的收件者地址根據 Active Directory 查詢。當發生這種情況的原始收件者地址會列在郵件追蹤郵件最終的傳遞狀態中的個別資料列。</span><span class="sxs-lookup"><span data-stu-id="983fa-p128">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up. When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

   <span data-ttu-id="983fa-235">請注意即使順利傳遞較為簡單的訊息就會產生多個**事件**項目在郵件追蹤。</span><span class="sxs-lookup"><span data-stu-id="983fa-235">Note that even an uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>

- <span data-ttu-id="983fa-236">**更多資訊**： 這一節包含下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="983fa-236">**More information**: This section contains the following details:</span></span>

   - <span data-ttu-id="983fa-p129">**訊息識別碼**： 此主題稍早[訊息識別碼](#message-id)一節說明此值。例如， `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="983fa-p129">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this topic. For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

   - <span data-ttu-id="983fa-239">**郵件大小**</span><span class="sxs-lookup"><span data-stu-id="983fa-239">**Message size**</span></span>

   - <span data-ttu-id="983fa-p130">**從 IP**： 傳送訊息之電腦的 IP 位址。從 Exchange Online 傳送輸出的郵件，這個值是空白的。</span><span class="sxs-lookup"><span data-stu-id="983fa-p130">**From IP**: The IP address of the computer that sent the message. For outbound messages sent from Exchange Online, this value is blank.</span></span>

   - <span data-ttu-id="983fa-p131">**若要 IP**： 的 IP 位址] 或 [服務嘗試傳遞郵件的地址。如果該郵件未多位收件者，會顯示這些。內送郵件傳送至 Exchange Online，這個值是空白的。</span><span class="sxs-lookup"><span data-stu-id="983fa-p131">**To IP**: The IP address or addresses where the service attempted to deliver the message. If the message has multiple recipients, these are displayed. For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="983fa-245">增強的摘要報告</span><span class="sxs-lookup"><span data-stu-id="983fa-245">Enhanced summary reports</span></span>

<span data-ttu-id="983fa-p132">開始郵件追蹤**報告 Downloadable**一節中有可用 （已完成） 的增強摘要報告。下列資訊可用於報告：</span><span class="sxs-lookup"><span data-stu-id="983fa-p132">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace. The following information is available in the report:</span></span>

- <span data-ttu-id="983fa-248">**origin_timestamp**<sup>\*</sup>： 的日期和時間時開始收到郵件服務，使用設定的 UTC 時區。</span><span class="sxs-lookup"><span data-stu-id="983fa-248">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="983fa-249">**sender_address 採用**： 寄件者的電子郵件地址 (*別名*@*網域*)。</span><span class="sxs-lookup"><span data-stu-id="983fa-249">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="983fa-p133">**Recipient_status**： 郵件的收件者傳送的狀態。如果郵件傳送給多個收件者，它會顯示所有收件者和對應的狀態格式的每個： \<*電子郵件地址*\>##\<*狀態*\>。例如：</span><span class="sxs-lookup"><span data-stu-id="983fa-p133">**Recipient_status**: The status of the delivery of the message to the recipient. If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>. For example:</span></span>

   - <span data-ttu-id="983fa-253">**##Receive、 傳送**表示服務已接收到郵件，並傳送至預定目的地。</span><span class="sxs-lookup"><span data-stu-id="983fa-253">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

   - <span data-ttu-id="983fa-254">**##Receive、 失敗**表示服務但傳遞至預定目的地失敗的收到郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-254">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

   - <span data-ttu-id="983fa-255">**##Receive、 傳遞**表示服務已接收到郵件，並已傳遞至收件者的信箱。</span><span class="sxs-lookup"><span data-stu-id="983fa-255">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="983fa-256">**message_subject**： 郵件的**主旨**] 欄位的前 256 個字元。</span><span class="sxs-lookup"><span data-stu-id="983fa-256">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="983fa-257">**total_bytes**： 以位元組為單位，包括附件的郵件大小。</span><span class="sxs-lookup"><span data-stu-id="983fa-257">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="983fa-p134">**message_id**： 此主題稍早[訊息識別碼](#message-id)一節說明此值。例如， `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="983fa-p134">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this topic. For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="983fa-p135">**network_message_id**： 套用到所有郵件可能會因為複本發送或通訊群組擴充而建立的複本的唯一訊息識別碼值。範例值是`1341ac7b13fb42ab4d4408cf7f55890f`。</span><span class="sxs-lookup"><span data-stu-id="983fa-p135">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion. An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="983fa-262">**original_client_ip**： 寄件者的用戶端的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="983fa-262">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="983fa-263">**directionality**： 指出是否已傳送郵件 （1），您的組織或是否送出 （2） 從您的組織。</span><span class="sxs-lookup"><span data-stu-id="983fa-263">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="983fa-p136">**connector_id**： 來源或目的地連接器名稱。如需 Exchange Online 中的連接器的詳細資訊，請參閱[使用 Office 365 中的連接器設定郵件流程](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="983fa-p136">**connector_id**: The name of the source or destination connector. For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="983fa-266">**delivery_priority**<sup>\*</sup>： 是否將郵件傳送**高**]、 [**低**] 或 [**內文**的優先順序。</span><span class="sxs-lookup"><span data-stu-id="983fa-266">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="983fa-267"><sup>\*</sup>這些屬性只能中可用增強摘要報告。</span><span class="sxs-lookup"><span data-stu-id="983fa-267"><sup>\*</sup>These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="983fa-268">延伸的報告</span><span class="sxs-lookup"><span data-stu-id="983fa-268">Extended reports</span></span>

<span data-ttu-id="983fa-p137">郵件追蹤開頭 [ **Downloadable 報告**] 區段中有可用 （已完成） 的延伸報告。幾乎所有的增強摘要報告是資訊的可在 （除了**origin_timestamp**和**delivery_priority**） Extended 報表。延伸報表中只有下列額外的資訊：</span><span class="sxs-lookup"><span data-stu-id="983fa-p137">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace. Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**). The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="983fa-272">**client_ip**： 電子郵件伺服器或送出郵件的郵件用戶端的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="983fa-272">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="983fa-273">**client_hostname**： 的主機名稱或電子郵件伺服器或送出郵件的郵件用戶端的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="983fa-273">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="983fa-274">**server_ip**： 來源或目的地伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="983fa-274">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="983fa-275">**server_hostname**： 的主機名稱或目的地伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="983fa-275">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="983fa-p138">**source_context**： 與**來源**欄位相關的額外資訊。例如：</span><span class="sxs-lookup"><span data-stu-id="983fa-p138">**source_context**: Extra information associated with the **source** field. For example:</span></span>

   - `Protocol Filter Agent`

   - `3489061114359050000`

- <span data-ttu-id="983fa-p139">**來源**： 負責事件的 Exchange Online 元件。例如：</span><span class="sxs-lookup"><span data-stu-id="983fa-p139">**source**: The Exchange Online component that's responsible for the event. For example:</span></span>

   - `AGENT`

   - `MAILBOXRULE`

   - `SMTP`

- <span data-ttu-id="983fa-280">**event_id**： 這些對應至所述來[尋找此郵件的相關的記錄](#find-related-records-for-this-message)] 區段中的**郵件事件**值。</span><span class="sxs-lookup"><span data-stu-id="983fa-280">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="983fa-281">**internal_message_id**： 指派 Exchange Online 伺服器目前正在處理之郵件的郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="983fa-281">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="983fa-p140">**recipient_address**： 郵件的收件者的電子郵件地址。以分號 （;） 分隔多個電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="983fa-p140">**recipient_address**: The email addresses of the message's recipients. Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="983fa-284">**recipient_count**： 收件者的郵件總數。</span><span class="sxs-lookup"><span data-stu-id="983fa-284">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="983fa-285">**related_recipient_address**： 搭配`EXPAND`、 `REDIRECT`，及`RESOLVE`事件來顯示其他收件者電子郵件相關聯之郵件的地址。</span><span class="sxs-lookup"><span data-stu-id="983fa-285">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="983fa-p141">**參考**： 此欄位會包含特定事件類型的其他資訊。例如：</span><span class="sxs-lookup"><span data-stu-id="983fa-p141">**reference**: This field contains additional information for specific types of events. For example:</span></span>

   - <span data-ttu-id="983fa-p142">**DSN**： 包含相關聯的傳遞狀態通知 （又稱為 DSN、 未傳遞回報、 NDR 或彈跳訊息） **message_id**值，則使用 DSN 產生此事件之後的報告] 連結。如果這是 DSN 郵件，此欄位會包含 DSN 產生的原始郵件的**message_id**值。</span><span class="sxs-lookup"><span data-stu-id="983fa-p142">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event. If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

   - <span data-ttu-id="983fa-290">**展開**： 含有相關郵件的**related_recipient_address**值。</span><span class="sxs-lookup"><span data-stu-id="983fa-290">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

   - <span data-ttu-id="983fa-291">**接收**： 如果郵件產生供其他程序 （例如 [收件匣規則） 可能會包含相關訊息**message_id**值。</span><span class="sxs-lookup"><span data-stu-id="983fa-291">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

   - <span data-ttu-id="983fa-292">**傳送**： 含有任何 DSN 郵件的**internal_message_id**值。</span><span class="sxs-lookup"><span data-stu-id="983fa-292">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

   - <span data-ttu-id="983fa-293">**傳輸**： 包含**internal_message_id**值被分叉時 （例如，依內容轉換、 郵件收件者限制或代理程式） 的郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-293">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

   - <span data-ttu-id="983fa-294">**MAILBOXRULE**： 包含**internal_message_id**值造成產生外寄郵件的收件匣規則的內送郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-294">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

   <span data-ttu-id="983fa-295">其他類型的事件，此欄位是通常是空白的。</span><span class="sxs-lookup"><span data-stu-id="983fa-295">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="983fa-p143">**return_path**： 指定傳送的郵件**MAIL FROM**命令所傳回的電子郵件地址。雖然此欄位永遠不是空白的它可以具有 null 寄件者地址值以表示`<>`。</span><span class="sxs-lookup"><span data-stu-id="983fa-p143">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message. Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="983fa-p144">**message_info**： 郵件的其他資訊。例如：</span><span class="sxs-lookup"><span data-stu-id="983fa-p144">**message_info**: Additional information about the message. For example:</span></span>

   - <span data-ttu-id="983fa-p145">郵件起始日期-時間的 utc`DELIVER`和`SEND`事件。起始日期-時間是當郵件先輸入 Exchange Online 組織的時間。UTC 的日期-時間表示以 ISO 8601 日期時間格式： `yyyy-mm-ddThh:mm:ss.fffZ`，其中`yyyy`= 年`mm`= 月、 `dd` = 一天`T`表示開頭的時間的元件， `hh` = 小時、 `mm` = 分鐘、 `ss` = 第二、 `fff`= 分數的第二、 和`Z`代表`Zulu`，這是另一種方式皆 UTC。</span><span class="sxs-lookup"><span data-stu-id="983fa-p145">The message origination date-time in UTC for `DELIVER` and `SEND` events. The origination date-time is the time when the message first entered the Exchange Online organization. The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

   - <span data-ttu-id="983fa-p146">驗證錯誤。例如，您可能會看到值`11a`和驗證錯誤發生時所使用的驗證類型。</span><span class="sxs-lookup"><span data-stu-id="983fa-p146">Authentication errors. For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="983fa-305">**tenant_id**： 代表 Exchange Online 組織的 GUID 值 (例如`39238e87-b5ab-4ef6-a559-af54c6b07b42`)。</span><span class="sxs-lookup"><span data-stu-id="983fa-305">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="983fa-306">**original_server_ip**： 原始伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="983fa-306">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="983fa-p147">**custom_data**： 包含與特定事件類型相關的資料。如需詳細資訊，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="983fa-p147">**custom_data**: Contains data related to specific event types. For more information, see the following sections.</span></span>

#### <a name="customdata-values"></a><span data-ttu-id="983fa-309">custom_data 值</span><span class="sxs-lookup"><span data-stu-id="983fa-309">custom_data values</span></span>

<span data-ttu-id="983fa-p148">**Custom_data**欄位`AGENTINFO`事件由 Exchange Online 的代理程式的各種可用來記錄訊息處理的詳細資訊。下列各節說明一些更有趣但代理程式。</span><span class="sxs-lookup"><span data-stu-id="983fa-p148">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details. Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="983fa-312">垃圾郵件篩選器代理程式</span><span class="sxs-lookup"><span data-stu-id="983fa-312">Spam filter agent</span></span>

<span data-ttu-id="983fa-p149">開頭的**custom_data**值`S:SFA`是來自垃圾郵件篩選器代理程式。下表說明重要詳細資料：</span><span class="sxs-lookup"><span data-stu-id="983fa-p149">A **custom_data** value that starts with `S:SFA` is from the spam filter agent. The key details are described in the following table:</span></span>

|<span data-ttu-id="983fa-315">**值**</span><span class="sxs-lookup"><span data-stu-id="983fa-315">**Value**</span></span>|<span data-ttu-id="983fa-316">**描述**</span><span class="sxs-lookup"><span data-stu-id="983fa-316">**Description**</span></span>|
|:-----|:-----|
|`SFV=NSPM`|<span data-ttu-id="983fa-317">郵件標記為非垃圾郵件，並傳送給預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="983fa-317">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="983fa-318">內容篩選已將郵件標記為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-318">The message was marked as spam by the content filter.</span></span>|
|`SFV=BLK`|<span data-ttu-id="983fa-319">已略過篩選，且郵件來自封鎖的寄件者，所以封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-319">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="983fa-p150">內容篩選在處理郵件前，已將郵件標記為垃圾郵件。這包括符合傳輸規則因此自動標記為垃圾郵件，因而略過所有其他篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-p150">The message was marked as spam prior to being processed by the content filter. This includes messages where the message matched a Transport rule to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="983fa-322">如需不同 SCL 值和其意義的詳細資訊，請參閱[Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx)。</span><span class="sxs-lookup"><span data-stu-id="983fa-322">For more information about the different SCL values and what they mean, see [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`PCL=<number>`|<span data-ttu-id="983fa-p151">網路釣魚信賴等級 (PCL) 值的郵件。這些可以解譯一樣 SCL[垃圾郵件信賴等級](https://technet.microsoft.com/library/jj200686.aspx)中記載的值。</span><span class="sxs-lookup"><span data-stu-id="983fa-p151">The Phishing Confidence Level (PCL) value of the message. These can be interpreted the same way as the SCL values documented in [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`DI=SB`|<span data-ttu-id="983fa-325">已封鎖郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="983fa-325">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="983fa-326">已隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-326">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="983fa-327">已刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-327">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="983fa-328">郵件已傳送給收件者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="983fa-328">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="983fa-p152">郵件已透過較高風險傳遞集區。如需詳細資訊，請參閱 ＜[高風險傳遞集區的外寄郵件](https://technet.microsoft.com/library/jj200746.aspx)。</span><span class="sxs-lookup"><span data-stu-id="983fa-p152">The message was routed through the higher risk delivery pool. For more information, see [High-risk delivery pool for outbound messages](https://technet.microsoft.com/library/jj200746.aspx).</span></span>|
|`DI=SO`|<span data-ttu-id="983fa-331">已透過標準輸出傳遞集區路由傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-331">The message was routed through the normal outbound delivery pool.</span></span>|
|<span data-ttu-id="983fa-332">' SFS = []</span><span class="sxs-lookup"><span data-stu-id="983fa-332">\`SFS=[a]</span></span>|<span data-ttu-id="983fa-333">SFS = [b] '</span><span class="sxs-lookup"><span data-stu-id="983fa-333">SFS=[b]\`</span></span>|<span data-ttu-id="983fa-334">這表示已符合垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="983fa-334">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="983fa-335">因為 IP 位址指定於連線篩選的 [IP 允許] 清單中，所以已透過垃圾郵件篩選允許郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-335">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="983fa-336">連線的電子郵件伺服器的 HELO 或 EHLO 字串。</span><span class="sxs-lookup"><span data-stu-id="983fa-336">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="983fa-337">傳送 IP 位址 (也稱為反向 DNS 位址) 的 PTR 記錄。</span><span class="sxs-lookup"><span data-stu-id="983fa-337">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|

<span data-ttu-id="983fa-338">針對類似的垃圾郵件篩選過的訊息範例**custom_data**值：</span><span class="sxs-lookup"><span data-stu-id="983fa-338">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="983fa-339">惡意程式碼篩選器代理程式</span><span class="sxs-lookup"><span data-stu-id="983fa-339">Malware filter agent</span></span>

<span data-ttu-id="983fa-p153">開頭的**custom_data**值`S:AMA`來自惡意軟體篩選器代理程式。下表說明重要詳細資料：</span><span class="sxs-lookup"><span data-stu-id="983fa-p153">A **custom_data** value that starts with `S:AMA` is from the malware filter agent. The key details are described in the following table:</span></span>

|<span data-ttu-id="983fa-342">**值**</span><span class="sxs-lookup"><span data-stu-id="983fa-342">**Value**</span></span>|<span data-ttu-id="983fa-343">**描述**</span><span class="sxs-lookup"><span data-stu-id="983fa-343">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="983fa-344">' AMA = SUM</span><span class="sxs-lookup"><span data-stu-id="983fa-344">\`AMA=SUM</span></span>|<span data-ttu-id="983fa-345">v = 1</span><span class="sxs-lookup"><span data-stu-id="983fa-345">v=1</span></span>|<span data-ttu-id="983fa-346">` or `AMA = EV</span><span class="sxs-lookup"><span data-stu-id="983fa-346">` or `AMA=EV</span></span>|<span data-ttu-id="983fa-347">v = 1'</span><span class="sxs-lookup"><span data-stu-id="983fa-347">v=1\`</span></span>|<span data-ttu-id="983fa-p154">郵件已決定要包含惡意程式碼。`SUM`指出惡意程式碼可能已偵測到的任意數量的引擎。`EV`會指出特定引擎所偵測到惡意程式碼。當惡意程式碼會偵測引擎這會觸發後續動作。</span><span class="sxs-lookup"><span data-stu-id="983fa-p154">The message was determined to contain malware. `SUM` indicates the malware could've been detected by any number of engines. `EV` indicates the malware was detected by a specific engine. When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="983fa-352">已取代郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-352">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="983fa-353">已略過郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-353">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="983fa-354">已延遲郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-354">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="983fa-355">已刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-355">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="983fa-356">已略過郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-356">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="983fa-357">已略過郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-357">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="983fa-358">已拒絕郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-358">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="983fa-359">已拒絕郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-359">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="983fa-360">已封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="983fa-360">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="983fa-361">偵測到之惡意程式碼的名稱。</span><span class="sxs-lookup"><span data-stu-id="983fa-361">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="983fa-362">含有惡意程式碼之檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="983fa-362">The name of the file that contained the malware.</span></span>|

<span data-ttu-id="983fa-363">郵件包含惡意程式碼範例**custom_data**值看起來如下：</span><span class="sxs-lookup"><span data-stu-id="983fa-363">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="983fa-364">傳輸規則代理程式</span><span class="sxs-lookup"><span data-stu-id="983fa-364">Transport rule agent</span></span>

<span data-ttu-id="983fa-p155">開頭的**custom_data**值`S:TRA`是來自傳輸規則代理程式郵件流程規則 （也稱為傳輸規則）。下表說明重要詳細資料：</span><span class="sxs-lookup"><span data-stu-id="983fa-p155">A **custom_data** value that starts with`S:TRA` is from the transport rule agent for mail flow rules (also known as transport rules). The key details are described in the following table:</span></span>

|<span data-ttu-id="983fa-367">**值**</span><span class="sxs-lookup"><span data-stu-id="983fa-367">**Value**</span></span>|<span data-ttu-id="983fa-368">**描述**</span><span class="sxs-lookup"><span data-stu-id="983fa-368">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="983fa-369">' ETR</span><span class="sxs-lookup"><span data-stu-id="983fa-369">\`ETR</span></span>|<span data-ttu-id="983fa-370">ruleId =<guid>\`</span><span class="sxs-lookup"><span data-stu-id="983fa-370">ruleId=<guid>\`</span></span>|<span data-ttu-id="983fa-371">已符合的規則 ID。</span><span class="sxs-lookup"><span data-stu-id="983fa-371">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="983fa-372">日期和時間 UTC 規則比對發生時。</span><span class="sxs-lookup"><span data-stu-id="983fa-372">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="983fa-p156">所套用的動作。如需可用動作的清單，請參閱[Mail flow 規則動作在 Exchange Online](https://technet.microsoft.com/library/jj919237.aspx)。</span><span class="sxs-lookup"><span data-stu-id="983fa-p156">The action that was applied. For a list of available actions, see [Mail flow rule actions in Exchange Online](https://technet.microsoft.com/library/jj919237.aspx).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="983fa-p157">規則的模式。有效值如下：</span><span class="sxs-lookup"><span data-stu-id="983fa-p157">The mode of the rule. Valid values are: </span></span><br/><span data-ttu-id="983fa-377">• **Enforce**： 將強制執行規則上的所有動作。</span><span class="sxs-lookup"><span data-stu-id="983fa-377">• **Enforce**: All actions on the rule will be enforced.</span></span> <br/><span data-ttu-id="983fa-378">•**搭配原則提示來測試：**： 將會傳送任何 「 原則提示 」 動作，但在應對不到其他強制執行動作。</span><span class="sxs-lookup"><span data-stu-id="983fa-378">• **Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span> <br/><span data-ttu-id="983fa-379">• [**不搭配原則提示的測試**： 動作將會列在記錄檔中，但不是會通知寄件者以任何方法，並在應對不到強制執行動作。</span><span class="sxs-lookup"><span data-stu-id="983fa-379">• **Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span>|

<span data-ttu-id="983fa-380">郵件流程規則的條件會比對範例**custom_data**值的郵件看起來如下：</span><span class="sxs-lookup"><span data-stu-id="983fa-380">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
