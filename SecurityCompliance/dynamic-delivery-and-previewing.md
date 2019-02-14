---
title: 動態傳遞和 Office 365 ATP 安全附件預覽
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: 當您設定好您 ATP 安全附件原則時，您選擇以避免郵件延遲，並啟用人員預覽會掃描附件的動態傳遞。
ms.openlocfilehash: ae027986cf5114bd024c679a59975d1e4be52d32
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995144"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>動態傳遞和 Office 365 ATP 安全附件預覽

**摘要**： 動態傳遞，則可以針對[ATP 安全附件](atp-safe-attachments.md)選取此選項。請閱讀本篇文章以深入了解動態傳遞，在[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)的附件預覽功能。

當[ATP 安全附件原則已設定](set-up-atp-safe-attachments-policies.md)為您的組織有數種選項如何處理電子郵件附件。包括**封鎖**、**取代**、 及**動態的傳遞**。依 ATP 安全附件的原則設定電子郵件收件者可能會遇到電子郵件傳遞的延遲次要時掃描其附件。若要避免郵件延遲回應，請選擇 [**動態傳遞**。
  
## <a name="how-dynamic-delivery-works"></a>動態傳遞的運作方式
  
動態傳遞給收件者與版面配置區的每個電子郵件附件形式傳送透過電子郵件訊息本文以不電子郵件延遲。掃描附件的複本，且為安全由[ATP 安全的附件](atp-safe-attachments.md)之前會維持版面配置區。 

- 清除 [每個附件時，它是可用來開啟或下載。 

- 如果設為惡意決定附件，它傳送至隔離某人在貴組織的安全性小組 （例如 Office 365 全域管理員或安全性管理員） 可以[管理 Office 365 中隔離的郵件](manage-quarantined-messages-and-files.md)。

大部分的 Pdf 和 Office 可以在安全模式中預覽文件時 ATP 掃描正在進行中。如果附件不相容的動態傳遞預覽程式，直到完成 ATP 安全附件掃描電子郵件收件者請參閱附件版面配置區。

> [!TIP]
> 如果您使用的行動裝置與 Pdf 不會呈現在第一次的動態傳遞預覽程式，請嘗試登入 Office 365 使用行動裝置瀏覽器。

具有動態傳遞人員可讀取及回應其電子郵件訊息向右離開時正在分析其附件。 

Office 365 資料所在的相同區域中放置 ATP 掃描取得安全的附件。多個資料中心地理位置的詳細資訊，請參閱[其中是位於資料？](https://products.office.com/where-is-your-data-located?geo=All) 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>當某人將轉送電子郵件的什麼包含附件？

假設組織會使用動態傳遞其[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)」 與某人接收電子郵件含有附件。現在假設該名人員將電子郵件轉寄給其他人。會發生什麼事？ATP 安全附件原則中是否包含其他收件者而定。
  
- 如果收件者使用動態的傳遞選項 ATP 安全附件原則所涵蓋、 收件者會看見版面配置區與能夠預覽相容的檔案。
    
- 如果收件者未涵蓋 ATP 安全附件原則，然後電子郵件和附件都會通過，而不掃描 ATP 安全附件或附件版面配置區。
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a>如何才能以動態傳遞給運作？

- 您的組織必須具有[Office 365 進階威脅保護](office-365-atp.md)
    
- 必須使用動態的傳遞選項 （請參閱[Set up Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)） ATP 安全附件定義原則
    
- Office 365 中必須主控貴組織的電子郵件
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a>是否有不提供動態傳遞案例吗？

以下是不會支援動態傳遞為特定案例。這些包括下列：
  
- 公用資料夾中的電子郵件
    
- 不會路由傳送然後回來成使用自訂規則的使用者信箱的電子郵件
    
- 不在主控信箱並將其他位置，包括封存資料夾 （自動或手動） 移動電子郵件
    
- 會刪除的電子郵件
    
- 處於錯誤狀態的使用者的信箱搜尋資料夾
    
- Exchange Online 系統管理員已啟用 Exclaimer 的環境。若要解決這個問題，請參閱[ATP 動態傳遞和 Exclaimer 可用時不會傳遞附件的郵件](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)

- 使用[安全/多用途網際網路郵件延伸標準 (S/MIME)](s-mime-for-message-signing-and-encryption.md)加密的郵件）

