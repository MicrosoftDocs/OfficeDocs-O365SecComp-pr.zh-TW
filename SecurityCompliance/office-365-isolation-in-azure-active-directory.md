---
title: Office 365 隔離與 Azure Active Directory 中的存取控制
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
description: 摘要： 隔離及存取控制 Azure Active Directory 中的運作方式。
ms.openlocfilehash: db4fa0d026c6c608f09252c65bf1e0de5354f68c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527281"
---
# <a name="isolation-and-access-control-in-azure-active-directory"></a><span data-ttu-id="8dbab-103">Azure Active Directory 中的隔離與存取控制</span><span class="sxs-lookup"><span data-stu-id="8dbab-103">Isolation and Access Control in Azure Active Directory</span></span>

<span data-ttu-id="8dbab-p101">Azure Active Directory 的設計目的在於裝載多個承租人透過邏輯資料隔離的高度安全方式。Azure Active directory 的存取控制出入由授權層。Azure Active Directory 隔離客戶使用租用戶容器做為安全性限制可保護客戶的內容以便無法存取或由共同撰寫的租用戶危害內容。三個檢查是由 Azure Active Directory 的授權層執行：</span><span class="sxs-lookup"><span data-stu-id="8dbab-p101">Azure Active Directory was designed to host multiple tenants in a highly secure way through logical data isolation. Access to Azure Active Directory is gated by an authorization layer. Azure Active Directory isolates customers using tenant containers as security boundaries to safeguard a customer's content so that the content cannot be accessed or compromised by co-tenants. Three checks are performed by Azure Active Directory's authorization layer:</span></span>
- <span data-ttu-id="8dbab-108">已啟用的存取權 Azure Active Directory 租用戶的主體</span><span class="sxs-lookup"><span data-stu-id="8dbab-108">Is the principal enabled for access to Azure Active Directory tenant?</span></span>
- <span data-ttu-id="8dbab-109">已啟用此租用戶中資料的存取權的主體</span><span class="sxs-lookup"><span data-stu-id="8dbab-109">Is the principal enabled for access to data in this tenant?</span></span>
- <span data-ttu-id="8dbab-110">授權類型的資料存取權要求此租用戶中功能的主體角色</span><span class="sxs-lookup"><span data-stu-id="8dbab-110">Is the principal's role in this tenant authorized for the type of data access requested?</span></span>

<span data-ttu-id="8dbab-p102">沒有應用程式、 使用者、 伺服器或服務可以存取 Azure Active Directory 而不正確的驗證與 token 或憑證。如果未伴隨適當的認證會拒絕要求。</span><span class="sxs-lookup"><span data-stu-id="8dbab-p102">No application, user, server, or service can access Azure Active Directory without the proper authentication and token or certificate. Requests are rejected if they are not accompanied by proper credentials.</span></span>

<span data-ttu-id="8dbab-113">實際上，Azure Active Directory 架設在自己受保護的容器、 原則與權限至] 和 [察覺擁有和管理承租人容器內的每個租用戶。</span><span class="sxs-lookup"><span data-stu-id="8dbab-113">Effectively, Azure Active Directory hosts each tenant in its own protected container, with policies and permissions to and within the container solely owned and managed by the tenant.</span></span>
 
![Azure 容器](media/office-365-isolation-azure-container.png)

<span data-ttu-id="8dbab-p103">租用戶容器的概念是深 ingrained 到持續性儲存空間的入口網站中的所有層級的目錄服務中。即使在多個 Azure Active Directory 租用戶中繼資料儲存在同一個實體磁碟上，則沒有任何關係儲存之間以外的項目定義目錄服務，接著會使用租用戶系統管理員指定容器上。可以沒有直接連線至 Azure Active Directory 存放區從任何要求的應用程式或不含第一個經由授權圖層的服務。</span><span class="sxs-lookup"><span data-stu-id="8dbab-p103">The concept of tenant containers is deeply ingrained in the directory service at all layers, from portals all the way to persistent storage. Even when multiple Azure Active Directory tenant metadata is stored on the same physical disk, there is no relationship between the containers other than what is defined by the directory service, which in turn is dictated by the tenant administrator. There can be no direct connections to Azure Active Directory storage from any requesting application or service without first going through the authorization layer.</span></span>

<span data-ttu-id="8dbab-118">在下列範例中，Contoso 及 Fabrikam 會有不同、 專用的容器，即使這些容器可能會共用相同的基礎結構、 伺服器及儲存等的一些及其和保持分開及之外的其他每，來控制出入授權及存取控制的層級。</span><span class="sxs-lookup"><span data-stu-id="8dbab-118">In the example below, Contoso and Fabrikam both have separate, dedicated containers, and even though those containers may share some of the same underlying infrastructure, such as servers and storage, they remain separate and isolated from each other, and gated by layers of authorization and access control.</span></span>
 
![Azure 專用的容器](media/office-365-isolation-azure-dedicated-containers.png)

<span data-ttu-id="8dbab-120">此外，有可從執行 Azure Active Directory 中沒有應用程式元件並不是可能的一個承租人收回破壞另一個承租人的完整性、 存取另一個承租人的加密金鑰或讀取伺服器的原始資料。</span><span class="sxs-lookup"><span data-stu-id="8dbab-120">In addition, there are no application components that can execute from within Azure Active Directory, and it is not possible for one tenant to forcibly breach the integrity of another tenant, access encryption keys of another tenant, or read raw data from the server.</span></span>

<span data-ttu-id="8dbab-p104">根據預設，Azure Active Directory 不允許其他租用戶的身分識別所發出的所有作業。每個租用戶是以邏輯方式隔離 Azure Active Directory 中透過宣告式存取控制項。讀取和寫入的目錄資料的範圍設為承租人容器和閘內部抽象層和角色型存取控制 (RBAC) 圖層，一起強制執行安全性界限為承租人。每個目錄資料存取要求處理依下列層級與 Office 365 中的每個存取要求 policed 由上述的邏輯。</span><span class="sxs-lookup"><span data-stu-id="8dbab-p104">By default, Azure Active Directory disallows all operations issued by identities in other tenants. Each tenant is logically isolated within Azure Active Directory through claims-based access controls. Reads and writes of directory data are scoped to tenant containers, and gated by an internal abstraction layer and a role-based access control (RBAC) layer, which together enforce the tenant as the security boundary. Every directory data access request is processed by these layers and every access request in Office 365 is policed by the logic above.</span></span>

<span data-ttu-id="8dbab-p105">Azure Active Directory 具有 「 北美地區 」、 美國政府、 歐盟、 德國及全球資訊網的分割區。租用戶存在於單一磁碟分割，並分割區可包含多個承租人。分割區資訊是從使用者區隔。指定的分割 （包括內的所有租用戶） 會複寫到多個資料中心。租用戶的磁碟分割選擇根據租用戶 （例如國家/地區碼） 的屬性。使用專用的金鑰加密機密資料和其他每個分割區中的敏感資訊。機碼建立新的分割區時自動產生。</span><span class="sxs-lookup"><span data-stu-id="8dbab-p105">Azure Active Directory has North America, U.S. Government, European Union, Germany, and World Wide partitions. A tenant exists in a single partition, and partitions can contain multiple tenants. Partition information is abstracted away from users. A given partition (including all the tenants within it) is replicated to multiple datacenters. The partition for a tenant is chosen based on properties of the tenant (e.g., the country code). Secrets and other sensitive information in each partition is encrypted with a dedicated key. The keys are generated automatically when a new partition is created.</span></span>

<span data-ttu-id="8dbab-p106">Azure Active Directory 系統功能是每個使用者工作階段的唯一執行個體。此外，Azure Active Directory 會使用加密技術提供共用的系統資源以避免未獲授權和不慎傳輸資訊的網路層級的隔離。</span><span class="sxs-lookup"><span data-stu-id="8dbab-p106">Azure Active Directory system functionalities are a unique instance to each user session. In addition, Azure Active Directory uses encryption technologies to provide isolation of shared system resources at the network level to prevent unauthorized and unintended transfer of information.</span></span>
