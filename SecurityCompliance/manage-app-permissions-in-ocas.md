---
title: 使用 Office 365 雲端 App 安全性管理 App 權限
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: Office 365 雲端應用程式安全性的應用程式權限可協助您管理您的使用者下載 Office 365 資料搭配使用的應用程式
ms.openlocfilehash: 7bda35bbbf3a16cd1d386adcb03b1c7c4176913a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527144"
---
# <a name="manage-app-permissions-using-office-365-cloud-app-security"></a><span data-ttu-id="d581b-103">使用 Office 365 雲端 App 安全性管理 App 權限</span><span class="sxs-lookup"><span data-stu-id="d581b-103">Manage app permissions using Office 365 Cloud App Security</span></span>

<span data-ttu-id="d581b-104">Office 365 進階安全性管理現在是 Office 365 雲端應用程式安全性。</span><span class="sxs-lookup"><span data-stu-id="d581b-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="d581b-105">評估 * *\>**</span><span class="sxs-lookup"><span data-stu-id="d581b-105">****Evaluation** \>**</span></span>|<span data-ttu-id="d581b-106">規劃 * *\>**</span><span class="sxs-lookup"><span data-stu-id="d581b-106">****Planning** \>**</span></span>|<span data-ttu-id="d581b-107">部署 * *\>**</span><span class="sxs-lookup"><span data-stu-id="d581b-107">****Deployment** \>**</span></span>|<span data-ttu-id="d581b-108">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="d581b-108">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="d581b-109">啟動評估</span><span class="sxs-lookup"><span data-stu-id="d581b-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="d581b-110">開始規劃</span><span class="sxs-lookup"><span data-stu-id="d581b-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="d581b-111">開始部署</span><span class="sxs-lookup"><span data-stu-id="d581b-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="d581b-112">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="d581b-112">You are here!</span></span>  <br/> [<span data-ttu-id="d581b-113">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d581b-113">Next steps</span></span>](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="d581b-p101">人員愛應用程式和他們通常下載，特別是人員考慮的應用程式將會使其成為容易取得其工作或學校資訊，以節省時間。不過，某些應用程式可能會對組織的安全性風險，取決於哪些資訊存取該資訊的處理方式。與[Office 365 雲端應用程式安全性](office-365-cas-overview.md)]，如果您是通用範圍或安全性的系統管理員，您可以管理應用程式權限您的組織。您可以看到應用程式的人員使用 Office 365 資料的權限這些應用程式有，等等。</span><span class="sxs-lookup"><span data-stu-id="d581b-p101">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information. However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information. With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage app permissions for your organization. You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="d581b-118">本文說明移至 [管理應用程式的權限的位置、 如何核准或禁止應用程式，以及如何建立應用程式的查詢。</span><span class="sxs-lookup"><span data-stu-id="d581b-118">This article describes where to go to manage app permissions, how to approve or ban an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-app-permissions-page"></a><span data-ttu-id="d581b-119">尋找 [管理應用程式的權限] 頁面上的方法</span><span class="sxs-lookup"><span data-stu-id="d581b-119">How to find the Manage app permissions page</span></span>
<span data-ttu-id="d581b-120"><a name="findappperms"> </a></span><span class="sxs-lookup"><span data-stu-id="d581b-120"></span></span>

> [!NOTE]
> <span data-ttu-id="d581b-p102">在 Office 365 雲端應用程式安全性入口網站中管理應用程式權限。您必須是全域管理員或安全性管理員可執行下列工作。若要了解更多，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="d581b-p102">App permissions are managed in the Office 365 Cloud App Security portal. You must be a global administrator or security administrator to perform the following task. To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="d581b-p103">移至 [[https://protection.office.com](https://protection.office.com)及使用 Office 365 工作或學校帳戶登入。(這會引導您安全性&amp;規範中心。)</span><span class="sxs-lookup"><span data-stu-id="d581b-p103">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="d581b-126">移至 [**提醒** \> **管理進階提醒**。</span><span class="sxs-lookup"><span data-stu-id="d581b-126">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="d581b-127">按一下 （或點選）**移至 Office 365 雲端應用程式安全性**。</span><span class="sxs-lookup"><span data-stu-id="d581b-127">Click (or tap) **Go to Office 365 Cloud App Security**.</span></span>
    
    ![安全性&amp;規範中心選擇管理進階警告移至 Office 365 雲端應用程式安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    > [!NOTE]
    > <span data-ttu-id="d581b-p104">如果 Office 365 雲端應用程式安全性不會開啟尚未，您可以執行的動作在此頁面上。請參閱[備妥可供 Office 365 雲端應用程式安全性](get-ready-for-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="d581b-p104">If Office 365 Cloud App Security is not turned on yet, you can do that on this page. See [Get ready for Office 365 Cloud App Security](get-ready-for-office-365-cas.md).</span></span> 
  
4. <span data-ttu-id="d581b-131">選擇**調查** \> **應用程式權限**。</span><span class="sxs-lookup"><span data-stu-id="d581b-131">Choose **Investigate** \> **App permissions**.</span></span>
    
    ![在 O365 CAS 入口網站中選擇 [調查]。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
## <a name="what-youll-see-on-the-manage-app-permissions-page"></a><span data-ttu-id="d581b-133">您會看到 [管理應用程式的權限] 頁面上</span><span class="sxs-lookup"><span data-stu-id="d581b-133">What you'll see on the Manage app permissions page</span></span>
<span data-ttu-id="d581b-134"><a name="whatsonpage"> </a></span><span class="sxs-lookup"><span data-stu-id="d581b-134"></span></span>

<span data-ttu-id="d581b-135">下表說明管理應用程式的權限] 頁面上的控制項和可用的選項。</span><span class="sxs-lookup"><span data-stu-id="d581b-135">The following table describes the controls and options available on the Manage app permissions page.</span></span>
  
|<span data-ttu-id="d581b-136">**項目**</span><span class="sxs-lookup"><span data-stu-id="d581b-136">**Item**</span></span>|<span data-ttu-id="d581b-137">**描述**</span><span class="sxs-lookup"><span data-stu-id="d581b-137">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d581b-138">應用程式查詢列中的基本圖示</span><span class="sxs-lookup"><span data-stu-id="d581b-138">Basic icon in the app query bar</span></span>  <br/> ![會指出查詢應用程式權限的基本查詢檢視的圖示](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="d581b-140">選取這個選項可切換至 [進階檢視。</span><span class="sxs-lookup"><span data-stu-id="d581b-140">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="d581b-141">（如果您看到**基本**，您會使用 [進階] 檢視）</span><span class="sxs-lookup"><span data-stu-id="d581b-141">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="d581b-142">應用程式查詢列中的進階的圖示</span><span class="sxs-lookup"><span data-stu-id="d581b-142">Advanced icon in the app query bar</span></span>  <br/> ![會指出進階查詢應用程式權限的查詢檢視的圖示](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="d581b-144">選取這個選項可切換至 [基本] 檢視。</span><span class="sxs-lookup"><span data-stu-id="d581b-144">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="d581b-145">（如果您看到**進階**，您會使用 [基本] 檢視）。</span><span class="sxs-lookup"><span data-stu-id="d581b-145">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="d581b-146">開啟或關閉此應用程式清單中的所有詳細資料圖示</span><span class="sxs-lookup"><span data-stu-id="d581b-146">Open or close all details icon in the app list</span></span>  <br/> ![按一下此圖示來開啟或關閉所有應用程式的所有詳細資料](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="d581b-148">選取此圖示來檢視每個應用程式的更多或更少詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d581b-148">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="d581b-149">匯出應用程式清單中的圖示</span><span class="sxs-lookup"><span data-stu-id="d581b-149">Export icon in the app list</span></span>  <br/> ![按一下此圖示來匯出 csv 檔案的所有應用程式](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="d581b-151">選取此圖示來匯出 CSV 檔案包含應用程式] 的使用者的每個應用程式相關聯的應用程式、 權限層級、 應用程式狀態和社群使用層級的權限的清單。</span><span class="sxs-lookup"><span data-stu-id="d581b-151">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="d581b-152">名稱</span><span class="sxs-lookup"><span data-stu-id="d581b-152">Name</span></span>  <br/> |<span data-ttu-id="d581b-p105">使用此看到的名稱 app 選取来檢視詳細資訊，例如其描述、 publisher、 應用程式網站與應用程式識別碼的名稱</span><span class="sxs-lookup"><span data-stu-id="d581b-p105">Use this to see the name of an app. Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="d581b-155">依授權</span><span class="sxs-lookup"><span data-stu-id="d581b-155">Authorized by</span></span>  <br/> |<span data-ttu-id="d581b-p106">使用此檢視多少使用者已獲得授權的應用程式以存取其 Office 365 帳戶。選取要檢視的使用者帳戶清單等的詳細資訊的數字。</span><span class="sxs-lookup"><span data-stu-id="d581b-p106">Use this to see how many users have authorized an app to access their Office 365 account. Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="d581b-158">權限層級</span><span class="sxs-lookup"><span data-stu-id="d581b-158">Permissions Level</span></span>  <br/> ![會指出應用程式的 permisiions 層級的圖示](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="d581b-p107">使用此請參閱 Office 365 資料有多少的應用程式的存取。權限層級指出**Low**、 **Medium**或**High**、 **Low**可能表示應用程式只能存取使用者設定檔和名稱。選取應用程式、 社群使用及相關的活動[控管記錄檔](suspend-or-restore-an-account-in-ocas.md)中授與檢視詳細資訊，例如權限層級。</span><span class="sxs-lookup"><span data-stu-id="d581b-p107">Use this to see how much access an app has to Office 365 data. Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name. Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).  </span></span><br/> |
|<span data-ttu-id="d581b-163">應用程式狀態 （ **Banned**、**已核准**或**Undetermined**）</span><span class="sxs-lookup"><span data-stu-id="d581b-163">App state ( **Banned**, **Approved**, or **Undetermined**)</span></span>  <br/> <span data-ttu-id="d581b-164">![應用程式的權限圖示後要允許、 封鎖或沒有動作所已由系統管理員](media/5748bd02-cd59-4bd1-a36f-d25a186e8055.png)</span><span class="sxs-lookup"><span data-stu-id="d581b-164">![App permissions icons after being allowed, blocked, or no action has been taken by an admin](media/5748bd02-cd59-4bd1-a36f-d25a186e8055.png)</span></span>|<span data-ttu-id="d581b-165">使用此項，將應用程式標示為已核准 」 或 「 Banned，或離開作為源自。</span><span class="sxs-lookup"><span data-stu-id="d581b-165">Use this to mark an app as Approved or Banned, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="d581b-166">標記為已核准的應用程式</span><span class="sxs-lookup"><span data-stu-id="d581b-166">Mark an app as approved</span></span>
<span data-ttu-id="d581b-167"><a name="approveapp"> </a></span><span class="sxs-lookup"><span data-stu-id="d581b-167"></span></span>

<span data-ttu-id="d581b-168">在 [**管理應用程式權限**] 頁面上找出您想要核准的應用程式並選擇**做為 Mark app 核准**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="d581b-168">On the **Manage app permissions** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![選擇標記應用程式已核准的圖示](media/dd1b7690-441a-48c9-9c3a-58466513c63d.png)
  
<span data-ttu-id="d581b-170">圖示會開啟綠色和應用程式為您所有的 Office 365 使用者的 「 已核准。</span><span class="sxs-lookup"><span data-stu-id="d581b-170">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d581b-p108">當您將應用程式標示為已核准時，有不會影響使用者。以視覺方式標示核准的應用程式可協助隔開尚未尚未檢閱的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d581b-p108">When you mark an app as approved, there is no effect on the end user. Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="d581b-173">禁止應用程式</span><span class="sxs-lookup"><span data-stu-id="d581b-173">Ban an app</span></span>
<span data-ttu-id="d581b-174"><a name="banapp"> </a></span><span class="sxs-lookup"><span data-stu-id="d581b-174"></span></span>

1. <span data-ttu-id="d581b-175">在 [**管理應用程式權限**] 頁面上找出您要禁止、 應用的程式並選擇**做為 Mark app 禁用**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="d581b-175">On the **Manage app permissions** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span> 
    
    ![選擇標記 app 禁用的圖示](media/b9b1c5f6-fde7-46d5-8589-1564d05702b3.png)
  
2. <span data-ttu-id="d581b-177">選擇是否要讓使用者知道已禁用其應用程式。</span><span class="sxs-lookup"><span data-stu-id="d581b-177">Choose whether to let users know that their app has been banned.</span></span>
    
    <span data-ttu-id="d581b-178">（建議）若要讓使用者了解，請選取**授與此禁用的應用程式的存取權的通知使用者**，以及新增或編輯自訂通知訊息。</span><span class="sxs-lookup"><span data-stu-id="d581b-178">(Recommended) To let users know, select **Notify users who granted access to this banned app**, and add or edit a custom notification message.</span></span>
    
    <span data-ttu-id="d581b-179">不讓使用者知道，清除 [**授與此禁用的應用程式的存取權的通知使用者**。</span><span class="sxs-lookup"><span data-stu-id="d581b-179">To not let users know, clear **Notify users who granted access to this banned app**.</span></span>
    
    ![禁用的應用程式的 [郵件] 範本](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)
  
3. <span data-ttu-id="d581b-181">選擇 [**禁止應用程式**。</span><span class="sxs-lookup"><span data-stu-id="d581b-181">Choose **Ban app**.</span></span>
    
## <a name="create-an-app-query"></a><span data-ttu-id="d581b-182">建立應用程式的查詢</span><span class="sxs-lookup"><span data-stu-id="d581b-182">Create an app query</span></span>
<span data-ttu-id="d581b-183"><a name="createapp"> </a></span><span class="sxs-lookup"><span data-stu-id="d581b-183"></span></span>

1. <span data-ttu-id="d581b-p109">在應用程式查詢列中，如果您看到**進階**，按一下 （或點選） 它移至 [進階] 檢視。（如果您看到 Basic，您使用 [進階的檢視 ； 其會保持在檢視）。</span><span class="sxs-lookup"><span data-stu-id="d581b-p109">In the app query bar, if you see **Advanced**, click (or tap) it to go to the Advanced view. (If you see Basic, you are using the Advanced view; keep your view as it is.)</span></span>
    
2. <span data-ttu-id="d581b-p110">使用 [**選取篩選**] 清單選擇選項。下表摘要說明可用的篩選選項。</span><span class="sxs-lookup"><span data-stu-id="d581b-p110">Use the **Select a filter** list to choose an option. The following table summarizes your available filter options.</span></span> 
    
|<span data-ttu-id="d581b-188">**使用此篩選器**</span><span class="sxs-lookup"><span data-stu-id="d581b-188">**Use this filter**</span></span>|<span data-ttu-id="d581b-189">**若要顯示**</span><span class="sxs-lookup"><span data-stu-id="d581b-189">**To display**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d581b-190">**應用程式**</span><span class="sxs-lookup"><span data-stu-id="d581b-190">**App**</span></span> <br/> |<span data-ttu-id="d581b-191">應用程式特定的名稱</span><span class="sxs-lookup"><span data-stu-id="d581b-191">Apps with certain names</span></span>  <br/> |
|<span data-ttu-id="d581b-192">**應用程式狀態**</span><span class="sxs-lookup"><span data-stu-id="d581b-192">**App state**</span></span> <br/> |<span data-ttu-id="d581b-193">根據其狀態 （已核准、 Banned 或 Undetermined） 的應用程式</span><span class="sxs-lookup"><span data-stu-id="d581b-193">Apps based on their state (Approved, Banned, or Undetermined)</span></span>  <br/> |
|<span data-ttu-id="d581b-194">**社群的使用**</span><span class="sxs-lookup"><span data-stu-id="d581b-194">**Community use**</span></span> <br/> |<span data-ttu-id="d581b-195">社群為基礎的應用程式使用層級 （Rare、 Uncommon、 或一般）</span><span class="sxs-lookup"><span data-stu-id="d581b-195">Apps based on community use levels (Rare, Uncommon, or Common)</span></span>  <br/> |
|<span data-ttu-id="d581b-196">**權限等級**</span><span class="sxs-lookup"><span data-stu-id="d581b-196">**Permission level**</span></span> <br/> |<span data-ttu-id="d581b-197">某些權限層級為基礎的應用程式</span><span class="sxs-lookup"><span data-stu-id="d581b-197">Apps based on certain permission levels</span></span>  <br/> |
|<span data-ttu-id="d581b-198">**權限**</span><span class="sxs-lookup"><span data-stu-id="d581b-198">**Permissions**</span></span> <br/> |<span data-ttu-id="d581b-199">需要特定的權限的應用程式</span><span class="sxs-lookup"><span data-stu-id="d581b-199">Apps that require certain permissions</span></span>  <br/> |
|<span data-ttu-id="d581b-200">**發行者**</span><span class="sxs-lookup"><span data-stu-id="d581b-200">**Publisher**</span></span> <br/> |<span data-ttu-id="d581b-201">從特定發行者的應用程式</span><span class="sxs-lookup"><span data-stu-id="d581b-201">Apps from certain publishers</span></span>  <br/> |
|<span data-ttu-id="d581b-202">**使用者**</span><span class="sxs-lookup"><span data-stu-id="d581b-202">**User**</span></span> <br/> |<span data-ttu-id="d581b-203">某些使用者授權的應用程式</span><span class="sxs-lookup"><span data-stu-id="d581b-203">Apps that a certain user authorized</span></span>  <br/> |
   
3. <span data-ttu-id="d581b-204">選取 [**等於**] 或 [**不等於**，並接著指定篩選的值。</span><span class="sxs-lookup"><span data-stu-id="d581b-204">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
4. <span data-ttu-id="d581b-205">若要新增更多的篩選器，請選取 [加號 （</span><span class="sxs-lookup"><span data-stu-id="d581b-205">To add more filters, select the plus sign (</span></span>![新增查詢應用程式的篩選圖示](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="d581b-207">)，然後重複步驟 2 和 3。</span><span class="sxs-lookup"><span data-stu-id="d581b-207">), and then repeat steps 2 and 3.</span></span>
    
5. <span data-ttu-id="d581b-208">若要移除篩選，請選取 [x (</span><span class="sxs-lookup"><span data-stu-id="d581b-208">To remove a filter, select the x (</span></span>![移除查詢應用程式的篩選圖示](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="d581b-210">) 旁的篩選器名稱。</span><span class="sxs-lookup"><span data-stu-id="d581b-210">) next to a filter name.</span></span>
    
<span data-ttu-id="d581b-211">自動套用篩選器與據以更新的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="d581b-211">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="d581b-212">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d581b-212">Next steps</span></span>
<span data-ttu-id="d581b-213"><a name="nextsteps"> </a></span><span class="sxs-lookup"><span data-stu-id="d581b-213"></span></span>

- [<span data-ttu-id="d581b-214">檢閱並採取行動提醒</span><span class="sxs-lookup"><span data-stu-id="d581b-214">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="d581b-215">檢閱您的[網頁流量記錄檔與資料來源為 Office 365 雲端應用程式安全性](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="d581b-215">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="d581b-216">檢閱您[的 Office 365 雲端應用程式安全性使用率活動](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="d581b-216">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

