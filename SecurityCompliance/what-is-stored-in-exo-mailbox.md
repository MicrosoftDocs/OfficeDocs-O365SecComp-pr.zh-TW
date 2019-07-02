---
title: 儲存在 Exchange Online 信箱中的內容
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
description: Office 365 中的雲端式應用程式所產生的資料, 會儲存在 Microsoft 雲端的使用者 Exchange Online 信箱中。
ms.openlocfilehash: d2d126d28a9b92962af7637610282e99e7685594
ms.sourcegitcommit: ecc823c2a4f1465114cf1d3a4630e31c47779ddc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2019
ms.locfileid: "35079397"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>儲存在 Exchange Online 信箱中的內容

Exchange Online 中的信箱主要用來儲存與電子郵件相關的專案, 例如郵件、行事曆專案、工作和記事。 但是, 若要變更為更多雲端式 Office 365 應用程式, 也會將其資料儲存在使用者的信箱中。 將資料儲存在信箱中的其中一個好處, 就是您可以使用內容搜尋、eDiscovery、高級 eDiscovery 和資料調查中的搜尋工具, 來尋找、查看及匯出這些雲端式應用程式中的資料。 這些應用程式中的資料會儲存在信箱中非人際郵件 (非 IPM) 子樹系的隱藏資料夾中。 這表示當使用者使用 Outlook 或其他郵件用戶端存取其信箱時, 會將資料隱藏在使用者的視圖中。

下表列出在雲端式信箱中儲存資料的 Office 365 應用程式。 該表也會說明每個應用程式所儲存的內容類型。

|Office 365 應用程式  |描述  |
|:---------|:---------|
|Forms     <br/> |表單 (儲存為 PDF 檔案) 和對表單的回應 (儲存于 CSV 檔案中) 會附加至電子郵件, 並儲存在建立表單之使用者信箱的隱藏資料夾中。 當您從 PST 檔案中的表單匯出內容時, 此資料會位於名為的子資料夾中的**ApplicationDataRoot**資料夾中, 該子資料夾具有下列全域唯一識別 (GUID): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**。        <br/> |
|Office 365 群組    <br/>|  電子郵件、行事曆專案、連絡人 (人員)、記事和任務都儲存在與 Office 365 群組相關聯的信箱中。       <br/> |
|Outlook/Exchange Online<br/>|  電子郵件、行事曆專案、連絡人 (人員)、記事和任務都儲存在使用者的信箱中。       <br/> |
|人員    <br/> |  [人員] 應用程式中的連絡人 (與 Outlook 中可存取的連絡人相同) 會儲存在使用者的信箱中。      <br/> |
|類別排程     <br/> |   在課程排程中建立的計畫, 會儲存在建立新計畫時所布建的對應 Office 365 群組信箱中。 群組信箱的別名是計畫的名稱。      <br/> |
|商務用 Skype    <br/>  | 商務用 Skype 中的對話會儲存在使用者信箱的 [交談記錄] 資料夾中。 如果將 Skype 會議的參與者的信箱設為訴訟暫止或指派給保留原則, 則附加至會議的檔案會保留在參與者信箱中。         <br/> |
|Sway     <br/> |  Sway 會儲存為附加至電子郵件的 HTML 檔案, 並儲存在建立 sway 之使用者信箱的隱藏資料夾中。 當您從 PST 檔案中的 Sway 匯出內容時, 此資料位於名為 with the GUID 的子資料夾中的**ApplicationDataRoot**資料夾中 (以下列 GUID) **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**。       <br/> |
|工作    <br/> |  任務應用程式中的工作 (與 Outlook 中可存取的工作相同), 會儲存在使用者的信箱中。       <br/> |
|Teams    <br/>  |屬於小組管道的交談, 會儲存在與小組相關聯的信箱中。 屬於小組中之聊天室清單一部分的交談 (也稱為*1 x N 聊天*) 會儲存在參與聊天的使用者信箱中。 此外, 在小組通道中的會議和通話的摘要資訊會儲存在撥入會議或通話的使用者信箱中。 <br/> | 
|To-Do  <br/> | 在 [待辦事項] 應用程式中的任務 (稱為待辦*事項*清單) 會儲存在使用者的信箱中。        <br/> |
||||

> [!NOTE]
> 此時, 如果保留信箱 (使用 eDiscovery 和 Advanced eDiscovery 案例中的保留), 則保留功能將不會保留來自表單和 Sway 的內容。 