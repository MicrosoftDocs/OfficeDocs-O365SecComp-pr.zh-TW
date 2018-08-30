---
title: Exchange Online 如何保護您的電子郵件機密資料
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/24/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
description: Office 365 信任中心提供 Office 365 的安全性、 隱私與規範資訊，以及可能會想要知道 Office 365 如何協助保護您提供其資料中心中的機密資料。我們使用稱為分散式金鑰管理員 (DKM) 的技術。
ms.openlocfilehash: a8fe1a2c9393958a391ec69a9a476a06de8c7576
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527277"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Exchange Online 如何保護您的電子郵件機密資料

本文說明 Microsoft 如何在其資料中心保護您的電子郵件機密資料。
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>我們如何保護您所提供的機密資料資訊？

Office 365 信任中心提供[安全性、 隱私與 Office 365 規範資訊](https://go.microsoft.com/fwlink/?linkid=874644)，以及可能會想要知道 Office 365 如何協助保護您提供其資料中心中的機密資料。我們使用稱為分散式金鑰管理員 (DKM) 的技術。
  
分散式金鑰管理員 (DKM) 是用戶端功能，使用一組秘密金鑰來加密及解密功能。只有在 Active Directory 網域服務中特定安全性群組的成員可以存取這些金鑰以解密 DKM 加密的資料。在 Exchange Online 中，只有 Exchange 處理程序執行的特定服務帳戶屬於該安全性群組。在資料中心的標準作業程序的一部分，是不會將屬於此安全性群組的認證給予任何使用者，因此沒有人具有可以解密這些機密資料之金鑰的存取權。
  
對於偵錯、疑難排解或稽核目的，資料中心系統管理員必須要求較高的權限以取得屬於安全性群組的暫時認證。此程序需要多個層級的法律核准。如果授與存取權時，所有活動會記錄和稽核。此外，存取權只會授與一段時間，在那之後自動到期。
  
對於額外保護，DKM 技術包含自動化金鑰變換和封存。這也確保您可以繼續存取舊的內容，而不需無限期地使用相同的金鑰。

  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Exchange Online 在哪些地方使用 DKM？

Microsoft 會使用 DKM 加密您的 Exchange Online 資料中心的機密資料。例如：
  
- 連線帳戶的電子郵件帳戶認證。連線的帳戶是協力廠商帳戶，例如 Hotmail、Gmail 和 Yahoo! 郵件帳戶。
    
- 版權管理服務 (RMS) 根機碼。這些是客戶機碼的其中一個匯入從 Azure RMS 或客戶的內部部署 Active Directory 網域服務 RMS 部署所用的加密與解密電子郵件與 RMS 或 Office 365 郵件加密 (OME)。
    
## <a name="related-topics"></a>相關主題

[Office 365 中的加密](encryption.md)
  
[關於 Office 365 中加密的技術參考細節](technical-reference-details-about-encryption.md)
  
[服務 Office 365 安全性保證&amp;規範中心](https://go.microsoft.com/fwlink/?linkid=874645)
  

