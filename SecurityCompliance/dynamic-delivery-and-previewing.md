---
title: 動態傳遞和預覽與 Office 365 ATP 安全附件
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 04/19/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: 當您設定 ATP 安全附件原則時，您可以選擇以避免郵件延遲，並讓使用者在預覽所掃描的附件動態傳遞。
ms.openlocfilehash: 567b5f0c5bc75123169073bf5dc33de191187846
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958564"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>動態傳遞和預覽與 Office 365 ATP 安全附件

## <a name="overview"></a>概觀

動態傳遞是可選取用於[ATP 安全附件](atp-safe-attachments.md)的選項。 閱讀本篇文章以了解動態傳遞和在[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)的附件預覽功能。

當[ATP 安全附件原則設定](set-up-atp-safe-attachments-policies.md)為您的組織，提供了幾種方式處理電子郵件附件。 這些包括**封鎖**、**取代**和**動態傳遞**。 根據 ATP 安全附件原則設定的方式，雖然其附件掃描電子郵件收件者時，可能會遇到次要電子郵件傳遞延遲。 若要避免郵件延遲，選擇 [**動態傳遞**]。
  
## <a name="how-dynamic-delivery-works"></a>動態傳遞的運作方式
  
動態傳遞會透過電子郵件延遲藉由將透過電子郵件訊息的本文傳送給收件者的每個電子郵件附件的預留位置。 一份附件會掃描，並為安全取決於[ATP 安全附件](atp-safe-attachments.md)之前，仍會保留版面配置區。 

- 清除 [每個附件時，它是可用來開啟或下載。 

- 如果判斷附件為惡意，就會傳送至隔離區，某人在貴組織的安全性小組 （例如 Office 365 全域系統管理員或安全性系統管理員） 可以[管理 Office 365 中的隔離的郵件](manage-quarantined-messages-and-files.md)。

大部分的 Pdf 和 Office ATP 掃描正在進行中時，可以在安全模式中預覽文件。 如果附件不相容於動態傳遞預覽程式，電子郵件收件者會看到附件版面配置區，直到 ATP 安全附件掃描已完成。

> [!TIP]
> 如果您使用的行動裝置，並且 Pdf 無法呈現在第一次的動態傳遞預覽程式，請嘗試登入 Office 365 中，使用您行動裝置瀏覽器。

動態傳遞的人員可以閱讀和回覆其電子郵件立即時正在分析其附件。 

ATP 安全附件掃描採取放在您的 Office 365 資料所在的相同區域中。 如需有關資料中心地理位置的詳細資訊，請參閱 <<c0>其中是位於您資料？ 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>當有人轉寄電子郵件，會發生什麼事包含附件？

假設組織會使用動態傳遞其[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)中，而人員會收到包含附件的電子郵件。 現在假設該人員將電子郵件轉寄給其他人。 會發生什麼事？ 這取決於是否 ATP 安全附件原則中隨附的其他收件者。
  
- 如果收件者使用 [動態傳遞] 選項的 ATP 安全附件原則所涵蓋，收件者會看到版面配置區，來預覽相容檔案的能力。
    
- 如果收件者未涵蓋的 ATP 安全附件原則，然後電子郵件和附件就會通過經歷，而不需要任何 ATP 安全附件掃描或附件版面配置區。
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a>項目具有所需的動態傳遞至運作？

- 您的組織必須有[Office 365 進階威脅防護](office-365-atp.md)
    
- 您必須定義使用動態傳遞選項 （請參閱 < <b0>Set up Office 365 中的 ATP 安全附件原則</b0>） 的 ATP 安全附件原則
    
- 貴組織的電子郵件必須裝載於 Office 365。 雖然[Office 365 進階威脅防護可以搭配任何 SMTP 郵件傳輸代理程式](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp)（例如 Exchange Server)、 動態傳遞選項 ATP 安全附件會需要您組織的電子郵件裝載於 Office 365。 如果您的電子郵件不架設在 Office 365 中，選擇不同的[ATP 安全附件原則] 選項](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options)，例如**區塊**。
    
## <a name="additional-considerations"></a>其他附註

有不支援動態傳遞是特定案例。 包括下列各項：
  
- 公用資料夾中的電子郵件
    
- 且不會路由傳送的電子郵件，再重新到使用者的信箱使用自訂規則
    
- 是 （自動或手動） 遭到託管信箱將及移到其他位置，包括封存資料夾的電子郵件
    
- 會刪除的電子郵件
    
- 處於錯誤狀態的使用者的信箱搜尋資料夾
    
- 採用 Exchange Online 的系統管理員已啟用 Exclaimer 的環境。 若要解決此問題，請參閱[時所使用 ATP 動態傳遞和 Exclaimer 含附件的郵件未傳送](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)

- 使用[安全/多用途網際網路郵件延伸 (S/MIME)](s-mime-for-message-signing-and-encryption.md)加密的郵件）

- 在動態傳遞不受支援所在的情況下，ATP 安全附件會掃描電子郵件訊息。 不過，傳遞電子郵件訊息附件包含 Url 就會檢查，根據您的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)設定的方式。 在這些情況下，就會檢查電子郵件和 Office 檔案中的 Url。
