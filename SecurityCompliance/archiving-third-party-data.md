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
description: 系統管理員可以將協力廠商資料從社交媒體平臺、立即訊息平臺, 以及檔共同作業平臺匯入 Office 365 組織中的信箱。 這可讓您在 Office 365 中封存 Facebook、Twitter 及其他協力廠商資料來源的資料。 然後, 您可以針對協力廠商資料使用和套用 Office 365 規範功能 (例如合法持有、eDiscovery、就地封存和保留原則)。
ms.openlocfilehash: 796ad0314374dca60d1ff5f6b9317be491b757a1
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014602"
---
# <a name="archive-third-party-data-in-office-365"></a>在 Office 365 中封存第三方資料

Office 365 可讓系統管理員將協力廠商資料從社交媒體平臺、立即訊息平臺和檔共同作業平臺匯入和封存至 Office 365 組織中的信箱。 您可以匯入至 Office 365 的協力廠商資料來源範例包括下列服務: 
  
- **社交**– Facebook、LinkedIn、Twitter 和 Yammer 
    
- **立即訊息**– Yahoo Messenger、GoogleTalk 和 Cisco jabber) 
    
- **檔**共同作業– Box 和 DropBox 
    
- **垂直行業**–客戶關係管理 (例如 Salesforce 交談) 和金融服務 (例如 Bloomberg 和 Thomson Reuters) 
    
- **SMS/文字訊息**– BlackBerry 
    
匯入協力廠商資料之後, 您可以將 Office 365 規範功能 (例如訴訟暫止、eDiscovery、就地封存、審核、監督和 Office 365 保留原則) 套用至此資料。 例如，當信箱置於訴訟暫止狀態時，協力廠商資料將會保留。 您可以使用 Microsoft eDiscovery 工具來搜尋協力廠商資料。 或者，您可以將封存和保留原則套用至協力廠商資料，就像您可以對 Microsoft 資料進行的動作一樣。 簡而言之, 封存 Office 365 中的協力廠商資料可協助您的組織符合政府和法規原則。

有兩種方式可匯入和封存 Office 365 中的協力廠商資料:

- **使用安全性 & 合規性中心內的協力廠商資料連線器**–使用 Office 365 的安全性 & 規範中心提供的自訂資料連線器。 在您設定及設定連接器之後, 它會連線至協力廠商資料來源、將專案的內容轉換成電子郵件格式, 然後將該專案匯入至 Office 365 中的信箱。 此時, 您可以從 Facebook 商務頁面、公司 Twitter 帳戶、立即 Bloomberg 和 LinkedIn 中, 採用連接器來匯入和封存資料。 如需設定連接器的逐步指示, 請參閱:
   
   - **Facebook** –[在 Office 365 中使用範例連接器封存 Facebook 資料](archive-facebook-data-with-sample-connector.md)
  
   - **Twitter** –[使用範例連接器來封存 Office 365 中的 Twitter 資料](archive-twitter-data-with-sample-connector.md)
    
   - **LinkedIn** –[設定連接器以封存 Office 365 中的 LinkedIn 資料](archive-linkedin-data.md)

- **使用 microsoft 合作夥伴**-您的組織可與 microsoft 合作夥伴合作, 其中提供自訂連接器, 將設定為從協力廠商資料來源提取專案 (定期), 然後以協力廠商 API, 並將這些專案匯入至 Office 365。 夥伴連接器也會將專案的內容從協力廠商資料來源轉換成電子郵件訊息, 然後將其匯入 Office 365 中的信箱。 如需您可以使用的合作夥伴清單, 以及此方法的逐步程式, 請參閱[在 Office 365 中與合作夥伴一起封存協力廠商資料](work-with-partner-to-archive-third-party-data.md)。