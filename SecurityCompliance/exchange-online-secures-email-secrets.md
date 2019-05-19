---
title: Exchange Online 如何保護您的電子郵件機密資料
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/24/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: 除了 Office 365 信任中心提供安全性、 隱私權和規範資訊的 Office 365，您可能想要知道 Office 365 如何協助保護您在其資料中心中提供的機密資料。 我們會使用稱為分散式金鑰管理員 (DKM) 的技術。
ms.openlocfilehash: 609d59b6e4da779e0fa663b40fdbf26036753669
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154585"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Exchange Online 如何保護您的電子郵件機密資料

本文說明 Microsoft 如何保護您的電子郵件機密資料，在其資料中心。
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>我們要如何保護您所提供的機密資料資訊？

除了 Office 365 信任中心提供[安全性、 隱私權和規範資訊的 Office 365](https://go.microsoft.com/fwlink/?linkid=874644)，您可能想要知道 Office 365 如何協助保護您在其資料中心中提供的機密資料。 我們會使用稱為分散式金鑰管理員 (DKM) 的技術。
  
分散式金鑰管理員 (DKM) 是使用一組秘密金鑰來加密及解密資訊用戶端功能。 只有在 Active Directory 網域服務中的特定安全性群組的成員可以存取這些機碼，以便解密由 DKM 加密的資料。 在 Exchange Online 中，只有在其下的 Exchange 處理程序執行特定服務帳戶屬於該 [安全性] 群組。 資料中心裡的標準作業程序的一部分，沒有人所指定屬於此安全性群組的認證，因此沒有 human 具有存取權才能解密這些機密的機碼。
  
偵錯、 疑難排解或稽核的用途，資料中心系統管理員必須要求提升權限的存取權的入侵屬於 [安全性] 群組的暫存認證。 此程序需要多個法律核准層級。 如果授與存取權，所有活動是記錄和稽核。 除了存取會只授與固定間隔的時間之後，它會自動到期。
  
額外的保護，DKM 技術包含自動化金鑰變換和封存。 這也可確保您可以繼續存取舊內容，而不需無限期依賴相同的金鑰。
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>在其中沒有 Exchange Online 進行地方使用 DKM？

Microsoft 會使用 DKM 加密您在 Exchange Online 資料中心中的機密資料。 例如：
  
- 已連線的帳戶的電子郵件帳戶認證。 已連線的帳戶是協力廠商的帳戶，例如 Hotmail、 Gmail 和 yahoo ！ 郵件帳號。
    
- 版權管理服務 (RMS) 根機碼。 以下是客戶金鑰是 [匯入從 Azure RMS 或客戶的內部部署 Active Directory 網域服務 RMS 部署所用的加密和解密電子郵件與 RMS 或 Office 365 郵件加密 (OME)。
    
## <a name="related-topics"></a>相關主題

[Office 365 中的加密](encryption.md)
  
[關於 Office 365 中加密的技術參考細節](technical-reference-details-about-encryption.md)
  
[服務保證在 Office 365 安全性&amp;合規性中心](https://go.microsoft.com/fwlink/?linkid=874645)
  

