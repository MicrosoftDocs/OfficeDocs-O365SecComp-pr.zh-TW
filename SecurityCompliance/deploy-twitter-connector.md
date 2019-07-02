---
title: 在 Office 365 中部署連接器以封存 Twitter 資料
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
description: 系統管理員可以設定原生連接器, 將 Twitter 資料匯入和封存至 Office 365。 將此資料匯入 Office 365 之後, 您就可以使用合規性功能 (例如法律保留、內容搜尋和保留原則) 來管理組織的 Twitter 資料的管理。
ms.openlocfilehash: c3c5af0fc42057d9fc2e8b8e67423398d6ed0ddf
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014772"
---
# <a name="deploy-a-connector-to-archive-twitter-data-in-office-365"></a><span data-ttu-id="392f8-104">在 Office 365 中部署連接器以封存 Twitter 資料</span><span class="sxs-lookup"><span data-stu-id="392f8-104">Deploy a connector to archive Twitter data in Office 365</span></span>

<span data-ttu-id="392f8-105">本文包含以部署使用 Office 365 匯入服務將資料從組織的 Twitter 帳戶匯入 Office 365 的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="392f8-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Office 365.</span></span> <span data-ttu-id="392f8-106">如需此程式的高階概述以及部署 Twitter 連接器所需的必要條件清單, 請參閱[在 Office 365 中使用範例連接器封存 Twitter 資料 (預覽)](archive-twitter-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="392f8-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Use a sample connector to archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="392f8-107">步驟 1: 下載套件</span><span class="sxs-lookup"><span data-stu-id="392f8-107">Step 1: Download the package</span></span>

<span data-ttu-id="392f8-108">從 GitHub 存放庫的版本章節下載預建套件, 網址[https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)為。</span><span class="sxs-lookup"><span data-stu-id="392f8-108">Download the prebuilt package from the Release section in the GitHub repository at [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> <span data-ttu-id="392f8-109">在最新的版本下, 下載名為**SampleConnector**的 zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="392f8-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="392f8-110">在步驟4中, 您將此 zip 檔案上傳至 Azure。</span><span class="sxs-lookup"><span data-stu-id="392f8-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="392f8-111">步驟 2: 在 Azure Active Directory 中建立應用程式</span><span class="sxs-lookup"><span data-stu-id="392f8-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="392f8-112">移至<https://portal.azure.com> , 並使用 Office 365 全域系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="392f8-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![](media/TCimage01.png)

2. <span data-ttu-id="392f8-113">在左功能窗格中, 按一下 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-113">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![](media/TCimage02.png)

3. <span data-ttu-id="392f8-114">在左功能窗格中, 按一下 **[應用程式註冊] ([預覽])** , 然後按一下 [**新增註冊**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-114">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![](media/TCimage03.png)

4. <span data-ttu-id="392f8-115">註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="392f8-115">Register the application.</span></span> <span data-ttu-id="392f8-116">在 [重新**導向 URI (選用)**] 下, 選取 [應用程式類型] 下拉式<https://portal.azure.com>清單中的 [Web], 然後輸入 URI 的方塊中。</span><span class="sxs-lookup"><span data-stu-id="392f8-116">Under **Redirect URI (optional)**, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![](media/TCimage04.png)

5. <span data-ttu-id="392f8-117">複製**應用程式 (用戶端) 識別碼**和**目錄 (租**使用者) 識別碼, 並將它們儲存到文字檔或其他安全的位置。</span><span class="sxs-lookup"><span data-stu-id="392f8-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="392f8-118">您可以在稍後的步驟中使用這些識別碼。</span><span class="sxs-lookup"><span data-stu-id="392f8-118">You use these IDs in later steps.</span></span>

    ![](media/TCimage05.png)

6. <span data-ttu-id="392f8-119">移至**新應用程式的憑證 & 機密**, 然後按一下 [**客戶**端密碼] 下的 [**新增用戶端密碼**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-119">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![](media/TCimage06.png)

7. <span data-ttu-id="392f8-120">建立新的密碼。</span><span class="sxs-lookup"><span data-stu-id="392f8-120">Create a new secret.</span></span> <span data-ttu-id="392f8-121">在 [描述] 方塊中, 輸入密碼, 然後選擇到期時間。</span><span class="sxs-lookup"><span data-stu-id="392f8-121">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![](media/TCimage08.png)

8. <span data-ttu-id="392f8-122">複製機密的值, 並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="392f8-122">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="392f8-123">這是您在稍後步驟中使用的 AAD 應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="392f8-123">This is the AAD application secret that you use in later steps.</span></span>

   ![](media/TCimage09.png)

9. <span data-ttu-id="392f8-124">請移至**資訊清單**, 並複製 identifierUris (也稱為 AAD 應用程式 Uri), 如下列螢幕擷取畫面所示。</span><span class="sxs-lookup"><span data-stu-id="392f8-124">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="392f8-125">將 AAD 應用程式 Uri 複製到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="392f8-125">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="392f8-126">您可以在步驟6中使用。</span><span class="sxs-lookup"><span data-stu-id="392f8-126">You use it in Step 6.</span></span>

    ![](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="392f8-127">步驟 3: 建立 Azure 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="392f8-127">Step 3: Create an Azure storage account</span></span>

1.  <span data-ttu-id="392f8-128">移至您組織的 Azure 首頁。</span><span class="sxs-lookup"><span data-stu-id="392f8-128">Go to the Azure home page for your organization.</span></span>

    ![](media/TCimage11.png)

2. <span data-ttu-id="392f8-129">按一下 [**建立資源**], 然後在 [搜尋] 方塊中輸入 [**儲存帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-129">Click **Create a resource** and they type **storage account** in the search box.</span></span>

   ![](media/TCimage12.png)

3. <span data-ttu-id="392f8-130">按一下 [**儲存**], 然後按一下 [**儲存帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-130">Click **Storage**, and then click **Storage account**.</span></span>

   ![](media/TCimage13.png)

4. <span data-ttu-id="392f8-131">在 [**建立儲存帳戶**] 頁面上的 [訂閱] 方塊中, 根據您擁有的 Azure 訂閱類型, 選取 [**隨**選即用] 或 [**免費試用**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-131">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> 

   ![](media/TCimage14.png)

5. <span data-ttu-id="392f8-132">選取或建立資源群組。</span><span class="sxs-lookup"><span data-stu-id="392f8-132">Select or create a resource group.</span></span>

   ![](media/TCimage15.png)

6. <span data-ttu-id="392f8-133">輸入儲存帳戶的名稱。</span><span class="sxs-lookup"><span data-stu-id="392f8-133">Type a name for the storage account.</span></span>

   ![](media/TCimage16.png)

7. <span data-ttu-id="392f8-134">檢查, 然後按一下 [**建立**] 以建立儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="392f8-134">Review and then click **Create** to create the storage account.</span></span>

   ![](media/TCimage17.png)

8. <span data-ttu-id="392f8-135">幾分鐘後, 按一下 [ \*\*\*\* 重新整理], 然後按一下 [**移至資源**] 以流覽至儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="392f8-135">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

   ![](media/TCimage18.png)

9. <span data-ttu-id="392f8-136">按一下左功能窗格中的 [**訪問金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-136">Click **Access keys** in the left navigation pane.</span></span>

   ![](media/TCimage19.png)

10. <span data-ttu-id="392f8-137">複製**連接字串**, 並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="392f8-137">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="392f8-138">在步驟4中建立 web 應用程式資源時, 您可以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="392f8-138">You use this when creating a web app resource in Step 4.</span></span>

    ![](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="392f8-139">步驟 4: 在 Azure 中建立新的 web 應用程式資源</span><span class="sxs-lookup"><span data-stu-id="392f8-139">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="392f8-140">在 Azure 入口網站的**首頁**上, 按一下 [**建立所有\> Web \>應用程式的資源**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-140">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="392f8-141">在 [ **Web 應用程式**] 頁面上, 按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-141">On the **Web app** page, click **Create**.</span></span>

   ![](media/TCimage21.png)

2. <span data-ttu-id="392f8-142">填寫詳細資料 (如下所示), 然後再建立 Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="392f8-142">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="392f8-143">您在 [**應用程式名稱**] 方塊中輸入的名稱, 是用來建立 Azure 應用程式服務 URL;例如, twitterconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="392f8-143">The name that you enter in the **App name** box is used to create the Azure app service URL; for example, twitterconnector.azurewebsites.net.</span></span>

   ![](media/TCimage22.png)

3. <span data-ttu-id="392f8-144">移至新建立的 web 應用程式資源, 然後按一下左功能窗格中的 [**應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-144">Go to the newly created web app resource and click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="392f8-145">在 [**應用程式設定**] 下, 按一下 [**新增設定**], 然後新增下列三個設定。</span><span class="sxs-lookup"><span data-stu-id="392f8-145">Under **Application settings**, click **Add new setting** and add the following three settings.</span></span> <span data-ttu-id="392f8-146">使用這些值 (您從先前的步驟複製到文字檔):</span><span class="sxs-lookup"><span data-stu-id="392f8-146">Use the values (that you copied to the text file from the previous steps):</span></span> 

    <span data-ttu-id="392f8-147">– \* \* APISecretKey-您可以輸入任何值作為密碼。</span><span class="sxs-lookup"><span data-stu-id="392f8-147">– \*\*APISecretKey — You can type any value as the secret.</span></span> <span data-ttu-id="392f8-148">這是用來存取步驟7中的連接器 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="392f8-148">This is used to access the connector web app in Step 7.</span></span>

    <span data-ttu-id="392f8-149">– **StorageAccountConnectionString** –在步驟3建立 Azure 儲存體帳戶之後複製的連接字串 Uri。</span><span class="sxs-lookup"><span data-stu-id="392f8-149">– **StorageAccountConnectionString** – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    <span data-ttu-id="392f8-150">– **tenantId** –您在步驟2中建立 Azure Active Directory 中的 Twitter 連接器應用程式後所複製之 Office 365 組織的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="392f8-150">– **tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

    ![](media/TCimage23.png)

4. <span data-ttu-id="392f8-151">在 **[一般設定**] \*\*\*\* 下, 按一下 [ **Always on**] 旁的 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="392f8-151">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="392f8-152">按一下頁面頂端的 [**儲存**] 以儲存應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="392f8-152">Click **Save** at the top of the page to save the application settings.</span></span>

   ![](media/TCimage24.png)

5. <span data-ttu-id="392f8-153">最後一個步驟是將連接器應用程式原始程式碼上傳至您在步驟1下載的 Azure。</span><span class="sxs-lookup"><span data-stu-id="392f8-153">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="392f8-154">在網頁瀏覽器中, 移至<AzureAppResourceName>HTTPs://。</span><span class="sxs-lookup"><span data-stu-id="392f8-154">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="392f8-155">例如, 如果您的 Azure 應用程式資源名稱 (在本節步驟2中命名為**twitterconnector**), 則您會前往https://twitterconnector.scm.azurewebsites.net/ZipDeployUi。</span><span class="sxs-lookup"><span data-stu-id="392f8-155">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **twitterconnector**, then you would go to https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span></span>

6. <span data-ttu-id="392f8-156">將 SampleConnector 的 .zip (您在步驟1下載) 拖放至此頁面。</span><span class="sxs-lookup"><span data-stu-id="392f8-156">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="392f8-157">上載檔案並成功部署後, 頁面看起來會類似下列螢幕擷取畫面:</span><span class="sxs-lookup"><span data-stu-id="392f8-157">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a><span data-ttu-id="392f8-158">步驟 5: 建立 Twitter 應用程式</span><span class="sxs-lookup"><span data-stu-id="392f8-158">Step 5: Create the Twitter app</span></span>

1. <span data-ttu-id="392f8-159">請移https://developer.twitter.com至, 使用組織的開發人員帳戶的認證登入, 然後按一下 [**應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-159">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![TCimage25-5 .png](media/TCimage25-5.png)
2. <span data-ttu-id="392f8-161">按一下 [**建立應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-161">Click **Create an app**.</span></span>
   
   ![](media/TCimage26.png)

3. <span data-ttu-id="392f8-162">在 [**應用程式詳細資料**] 下, 新增應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="392f8-162">Under **App details**, add information about the application.</span></span>

   ![](media/TCimage27.png)

4. <span data-ttu-id="392f8-163">在 [Twitter 開發人員] 儀表板上, 選取您剛建立的應用程式, 並複製所顯示的應用程式識別碼, 並將其儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="392f8-163">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="392f8-164">然後按一下 [**詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-164">Then click **Details**.</span></span>
   
   ![](media/TCimage28.png)

5. <span data-ttu-id="392f8-165">在 [ \*\*\*\* 索引標籤] 索引標籤的 [**使用者 api 機碼**] 下, 複製 API 金鑰, 並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="392f8-165">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="392f8-166">然後按一下 [**建立**] 以產生存取權杖和存取權杖機密, 並將它們複製到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="392f8-166">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![](media/TCimage29.png)

   <span data-ttu-id="392f8-167">然後按一下 [**建立**] 以產生存取權杖和存取權杖機密, 並將它們複製到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="392f8-167">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="392f8-168">按一下 [**許可權**] 索引標籤, 並設定許可權, 如下列螢幕擷取畫面所示:</span><span class="sxs-lookup"><span data-stu-id="392f8-168">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![](media/TCimage30.png)

7. <span data-ttu-id="392f8-169">在您儲存許可權設定後, 按一下 [**應用程式詳細資料**] 索引標籤, 然後按一下 [**編輯 > 編輯詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-169">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![](media/TCimage31.png)

8. <span data-ttu-id="392f8-170">請執行下列工作:</span><span class="sxs-lookup"><span data-stu-id="392f8-170">Do the following tasks:</span></span>

   <span data-ttu-id="392f8-171">–選取此核取方塊可允許連接器應用程式登入 Twitter。</span><span class="sxs-lookup"><span data-stu-id="392f8-171">– Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   <span data-ttu-id="392f8-172">–使用下列格式新增 OAuth 重新導向 Uri: \*\* \<connectorserviceuri>/views/twitteroauth\**, 其中*connectorserviceuri\*的值是您組織的 Azure 應用程式服務 URL;例如, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth。</span><span class="sxs-lookup"><span data-stu-id="392f8-172">– Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

   ![](media/TCimage32.png)

<span data-ttu-id="392f8-173">現在可以使用 Twitter 開發人員應用程式。</span><span class="sxs-lookup"><span data-stu-id="392f8-173">The Twitter developer app is now ready to use.</span></span>

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="392f8-174">步驟 6: 設定連接器 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="392f8-174">Step 6: Configure the connector web app</span></span> 

1. <span data-ttu-id="392f8-175">移至 HTTPs://\<AzureAppResourceName> azurewebsites.net (其中**AzureAppResourceName**是您在步驟4中命名的 Azure 應用程式資源名稱)。</span><span class="sxs-lookup"><span data-stu-id="392f8-175">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="392f8-176">例如, 如果名稱為**twitterconnector**, 請移至https://twitterconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="392f8-176">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="392f8-177">應用程式的首頁看起來像下列螢幕擷取畫面:</span><span class="sxs-lookup"><span data-stu-id="392f8-177">The home page of the app looks like the following screenshot:</span></span>

   ![](media/FBCimage41.png)

2. <span data-ttu-id="392f8-178">按一下 [**設定**] 以顯示登入頁面。</span><span class="sxs-lookup"><span data-stu-id="392f8-178">Click **Configure** to display a sign in page.</span></span>

   ![](media/FBCimage42.png)

3. <span data-ttu-id="392f8-179">在 [租使用者識別碼] 方塊中, 輸入或貼上您在步驟2中取得的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="392f8-179">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="392f8-180">在 [密碼] 方塊中, 輸入或貼上 APISecretKey (您在步驟2中取得的), 然後按一下 [**設定設定設定**] 以顯示 [設定**詳細資料**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="392f8-180">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

   ![](media/TCimage35.png)

4. <span data-ttu-id="392f8-181">在 [設定**詳細資料**] 下, 輸入下列設定</span><span class="sxs-lookup"><span data-stu-id="392f8-181">Under **Configuration Details**, enter the following configuration settings</span></span> 

   <span data-ttu-id="392f8-182">– **Twitter Api Key** –您在步驟5中建立之 Twitter 應用程式的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="392f8-182">– **Twitter Api Key** – The app ID for the Twitter application that you created in Step 5.</span></span>
   <span data-ttu-id="392f8-183">– **Twitter api**金鑰–您在步驟5中建立之 Twitter 應用程式的 Api 金鑰。</span><span class="sxs-lookup"><span data-stu-id="392f8-183">– **Twitter Api Secret Key** – The API secret key for the Twitter application that you created in Step 5.</span></span>
   <span data-ttu-id="392f8-184">– **Twitter 存取 token** –您在步驟5中建立的存取權杖。</span><span class="sxs-lookup"><span data-stu-id="392f8-184">– **Twitter Access Token** – The access token that you created in Step 5.</span></span>
   <span data-ttu-id="392f8-185">– **Twitter 存取 Token 機密**–您在步驟5中建立的存取權杖機密。</span><span class="sxs-lookup"><span data-stu-id="392f8-185">– **Twitter Access Token Secret** – The access token secret that you created in Step 5.</span></span>
   <span data-ttu-id="392f8-186">– **AAD 應用程式識別碼**–您在步驟2– **AAD 應用程式機密**中建立之 Azure Active Directory 應用程式的應用程式識別碼–您在步驟4中建立之 APISecretKey 密碼的值。</span><span class="sxs-lookup"><span data-stu-id="392f8-186">– **AAD Application ID** – The application ID for the Azure Active Directory app that you created in Step 2 – **AAD Application Secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   <span data-ttu-id="392f8-187">– **Aad 應用程式 uri** –在步驟2取得的 aad 應用程式 uri;例如, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213。</span><span class="sxs-lookup"><span data-stu-id="392f8-187">– **AAD Application Uri** – The AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span></span>
   <span data-ttu-id="392f8-188">– **App Insights 工具金鑰**–將此方塊保留空白。</span><span class="sxs-lookup"><span data-stu-id="392f8-188">– **App Insights Instrumentation Key** – Leave this box blank.</span></span>

5. <span data-ttu-id="392f8-189">按一下 [**儲存**] 以儲存連接器設定。</span><span class="sxs-lookup"><span data-stu-id="392f8-189">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a><span data-ttu-id="392f8-190">步驟 7: 在安全性與合規性中心設定自訂連接器</span><span class="sxs-lookup"><span data-stu-id="392f8-190">Step 7: Set up a custom connector in the security and compliance center</span></span>

1.  <span data-ttu-id="392f8-191">移至<https://protection.office.com> , 然後按一下 [**資料\>控制\>匯入封存協力廠商資料**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-191">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

    ![](media/TCimage36.png)

2. <span data-ttu-id="392f8-192">按一下 [**新增連接器**], 然後按一下 [ **Twitter**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-192">Click **Add a connector** and then click **Twitter**.</span></span>

   ![](media/TCimage37.png)

3. <span data-ttu-id="392f8-193">在 [**新增連接器應用程式**] 頁面上, 輸入下列資訊, 然後按一下 [**驗證連接器**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-193">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    <span data-ttu-id="392f8-194">-在第一個方塊中, 輸入連接器的名稱, 例如**Twitter**。</span><span class="sxs-lookup"><span data-stu-id="392f8-194">– In the first box, type a name for the connector, such as **Twitter**.</span></span>
    <span data-ttu-id="392f8-195">-在第二個方塊中, 輸入或貼上您在步驟4中新增之 APISecretKey 的值。</span><span class="sxs-lookup"><span data-stu-id="392f8-195">– In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    <span data-ttu-id="392f8-196">-在第三個方塊中, 輸入或貼上 Azure 應用程式服務 URL;例如, **https://twitterconnector.azurewebsites.net**。</span><span class="sxs-lookup"><span data-stu-id="392f8-196">– In the third box, type or paste the Azure app service URL; for example, **https://twitterconnector.azurewebsites.net**.</span></span>

   <span data-ttu-id="392f8-197">成功驗證連接器之後, 按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="392f8-197">After the connector is successfully validated, click **Next**.</span></span>

   ![](media/TCimage38.png)

4. <span data-ttu-id="392f8-198">按一下 **[使用連接器應用程式登**入]。</span><span class="sxs-lookup"><span data-stu-id="392f8-198">Click **Login with Connector App**.</span></span>

   ![](media/TCimage39.png)

5. <span data-ttu-id="392f8-199">再次輸入或貼上 APISecretKey, 然後按一下 **[登入連接器服務**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-199">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![](media/TCimage40.png)


6. <span data-ttu-id="392f8-200">按一下 [**繼續使用 Twitter**]。</span><span class="sxs-lookup"><span data-stu-id="392f8-200">Click **Continue with Twitter**.</span></span>

7. <span data-ttu-id="392f8-201">在 [Twitter 登入] 頁面上, 使用您組織的 Twitter 帳戶的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="392f8-201">On the Twitter sign in page, sign in using the credentials for the account for your organization’s Twitter account.</span></span>

   ![](media/TCimage42.png)

   <span data-ttu-id="392f8-202">登入後, Twitter 頁面會顯示下列訊息: 「已成功設定 Twitter 連接器工作」。</span><span class="sxs-lookup"><span data-stu-id="392f8-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

8. <span data-ttu-id="392f8-203">按一下 **[完成]** , 以完成 Twitter 連接器的設定。</span><span class="sxs-lookup"><span data-stu-id="392f8-203">Click **Finish** to complete setting up the Twitter connector.</span></span>

9. <span data-ttu-id="392f8-204">在 [**設定篩選**] 頁面上, 您可以套用篩選, 以匯入 (封存) 特定時期的專案。</span><span class="sxs-lookup"><span data-stu-id="392f8-204">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="392f8-205">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="392f8-205">Click **Next**.</span></span>

   ![](media/TCimage44.png)

10. <span data-ttu-id="392f8-206">在 [**設定儲存帳戶**] 頁面上, 輸入將會匯入 Twitter 專案的 Office 365 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="392f8-206">On the **Set Storage Account** page, type the email address of an Office 365 mailbox that the Twitter items will be imported to.</span></span>

    ![](media/TCimage45.png)

11. <span data-ttu-id="392f8-207">檢查您的設定, 然後按一下 **[完成]** , 以完成安全性 & 規範中心內的連接器設定。</span><span class="sxs-lookup"><span data-stu-id="392f8-207">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![](media/TCimage46.png)

    ![](media/TCimage47.png)

12. <span data-ttu-id="392f8-208">移至「封存**協力廠商資料**」頁面, 以查看匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="392f8-208">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![](media/TCimage48.png)
