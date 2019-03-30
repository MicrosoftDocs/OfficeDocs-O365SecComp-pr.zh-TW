---
title: 在 Office 中的 office 365 租用戶隔離 Graph 和 Delve
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 摘要： 在 Office Graph 和 Delve 中的租用戶隔離的說明。
ms.openlocfilehash: 22bcf581c26ea4e334539a81861ff4dee68967ef
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004200"
---
# <a name="tenant-isolation-in-the-office-graph-and-delve"></a>Office Graph 與 Delve 中的租用戶隔離

## <a name="tenant-isolation-in-the-office-graph"></a>Office 圖形中的租用戶隔離
[Office Graph](https://dev.office.com/officegraph)模型活動在 Office 365 服務，包括 Exchange Online、 SharePoint Online、 Yammer、 Skype for Business、 Azure Active Directory 和更多]，和外部的服務，例如其他 Microsoft 服務或協力廠商服務。 Office Graph 元件會使用整個 Office 365。 Office Graph 代表一群內容和活動，以及它們跨整個 Office 套件，即會發生之間的關係。 它會使用複雜的機器學習技術來連線至相關的內容、 交談及人員前後的人員。 例如，SharePoint Online 中的租用戶索引具有用來提供 Delve 查詢 Office Graph 索引、 SharePoint Online 中的 「 分析處理引擎用來儲存信號，並計算深入資訊、 和 Exchange Online 會計算每位使用者做為輸入至租用戶分析的收件者快取區。

Office Graph 包含企業物件，例如人員及文件，以及關聯性和這些物件之間的互動的相關資訊。 關聯性及互動被當成*邊緣*。 Office Graph 分成事業依承租人，使得邊緣只能存在於相同的租用戶中的*節點*之間。 *節點*為以統一資源識別元 (URI)、 節點類型、 存取控制清單，以及一組 facet 包含*中繼資料*和邊緣的實體。 每個節點相關聯的中繼資料和邊緣，排列成*facet*如同常見的知識模型。 *中繼資料*是名為可以用於搜尋、 篩選或分析 office 圖形內的節點上儲存的內容。 *Facet*是中繼資料和節點上的邊緣的邏輯集合。 每個 facet 說明節點的一環。 

Office Graph 不會將所有資料移入單一存放庫;相反地，它會儲存中繼資料和資料的記錄位於其他地方相關的關聯性。 Office Graph 是由數個資料存放區和處理元件所組成：
- 租用戶 Graph 存放區提供有效率的分析最適合的大量存放區。
- 作用中的內容快取提供快速隨機存取主動節點和磁碟機的使用者體驗的邊緣。
- 輸入的路由器通知元件內部和外部的租用戶圖形的變更。

內每個工作負載的分析推算深入了解相關的全租用戶計算，並將它們推送到此租用戶圖形。 租用戶分析原因透過租用戶中的所有活動，產生的行為模式深入了解。 例如，Exchange Online 會計算與有效率地原因每位使用者的信箱上的分析每位使用者的收件者快取。 這些每位使用者分析產生*RecipientCache 邊緣*的每個人，在一組可輪流推送至租用戶圖形。 這會保留為最多的最接近盡可能的來源資料的分析處理。

## <a name="tenant-isolation-in-delve"></a>Delve 中的租用戶隔離
如先前所述，Office Graph 力量協助人員探索及共同作業在其 enterprise 中，目前活動的體驗，並提供實體為主的平台原因分析內容和活動透過跨工作負載和超過 Office 365。 Delve 是第一封由 Office Graph 提供的這類體驗。
Delve 是 Office Graph 透過 Office 365 使用者呈現內容從 Office 365 和 Yammer 企業 Office 365 web 體驗。 Web 體驗不同面板，每個都有特定主題，例如*我附近的 [趨勢*] 或 [*由我修改*方式顯示資料。 每個版包含數個顯示摘要的文字及圖片貼文件的文件卡。 卡可讓使用者執行動作等項目開啟文件或文件的 Yammer 頁面。 沒有顯示最相關的文件此人，針對 Office 365 租用戶和可以叫用 Exchange Online 或商務用 Skype 互動該人員的圖示中的每個人的頁面。 Delve 根據 Office Graph API，因為它是由該 API 的租用戶型隔離繫結。