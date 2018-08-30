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
ms.collection: Strat_O365_Enterprise
description: 摘要： 在 Office 365 視訊的租用戶隔離說明。
ms.openlocfilehash: 9476047d56161ec2589fdf743d7ee837ea558865
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527017"
---
# <a name="tenant-isolation-in-office-365-video"></a><span data-ttu-id="1a4f7-103">Office 365 影片中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="1a4f7-103">Tenant Isolation in Office 365 Video</span></span>

> [!NOTE]
> <span data-ttu-id="1a4f7-p101">Office 365 影片將會取代 Microsoft 資料流。若要深入了解新的企業視訊服務會智慧新增視訊的共同作業及目前的 Office 365 視訊客戶了解轉換方案，請參閱[移轉到來自 Office 365 視訊資料流](https://docs.microsoft.com/stream/)。</span><span class="sxs-lookup"><span data-stu-id="1a4f7-p101">Office 365 Video will be replaced by Microsoft Stream. To learn more about the new enterprise video service that adds intelligence to video collaboration and learn about the transition plans for current Office 365 Video customers, see [Migrate to Stream from Office 365 Video](https://docs.microsoft.com/stream/).</span></span>

## <a name="introduction"></a><span data-ttu-id="1a4f7-106">簡介</span><span class="sxs-lookup"><span data-stu-id="1a4f7-106">Introduction</span></span>
<span data-ttu-id="1a4f7-p102">Azure 存放區用來儲存的多個 Office 365 服務，包括 Office 365 影片和 Sway 資料。Azure 儲存包含 Blob 存放區，這是用來儲存非結構化的資料高度可擴充、 REST 型雲端物件存放區。Azure 儲存使用簡單存取控制模型;每個 Azure 訂閱可以建立一個或多個儲存區的帳戶。每個儲存帳戶具有單一私密金鑰用來控制存取至該存放區的帳戶中的所有資料。這種情況支援其中儲存區相關聯的應用程式，而這些應用程式可完全控制其關聯的資料 ； 一般案例例如，Sway Azure 存放區中儲存的內容。Sway 所有客戶內容會都儲存在共用 Azure 儲存的帳戶。每位使用者的內容會在不同的目錄樹狀目錄中的 blob 位於 Azure 存放區。</span><span class="sxs-lookup"><span data-stu-id="1a4f7-p102">Azure Storage is used to store data for multiple Office 365 services, including Office 365 Video and Sway. Azure Storage includes Blob storage, which is a highly-scalable, REST-based, cloud object store that is used for storing unstructured data. Azure Storage uses a simple access control model; each Azure subscription can create one or more Storage Accounts. Each Storage Account has a single secret key that is used to control access to all data in that Storage Account. This supports the typical scenario where storage is associated with applications and those applications have full control over their associated data; for example, Sway storing content in Azure Storage. All customer content for Sway is stored in shared Azure storage accounts. Each user's content is in a separate directory tree of blobs in Azure storage.</span></span>

<span data-ttu-id="1a4f7-p103">隔離 21vianet microsoft Azure 應用程式內的管理 （例如 Azure 入口網站、 SMAPI、 等） 的客戶環境的存取系統。這就必定分隔客戶存取基礎結構的客戶應用程式及儲存層。</span><span class="sxs-lookup"><span data-stu-id="1a4f7-p103">The systems managing access to customer environments (e.g., the Azure Portal, SMAPI, etc.) are isolated within an Azure application operated by Microsoft. This logically separates the customer access infrastructure from the customer applications and storage layer.</span></span>

## <a name="tenant-isolation-in-office-365-video"></a><span data-ttu-id="1a4f7-116">Office 365 影片中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="1a4f7-116">Tenant Isolation in Office 365 Video</span></span>
<span data-ttu-id="1a4f7-p104">[Office 365 視訊](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)是提供組織都會特別高、 全組織的目的地的張貼、 共用及探索視訊內容的企業入口網站。在 Office 365 影片中，每個用戶影片隔離和已加密中保留所有位置及皆可用只有已驗證的使用者具有存取及組織的影片的權限。Office 365 影片使用技術的組合來完成這項作業：</span><span class="sxs-lookup"><span data-stu-id="1a4f7-p104">[Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) is an enterprise portal that provides organizations with a highly secure, organization-wide destination for posting, sharing, and discovering video content. In Office 365 Video, each tenant's videos are kept isolated and encrypted in all locations, and are only available to authenticated users that have access and permissions to the organization's videos. Office 365 Video uses a combination of technologies to accomplish this:</span></span>
- <span data-ttu-id="1a4f7-p105">SharePoint Online 是用來儲存的視訊檔案和中繼資料 （影片標題、 描述）。它也提供 （包括驗證） 的安全性和規範層，及搜尋功能。</span><span class="sxs-lookup"><span data-stu-id="1a4f7-p105">SharePoint Online is used for storing the video file and metadata (video title, description, etc.). It also provides the security and compliance layer (including authentication), and search features.</span></span>
- <span data-ttu-id="1a4f7-122">Azure Media Services 提供針對轉碼、 調適型串流、 （使用 AES 加密） 的安全傳遞和縮圖的功能。</span><span class="sxs-lookup"><span data-stu-id="1a4f7-122">Azure Media Services provides transcoding, adaptive streaming, secure delivery (using AES encryption), and thumbnail features.</span></span>

<span data-ttu-id="1a4f7-p106">[Azure 媒體 Services](https://azure.microsoft.com/services/media-services/)是平台為-a-服務提供啟用端對端媒體雲端中的工作流程。平台提供 REST API 的上傳、 編碼、 加密 （含有 PlayReady) 以及媒體透過全球各地的 Azure 資料中心的傳遞。</span><span class="sxs-lookup"><span data-stu-id="1a4f7-p106">[Azure Media Services](https://azure.microsoft.com/services/media-services/) is a platform-as-a-service offering for enabling end-to-end media workflows in the cloud. The platform provides a REST API for uploading, encoding, encrypting (with PlayReady), and delivery of media through Azure datacenters around the world.</span></span>

<span data-ttu-id="1a4f7-p107">所有上的傳給 Office 365 視訊發生透過 HTTPS。影片檔案上傳、 時儲存在 SharePoint Online 和檔案的複本透過加密通道傳送至 Azure 媒體服務。Azure Media Services 轉碼視訊至多個格式進行過最佳化的檢視經驗 （例如行動、 低頻寬高頻寬、 等）。這些檔案，以及 [原始檔案期間上傳，取得儲存在 Azure Blob 存放區中。將檔案使用每個 MPEG 一般加密封裝演算法 （或舊版 PlayReady） 播放] 之下的 AES 128 加密和使用之前儲存在 Azure Blob 存放區中的 AES 256 儲存加密加密。（使用 Azure 媒體服務用戶端 SDK，客戶可以控制使用的加密。例如，客戶無法適用於 Azure Media Services 儲存加密 (AES 256) 高價值媒體資產之前將 Azure Blob 儲存上傳其。）</span><span class="sxs-lookup"><span data-stu-id="1a4f7-p107">All uploads for Office 365 Video occur via HTTPS. When a video file is uploaded, it is stored in SharePoint Online, and a copy of the file is sent via an encrypted channel to Azure Media Services. Azure Media Services transcodes the video into multiple formats that are optimized for viewing experience (e.g., mobile, low-bandwidth, high-bandwidth, etc.). These files, along with the original file acquired during upload, are stored in Azure Blob storage. The files are encrypted using AES 128 per the MPEG Common Encryption packaging algorithm (or an earlier PlayReady version) for playback, and encrypted using AES 256 storage encryption before being stored in Azure Blob storage. (Using the Azure Media Services Client SDK, customers can control which encryption is used. For example, a customer could apply Azure Media Services storage encryption (AES 256) to a high-value media asset before uploading it Azure Blob storage.)</span></span>

<span data-ttu-id="1a4f7-132">Azure 媒體服務也會產生它傳輸縮圖的中繼資料至 SharePoint Online 透過加密通道及視訊縮圖。</span><span class="sxs-lookup"><span data-stu-id="1a4f7-132">Azure Media Services also generates a thumbnail for the video, which it transmits along with thumbnail metadata to SharePoint Online via an encrypted channel.</span></span>
