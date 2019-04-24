---
title: Office 365 隔離和 Azure Active Directory 中的存取控制
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
description: 摘要： 如何在 Azure Active Directory 中工作的隔離與存取控制。
ms.openlocfilehash: bca7dc11bc3cc76e18972eb03761775da5f5cb41
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262651"
---
# <a name="isolation-and-access-control-in-azure-active-directory"></a><span data-ttu-id="57521-103">Azure Active Directory 中的隔離與存取控制</span><span class="sxs-lookup"><span data-stu-id="57521-103">Isolation and Access Control in Azure Active Directory</span></span>

<span data-ttu-id="57521-104">Azure Active Directory 的設計目的在於多個承租人裝載高度安全的方式透過邏輯資料隔離。</span><span class="sxs-lookup"><span data-stu-id="57521-104">Azure Active Directory was designed to host multiple tenants in a highly secure way through logical data isolation.</span></span> <span data-ttu-id="57521-105">Azure Active Directory 存取控制出入授權層。</span><span class="sxs-lookup"><span data-stu-id="57521-105">Access to Azure Active Directory is gated by an authorization layer.</span></span> <span data-ttu-id="57521-106">Azure Active Directory 隔離客戶與安全性界限以內使用租用戶容器，以保護客戶內容，以便無法存取或洩漏共同的租用戶內容。</span><span class="sxs-lookup"><span data-stu-id="57521-106">Azure Active Directory isolates customers using tenant containers as security boundaries to safeguard a customer's content so that the content cannot be accessed or compromised by co-tenants.</span></span> <span data-ttu-id="57521-107">由 Azure Active Directory 的授權層執行三個檢查：</span><span class="sxs-lookup"><span data-stu-id="57521-107">Three checks are performed by Azure Active Directory's authorization layer:</span></span>
- <span data-ttu-id="57521-108">存取 Azure Active Directory 租用戶啟用主體嗎？</span><span class="sxs-lookup"><span data-stu-id="57521-108">Is the principal enabled for access to Azure Active Directory tenant?</span></span>
- <span data-ttu-id="57521-109">主體已啟用此租用戶中資料的存取權嗎？</span><span class="sxs-lookup"><span data-stu-id="57521-109">Is the principal enabled for access to data in this tenant?</span></span>
- <span data-ttu-id="57521-110">授權類型的資料存取要求此租用戶中是主體角色？</span><span class="sxs-lookup"><span data-stu-id="57521-110">Is the principal's role in this tenant authorized for the type of data access requested?</span></span>

<span data-ttu-id="57521-111">無應用程式、 使用者、 伺服器或服務可以存取 Azure Active Directory，而不正確的驗證與 token 或憑證。</span><span class="sxs-lookup"><span data-stu-id="57521-111">No application, user, server, or service can access Azure Active Directory without the proper authentication and token or certificate.</span></span> <span data-ttu-id="57521-112">如果未伴隨適當的認證，會拒絕要求。</span><span class="sxs-lookup"><span data-stu-id="57521-112">Requests are rejected if they are not accompanied by proper credentials.</span></span>

<span data-ttu-id="57521-113">實際上，Azure Active Directory 裝載在自己受保護的容器，與原則和權限至及察覺擁有和管理租用戶容器內的每個租用戶。</span><span class="sxs-lookup"><span data-stu-id="57521-113">Effectively, Azure Active Directory hosts each tenant in its own protected container, with policies and permissions to and within the container solely owned and managed by the tenant.</span></span>
 
![Azure 容器](media/office-365-isolation-azure-container.png)

<span data-ttu-id="57521-115">租用戶容器的概念是深 ingrained 所有層級，一直到持續性儲存體的入口網站從目錄服務中。</span><span class="sxs-lookup"><span data-stu-id="57521-115">The concept of tenant containers is deeply ingrained in the directory service at all layers, from portals all the way to persistent storage.</span></span> <span data-ttu-id="57521-116">多個 Azure Active Directory 租用戶中繼資料儲存在同一個實體磁碟上，即使沒有之間關係以外的項目由目錄服務，這依照租用戶系統管理員所定義的容器。</span><span class="sxs-lookup"><span data-stu-id="57521-116">Even when multiple Azure Active Directory tenant metadata is stored on the same physical disk, there is no relationship between the containers other than what is defined by the directory service, which in turn is dictated by the tenant administrator.</span></span> <span data-ttu-id="57521-117">可以有無直接連線至 Azure Active Directory 存放區從任何要求的應用程式或服務，未經第一個經由授權層。</span><span class="sxs-lookup"><span data-stu-id="57521-117">There can be no direct connections to Azure Active Directory storage from any requesting application or service without first going through the authorization layer.</span></span>

<span data-ttu-id="57521-118">在下列範例中，Contoso 和 Fabrikam 都有個別的專用的容器，且即使這些容器可能會共用相同的基礎結構，例如伺服器和儲存體，部分他們保持分開及彼此隔離，然後閘藉由層級的授權和存取控制。</span><span class="sxs-lookup"><span data-stu-id="57521-118">In the example below, Contoso and Fabrikam both have separate, dedicated containers, and even though those containers may share some of the same underlying infrastructure, such as servers and storage, they remain separate and isolated from each other, and gated by layers of authorization and access control.</span></span>
 
![Azure 的專用的容器](media/office-365-isolation-azure-dedicated-containers.png)

<span data-ttu-id="57521-120">此外，有可以內執行，從 Azure Active Directory，沒有應用程式元件，而且您不能強制破壞另一個租用戶的完整性、 存取加密金鑰的另一個租用戶，或從伺服器讀取未經處理資料的一個租用戶。</span><span class="sxs-lookup"><span data-stu-id="57521-120">In addition, there are no application components that can execute from within Azure Active Directory, and it is not possible for one tenant to forcibly breach the integrity of another tenant, access encryption keys of another tenant, or read raw data from the server.</span></span>

<span data-ttu-id="57521-121">根據預設，Azure Active Directory 不允許在其他租用戶中的身分識別所發出的所有作業。</span><span class="sxs-lookup"><span data-stu-id="57521-121">By default, Azure Active Directory disallows all operations issued by identities in other tenants.</span></span> <span data-ttu-id="57521-122">每個承租人都是以邏輯方式隔離的 Azure Active Directory 內透過宣告型存取控制。</span><span class="sxs-lookup"><span data-stu-id="57521-122">Each tenant is logically isolated within Azure Active Directory through claims-based access controls.</span></span> <span data-ttu-id="57521-123">讀取和寫入的範圍限定為租用戶容器] 中，資料且閘由內部抽象層和角色型存取控制 (RBAC) 層，一起強制執行安全性界限為租用戶的目錄。</span><span class="sxs-lookup"><span data-stu-id="57521-123">Reads and writes of directory data are scoped to tenant containers, and gated by an internal abstraction layer and a role-based access control (RBAC) layer, which together enforce the tenant as the security boundary.</span></span> <span data-ttu-id="57521-124">每個目錄資料存取要求會處理這些層級，並在 Office 365 中的每個存取要求 policed 依上述的邏輯。</span><span class="sxs-lookup"><span data-stu-id="57521-124">Every directory data access request is processed by these layers and every access request in Office 365 is policed by the logic above.</span></span>

<span data-ttu-id="57521-125">Azure Active Directory 發生 「 北美地區 」、 US Government、 歐盟 （德國），及全球資訊網的分割區。</span><span class="sxs-lookup"><span data-stu-id="57521-125">Azure Active Directory has North America, U.S. Government, European Union, Germany, and World Wide partitions.</span></span> <span data-ttu-id="57521-126">租用戶存在於單一磁碟分割，並分割區可以包含多個承租人。</span><span class="sxs-lookup"><span data-stu-id="57521-126">A tenant exists in a single partition, and partitions can contain multiple tenants.</span></span> <span data-ttu-id="57521-127">磁碟分割的資訊是開使用者區隔。</span><span class="sxs-lookup"><span data-stu-id="57521-127">Partition information is abstracted away from users.</span></span> <span data-ttu-id="57521-128">指定的分割 （包括內的所有承租人） 會複寫到多個資料中心。</span><span class="sxs-lookup"><span data-stu-id="57521-128">A given partition (including all the tenants within it) is replicated to multiple datacenters.</span></span> <span data-ttu-id="57521-129">租用戶的磁碟分割會選擇根據租用戶 （例如，國家/地區碼） 的屬性。</span><span class="sxs-lookup"><span data-stu-id="57521-129">The partition for a tenant is chosen based on properties of the tenant (e.g., the country code).</span></span> <span data-ttu-id="57521-130">使用專用的金鑰加密機密資料和其他每個分割區中的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="57521-130">Secrets and other sensitive information in each partition is encrypted with a dedicated key.</span></span> <span data-ttu-id="57521-131">當您建立新的分割區時，會自動產生金鑰。</span><span class="sxs-lookup"><span data-stu-id="57521-131">The keys are generated automatically when a new partition is created.</span></span>

<span data-ttu-id="57521-132">Azure Active Directory 系統功能是以每個使用者工作階段的唯一執行個體。</span><span class="sxs-lookup"><span data-stu-id="57521-132">Azure Active Directory system functionalities are a unique instance to each user session.</span></span> <span data-ttu-id="57521-133">此外，Azure Active Directory 會使用加密技術來提供的共用的系統資源，以防止未經授權和非預期的資訊傳輸網路層級的隔離。</span><span class="sxs-lookup"><span data-stu-id="57521-133">In addition, Azure Active Directory uses encryption technologies to provide isolation of shared system resources at the network level to prevent unauthorized and unintended transfer of information.</span></span>
