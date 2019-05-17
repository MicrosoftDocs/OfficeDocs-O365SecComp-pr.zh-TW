---
title: 使用範例連接器，來封存 Twitter 資料在 Office 365 （預覽）
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 系統管理員可以設定原生連接器 Twitter 資料匯入至 Office 365。 這可讓您封存在 Office 365 中的協力廠商資料來源中的資料，所以您可以使用合規性功能，例如合法持有、 內容搜尋和保留原則來管理貴組織的協力廠商資料的控管。
ms.openlocfilehash: b561c5f471988e567624b49475bbf24a6dd88a2a
ms.sourcegitcommit: 5bd7a97aeab1c89e0a3660ba7bdb3200224107a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/16/2019
ms.locfileid: "34103848"
---
# <a name="use-a-sample-connector-to-archive-twitter-data-in-office-365-preview"></a>使用範例連接器，來封存 Twitter 資料在 Office 365 （預覽）

若要封存 Twitter Office 365 中的資料的範例連接器功能是在預覽。

使用安全性 & 在 Office 365 規範中心中的範例連接器，來匯入及封存資料從 Twitter。 設定後，當您設定範例連接器時，它連線到您的組織 Twitter 帳戶 （按照排程）、 將項目的內容轉換成電子郵件訊息的格式，並再將這些項目匯入至 Office 365 中的信箱。

在匯入 Twitter 資料之後，您可以套用 Office 365 符合性功能，例如訴訟暫止狀態，內容搜尋，就地封存、 稽核、 監督，與 Office 365 保留原則至信箱中所儲存的資料。 例如，您可以搜尋使用內容搜尋的協力廠商資料，或其關聯 custodian 進階電子文件探索案例中。 匯入和封存 Twitter 資料 Office 365 中的使用範例連接器，可協助組織符合規範與政府法規的原則。

> [!NOTE]
> 目前，只有 Twitter 和[Facebook 商務頁面](archive-facebook-data-with-sample-connector.md)的範例連接器可供預覽。 更多範例連接器即將推出。


## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a>Twitter 設定連接器的必要條件

您可以設定與設定安全性 & 匯入和封存資料從您的組織 Twitter 帳戶的合規性中心中的範例連接器之前，您必須完成下列必要條件。 

- 您需要 Twitter 帳戶為您的組織;您需要設定連接器時，登入到這個帳戶。

- 您的組織必須具有有效的 Azure 訂用帳戶。 如果您沒有現有的 Azure 訂用帳戶，您可以註冊其中一個選項：

    - [註冊免費 1 年 Azure 訂用帳戶](https://azure.microsoft.com/free) 

    - [註冊 Pay-As-You-Go Azure 訂用帳戶](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > 已內含於您的 Office 365 訂閱的[免費的 Azure Active Directory 訂閱](use-your-free-azure-ad-subscription-in-office-365.md)不支援的範例連接器中安全性 & 合規性中心。

- 您的組織必須同意允許存取您組織中的信箱資料的 Office 365 匯入服務。 若要同意這項要求，請移到[此頁面上](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，登入的 Office 365 全域管理員認證，並接受要求。

- 設定安全性 & 合規性 （步驟 7) 中的自訂連接器的使用者必須獲指派信箱匯入匯出角色在 Exchange Online。 根據預設，此角色不指派給任何角色群組在 Exchange Online。 您可以新增 「 信箱匯入 / 匯出 」 角色給組織管理角色群組在 Exchange Online。 或者，您可以建立新的角色群組、 指派 「 信箱匯入 / 匯出 」 角色，並再將適當的使用者新增為成員。 如需詳細資訊，請參閱 < 文件中的<b0>建立角色群組</b0>或<b1>修改角色群組</b1>區段 」 管理角色群組在 Exchange Online 」。

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a>步驟 1： 從 Github 下載預先內建的連接器應用程式套件

第一個步驟是下載 Twitter 範例連接器應用程式將用來連線到您的 Twitter 帳戶，並擷取資料，因此您可以將它匯入 Office 365 的 Twitter API 的程式碼。

1. 移至[這個 GitHub 網站](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)。 
2. [最新版本中，按一下 [ **SampleConnector.zip**檔案。
3. ZIP 檔案儲存到您本機電腦上的位置。 您將此 zip 檔案上傳到步驟 4 中的 Azure 中。

## <a name="step-2-create-an-app-in-azure-active-directory"></a>步驟 2： 在 Azure Active Directory 中建立的應用程式

下一步是註冊新的應用程式在 Azure Active Directory (AAD)。 此應用程式將會對應至將在步驟 4 中 Twitter 連接器實作的 web 應用程式資源。 

如需逐步指示，請參閱[步驟 2： 在 Azure Active Directory 中建立的應用程式](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory)。

期間完成此步驟中 （藉由遵循的逐步指示） 時，您會將下列資訊儲存到文字檔。 在部署程序稍後步驟，就會使用這些值。

- AAD 應用程式識別碼
- AAD 應用程式密碼
- AAD 應用程式的 Uri
- 租用戶識別碼

## <a name="step-3-create-an-azure-storage-account"></a>步驟 3： 建立 Azure 儲存體帳戶

為貴組織部署 Twitter 連接器將上傳您在此步驟中建立的 Azure 儲存體位置從 Twitter 的項目。 在安全性 & （在步驟 7) 的合規性中心建立自訂連接器之後，Office 365 匯入服務將 Twitter 將資料複製從 Azure 儲存體位置到 Office 365 中的信箱。 如同先前所述[的必要條件](#prerequisites-for-setting-up-a-connector-for-twitter)] 區段中，您必須建立 Azure 儲存體帳戶的有效 Azure 訂用帳戶。

如需逐步指示，請參閱[步驟 3： 建立 Azure 儲存體帳戶](deploy-twitter-connector.md#step-3-create-an-azure-storage-account)。

完成此步驟中 （藉由遵循的逐步指示） 的期間，您將儲存的連線字串產生的 Uri。 在步驟 4 中的 Azure 中建立 web 應用程式資源時，您將使用此字串。

## <a name="step-4-create-a-web-app-resource-in-azure"></a>步驟 4： 在 Azure 中建立 web 應用程式資源

下一步是在 Azure 中建立 web 應用程式資源 Twitter 連接器。 

如需逐步指示，請參閱[步驟 4： 在 Azure 中建立新的 web 應用程式資源](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure)。

期間完成此步驟中 （藉由遵循的逐步指示） 時，您將提供下列資訊 （完成上述步驟之後，您已複製到文字檔案） 時建立的 web 應用程式資源。

- APISecretKey – 您會在完成此步驟中; 的期間建立此密碼步驟 7 中，將使用它。
- StorageAccountConnectionString – 您在步驟 3 中建立 Azure 儲存體帳戶之後所複製的 Uri 的連接字串。
- tenantId – 您在步驟 2 中的 Azure Active Directory 中建立 Twitter 連接器應用程式之後複製您 Office 365 組織租用戶識別碼。

此外，您會在此步驟中部署 Twitter 連接器應用程式的原始碼上載 SampleConnector.zip （下載檔案，您在步驟 1 中）。

之後完成此步驟，請務必要複製之 Azure 應用程式服務 URL (例如， https://twitterconnector.azurewebsites.net)。 您將需要使用此功能來完成步驟 5、 步驟 6 和步驟 7）。

## <a name="step-5-create-developer-app-on-twitter"></a>步驟 5： 在 Twitter 上建立開發人員應用程式

下一步是建立和設定的應用程式開發人員在 Twitter 上。 您在步驟 7 中建立的自訂連接器會使用 Twitter 應用程式互動 Twitter API 以取得資料從您的組織 Twitter 帳戶。

如需逐步指示，請參閱[步驟 5： 建立 Twitter 應用程式](deploy-twitter-connector.md#step-5-create-the-twitter-app)。

期間完成此步驟中 （藉由遵循的逐步指示） 時，您會將下列資訊儲存到文字檔。 這些值會用於步驟 6 中設定 Twitter 連接器應用程式。

- 在 twitter 應用程式識別碼
- 在 twitter 應用程式密碼 （API 祕密金鑰）
- 在 twitter 用戶端權杖
- Twitter 語彙基元的用戶端密碼

## <a name="step-6-configure-the-twitter-connector-app"></a>步驟 6： 設定 Twitter 連接器應用程式

下一步是將組態設定新增至您上傳時您在步驟 4 中建立 Azure 的 web 應用程式資源 Twitter 連接器應用程式。 您將移至您的連接器應用程式的 [首頁] 頁面上，並設定其來這麼做。

如需逐步指示，請參閱[步驟 6： 設定連接器的 web 應用程式](deploy-twitter-connector.md#step-6-configure-the-connector-web-app)。

期間完成此步驟中 （藉由遵循的逐步指示） 時，您將提供下列資訊 （也就完成上述步驟之後，您已複製到文字檔案）：

- 在 twitter 應用程式識別碼 （在步驟 5 中所取得）
- 在 twitter 應用程式密碼 （在步驟 5 中所取得）
- 在 twitter 用戶端語彙基元 （在步驟 5 中所取得）
- 在 twitter 用戶端 token 密碼 （在步驟 5 中所取得）
- Azure Active Directory 應用程式識別碼 （在步驟 2 中所取得的 AAD 應用程式識別碼）
- Azure Active Directory 應用程式密碼 （在步驟 2 中所取得的 AAD 應用程式密碼）
- Azure Active Directory 應用程式的 Uri (AAD 應用程式的 Uri 取得在步驟 2; 例如，https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>步驟 7： 設立安全性 & 合規性中心中的自訂連接器

最後一個步驟是設定安全性 & 會從資料匯入您的組織 Twitter 帳戶指定的信箱，Office 365 中的規範中心中的自訂連接器。 您已成功完成此步驟之後，Office 365 匯入服務會啟動將資料從 Twitter 匯入 Office 365 的程序。 

如需逐步指示，請參閱[步驟 7： 設定安全性與合規性中心中的自訂連接器](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center)。 

期間完成此步驟中 （藉由遵循的逐步指示） 時，您將提供下列資訊 （也就完成步驟之後，您已複製到文字檔案）。

- Azure 應用程式服務的 URL (取得在步驟 4; 例如https://twitterconnector.azurewebsites.net)
- APISecretKey （，您在步驟 4 中建立）
