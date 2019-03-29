---
title: 使用 Office 365 雲端 App 安全性管理 OAuth 應用程式
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: Office 365 雲端 App 安全性中的 OAuth 應用程式可協助您管理您的使用者下載 Office 365 資料搭配使用的應用程式
ms.openlocfilehash: 0d9916414d55abb73fd99eaf30c3b6df0648b191
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862585"
---
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a><span data-ttu-id="1bb43-103">使用 Office 365 雲端 App 安全性管理 OAuth 應用程式</span><span class="sxs-lookup"><span data-stu-id="1bb43-103">Manage OAuth apps using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="1bb43-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1bb43-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="1bb43-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1bb43-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="1bb43-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1bb43-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="1bb43-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="1bb43-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="1bb43-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="1bb43-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="1bb43-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="1bb43-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="1bb43-110">開始部署</span><span class="sxs-lookup"><span data-stu-id="1bb43-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="1bb43-111">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="1bb43-111">You are here!</span></span>  <br/> [<span data-ttu-id="1bb43-112">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1bb43-112">Next steps</span></span>](#next-steps)<br/> |
   
<span data-ttu-id="1bb43-113">人員愛應用程式和其通常下載它們，尤其是人員考慮的應用程式將會使其成為容易取得在他們的公司或學校資訊以節省時間。</span><span class="sxs-lookup"><span data-stu-id="1bb43-113">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information.</span></span> <span data-ttu-id="1bb43-114">不過，某些應用程式可能有貴組織的安全性風險，哪些資訊為基礎，這取決於使用者存取，以及該資訊的處理方式。</span><span class="sxs-lookup"><span data-stu-id="1bb43-114">However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information.</span></span> <span data-ttu-id="1bb43-115">使用[Office 365 雲端 App 安全性](office-365-cas-overview.md)，如果您是全域或安全性系統管理員，您可以管理 OAuth 應用程式為您的組織。</span><span class="sxs-lookup"><span data-stu-id="1bb43-115">With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage OAuth apps for your organization.</span></span> <span data-ttu-id="1bb43-116">您可以看到應用程式的人員會使用與 Office 365 資料有何權限那些 sharepoint 應用程式，等等。</span><span class="sxs-lookup"><span data-stu-id="1bb43-116">You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="1bb43-117">本文說明移至管理 OAuth 應用程式的位置、 如何核准、 禁止，或報告應用程式，以及如何建立應用程式的查詢。</span><span class="sxs-lookup"><span data-stu-id="1bb43-117">This article describes where to go to manage OAuth apps, how to approve, ban, or report an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a><span data-ttu-id="1bb43-118">如何找出管理 OAuth 應用程式] 頁面</span><span class="sxs-lookup"><span data-stu-id="1bb43-118">How to find the Manage OAuth apps page</span></span>

> [!NOTE]
> <span data-ttu-id="1bb43-119">在 Office 365 雲端 App 安全性入口網站中管理 OAuth 應用程式。</span><span class="sxs-lookup"><span data-stu-id="1bb43-119">OAuth apps are managed in the Office 365 Cloud App Security portal.</span></span> <span data-ttu-id="1bb43-120">您必須是全域系統管理員或安全性系統管理員可執行下列工作。</span><span class="sxs-lookup"><span data-stu-id="1bb43-120">You must be a global administrator or security administrator to perform the following task.</span></span> <span data-ttu-id="1bb43-121">若要了解更多，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1bb43-121">To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="1bb43-122">移至 Cloud App Security 入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，並登入。</span><span class="sxs-lookup"><span data-stu-id="1bb43-122">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="1bb43-123">選擇 [**調查** \> **OAuth 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="1bb43-123">Choose **Investigate** \> **OAuth apps**.</span></span><br/><span data-ttu-id="1bb43-124">![在 O365 CAS 入口網站中，選擇 [調查]。](media/OCAS-OAuthApps.png)</span><span class="sxs-lookup"><span data-stu-id="1bb43-124">![In the O365 CAS portal, choose Investigate.](media/OCAS-OAuthApps.png)</span></span><br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a><span data-ttu-id="1bb43-125">您會看到在管理 OAuth 應用程式] 頁面</span><span class="sxs-lookup"><span data-stu-id="1bb43-125">What you'll see on the Manage OAuth apps page</span></span>

<span data-ttu-id="1bb43-126">下表說明在管理 OAuth 應用程式] 頁面上的控制項和可用的選項。</span><span class="sxs-lookup"><span data-stu-id="1bb43-126">The following table describes the controls and options available on the Manage OAuth apps page.</span></span>
  
|<span data-ttu-id="1bb43-127">**項目**</span><span class="sxs-lookup"><span data-stu-id="1bb43-127">**Item**</span></span>|<span data-ttu-id="1bb43-128">**描述**</span><span class="sxs-lookup"><span data-stu-id="1bb43-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1bb43-129">在 [應用程式查詢列中的基本圖示</span><span class="sxs-lookup"><span data-stu-id="1bb43-129">Basic icon in the app query bar</span></span>  <br/> ![會指出查詢的基本查詢檢視的圖示](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="1bb43-131">選取這個選項可切換至 [進階檢視。</span><span class="sxs-lookup"><span data-stu-id="1bb43-131">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="1bb43-132">（如果您看到**基本**，您正在使用的進階的檢視）</span><span class="sxs-lookup"><span data-stu-id="1bb43-132">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="1bb43-133">在 [應用程式查詢列中的進階的圖示</span><span class="sxs-lookup"><span data-stu-id="1bb43-133">Advanced icon in the app query bar</span></span>  <br/> ![會指出查詢的進階的查詢檢視的圖示](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="1bb43-135">選取這個選項可切換到 [基本] 檢視。</span><span class="sxs-lookup"><span data-stu-id="1bb43-135">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="1bb43-136">（如果您看到**進階**，您正在使用基本檢視）。</span><span class="sxs-lookup"><span data-stu-id="1bb43-136">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="1bb43-137">開啟或關閉應用程式清單中的所有詳細資料圖示</span><span class="sxs-lookup"><span data-stu-id="1bb43-137">Open or close all details icon in the app list</span></span>  <br/> ![按一下此圖示來開啟或關閉的所有應用程式的所有詳細資料](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="1bb43-139">選取 [此圖示來檢視每個應用程式的更多或較少詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="1bb43-139">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="1bb43-140">在應用程式清單中的匯出圖示</span><span class="sxs-lookup"><span data-stu-id="1bb43-140">Export icon in the app list</span></span>  <br/> ![按一下此圖示來匯出 csv 檔案的所有應用程式](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="1bb43-142">選取此圖示來匯出 CSV 檔案包含清單中的應用程式，每個應用程式，應用程式的權限層級、 應用程式的狀態，相關聯的權限的使用者數目和社群使用層級。</span><span class="sxs-lookup"><span data-stu-id="1bb43-142">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="1bb43-143">名稱</span><span class="sxs-lookup"><span data-stu-id="1bb43-143">Name</span></span>  <br/> |<span data-ttu-id="1bb43-144">使用此功能來查看應用程式的名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb43-144">Use this to see the name of an app.</span></span> <span data-ttu-id="1bb43-145">選取要檢視詳細資訊，例如其說明、 publisher、 應用程式網站和應用程式識別碼的名稱</span><span class="sxs-lookup"><span data-stu-id="1bb43-145">Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="1bb43-146">由授權</span><span class="sxs-lookup"><span data-stu-id="1bb43-146">Authorized by</span></span>  <br/> |<span data-ttu-id="1bb43-147">使用此功能來查看多少使用者已獲授權的應用程式，才能存取其 Office 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="1bb43-147">Use this to see how many users have authorized an app to access their Office 365 account.</span></span> <span data-ttu-id="1bb43-148">選取要檢視詳細資訊，例如清單中的使用者帳戶的數字。</span><span class="sxs-lookup"><span data-stu-id="1bb43-148">Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="1bb43-149">權限層級</span><span class="sxs-lookup"><span data-stu-id="1bb43-149">Permissions Level</span></span>  <br/> ![會指出應用程式的 permisiions 層級的圖示](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="1bb43-151">使用此功能來查看 Office 365 資料有多少的應用程式的存取。</span><span class="sxs-lookup"><span data-stu-id="1bb43-151">Use this to see how much access an app has to Office 365 data.</span></span> <span data-ttu-id="1bb43-152">權限層級指出**低**、 **Medium**或**High**、 **Low**可能表示應用程式只能存取使用者設定檔與名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb43-152">Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name.</span></span> <span data-ttu-id="1bb43-153">選取 [檢視詳細資訊，例如權限授與應用程式、 社群使用和[管理記錄](suspend-or-restore-an-account-in-ocas.md)的相關的活動的層級。</span><span class="sxs-lookup"><span data-stu-id="1bb43-153">Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).</span></span>  <br/> |
|<span data-ttu-id="1bb43-154">上次授權</span><span class="sxs-lookup"><span data-stu-id="1bb43-154">Last authorized</span></span> <br/> |<span data-ttu-id="1bb43-155">使用此功能來查看的日期和時間 OAuth 應用程式已上次存取權限貴組織的 Office 365 資料。</span><span class="sxs-lookup"><span data-stu-id="1bb43-155">Use this to see the date and time an OAuth app was last authorized to access your organization's Office 365 data.</span></span> <br/>  |
|<span data-ttu-id="1bb43-156">動作</span><span class="sxs-lookup"><span data-stu-id="1bb43-156">Actions</span></span><br/>![OAuth 應用程式](media/OCAS-OAuthAppApproveBanReport.png)<br/> |<span data-ttu-id="1bb43-158">使用此功能來查看或將應用程式標示為已核准 」 或 「 Banned，OAuth 應用程式向 Microsoft 報告以，或保留為未定。</span><span class="sxs-lookup"><span data-stu-id="1bb43-158">Use this to see or to mark an app as Approved or Banned, report an OAuth app to Microsoft, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="1bb43-159">將應用程式標示為已核准</span><span class="sxs-lookup"><span data-stu-id="1bb43-159">Mark an app as approved</span></span>

<span data-ttu-id="1bb43-160">在 [**管理 OAuth 應用程式**] 頁面上，找出您想要核准的應用程式，選擇 [**標記應用程式作為核准**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="1bb43-160">On the **Manage OAuth apps** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![選擇 [標記應用程式以核准圖示](media/OCAS-MarkOAuthApproved.png)
  
<span data-ttu-id="1bb43-162">圖示會變成綠色，和所有 Office 365 使用者的核准應用程式。</span><span class="sxs-lookup"><span data-stu-id="1bb43-162">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1bb43-163">當您將應用程式標示為核准時，就會對使用者造成任何影響。</span><span class="sxs-lookup"><span data-stu-id="1bb43-163">When you mark an app as approved, there is no effect on the end user.</span></span> <span data-ttu-id="1bb43-164">以視覺方式將標示要核准的應用程式，可以幫助隔開尚未尚未檢閱的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1bb43-164">Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="1bb43-165">禁止使用應用程式</span><span class="sxs-lookup"><span data-stu-id="1bb43-165">Ban an app</span></span>

1. <span data-ttu-id="1bb43-166">在**管理 OAuth 應用程式**] 頁面上，找出您要禁止，應用的程式，選擇 [**為標記應用程式禁止**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="1bb43-166">On the **Manage OAuth apps** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span><br/><span data-ttu-id="1bb43-167">![選擇 [標記應用程式以禁用圖示](media/OCAS-MarkOAuthBanned.png)</span><span class="sxs-lookup"><span data-stu-id="1bb43-167">![Choose the Mark app as banned icon](media/OCAS-MarkOAuthBanned.png)</span></span>
  
2. <span data-ttu-id="1bb43-168">通知訊息方塊中，保留現有的文字為是，或自訂的文字。</span><span class="sxs-lookup"><span data-stu-id="1bb43-168">In the notification message box, keep the existing text as it is, or customize the text.</span></span> <span data-ttu-id="1bb43-169">選擇是否要讓使用者知道，其 app 郵件已遭禁止。</span><span class="sxs-lookup"><span data-stu-id="1bb43-169">Choose whether to let users know that their app has been banned.</span></span> <br/>![禁用的應用程式的 [郵件] 範本](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. <span data-ttu-id="1bb43-171">選擇 [**郵件應用程式**。</span><span class="sxs-lookup"><span data-stu-id="1bb43-171">Choose **Ban app**.</span></span>

## <a name="report-an-oauth-app-to-microsoft"></a><span data-ttu-id="1bb43-172">向 Microsoft 報告 OAuth 應用程式</span><span class="sxs-lookup"><span data-stu-id="1bb43-172">Report an OAuth app to Microsoft</span></span>

<span data-ttu-id="1bb43-173">如果您想要提交給 Microsoft 進行分析 OAuth 應用程式，您可以報告該應用程式。</span><span class="sxs-lookup"><span data-stu-id="1bb43-173">If you want to submit an OAuth app to Microsoft for analysis, you can report that app.</span></span>

1. <span data-ttu-id="1bb43-174">在 [**管理 OAuth 應用程式**] 頁面上，找出您想要提交進行分析的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1bb43-174">On the **Manage OAuth apps** page, locate the app you want to submit for analysis.</span></span>

2. <span data-ttu-id="1bb43-175">選擇 [垂直的省略符號，，然後選擇**報表 app..**。</span><span class="sxs-lookup"><span data-stu-id="1bb43-175">Choose the vertical ellipsis, and then choose **Report app...**.</span></span><br/><span data-ttu-id="1bb43-176">![報告 OAuth 應用程式](media/OCAS-MarkOAuthReported.png)</span><span class="sxs-lookup"><span data-stu-id="1bb43-176">![Report an OAuth app](media/OCAS-MarkOAuthReported.png)</span></span><br/>

3. <span data-ttu-id="1bb43-177">在 [**報告此應用程式**] 對話方塊中，使用下拉式清單來表示您的考量。</span><span class="sxs-lookup"><span data-stu-id="1bb43-177">In the **Report this app** dialog box, use the drop-down list to indicate your concern.</span></span> <span data-ttu-id="1bb43-178">根據預設，會選取**此應用程式是惡意**。</span><span class="sxs-lookup"><span data-stu-id="1bb43-178">By default, **This app is malicious** is selected.</span></span> <span data-ttu-id="1bb43-179">不過，您可以選擇在其中一個其他可用的選項。</span><span class="sxs-lookup"><span data-stu-id="1bb43-179">However, you can choose on one of the other available options.</span></span> <br/><span data-ttu-id="1bb43-180">![報告 OAuth 應用程式](media/OCAS-ReportOAuthApp.png)</span><span class="sxs-lookup"><span data-stu-id="1bb43-180">![Report an OAuth app](media/OCAS-ReportOAuthApp.png)</span></span><br/>

4. <span data-ttu-id="1bb43-181">（建議使用）保留選項，可連絡您選取，並確認 （或編輯） 所列的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1bb43-181">(Recommended) Keep the option to contact you selected, and confirm (or edit) the email address listed.</span></span>

5. <span data-ttu-id="1bb43-182">Choose **Submit**.</span><span class="sxs-lookup"><span data-stu-id="1bb43-182">Choose **Submit**.</span></span> 
    
## <a name="create-an-app-query"></a><span data-ttu-id="1bb43-183">建立應用程式的查詢</span><span class="sxs-lookup"><span data-stu-id="1bb43-183">Create an app query</span></span>

<span data-ttu-id="1bb43-184">我們建議使用進階的檢視中，看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="1bb43-184">We recommend using the Advanced view, which looks like this:</span></span> 

![進階的檢視](media/OCAS-OAuthAppsAdvQueryView.png)

<span data-ttu-id="1bb43-186">在應用程式查詢列中，如果您看到 [**進階**]，您正在使用基本的檢視。</span><span class="sxs-lookup"><span data-stu-id="1bb43-186">In the app query bar, if you see **Advanced**, you're using the Basic view.</span></span> <span data-ttu-id="1bb43-187">按一下 （或點選） [**進階**]，以移至 [進階檢視。</span><span class="sxs-lookup"><span data-stu-id="1bb43-187">Click (or tap) **Advanced** to go to the Advanced view.</span></span> 

![基本檢視](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. <span data-ttu-id="1bb43-189">在 [查詢] 列中，使用**選取篩選器**清單中選擇一個選項。</span><span class="sxs-lookup"><span data-stu-id="1bb43-189">In the query bar, use the **Select a filter** list to choose an option.</span></span> 
    - <span data-ttu-id="1bb43-190">**應用程式**具有特定名稱的應用程式</span><span class="sxs-lookup"><span data-stu-id="1bb43-190">**App** Apps with certain names</span></span>
    - <span data-ttu-id="1bb43-191">**應用程式狀態**根據其狀態 （已核准、 Banned 或 「 未定 」） 的應用程式</span><span class="sxs-lookup"><span data-stu-id="1bb43-191">**App state** Apps based on their state (Approved, Banned, or Undetermined)</span></span>
    - <span data-ttu-id="1bb43-192">**使用社群**社群為基礎的應用程式使用層級 （Rare、 Uncommon 或一般）</span><span class="sxs-lookup"><span data-stu-id="1bb43-192">**Community use** Apps based on community use levels (Rare, Uncommon, or Common)</span></span>
    - <span data-ttu-id="1bb43-193">**權限等級**根據特定權限層級的應用程式</span><span class="sxs-lookup"><span data-stu-id="1bb43-193">**Permission level** Apps based on certain permission levels</span></span> 
    - <span data-ttu-id="1bb43-194">**權限**需要特定權限的應用程式</span><span class="sxs-lookup"><span data-stu-id="1bb43-194">**Permissions** Apps that require certain permissions</span></span>
    - <span data-ttu-id="1bb43-195">**發行者** 來自特定發行者應用程式</span><span class="sxs-lookup"><span data-stu-id="1bb43-195">**Publisher**  Apps from certain publishers</span></span>
    - <span data-ttu-id="1bb43-196">**使用者**特定使用者的權限的應用程式</span><span class="sxs-lookup"><span data-stu-id="1bb43-196">**User** Apps that a certain user authorized</span></span>
   
2. <span data-ttu-id="1bb43-197">選取 [**等於**] 或 [**不等於**，，，然後指定篩選的值。</span><span class="sxs-lookup"><span data-stu-id="1bb43-197">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
3. <span data-ttu-id="1bb43-198">若要新增更多篩選器，請選取加上加號 （</span><span class="sxs-lookup"><span data-stu-id="1bb43-198">To add more filters, select the plus sign (</span></span>![新增查詢應用程式的篩選器圖示](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="1bb43-200">)，然後重複步驟 2 和 3。</span><span class="sxs-lookup"><span data-stu-id="1bb43-200">), and then repeat steps 2 and 3.</span></span>
    
4. <span data-ttu-id="1bb43-201">若要移除篩選，請選取 [x (</span><span class="sxs-lookup"><span data-stu-id="1bb43-201">To remove a filter, select the x (</span></span>![移除查詢應用程式的篩選器圖示](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="1bb43-203">) 旁的篩選器名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb43-203">) next to a filter name.</span></span>
    
<span data-ttu-id="1bb43-204">自動套用篩選器，並據此更新應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="1bb43-204">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="1bb43-205">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1bb43-205">Next steps</span></span>

- [<span data-ttu-id="1bb43-206">檢閱並採取相應動作提醒</span><span class="sxs-lookup"><span data-stu-id="1bb43-206">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="1bb43-207">檢閱您的[Web 流量記錄及資料來源的 Office 365 雲端 App 安全性](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="1bb43-207">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="1bb43-208">檢閱您[的 Office 365 雲端 App 安全性的使用率活動](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="1bb43-208">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

