---
title: 使用 Office 365 ATP 安全附件的動態傳遞和預覽
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: 當您設定 ATP 安全附件原則時, 您可以選擇 [動態傳遞] 以避免郵件延遲, 並讓使用者預覽所掃描的附件。
ms.openlocfilehash: 5d04593dd0884b21deefc202485aee27f60d1a5f
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077829"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>使用 Office 365 ATP 安全附件的動態傳遞和預覽

## <a name="overview"></a>概觀

[動態傳遞] 是可為[ATP 安全附件](atp-safe-attachments.md)選取的選項。 請閱讀本文以瞭解[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)中的動態傳遞和附件預覽功能。

為您的組織[設定 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)時, 有數個選項可讓您處理電子郵件附件。 其中包括**區塊**、**取代**和**動態傳遞**。 根據如何設定 ATP 安全附件原則, 電子郵件收件者可能會在掃描附件時, 在電子郵件傳遞期間遇到輕微延遲。 若要避免郵件延遲, 請選擇 [**動態傳遞**]。
  
## <a name="how-dynamic-delivery-works"></a>動態傳遞的運作方式
  
動態傳遞會將電子郵件的本文與每個電子郵件附件的預留位置傳送給收件者, 以避免電子郵件延遲。 在掃描附件的複本之前, 會保留預留位置, 並將其判定為安全的[ATP 安全附件](atp-safe-attachments.md)。 

- 一旦清除每個附件, 就可以開啟或下載。 

- 如果將附件決定為惡意, 則會將其傳送至隔離區, 您組織的安全小組 (例如 Office 365 全域管理員或安全性系統管理員) 可以在[office 365 中管理隔離的郵件](manage-quarantined-messages-and-files.md)。

大部分的 Pdf 和 Office 檔都可以在安全模式中預覽, 同時進行 ATP 掃描。 如果附件與動態傳遞預覽程式不相容, 則電子郵件收件者會看到附件預留位置, 直到已完成 ATP 安全附件掃描。

> [!TIP]
> 如果您使用的是行動裝置, 且 Pdf 不是先在動態傳遞預覽程式中轉譯, 請嘗試使用行動裝置瀏覽器登入 Office 365。

透過動態傳遞, 使用者可以立即讀取和回復電子郵件, 同時也會分析其附件。 

ATP 安全附件掃描會在您的 Office 365 資料所在的同一個區域中進行。 如需資料中心地理位置的詳細資訊, 請參閱[您的資料位於何處？](https://products.office.com/where-is-your-data-located?geo=All) 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>當某人轉寄包含附件的電子郵件時會發生什麼事？

假設組織使用的是其[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)的動態傳遞, 而某人收到包含附件的電子郵件。 現在假設人員將電子郵件轉寄給其他人。 會發生什麼事？ 這取決於是否在 ATP 安全附件原則中包含其他收件者。
  
- 如果使用動態傳遞選項的 ATP 安全附件原則所涵蓋的收件者, 則收件者會看到該預留位置, 並具備預覽相容檔案的能力。
    
- 如果不是 ATP 安全附件原則所涵蓋的收件者, 則電子郵件和附件會經過, 不含任何 ATP 安全附件掃描或附件預留位置。
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a>進行動態傳遞所需的作業為何？

- 您的組織必須有[Office 365 高級威脅防護](office-365-atp.md)
    
- 您必須使用動態傳遞選項來定義 ATP 安全附件的原則 (請參閱[在 Office 365 中設定 Atp 安全附件原則](set-up-atp-safe-attachments-policies.md))
    
- 您組織的電子郵件必須主控于 Office 365。 雖然[office 365 的高級威脅防護可以搭配任何 SMTP 郵件傳輸代理程式使用](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp)(例如 Exchange Server), 但 ATP 安全附件的動態傳遞選項需要組織的電子郵件位於 Office 365。 如果您的電子郵件不是在 Office 365 中主控, 請選擇不同的[ATP 安全附件原則選項](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), 例如**區塊**。
    
## <a name="additional-considerations"></a>其他附註

在某些情況下, 不支援動態傳遞。 包括下列各項：
  
- 公用資料夾中的電子郵件
    
- 使用自訂規則, 然後再移至使用者信箱的電子郵件
    
- 移動 (自動或手動) 從裝載的信箱移至其他位置 (包括封存資料夾) 的電子郵件訊息
    
- 已刪除的電子郵件
    
- 處於錯誤狀態的使用者信箱搜尋資料夾
    
- Exchange Online 系統管理員已啟用 Exclaimer 的環境。 若要解決此問題, 請參閱[使用 ATP 動態傳遞和 Exclaimer 時, 不會傳遞含有附件的郵件](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)

- 使用[安全/多用途網際網路郵件延伸 (S/MIME)](s-mime-for-message-signing-and-encryption.md)加密的郵件

- 在不支援動態傳遞的情況下, ATP 安全附件將不會掃描電子郵件。 不過, 根據您的[ATP 安全連結原則](set-up-atp-safe-links-policies.md)的設定方式, 會檢查傳送包含 url 附件的電子郵件。 在這些情況下, 會檢查電子郵件訊息和 Office 檔案中的 Url。
