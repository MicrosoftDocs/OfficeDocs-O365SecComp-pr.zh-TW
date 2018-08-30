---
title: Microsoft Dynamics 365 中的 office 365 加密
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 5/31/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 了解 Microsoft Dynamics 365 中的加密。
ms.openlocfilehash: 181db1724f140c86fb1ac1dbf4a4bfb7063d25a3
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526153"
---
# <a name="office-365-encryption-in-microsoft-dynamics-365"></a>Microsoft Dynamics 365 中的 office 365 加密

Microsoft 會使用加密技術來保護 Dynamics 365 在 [在 Microsoft 資料庫，並為使用者裝置與我們的資料中心間傳輸時的其餘部分中的客戶資料。建立客戶與 Microsoft 資料中心之間的連線會加密，並使用業界標準 TLS 保護所有的公用端點。TLS 有效率地建立的安全性強化瀏覽器對伺服器連線以協助確保資料機密性和桌面和資料中心之間的完整性。資料加密啟動之後，它不能已關閉。如需詳細資訊，請參閱[欄位層級資料加密](https://msdn.microsoft.com/en-us/library/dn481562.aspx)。

Dynamics 365 會使用標準 Microsoft SQL Server 儲存格層級加密的一組包含機密資訊，例如使用者名稱和電子郵件密碼的預設實體屬性。此功能可協助組織符合法規需求 FIPS 140-2 相關聯。欄位層級資料加密則特別重要的運用[Microsoft Dynamics CRM 電子郵件路由器](https://technet.microsoft.com/en-us/library/hh699800.aspx)，這必須儲存使用者名稱與密碼來啟用 Dynamics 365 執行個體與電子郵件服務之間的整合案例中。 

所有執行個體 Dynamics 365 使用[Microsoft SQL Server 透明資料加密](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017)(TDE) 來執行即時資料時寫入至磁碟 （位於 rest) 加密。TDE 加密 SQL Server、 Azure SQL 資料庫和 Azure SQL 資料倉儲的資料檔案。根據預設，Microsoft 儲存及管理資料庫加密金鑰的 Dynamics 365 您執行個體。（如 Financials Dynamics 365 所使用的按鍵.NET Framework Data Protection API 所產生）。 

Dynamics 365 系統管理中心的管理機碼功能讓系統管理員能夠自行管理與 Dynamics 365 的執行個體相關聯的資料庫加密金鑰。（自我受管理的資料庫加密金鑰只可使用中 Microsoft Dynamics 365 2017 年 1 月更新且可能不可供更新版本。如需詳細資訊，請參閱 「[管理加密金鑰 Dynamics 365 （線上） 執行個體](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)）。金鑰管理功能可支援 PFX 和 BYOK 加密金鑰檔案，例如那些儲存在 HSM。（如需產生和透過網際網路傳送 HSM 受保護的機碼的詳細資訊，請參閱[如何產生及傳輸 HSM 保護 Azure 機碼存放庫的機碼](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys)）。 

若要使用加密金鑰上傳] 選項，您需要兩個公用及私人的加密金鑰。

金鑰管理功能便會使用 Azure 機碼存放庫來安全地儲存加密金鑰不在加密金鑰管理的複雜性。Azure 機碼存放庫可協助保護密碼編譯金鑰及雲端應用程式和服務所使用的機密資料。金鑰管理功能不需要有 Azure 機碼存放庫訂閱及大部分的情況下會有任何需要存取用於 Dynamics 365 存放庫中的加密金鑰。
