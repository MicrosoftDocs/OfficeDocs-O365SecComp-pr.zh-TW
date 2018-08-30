---
title: Office 365 BitLocker 加密
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
description: 摘要： BitLocker 加密雲端中的資訊。
ms.openlocfilehash: 86c6bc9282d7c2b0a7d4e08d4636c8f9c2fa5db8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526769"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker 與 Distributed Key Manager (DKM) 的加密
Office 365 伺服器使用 BitLocker 加密包含在磁碟區層級的其餘部分的客戶資料磁碟機。BitLocker 加密是 Windows 內建的資料保護功能。BitLocker 是硬體的其中一個用來防範威脅以防有漏洞其他處理程序或可能導致某人取得實體磁碟包含客戶資料存取的控制項 （例如，存取控制或回收） 中的技術。在此例中 BitLocker 不資料竊取或洩露可能因遺失、 竊、 或不當解除委任電腦與磁碟。

BitLocker 一起部署與進階加密標準 (AES) 256 位元加密磁碟包含客戶資料在 Exchange Online、 SharePoint Online 和 Skype for Business。與完整大量加密金鑰 (FVEK)，這要加密以大量主索引鍵 (VMK)，接下來繫結至信任的平台模組 (TPM) 的伺服器中的加密磁碟的磁區。VMK 直接保護 FVEK 與因此保護 VMK 變成重要。下圖說明指定伺服器 （在此例中，使用 Exchange Online 伺服器） 的 BitLocker 金鑰保護鏈結的範例。

下表說明指定伺服器 （在此情況下，Exchange Online 伺服器） 的 BitLocker 金鑰保護鏈結。

| 金鑰保護裝置 | 精確度 | 如何產生？ | 其儲存？ | 保護 |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| AES 256 位元的外部索引鍵 | 每個伺服器 | BitLocker api （英文) | TPM 或秘密安全 | Lockbox / 存取控制 |
|  |  |  | 信箱伺服器登錄 | TPM 加密 |
| 48 位數數字的密碼 | 每部磁碟 | BitLocker api （英文) | Active Directory | Lockbox / 存取控制 |
| X.509 憑證做為資料復原代理程式 (DRA) 又稱為公用金鑰保護裝置 | 環境 (例如 Exchange Online multitenant) | Microsoft CA | 建立系統 | 沒有一位使用者具有完整密碼的私密金鑰。Password 是實體保護之下。 |


BitLocker 金鑰管理包括復原按鍵的可用來解除鎖定/復原加密的磁碟在 Office 365 資料中心內的管理。Office 365 儲存在安全共用，只能由個人篩選並核准之主要金鑰。機碼的認證會儲存在 （什麼我們呼叫"secret 存放區"），存取控制資料的安全存放庫需要提高權限與管理核准存取使用剛剛-時間存取權限提高工具高層級。

BitLocker 支援可分為兩種管理類別的機碼：
- BitLocker managed 鍵，這通常是短期和採用在伺服器上安裝作業系統執行個體的存留期或指定的磁碟。這些機碼的刪除和重設在伺服器重新安裝或磁碟格式設定。
- BitLocker 復原鍵，受管理的外部 BitLocker 但用於磁碟解密。BitLocker 會重新安裝作業系統，及加密的資料磁碟已經存在的案例使用復原機碼。復原機碼也可用來監視探查 Exchange 線上回應程式可能需要所在的受管理的可用性來解除鎖定磁碟。

BitLocker 受保護的磁碟區加密使用接著會使用大量主要金鑰加密的完整的磁碟區加密金鑰。BitLocker 會使用 FIPS 相容演算法來確保加密金鑰會永遠不儲存或傳送透過電線中清除。Office 365 實作的客戶資料-在-rest-保護不會從預設 BitLocker 實作以外。