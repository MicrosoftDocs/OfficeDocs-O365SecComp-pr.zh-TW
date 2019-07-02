---
title: 在 Office 365 中部署連接器以封存 Facebook 資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 系統管理員可以設定原生連接器, 將 Facebook 商務頁面匯入和封存至 Office 365。 將此資料匯入 Office 365 之後, 您就可以使用符合性功能 (例如法律保留、內容搜尋和保留原則) 來管理組織 Facebook 資料的控管。
ms.openlocfilehash: 1f5b0f241616cc95e79e80d054a8782f97c5887b
ms.sourcegitcommit: 3699da2cad6e6a2002083e2884e32393dacab0ca
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2019
ms.locfileid: "34694735"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a><span data-ttu-id="b626e-104">在 Office 365 中部署連接器以封存 Facebook 資料</span><span class="sxs-lookup"><span data-stu-id="b626e-104">Deploy a connector to archive Facebook data in Office 365</span></span>

<span data-ttu-id="b626e-105">本文包含以部署使用 Office 365 匯入服務將資料從 Facebook 商務頁面匯入至 Office 365 的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="b626e-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Office 365.</span></span> <span data-ttu-id="b626e-106">如需此程式的高階概述以及部署 Facebook 連接器所需的必要條件清單, 請參閱[在 Office 365 中使用範例連接器封存 Facebook 資料 (預覽)](archive-facebook-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="b626e-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Use a sample connector to archive Facebook data in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="b626e-107">步驟 1: 下載套件</span><span class="sxs-lookup"><span data-stu-id="b626e-107">Step 1: Download the package</span></span>

<span data-ttu-id="b626e-108">從 GitHub 存放庫的版本章節下載預建套件, 網址<https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>為。</span><span class="sxs-lookup"><span data-stu-id="b626e-108">Download the prebuilt package from the Release section in the GitHub repository at <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span></span> <span data-ttu-id="b626e-109">在最新的版本下, 下載名為**SampleConnector**的 zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="b626e-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="b626e-110">在步驟4中, 您將此 zip 檔案上傳至 Azure。</span><span class="sxs-lookup"><span data-stu-id="b626e-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="b626e-111">步驟 2: 在 Azure Active Directory 中建立應用程式</span><span class="sxs-lookup"><span data-stu-id="b626e-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="b626e-112">移至<https://portal.azure.com> , 並使用 Office 365 全域系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="b626e-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![在 AAD 中建立應用程式](media/FBCimage1.png)

2. <span data-ttu-id="b626e-114">在左功能窗格中, 按一下 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![](media/FBCimage2.png)

3. <span data-ttu-id="b626e-115">在左功能窗格中, 按一下 **[應用程式註冊] ([預覽])** , 然後按一下 [**新增註冊**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-115">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![](media/FBCimage3.png)

4. <span data-ttu-id="b626e-116">註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="b626e-116">Register the application.</span></span> <span data-ttu-id="b626e-117">在 [重新導向 URI] 下, 選取 [應用程式類型] 下拉式<https://portal.azure.com>清單中的 [Web], 然後輸入 URI 的方塊。</span><span class="sxs-lookup"><span data-stu-id="b626e-117">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![](media/FBCimage4.png)

5. <span data-ttu-id="b626e-118">複製**應用程式 (用戶端) 識別碼**和**目錄 (租**使用者) 識別碼, 並將它們儲存到文字檔或其他安全的位置。</span><span class="sxs-lookup"><span data-stu-id="b626e-118">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="b626e-119">您可以在稍後的步驟中使用這些識別碼。</span><span class="sxs-lookup"><span data-stu-id="b626e-119">You use these IDs in later steps.</span></span>

   ![](media/FBCimage5.png)

6. <span data-ttu-id="b626e-120">移至 **[憑證] & 新應用程式的機密。**</span><span class="sxs-lookup"><span data-stu-id="b626e-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![](media/FBCimage6.png)

7. <span data-ttu-id="b626e-121">按一下 [**新增用戶端密碼**]</span><span class="sxs-lookup"><span data-stu-id="b626e-121">Click **New client secret**</span></span>

   ![](media/FBCimage7.png)

8. <span data-ttu-id="b626e-122">建立新的密碼。</span><span class="sxs-lookup"><span data-stu-id="b626e-122">Create a new secret.</span></span> <span data-ttu-id="b626e-123">在 [描述] 方塊中, 輸入密碼, 然後選擇到期時間。</span><span class="sxs-lookup"><span data-stu-id="b626e-123">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![](media/FBCimage8.png)

9. <span data-ttu-id="b626e-124">複製機密的值, 並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="b626e-124">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="b626e-125">這是您在稍後步驟中使用的 AAD 應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="b626e-125">This is the AAD application secret that you use in later steps.</span></span>

   ![](media/FBCimage9.png)

10. <span data-ttu-id="b626e-126">請移至**資訊清單**, 並複製 identifierUris (也稱為 AAD 應用程式 Uri), 如下列螢幕擷取畫面所示。</span><span class="sxs-lookup"><span data-stu-id="b626e-126">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="b626e-127">將 AAD 應用程式 Uri 複製到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="b626e-127">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="b626e-128">您可以在步驟6中使用。</span><span class="sxs-lookup"><span data-stu-id="b626e-128">You use it in Step 6.</span></span>

   ![](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="b626e-129">步驟 3: 建立 Azure 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="b626e-129">Step 3: Create an Azure storage account</span></span>

1. <span data-ttu-id="b626e-130">移至您組織的 Azure 首頁。</span><span class="sxs-lookup"><span data-stu-id="b626e-130">Go to the Azure home page for your organization.</span></span>

    ![](media/FBCimage11.png)

2. <span data-ttu-id="b626e-131">按一下 [**建立資源**], 然後在 [搜尋] 方塊中輸入 [**儲存帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-131">Click **Create a resource** and they type **storage account** in the search box.</span></span>

    ![](media/FBCimage12.png)

3. <span data-ttu-id="b626e-132">按一下 [**儲存**], 然後按一下 [**儲存帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-132">Click **Storage**, and then click **Storage account**.</span></span>

    ![](media/FBCimage13.png)

4. <span data-ttu-id="b626e-133">在 [**建立儲存帳戶**] 頁面上的 [訂閱] 方塊中, 根據您擁有的 Azure 訂閱類型, 選取 [**隨**選即用] 或 [**免費試用**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-133">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> <span data-ttu-id="b626e-134">然後選取或建立資源群組。</span><span class="sxs-lookup"><span data-stu-id="b626e-134">Then select or create a resource group.</span></span>

    ![](media/FBCimage14.png)

5. <span data-ttu-id="b626e-135">輸入儲存帳戶的名稱。</span><span class="sxs-lookup"><span data-stu-id="b626e-135">Type a name for the storage account.</span></span>

    ![](media/FBCimage15.png)

6. <span data-ttu-id="b626e-136">檢查, 然後按一下 [**建立**] 以建立儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="b626e-136">Review and then click **Create** to create the storage account.</span></span>

    ![](media/FBCimage16.png)

7. <span data-ttu-id="b626e-137">幾分鐘後, 按一下 [ \*\*\*\* 重新整理], 然後按一下 [**移至資源**] 以流覽至儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="b626e-137">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

    ![](media/FBCimage17.png)

8. <span data-ttu-id="b626e-138">按一下左功能窗格中的 [**訪問金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-138">Click **Access keys** in the left navigation pane.</span></span>

    ![](media/FBCimage18.png)

9. <span data-ttu-id="b626e-139">複製**連接字串**, 並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="b626e-139">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="b626e-140">您可以在建立 web 應用程式資源時使用此程式。</span><span class="sxs-lookup"><span data-stu-id="b626e-140">You use this when creating a web app resource.</span></span>

    ![](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="b626e-141">步驟 4: 在 Azure 中建立新的 web 應用程式資源</span><span class="sxs-lookup"><span data-stu-id="b626e-141">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="b626e-142">在 Azure 入口網站的**首頁**上, 按一下 [**建立所有\> Web \>應用程式的資源**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-142">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="b626e-143">在 [ **Web 應用程式**] 頁面上, 按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-143">On the **Web app** page, click **Create**.</span></span> 

   ![](media/FBCimage20.png)

2. <span data-ttu-id="b626e-144">填寫詳細資料 (如下所示), 然後再建立 Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="b626e-144">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="b626e-145">請注意, 您在 [**應用程式名稱**] 方塊中輸入的名稱會用來建立 Azure 應用程式服務 URL;例如, fbconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="b626e-145">Note that the name that you enter in the **App name** box is used to create the Azure app service URL; for example, fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage21.png)

3. <span data-ttu-id="b626e-146">移至新建立的 web 應用程式資源, 按一下左功能窗格中的 [**應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-146">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="b626e-147">在 [應用程式設定] 下, 按一下 [新增設定], 然後新增下列三個設定: 使用值 (您從先前的步驟複製到文字檔):</span><span class="sxs-lookup"><span data-stu-id="b626e-147">Under Application settings, click Add new setting and add the following three settings: Use the values (that you copied to the text file from the previous steps):</span></span> 

    <span data-ttu-id="b626e-148">– **APISecretKey** –您可以輸入任何值作為機密。</span><span class="sxs-lookup"><span data-stu-id="b626e-148">– **APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="b626e-149">這是用來存取步驟7中的連接器 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="b626e-149">This is used to access the connector web app in Step 7.</span></span>

    <span data-ttu-id="b626e-150">– \* \* StorageAccountConnectionString-您在步驟3中建立 Azure 儲存體帳戶之後複製的連接字串 Uri。</span><span class="sxs-lookup"><span data-stu-id="b626e-150">– \*\*StorageAccountConnectionString — The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    <span data-ttu-id="b626e-151">– **tenantId** –您在步驟2中建立 Azure Active Directory 中的 Facebook 連接器應用程式後所複製之 Office 365 組織的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="b626e-151">– **tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

    ![](media/FBCimage22.png)

4. <span data-ttu-id="b626e-152">在 **[一般設定**] \*\*\*\* 下, 按一下 [ **Always on**] 旁的 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="b626e-152">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="b626e-153">按一下頁面頂端的 [**儲存**] 以儲存應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="b626e-153">Click **Save** at the top of the page to save application settings.</span></span>

   ![](media/FBCimage23.png)

5. <span data-ttu-id="b626e-154">最後一個步驟是將連接器應用程式原始程式碼上傳至您在步驟1下載的 Azure。</span><span class="sxs-lookup"><span data-stu-id="b626e-154">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="b626e-155">在網頁瀏覽器中, 移至<AzureAppResourceName>HTTPs://。</span><span class="sxs-lookup"><span data-stu-id="b626e-155">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="b626e-156">例如, 如果您的 Azure 應用程式資源名稱 (在本節步驟2中命名為**fbconnector**), 則您會前往https://fbconnector.scm.azurewebsites.net/ZipDeployUi。</span><span class="sxs-lookup"><span data-stu-id="b626e-156">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **fbconnector**, then you would go to https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span></span> 

6. <span data-ttu-id="b626e-157">將 SampleConnector 的 .zip (您在步驟1下載) 拖放至此頁面。</span><span class="sxs-lookup"><span data-stu-id="b626e-157">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="b626e-158">上載檔案並成功部署後, 頁面看起來會類似下列螢幕擷取畫面:</span><span class="sxs-lookup"><span data-stu-id="b626e-158">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a><span data-ttu-id="b626e-159">步驟 5: 註冊 Facebook 應用程式</span><span class="sxs-lookup"><span data-stu-id="b626e-159">Step 5: Register the Facebook app</span></span>

1. <span data-ttu-id="b626e-160">請移<https://developers.facebook.com>至, 使用組織的 Facebook 商務頁帳戶登入, 然後按一下 [新增**應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-160">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![](media/FBCimage25.png)

2. <span data-ttu-id="b626e-161">建立新的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="b626e-161">Create a new app ID.</span></span>

   ![](media/FBCimage26.png)

3. <span data-ttu-id="b626e-162">在左功能窗格中, 按一下 [**新增產品**], 然後按一下 [ **Facebook 登**入] 磚中的 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-162">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![](media/FBCimage27.png)

4. <span data-ttu-id="b626e-163">在 [整合 Facebook 登入] 頁面上, 按一下 [ **Web**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-163">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![](media/FBCimage28.png)

5. <span data-ttu-id="b626e-164">新增 Azure 應用程式服務 URL;例如https://fbconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="b626e-164">Add the Azure app service URL; for example https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage29.png)

6. <span data-ttu-id="b626e-165">完成 Facebook 登入設定的快速入門一節。</span><span class="sxs-lookup"><span data-stu-id="b626e-165">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![](media/FBCimage30.png)

7. <span data-ttu-id="b626e-166">在 [ **Facebook 登**入] 底下的左功能窗格中, 按一下 [**設定**], 然後在 [**有效的 OAuth 重新導向 Uri** ] 方塊中新增 OAuth 重新導向 URI。</span><span class="sxs-lookup"><span data-stu-id="b626e-166">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="b626e-167">使用格式\*\* \<connectorserviceuri>/views/facebookoauth\*\*, 其中 connectorserviceuri 的值是您組織的 Azure 應用程式服務 URL;例如, https://fbconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="b626e-167">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage31.png)

8. <span data-ttu-id="b626e-168">在左功能窗格中, 按一下 [**新增產品**], 然後按一下 [ **Webhooks]。**</span><span class="sxs-lookup"><span data-stu-id="b626e-168">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="b626e-169">在 [**頁面**] 下拉式功能表中, 按一下 [**頁面**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-169">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![](media/FBCimage32.png)

9. <span data-ttu-id="b626e-170">新增 Webhooks 回呼 URL 並新增 verify token。</span><span class="sxs-lookup"><span data-stu-id="b626e-170">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="b626e-171">回呼 URL 的格式, 請使用格式\*\* <connectorserviceuri>/api/FbPageWebhook\*\*, 其中 connectorserviceuri 的值是貴組織的 Azure 應用程式服務 URL;例如https://fbconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="b626e-171">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example https://fbconnector.azurewebsites.net.</span></span> 

    <span data-ttu-id="b626e-172">Verify token 應該類似強式密碼。</span><span class="sxs-lookup"><span data-stu-id="b626e-172">The verify token should similar to a strong password.</span></span> <span data-ttu-id="b626e-173">將 verify token 複製到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="b626e-173">Copy the verify token to a text file or other storage location.</span></span>

     ![](media/FBCimage33.png)

10. <span data-ttu-id="b626e-174">測試並訂閱提要的端點。</span><span class="sxs-lookup"><span data-stu-id="b626e-174">Test and subscribe to the endpoint for feed.</span></span>

    ![](media/FBCimage34.png)

11. <span data-ttu-id="b626e-175">新增隱私權 URL、應用程式圖示及商務用。</span><span class="sxs-lookup"><span data-stu-id="b626e-175">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="b626e-176">此外, 請將應用程式識別碼和應用程式密碼複製到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="b626e-176">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![](media/FBCimage35.png)

12. <span data-ttu-id="b626e-177">將應用程式設為公用。</span><span class="sxs-lookup"><span data-stu-id="b626e-177">Make the app public.</span></span>

    ![](media/FBCimage36.png)

13. <span data-ttu-id="b626e-178">將使用者新增至 [管理員] 或 [測試人員] 角色。</span><span class="sxs-lookup"><span data-stu-id="b626e-178">Add user to the admin or tester role.</span></span>

    ![](media/FBCimage37.png)

14. <span data-ttu-id="b626e-179">新增**頁面公開內容訪問**許可權。</span><span class="sxs-lookup"><span data-stu-id="b626e-179">Add the **Page Public Content Access** permission.</span></span>

    ![](media/FBCimage38.png)

15. <span data-ttu-id="b626e-180">[新增管理頁面] 許可權。</span><span class="sxs-lookup"><span data-stu-id="b626e-180">Add Manage Pages permission.</span></span>

    ![](media/FBCimage39.png)

16. <span data-ttu-id="b626e-181">取得 Facebook 所審查的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b626e-181">Get the application reviewed by Facebook.</span></span>

    ![](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="b626e-182">步驟 6: 設定連接器 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="b626e-182">Step 6: Configure the connector web app</span></span>

1. <span data-ttu-id="b626e-183">移至 HTTPs://\<AzureAppResourceName> azurewebsites.net (其中 AzureAppResourceName 是您在步驟4中命名的 Azure 應用程式資源名稱), 例如, 如果名稱是**fbconnector**, 請移至https://fbconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="b626e-183">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to https://fbconnector.azurewebsites.net.</span></span> <span data-ttu-id="b626e-184">應用程式的首頁看起來將如下列螢幕擷取畫面所示:</span><span class="sxs-lookup"><span data-stu-id="b626e-184">The home page of the app will look like the following screenshot:</span></span>


   ![](media/FBCimage41.png)

2. <span data-ttu-id="b626e-185">按一下 [**設定**] 以顯示登入頁面。</span><span class="sxs-lookup"><span data-stu-id="b626e-185">Click **Configure** to display a sign in page.</span></span>
 
   ![](media/FBCimage42.png)

3. <span data-ttu-id="b626e-186">在 [租使用者識別碼] 方塊中, 輸入或貼上您在步驟2中取得的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="b626e-186">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="b626e-187">在 [密碼] 方塊中, 輸入或貼上 APISecretKey (您在步驟2中取得的), 然後按一下 [**設定設定設定**] 以顯示 [設定**詳細資料**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="b626e-187">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

    ![](media/FBCimage43.png)


4. <span data-ttu-id="b626e-188">在 [設定**詳細資料**] 下, 輸入下列設定</span><span class="sxs-lookup"><span data-stu-id="b626e-188">Under **Configuration Details**, enter the following configuration settings</span></span> 

   <span data-ttu-id="b626e-189">– **Facebook 應用程式識別碼**–您在步驟5中取得之 Facebook 應用程式的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="b626e-189">– **Facebook application ID** – The app ID for the Facebook application that you obtained in Step 5.</span></span>
   <span data-ttu-id="b626e-190">– **Facebook 應用程式機密**–您在步驟5中取得的 Facebook 應用程式的應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="b626e-190">– **Facebook application secret** – The app secret for the Facebook application that you obtained in Step 5.</span></span>
   <span data-ttu-id="b626e-191">– **Facebook webhooks verify token** –您在步驟5中建立的 verify token。</span><span class="sxs-lookup"><span data-stu-id="b626e-191">– **Facebook webhooks verify token** – The verify token that you created in Step 5.</span></span>
   <span data-ttu-id="b626e-192">– **AAD 應用程式識別碼**–您在步驟2中建立之 Azure Active Directory 應用程式的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="b626e-192">– **AAD application ID** – The application ID for the Azure Active Directory app that you created in Step 2.</span></span>
   <span data-ttu-id="b626e-193">– **AAD 應用程式機密**–您在步驟4中建立之 APISecretKey 密碼的值。</span><span class="sxs-lookup"><span data-stu-id="b626e-193">– **AAD application secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   <span data-ttu-id="b626e-194">– **Aad 應用程式 uri** –在步驟2取得的 aad 應用程式 uri;例如, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213。</span><span class="sxs-lookup"><span data-stu-id="b626e-194">– **AAD application Uri** – The AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span></span>
   <span data-ttu-id="b626e-195">– **App insights 工具金鑰**–將此方塊保留空白。</span><span class="sxs-lookup"><span data-stu-id="b626e-195">– **App insights instrumentation key** – Leave this box blank.</span></span>

5. <span data-ttu-id="b626e-196">按一下 [**儲存**] 以儲存連接器設定。</span><span class="sxs-lookup"><span data-stu-id="b626e-196">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="b626e-197">步驟 7: 在安全性 & 規範中心內設定自訂連接器</span><span class="sxs-lookup"><span data-stu-id="b626e-197">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

1. <span data-ttu-id="b626e-198">移至<https://protection.office.com> , 然後按一下 [**資料\>控制\>匯入封存協力廠商資料**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-198">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

   ![](media/FBCimage44.png)

2.  <span data-ttu-id="b626e-199">按一下 [**新增連接器**], 然後按一下 [ **Facebook 頁面**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-199">Click **Add a connector** and then click **Facebook pages**.</span></span>

    ![](media/FBCimage46.png)

3.  <span data-ttu-id="b626e-200">在 [**新增連接器應用程式**] 頁面上, 輸入下列資訊, 然後按一下 [**驗證連接器**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-200">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    <span data-ttu-id="b626e-201">-在第一個方塊中, 輸入連接器的名稱, 例如**Facebook**。</span><span class="sxs-lookup"><span data-stu-id="b626e-201">– In the first box, type a name for the connector, such as **Facebook**.</span></span>
    <span data-ttu-id="b626e-202">-在第二個方塊中, 輸入或貼上您在步驟4中新增之 APISecretKey 的值。</span><span class="sxs-lookup"><span data-stu-id="b626e-202">– In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    <span data-ttu-id="b626e-203">-在第三個方塊中, 輸入或貼上 Azure 應用程式服務 URL;例如**https://fbconnector.azurewebsites.net**。</span><span class="sxs-lookup"><span data-stu-id="b626e-203">– In the third box, type or paste the Azure app service URL; for example **https://fbconnector.azurewebsites.net**.</span></span>
 
    <span data-ttu-id="b626e-204">成功驗證連接器之後, 按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b626e-204">After the connector is successfully validated, click **Next**.</span></span>
    
    ![](media/FBCimage47.png)

4.  <span data-ttu-id="b626e-205">按一下 **[使用連接器應用程式登**入]。</span><span class="sxs-lookup"><span data-stu-id="b626e-205">Click **Login with Connector App**.</span></span>

    ![](media/FBCimage45.png)

5. <span data-ttu-id="b626e-206">再次輸入或貼上 APISecretKey, 然後按一下 **[登入連接器服務**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-206">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![](media/FBCimage48.png)


6. <span data-ttu-id="b626e-207">按一下 **[以 Facebook 登**入]。</span><span class="sxs-lookup"><span data-stu-id="b626e-207">Click **Login with Facebook.**</span></span>

   ![](media/FBCimage49.png)

7. <span data-ttu-id="b626e-208">在 [**登入 Facebook** ] 頁面上, 使用組織的 Facebook 商務版頁面的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="b626e-208">On the **Log in to Facebook** page, log in using the credentials for the account for your organization’s Facebook Business pages.</span></span> <span data-ttu-id="b626e-209">請確定您登入的 Facebook 帳戶已指派給組織的 Facebook 商務頁面的系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="b626e-209">Make sure the Facebook account that you logged in to is assigned the admin role for your organization’s Facebook Business pages</span></span>

   ![](media/FBCimage50.png)

8. <span data-ttu-id="b626e-210">按一下 [**選取頁面**], 選擇您要在 Office 365 中封存的組織商務頁面。</span><span class="sxs-lookup"><span data-stu-id="b626e-210">Click **Select Pages** to choose your organization’s business pages that you want to archive in Office 365.</span></span>

   ![](media/FBCimage51.png)

9. <span data-ttu-id="b626e-211">您所登入的 Facebook 帳戶所管理的商務頁面清單會隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="b626e-211">A list of the Business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="b626e-212">選取要封存的頁面, 然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b626e-212">Select the page to archive and then click **Save**.</span></span>

    ![](media/FBCimage52.png)

10. <span data-ttu-id="b626e-213">按一下 [**準備**], 結束連接器服務應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="b626e-213">Click **prepare** to exit the setup of the connector service app.</span></span>

    ![](media/FBCimage53.png)

11. <span data-ttu-id="b626e-214">在 [**設定篩選**] 頁面上, 您可以套用篩選, 以匯入 (封存) 特定時期的專案。</span><span class="sxs-lookup"><span data-stu-id="b626e-214">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="b626e-215">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b626e-215">Click **Next**.</span></span>

    ![](media/FBCimage54.png)

12. <span data-ttu-id="b626e-216">在 [**設定儲存帳戶**] 頁面上, 選取您先前所選取之 Facebook 商務頁中的專案要匯入的 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="b626e-216">On the **Set Storage Account** page, select the Office 365 mailbox that the items from the Facebook Business pages that you previously selected will be imported to.</span></span>

    ![](media/FBCimage55.png)

13. <span data-ttu-id="b626e-217">檢查您的設定, 然後按一下 **[完成]** , 以完成安全性 & 規範中心內的連接器設定。</span><span class="sxs-lookup"><span data-stu-id="b626e-217">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![](media/FBCimage56.png)

14. <span data-ttu-id="b626e-218">移至「封存**協力廠商資料**」頁面, 以查看匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="b626e-218">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![](media/FBCimage58.png)
