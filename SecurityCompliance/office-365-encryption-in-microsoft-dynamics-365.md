---
title: Microsoft Dynamics 365 中的 office 365 加密
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
description: 摘要： 了解 Microsoft Dynamics 365 中的加密。
ms.openlocfilehash: 7c2a352dd712b0db9d2ad623745f854b863dd2e0
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32265965"
---
# <a name="office-365-encryption-in-microsoft-dynamics-365"></a>Microsoft Dynamics 365 中的 office 365 加密

Microsoft 會使用加密技術來保護在 rest Microsoft 資料庫中，並在使用者裝置與我們的資料中心之間傳輸時的 Dynamics 365 中的客戶資料。 建立客戶與 Microsoft 資料中心之間的連線加密，並使用業界標準 TLS 保護所有的公開端點。 TLS 有效率地建立的安全性強化瀏覽器對伺服器連線以協助確保資料的機密性及桌上型電腦和資料中心之間的完整性。 啟用資料加密之後，它不能關閉。 如需詳細資訊，請參閱 <<c0>欄位層級資料加密。

Dynamics 365 會使用標準 Microsoft SQL Server 儲存格層級加密的一組預設實體屬性包含機密資訊，例如使用者名稱和電子郵件密碼。 這項功能可協助組織符合 FIPS 140-2 相關聯的符合性需求。 欄位層級資料加密是利用[Microsoft Dynamics CRM 電子郵件路由器](https://technet.microsoft.com/en-us/library/hh699800.aspx)，必須將儲存使用者名稱和密碼，以啟用的 Dynamics 365 執行個體與電子郵件服務之間的整合案例中尤其重要。 

Dynamics 365 的所有執行個體執行即時加密的資料寫入至磁碟 （靜態） 時使用[Microsoft SQL Server 透明資料加密](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017)（tde） >。 TDE 加密 SQL Server、 Azure SQL Database 和 Azure SQL 資料倉儲的資料檔案。 根據預設，Microsoft 儲存及管理資料庫加密金鑰的 Dynamics 365 您執行個體。 （由用於 Financials Dynamics 365 的機碼.NET Framework 資料保護 API 所產生）。 

Dynamics 365 系統管理中心中的 [管理] 機碼功能讓系統管理員能夠自行管理 Dynamics 365 執行個體相關聯的資料庫加密金鑰。 （自我管理的資料庫的加密金鑰只可在 Microsoft Dynamics 365 的 2017 年 1 月更新中，並可能不可供較新版本。 如需詳細資訊，請參閱 「[管理 Dynamics 365 （線上） 執行個體的加密金鑰](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)）。金鑰管理功能支援 PFX 和 BYOK 加密金鑰檔案，例如與儲存於 HSM。 （如需產生，並透過網際網路傳送 HSM 保護機碼的詳細資訊，請參閱[How to 產生，並且傳送 HSM 保護機碼的 Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys)）。 

若要使用的上傳加密金鑰] 選項，您需要兩個公用和私人加密金鑰。

金鑰管理功能使用 Azure Key Vault 安全地儲存加密金鑰會超出加密金鑰管理的複雜度。 Azure 金鑰保存庫可協助保護密碼編譯金鑰和雲端應用程式和服務所使用的密碼。 金鑰管理功能不需要您有 Azure Key Vault 訂閱，並在大部分情況下，則不需要存取儲藏室內所使用的 Dynamics 365 的加密金鑰。
