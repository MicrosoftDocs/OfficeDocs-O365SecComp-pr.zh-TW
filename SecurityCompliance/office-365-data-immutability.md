---
title: Office 365 資料不變性
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 定義並說明資料不變性或必須是可供搜尋的資料並無法移除或變更。
ms.openlocfilehash: ab7bfc3795da761eacc9e9aa7d41e69e482fc411
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090875"
---
# <a name="immutability-in-office-365"></a>Office 365 中的不變性
有些組織、 規範、 內部控管需求或訴訟資料暫留風險需要保留電子郵件和可供搜尋的表單中的相關的資料。系統中的所有資料都必須可供搜尋、 且完全沒有可移除或變更。這的業界標準字詞是"不變性。 」 

繁體中文方法變性通常有將電子郵件訊息移至不同、 唯讀的儲存位置正常運作。雖然這類系統提供服務的目的保存的探索信箱項目，他們通常會影響使用者經驗重大的方式來移除保留項目從慣用的每日工作流程。適用於 IT 專業人員不變性這個方法需要的部署和持續維護個別的伺服器及儲存基礎結構。探索本身被執行工具外部郵件系統，具有相關聯的部署與維護成本。

透過設定為就地保留和封存 Office 365 中並搭配 Office 365 套裝軟體，例如 Exchange Online、 SharePoint Online、 OneDrive for Business 和 Skype for Business，在服務中的保留原則功能封存 Office 365 中可保留並保留來電、 內部及撥出的資料包含許多類別：
- 內送和外寄電子郵件通訊
- 書籍和共用的線上文件或電子郵件表單中所包含的記錄
- 會議邀請
- 傳真
- 立即訊息
- 線上會議期間共用的文件
- 語音郵件要

此外，Microsoft 已經開發允許從其他來源整合到[封存的資料](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc)與協力廠商資料擷取及管理解決方案的附加元件功能。在匯入協力廠商資料之後，您可以套用 Office 365 的符合性功能資料，包括訴訟暫止狀態、 就地 eDiscovery 和保留、 規範搜尋、 就地封存、 稽核、 及保留原則。例如，當信箱處於訴訟暫止狀態，則會保留與協力廠商資料。您可以使用就地 eDiscovery 或規範搜尋來搜尋協力廠商資料。或您可以套用封存和保留原則就像您可以為 Microsoft 資料的第三方資料。在短封存 Office 365 中的第三方資料可協助組織保持在最符合政府和法規的原則。

在 Office 365 中封存提供證券 and Exchange 委員會 （秒） 規則 17a 4-相容存放區，並保留永久檔案的所有資料收集使用就地保留原則和保留原則以非可重複燒錄、 非可清除格式包括保留鎖定。特別：
- 會儲存使用上述上方的保留原則的所有記錄會都保留在專用的存放區] 區域中不在一般使用者的 purview。此外，授權的使用者可以存取和搜尋這些記錄，但無法更改或清除其。
- 每個項目的中繼資料保留期間的計算包含使用時間戳記。接收到新的項目時套用時間戳記或建立並無法後續修改或移除中繼資料。
- 在 Office 365 中封存可讓使用者結合不同保留原則和保留動作建立更精細的保留原則來定義要會永久保留的類型或位置的項目與這類保留持續時間。
- 保留鎖定功能可讓使用者選擇是否要將原則設定嚴格的原則。嚴格的原則會禁止任何人都擁有移除、 停用或變更的保留原則的能力。這表示保留鎖定已啟用、 它不能停用，且沒有機制會存在於之後下的任何資料從現有的 custodians 保留已收集備妥原則可能會覆寫、 修改、 清除或刪除期間保留期間。進一步、 保留期間設定保留鎖定可能不是簡稱或縮小。有，但可能加長，但如果是以繼續保留的預存的資料，成為上述法規需求。保留鎖定可確保無人、 不甚至是系統管理員或這些特定控制項的存取權，可能會變更的設定或覆寫或清除具有已儲存的資料將引進 Office 365 中設定反覆秒 2003年版本中的指導與封存規則條例 17a-4。

客戶更深入了解如何利用 Office 365，以符合其法規責任，特別是與規則條例 17a-4 需求，我們已發行涵蓋 Exchange Online 封存、 SharePoint Online、 OneDrive[白皮書 （英文）](https://go.microsoft.com/fwlink/?linkid=830440)for Business 和 Skype for Business。本白皮書也提供深入的分析的 Office 365 封存功能並針對每個下秒規則條例 17a-4 需求的功能與規範的客戶示範如何封存 Office 365 可以讓他們能夠符合這些需求。