---
title: Office 365 的資料不變性
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
description: 定義，並說明資料不變性或必須可供搜尋的資料和損毀，也無法變更。
ms.openlocfilehash: b23a62dd95ec2ca554997fc667d89e6979e5b747
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262865"
---
# <a name="immutability-in-office-365"></a>Office 365 中的不變性
某些組織、 法規遵循、 內部控管需求，或訴訟暫止的風險需要保留電子郵件和可被探索到表單中的相關的資料。 系統中的所有資料必須都可供搜尋，並都可完全沒有損毀，或變更。 業界標準字詞，這是 「 不變性。 」 

傳統方法達到不變性通常曾以將電子郵件移至不同的唯讀的儲存位置。 雖然這類系統提供保留信箱項目，適用於探索的用途，它們通常會影響的使用者經驗顯著藉由移除保留自訂的每日工作流程中的項目。 適用於 IT 專業人員，這個方法可以不變性需要持續維護個別的伺服器和儲存體基礎結構與部署。 執行探索本身時若搭配外部郵件系統，相關聯的部署與維護成本的工具。

透過就地保留和封存搭配 Office 365 套件，例如 Exchange Online、 SharePoint Online、 商務用 OneDrive 和商務用 Skype 中服務和 Office 365 中的保留原則功能的組態在 Office 365 中封存可以保留並保留多個類別的內送、 內部和撥出的資料包括：
- 輸入和輸出電子郵件通訊
- 通訊錄與共用的線上文件或電子郵件表單中所包含的記錄
- 會議邀請
- 傳真
- 立即訊息
- 線上會議期間共用的文件
- 語音郵件要

此外，Microsoft 已開發的附加元件功能，以從其他來源透過整合的[封存資料的](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc)擷取的協力廠商資料及管理解決方案。 協力廠商資料匯入之後，您可以將 Office 365 合規性功能套用至資料，包括訴訟暫止狀態，就地 eDiscovery 和保留、 符合性搜尋、 就地封存、 稽核，以及保留原則。 例如，當信箱置於訴訟暫止狀態時，協力廠商資料將會保留。 您可以使用就地 eDiscovery 或規範搜尋來搜尋協力廠商資料。 或者，您可以將封存和保留原則套用至協力廠商資料，就像您可以對 Microsoft 資料進行的動作一樣。 總之，封存在 Office 365 中的協力廠商資料可協助組織符合規範與政府法規的原則。

在 Office 365 中封存提供證券與 Exchange 委員會 （秒） 規則 17a 4-相容的儲存空間，並保留永久檔案的所有資料收集非可重複燒錄、 非可清除格式，使用就地保留原則和保留原則包括保留鎖定。 特別是：
- 會儲存使用上述的保留原則的所有記錄會都保留在不足的一般使用者 purview 專用的儲存區。 此外，只有授權的使用者可以存取及搜尋這些記錄，但無法改變或清除它們。
- 每個項目的中繼資料保留期間的計算包含使用時間戳記。 在收到新的項目時，會套用時間戳記或建立並無法後續修改或移除從中繼資料。
- 在 Office 365 中封存 」 可讓使用者合併不同的保留原則和保留動作，以建立細微的保留原則，以定義的類型或位置的項目會保留不變，與這類保留持續時間。
- 保留鎖定功能可讓使用者選擇是否要讓原則成為嚴格的原則。 嚴格的原則會禁止任何人都可讓您移除、 停用或變更的保留原則。 這表示一旦啟用保留鎖定、 無法停用它，並將存在的任何機制下的任何資料從現有 custodians 收集而來的保留原則中的位置可能會覆寫，修改，清除或刪除期間保留期間。 此外，保留期間設定保留鎖定可能不是縮短或減少。 不過，可能加長，若是繼續保留儲存的資料，成為上述的法律需求。 保留鎖定可確保沒有人，甚至不系統管理員或其他含有特定控制項的存取，可能會變更的設定或覆寫或清除已儲存的資料將在 Office 365 中封存內嵌秒 2003年版本中所設定的指引規則 17a-4。

客戶進一步了解如何運用 Office 365 符合其法規義務，特別是相對規則 17a-4 需求，我們已發行涵蓋 Exchange Online 封存，SharePoint Online、 OneDrive[白皮書](https://go.microsoft.com/fwlink/?linkid=830440)for Business 和商務用 Skype。 本白皮書也提供深入分析 Office 365 封存功能以及針對每個下 SEC Rule 17a-4 需求的功能，並示範受管制客戶如何 Office 365 封存可讓它們以符合這些需求。