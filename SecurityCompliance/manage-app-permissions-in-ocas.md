---
title: 使用 Office 365 雲端 App 安全性管理 OAuth 應用程式
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: Office 365 雲端應用程式安全性的 OAuth 應用程式可協助您管理您的使用者下載 Office 365 資料搭配使用的應用程式
ms.openlocfilehash: 2e3c6d9d42b22aa8bb666211431197744471e84f
ms.sourcegitcommit: 25f72d20e76463c2f0a075dfc0116f00c934bd77
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/27/2018
ms.locfileid: "27447041"
---
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a><span data-ttu-id="b062c-103">使用 Office 365 雲端 App 安全性管理 OAuth 應用程式</span><span class="sxs-lookup"><span data-stu-id="b062c-103">Manage OAuth apps using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="b062c-104">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b062c-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="b062c-105">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b062c-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="b062c-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b062c-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="b062c-107">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="b062c-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="b062c-108">啟動評估</span><span class="sxs-lookup"><span data-stu-id="b062c-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="b062c-109">開始規劃</span><span class="sxs-lookup"><span data-stu-id="b062c-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="b062c-110">開始部署</span><span class="sxs-lookup"><span data-stu-id="b062c-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="b062c-111">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="b062c-111">You are here!</span></span>  <br/> [<span data-ttu-id="b062c-112">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b062c-112">Next steps</span></span>](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="b062c-p101">人員愛應用程式和他們通常下載，特別是人員考慮的應用程式將會使其成為容易取得其工作或學校資訊，以節省時間。不過，某些應用程式可能會對組織的安全性風險，取決於哪些資訊存取該資訊的處理方式。與[Office 365 雲端應用程式安全性](office-365-cas-overview.md)] 如果您是通用範圍或安全性的系統管理員，您可以管理 OAuth 應用程式的組織。您可以看到應用程式的人員使用 Office 365 資料的權限這些應用程式有，等等。</span><span class="sxs-lookup"><span data-stu-id="b062c-p101">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information. However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information. With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage OAuth apps for your organization. You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="b062c-117">本文說明移至 [管理 OAuth 應用程式的位置、 如何核准、 禁止、 或報告應用程式，以及如何建立應用程式的查詢。</span><span class="sxs-lookup"><span data-stu-id="b062c-117">This article describes where to go to manage OAuth apps, how to approve, ban, or report an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a><span data-ttu-id="b062c-118">如何尋找管理 OAuth 應用程式] 頁面</span><span class="sxs-lookup"><span data-stu-id="b062c-118">How to find the Manage OAuth apps page</span></span>

> [!NOTE]
> <span data-ttu-id="b062c-p102">在 Office 365 雲端應用程式安全性入口網站管理 OAuth 應用程式。您必須是全域管理員或安全性管理員可執行下列工作。若要了解更多，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b062c-p102">OAuth apps are managed in the Office 365 Cloud App Security portal. You must be a global administrator or security administrator to perform the following task. To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="b062c-p103">移至 [[https://protection.office.com](https://protection.office.com)及使用 Office 365 工作或學校帳戶登入。(這會引導您安全性&amp;規範中心。)</span><span class="sxs-lookup"><span data-stu-id="b062c-p103">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="b062c-124">移至 [**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="b062c-124">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="b062c-125">按一下 （或點選）**移至 Office 365 雲端應用程式安全性**。</span><span class="sxs-lookup"><span data-stu-id="b062c-125">Click (or tap) **Go to Office 365 Cloud App Security**.</span></span><br/><span data-ttu-id="b062c-126">![安全性&amp;規範中心選擇管理進階警告移至 Office 365 雲端應用程式安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="b062c-126">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br/><span data-ttu-id="b062c-p104">**請注意**： 如果 Office 365 雲端應用程式安全性不會開啟尚未，您就可以執行的動作在此頁面上。請參閱[備妥可供 Office 365 雲端應用程式安全性](get-ready-for-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="b062c-p104">**NOTE**: If Office 365 Cloud App Security is not turned on yet, you can do that on this page. See [Get ready for Office 365 Cloud App Security](get-ready-for-office-365-cas.md).</span></span> 
  
4. <span data-ttu-id="b062c-129">選擇**調查** \> **OAuth 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="b062c-129">Choose **Investigate** \> **OAuth apps**.</span></span><br/><span data-ttu-id="b062c-130">![在 O365 CAS 入口網站中選擇 [調查]。](media/OCAS-OAuthApps.png)</span><span class="sxs-lookup"><span data-stu-id="b062c-130">![In the O365 CAS portal, choose Investigate.](media/OCAS-OAuthApps.png)</span></span><br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a><span data-ttu-id="b062c-131">您會看到管理 OAuth 應用程式] 頁面上</span><span class="sxs-lookup"><span data-stu-id="b062c-131">What you'll see on the Manage OAuth apps page</span></span>

<span data-ttu-id="b062c-132">下表說明管理 OAuth 應用程式] 頁面上的控制項與可用選項。</span><span class="sxs-lookup"><span data-stu-id="b062c-132">The following table describes the controls and options available on the Manage OAuth apps page.</span></span>
  
|<span data-ttu-id="b062c-133">**項目**</span><span class="sxs-lookup"><span data-stu-id="b062c-133">**Item**</span></span>|<span data-ttu-id="b062c-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="b062c-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b062c-135">應用程式查詢列中的基本圖示</span><span class="sxs-lookup"><span data-stu-id="b062c-135">Basic icon in the app query bar</span></span>  <br/> ![會指出查詢的基本查詢檢視的圖示](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="b062c-137">選取這個選項可切換至 [進階檢視。</span><span class="sxs-lookup"><span data-stu-id="b062c-137">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="b062c-138">（如果您看到**基本**，您會使用 [進階] 檢視）</span><span class="sxs-lookup"><span data-stu-id="b062c-138">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="b062c-139">應用程式查詢列中的進階的圖示</span><span class="sxs-lookup"><span data-stu-id="b062c-139">Advanced icon in the app query bar</span></span>  <br/> ![會指出查詢的進階的查詢檢視的圖示](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="b062c-141">選取這個選項可切換至 [基本] 檢視。</span><span class="sxs-lookup"><span data-stu-id="b062c-141">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="b062c-142">（如果您看到**進階**，您會使用 [基本] 檢視）。</span><span class="sxs-lookup"><span data-stu-id="b062c-142">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="b062c-143">開啟或關閉此應用程式清單中的所有詳細資料圖示</span><span class="sxs-lookup"><span data-stu-id="b062c-143">Open or close all details icon in the app list</span></span>  <br/> ![按一下此圖示來開啟或關閉所有應用程式的所有詳細資料](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="b062c-145">選取此圖示來檢視每個應用程式的更多或更少詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b062c-145">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="b062c-146">匯出應用程式清單中的圖示</span><span class="sxs-lookup"><span data-stu-id="b062c-146">Export icon in the app list</span></span>  <br/> ![按一下此圖示來匯出 csv 檔案的所有應用程式](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="b062c-148">選取此圖示來匯出 CSV 檔案包含應用程式] 的使用者的每個應用程式相關聯的應用程式、 權限層級、 應用程式狀態和社群使用層級的權限的清單。</span><span class="sxs-lookup"><span data-stu-id="b062c-148">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="b062c-149">名稱</span><span class="sxs-lookup"><span data-stu-id="b062c-149">Name</span></span>  <br/> |<span data-ttu-id="b062c-p105">使用此看到的名稱 app 選取来檢視詳細資訊，例如其描述、 publisher、 應用程式網站與應用程式識別碼的名稱</span><span class="sxs-lookup"><span data-stu-id="b062c-p105">Use this to see the name of an app. Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="b062c-152">依授權</span><span class="sxs-lookup"><span data-stu-id="b062c-152">Authorized by</span></span>  <br/> |<span data-ttu-id="b062c-p106">使用此檢視多少使用者已獲得授權的應用程式以存取其 Office 365 帳戶。選取要檢視的使用者帳戶清單等的詳細資訊的數字。</span><span class="sxs-lookup"><span data-stu-id="b062c-p106">Use this to see how many users have authorized an app to access their Office 365 account. Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="b062c-155">權限層級</span><span class="sxs-lookup"><span data-stu-id="b062c-155">Permissions Level</span></span>  <br/> ![會指出應用程式的 permisiions 層級的圖示](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="b062c-p107">使用此請參閱 Office 365 資料有多少的應用程式的存取。權限層級指出**Low**、 **Medium**或**High**、 **Low**可能表示應用程式只能存取使用者設定檔和名稱。選取應用程式、 社群使用及相關的活動[控管記錄檔](suspend-or-restore-an-account-in-ocas.md)中授與檢視詳細資訊，例如權限層級。</span><span class="sxs-lookup"><span data-stu-id="b062c-p107">Use this to see how much access an app has to Office 365 data. Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name. Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).  </span></span><br/> |
|<span data-ttu-id="b062c-160">上一次授權</span><span class="sxs-lookup"><span data-stu-id="b062c-160">Last authorized</span></span> <br/> |<span data-ttu-id="b062c-161">使用此檢視的日期和時間 OAuth 應用程式上一次已授權存取您的組織的 Office 365 資料。</span><span class="sxs-lookup"><span data-stu-id="b062c-161">Use this to see the date and time an OAuth app was last authorized to access your organization's Office 365 data.</span></span> <br/>  |
|<span data-ttu-id="b062c-162">動作</span><span class="sxs-lookup"><span data-stu-id="b062c-162">Actions</span></span><br/>![OAuth 應用程式](media/OCAS-OAuthAppApproveBanReport.png)<br/> |<span data-ttu-id="b062c-164">使用此查看或，將應用程式標示為已核准 」 或 「 Banned、 OAuth 應用程式的向 Microsoft、 報告或離開作為源自。</span><span class="sxs-lookup"><span data-stu-id="b062c-164">Use this to see or to mark an app as Approved or Banned, report an OAuth app to Microsoft, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="b062c-165">標記為已核准的應用程式</span><span class="sxs-lookup"><span data-stu-id="b062c-165">Mark an app as approved</span></span>

<span data-ttu-id="b062c-166">在 [**管理 OAuth 應用程式**] 頁面上找出您想要核准的應用程式並選擇**做為 Mark app 核准**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="b062c-166">On the **Manage OAuth apps** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![選擇標記應用程式已核准的圖示](media/OCAS-MarkOAuthApproved.png)
  
<span data-ttu-id="b062c-168">圖示會開啟綠色和應用程式為您所有的 Office 365 使用者的 「 已核准。</span><span class="sxs-lookup"><span data-stu-id="b062c-168">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b062c-p108">當您將應用程式標示為已核准時，有不會影響使用者。以視覺方式標示核准的應用程式可協助隔開尚未尚未檢閱的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b062c-p108">When you mark an app as approved, there is no effect on the end user. Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="b062c-171">禁止應用程式</span><span class="sxs-lookup"><span data-stu-id="b062c-171">Ban an app</span></span>

1. <span data-ttu-id="b062c-172">在 [**管理 OAuth 應用程式**] 頁面上找出您要禁止、 應用的程式並選擇**做為 Mark app 禁用**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="b062c-172">On the **Manage OAuth apps** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span><br/><span data-ttu-id="b062c-173">![選擇標記 app 禁用的圖示](media/OCAS-MarkOAuthBanned.png)</span><span class="sxs-lookup"><span data-stu-id="b062c-173">![Choose the Mark app as banned icon](media/OCAS-MarkOAuthBanned.png)</span></span>
  
2. <span data-ttu-id="b062c-p109">通知訊息] 方塊中，保持現有的文字或自訂的文字。選擇是否要讓使用者知道已禁用其應用程式。</span><span class="sxs-lookup"><span data-stu-id="b062c-p109">In the notification message box, keep the existing text as it is, or customize the text. Choose whether to let users know that their app has been banned.</span></span> <br/>![禁用的應用程式的 [郵件] 範本](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. <span data-ttu-id="b062c-177">選擇 [**禁止應用程式**。</span><span class="sxs-lookup"><span data-stu-id="b062c-177">Choose **Ban app**.</span></span>

## <a name="report-an-oauth-app-to-microsoft"></a><span data-ttu-id="b062c-178">向 Microsoft 報告 OAuth 應用程式</span><span class="sxs-lookup"><span data-stu-id="b062c-178">Report an OAuth app to Microsoft</span></span>

<span data-ttu-id="b062c-179">如果您想要提交給 Microsoft 進行分析 OAuth 應用程式，您可以報告該應用程式。</span><span class="sxs-lookup"><span data-stu-id="b062c-179">If you want to submit an OAuth app to Microsoft for analysis, you can report that app.</span></span>

1. <span data-ttu-id="b062c-180">在 [**管理 OAuth 應用程式**] 頁面上找出您想要送出進行分析的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b062c-180">On the **Manage OAuth apps** page, locate the app you want to submit for analysis.</span></span>

2. <span data-ttu-id="b062c-181">選擇的垂直的省略符號，然後選擇**報表 app。。 {3}**。</span><span class="sxs-lookup"><span data-stu-id="b062c-181">Choose the vertical ellipsis, and then choose **Report app...**.</span></span><br/><span data-ttu-id="b062c-182">![報告 OAuth 應用程式](media/OCAS-MarkOAuthReported.png)</span><span class="sxs-lookup"><span data-stu-id="b062c-182">![Report an OAuth app](media/OCAS-MarkOAuthReported.png)</span></span><br/>

3. <span data-ttu-id="b062c-p110">在 [**報告此應用程式**] 對話方塊中，使用下拉式清單以指出您擔心。根據預設，會選取**此應用程式是惡意**。不過，您可以選擇其中一個可用的選項。</span><span class="sxs-lookup"><span data-stu-id="b062c-p110">In the **Report this app** dialog box, use the drop-down list to indicate your concern. By default, **This app is malicious** is selected. However, you can choose on one of the other available options. </span></span><br/><span data-ttu-id="b062c-186">![報告 OAuth 應用程式](media/OCAS-ReportOAuthApp.png)</span><span class="sxs-lookup"><span data-stu-id="b062c-186">![Report an OAuth app](media/OCAS-ReportOAuthApp.png)</span></span><br/>

4. <span data-ttu-id="b062c-187">（建議）請連絡您選取的選項，並確認 （或編輯） 所列的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b062c-187">(Recommended) Keep the option to contact you selected, and confirm (or edit) the email address listed.</span></span>

5. <span data-ttu-id="b062c-188">選擇 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="b062c-188">Choose **Submit**.</span></span> 
    
## <a name="create-an-app-query"></a><span data-ttu-id="b062c-189">建立應用程式的查詢</span><span class="sxs-lookup"><span data-stu-id="b062c-189">Create an app query</span></span>

<span data-ttu-id="b062c-190">我們建議使用進階的檢視中，看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="b062c-190">We recommend using the Advanced view, which looks like this:</span></span> 

![進階的檢視](media/OCAS-OAuthAppsAdvQueryView.png)

<span data-ttu-id="b062c-p111">在應用程式查詢列中，如果您看到 [**進階**]，您使用 [基本] 檢視。按一下 （或點選）**進階**移至 [進階] 檢視。</span><span class="sxs-lookup"><span data-stu-id="b062c-p111">In the app query bar, if you see **Advanced**, you're using the Basic view. Click (or tap) **Advanced** to go to the Advanced view.</span></span> 

![基本檢視](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. <span data-ttu-id="b062c-195">在 [查詢] 列中使用 [**選取篩選**] 清單選擇選項。</span><span class="sxs-lookup"><span data-stu-id="b062c-195">In the query bar, use the **Select a filter** list to choose an option.</span></span> 
    - <span data-ttu-id="b062c-196">**應用程式**應用程式特定的名稱</span><span class="sxs-lookup"><span data-stu-id="b062c-196">**App** Apps with certain names</span></span>
    - <span data-ttu-id="b062c-197">**應用程式狀態**根據其狀態 （已核准、 Banned 或 Undetermined） 的應用程式</span><span class="sxs-lookup"><span data-stu-id="b062c-197">**App state** Apps based on their state (Approved, Banned, or Undetermined)</span></span>
    - <span data-ttu-id="b062c-198">**使用社群**社群為基礎的應用程式使用層級 （Rare、 Uncommon、 或一般）</span><span class="sxs-lookup"><span data-stu-id="b062c-198">**Community use** Apps based on community use levels (Rare, Uncommon, or Common)</span></span>
    - <span data-ttu-id="b062c-199">**權限層級**某些權限層級為基礎的應用程式</span><span class="sxs-lookup"><span data-stu-id="b062c-199">**Permission level** Apps based on certain permission levels</span></span> 
    - <span data-ttu-id="b062c-200">**權限**需要特定的權限的應用程式</span><span class="sxs-lookup"><span data-stu-id="b062c-200">**Permissions** Apps that require certain permissions</span></span>
    - <span data-ttu-id="b062c-201">**發行者** 從特定發行者的應用程式</span><span class="sxs-lookup"><span data-stu-id="b062c-201">**Publisher**  Apps from certain publishers</span></span>
    - <span data-ttu-id="b062c-202">**使用者**某些使用者授權的應用程式</span><span class="sxs-lookup"><span data-stu-id="b062c-202">**User** Apps that a certain user authorized</span></span>
   
2. <span data-ttu-id="b062c-203">選取 [**等於**] 或 [**不等於**，並接著指定篩選的值。</span><span class="sxs-lookup"><span data-stu-id="b062c-203">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
3. <span data-ttu-id="b062c-204">若要新增更多的篩選器，請選取 [加號 （</span><span class="sxs-lookup"><span data-stu-id="b062c-204">To add more filters, select the plus sign (</span></span>![新增查詢應用程式的篩選圖示](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="b062c-206">)，然後重複步驟 2 和 3。</span><span class="sxs-lookup"><span data-stu-id="b062c-206">), and then repeat steps 2 and 3.</span></span>
    
4. <span data-ttu-id="b062c-207">若要移除篩選，請選取 [x (</span><span class="sxs-lookup"><span data-stu-id="b062c-207">To remove a filter, select the x (</span></span>![移除查詢應用程式的篩選圖示](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="b062c-209">) 旁的篩選器名稱。</span><span class="sxs-lookup"><span data-stu-id="b062c-209">) next to a filter name.</span></span>
    
<span data-ttu-id="b062c-210">自動套用篩選器與據以更新的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="b062c-210">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="b062c-211">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b062c-211">Next steps</span></span>

- [<span data-ttu-id="b062c-212">檢閱並採取行動提醒</span><span class="sxs-lookup"><span data-stu-id="b062c-212">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="b062c-213">檢閱您的[網頁流量記錄檔與資料來源為 Office 365 雲端應用程式安全性](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="b062c-213">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="b062c-214">檢閱您[的 Office 365 雲端應用程式安全性使用率活動](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="b062c-214">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

