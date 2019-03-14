---
title: Office 365 雲端 App 安全性中的工作階段原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Office 365 雲端 App 安全性工作階段原則啟用即時工作階段層級監視，並細微的可視性 Office 365 應用程式所能採取不同的動作為使用者工作階段的原則。 而不是允許或封鎖存取完全，工作階段控制您可以同時監視使用條件式存取應用程式控制項的反向 proxy 功能的工作階段及/或限制特定的工作階段活動允許存取。
ms.openlocfilehash: e0e4b04ee8cc0f7a14adbc26b074a5f2947e44c2
ms.sourcegitcommit: 866d8cab6bcfdd124516a8369e47ec797bc7cf8a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/27/2019
ms.locfileid: "30312090"
---
# <a name="session-policies-in-office-365-cloud-app-security"></a><span data-ttu-id="0622a-104">Office 365 雲端 App 安全性中的工作階段原則</span><span class="sxs-lookup"><span data-stu-id="0622a-104">Session policies in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="0622a-105">評估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0622a-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="0622a-106">規劃 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0622a-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="0622a-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0622a-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="0622a-108">使用率 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="0622a-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="0622a-109">啟動評估</span><span class="sxs-lookup"><span data-stu-id="0622a-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="0622a-110">開始規劃</span><span class="sxs-lookup"><span data-stu-id="0622a-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="0622a-111">您在此處 ！</span><span class="sxs-lookup"><span data-stu-id="0622a-111">You are here!</span></span>  <br/> [<span data-ttu-id="0622a-112">下一步</span><span class="sxs-lookup"><span data-stu-id="0622a-112">Next step</span></span>](ocas-access-policies.md) <br/> |[<span data-ttu-id="0622a-113">開始使用</span><span class="sxs-lookup"><span data-stu-id="0622a-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="0622a-114">Office 365 雲端 App 安全性工作階段原則啟用即時工作階段層級監視，並細微的可視性 Office 365 應用程式所能採取不同的動作為使用者工作階段的原則。</span><span class="sxs-lookup"><span data-stu-id="0622a-114">Office 365 Cloud App Security session policies enable real-time session-level monitoring, affording you granular visibility into Office 365 apps and the ability to take different actions depending on the policy you set for a user session.</span></span> <span data-ttu-id="0622a-115">而不是允許或封鎖存取完全，工作階段控制您可以同時監視使用條件式存取應用程式控制項的反向 proxy 功能的工作階段及/或限制特定的工作階段活動允許存取。</span><span class="sxs-lookup"><span data-stu-id="0622a-115">Instead of allowing or blocking access completely, with session control you can allow access while monitoring the session and/or limit specific session activities using the reverse proxy capabilities of Conditional Access App Control.</span></span>

<span data-ttu-id="0622a-116">例如，您可以決定，從受管理的裝置，或來自特定位置工作階段，您想要允許使用者存取應用程式，但也限制的機密檔案下載，或需要特定文件受到保護時下載。</span><span class="sxs-lookup"><span data-stu-id="0622a-116">For example, you can decide that from unmanaged devices, or for sessions coming from specific locations, you want to allow the user to access the app but also limit the download of sensitive files or require that certain documents be protected upon download.</span></span> <span data-ttu-id="0622a-117">工作階段原則可讓您設定這些使用者工作階段的控制項，並允許存取，並可讓您：</span><span class="sxs-lookup"><span data-stu-id="0622a-117">Session policies enable you to set these user-session controls and allow access and enables you to:</span></span>

- [<span data-ttu-id="0622a-118">監視所有活動</span><span class="sxs-lookup"><span data-stu-id="0622a-118">Monitor all activities</span></span>](#monitor-all-activities)

- [<span data-ttu-id="0622a-119">封鎖所有的下載項目</span><span class="sxs-lookup"><span data-stu-id="0622a-119">Block all downloads</span></span>](#block-all-downloads)

- [<span data-ttu-id="0622a-120">封鎖特定活動</span><span class="sxs-lookup"><span data-stu-id="0622a-120">Block specific activities</span></span>](#block-specific-activities)

- [<span data-ttu-id="0622a-121">保護上下載的檔案</span><span class="sxs-lookup"><span data-stu-id="0622a-121">Protect files on download</span></span>](#protect-files-on-download)

## <a name="prerequisites-to-using-session-policies"></a><span data-ttu-id="0622a-122">若要使用的工作階段原則的必要條件</span><span class="sxs-lookup"><span data-stu-id="0622a-122">Prerequisites to using session policies</span></span>

- <span data-ttu-id="0622a-123">Azure AD Premium P1 授權</span><span class="sxs-lookup"><span data-stu-id="0622a-123">Azure AD Premium P1 license</span></span>

- <span data-ttu-id="0622a-124">相關的 Office 365 應用程式應該是 [使用條件式存取應用程式控制部署](ocas-deploy-conditional-access-app-control.md)</span><span class="sxs-lookup"><span data-stu-id="0622a-124">The relevant Office 365 apps should be [deployed with Conditional Access App Control](ocas-deploy-conditional-access-app-control.md)</span></span>

- <span data-ttu-id="0622a-125"> [Azure AD 條件式存取原則](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 應該在將使用者重新導向至 Office 365 雲端 App 安全性的地方</span><span class="sxs-lookup"><span data-stu-id="0622a-125">An [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) should be in place that redirects users to Office 365 Cloud App Security</span></span>

## <a name="create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="0622a-126">建立 Azure AD 條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="0622a-126">Create an Azure AD conditional access policy</span></span>

<span data-ttu-id="0622a-127">Azure Active Directory 條件式存取原則與 Cloud App Security 工作階段原則適用於搭配檢查每個使用者工作階段，並決定每個應用程式的原則。</span><span class="sxs-lookup"><span data-stu-id="0622a-127">Azure Active Directory conditional access policies and Cloud App Security session policies work in tandem to examine each user session and make policy decisions for each app.</span></span> <span data-ttu-id="0622a-128">若要在 Azure AD 中設定的條件式存取原則，請遵循此程序：</span><span class="sxs-lookup"><span data-stu-id="0622a-128">To set up a conditional access policy in Azure AD, follow this procedure:</span></span>

1. <span data-ttu-id="0622a-129">設定 [Azure AD 條件式存取原則](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 與使用者或群組的使用者與您想要與條件式存取應用程式控制項的控制項的應用程式的工作分派。</span><span class="sxs-lookup"><span data-stu-id="0622a-129">Configure an [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) with assignments for a user or group of users and the app you want to control with the Conditional Access App Control.</span></span> <span data-ttu-id="0622a-130">附註： 已 [部署與條件式存取應用程式控制項](ocas-deploy-conditional-access-app-control.md)僅應用程式 將會受到此原則。</span><span class="sxs-lookup"><span data-stu-id="0622a-130">NOTE: Only apps that were [deployed with Conditional Access App Control](ocas-deploy-conditional-access-app-control.md) will be affected by this policy.</span></span>

2. <span data-ttu-id="0622a-131">將使用者路由傳送至 Office 365 雲端 App 安全性藉由選取 [ **使用條件式存取應用程式控制強制執行限制**  **工作階段**中 ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0622a-131">Route users to Office 365 Cloud App Security by selecting the **Use Conditional Access App Control enforced restrictions** in the **Session** page.</span></span>

## <a name="create-a-cloud-app-security-session-policy"></a><span data-ttu-id="0622a-132">建立雲端 App 安全性工作階段原則</span><span class="sxs-lookup"><span data-stu-id="0622a-132">Create a Cloud App Security session policy</span></span>

<span data-ttu-id="0622a-133">若要建立新的工作階段原則，請遵循此程序：</span><span class="sxs-lookup"><span data-stu-id="0622a-133">To create a new session policy, follow this procedure:</span></span>

1. <span data-ttu-id="0622a-134">在 [入口網站中，選取 **控制項** 後面接著 **原則**。</span><span class="sxs-lookup"><span data-stu-id="0622a-134">In the portal, select **Control** followed by **Policies**.</span></span>

2. <span data-ttu-id="0622a-135">在 [ **原則** ] 頁面上，按一下 [ **建立原則** 並選取 [ **工作階段原則**。</span><span class="sxs-lookup"><span data-stu-id="0622a-135">In the **Policies** page, click **Create policy** and select **Session policy**.</span></span>

3. <span data-ttu-id="0622a-136">在 [ **工作階段原則** ] 視窗中，指派原則的名稱</span><span class="sxs-lookup"><span data-stu-id="0622a-136">In the **Session policy** window, assign a name for your policy</span></span>

4. <span data-ttu-id="0622a-137">在 **工作階段的控制項類型** 欄位：</span><span class="sxs-lookup"><span data-stu-id="0622a-137">In the **Session control type** field:</span></span>
    
    - <span data-ttu-id="0622a-138">選取 [ **僅限監視器** 如果您只想要監視使用者活動。</span><span class="sxs-lookup"><span data-stu-id="0622a-138">Select **Monitor only** if you only want to monitor activities by users.</span></span> <span data-ttu-id="0622a-139">此選取項目將會建立您所選取其中所有登入、 啟發式下載及活動類型將都下載的應用程式的監視器唯一原則。</span><span class="sxs-lookup"><span data-stu-id="0622a-139">This selection will create a Monitor only policy for the apps you selected where all sign-ins, heuristic downloads, and Activity types will be downloaded.</span></span>
    
    - <span data-ttu-id="0622a-140">選取 [ **控制 （使用 DLP 時) 的檔案下載** 如果您想要監視使用者活動。</span><span class="sxs-lookup"><span data-stu-id="0622a-140">Select **Control file download (with DLP)** if you want to monitor user activities.</span></span> <span data-ttu-id="0622a-141">您可以採取其他動作，例如封鎖或保護使用者的下載項目。</span><span class="sxs-lookup"><span data-stu-id="0622a-141">You can take additional actions like block or protect downloads for users.</span></span>
    
    - <span data-ttu-id="0622a-142">選取 [ **封鎖活動** 來封鎖特定的活動，您可以選擇使用 **活動類型** 篩選器。</span><span class="sxs-lookup"><span data-stu-id="0622a-142">Select **Block activities** to block specific activities, which you can select using the **Activity type** filter.</span></span> <span data-ttu-id="0622a-143">從選取的應用程式的所有活動會是監控 （和報告在活動記錄）。</span><span class="sxs-lookup"><span data-stu-id="0622a-143">All activities from selected apps will be monitored (and reported in the Activity log).</span></span> <span data-ttu-id="0622a-144">如果您選取 [ **區塊**，將會封鎖您選取的特定活動 巨集指令。</span><span class="sxs-lookup"><span data-stu-id="0622a-144">The specific activities you select will be blocked if you select the **Block** action.</span></span> <span data-ttu-id="0622a-145">如果您選取 [ **測試**您所選取的特定活動會引發警示 巨集指令與已開啟的提醒。</span><span class="sxs-lookup"><span data-stu-id="0622a-145">The specific activities you selected will raise alerts if you select the **Test** action and have alerts turned on.</span></span>

5. <span data-ttu-id="0622a-146">[ **活動來源** 中 **比對下列所有的活動** ] 區段中，選取要套用至該原則的其他活動篩選。</span><span class="sxs-lookup"><span data-stu-id="0622a-146">Under **Activity source** in the **Activities matching all of the following** section, select additional activity filters to apply to the policy.</span></span> <span data-ttu-id="0622a-147">這些篩選器可以包含下列選項：</span><span class="sxs-lookup"><span data-stu-id="0622a-147">These filters can include the following options:</span></span>
    
    - <span data-ttu-id="0622a-148">**裝置標記**： 使用此篩選器來識別未受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="0622a-148">**Device tags**: Use this filter to identify unmanaged devices.</span></span>
    
    - <span data-ttu-id="0622a-149">**位置**： 使用此篩選器來識別不明 （並因此風險） 的位置。</span><span class="sxs-lookup"><span data-stu-id="0622a-149">**Location**: Use this filter to identify unknown (and therefore risky) locations.</span></span>
    
    - <span data-ttu-id="0622a-150">**IP 位址**： 使用此篩選條件來篩選每個 IP 位址] 或 [使用先前指派的 IP 位址標記。</span><span class="sxs-lookup"><span data-stu-id="0622a-150">**IP address**: Use this filter to filter per IP addresses or use previously assigned IP address tags.</span></span>
    
    - <span data-ttu-id="0622a-151">**使用者代理程式標記**： 使用此篩選器啟用的啟發學習法來識別行動裝置和傳統型應用程式。</span><span class="sxs-lookup"><span data-stu-id="0622a-151">**User agent tag**: Use this filter to enable the heuristic to identify mobile and desktop apps.</span></span> <span data-ttu-id="0622a-152">此篩選器可以設定為等於或不等於 **原生用戶端**。</span><span class="sxs-lookup"><span data-stu-id="0622a-152">This filter can be set to equals or doesn't equal **Native client**.</span></span> <span data-ttu-id="0622a-153">此篩選應該比照您每個雲端應用程式的行動裝置和傳統型應用程式。</span><span class="sxs-lookup"><span data-stu-id="0622a-153">This filter should be tested against your mobile and desktop apps for each cloud app.</span></span><br><span data-ttu-id="0622a-154">附註： 工作階段原則不支援行動裝置和傳統型應用程式。</span><span class="sxs-lookup"><span data-stu-id="0622a-154">NOTE: Session policies don’t support mobile and desktop apps.</span></span> <span data-ttu-id="0622a-155">桌面應用程式和行動應用程式可以也封鎖或允許藉由建立存取原則。</span><span class="sxs-lookup"><span data-stu-id="0622a-155">Mobile apps and desktop apps can also be blocked or allowed by creating an access policy.</span></span>

6. <span data-ttu-id="0622a-156">如果您選取選項來 **控制檔案下載 （使用 DLP 時)**，請在 **活動來源**] 下  **符合下列所有檔案**中 ] 區段中，選取要套用至該原則的其他檔案篩選。</span><span class="sxs-lookup"><span data-stu-id="0622a-156">If you selected the option to **Control file download (with DLP)**, under **Activity source** in the **Files matching all of the following** section, select additional file filters to apply to the policy.</span></span> <span data-ttu-id="0622a-157">這些篩選器可以包含下列選項：</span><span class="sxs-lookup"><span data-stu-id="0622a-157">These filters can include the following options:</span></span>
        
    - <span data-ttu-id="0622a-158">**分類標籤** -如果您的組織使用 Azure 資訊保護和其分類標籤所受保護您的資料後，請使用此篩選。</span><span class="sxs-lookup"><span data-stu-id="0622a-158">**Classification label** - Use this filter if your organization uses Azure Information Protection and your data has been protected by its Classification labels.</span></span> <span data-ttu-id="0622a-159">您可以篩選套用至他們的分類標籤為基礎的檔案。</span><span class="sxs-lookup"><span data-stu-id="0622a-159">You can filter files based on the Classification label you applied to them.</span></span> <span data-ttu-id="0622a-160">如需有關整合使用 Azure 資訊保護，請參閱 [Azure 資訊保護整合](https://docs.microsoft.com/cloud-app-security/azip-integration)。</span><span class="sxs-lookup"><span data-stu-id="0622a-160">For more information about integration with Azure Information Protection, see [Azure Information Protection integration](https://docs.microsoft.com/cloud-app-security/azip-integration).</span></span>
        
    - <span data-ttu-id="0622a-161">**檔案名稱** -使用此篩選器原則套用至特定的檔案。</span><span class="sxs-lookup"><span data-stu-id="0622a-161">**File name** - Use this filter to apply the policy to specific files.</span></span>
        
    - <span data-ttu-id="0622a-162">**檔案類型** -使用此篩選器原則套用至特定檔案類型，例如封鎖下載所有.xls 檔案。</span><span class="sxs-lookup"><span data-stu-id="0622a-162">**File type** - Use this filter to apply the policy to specific file types, for example, block download for all .xls files.</span></span>
    
    - <span data-ttu-id="0622a-163">在 [ **內容檢查** ] 區段中，設定是否要讓 DLP 引擎掃描的文件和檔案內容。</span><span class="sxs-lookup"><span data-stu-id="0622a-163">In the **Content inspection** section, set whether you want to enable the DLP engine to scan documents and file content.</span></span>
    
    - <span data-ttu-id="0622a-164">在 [ **動作**] 下選取下列其中一個下列項目：</span><span class="sxs-lookup"><span data-stu-id="0622a-164">Under **Actions**, select one of the following items:</span></span>
        
        - <span data-ttu-id="0622a-165">**測試 （監視所有活動）**： 設定此巨集指令，明確允許下載根據您所設定的原則篩選器。</span><span class="sxs-lookup"><span data-stu-id="0622a-165">**Test (Monitor all activities)**: Set this action to explicitly allow download according to the policy filters you set.</span></span>
        
        - <span data-ttu-id="0622a-166">**區塊 （封鎖檔案下載和監視所有活動）**： 設定明確封鎖根據您所設定的原則篩選器下載此巨集指令。</span><span class="sxs-lookup"><span data-stu-id="0622a-166">**Block (Block file download and monitor all activities)**: Set this action to explicitly block download according to the policy filters you set.</span></span> <span data-ttu-id="0622a-167">如需詳細資訊，請參閱 [封鎖下載運作的方式](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#block-download)。</span><span class="sxs-lookup"><span data-stu-id="0622a-167">For more information, see [How block download works](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#block-download).</span></span>
        
        - <span data-ttu-id="0622a-168">**Protect （套用分類標籤來下載及監視所有活動）**： 此選項才可用如果您選取了 **控制檔案下載 （與 DLP)**  **工作階段原則**] 底下。</span><span class="sxs-lookup"><span data-stu-id="0622a-168">**Protect (Apply classification label to download and monitor all activities)**: This option is only available if you selected **Control file download (with DLP)** under **Session policy**.</span></span> <span data-ttu-id="0622a-169">如果您的組織使用 Azure 資訊保護，您可以設定 **巨集指令** 若要套用的分類標籤設定 Azure 資訊保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="0622a-169">If your organization uses Azure Information Protection, you can set an **Action** to apply a classification label set in Azure Information Protection to the file.</span></span> <span data-ttu-id="0622a-170">如需詳細資訊，請參閱 <<c0>如何保護下載運作。</span><span class="sxs-lookup"><span data-stu-id="0622a-170">For more information, see [How protect download works](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#protect-download).</span></span>

7. <span data-ttu-id="0622a-171">您可以 **建立的原則嚴重性與每個比對事件警示** 和設定的警示限制。</span><span class="sxs-lookup"><span data-stu-id="0622a-171">You can **Create an alert for each matching event with the policy's severity** and set an alert limit.</span></span> <span data-ttu-id="0622a-172">選取是否要為一封電子郵件、 文字訊息，或兩者警示。</span><span class="sxs-lookup"><span data-stu-id="0622a-172">Select whether you want the alert as an email, a text message, or both.</span></span>

## <a name="monitor-all-activities"></a><span data-ttu-id="0622a-173">監視所有活動</span><span class="sxs-lookup"><span data-stu-id="0622a-173">Monitor all activities</span></span>

<span data-ttu-id="0622a-174">當您建立工作階段原則時，原則會比對每個使用者工作階段會重新導向至工作階段控制，而不是應用程式直接。</span><span class="sxs-lookup"><span data-stu-id="0622a-174">When you create a session policy, each user session that matches the policy is redirected to session control rather than to the app directly.</span></span> <span data-ttu-id="0622a-175">使用者會看到監視的通知，以讓他們知道其工作階段會受監視。</span><span class="sxs-lookup"><span data-stu-id="0622a-175">The user will see a monitoring notice to let them know that their sessions are being monitored.</span></span>

<span data-ttu-id="0622a-176">如果您不想要通知使用者他們正在受監視，您可以停用的通知訊息。</span><span class="sxs-lookup"><span data-stu-id="0622a-176">If you don't want to notify the user that they're being monitored, you can disable the notification message.</span></span>

1. <span data-ttu-id="0622a-177">在設定商旅中，選取 [ **一般設定**]。</span><span class="sxs-lookup"><span data-stu-id="0622a-177">Under the settings cog, select **General settings**.</span></span>

2. <span data-ttu-id="0622a-178">然後，在 **條件式存取應用程式控制** 選取 **使用者監視** 並取消選取 **通知使用者** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0622a-178">Then, under **Conditional Access App Control** select **User monitoring** and unselect the **Notify users** checkbox.</span></span>

<span data-ttu-id="0622a-179">若要保留內的工作階段、 條件式存取應用程式控制取代所有相關的 Url、 Java 指令碼和 cookie 的使用者，與 Office 365 雲端 App 安全性 Url 的應用程式工作階段內。</span><span class="sxs-lookup"><span data-stu-id="0622a-179">To keep the user within the session, Conditional Access App Control replaces all the relevant URLs, Java scripts, and cookies within the app session with Office 365 Cloud App Security URLs.</span></span> <span data-ttu-id="0622a-180">例如，如果應用程式會傳回有連結的頁面，其網域結束於`myapp.com`，條件式存取應用程式控制會取代以類似的網域中的連結`myapp.com.us.cas.ms`。</span><span class="sxs-lookup"><span data-stu-id="0622a-180">For example, if the app returns a page with links whose domains ends with `myapp.com`, Conditional Access App Control replaces the links with domains ending with something like `myapp.com.us.cas.ms`.</span></span> <span data-ttu-id="0622a-181">這種方式在整個工作階段的監視可以 Office 365 雲端 App 安全性。</span><span class="sxs-lookup"><span data-stu-id="0622a-181">This way the entire session is monitored by Office 365 Cloud App Security.</span></span>

<span data-ttu-id="0622a-182">條件式存取應用程式控制記錄每個使用者工作階段，透過它路由傳送的流量記錄檔。</span><span class="sxs-lookup"><span data-stu-id="0622a-182">Conditional Access App Control records the traffic logs of every user session that is routed through it.</span></span> <span data-ttu-id="0622a-183">流量記錄檔包括時間、 IP、 使用者代理程式，瀏覽的 Url，並上傳及下載的位元組數。</span><span class="sxs-lookup"><span data-stu-id="0622a-183">The traffic logs include the time, IP, user agent, URLs visited, and the number of bytes uploaded and downloaded.</span></span> <span data-ttu-id="0622a-184">這些記錄檔會經過分析，連續的報表， **雲端 App 安全性條件式存取應用程式控制項**，會新增至雲端探索儀表板中的雲端探索報表的清單。</span><span class="sxs-lookup"><span data-stu-id="0622a-184">These logs are analyzed and a continuous report, **Cloud App Security Conditional Access App Control**, is added to the list of Cloud Discovery reports in the Cloud Discovery dashboard.</span></span>

### <a name="to-export-these-logs"></a><span data-ttu-id="0622a-185">若要匯出這些記錄檔：</span><span class="sxs-lookup"><span data-stu-id="0622a-185">To export these logs:</span></span>

1. <span data-ttu-id="0622a-186">前往 [設定商旅，然後按一下 [ **條件式存取應用程式控制**。</span><span class="sxs-lookup"><span data-stu-id="0622a-186">Go to the settings cog and click **Conditional Access App Control**.</span></span>

2. <span data-ttu-id="0622a-187">在表格的右側，按一下 [匯出] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="0622a-187">On the right side of the table, click the export button.</span></span><br>![匯出] 按鈕](media/image3.png)<br>

3. <span data-ttu-id="0622a-189">選取報表的範圍，然後按一下 [ **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="0622a-189">Select the range of the report and click **Export**.</span></span> <span data-ttu-id="0622a-190">此程序可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="0622a-190">This process may take some time.</span></span>

### <a name="to-download-the-exported-log"></a><span data-ttu-id="0622a-191">若要下載匯出的記錄檔：</span><span class="sxs-lookup"><span data-stu-id="0622a-191">To download the exported log:</span></span>

1. <span data-ttu-id="0622a-192">準備報表之後，請移至 [ **設定** ，然後 **匯出報告**。</span><span class="sxs-lookup"><span data-stu-id="0622a-192">After the report is ready, go to **Settings** and then **Exported reports**.</span></span>

2. <span data-ttu-id="0622a-193">在表格中，請從 **條件式存取應用程式控制項的流量記錄檔**的清單中選取相關的報告 並按一下 [下載]。</span><span class="sxs-lookup"><span data-stu-id="0622a-193">In the table, select the relevant report from the list of **Conditional Access App Control traffic logs** and click download.</span></span><br><span data-ttu-id="0622a-194">![下載] 按鈕](media/image4.png)</span><span class="sxs-lookup"><span data-stu-id="0622a-194">![download button](media/image4.png)</span></span><br>

## <a name="block-all-downloads"></a><span data-ttu-id="0622a-195">封鎖所有的下載項目</span><span class="sxs-lookup"><span data-stu-id="0622a-195">Block all downloads</span></span>

<span data-ttu-id="0622a-196">當 **封鎖** 設為 **巨集指令** 您想要取得雲端 App 安全性工作階段原則中，條件式存取應用程式控制可防止使用者下載每個原則的檔案篩選器的檔案。</span><span class="sxs-lookup"><span data-stu-id="0622a-196">When **Block** is set as the **Action** you want to take in the Cloud App Security session policy, Conditional Access App Control prevents a user from downloading a file per the policy’s file filters.</span></span> <span data-ttu-id="0622a-197">下載事件辨識 Office 365 雲端 App 安全性每個應用程式當使用者開始下載。</span><span class="sxs-lookup"><span data-stu-id="0622a-197">A download event is recognized by Office 365 Cloud App Security for each app when a user starts a download.</span></span> <span data-ttu-id="0622a-198">條件式存取應用程式控制介入可防止執行的即時為止。</span><span class="sxs-lookup"><span data-stu-id="0622a-198">Conditional Access App Control intervenes in real time to prevent it from running.</span></span> <span data-ttu-id="0622a-199">條件式存取應用程式控制使用者已經啟動下載收到接收的訊號時，傳回 **下載限制** 訊息給使用者，並以文字檔案取代下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="0622a-199">When the signal is received that a user has initiated a download, Conditional Access App Control returns a **Download restricted** message to the user and replaces the downloaded file with a text file.</span></span> <span data-ttu-id="0622a-200">可設定及透過 「 工作階段原則來自訂文字檔的訊息給使用者。</span><span class="sxs-lookup"><span data-stu-id="0622a-200">The text file's message to the user can be configured and customized from the session policy.</span></span>

## <a name="block-specific-activities"></a><span data-ttu-id="0622a-201">封鎖特定活動</span><span class="sxs-lookup"><span data-stu-id="0622a-201">Block specific activities</span></span>

<span data-ttu-id="0622a-202">時 **封鎖活動** 設為 **活動類型**中，您可以選取要封鎖特定的應用程式中的特定活動。</span><span class="sxs-lookup"><span data-stu-id="0622a-202">When **Block activities** is set as the **Activity type**, you can select specific activities to block in specific apps.</span></span> <span data-ttu-id="0622a-203">將監視從選取的應用程式的所有活動，並將其活動記錄檔中報告。</span><span class="sxs-lookup"><span data-stu-id="0622a-203">All activities from selected apps will be monitored and reported in the Activity log.</span></span> <span data-ttu-id="0622a-204">如果您選取 [ **區塊**，將會封鎖您選取的特定活動 巨集指令。</span><span class="sxs-lookup"><span data-stu-id="0622a-204">The specific activities you select will be blocked if you select the **Block** action.</span></span> <span data-ttu-id="0622a-205">如果您選取的 **測試**巨集指令，而且具有提醒您所選取的特定活動會引發警示開啟。</span><span class="sxs-lookup"><span data-stu-id="0622a-205">The specific activities you selected will raise alerts if you select the **Test** action and have alerts turned on.</span></span>

<span data-ttu-id="0622a-206">**封鎖特定活動** 並將其套用至特定群組，以建立您的組織使用完整唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="0622a-206">**Block specific activities** and apply it to specific groups to create a comprehensive read-only mode for your organization.</span></span>

## <a name="protect-files-on-download"></a><span data-ttu-id="0622a-207">保護上下載的檔案</span><span class="sxs-lookup"><span data-stu-id="0622a-207">Protect files on download</span></span>

<span data-ttu-id="0622a-208">選取 [ **封鎖活動** 來封鎖特定的活動，您可以找到使用 **活動類型** 篩選器。</span><span class="sxs-lookup"><span data-stu-id="0622a-208">Select **Block activities** to block specific activities, which you can find using the **Activity type** filter.</span></span> <span data-ttu-id="0622a-209">從選取的應用程式的所有活動會是監控 （和報告在活動記錄）。</span><span class="sxs-lookup"><span data-stu-id="0622a-209">All activities from selected apps will be monitored (and reported in the Activity log).</span></span> <span data-ttu-id="0622a-210">如果您選取 [ **區塊**，將會封鎖您選取的特定活動 巨集指令。</span><span class="sxs-lookup"><span data-stu-id="0622a-210">The specific activities you select will be blocked if you select the **Block** action.</span></span> <span data-ttu-id="0622a-211">如果您選取 [ **測試**您所選取的特定活動會引發警示 巨集指令與已開啟的提醒。</span><span class="sxs-lookup"><span data-stu-id="0622a-211">The specific activities you selected will raise alerts if you select the **Test** action and have alerts turned on.</span></span>

<span data-ttu-id="0622a-212">當 **保護** 設為 **巨集指令** 所要採取的 Cloud App Security 工作階段原則中，條件式存取應用程式控制強制執行原則的檔案篩選器每一個檔案的標籤和後續保護。</span><span class="sxs-lookup"><span data-stu-id="0622a-212">When **Protect** is set as the **Action** to be taken in the Cloud App Security session policy, Conditional Access App Control enforces the labeling and subsequent protection of a file per the policy’s file filters.</span></span> <span data-ttu-id="0622a-213">標籤已在 [Azure 資訊保護主控台和 **保護** 必須選取內就會出現在 Cloud App Security 原則選項的標籤。</span><span class="sxs-lookup"><span data-stu-id="0622a-213">Labels are configured in the Azure Information Protection console and **Protect** must be selected within the label for it to appear as an option in the Cloud App Security policy.</span></span> <span data-ttu-id="0622a-214">當選取標籤，並下載檔案後，符合準則的 Cloud App Security 原則時，label 及對應的保護 （具有權限） 會套用至在下載時的檔案。</span><span class="sxs-lookup"><span data-stu-id="0622a-214">When a label is selected, and a file is downloaded that meets the criteria of the Cloud App Security policy, the label, and corresponding protection (with permissions) is applied to the file upon download.</span></span> <span data-ttu-id="0622a-215">原始的檔案會保持為-是在雲端應用程式中，而現在保護下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="0622a-215">The original file remains as-is in the cloud app while the downloaded file is now protected.</span></span> <span data-ttu-id="0622a-216">嘗試存取檔案的使用者必須符合取決於保護套用的權限需求。</span><span class="sxs-lookup"><span data-stu-id="0622a-216">Users who try to access the file must meet the permission requirements determined by the protection applied.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0622a-217">後續步驟</span><span class="sxs-lookup"><span data-stu-id="0622a-217">Next steps</span></span>

- [<span data-ttu-id="0622a-218">了解 Office 365 雲端 App 安全性中的存取原則</span><span class="sxs-lookup"><span data-stu-id="0622a-218">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md)

- [<span data-ttu-id="0622a-219">封鎖使用 Azure AD 條件式存取應用程式控制功能未受管理的裝置上的下載項目</span><span class="sxs-lookup"><span data-stu-id="0622a-219">Blocking downloads on unmanaged devices using Azure AD Conditional Access App Control capabilities</span></span>](https://docs.microsoft.com/en-us/cloud-app-security/use-case-proxy-block-session-aad)

