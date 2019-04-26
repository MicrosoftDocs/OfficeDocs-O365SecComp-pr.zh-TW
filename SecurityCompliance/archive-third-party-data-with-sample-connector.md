---
title: 使用範例連接器來封存 Office 365 （預覽） 中的協力廠商資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 系統管理員可以設定協力廠商資料匯入 Facebook 商務頁面、 LinkedIn 公司頁面等立即 Bloomberg 資料來源的原生的連接器。 這可讓您封存在 Office 365 中的協力廠商資料來源中的資料，所以您可以使用合規性功能，例如合法持有、 內容搜尋和保留原則來管理貴組織的協力廠商資料的控管。
ms.openlocfilehash: bca193753d0a63de867bdb11cfce3918c124f429
ms.sourcegitcommit: 63a10dc5ffa9d709fac437d3fc9e554b1bcd826f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/25/2019
ms.locfileid: "33307826"
---
# <a name="use-sample-connectors-to-archive-third-party-data-in-office-365-preview"></a>使用範例連接器來封存 Office 365 （預覽） 中的協力廠商資料

若要封存 Office 365 中的協力廠商資料的範例連接器功能是在預覽。

使用安全性 & 在 Office 365 規範中心中的範例連接器，來匯入及封存如 Facebook、 LinkedIn、 Twitter 和 Bloomberg 協力廠商資料來源中的資料。 設定後，當您設定範例連接器時，它連接至 （按照排程） 的協力廠商資料來源、 將項目的內容轉換成電子郵件訊息的格式，並再將這些項目匯入至 Office 365 中的信箱。

協力廠商資料匯入之後，您可以將 Office 365 符合性功能，例如訴訟暫止狀態，內容搜尋、 就地封存、 稽核、 監督，與 Office 365 保留原則套用至協力廠商資料。 例如，當信箱處於訴訟暫止狀態或指派到保留原則時，仍會保留協力廠商資料。 您可以搜尋協力廠商資料使用內容搜尋，或其關聯 custodian 進階電子文件探索案例中。 使用匯入和封存 Office 365 中的協力廠商資料的範例連接器，可協助組織符合規範與政府法規的原則。

> [!NOTE]
> 目前，只有 Facebook 商務頁面的範例連接器是供預覽。 更多範例連接器即將推出。


## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>設定 Facebook 商務頁面的連接器的必要條件

您可以設定和安全性 & 合規性中心，以匯入及封存資料從您的組織 Facebook 商務頁面中設定的範例連接器之前，您必須完成下列必要條件。 

- 您需要的 Facebook 帳戶貴組織的業務頁面 （您需要設定連接器時，登入到這個帳戶）。 目前，您可以僅封存資料從 Facebook 商務頁面;您無法封存資料從個別 Facebook 設定檔。

- 您的組織必須具有有效的 Azure 訂用帳戶。 如果您沒有現有的 Azure 訂用帳戶，您可以註冊其中一個選項：

    - [註冊免費 1 年 Azure 訂用帳戶](https://azure.microsoft.com/free) 

    - [註冊 Pay-As-You-Go Azure 訂用帳戶](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > 已內含於您的 Office 365 訂閱的[免費的 Azure Active Directory 訂閱](use-your-free-azure-ad-subscription-in-office-365.md)不支援的範例連接器中安全性 & 合規性中心。

- 您的組織必須同意允許存取您組織中的信箱資料的 Office 365 匯入服務。 若要同意這項要求，請移到[此頁面上](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，登入的 Office 365 全域管理員認證，並接受要求。

- 設定安全性 & 合規性 （步驟 7) 中的自訂連接器的使用者必須獲指派信箱匯入匯出角色在 Exchange Online。 根據預設，此角色不指派給任何角色群組在 Exchange Online。 您可以新增 「 信箱匯入 / 匯出 」 角色給組織管理角色群組在 Exchange Online。 或者，您可以建立新的角色群組、 指派 「 信箱匯入 / 匯出 」 角色，並再將適當的使用者新增為成員。 如需詳細資訊，請參閱 < 文件中的<b0>建立角色群組</b0>或<b1>修改角色群組</b1>區段 」 管理角色群組在 Exchange Online 」。

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a>步驟 1： 從 Github 下載預先內建的連接器應用程式套件

第一個步驟是下載預先內建 Facebook 連接器應用程式將用來連線至您的 Facebook 商務頁面並解壓縮 Facebook 資料，讓您可以將它匯入 Office 365 的 Facebook API 的程式碼。

1. 移至[這個 GitHub 網站](https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases)。 
2. [最新版本中，按一下 [ **SampleConnector.zip**檔案。
3. ZIP 檔案儲存到您本機電腦上的位置。 您將此 zip 檔案上傳到步驟 4 中的 Azure 中。

## <a name="step-2-create-an-app-in-azure-active-directory"></a>步驟 2： 在 Azure Active Directory 中建立的應用程式

下一步是註冊新的應用程式在 Azure Active Directory (AAD)。 此應用程式將會對應至您將 Facebook 連接器在步驟 4 中實作的 web 應用程式資源。 

如需逐步指示，請參閱 <<c0>建立 Azure Active Directory 中的應用程式。

期間完成此步驟中 （藉由遵循的逐步指示） 時，您會將下列資訊儲存到文字檔。 在部署程序稍後步驟，就會使用這些值。

- AAD 應用程式識別碼
- AAD 應用程式密碼
- AAD 應用程式的 Uri
- 租用戶識別碼

## <a name="step-3-create-an-azure-storage-account"></a>步驟 3： 建立 Azure 儲存體帳戶

為貴組織部署 Facebook 連接器將上傳您在此步驟中建立的 Azure 儲存體位置從 Facebook 商務網頁的項目。 在安全性 & （在步驟 7) 的合規性中心建立自訂連接器之後，Office 365 匯入服務將 Facebook 將資料複製從 Azure 儲存體位置到 Office 365 中的信箱。 如同先前所述[的必要條件](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages)] 區段中，您必須建立 Azure 儲存體帳戶的有效 Azure 訂用帳戶。

如需逐步指示，請參閱 <<c0>建立 Azure 儲存體帳戶。

完成此步驟中 （藉由遵循的逐步指示） 的期間，您將儲存的連線字串產生的 Uri。 在步驟 4 中的 Azure 中建立 web 應用程式資源時，您將使用此字串。

## <a name="step-4-create-a-web-app-resource-in-azure"></a>步驟 4： 在 Azure 中建立 web 應用程式資源

下一步是在 Azure 中建立 web 應用程式資源 Facebook 連接器。 

如需逐步指示，請參閱 <<c0>建立新的 web 應用程式資源在 Azure 中。

期間完成此步驟中 （藉由遵循的逐步指示） 時，您將提供下列資訊 （完成上述步驟之後，您已複製到文字檔案） 時建立的 web 應用程式資源。

- APISecretKey – 您會在完成此步驟中; 的期間建立此密碼步驟 7 中，將使用它。
- StorageAccountConnectionString – 您在步驟 3 中建立 Azure 儲存體帳戶之後所複製的 Uri 的連接字串。
- tenantId – 您在步驟 2 中的 Azure Active Directory 中建立 Facebook 連接器應用程式之後複製您 Office 365 組織租用戶識別碼。

此外，您會在此步驟中部署 Facebook 連接器應用程式的原始碼上載 SampleConnector.zip （下載檔案，您在步驟 1 中）。

之後完成此步驟，請務必要複製的應用程式服務的 URL (例如， https://fbconnector.azurewebsites.net)。 您將需要使用此功能來完成步驟 5、 步驟 6 和步驟 7）。

## <a name="step-5-register-the-web-app-on-facebook"></a>步驟 5： 註冊在 Facebook 上的 web 應用程式

下一步是建立及設定新的應用程式在 Facebook 上。 您在步驟 7 中建立的自訂連接器會使用 Facebook web app 與 Facebook API，以取得從貴組織的 Facebook 商務資料互動。

如需逐步指示，請參閱[註冊 Facebook 應用程式](deploy-facebook-connector.md#step-5-register-the-facebook-app)。

期間完成此步驟中 （藉由遵循的逐步指示） 時，您會將下列資訊儲存到文字檔。 這些值會用來在步驟 6 中設定 Facebook 連接器應用程式。

- Facebook 應用程式識別碼
- Facebook 應用程式密碼
- Facebook webhooks 驗證權杖

## <a name="step-6-configure-the-facebook-connector-app"></a>步驟 6： 設定 Facebook 連接器應用程式

下一步是將組態設定新增至您上傳時您在步驟 4 中建立 Azure 的 web 應用程式資源 Facebook 連接器應用程式。 您將移至您的連接器應用程式的 [首頁] 頁面上，並設定其來這麼做。

如需逐步指示，請參閱[步驟 6： 設定連接器的 web 應用程式](deploy-facebook-connector.md#step-6-configure-the-connector-web-app)。

期間完成此步驟中 （藉由遵循的逐步指示） 時，您將提供下列資訊 （也就完成上述步驟之後，您已複製到文字檔案）：

- Facebook 應用程式識別碼 （在步驟 5 中所取得）
- Facebook 應用程式密碼 （在步驟 5 中所取得）
- Facebook webhooks 驗證權杖 （在步驟 5 中所取得）
- Azure Active Directory 應用程式識別碼 （在步驟 2 中所取得的 AAD 應用程式識別碼）
- Azure Active Directory 應用程式密碼 （在步驟 2 中所取得的 AAD 應用程式密碼）
- Azure Active Directory 應用程式的 Uri (AAD 應用程式的 Uri 取得在步驟 2; 例如，https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>步驟 7： 設立安全性 & 合規性中心中的自訂連接器

最後一個步驟是設定安全性 & 會從資料匯入 Facebook 商務頁面指定的信箱，Office 365 中的規範中心中的自訂連接器。 您已成功完成此步驟之後，Office 365 匯入服務會啟動將資料從您的 Facebook 商務頁面匯入 Office 365 的程序。 

如需逐步指示，請參閱 <<c0>設定安全性 &amp; 合規性中心中的自訂連接器。 

期間完成此步驟中 （藉由遵循的逐步指示） 時，您將提供下列資訊 （也就完成步驟之後，您已複製到文字檔案）。

- Azure 應用程式服務的 URL (取得在步驟 4; 例如https://fbconnector.azurewebsites.net)
- APISecretKey （，您在步驟 4 中建立）
