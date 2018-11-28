---
title: 檢閱 Office 365 雲端 App 安全性中的 App 探索結果
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: 檢閱在 [進階安全性管理應用程式探索報告可協助您深入了解如何在組織中的人員使用雲端應用程式。您已建立應用程式探索報告使用來自防火牆及 proxy 記錄檔之後，請檢閱應用程式探索儀表板中的結果。
ms.openlocfilehash: ddf3826f5aac9d3c837cf66f1b97b4650df70f32
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706257"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a>檢閱 Office 365 雲端 App 安全性中的 App 探索結果
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |[開始部署](turn-on-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](#next-steps) <br/> |
   
雲端探索儀表板適用於您組織的網頁流量記錄以提供雲端應用程式使用方式的詳細的資訊。如果您正在全域管理員、 安全性管理員或安全性讀者和您的組織有[建立 Office 365 雲端應用程式安全性的應用程式探索報告](create-app-discovery-reports-in-ocas.md)、 您可以使用雲端探索儀表板的入侵深入了解如何人員在您組織使用 Office 365 及其他雲端應用程式。（雲端探索儀表板也稱為是產能應用程式探索）。
  
 **年 3 月 2018年雲端探索儀表板有新的功能**可讓您輕鬆將檢視您組織中的人員如何使用 Office 365 及其他應用程式的詳細的資訊。 
  
![已更新雲端探索儀表板](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a>移至雲端探索儀表板

1. 移至 [[https://protection.office.com](https://protection.office.com)及使用 Office 365 工作或學校帳戶登入。(這會引導您安全性&amp;規範中心。) 
    
2. 安全性&amp;規範中心選擇**提醒** \> **管理進階提醒**。<br/>（如果尚未未啟用 Office 365 雲端應用程式安全性，而且會[開啟 [Office 365 雲端應用程式安全性](turn-on-office-365-cas.md)全域系統管理員）。
    
3. 選擇 [**移至 Office 365 的雲端應用程式安全性**]。
    
4. 移至 [**搜索** \> **雲端探索儀表板**。
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a>請參閱您的主要使用者、 IP 位址、 應用程式] 及風險層級

雲端探索儀表板可讓您的組織、 任何開啟的提醒、 主要使用者及風險層級中搭配 Office 365 的應用程式 a glance 在-概觀 （英文）。
  
![雲端探索 dashboaard](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. 在 [**儀表板**] 索引標籤上查看您組織的 [概觀] 區段中的整體雲端應用程式使用螢幕頂端之間。 
    
2. 請參閱**Office 365 類別**您組織中使用的應用程式。 
    
3. 查看**Discovered apps** widget 查看 Office 365 與此檢視中的其他應用程式的流量。 
    
4. 查看來識別使用者可以使用 Office 365 部署及雲端組織中最多的應用程式的**主要使用者**和**頂端 IP 位址**widget。 
    
5. 請參閱依地理位置人員所使用的應用程式所使用的**應用程式 headquarters 位置**對應位置。 
    
6. 高於地圖] 區域中，看看探索到中的應用程式**的風險層級**概觀 （英文） 的風險分數。您可以查看由同一個群組和**Discovered 應用程式**] 區域中所使用的類別的風險。例如，您可以看到流量多寡中每個群組是從高、 中型或低風險應用程式。 
    
## <a name="dive-deeper-into-the-information"></a>深入分析資訊

您可以使用雲端探索採取深入的應用程式、 子網域、 IP 位址及使用者。
  
1. 雲端探索儀表板中選擇 [ **Discovered 應用程式**] 索引標籤。 
    
2. 使用 [篩選] 區段中檢視應用程式的名稱、 類別、 使用量層級或看到的日期。
    
3. 在結果清單中，將游標移所顯示的**檢視子網域**的連結應用程式名稱。<br/> ![將滑鼠指標移至顯示檢視子網域的詳細資訊連結的應用程式旁](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)<br/>會顯示所選的應用程式的詳細的資訊。
    
4. 若要檢視有關的 IP 位址的詳細資訊，請選擇 [ **IP 位址**] 索引標籤。<br/>![雲端探索顯示 IP 位址的詳細的資訊](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)<br/>在結果清單中，選取 [個別 IP 位址來檢視的詳細的資訊。
    
5. 若要檢視您組織中的 Office 365 使用者相關的詳細資訊，請選擇 [**使用者**] 索引標籤。<br/>![雲端探索-使用者資訊](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)
  
## <a name="exclude-entities"></a>排除實體

您可以排除特定系統的使用者或 IP 位址以專注於更特定的資訊。
  
1. 選擇 [**設定** \> **雲端探索設定**。
    
2. 選擇 [**排除實體**。
    
3. 選擇 [**排除的使用者**或**排除的 IP 位址**。
    
4. 指定的使用者或 IP 位址並在 [**註解**] 方塊中輸入為什麼會排除這些使用者或 IP 位址資訊。 
    
5. 選擇 [**新增**]。
    
## <a name="next-steps"></a>後續步驟

- [檢閱並採取行動提醒](review-office-365-cas-alerts.md)
    
- [建立應用程式探索報告](create-app-discovery-reports-in-ocas.md)
    
- 檢閱您[的 Office 365 雲端應用程式安全性使用率活動](utilization-activities-for-ocas.md)
    

