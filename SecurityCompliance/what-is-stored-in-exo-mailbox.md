---
title: Exchange Online 信箱中儲存的內容
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 在 Office 365 雲端式應用程式所產生的資料會儲存在 Microsoft cloud 中的使用者的 Exchange Online 信箱。
ms.openlocfilehash: 380c16e65c2358961b9ee5185c40d3eb7d85950b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157715"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>Exchange Online 信箱中儲存的內容

Exchange Online 中的信箱主要用來儲存郵件、 行事曆項目、 工作及備忘稿例如電子郵件相關項目。 但是，變更為更多的基於雲端的 Office 365 應用程式也會儲存其資料在使用者的信箱。 將資料儲存在信箱中的其中一個優勢是，您可以使用內容搜尋電子文件探索、 進階的 eDiscovery 中搜尋工具資料調查尋找、 檢視和匯出資料從這些雲端式應用程式。 請注意，從這些應用程式的一些資料會儲存在隱藏的資料夾位於信箱中的非人際郵件 (非 IPM) 樹狀子目錄。 這表示當他們使用 Outlook 或其他郵件用戶端來存取其信箱的使用者檢視中隱藏資料。

下表列出 Office 365 應用程式可將資料儲存在雲端式信箱中。 下表也會說明每個應用程式儲存的內容類型。

|Office 365 應用程式  |描述  |
|:---------|:---------|
|Forms     <br/> |（儲存為 PDF 檔案） 的表單和表單 （儲存 CSV 檔案中） 的回覆電子郵件附加且儲存在隱藏的資料夾中建立表單之使用者的信箱。 當您匯出內容從 PST 檔案中的表單時，此資料位於名為下列全域唯一識別 (guid) 的子資料夾中的 [ **ApplicationDataRoot** ] 資料夾： **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**。        <br/> |
|MyAnalytics    <br/> |   MyAnalytics 提供使用者深入了解有關如何在每日花在其根據其信箱中的郵件和行事曆資料的時間。 此資料儲存在隱藏的資料夾中的使用者的信箱。 如需詳細資訊 MyAnalytics 資料及如何將其匯出，請參閱 <<c0>從 MyAnalytics 匯出資料。      <br/> |
|Office 365 群組    <br/>|  電子郵件、 行事曆項目、 連絡人 （人員）、 備忘稿和工作會儲存在與 Office 365 群組相關聯的信箱。       <br/> |
|Outlook/Exchange Online<br/>|  電子郵件、 行事曆項目、 連絡人 （人員）、 備忘稿和工作會儲存在使用者的信箱。       <br/> |
|人員    <br/> |  人員應用程式 （也就是可在 Outlook 中存取該組相同的連絡人） 的連絡人會儲存在使用者的信箱。      <br/> |
|Planner     <br/> |   在 Planner 中建立的計劃會儲存在對應的 Office 365 群組時建立新的計劃佈建的信箱。 群組信箱的別名是計劃的名稱。      <br/> |
|商務用 Skype    <br/>  | 在商務用 Skype 對話會儲存在使用者的信箱中的 [交談歷程記錄] 資料夾。 如果 Skype 會議的參與者的信箱處於訴訟暫止狀態或指派到保留原則後，附加至會議的檔案會保留在參與者信箱。         <br/> |
|Sway     <br/> |  Sways 會儲存為 HTML 檔案附加到電子郵件，並儲存在隱藏的資料夾中建立 sway 之使用者的信箱。 當您匯出內容從 PST 檔案中的 Sway 時，此資料位於名為下列 guid 的子資料夾中的 [ **ApplicationDataRoot** ] 資料夾中） **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**。       <br/> |
|工作    <br/> |  在 [工作] app 中的工作 （也就是可在 Outlook 中存取的相同的工作） 會儲存在使用者的信箱。       <br/> |
|Teams    <br/>  |屬於小組通道的交談儲存在小組與相關聯的信箱。 交談屬於 [聊天室] 清單中 （也稱為*1 x N 聊天室*） 的團隊會儲存在參與聊天室的使用者信箱。 此外，會議與通話中的小組通道的摘要資訊會儲存在使用者撥入會議或通話者的信箱。 <br/> | 
|To-Do  <br/> | 工作 (稱為*to-dos*，它們儲存於待辦事項清單) 中的待辦事項應用程式會儲存在使用者的信箱。        <br/> |
||||

> [!NOTE]
> 目前，如果保留在信箱上 （藉由使用 eDiscovery 和進階電子文件探索案例中的保留），從表單和 Sway 的內容不會保留此保留。 