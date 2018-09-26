---
title: Office 365 的 Office 365 工程內部記錄
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 說明如何內部登入的 Office 365 工程小組運作。
ms.openlocfilehash: 4cade759fb4c095565b4e1f85ce15ed546177082
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038186"
---
# <a name="internal-logging-for-office-365-engineering"></a><span data-ttu-id="77699-103">Office 365 工程內部記錄</span><span class="sxs-lookup"><span data-stu-id="77699-103">Internal Logging for Office 365 Engineering</span></span>
<span data-ttu-id="77699-p101">除了事件及記錄資料可供客戶，也有內部的記錄資料集合系統可供 Office 365 工程師。許多不同類型的記錄資料從 Office 365 的伺服器上傳至運算服務呼叫宇宙 internal，big 資料。每個服務小組可將稽核記錄檔從其各自的伺服器上傳到宇宙資料庫中的彙總及分析。此資料傳送發生透過 FIPS 140-2-驗證 TLS 連線特別核准的連接埠和通訊協定使用專屬的自動化工具呼叫 Office 資料載入器 (ODL)。Office 365 中使用收集的工具與程序稽核記錄不允許永久或不能取消變更原始稽核記錄的內容或時間順序。</span><span class="sxs-lookup"><span data-stu-id="77699-p101">In addition to the events and log data available for customers, there is also an internal log data collection system that is available to Office 365 engineers. Many different types of log data are uploaded from Office 365 servers to an internal, big data computing service called Cosmos. Each service team uploads audit logs from their respective servers into the Cosmos database for aggregation and analysis. This data transfer occurs over a FIPS 140-2-validated TLS connection on specifically approved ports and protocols using a proprietary automation tool called the Office Data Loader (ODL). The tools used in Office 365 to collect and process audit records do not allow permanent or irreversible changes to the original audit record content or time ordering.</span></span>

<span data-ttu-id="77699-p102">服務小組作為宇宙集中存放庫進行分析的應用程式使用量測量系統以及操作效能，並尋找異常和可能表示問題或安全性問題的模式。每個服務小組上傳的基準記錄檔的宇宙，將根據他們尋求分析，通常包含：</span><span class="sxs-lookup"><span data-stu-id="77699-p102">Service teams use Cosmos as a centralized repository to conduct an analysis of application usage, to measure system and operational performance, and to look for abnormalities and patterns that may indicate problems or security issues. Each service team uploads a baseline of logs into Cosmos, depending on what they are looking to analyze, that often include:</span></span>
- <span data-ttu-id="77699-111">事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="77699-111">Event logs</span></span>
- <span data-ttu-id="77699-112">AppLocker 記錄檔</span><span class="sxs-lookup"><span data-stu-id="77699-112">AppLocker logs</span></span>
- <span data-ttu-id="77699-113">效能資料</span><span class="sxs-lookup"><span data-stu-id="77699-113">Performance data</span></span>
- <span data-ttu-id="77699-114">System Center data</span><span class="sxs-lookup"><span data-stu-id="77699-114">System Center data</span></span>
- <span data-ttu-id="77699-115">詳細通話記錄</span><span class="sxs-lookup"><span data-stu-id="77699-115">Call detail records</span></span>
- <span data-ttu-id="77699-116">經驗品質資料</span><span class="sxs-lookup"><span data-stu-id="77699-116">Quality of experience data</span></span>
- <span data-ttu-id="77699-117">IIS Web 伺服器記錄檔</span><span class="sxs-lookup"><span data-stu-id="77699-117">IIS Web Server logs</span></span>
- <span data-ttu-id="77699-118">SQL Server 記錄檔</span><span class="sxs-lookup"><span data-stu-id="77699-118">SQL Server logs</span></span>
- <span data-ttu-id="77699-119">Syslog 資料</span><span class="sxs-lookup"><span data-stu-id="77699-119">Syslog data</span></span>
- <span data-ttu-id="77699-120">安全性稽核記錄</span><span class="sxs-lookup"><span data-stu-id="77699-120">Security audit logs</span></span>

<span data-ttu-id="77699-p103">再將資料上傳到宇宙、 ODL 應用程式使用清除 service 模糊任何欄位包含客戶資料，例如承租人資訊及使用者識別資訊，並將這些欄位取代雜湊值。修正，然後上載到宇宙匿名及雜湊記錄檔]。服務小組針對宇宙中的相互關聯之通知，並回報其資料執行範圍的查詢。服務小組 ； 取決於宇宙中的稽核記錄檔資料保留期間大部分的稽核記錄檔資料會保留期為 90 天或更久支援安全性附隨調查並符合法規保留需求。</span><span class="sxs-lookup"><span data-stu-id="77699-p103">Prior to uploading data into Cosmos, the ODL application uses a scrubbing service to obfuscate any fields that contain customer data, such as tenant information and end-user identifiable information, and replace those fields with a hash value. The anonymized and hashed logs are rewritten and then uploaded into Cosmos. Service teams run scoped queries against their data in Cosmos for correlation, alerting, and reporting. The period of audit log data retention in Cosmos is determined by the service teams; most audit log data is retained for 90 days or longer to support security incident investigations and to meet regulatory retention requirements.</span></span>

<span data-ttu-id="77699-p104">存取 Office 365 資料儲存在宇宙僅限於授權的人員。Microsoft 限制服務小組成員負責稽核功能有限的子集的稽核功能的管理。這些小組成員能夠修改或刪除資料從宇宙、 和沒有宇宙的記錄機制的所有修訂已錄製並進行稽核。</span><span class="sxs-lookup"><span data-stu-id="77699-p104">Access to Office 365 data stored in Cosmos is restricted to authorized personnel. Microsoft restricts the management of audit functionality to the limited subset of service team members that are responsible for audit functionality. These team members do not have the ability to modify or delete data from Cosmos, and all changes to logging mechanisms for Cosmos are recorded and audited.</span></span>

<span data-ttu-id="77699-p105">每個服務小組的授權以進行特定分析特定應用程式存取其記錄資料以供分析。例如，Office 365 安全性小組使用宇宙透過專屬的事件記錄剖析器的資料與相互關聯、 通知及 Office 365 實際執行環境中產生可採取的報告可能可疑的活動。此資料從報表可用以更正弱點，並改善服務的整體效能。如果特定的通知或報告需要進一步調查、 服務人員可以要求資料匯回至 Office 365 服務。自特定的記錄檔匯入從宇宙中加密和服務人員沒有解密機碼的權限、 目標記錄以程式設計方式通過解密服務授權的服務人員傳回範圍的結果。從這個練習找到任何弱點報告和擴大使用 Microsoft 的標準安全性附隨管理通道。</span><span class="sxs-lookup"><span data-stu-id="77699-p105">Each service team accesses its log data for analysis by authorizing certain applications to conduct specific analysis. For example, the Office 365 Security team uses data from Cosmos through a proprietary event log parser to correlate, alert, and generate actionable reports on possible suspicious activity in the Office 365 production environment. The reports from this data are used to correct vulnerabilities, and to improve the overall performance of the service. If a specific alert or report requires further investigation, service personnel can request that data be imported back into the Office 365 service. Since the specific log being imported from Cosmos is in encrypted and service personnel do not have access to decryption keys, the target log is programmatically passed through a decryption service that returns scoped results to the authorized service personnel. Any vulnerabilities found from this exercise are reported and escalated using Microsoft's standard security incident management channels.</span></span>
