---
title: 在 Azure 中的 office 365 加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 摘要： 在 Azure 中加密的說明。
ms.openlocfilehash: 4d6d898ecd711f09519ca53eaebb8c345f443488
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276253"
---
# <a name="office-365-encryption-in-azure"></a>在 Azure 中的 office 365 加密

## <a name="introduction"></a>簡介
在 Azure，以保護措施等加密的通訊和操作的程序，協助保護資料安全。您也可以實作其他加密功能和管理自己的密碼編譯金鑰的彈性。不論客戶設定 Microsoft 適用於保護在 Azure 中的客戶資料的加密。Microsoft 也可讓您控制您透過某個範圍的進階技術來加密、 控制及管理密碼編譯金鑰架設在 Azure 中的資料控制項及稽核資料的存取權。此外，Azure 存放區提供一組完整的安全性功能一起啟用 [開發人員建置安全的應用程式。

Azure 提供資料保護為從某個位置移至另一個許多機制。Microsoft 使用 TLS 來保護資料安全性時它出差雲端服務與客戶之間。Microsoft 的資料中心會交涉 TLS 連線與用戶端連線至 Azure 服務的系統。完整轉寄密碼 (PFS) 會由專用鍵保護客戶的用戶端系統和 Microsoft 雲端服務之間的連線。連線也會使用 RSA 型為 2048 位元加密金鑰長度。此組合可讓很難某人截距和存取已傳送過程中的資料。

可以使用[用戶端加密](https://docs.microsoft.com/azure/storage/storage-client-side-encryption)、 HTTPS 或 SMB 3.0 應用程式與 Azure 之間傳輸保護資料。您可以自行虛擬機器 (Vm) 與您的使用者之間啟用加密的流量。搭配[Azure 虛擬網路](https://azure.microsoft.com/services/virtual-network/)，您可以使用的業界標準 IPsec 通訊協定來加密之間您公司的 VPN 閘道和 Azure 也例如在 Vm 位於虛擬網路之間的流量。

靜態資料，Azure 會提供許多加密選項，例如支援 AES 256，讓您選擇最符合您需求的資料儲存區案例的彈性。資料可以自動加密時寫入使用[Storage Service 加密](https://docs.microsoft.com/azure/storage/storage-service-encryption)的 Azure 儲存及作業系統和 Vm 所使用的資料磁碟可以加密[Azure 磁碟加密](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)。此外，在 Azure 存放區中的資料物件的委派的存取可授與使用[共用存取簽章](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1)。Azure 也會提供使用[透明資料加密的 Azure SQL 資料庫和資料倉儲](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)的靜態資料的加密。

如需在 Azure 中加密的詳細資訊，請參閱[Azure 加密概觀](https://docs.microsoft.com/azure/security/security-azure-encryption-overview)及[Azure 資料加密位在-其餘部分](https://docs.microsoft.com/azure/security/azure-security-encryption-atrest)。

## <a name="azure-disk-encryption"></a>Azure 磁碟加密
[Azure 磁碟加密](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)可讓您在加密您的 Windows 和 Linux 基礎架構以服務 (IaaS) 虛擬機器的磁碟。Azure 磁碟加密如何運用 BitLocker 功能的 Windows 和 Linux 提供作業系統與資料磁碟區層級加密性資料採擷窖功能。它也可確保在虛擬機器的磁碟上的所有資料會都加密在 Azure 的存放裝置中的其餘部分。Azure 磁碟加密整合可協助您控制、 管理及稽核使用加密金鑰及機密資料 Azure 機碼存放庫。

如需詳細資訊，請參閱[Azure 磁碟加密的 Windows 和 Linux IaaS Vm](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)。

## <a name="azure-storage-service-encryption"></a>Azure Storage Service 加密
與[Azure Storage Service 加密](https://docs.microsoft.com/azure/storage/storage-service-encryption)、 Azure 儲存自動加密資料之前先保存它以儲存空間及解密前擷取資料。加密、 解密和金鑰管理程序是完全透明的使用者。Azure Storage Service 加密可以用於[Azure Blob 儲存](https://azure.microsoft.com/services/storage/blobs/)與[Azure 檔案](https://azure.microsoft.com/services/storage/files/)。您也可以使用 Microsoft 管理加密金鑰與 Azure Storage Service 加密，或您可以使用自己的加密金鑰。（如需使用您自己的機碼，請參閱[Storage Service 加密使用客戶管理 Azure 機碼存放庫中的機碼](https://docs.microsoft.com/azure/storage/common/storage-service-encryption-customer-managed-keys)。如需使用 Microsoft managed 金鑰的資訊，請參閱[儲存為靜態資料的服務加密](https://docs.microsoft.com/azure/storage/storage-service-encryption)）。此外，您可以自動化使用加密。例如，以程式設計方式啟用或停用上使用[Azure 儲存資源提供者 REST API](https://msdn.microsoft.com/library/azure/mt163683.aspx)、[儲存資源提供者用戶端程式庫的.NET](https://msdn.microsoft.com/library/azure/mt131037.aspx)、 [PowerShell 的 windows Azure](https://docs.microsoft.com/powershell/azureps-cmdlets-docs)中的儲存空間帳戶的 Storage Service 加密或[Azure CLI](https://docs.microsoft.com/azure/storage/storage-azure-cli)中。

某些 Office 365 服務使用 Azure 儲存的資料。例如，SharePoint Online 和 OneDrive for Business 資料儲存在 Azure Blob 存放區並的 Microsoft 小組將資料儲存其聊天服務的資料表、，blob 及佇列。此外，服務信任入口網站的規範管理員功能儲存會儲存在[Azure 宇宙 DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)的平台服務 (PaaS) 全域分散式、 多模型資料庫中的加密表單中的客戶輸入資料。Azure Storage Service 加密加密資料儲存在 Azure Blob 存放區和表格，並 Azure 磁碟加密加密佇列，以及提供作業系統的磁碟區加密的 Windows 和 IaaS 虛擬機器磁碟及資料磁碟中的資料。解決方案可確保在虛擬機器的磁碟上的所有資料會都加密在 Azure 的存放裝置中的其餘部分。使用數種安全性技術，包括安全的主要儲存系統、 加密的網路及密碼編譯 Api 實作的[靜態 Azure 宇宙 DB 中的加密](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)。

## <a name="azure-key-vault"></a>Azure 金鑰保存庫
安全的金鑰管理未加密的最佳作法，以只核心它也是在雲端中的資料保護。[Azure 機碼存放庫](https://docs.microsoft.com/azure/key-vault/key-vault-whatis)可讓您加密金鑰及小型機密資料像使用硬體安全性模組 (Hsm) 中儲存的金鑰的密碼。Azure 機碼存放庫是 Microsoft 的建議的解決方案管理及控制存取權雲端服務所使用的加密金鑰。服務或使用 Azure Active Directory 帳戶的使用者可以指派權限來存取索引鍵。Azure 機碼存放庫減輕組織之設定、 修補程式、 及維護 Hsm 和金鑰管理軟體需求。使用 Azure 機碼存放庫，Microsoft 永遠不會看到您的機碼和應用程式沒有直接存取權，您持續控制。您也可以匯入或產生金鑰的 Hsm。 有包含 Azure 資訊保護訂閱的組織可以設定以使用客戶 managed 金鑰[將您自己的金鑰](https://docs.microsoft.com/information-protection/plan-design/byok-price-restrictions)(BYOK) 及其 Azure 資訊保護租用戶) 和[記錄使用方式](https://docs.microsoft.com/information-protection/deploy-use/log-analyze-usage)。
