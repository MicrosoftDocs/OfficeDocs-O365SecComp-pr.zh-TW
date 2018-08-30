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
# <a name="manage-app-permissions-using-office-365-cloud-app-security"></a>使用 Office 365 雲端 App 安全性管理 App 權限

Office 365 進階安全性管理現在是 Office 365 雲端應用程式安全性。
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |[開始部署](turn-on-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
人員愛應用程式和他們通常下載，特別是人員考慮的應用程式將會使其成為容易取得其工作或學校資訊，以節省時間。不過，某些應用程式可能會對組織的安全性風險，取決於哪些資訊存取該資訊的處理方式。與[Office 365 雲端應用程式安全性](office-365-cas-overview.md)]，如果您是通用範圍或安全性的系統管理員，您可以管理應用程式權限您的組織。您可以看到應用程式的人員使用 Office 365 資料的權限這些應用程式有，等等。 
  
本文說明移至 [管理應用程式的權限的位置、 如何核准或禁止應用程式，以及如何建立應用程式的查詢。
  
## <a name="how-to-find-the-manage-app-permissions-page"></a>尋找 [管理應用程式的權限] 頁面上的方法
<a name="findappperms"> </a>

> [!NOTE]
> 在 Office 365 雲端應用程式安全性入口網站中管理應用程式權限。您必須是全域管理員或安全性管理員可執行下列工作。若要了解更多，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。 
  
1. 移至 [[https://protection.office.com](https://protection.office.com)及使用 Office 365 工作或學校帳戶登入。(這會引導您安全性&amp;規範中心。) 
    
2. 移至 [**提醒** \> **管理進階提醒**。
    
3. 按一下 （或點選）**移至 Office 365 雲端應用程式安全性**。
    
    ![安全性&amp;規範中心選擇管理進階警告移至 Office 365 雲端應用程式安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    > [!NOTE]
    > 如果 Office 365 雲端應用程式安全性不會開啟尚未，您可以執行的動作在此頁面上。請參閱[備妥可供 Office 365 雲端應用程式安全性](get-ready-for-office-365-cas.md)。 
  
4. 選擇**調查** \> **應用程式權限**。
    
    ![在 O365 CAS 入口網站中選擇 [調查]。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
## <a name="what-youll-see-on-the-manage-app-permissions-page"></a>您會看到 [管理應用程式的權限] 頁面上
<a name="whatsonpage"> </a>

下表說明管理應用程式的權限] 頁面上的控制項和可用的選項。
  
|**項目**|**描述**|
|:-----|:-----|
|應用程式查詢列中的基本圖示  <br/> ![會指出查詢應用程式權限的基本查詢檢視的圖示](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|選取這個選項可切換至 [進階檢視。  <br/> （如果您看到**基本**，您會使用 [進階] 檢視）  <br/> |
|應用程式查詢列中的進階的圖示  <br/> ![會指出進階查詢應用程式權限的查詢檢視的圖示](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|選取這個選項可切換至 [基本] 檢視。  <br/> （如果您看到**進階**，您會使用 [基本] 檢視）。  <br/> |
|開啟或關閉此應用程式清單中的所有詳細資料圖示  <br/> ![按一下此圖示來開啟或關閉所有應用程式的所有詳細資料](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|選取此圖示來檢視每個應用程式的更多或更少詳細資料。  <br/> |
|匯出應用程式清單中的圖示  <br/> ![按一下此圖示來匯出 csv 檔案的所有應用程式](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|選取此圖示來匯出 CSV 檔案包含應用程式] 的使用者的每個應用程式相關聯的應用程式、 權限層級、 應用程式狀態和社群使用層級的權限的清單。  <br/> |
|名稱  <br/> |使用此看到的名稱 app 選取来檢視詳細資訊，例如其描述、 publisher、 應用程式網站與應用程式識別碼的名稱  <br/> |
|依授權  <br/> |使用此檢視多少使用者已獲得授權的應用程式以存取其 Office 365 帳戶。選取要檢視的使用者帳戶清單等的詳細資訊的數字。  <br/> |
|權限層級  <br/> ![會指出應用程式的 permisiions 層級的圖示](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|使用此請參閱 Office 365 資料有多少的應用程式的存取。權限層級指出**Low**、 **Medium**或**High**、 **Low**可能表示應用程式只能存取使用者設定檔和名稱。選取應用程式、 社群使用及相關的活動[控管記錄檔](suspend-or-restore-an-account-in-ocas.md)中授與檢視詳細資訊，例如權限層級。<br/> |
|應用程式狀態 （ **Banned**、**已核准**或**Undetermined**）  <br/> ![應用程式的權限圖示後要允許、 封鎖或沒有動作所已由系統管理員](media/5748bd02-cd59-4bd1-a36f-d25a186e8055.png)|使用此項，將應用程式標示為已核准 」 或 「 Banned，或離開作為源自。  <br/> |
   
## <a name="mark-an-app-as-approved"></a>標記為已核准的應用程式
<a name="approveapp"> </a>

在 [**管理應用程式權限**] 頁面上找出您想要核准的應用程式並選擇**做為 Mark app 核准**] 圖示。 
  
![選擇標記應用程式已核准的圖示](media/dd1b7690-441a-48c9-9c3a-58466513c63d.png)
  
圖示會開啟綠色和應用程式為您所有的 Office 365 使用者的 「 已核准。
  
> [!NOTE]
> 當您將應用程式標示為已核准時，有不會影響使用者。以視覺方式標示核准的應用程式可協助隔開尚未尚未檢閱的應用程式。 
  
## <a name="ban-an-app"></a>禁止應用程式
<a name="banapp"> </a>

1. 在 [**管理應用程式權限**] 頁面上找出您要禁止、 應用的程式並選擇**做為 Mark app 禁用**] 圖示。 
    
    ![選擇標記 app 禁用的圖示](media/b9b1c5f6-fde7-46d5-8589-1564d05702b3.png)
  
2. 選擇是否要讓使用者知道已禁用其應用程式。
    
    （建議）若要讓使用者了解，請選取**授與此禁用的應用程式的存取權的通知使用者**，以及新增或編輯自訂通知訊息。
    
    不讓使用者知道，清除 [**授與此禁用的應用程式的存取權的通知使用者**。
    
    ![禁用的應用程式的 [郵件] 範本](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)
  
3. 選擇 [**禁止應用程式**。
    
## <a name="create-an-app-query"></a>建立應用程式的查詢
<a name="createapp"> </a>

1. 在應用程式查詢列中，如果您看到**進階**，按一下 （或點選） 它移至 [進階] 檢視。（如果您看到 Basic，您使用 [進階的檢視 ； 其會保持在檢視）。
    
2. 使用 [**選取篩選**] 清單選擇選項。下表摘要說明可用的篩選選項。 
    
|**使用此篩選器**|**若要顯示**|
|:-----|:-----|
|**應用程式** <br/> |應用程式特定的名稱  <br/> |
|**應用程式狀態** <br/> |根據其狀態 （已核准、 Banned 或 Undetermined） 的應用程式  <br/> |
|**社群的使用** <br/> |社群為基礎的應用程式使用層級 （Rare、 Uncommon、 或一般）  <br/> |
|**權限等級** <br/> |某些權限層級為基礎的應用程式  <br/> |
|**權限** <br/> |需要特定的權限的應用程式  <br/> |
|**發行者** <br/> |從特定發行者的應用程式  <br/> |
|**使用者** <br/> |某些使用者授權的應用程式  <br/> |
   
3. 選取 [**等於**] 或 [**不等於**，並接著指定篩選的值。
    
4. 若要新增更多的篩選器，請選取 [加號 （![新增查詢應用程式的篩選圖示](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg))，然後重複步驟 2 和 3。
    
5. 若要移除篩選，請選取 [x (![移除查詢應用程式的篩選圖示](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)) 旁的篩選器名稱。
    
自動套用篩選器與據以更新的應用程式清單。
  
## <a name="next-steps"></a>後續步驟
<a name="nextsteps"> </a>

- [檢閱並採取行動提醒](review-office-365-cas-alerts.md)
    
- 檢閱您的[網頁流量記錄檔與資料來源為 Office 365 雲端應用程式安全性](web-traffic-logs-and-data-sources-for-ocas.md)
    
- 檢閱您[的 Office 365 雲端應用程式安全性使用率活動](utilization-activities-for-ocas.md)
    

