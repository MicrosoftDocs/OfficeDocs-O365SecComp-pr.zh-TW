---
title: Office 365 影片中的 office 365 租用戶隔離
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
description: 摘要： 在 Office 365 影片中的租用戶隔離的說明。
ms.openlocfilehash: 071a71266191748db8f6cb27ae86e1f65dcb4d1d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262585"
---
# <a name="tenant-isolation-in-office-365-video"></a>Office 365 影片中的租用戶隔離

> [!NOTE]
> Office 365 影片會由 Microsoft Stream 取代。 若要深入了解新的企業視訊服務，將智慧新增視訊共同作業，並了解切換計劃目前的 Office 365 影片客戶，請參閱 <<c0>移轉至來自 Office 365 視訊資料流。

## <a name="introduction"></a>簡介
Azure 儲存體用來儲存多個 Office 365 服務，包括 Office 365 影片和 Sway 的資料。 Azure 儲存體包含 Blob 存放區，這是用來儲存非結構化的資料高度擴充性、 REST 型雲端物件存放區。 Azure 儲存體使用簡單存取控制模型;每個 Azure 訂用帳戶可以建立一或多個儲存體帳戶。 每個儲存體帳戶具有用來控制對該儲存體帳戶中的所有資料存取的單一祕密金鑰。 這種情況支援典型的案例，其中儲存區相關聯的應用程式，而這些應用程式具有完整控制權及其相關聯的資料;例如，在 Azure 儲存體中 Sway 儲存內容。 Sway 的所有客戶內容會都儲存在共用的 Azure 儲存體帳戶。 每位使用者的內容會位於 Azure 儲存體中的個別目錄樹狀目錄中的 blob。

系統管理存取權 （例如，Azure 入口網站、 SMAPI 等等） 的客戶環境會隔離在 21vianet 運作的 Microsoft Azure 應用程式。 這會以邏輯方式分隔客戶存取基礎結構和從客戶應用程式和儲存層。

## <a name="tenant-isolation-in-office-365-video"></a>Office 365 影片中的租用戶隔離
[Office 365 影片](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)是提供公佈、 共用與探索視訊內容高度安全的全組織的目的地的組織的企業入口網站。 在 Office 365 影片中，每位承租人的影片會保留隔離和已加密中所有的位置，以及只可為已驗證的使用者擁有存取，以及組織的影片的權限。 Office 365 影片使用技術的組合來完成這項作業：
- SharePoint Online 用來儲存的視訊檔案和中繼資料 （影片標題、 描述）。 它也會提供 （包括驗證） 的安全性與合規性層，以及搜尋功能。
- Azure 媒體服務提供轉碼、 調適型資料流、 安全傳遞 （使用 AES 加密） 及縮圖的功能。

[Azure 媒體服務](https://azure.microsoft.com/services/media-services/)是平台為-服務提供啟用端對端媒體定域機組中的工作流程。 平台上傳、 編碼、 加密 （使用 PlayReady)，和交付的媒體透過世界各地的 Azure 資料中心提供 REST API。

所有上傳的 Office 365 影片發生透過 HTTPS。 當視訊檔案上傳時，它會儲存在 SharePoint Online 中，與檔案的複本透過加密通道傳送至 Azure 媒體服務。 Azure 媒體服務轉碼到最佳化的檢視經驗 （例如，行動裝置、 低頻寬、 高頻寬等等） 的多個格式的視訊。 這些檔案，以及上傳，期間取得原始的檔案會儲存在 Azure Blob 儲存。 檔案使用 AES 128 每個播放，MPEG 常見加密封裝演算法 （或舊版 PlayReady） 加密，並且使用之前儲存在 Azure Blob 存放區中的 AES 256 儲存加密進行加密。 （使用 Azure 媒體服務用戶端 SDK，客戶可以控制使用哪一個加密。 例如，客戶可以適用於 Azure 媒體服務儲存加密 (AES 256) 高價值媒體資產上載 Azure Blob 儲存之前。）

Azure 媒體服務也會產生影片，它會連同縮圖的中繼資料，SharePoint Online 透過加密通道縮的圖。
