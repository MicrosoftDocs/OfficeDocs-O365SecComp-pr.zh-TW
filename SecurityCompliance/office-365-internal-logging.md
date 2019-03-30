---
title: Office 365 的 Office 365 工程內部記錄
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
description: 說明如何內部登記錄的 Office 365 工程團隊運作。
ms.openlocfilehash: e8798d4c6d4ba7393612f9a2b22bc282956a2aa9
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004212"
---
# <a name="internal-logging-for-office-365-engineering"></a><span data-ttu-id="d8238-103">Office 365 工程內部記錄</span><span class="sxs-lookup"><span data-stu-id="d8238-103">Internal Logging for Office 365 Engineering</span></span>
<span data-ttu-id="d8238-104">除了事件和供客戶使用的記錄資料，還有就可使用 Office 365 工程內部記錄資料集合系統。</span><span class="sxs-lookup"><span data-stu-id="d8238-104">In addition to the events and log data available for customers, there is also an internal log data collection system that is available to Office 365 engineers.</span></span> <span data-ttu-id="d8238-105">許多不同類型的記錄資料從 Office 365 伺服器上傳至運算稱為宇宙服務內部、 大的資料。</span><span class="sxs-lookup"><span data-stu-id="d8238-105">Many different types of log data are uploaded from Office 365 servers to an internal, big data computing service called Cosmos.</span></span> <span data-ttu-id="d8238-106">每個服務小組會將稽核記錄檔，從其各自的伺服器上傳至宇宙資料庫以進行彙總及分析。</span><span class="sxs-lookup"><span data-stu-id="d8238-106">Each service team uploads audit logs from their respective servers into the Cosmos database for aggregation and analysis.</span></span> <span data-ttu-id="d8238-107">FIPS 140-2-驗證 TLS 連線特別核准的連接埠和通訊協定使用一個稱為 Office 資料載入器 (ODL) 的專屬的自動化工具，就會發生此資料傳送。</span><span class="sxs-lookup"><span data-stu-id="d8238-107">This data transfer occurs over a FIPS 140-2-validated TLS connection on specifically approved ports and protocols using a proprietary automation tool called the Office Data Loader (ODL).</span></span> <span data-ttu-id="d8238-108">工具在 Office 365 中用來收集和處理程序的稽核記錄不允許永久，或者不能取消變更原始稽核記錄的內容或時間排序。</span><span class="sxs-lookup"><span data-stu-id="d8238-108">The tools used in Office 365 to collect and process audit records do not allow permanent or irreversible changes to the original audit record content or time ordering.</span></span>

<span data-ttu-id="d8238-109">服務小組會使用為集中存放庫宇宙，以進行分析的應用程式使用量，以測量系統以及操作效能，並尋找異常和可能表示問題或安全性問題的模式。</span><span class="sxs-lookup"><span data-stu-id="d8238-109">Service teams use Cosmos as a centralized repository to conduct an analysis of application usage, to measure system and operational performance, and to look for abnormalities and patterns that may indicate problems or security issues.</span></span> <span data-ttu-id="d8238-110">每個服務小組上傳的基準之記錄到宇宙，根據他們正在分析時，通常包含下列：</span><span class="sxs-lookup"><span data-stu-id="d8238-110">Each service team uploads a baseline of logs into Cosmos, depending on what they are looking to analyze, that often include:</span></span>
- <span data-ttu-id="d8238-111">事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="d8238-111">Event logs</span></span>
- <span data-ttu-id="d8238-112">AppLocker 記錄檔</span><span class="sxs-lookup"><span data-stu-id="d8238-112">AppLocker logs</span></span>
- <span data-ttu-id="d8238-113">效能資料</span><span class="sxs-lookup"><span data-stu-id="d8238-113">Performance data</span></span>
- <span data-ttu-id="d8238-114">System Center data</span><span class="sxs-lookup"><span data-stu-id="d8238-114">System Center data</span></span>
- <span data-ttu-id="d8238-115">詳細通話記錄</span><span class="sxs-lookup"><span data-stu-id="d8238-115">Call detail records</span></span>
- <span data-ttu-id="d8238-116">經驗品質資料</span><span class="sxs-lookup"><span data-stu-id="d8238-116">Quality of experience data</span></span>
- <span data-ttu-id="d8238-117">IIS 網頁伺服器記錄檔</span><span class="sxs-lookup"><span data-stu-id="d8238-117">IIS Web Server logs</span></span>
- <span data-ttu-id="d8238-118">SQL Server 記錄檔</span><span class="sxs-lookup"><span data-stu-id="d8238-118">SQL Server logs</span></span>
- <span data-ttu-id="d8238-119">Syslog 資料</span><span class="sxs-lookup"><span data-stu-id="d8238-119">Syslog data</span></span>
- <span data-ttu-id="d8238-120">安全性稽核記錄檔</span><span class="sxs-lookup"><span data-stu-id="d8238-120">Security audit logs</span></span>

<span data-ttu-id="d8238-121">之前將資料上傳到宇宙，ODL 應用程式使用清除 service 模糊任何包含客戶資料，例如租用戶資訊及使用者識別資訊的欄位，並將這些欄位取代雜湊值。</span><span class="sxs-lookup"><span data-stu-id="d8238-121">Prior to uploading data into Cosmos, the ODL application uses a scrubbing service to obfuscate any fields that contain customer data, such as tenant information and end-user identifiable information, and replace those fields with a hash value.</span></span> <span data-ttu-id="d8238-122">將匿名與雜湊記錄會修正，然後上傳到宇宙。</span><span class="sxs-lookup"><span data-stu-id="d8238-122">The anonymized and hashed logs are rewritten and then uploaded into Cosmos.</span></span> <span data-ttu-id="d8238-123">服務小組針對相互關聯，警示，以及報告其資料在宇宙執行範圍的查詢。</span><span class="sxs-lookup"><span data-stu-id="d8238-123">Service teams run scoped queries against their data in Cosmos for correlation, alerting, and reporting.</span></span> <span data-ttu-id="d8238-124">宇宙中的稽核記錄資料保留期間取決於服務小組;若要支援安全性事件調查並以符合法規保留需求，大部分的稽核記錄資料會保留 90 天或更久。</span><span class="sxs-lookup"><span data-stu-id="d8238-124">The period of audit log data retention in Cosmos is determined by the service teams; most audit log data is retained for 90 days or longer to support security incident investigations and to meet regulatory retention requirements.</span></span>

<span data-ttu-id="d8238-125">存取 Office 365 資料儲存在宇宙只有授權的人員。</span><span class="sxs-lookup"><span data-stu-id="d8238-125">Access to Office 365 data stored in Cosmos is restricted to authorized personnel.</span></span> <span data-ttu-id="d8238-126">Microsoft 服務負責稽核功能的小組成員少部分限制的稽核功能的管理。</span><span class="sxs-lookup"><span data-stu-id="d8238-126">Microsoft restricts the management of audit functionality to the limited subset of service team members that are responsible for audit functionality.</span></span> <span data-ttu-id="d8238-127">這些小組成員不需要修改或刪除資料從宇宙，能夠與宇宙記錄機制的所有變更都記錄及稽核。</span><span class="sxs-lookup"><span data-stu-id="d8238-127">These team members do not have the ability to modify or delete data from Cosmos, and all changes to logging mechanisms for Cosmos are recorded and audited.</span></span>

<span data-ttu-id="d8238-128">每個服務小組進行授權以進行特定分析特定應用程式以存取其記錄資料以供分析。</span><span class="sxs-lookup"><span data-stu-id="d8238-128">Each service team accesses its log data for analysis by authorizing certain applications to conduct specific analysis.</span></span> <span data-ttu-id="d8238-129">例如，Office 365 安全性小組使用資料從宇宙專屬的事件記錄剖析器透過相互關聯，提醒，並在 Office 365 的實際執行環境中產生可採取動作可能可疑的活動報告。</span><span class="sxs-lookup"><span data-stu-id="d8238-129">For example, the Office 365 Security team uses data from Cosmos through a proprietary event log parser to correlate, alert, and generate actionable reports on possible suspicious activity in the Office 365 production environment.</span></span> <span data-ttu-id="d8238-130">更正弱點，並改善服務的整體效能，會使用此資料的報告。</span><span class="sxs-lookup"><span data-stu-id="d8238-130">The reports from this data are used to correct vulnerabilities, and to improve the overall performance of the service.</span></span> <span data-ttu-id="d8238-131">如果特定提醒或報表時，需要進一步調查，服務人員可以要求資料，匯入回至 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="d8238-131">If a specific alert or report requires further investigation, service personnel can request that data be imported back into the Office 365 service.</span></span> <span data-ttu-id="d8238-132">自特定的記錄檔從宇宙匯入在加密，服務人員不需要存取解密金鑰，目標記錄檔以程式設計方式通過範圍的結果傳回授權的服務人員解密服務。</span><span class="sxs-lookup"><span data-stu-id="d8238-132">Since the specific log being imported from Cosmos is in encrypted and service personnel do not have access to decryption keys, the target log is programmatically passed through a decryption service that returns scoped results to the authorized service personnel.</span></span> <span data-ttu-id="d8238-133">此作業中找到任何弱點報告，以及擴大使用 Microsoft 的標準安全性事件管理通道。</span><span class="sxs-lookup"><span data-stu-id="d8238-133">Any vulnerabilities found from this exercise are reported and escalated using Microsoft's standard security incident management channels.</span></span>
