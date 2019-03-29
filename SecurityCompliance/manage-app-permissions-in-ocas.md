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
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a>使用 Office 365 雲端 App 安全性管理 OAuth 應用程式

|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |[開始部署](turn-on-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](#next-steps)<br/> |
   
人員愛應用程式和其通常下載它們，尤其是人員考慮的應用程式將會使其成為容易取得在他們的公司或學校資訊以節省時間。 不過，某些應用程式可能有貴組織的安全性風險，哪些資訊為基礎，這取決於使用者存取，以及該資訊的處理方式。 使用[Office 365 雲端 App 安全性](office-365-cas-overview.md)，如果您是全域或安全性系統管理員，您可以管理 OAuth 應用程式為您的組織。 您可以看到應用程式的人員會使用與 Office 365 資料有何權限那些 sharepoint 應用程式，等等。 
  
本文說明移至管理 OAuth 應用程式的位置、 如何核准、 禁止，或報告應用程式，以及如何建立應用程式的查詢。
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a>如何找出管理 OAuth 應用程式] 頁面

> [!NOTE]
> 在 Office 365 雲端 App 安全性入口網站中管理 OAuth 應用程式。 您必須是全域系統管理員或安全性系統管理員可執行下列工作。 若要了解更多，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。 
  
1. 移至 Cloud App Security 入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，並登入。
  
2. 選擇 [**調查** \> **OAuth 應用程式**。<br/>![在 O365 CAS 入口網站中，選擇 [調查]。](media/OCAS-OAuthApps.png)<br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a>您會看到在管理 OAuth 應用程式] 頁面

下表說明在管理 OAuth 應用程式] 頁面上的控制項和可用的選項。
  
|**項目**|**描述**|
|:-----|:-----|
|在 [應用程式查詢列中的基本圖示  <br/> ![會指出查詢的基本查詢檢視的圖示](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|選取這個選項可切換至 [進階檢視。  <br/> （如果您看到**基本**，您正在使用的進階的檢視）  <br/> |
|在 [應用程式查詢列中的進階的圖示  <br/> ![會指出查詢的進階的查詢檢視的圖示](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|選取這個選項可切換到 [基本] 檢視。  <br/> （如果您看到**進階**，您正在使用基本檢視）。  <br/> |
|開啟或關閉應用程式清單中的所有詳細資料圖示  <br/> ![按一下此圖示來開啟或關閉的所有應用程式的所有詳細資料](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|選取 [此圖示來檢視每個應用程式的更多或較少詳細資料]。  <br/> |
|在應用程式清單中的匯出圖示  <br/> ![按一下此圖示來匯出 csv 檔案的所有應用程式](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|選取此圖示來匯出 CSV 檔案包含清單中的應用程式，每個應用程式，應用程式的權限層級、 應用程式的狀態，相關聯的權限的使用者數目和社群使用層級。  <br/> |
|名稱  <br/> |使用此功能來查看應用程式的名稱。 選取要檢視詳細資訊，例如其說明、 publisher、 應用程式網站和應用程式識別碼的名稱  <br/> |
|由授權  <br/> |使用此功能來查看多少使用者已獲授權的應用程式，才能存取其 Office 365 帳戶。 選取要檢視詳細資訊，例如清單中的使用者帳戶的數字。  <br/> |
|權限層級  <br/> ![會指出應用程式的 permisiions 層級的圖示](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|使用此功能來查看 Office 365 資料有多少的應用程式的存取。 權限層級指出**低**、 **Medium**或**High**、 **Low**可能表示應用程式只能存取使用者設定檔與名稱。 選取 [檢視詳細資訊，例如權限授與應用程式、 社群使用和[管理記錄](suspend-or-restore-an-account-in-ocas.md)的相關的活動的層級。  <br/> |
|上次授權 <br/> |使用此功能來查看的日期和時間 OAuth 應用程式已上次存取權限貴組織的 Office 365 資料。 <br/>  |
|動作<br/>![OAuth 應用程式](media/OCAS-OAuthAppApproveBanReport.png)<br/> |使用此功能來查看或將應用程式標示為已核准 」 或 「 Banned，OAuth 應用程式向 Microsoft 報告以，或保留為未定。  <br/> |
   
## <a name="mark-an-app-as-approved"></a>將應用程式標示為已核准

在 [**管理 OAuth 應用程式**] 頁面上，找出您想要核准的應用程式，選擇 [**標記應用程式作為核准**] 圖示。 
  
![選擇 [標記應用程式以核准圖示](media/OCAS-MarkOAuthApproved.png)
  
圖示會變成綠色，和所有 Office 365 使用者的核准應用程式。
  
> [!NOTE]
> 當您將應用程式標示為核准時，就會對使用者造成任何影響。 以視覺方式將標示要核准的應用程式，可以幫助隔開尚未尚未檢閱的應用程式。 
  
## <a name="ban-an-app"></a>禁止使用應用程式

1. 在**管理 OAuth 應用程式**] 頁面上，找出您要禁止，應用的程式，選擇 [**為標記應用程式禁止**] 圖示。<br/>![選擇 [標記應用程式以禁用圖示](media/OCAS-MarkOAuthBanned.png)
  
2. 通知訊息方塊中，保留現有的文字為是，或自訂的文字。 選擇是否要讓使用者知道，其 app 郵件已遭禁止。 <br/>![禁用的應用程式的 [郵件] 範本](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. 選擇 [**郵件應用程式**。

## <a name="report-an-oauth-app-to-microsoft"></a>向 Microsoft 報告 OAuth 應用程式

如果您想要提交給 Microsoft 進行分析 OAuth 應用程式，您可以報告該應用程式。

1. 在 [**管理 OAuth 應用程式**] 頁面上，找出您想要提交進行分析的應用程式。

2. 選擇 [垂直的省略符號，，然後選擇**報表 app..**。<br/>![報告 OAuth 應用程式](media/OCAS-MarkOAuthReported.png)<br/>

3. 在 [**報告此應用程式**] 對話方塊中，使用下拉式清單來表示您的考量。 根據預設，會選取**此應用程式是惡意**。 不過，您可以選擇在其中一個其他可用的選項。 <br/>![報告 OAuth 應用程式](media/OCAS-ReportOAuthApp.png)<br/>

4. （建議使用）保留選項，可連絡您選取，並確認 （或編輯） 所列的電子郵件地址。

5. Choose **Submit**. 
    
## <a name="create-an-app-query"></a>建立應用程式的查詢

我們建議使用進階的檢視中，看起來像這樣： 

![進階的檢視](media/OCAS-OAuthAppsAdvQueryView.png)

在應用程式查詢列中，如果您看到 [**進階**]，您正在使用基本的檢視。 按一下 （或點選） [**進階**]，以移至 [進階檢視。 

![基本檢視](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. 在 [查詢] 列中，使用**選取篩選器**清單中選擇一個選項。 
    - **應用程式**具有特定名稱的應用程式
    - **應用程式狀態**根據其狀態 （已核准、 Banned 或 「 未定 」） 的應用程式
    - **使用社群**社群為基礎的應用程式使用層級 （Rare、 Uncommon 或一般）
    - **權限等級**根據特定權限層級的應用程式 
    - **權限**需要特定權限的應用程式
    - **發行者** 來自特定發行者應用程式
    - **使用者**特定使用者的權限的應用程式
   
2. 選取 [**等於**] 或 [**不等於**，，，然後指定篩選的值。
    
3. 若要新增更多篩選器，請選取加上加號 （![新增查詢應用程式的篩選器圖示](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg))，然後重複步驟 2 和 3。
    
4. 若要移除篩選，請選取 [x (![移除查詢應用程式的篩選器圖示](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)) 旁的篩選器名稱。
    
自動套用篩選器，並據此更新應用程式清單。
  
## <a name="next-steps"></a>後續步驟

- [檢閱並採取相應動作提醒](review-office-365-cas-alerts.md)
    
- 檢閱您的[Web 流量記錄及資料來源的 Office 365 雲端 App 安全性](web-traffic-logs-and-data-sources-for-ocas.md)
    
- 檢閱您[的 Office 365 雲端 App 安全性的使用率活動](utilization-activities-for-ocas.md)
    

