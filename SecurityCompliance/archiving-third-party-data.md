---
title: 在 Office 365 中封存第三方資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 系統管理員可以將協力廠商資料從社交媒體平臺、立即訊息平臺, 以及檔共同作業平臺匯入 Office 365 組織中的信箱。 這可讓您在 Office 365 中封存 Facebook、Twitter 及其他協力廠商資料來源的資料。 然後, 您可以針對協力廠商資料使用和套用 Office 365 規範功能 (例如合法持有、eDiscovery、就地封存和保留原則)。
ms.openlocfilehash: 796ad0314374dca60d1ff5f6b9317be491b757a1
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014602"
---
# <a name="archive-third-party-data-in-office-365"></a><span data-ttu-id="814d1-105">在 Office 365 中封存第三方資料</span><span class="sxs-lookup"><span data-stu-id="814d1-105">Archive third-party data in Office 365</span></span>

<span data-ttu-id="814d1-106">Office 365 可讓系統管理員將協力廠商資料從社交媒體平臺、立即訊息平臺和檔共同作業平臺匯入和封存至 Office 365 組織中的信箱。</span><span class="sxs-lookup"><span data-stu-id="814d1-106">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization.</span></span> <span data-ttu-id="814d1-107">您可以匯入至 Office 365 的協力廠商資料來源範例包括下列服務:</span><span class="sxs-lookup"><span data-stu-id="814d1-107">Examples of third-party data sources that you can import to Office 365 include the following services:</span></span> 
  
- <span data-ttu-id="814d1-108">**社交**– Facebook、LinkedIn、Twitter 和 Yammer</span><span class="sxs-lookup"><span data-stu-id="814d1-108">**Social** – Facebook, LinkedIn, Twitter, and Yammer</span></span> 
    
- <span data-ttu-id="814d1-109">**立即訊息**– Yahoo Messenger、GoogleTalk 和 Cisco jabber)</span><span class="sxs-lookup"><span data-stu-id="814d1-109">**Instant messaging** – Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="814d1-110">**檔**共同作業– Box 和 DropBox</span><span class="sxs-lookup"><span data-stu-id="814d1-110">**Document collaboration** – Box and DropBox</span></span> 
    
- <span data-ttu-id="814d1-111">**垂直行業**–客戶關係管理 (例如 Salesforce 交談) 和金融服務 (例如 Bloomberg 和 Thomson Reuters)</span><span class="sxs-lookup"><span data-stu-id="814d1-111">**Vertical industries** – Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span> 
    
- <span data-ttu-id="814d1-112">**SMS/文字訊息**– BlackBerry</span><span class="sxs-lookup"><span data-stu-id="814d1-112">**SMS/text messaging** – BlackBerry</span></span> 
    
<span data-ttu-id="814d1-113">匯入協力廠商資料之後, 您可以將 Office 365 規範功能 (例如訴訟暫止、eDiscovery、就地封存、審核、監督和 Office 365 保留原則) 套用至此資料。</span><span class="sxs-lookup"><span data-stu-id="814d1-113">After third-party data is imported, you can apply Office 365 compliance features — such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Supervision, and Office 365 retention policies — to this data.</span></span> <span data-ttu-id="814d1-114">例如，當信箱置於訴訟暫止狀態時，協力廠商資料將會保留。</span><span class="sxs-lookup"><span data-stu-id="814d1-114">For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved.</span></span> <span data-ttu-id="814d1-115">您可以使用 Microsoft eDiscovery 工具來搜尋協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="814d1-115">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="814d1-116">或者，您可以將封存和保留原則套用至協力廠商資料，就像您可以對 Microsoft 資料進行的動作一樣。</span><span class="sxs-lookup"><span data-stu-id="814d1-116">Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="814d1-117">簡而言之, 封存 Office 365 中的協力廠商資料可協助您的組織符合政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="814d1-117">In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="814d1-118">有兩種方式可匯入和封存 Office 365 中的協力廠商資料:</span><span class="sxs-lookup"><span data-stu-id="814d1-118">There are two ways to import and archive third-party data in Office 365:</span></span>

- <span data-ttu-id="814d1-119">**使用安全性 & 合規性中心內的協力廠商資料連線器**–使用 Office 365 的安全性 & 規範中心提供的自訂資料連線器。</span><span class="sxs-lookup"><span data-stu-id="814d1-119">**Use a third-party data connector in the Security & Compliance Center** – Use a custom data connector that's available in the Security & Compliance Center in Office 365.</span></span> <span data-ttu-id="814d1-120">在您設定及設定連接器之後, 它會連線至協力廠商資料來源、將專案的內容轉換成電子郵件格式, 然後將該專案匯入至 Office 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="814d1-120">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Office 365.</span></span> <span data-ttu-id="814d1-121">此時, 您可以從 Facebook 商務頁面、公司 Twitter 帳戶、立即 Bloomberg 和 LinkedIn 中, 採用連接器來匯入和封存資料。</span><span class="sxs-lookup"><span data-stu-id="814d1-121">At this time, you can implement connectors to import and archive data from Facebook Business pages, corporate Twitter accounts, Instant Bloomberg, and LinkedIn.</span></span> <span data-ttu-id="814d1-122">如需設定連接器的逐步指示, 請參閱:</span><span class="sxs-lookup"><span data-stu-id="814d1-122">For the step-by-step instructions to set up a connector, see:</span></span>
   
   - <span data-ttu-id="814d1-123">**Facebook** –[在 Office 365 中使用範例連接器封存 Facebook 資料](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="814d1-123">**Facebook** – [Use a sample connector to archive Facebook data in Office 365](archive-facebook-data-with-sample-connector.md)</span></span>
  
   - <span data-ttu-id="814d1-124">**Twitter** –[使用範例連接器來封存 Office 365 中的 Twitter 資料](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="814d1-124">**Twitter** – [Use a sample connector to archive Twitter data in Office 365](archive-twitter-data-with-sample-connector.md)</span></span>
    
   - <span data-ttu-id="814d1-125">**LinkedIn** –[設定連接器以封存 Office 365 中的 LinkedIn 資料](archive-linkedin-data.md)</span><span class="sxs-lookup"><span data-stu-id="814d1-125">**LinkedIn** – [Set up a connector to archive LinkedIn data in Office 365](archive-linkedin-data.md)</span></span>

- <span data-ttu-id="814d1-126">**使用 microsoft 合作夥伴**-您的組織可與 microsoft 合作夥伴合作, 其中提供自訂連接器, 將設定為從協力廠商資料來源提取專案 (定期), 然後以協力廠商 API, 並將這些專案匯入至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="814d1-126">**Work with a Microsoft partner** – Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source (on a regular basis) and then connect to the Microsoft cloud by a third-party API and import those items to Office 365.</span></span> <span data-ttu-id="814d1-127">夥伴連接器也會將專案的內容從協力廠商資料來源轉換成電子郵件訊息, 然後將其匯入 Office 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="814d1-127">The partner connector also converts the content of an item from the third-party data source to an email message and then imports them to a mailbox in Office 365.</span></span> <span data-ttu-id="814d1-128">如需您可以使用的合作夥伴清單, 以及此方法的逐步程式, 請參閱[在 Office 365 中與合作夥伴一起封存協力廠商資料](work-with-partner-to-archive-third-party-data.md)。</span><span class="sxs-lookup"><span data-stu-id="814d1-128">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>