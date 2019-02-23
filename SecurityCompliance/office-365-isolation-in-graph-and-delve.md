---
title: 在 Office 中的 office 365 租用戶隔離圖形及探索
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 摘要： 租用戶隔離 Delve 及 Office 圖形中說明。
ms.openlocfilehash: cb1b432dccff6c4f890ef4aeb8ea4c19989b09d5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216803"
---
# <a name="tenant-isolation-in-the-office-graph-and-delve"></a>Office Graph 與 Delve 中的租用戶隔離

## <a name="tenant-isolation-in-the-office-graph"></a>在 Office 圖中顯示的租用戶隔離
[Office 圖表](https://dev.office.com/officegraph)模型活動在 Office 365 服務、 商務、 Azure Active Directory、 及詳細資訊，包括 Exchange Online、 SharePoint Online、 Yammer、 Skype 及其他 Microsoft 服務或協力廠商服務外部服務。Office 圖表元件可用整個 Office 365 中。Office 圖表代表一群內容及活動，與發生跨整個 Office 套件的兩者之間的關係。它會使用複雜的機器學習技術 （英文） 連線至相關的內容、 對話及周圍這些人員的人員。例如承租人索引 SharePoint Online 中的有 Office 圖表索引用來提供 Delve 查詢服務、 SharePoint Online 中的 「 分析處理引擎用來儲存信號和計算前瞻、 與 Exchange Online 會計算每位使用者做為輸入到租用戶分析的收件者快取。

Office 圖表包含企業物件，例如人員及文件，以及關係與這些物件之間的互動的相關資訊。*邊緣*以表示關聯及互動。Office 圖表被區分依承租人如此邊緣能夠只存在於相同租用中的*節點*之間。*節點*為具有統一資源識別元 (URI)、 節點類型、 存取控制清單，以及一組 facet 包含*中繼資料*與邊緣的實體。每個節點相關聯的中繼資料與邊緣、 排入*facet*如常見的知識模型所示。*中繼資料*被具名內容儲存在其可用為搜尋、 篩選或分析 office 圖表內的節點上。*Facet*是邏輯的一組的中繼資料與在節點上的邊緣。每個 facet 說明一個節點的外觀。 

Office 圖表不會將所有資料移入單一存放庫 ；而是儲存中繼資料與其他地方儲存的資料相關的關係。Office 圖表是由數個資料儲存區和處理元件所組成：
- 租用戶圖存放區提供有效率的分析最適合的大量儲存區。
- 作用中的內容快取提供至作用中節點的快速隨機存取和磁碟機使用者體驗的邊緣。
- 輸入的路由器通知元件內部和外部的用戶圖的變更。

分析內每個工作負載推斷前瞻相關租用戶全計算並加以推送到用戶圖。租用戶分析的原因 over 租用中的所有活動產生算行為的模式。例如，Exchange Online 計算有效率地原因每位使用者的信箱上的分析與每個使用者的收件者快取。這些個別使用者分析會產生一組*RecipientCache 邊緣*的每個人，在其中接下來推送至租用戶圖。這會保持不變部分接近位置儘可能的來源資料的分析處理。

## <a name="tenant-isolation-in-delve"></a>在租用戶隔離探索
如前文所述，Office 圖力量他人探索和共同作業在其 enterprise 中，目前活動的體驗，並提供實體為主的平台原因的分析內容及活動上不同工作負載與超過 Office 365。探索是第一個由 Office 圖提供這類經驗。探索是透過 Office 圖表至 Office 365 使用者會內容從 Office 365 和 Yammer Enterprise 呈現 Office 365 web 功能。網站體驗將資料顯示為每個特定主題，例如*周圍我的 [趨勢*] 或 [*修改由我*的不同區。每個版包含數個文件卡片顯示摘要文字與文件中的圖片。卡片可讓使用者執行像是開啟文件或文件的 Yammer] 頁面上作業。沒有顯示最相關的文件的這個人 Office 365 租用戶和可以呼叫 Exchange Online 或企業版 Skype 互動與該連絡人的圖示中的每個人的頁面。Delve 根據 Office 圖表 API，因為它是租用戶為基礎的隔離該 API 所繫結。