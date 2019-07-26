---
title: 在 Office 365 中封存第三方資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 系統管理員可以從匯入協力廠商資料社交媒體平台、 立即訊息平台，以及文件共同作業平台到 Office 365 組織中的信箱。 這可讓您封存 Facebook、 Twitter 和其他 Office 365 中的協力廠商資料來源的資料。 然後您可以使用或協力廠商資料套用 Office 365 符合性功能 （例如合法持有、 eDiscovery、 就地封存和保留原則）。
ms.openlocfilehash: 4b6236a7eaac4fa061d1cfbb770efd0a721804aa
ms.sourcegitcommit: a550519ca8f2a54712bf0a43be7f954e55675dac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/25/2019
ms.locfileid: "35902455"
---
# <a name="archive-third-party-data-in-office-365"></a>在 Office 365 中封存第三方資料

Office 365 可讓系統管理員匯入及封存立即訊息平台，與文件共同作業平台，您的 Office 365 組織中的信箱從社交媒體平台的協力廠商資料。 您可以匯入至 Office 365 的協力廠商資料來源的範例包括下列服務： 
  
- **社交：** Facebook、 LinkedIn、 Twitter 和 Yammer 
    
- **立即訊息：** Yahoo Messenger、 GoogleTalk 和 Cisco Jabber 
    
- **文件共同作業：** 方塊和 DropBox 
    
- **垂直產業：** 客戶關係管理 （例如 Salesforce Chatter) 和金融服務 (例如 Bloomberg 和 Thomson Reuters) 
    
- **SMS/簡訊：** BlackBerry 
    
協力廠商資料匯入之後，您可以將 Office 365 符合性功能 – 例如訴訟暫止狀態、 eDiscovery、 就地封存、 稽核、 監督，與 Office 365 保留原則-套用此資料。 例如，當信箱處於訴訟暫止，會保留協力廠商資料。 您可以使用 Microsoft eDiscovery 工具來搜尋協力廠商資料。 或者，您可以將封存和保留原則套用至協力廠商資料如同您可以為 Microsoft 資料。 總之，封存在 Office 365 中的協力廠商資料可協助組織符合規範與政府法規的原則。

有兩種方式可匯入及封存 Office 365 中的協力廠商資料：

- **安全 & 合規性中心內使用的協力廠商資料連接器：** 使用 Office 365 中的安全性 & 合規性中心中的自訂資料連接器。 設定後，當您設定連接器時，它在連線至協力廠商資料來源、 將項目的內容轉換成電子郵件訊息的格式，並再將項目匯入至 Office 365 中的信箱。 目前，您可以實作匯入及封存資料從 Facebook 商務頁面、 公司 Twitter 帳戶、 立即 Bloomberg 和 LinkedIn 的連接器。 若要設定連接器的逐步指示，請參閱：
   
   - **Facebook:**[使用 Office 365 中的 Facebook 資料保存的範例連接器](archive-facebook-data-with-sample-connector.md)
  
   - **Twitter:**[使用封存 Twitter 資料 Office 365 中的範例連接器](archive-twitter-data-with-sample-connector.md)
    
   - **LinkedIn:**[設定連接器，以在 Office 365 中的 LinkedIn 資料保存](archive-linkedin-data.md)

   - **立即 Bloomberg:**[設定要封存立即 Bloomberg 資料 Office 365 中的連接器](archive-instant-bloomberg-data.md)

- **與 Microsoft 合作夥伴合作，：** 貴組織的運作方式與 Microsoft 合作夥伴，負責提供的自訂連接器，將會設定為從以規則為基礎的協力廠商資料來源擷取項目然後連線至 Microsoft 雲端由協力廠商 API 並匯入到這些項目Office 365。 協力廠商連接器也會項目的內容從協力廠商資料來源將轉換成電子郵件訊息，並再將它們匯入至 Office 365 中的信箱。 您可以使用的協力廠商和此方法的逐步程序的清單，請參閱[與封存 Office 365 中的協力廠商資料合作夥伴合作](work-with-partner-to-archive-third-party-data.md)。
