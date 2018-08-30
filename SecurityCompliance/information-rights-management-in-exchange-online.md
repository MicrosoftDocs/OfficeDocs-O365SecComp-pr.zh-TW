---
title: Exchange Online 的資訊版權管理
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
description: 人員通常會使用電子郵件來交換機密資訊，例如財務資料、法律合約、機密產品資訊、銷售報告和預測、病患健康資訊，或是客戶和員工資訊。因此，信箱可能會成為大量潛在機密資訊的存放庫，而且資訊外洩可能會變成組織的嚴重威脅。
ms.openlocfilehash: 5036fe359215de1c2674d7efabbb283c78418a19
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002560"
---
# <a name="information-rights-management-in-exchange-online"></a>Exchange Online 的資訊版權管理

人員通常會使用電子郵件來交換機密資訊，例如財務資料、法律合約、機密產品資訊、銷售報告和預測、病患健康資訊，或是客戶和員工資訊。因此，信箱可能會成為大量潛在機密資訊的存放庫，而且資訊外洩可能會變成組織的嚴重威脅。
  
若要協助防止資訊外洩，Exchange Online 包括資訊版權管理 (IRM) 功能所提供的電子郵件訊息與附件的線上及離線保護。IRM 保護可以套用在 Microsoft Outlook 或 Outlook web 上的使用者，以及它可由系統管理員使用傳輸保護規則或 Outlook 保護規則套用。IRM 可協助您及您的使用者控制項可以存取、 轉寄、 列印或複製電子郵件中的機密資料。
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>IRM 與 Office 365 郵件加密 (OME) 和 Azure Active Directory 的運作方式的變更

年 9 月 2017，當您設定新的 Office 365 郵件加密功能您的組織，您也設定 IRM 搭配 Azure 版權管理 (Azure RMS)。您無法再設定以 Azure RMS 的 IRM 分開。而是 OME 與版權管理可以順暢地搭配使用。如需詳細資訊的新功能，請參閱[Office 365 郵件加密常見問題集](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)。如果您已經準備好要開始使用在組織內的新 OME 功能，請參閱[設定新的 Office 365 郵件加密功能建置於 Azure 資訊保護](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)。
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>IRM 與 Exchange Online 與 Active Directory Rights Management Services 的運作方式

Exchange Online IRM 使用內部部署 Active Directory Rights Management Services (AD RMS)、 Windows Server 2008 和較新版本的資訊保護技術。IRM 保護套用至電子郵件將 AD RMS 權限原則範本套用至電子郵件訊息。權限附加郵件本身使保護發生線上及離線和內部與外部組織的防火牆。
  
使用者可套用至電子郵件訊息來控制已在郵件的收件者的權限的範本。可以由將 AD RMS 權限原則套用至郵件控制動作，例如轉寄、 擷取訊息的資訊、 儲存一則訊息或列印郵件。
  
您可以設定 IRM 以使用 AD RMS 伺服器正在執行 Windows Server 2008 或更新版本。您可以使用此 AD RMS 伺服器的雲端架構組織中管理 AD RMS 權限原則範本。Outlook 也會依賴 AD RMS 伺服器以讓使用者能夠將 IRM 保護套用到傳送的訊息。如需詳細資訊，請參閱[設定 IRM 以使用內部部署 AD RMS 伺服器](configure-irm-to-use-an-on-premises-ad-rms-server.md)。 
  
啟用之後，您就可以依照下列方式，將 IRM 保護套用至郵件：
  
- **使用者可手動套用使用 Outlook 和 Outlook web 上的範本。** 使用者可以套用 AD RMS 權限原則範本至電子郵件訊息從 [**設定權限**] 清單中選取範本。當使用者傳送受 IRM 保護之訊息時、 使用的支援的格式的任何附加的檔案還會收到相同 IRM 保護郵件。IRM 保護套用至 Word、 Excel 及 PowerPoint 以及.xps 檔案和附加的電子郵件相關聯的檔案。 
    
- **系統管理員可以使用自動將 IRM 保護套用至 Outlook 和 Outlook web 上的傳輸保護規則。** 您可以建立 IRM 保護的郵件傳輸保護規則。設定 AD RMS 權限原則範本套用至符合的規則條件的郵件傳輸保護規則動作。啟用 IRM 之後，您的組織 AD RMS 權限原則範本可用搭配呼叫**套用權限保護到具有郵件**傳輸保護規則動作。
    
- **系統管理員可以建立 Outlook protection rules。** Outlook 保護規則會自動將 IRM 保護套用至根據郵件條件來包含寄件者的部門將郵件傳送給、 Outlook 2010 (不在網路上的 Outlook) 中郵件和收件者位於內部或外部您組織。如需詳細資訊，請參閱 ＜ [Create Outlook 保護規則](http://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx)。
    

