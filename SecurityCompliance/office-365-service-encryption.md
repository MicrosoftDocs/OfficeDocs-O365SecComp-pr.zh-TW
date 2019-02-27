---
title: Office 365 服務加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 了解 Microsoft Office 365 中的資料恢復能力。
ms.openlocfilehash: 385bb936de2c0cfcb478f0b20d2f7367d5b55ff4
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275693"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="55e75-103">Office 365 服務加密</span><span class="sxs-lookup"><span data-stu-id="55e75-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="55e75-p101">除了使用 Exchange Online 的磁碟區層級加密 Skype Business、 SharePoint Online 和 OneDrive for Business 也使用服務加密來加密的客戶資料。服務加密可讓兩個主要的管理選項：</span><span class="sxs-lookup"><span data-stu-id="55e75-p101">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data. Service Encryption allows for two key management options:</span></span>
- <span data-ttu-id="55e75-p102">Microsoft 管理所有的密碼編譯金鑰。（此選項是目前可用的 SharePoint Online、 OneDrive for Business 和 Skype for Business。它是目前在 Exchange Online 的發展藍圖）。</span><span class="sxs-lookup"><span data-stu-id="55e75-p102">Microsoft manages all cryptographic keys. (This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business. It is currently on the roadmap for Exchange Online.)</span></span>
- <span data-ttu-id="55e75-p103">客戶提供服務加密搭配使用的根機碼，以及客戶管理使用 Azure 金鑰儲藏室這些機碼。Microsoft 管理其他所有的按鍵。此選項會呼叫客戶機碼，以及目前可使用 Exchange Online、 SharePoint Online 和 OneDrive for Business。（先前稱為 BYOK 與進階加密。請參閱[Enhancing 透明度及控制項的 Office 365 客戶](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)原始宣告）。</span><span class="sxs-lookup"><span data-stu-id="55e75-p103">The customer supplies root keys used with service encryption and the customer manages these keys using Azure Key Vault. Microsoft manages all other keys. This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business. (Previously referred to as Advanced Encryption with BYOK. See [Enhancing transparency and control for Office 365 customers](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="55e75-p104">服務加密提供許多優點。例如，它：</span><span class="sxs-lookup"><span data-stu-id="55e75-p104">Service encryption provides multiple benefits. For example, it:</span></span>
- <span data-ttu-id="55e75-116">提供權限保護和一般管理功能上的強式加密保護功能。</span><span class="sxs-lookup"><span data-stu-id="55e75-116">provides rights protection and management features on top of strong encryption protection.</span></span>
- <span data-ttu-id="55e75-117">包含可讓多承租人服務來提供每個租用戶金鑰管理客戶機碼選項。</span><span class="sxs-lookup"><span data-stu-id="55e75-117">includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>
- <span data-ttu-id="55e75-118">提供區分 Windows 作業系統的系統管理員無法存取客戶資料儲存或處理的作業系統。</span><span class="sxs-lookup"><span data-stu-id="55e75-118">provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>
- <span data-ttu-id="55e75-119">增強了 Office 365 能夠符合有關加密規範需求的客戶的需求。</span><span class="sxs-lookup"><span data-stu-id="55e75-119">enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="55e75-120">客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="55e75-120">Customer Key</span></span>
<span data-ttu-id="55e75-p105">您可以使用客戶機碼，來產生自己使用內部部署 HSM 」 或 「 Azure 機碼存放庫的密碼編譯金鑰。不論如何產生金鑰客戶使用 Azure 機碼存放庫控制及管理 Office 365 所使用的密碼編譯機碼。一旦您機碼儲存在 Azure 機碼存放庫，他們可以指派給例如 Exchange Online 和 SharePoint Online 的工作量及作為用來加密您的信箱資料及檔案鑰匙的根目錄。其中一個使用客戶機碼的其他優點是，控制 Microsoft 能夠處理程序的客戶資料。這項功能有想要移除的資料從 Office 365 （例如客戶終止與 Microsoft 服務或時移除資料儲存在雲端中的一部分） 客戶可以這麼和使用客戶按鍵做技術的控制項確定無人包括 Microsoft、 可以存取或處理的資料。這是加入 （和互補） 客戶 Lockbox 功能 Microsoft 人員可用來控制客戶資料的存取權。</span><span class="sxs-lookup"><span data-stu-id="55e75-p105">Using Customer Key, you can generate your own cryptographic keys using either an on-premises HSM or Azure Key Vault. Regardless of how the key is generated, customers use Azure Key Vault to control and manage the cryptographic keys used by Office 365. Once your keys are stored in Azure Key Vault, they can be assigned to workloads such as Exchange Online and SharePoint Online and used to as the root of the keychain used to encrypt your mailbox data and files. One of the other benefits of using Customer Key is to control the ability of Microsoft to process customer data. This capability exists so that a customer that wants to remove data from Office 365 (such as when a customer terminates service with Microsoft or removes a portion of data stored in the cloud) can do so and use Customer Key as a technical control to ensure that no one, including Microsoft, can access or process the data. This is in addition (and a complement) to the Customer Lockbox feature that can be used to control access to customer data by Microsoft personnel.</span></span>

<span data-ttu-id="55e75-p106">若要了解如何設定 Office 365 的 Exchange Online 客戶機碼，Skype Business、 SharePoint Online 和 OneDrive for Business，請參閱[控制您使用客戶金鑰的 Office 365 中的資料](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697)。如需詳細資訊，請參閱[Office 365 常見問題集的客戶機碼](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6)，與[管理] 和 [控制項資料以有助於符合規範需求與客戶機碼](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580)。</span><span class="sxs-lookup"><span data-stu-id="55e75-p106">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business, see [Controlling your data in Office 365 using Customer Key](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697). For additional information, see the [Customer Key for Office 365 FAQ](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6), and [Manage and control your data to help meet compliance needs with Customer Key](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580).</span></span>
