---
title: 如何減少 Office 365 中的垃圾郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
description: 了解最常用來協助減少 Office 365 中垃圾郵件的方式。
ms.openlocfilehash: 59778f992ebc232ae31ebc9aaae4ca5333080698
ms.sourcegitcommit: 7023fd3c4d6088f82a5cd2fda241897a3a1c7f5c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2019
ms.locfileid: "29453689"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a>如何減少 Office 365 中的垃圾郵件

 **您在 Office 365 收到太多垃圾郵件嗎？請執行此動作。**
  
Office 365 中許多有關垃圾郵件的問題可以透過[檢視電子郵件標頭](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) (機器翻譯)，並判斷出了什麼差錯來解決。如果您看到名為 X-Forefront-Antispam-Report 的郵件標頭，其中包含 SFV:NSPM 字串，這表示 Exchange Online Protection (EOP) 已掃描郵件，而且未將它視為垃圾郵件。在此情況下，我們強烈建議您[使用回報郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) (機器翻譯) 來協助我們改進篩選器。如果您在標題中沒有看到此值，它可能表示郵件未通過垃圾郵件掃描，或設定出問題，導致忽略郵件。在此情況下，請參閱下列資訊。 
  
您可以深入了解[反垃圾郵件標頭](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx) (機器翻譯)。
  
## <a name="solutions-to-common-causes-of-getting-too-much-spam"></a>收到太多垃圾郵件的常見原因的解決方案

為了保護您免於收到太多垃圾郵件，Exchange Online Protection (EOP) 需要系統管理員完成一些工作。如果您不是 Office 365 租用戶的系統管理員，而且收到太多垃圾郵件，則您可能會想要與您的系統管理員合作處理這些工作。否則，您可以跳至使用者區段。
  
### <a name="for-admins"></a>若為系統管理員

- **將您的 DNS 記錄指向 Office 365** 為了讓 EOP 提供防護，所有網域的郵件交換程式 (MX) DNS 記錄都必須指向 Office 365，而且只能指向 Office 365。如果您的 [MX 未指向 Office 365](https://blogs.msdn.microsoft.com/tzink/2017/12/28/if-you-use-office-365-but-your-mx-record-doesnt-point-to-office-you-may-want-to-close-down-your-security-settings/) (英文)，則 EOP 不會為您的使用者提供垃圾郵件篩選功能。請參閱[當您管理 DNS 記錄時建立 Office 365 的 DNS 記錄](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23) (機器翻譯)。
    
- **啟用所有信箱上的垃圾郵件規則** 根據預設，垃圾郵件篩選動作會設為 [將郵件移至垃圾郵件資料夾]****。如果這是您目前喜好的垃圾郵件原則動作，則每個信箱[也須啟用垃圾郵件規則](https://blogs.msdn.microsoft.com/tzink/2017/12/14/making-sure-your-junk-email-filtering-is-enabled-in-office-365/) (英文)。若要進行此檢查，您可以對一或多個信箱執行 Get-MailboxJunkEmailConfiguration Cmdlet。例如，您可能會對所有信箱進行此檢查，方法為執行 Cmdlet：Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}
    
    檢視輸出時，Enable 屬性應該設為 True。若設為 false，您可以執行 Set-MailboxJunkEmailConfiguration，將它變更為 True。
    
- **檢查您的郵件流程規則與安全清單** 查看應該已標示為垃圾郵件之郵件的郵件標頭。在 X-Forefront-Antispam-Report 標頭中找出 SCL 屬性。如果 SCL 值為 -1，這表示郵件列為安全郵件，並略過 EOP 垃圾郵件篩選。請調查郵件流程規則、允許清單和收件者的允許寄件者清單。[以商務用 Office 365 系統管理員身分找出並修正電子郵件傳遞問題](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6) (機器翻譯) 也會有助於提供郵件收到的 SCL 為何是 -1 的詳細資訊。 
    
- **在內部部署 Exchange Server 中建立郵件流程規則** 如果您使用的是 Exchange Online Protection，但您的信箱位於內部部署 Exchange Server，則您需要在內部部署 Exchange Server 中建立幾個郵件流程規則。請參閱 [EOP 專屬的指示](https://technet.microsoft.com/library/ms.exch.eac.EditAntispamPolicy_SpamAction%28EXCHG.150%29.aspx?v=15.20.548.14&amp;l=1&amp;s=BPOS_S_E15_0) (英文)。
    
- **將大量電子郵件標示為垃圾郵件** 大量電子郵件是使用者可能已註冊，但仍有可能不想要的電子郵件。在郵件標頭中，於 X-Microsoft-Antispam 標頭中尋找 BCL (大量信賴等級) 屬性。如果 BCL 值小於垃圾郵件篩選器中設定的閾值，您可能想要調整閾值，而不是將這些類型的大宗郵件標示為垃圾郵件。不同的使用者對於[大量電子郵件的處理方式](https://blogs.msdn.microsoft.com/tzink/2014/08/25/different-levels-of-bulk-mail-filtering-in-office-365/) (英文) 各有不同的容錯和喜好設定。您可以針對不同的使用者喜好設定建立不同的原則或規則。 
    
- **立即封鎖寄件者** 在您需要立即封鎖寄件者的情況下，您可以依電子郵件地址、網域或 IP 位址進行封鎖。請參閱[利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件，以避免誤判問題](block-email-spam-to-prevent-false-negatives.md)。使用者允許清單中的項目可以覆寫系統管理員所設定的封鎖。
    
- **為使用者開啟回報郵件增益集** 我們建議建議您[為使用者啟用回報郵件增益集](enable-the-report-message-add-in.md)。身為系統管理員，您也可以檢視使用者傳送的意見反應，並使用任何模式，來調整任何可能造成問題的設定。
    
### <a name="for-users"></a>若為使用者

- **啟用垃圾郵件規則，並檢查您的允許清單** 檢查垃圾郵件動作規則是否已啟用，以及寄件者或寄件者的網域是否未設為要在您的個人允許清單中略過。存取這些設定的最佳方式來自[封鎖或允許 (垃圾郵件設定)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) (機器翻譯)。當您在那裡時，也可以選擇封鎖寄件者的電子郵件地址或網域。
    
- **向 Microsoft 報告垃圾郵件** 透過[使用回報郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) (機器翻譯)，向 Microsoft 報告垃圾郵件。此外，您可以將郵件傳送至 junk@office365.microsoft.com，並將一或多封郵件附加到報告。
    
    **重要** 如果您未以附件形式轉寄郵件，則[標頭將會遺失，而且我們將無法改善](https://blogs.msdn.microsoft.com/tzink/2017/11/30/when-creating-support-tickets-about-spam-be-sure-to-include-message-headers/) (英文) Office 365 中的垃圾郵件篩選功能。 
    
- **從大量電子郵件取消訂閱** 如果郵件是您已註冊的項目 (例如電子報、產品公告等)，而且其包含的連結來自聲譽卓著的來源，則您可能只想取消訂閱。Office 365 通常不會將這些郵件視為垃圾郵件。您也可以選擇封鎖寄件者，或要求系統管理員進行將導致所有大宗郵件被視為垃圾郵件的變更。 
    

