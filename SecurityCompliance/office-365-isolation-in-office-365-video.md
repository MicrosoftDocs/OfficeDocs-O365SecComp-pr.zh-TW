---
title: Office 365 視訊] 中的 office 365 租用戶隔離
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
description: 摘要： 在 Office 365 視訊的租用戶隔離說明。
ms.openlocfilehash: e153605a0e8d938ab7bddb92e46d7d54a94f612a
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091045"
---
# <a name="tenant-isolation-in-office-365-video"></a>Office 365 影片中的租用戶隔離

> [!NOTE]
> Office 365 影片將會取代 Microsoft 資料流。若要深入了解新的企業視訊服務會智慧新增視訊的共同作業及目前的 Office 365 視訊客戶了解轉換方案，請參閱[移轉到來自 Office 365 視訊資料流](https://docs.microsoft.com/stream/)。

## <a name="introduction"></a>簡介
Azure 存放區用來儲存的多個 Office 365 服務，包括 Office 365 影片和 Sway 資料。Azure 儲存包含 Blob 存放區，這是用來儲存非結構化的資料高度可擴充、 REST 型雲端物件存放區。Azure 儲存使用簡單存取控制模型;每個 Azure 訂閱可以建立一個或多個儲存區的帳戶。每個儲存帳戶具有單一私密金鑰用來控制存取至該存放區的帳戶中的所有資料。這種情況支援其中儲存區相關聯的應用程式，而這些應用程式可完全控制其關聯的資料 ； 一般案例例如，Sway Azure 存放區中儲存的內容。Sway 所有客戶內容會都儲存在共用 Azure 儲存的帳戶。每位使用者的內容會在不同的目錄樹狀目錄中的 blob 位於 Azure 存放區。

隔離 21vianet microsoft Azure 應用程式內的管理 （例如 Azure 入口網站、 SMAPI、 等） 的客戶環境的存取系統。這就必定分隔客戶存取基礎結構的客戶應用程式及儲存層。

## <a name="tenant-isolation-in-office-365-video"></a>Office 365 影片中的租用戶隔離
[Office 365 視訊](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)是提供組織都會特別高、 全組織的目的地的張貼、 共用及探索視訊內容的企業入口網站。在 Office 365 影片中，每個用戶影片隔離和已加密中保留所有位置及皆可用只有已驗證的使用者具有存取及組織的影片的權限。Office 365 影片使用技術的組合來完成這項作業：
- SharePoint Online 是用來儲存的視訊檔案和中繼資料 （影片標題、 描述）。它也提供 （包括驗證） 的安全性和規範層，及搜尋功能。
- Azure Media Services 提供針對轉碼、 調適型串流、 （使用 AES 加密） 的安全傳遞和縮圖的功能。

[Azure 媒體 Services](https://azure.microsoft.com/services/media-services/)是平台為-a-服務提供啟用端對端媒體雲端中的工作流程。平台提供 REST API 的上傳、 編碼、 加密 （含有 PlayReady) 以及媒體透過全球各地的 Azure 資料中心的傳遞。

所有上的傳給 Office 365 視訊發生透過 HTTPS。影片檔案上傳、 時儲存在 SharePoint Online 和檔案的複本透過加密通道傳送至 Azure 媒體服務。Azure Media Services 轉碼視訊至多個格式進行過最佳化的檢視經驗 （例如行動、 低頻寬高頻寬、 等）。這些檔案，以及 [原始檔案期間上傳，取得儲存在 Azure Blob 存放區中。將檔案使用每個 MPEG 一般加密封裝演算法 （或舊版 PlayReady） 播放] 之下的 AES 128 加密和使用之前儲存在 Azure Blob 存放區中的 AES 256 儲存加密加密。（使用 Azure 媒體服務用戶端 SDK，客戶可以控制使用的加密。例如，客戶無法適用於 Azure Media Services 儲存加密 (AES 256) 高價值媒體資產之前將 Azure Blob 儲存上傳其。）

Azure 媒體服務也會產生它傳輸縮圖的中繼資料至 SharePoint Online 透過加密通道及視訊縮圖。
