---
title: 如何在 Office 365 中防止實際電子郵件被標示為垃圾郵件
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 34823bbc-a3e3-4949-ba42-97c73997eeed
description: 了解如何讓實際電子郵件不會成為垃圾郵件，以及在 Office 365 中避免被標示為垃圾郵件。
ms.openlocfilehash: d092dc0a1a222f51f48102eb8c07e8e6051aa1bd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526375"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a>如何在 Office 365 中防止實際電子郵件被標示為垃圾郵件

 **您的實際電子郵件將在 Office 365 中被標示為垃圾郵件嗎？請執行此動作。**
  
Exchange Online Protection (EOP) 會嘗試篩選掉垃圾郵件，讓您的收件匣沒有使用者不想看到的內容。但有時候，EOP 會篩選掉您想看到的內容。
  
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a>判斷郵件為何被標示為垃圾郵件的原因

Office 365 中許多有關垃圾郵件的問題可以透過[檢視電子郵件標頭](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) (機器翻譯)，並判斷出了什麼差錯來解決。如果您看到名為 X-Forefront-Antispam-Report 的郵件標頭，其中包含 SFV:NSPM 字串，這則表示 Exchange Online Protection (EOP) 已掃描郵件，並認為它是垃圾郵件。在此情況下，我們強烈建議您[使用回報郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) 來協助我們改進篩選器。如果您在標題中沒有看到此值，它可能表示郵件未通過垃圾郵件掃描，或設定出問題，導致郵件被錯誤地分類為垃圾郵件。您可以[深入了解反垃圾郵件標頭](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx) (機器翻譯)。
  
在標頭中，尋找下列標題和值。
  
### <a name="x-forefront-antispam-report"></a>X-Forefront-Antispam-Report

- **SFV:BLK** 表示郵件已標示為垃圾郵件，因為寄件地址是在收件者封鎖的寄件者清單上。 
    
- **SFV:SKS** 表示在篩選內容之前已將郵件標示為垃圾郵件。這可能包括將郵件標示為垃圾郵件的傳輸規則。執行郵件追蹤，來查看是否已觸發可能設定高垃圾郵件信賴等級 (SCL) 的傳輸規則。 
    
- **SFV:SKB** 表示郵件已標示為垃圾郵件，因為它符合垃圾郵件篩選原則中的封鎖清單。 
    
- **SFV:BULK** 表示位於 x-microsoft-antispam 的大量抱怨層級 (BCL) 值高於已對內容篩選器設定的大量閾值。大量電子郵件是使用者可能已註冊，但仍有可能不想要的電子郵件。在郵件標頭中，於 X-Microsoft-Antispam 標頭中尋找 BCL (大量信賴等級) 屬性。如果 BCL 值小於垃圾郵件篩選器中設定的閾值，您可能想要調整閾值，而不是將這些類型的大宗郵件標示為垃圾郵件。不同的使用者對於[大量電子郵件的處理方式](https://blogs.msdn.microsoft.com/tzink/2014/08/25/different-levels-of-bulk-mail-filtering-in-office-365/) (英文) 各有不同的容錯和喜好設定。您可以針對不同的使用者喜好設定建立不同的原則或規則。
    
- **CAT:SPOOF** 或 **CAT:PHISH** 表示郵件似乎是詐騙郵件，表示無法驗證郵件來源，且可能是可疑的郵件。如果有效，寄件者將需要確定它們具有適當的 SPF 及 DKIM 設定。如需詳細資訊，請檢查 Authentication-Results 標頭。雖然可能很難讓所有寄件者都使用適當的電子郵件驗證方法，但略過這些檢查可能風險極大，而且是造成危害的首要原因。 
    
### <a name="x-customspam"></a>x-customspam

- 若出現此標頭，表示郵件已標示為垃圾郵件，因為已在您的垃圾郵件篩選器中啟用其中一個[進階垃圾郵件選項](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx) (機器翻譯)。除非您需要這些功能，否則我們建議您使用預設設定。 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a>造成太多垃圾郵件之其他原因的解決方案

若要有效地運作，Exchange Online Protection (EOP) 需要系統管理員完成一些工作。如果您不是 Office 365 租用戶的系統管理員，而且收到太多垃圾郵件，則您可能會想要與您的系統管理員合作處理這些工作。否則，您可以跳至使用者區段。
  
### <a name="for-admins"></a>若為系統管理員

- **將您的 DNS 記錄指向 Office 365** 為了讓 EOP 提供防護，所有網域的郵件交換程式 (MX) DNS 記錄都必須指向 Office 365，而且只能指向 Office 365。如果您的 MX 未指向 Office 365，則 EOP 不會為您的使用者提供垃圾郵件篩選功能。在您想要使用其他服務或應用裝置，為您的網域提供垃圾郵件篩選功能的情況下，您應該考慮在 EOP 中停用垃圾郵件保護。做法為建立一個傳輸規則，將 SCL 值設為 -1。如果您稍後決定要使用 EOP，請務必移除此傳輸規則。 
    
- **停用 Outlook 中的 SmartScreen 篩選** 如果您的使用者是使用 Outlook 桌面用戶端，則他們應該停用已終止的 SmartScreen 篩選功能。如果執行已更新的桌面 Outlook 用戶端，應該不需要此功能。 
    
- **為使用者開啟回報郵件增益集** 我們建議建議您[為使用者啟用回報郵件增益集](enable-the-report-message-add-in.md)。身為系統管理員，您也可以檢視使用者傳送的意見反應，並使用任何模式，來調整任何可能造成問題的設定。
    
- **立即允許寄件者** 在您需要立即允許寄件者的情況下，我們強烈建議您**只允許特定寄件者的 IP 位址**。或者，您可以允許寄件者，並同時確定寄件者通過 SPF 或 DKIM 這類的驗證檢查，方法為建立一個傳輸規則，**同時**找出寄件者網域和成功的 Authentication-Results 標頭。 
    
### <a name="for-users"></a>若為使用者

- **向 Microsoft 報告垃圾郵件** 透過[使用回報郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) (機器翻譯)，向 Microsoft 報告垃圾郵件。此外，您可以將郵件傳送至 junk@office365.microsoft.com，並將一或多封郵件附加到報告。
    
    **重要** 如果您未以附件形式轉寄郵件，則[標頭將會遺失，而且我們將無法改善](https://blogs.msdn.microsoft.com/tzink/2017/11/30/when-creating-support-tickets-about-spam-be-sure-to-include-message-headers/) (英文) Office 365 中的垃圾郵件篩選功能。 
    
- **將寄件者新增至您的允許清單 - 但謹慎使用** 做為最後的手段，您可以[封鎖或允許 (垃圾郵件設定)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) (機器翻譯)。如果這麼做，您應該注意可能允許以網路釣魚為目標的嘗試進入收件匣。
    

