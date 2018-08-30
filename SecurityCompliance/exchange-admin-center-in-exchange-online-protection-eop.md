---
title: 'Exchange Online Protection 中的 Exchange 系統管理中心 '
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
description: Exchange 系統管理中心 (EAC) 是 Microsoft Exchange Online Protection (EOP) 的 Web 式管理主控台。
ms.openlocfilehash: 144907110af9fcbec1c6399e0695abb705bef409
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002942"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a>Exchange Online Protection 中的 Exchange 系統管理中心 

Exchange 系統管理中心 (EAC) 是 Microsoft Exchange Online Protection (EOP) 的 Web 式管理主控台。 
  
在尋找本主題的 Exchange 2013 版本嗎？請參閱[Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx)。
  
在尋找本主題的 Exchange Online 版本嗎？請參閱[Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。
  
## <a name="accessing-the-eac"></a>存取 EAC

在大多數情況下，EOP 客戶會透過 Office 365 系統管理中心存取 EAC。您可在 **[管理磚]** (位於 **[自有磚]** 旁) 的下拉式功能表中找到 EOP 的連結。按一下 **[管理磚]** 並從下拉式功能表中選取 **[Exchange Online Protection]** 以將您帶往 EAC。 
  
您也可以透過下列 URL 直接存取 EAC 登入頁面：https://admin.protection.outlook.com/ecp/\<companydomain\>。例如，https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com。指定使用者認證後，您會被直接帶往 EAC。
  
## <a name="common-user-interface-elements-in-the-eac"></a>EAC 中常見的使用者介面元素

本節說明 EMC 中的使用者介面元素。
  
![EOP AdminCenter](media/EOP-AdminCenter.png)
  
### <a name="feature-pane"></a>功能窗格

這是您在 EAC 中執行大部分工作時的第一個導覽層級。功能窗格依功能區域組織。
  
1. **收件者** 您可在此檢視內部使用者和外部連絡人。 
    
2. **權限** 您可在此管理系統管理員角色。 
    
3. **規範管理** 您可在此尋找稽核記錄和報告，例如系統管理員角色群組報告。 
    
4. **保護** 您可在此管理組織的反惡意程式碼和反垃圾郵件保護，以及管理隔離郵件。 
    
5. **郵件流程** 您可在此管理規則、公認的網域和連接器，以及執行郵件追蹤。 
    
### <a name="tabs"></a>索引標籤

索引標籤是您的第二個導覽層級。每一個功能區都包含不同的索引標籤，各自代表一項功能。
  
### <a name="toolbar"></a>工具列

按一下大部分的索引標籤時，會看到一個工具列。工具列上的圖示會執行特定動作。下表描述圖示及其動作。
  
|**圖示**|**名稱**|**Action**|
|:-----|:-----|:-----|
|![加入圖示](media/ITPro-EAC-AddIcon.gif)           <br/> |新增  <br/> |使用此圖示來建立新的物件。這些圖示中有些擁有一個關聯的向下箭號，您可以按一下以顯示所能建立的其他物件。  <br/> |
|![編輯圖示](media/ITPro-EAC-EditIcon.gif)           <br/> |編輯  <br/> |使用此圖示來編輯物件。  <br/> |
|![刪除圖示](media/ITPro-EAC-DeleteIcon.gif)           <br/> |刪除  <br/> |使用此圖示來刪除物件。部分刪除圖示擁有一個向下箭號，您可以按一下以顯示額外選項。  <br/> |
|![搜尋圖示](media/ITPro-EAC-.gif)           <br/> |搜尋  <br/> |使用此圖示來開啟搜尋方塊，您可在此處輸入想要尋找之物件的搜尋字詞。  <br/> |
|![重新整理圖示](media/ITPro-EAC-RefreshIcon.gif)           <br/> |重新整理  <br/> |使用此圖示來重新整理清單檢視。  <br/> |
|![更多選項圖示](media/ITPro-EAC-MoreOptionsIcon.gif)           <br/> |更多選項  <br/> |使用此圖示來檢視更多可對該索引標籤之物件執行的動作。例如，在 **[收件者 \> 使用者]** 中按一下此圖示會顯示可執行 **[進階搜尋]** 的選項。  <br/> |
|![向上箭號圖示](media/ITPro-EAC-UpArrowIcon.gif)![向下箭號圖示](media/ITPro-EAC-DownArrowIcon.gif)           <br/> |向上鍵和向下鍵  <br/> |使用這些圖示向上或向下移動物件的優先順序。  <br/> |
|![[移除] 圖示](media/ITPro-EAC-RemoveIcon.gif)           <br/> |移除  <br/> |使用此圖示來移除清單中的物件。  <br/> |
   
### <a name="list-view"></a>清單檢視

當您選取索引標籤時，大部分情況下會看見清單檢視。EAC 清單檢視內可檢視的限制約為 10,000 個物件。此外，也包括分頁功能，所以你可以將結果分頁顯示。
  
### <a name="details-pane"></a>詳細資料窗格

當您從清單檢視中選取物件時，該物件的相關資訊就會顯示在詳細資料窗格中。在部分情況下，詳細資料窗格包括管理工作。
  
### <a name="me-tile-and-help"></a>自有磚與說明

**[自有磚]** 可讓您登出 EAC，然後以不同使用者的身分登入。您可以從 **[說明]**![說明圖示](media/ITPro-EAC-HelpIcon.gif) 下拉式功能表執行下列動作： 
  
1. **說明：** 按一下 ![說明圖示](media/ITPro-EAC-HelpIcon.gif) 即可檢視線上說明內容。 
    
2. **停用說明泡泡圖** [說明泡泡圖] 會在您建立或編輯物件時，顯示欄位的內容說明。您可以關閉 [說明泡泡圖]，或是在停用的狀態下將它開啟。 
    
3. **著作權** 按一下此連結可以閱讀 Exchange Online Protection 的著作權聲明。 
    
4. **隱私權** 按一下可閱讀 Exchange Online Protection 的隱私權原則。 
    
## <a name="supported-browsers"></a>支援的瀏覽器

為享有 EAC 最佳使用體驗，建議您一律使用最新的瀏覽器、Office 用戶端和應用程式。我們也建議您隨時安裝最新的軟體更新。如需此服務支援的瀏覽器和系統需求的詳細資訊，請參閱＜[Office 365 系統需求](https://go.microsoft.com/fwlink/p/?LinkID=402699)＞。 
  
## <a name="supported-languages-in-eop"></a>EOP 的支援語言

Exchange Online Protection 支援且可使用下列語言。
  
- 阿姆哈拉文
    
- 阿拉伯文
    
- 巴斯克文 (巴斯克文)
    
- 孟加拉文 (印度)
    
- 保加利亞文
    
- 卡達隆尼亞文
    
- 簡體中文
    
- 繁體中文
    
- 克羅埃西亞文
    
- 捷克文
    
- 丹麥文
    
- 荷蘭文
    
- 荷蘭文
    
- 英文
    
- 愛沙尼亞文
    
- 菲律賓文 (菲律賓)
    
- 芬蘭文
    
- 法文
    
- 加里斯亞文
    
- 德文
    
- 希臘文
    
- 古吉拉特文
    
- 希伯來文
    
- 印度文
    
- 匈牙利文
    
- 冰島文
    
- 印尼文
    
- 義大利文
    
- 日文
    
- 埃納德文
    
- 哈薩克文
    
- 史瓦希里文
    
- 韓文
    
- 拉脫維亞文
    
- 立陶宛文
    
- 馬來文 (汶萊)
    
- 馬來文 (馬來西亞)
    
- 馬來亞拉姆文
    
- 馬拉提文
    
- 挪威文 (巴克摩)
    
- 挪威文 (尼洛斯克)
    
- 歐利亞文
    
- 波斯文
    
- 波蘭文
    
- 葡萄牙文 (巴西)
    
- 葡萄牙文 (葡萄牙)
    
- 羅馬尼亞文
    
- 俄文
    
- 塞爾維亞文 (斯拉夫、塞爾維亞)
    
- 塞爾維亞文 (拉丁)
    
- 斯洛伐克文
    
- 斯洛維尼亞文
    
- 西班牙文
    
- 瑞典文
    
- 坦米爾文
    
- 特拉古文
    
- 泰文
    
- 土耳其文
    
- 烏克蘭文
    
- 烏都文
    
- 越南文
    
- 威爾斯文
    

