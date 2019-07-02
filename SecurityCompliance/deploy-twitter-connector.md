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
# <a name="deploy-a-connector-to-archive-twitter-data-in-office-365"></a>在 Office 365 中部署連接器以封存 Twitter 資料

本文包含以部署使用 Office 365 匯入服務將資料從組織的 Twitter 帳戶匯入 Office 365 的逐步程式。 如需此程式的高階概述以及部署 Twitter 連接器所需的必要條件清單, 請參閱[在 Office 365 中使用範例連接器封存 Twitter 資料 (預覽)](archive-twitter-data-with-sample-connector.md)。 

## <a name="step-1-download-the-package"></a>步驟 1: 下載套件

從 GitHub 存放庫的版本章節下載預建套件, 網址[https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)為。 在最新的版本下, 下載名為**SampleConnector**的 zip 檔案。 在步驟4中, 您將此 zip 檔案上傳至 Azure。

## <a name="step-2-create-an-app-in-azure-active-directory"></a>步驟 2: 在 Azure Active Directory 中建立應用程式

1. 移至<https://portal.azure.com> , 並使用 Office 365 全域系統管理員帳戶的認證登入。

   ![](media/TCimage01.png)

2. 在左功能窗格中, 按一下 [ **Azure Active Directory**]。

   ![](media/TCimage02.png)

3. 在左功能窗格中, 按一下 **[應用程式註冊] ([預覽])** , 然後按一下 [**新增註冊**]。

   ![](media/TCimage03.png)

4. 註冊應用程式。 在 [重新**導向 URI (選用)**] 下, 選取 [應用程式類型] 下拉式<https://portal.azure.com>清單中的 [Web], 然後輸入 URI 的方塊中。

   ![](media/TCimage04.png)

5. 複製**應用程式 (用戶端) 識別碼**和**目錄 (租**使用者) 識別碼, 並將它們儲存到文字檔或其他安全的位置。 您可以在稍後的步驟中使用這些識別碼。

    ![](media/TCimage05.png)

6. 移至**新應用程式的憑證 & 機密**, 然後按一下 [**客戶**端密碼] 下的 [**新增用戶端密碼**]。

   ![](media/TCimage06.png)

7. 建立新的密碼。 在 [描述] 方塊中, 輸入密碼, 然後選擇到期時間。 

   ![](media/TCimage08.png)

8. 複製機密的值, 並將它儲存到文字檔或其他儲存位置。 這是您在稍後步驟中使用的 AAD 應用程式密碼。

   ![](media/TCimage09.png)

9. 請移至**資訊清單**, 並複製 identifierUris (也稱為 AAD 應用程式 Uri), 如下列螢幕擷取畫面所示。 將 AAD 應用程式 Uri 複製到文字檔或其他儲存位置。 您可以在步驟6中使用。

    ![](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a>步驟 3: 建立 Azure 儲存體帳戶

1.  移至您組織的 Azure 首頁。

    ![](media/TCimage11.png)

2. 按一下 [**建立資源**], 然後在 [搜尋] 方塊中輸入 [**儲存帳戶**]。

   ![](media/TCimage12.png)

3. 按一下 [**儲存**], 然後按一下 [**儲存帳戶**]。

   ![](media/TCimage13.png)

4. 在 [**建立儲存帳戶**] 頁面上的 [訂閱] 方塊中, 根據您擁有的 Azure 訂閱類型, 選取 [**隨**選即用] 或 [**免費試用**]。 

   ![](media/TCimage14.png)

5. 選取或建立資源群組。

   ![](media/TCimage15.png)

6. 輸入儲存帳戶的名稱。

   ![](media/TCimage16.png)

7. 檢查, 然後按一下 [**建立**] 以建立儲存體帳戶。

   ![](media/TCimage17.png)

8. 幾分鐘後, 按一下 [ **** 重新整理], 然後按一下 [**移至資源**] 以流覽至儲存體帳戶。

   ![](media/TCimage18.png)

9. 按一下左功能窗格中的 [**訪問金鑰**]。

   ![](media/TCimage19.png)

10. 複製**連接字串**, 並將它儲存到文字檔或其他儲存位置。 在步驟4中建立 web 應用程式資源時, 您可以使用此功能。

    ![](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a>步驟 4: 在 Azure 中建立新的 web 應用程式資源

1. 在 Azure 入口網站的**首頁**上, 按一下 [**建立所有\> Web \>應用程式的資源**]。 在 [ **Web 應用程式**] 頁面上, 按一下 [**建立**]。

   ![](media/TCimage21.png)

2. 填寫詳細資料 (如下所示), 然後再建立 Web 應用程式。 您在 [**應用程式名稱**] 方塊中輸入的名稱, 是用來建立 Azure 應用程式服務 URL;例如, twitterconnector.azurewebsites.net。

   ![](media/TCimage22.png)

3. 移至新建立的 web 應用程式資源, 然後按一下左功能窗格中的 [**應用程式設定**]。 在 [**應用程式設定**] 下, 按一下 [**新增設定**], 然後新增下列三個設定。 使用這些值 (您從先前的步驟複製到文字檔): 

    – * * APISecretKey-您可以輸入任何值作為密碼。 這是用來存取步驟7中的連接器 web 應用程式。

    – **StorageAccountConnectionString** –在步驟3建立 Azure 儲存體帳戶之後複製的連接字串 Uri。

    – **tenantId** –您在步驟2中建立 Azure Active Directory 中的 Twitter 連接器應用程式後所複製之 Office 365 組織的租使用者識別碼。

    ![](media/TCimage23.png)

4. 在 **[一般設定**] **** 下, 按一下 [ **Always on**] 旁的 [下一步]。 按一下頁面頂端的 [**儲存**] 以儲存應用程式設定。

   ![](media/TCimage24.png)

5. 最後一個步驟是將連接器應用程式原始程式碼上傳至您在步驟1下載的 Azure。 在網頁瀏覽器中, 移至<AzureAppResourceName>HTTPs://。 例如, 如果您的 Azure 應用程式資源名稱 (在本節步驟2中命名為**twitterconnector**), 則您會前往https://twitterconnector.scm.azurewebsites.net/ZipDeployUi。

6. 將 SampleConnector 的 .zip (您在步驟1下載) 拖放至此頁面。 上載檔案並成功部署後, 頁面看起來會類似下列螢幕擷取畫面:

   ![](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a>步驟 5: 建立 Twitter 應用程式

1. 請移https://developer.twitter.com至, 使用組織的開發人員帳戶的認證登入, 然後按一下 [**應用程式**]。

   ![TCimage25-5 .png](media/TCimage25-5.png)
2. 按一下 [**建立應用程式**]。
   
   ![](media/TCimage26.png)

3. 在 [**應用程式詳細資料**] 下, 新增應用程式的相關資訊。

   ![](media/TCimage27.png)

4. 在 [Twitter 開發人員] 儀表板上, 選取您剛建立的應用程式, 並複製所顯示的應用程式識別碼, 並將其儲存到文字檔或其他儲存位置。 然後按一下 [**詳細資料**]。
   
   ![](media/TCimage28.png)

5. 在 [ **** 索引標籤] 索引標籤的 [**使用者 api 機碼**] 下, 複製 API 金鑰, 並將它儲存到文字檔或其他儲存位置。 然後按一下 [**建立**] 以產生存取權杖和存取權杖機密, 並將它們複製到文字檔或其他儲存位置。
   
   ![](media/TCimage29.png)

   然後按一下 [**建立**] 以產生存取權杖和存取權杖機密, 並將它們複製到文字檔或其他儲存位置。

6. 按一下 [**許可權**] 索引標籤, 並設定許可權, 如下列螢幕擷取畫面所示:

   ![](media/TCimage30.png)

7. 在您儲存許可權設定後, 按一下 [**應用程式詳細資料**] 索引標籤, 然後按一下 [**編輯 > 編輯詳細資料**]。

   ![](media/TCimage31.png)

8. 請執行下列工作:

   –選取此核取方塊可允許連接器應用程式登入 Twitter。
   
   –使用下列格式新增 OAuth 重新導向 Uri: ** \<connectorserviceuri>/views/twitteroauth**, 其中*connectorserviceuri*的值是您組織的 Azure 應用程式服務 URL;例如, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth。

   ![](media/TCimage32.png)

現在可以使用 Twitter 開發人員應用程式。

## <a name="step-6-configure-the-connector-web-app"></a>步驟 6: 設定連接器 web 應用程式 

1. 移至 HTTPs://\<AzureAppResourceName> azurewebsites.net (其中**AzureAppResourceName**是您在步驟4中命名的 Azure 應用程式資源名稱)。 例如, 如果名稱為**twitterconnector**, 請移至https://twitterconnector.azurewebsites.net。 應用程式的首頁看起來像下列螢幕擷取畫面:

   ![](media/FBCimage41.png)

2. 按一下 [**設定**] 以顯示登入頁面。

   ![](media/FBCimage42.png)

3. 在 [租使用者識別碼] 方塊中, 輸入或貼上您在步驟2中取得的租使用者識別碼。 在 [密碼] 方塊中, 輸入或貼上 APISecretKey (您在步驟2中取得的), 然後按一下 [**設定設定設定**] 以顯示 [設定**詳細資料**] 頁面。

   ![](media/TCimage35.png)

4. 在 [設定**詳細資料**] 下, 輸入下列設定 

   – **Twitter Api Key** –您在步驟5中建立之 Twitter 應用程式的應用程式識別碼。
   – **Twitter api**金鑰–您在步驟5中建立之 Twitter 應用程式的 Api 金鑰。
   – **Twitter 存取 token** –您在步驟5中建立的存取權杖。
   – **Twitter 存取 Token 機密**–您在步驟5中建立的存取權杖機密。
   – **AAD 應用程式識別碼**–您在步驟2– **AAD 應用程式機密**中建立之 Azure Active Directory 應用程式的應用程式識別碼–您在步驟4中建立之 APISecretKey 密碼的值。
   – **Aad 應用程式 uri** –在步驟2取得的 aad 應用程式 uri;例如, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213。
   – **App Insights 工具金鑰**–將此方塊保留空白。

5. 按一下 [**儲存**] 以儲存連接器設定。

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a>步驟 7: 在安全性與合規性中心設定自訂連接器

1.  移至<https://protection.office.com> , 然後按一下 [**資料\>控制\>匯入封存協力廠商資料**]。

    ![](media/TCimage36.png)

2. 按一下 [**新增連接器**], 然後按一下 [ **Twitter**]。

   ![](media/TCimage37.png)

3. 在 [**新增連接器應用程式**] 頁面上, 輸入下列資訊, 然後按一下 [**驗證連接器**]。

    -在第一個方塊中, 輸入連接器的名稱, 例如**Twitter**。
    -在第二個方塊中, 輸入或貼上您在步驟4中新增之 APISecretKey 的值。
    -在第三個方塊中, 輸入或貼上 Azure 應用程式服務 URL;例如, **https://twitterconnector.azurewebsites.net**。

   成功驗證連接器之後, 按 **[下一步]**。

   ![](media/TCimage38.png)

4. 按一下 **[使用連接器應用程式登**入]。

   ![](media/TCimage39.png)

5. 再次輸入或貼上 APISecretKey, 然後按一下 **[登入連接器服務**]。

   ![](media/TCimage40.png)


6. 按一下 [**繼續使用 Twitter**]。

7. 在 [Twitter 登入] 頁面上, 使用您組織的 Twitter 帳戶的帳戶登入。

   ![](media/TCimage42.png)

   登入後, Twitter 頁面會顯示下列訊息: 「已成功設定 Twitter 連接器工作」。

8. 按一下 **[完成]** , 以完成 Twitter 連接器的設定。

9. 在 [**設定篩選**] 頁面上, 您可以套用篩選, 以匯入 (封存) 特定時期的專案。 按 [下一步]****。

   ![](media/TCimage44.png)

10. 在 [**設定儲存帳戶**] 頁面上, 輸入將會匯入 Twitter 專案的 Office 365 信箱的電子郵件地址。

    ![](media/TCimage45.png)

11. 檢查您的設定, 然後按一下 **[完成]** , 以完成安全性 & 規範中心內的連接器設定。

    ![](media/TCimage46.png)

    ![](media/TCimage47.png)

12. 移至「封存**協力廠商資料**」頁面, 以查看匯入程式的進度。

    ![](media/TCimage48.png)
