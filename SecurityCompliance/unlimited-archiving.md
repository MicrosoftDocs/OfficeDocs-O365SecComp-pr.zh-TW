---
title: Office 365 中不受限制封存概觀
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 了解自動展開封存 Office 365 中，其會提供的 Exchange Online 信箱執行不受限制的封存儲存區。
ms.openlocfilehash: a762a0fb8295a645957404c1c88881f40329f7a1
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782120"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a>Office 365 中不受限制封存概觀

Office 365 中封存信箱會提供使用者對其他信箱的儲存空間。啟用使用者的封存信箱後，最多 100 GB 的額外儲存空間使用。當達到 100 GB 儲存配額時，組織都封存信箱的要求額外儲存空間來連絡 Microsoft。那是不會再大小寫。Office 365 （稱為 「*自動展開封存*） 中的新不受限制封存功能提供不受限制的封存信箱中的儲存空間量。現在，當達到封存信箱中的儲存配額，Office 365 自動增加的封存，這表示使用者不會執行移出信箱的儲存空間和系統管理員不需要要求的封存信箱的額外儲存空間.
  
如需逐步說明的開啟自動展開封存，請參閱[啟用 Office 365 中沒有限制之封存](enable-unlimited-archiving.md)。
  
> [!NOTE]
> 自動展開封存也支援共用的信箱。若要啟用共用信箱的封存，Exchange Online 計劃 2 授權或 Exchange Online 計劃 1 授權來搭配 Exchange Online 封存的授權，則需要。 
  
## <a name="how-auto-expanding-archiving-works"></a>如何自動展開封存的運作

為先前所述]、 [其他信箱使用者的封存信箱啟用時建立的儲存空間。啟用自動展開封存時，Office 365 定期檢查封存信箱的大小。當封存信箱取得接近其儲存限制時，Office 365 會自動建立封存的額外儲存空間。如果使用者是執行此額外儲存空間不足，Office 365 會將更多儲存空間新增至使用者的封存。此程序就會發生自動，這表示系統管理員不需要要求其他封存存放區] 或 [管理自動展開封存。 
  
以下是程序的快速概觀 （英文）。
  
![自動展開封存程序概觀](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. 使用者信箱或共用的信箱啟用封存。建立封存信箱與 100 GB 的存放區空間、 且封存信箱的警告配額設為 90 GB。
    
2. 系統管理員啟用自動展開封存信箱。當封存信箱 （包括可復原的項目] 資料夾） 達到 90 GB，它會轉換為自動展開封存，然後 Office 365 新增至封存儲存空間。請注意其可採取的額外儲存空間來佈建多達 30 天。
    
3. Office 365 自動封存在必要時將更多儲存空間。
  
> [!IMPORTANT]
> 如果信箱處於保留狀態或指派給 Office 365 保留原則、 封存信箱儲存配額增加為 110 GB 時自動展開封存已啟用。同樣地，增加封存警告配額為 100 GB。

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>新取得移至其他封存儲存空間？

若要有效使用自動展開封存儲存，可能會取得移動資料夾。Office 365 會決定哪些資料夾要取得移動額外儲存空間新增至封存時。移動資料夾時，在 Outlook 中的資料夾清單的封存部分原始資料夾下自動建立子資料夾。這個新的子資料夾會指向已移動的項目。Office 365 使用命名此資料夾的命名慣例是**\<資料夾名稱\>_yyyy （建立上 mmm dd，yyyy h_mm）**，其中： 
  
- **yyyy**是收到的郵件] 資料夾中的年份。 
    
- **mmm dd，yyyy h_m**是日期與時間的子資料夾以 UTC 格式，根據使用者的時區和地區設定在 Outlook 中的建立的 Office 365。 
    
下列螢幕擷取畫面顯示的資料夾清單之前和之後郵件會自動展開封存中移。
  
 **新增額外儲存空間之前**
  
![資料夾清單] 的前已佈建自動展開封存的封存信箱](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 **新增額外儲存空間之後**
  
![資料夾清單中的封存信箱之後自動展開封存已佈建](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Outlook 需求存取自動展開封存中的項目

若要存取儲存在自動展開封存中的郵件，使用者必須使用下列 Outlook 用戶端之一：
  
- Windows outlook 2016
    
- 網頁型 Outlook 
    
- Outlook 2016 for Mac 
    
> [!NOTE]
> Outlook 2013 使用者可以原本已儲存封存信箱的存取項目。他們將無法存取項目移至其他封存存放區。 
  
以下是使用 Outlook 或 Outlook 存取郵件中自動展開封存儲存在 web 上的時所應考量事項。
  
- 您可以存取您的封存信箱，包括類已移至 [自動展開存放區] 區域中的任何資料夾。
    
- 您可以搜尋已移至其他儲存區只能由搜尋資料夾本身的項目。這表示您必須選取資料夾清單] 以選取 [**目前的資料夾**選項為搜尋範圍中的 [封存] 資料夾。同樣地，如果自動展開儲存區中的資料夾包含子資料夾，您必須分別搜尋每一個子資料夾。 
    
- Outlook 中的項目計數和 （在 Outlook 和 Outlook web 上的） 的讀取/未閱讀計數自動展開封存中可能不正確。
    
- 您可以刪除自動展開存放區] 區域中，會指向子資料夾中的項目，但無法刪除資料夾本身。
    
- 您無法復原從自動展開儲存區中已刪除的項目使用的復原刪除的郵件功能。
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a>自動展開封存和其他 Office 365 的符合性功能

本節說明自動展開封存和其他 Office 365 規範和資料控管功能之間的功能。
  
- **eDiscovery** -使用 Office 365 eDiscovery 工具，例如內容搜尋] 或 [就地 eDiscovery 自動展開封存中的額外儲存空間區域時也會搜尋。
    
- **保留**-當您將信箱保留放在 Exchange Online 中使用工具，例如訴訟暫止狀態或保留 eDiscovery 案例和 Office 365 安全性的保留原則&amp;規範中心位於自動展開封存的內容也是處於保留狀態。
    
- **通訊記錄管理 (MRM)** -如果您在 Exchange Online 中使用 MRM 刪除原則永久刪除過期的信箱項目、 到期的項目位於自動展開封存也都會刪除。
    
- **匯入服務**-您可以使用匯入 Office 365 服務至 PST 檔案匯入的使用者自動展開封存。您可以在使用者的封存信箱 PST 檔案匯最大 100 GB 的資料。 

## <a name="more-information"></a>其他資訊

如需自動展開封存，請參閱更多技術詳細資料[Office 365： 自動展開封存常見問題集](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)。