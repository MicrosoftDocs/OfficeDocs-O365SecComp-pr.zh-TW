---
title: 設定 Office 365 企業版中的加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: 使用 Office 365 某些加密功能的預設開啟;其他功能可以設定成符合特定規範或法律規定。
ms.openlocfilehash: 5447f8c9a2074ce586ad38b0c1881afa6d948ad1
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213453"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>設定 Office 365 企業版中的加密

加密可以從所讀取的未經授權的使用者來保護您的內容。因為您可以選擇[加密 Office 365 中的](encryption.md)使用各種不同的技術和方法，沒有一個單一位置供您開啟或加密設定。本文提供您可以設定或加密設定的資訊保護策略的一部分的各種方式的相關資訊。 
  
> [!TIP]
> 如果您要尋找更多技術加密的相關的詳細資訊，請參閱[Office 365 中加密的相關的技術參考 （英文） 詳細資料](technical-reference-details-about-encryption.md)。 
  
Office 365 的數種加密功能預設可用。其他加密功能可以設定成符合特定規範或法律規定。下表說明針對不同案例的數種加密方法。
  
|**案例**|**加密方法**|
|:-----|:-----|
|檔案都儲存在 Windows 電腦上  <br/> |您可以選擇加密層級的電腦上 Windows 裝置使用 BitLocker。為企業系統管理員或 IT 專業人員，您可以設定此使用 Microsoft Deployment Toolkit (MDT)。請參閱 ＜ [Set up MDT 的 BitLocker](https://go.microsoft.com/fwlink/?linkid=849282)。<br/> |
|檔案都儲存在行動裝置上  <br/> |某些類型的行動裝置加密預設儲存至那些裝置的檔案。使用[內建行動裝置管理 Office 365 的功能](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0)，您可以設定原則決定是否要讓行動裝置能夠存取 Office 365 中的資料。例如，您可以設定原則允許裝置的加密來存取 Office 365 資料的內容。請參閱[建立及部署裝置安全性原則](https://support.office.com/article/d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)。<br/> 與 Office 365 進行互動方式行動裝置上的其他控制項，您可以考慮新增[Microsoft Intune](https://aka.ms/qzln04)。請參閱 ＜ [Choose between MDM for Office 365 and Microsoft Intune](https://support.office.com/article/c93d9ab9-efb2-4349-9b93-30c30562ee22)。<br/> |
|您需要用來加密您在 Microsoft 資料中心中的資料的加密金鑰的控制權  <br/> | Office 365 系統管理員身分您可以控制您組織的加密金鑰及使用方式來加密 Microsoft 資料中心的靜態資料的 Office 365，則設定。  <br/> [使用客戶金鑰控制 Office 365 中的資料](controlling-your-data-using-customer-key.md) <br/> [客戶金鑰的 Office 365 常見問題集](service-encryption-with-customer-key-faq.md) <br/> |
|人員會傳達透過電子郵件 (Exchange Online)  <br/> | 身為 Exchange Online 管理員，您必須設定電子郵件加密的數個選項。這些包括：<br/>  使用 Azure 版權管理 (Azure RMS) 與[Office 365 郵件加密 (OME)](set-up-new-message-encryption-capabilities.md)啟用來傳送加密的郵件貴組織內外的人員  <br/>  使用[用於訊息簽署和加密的 S/MIME](https://aka.ms/c6dozg)加密及數位簽署電子郵件  <br/>  若要[設定連接器的安全郵件流程與其他組織](https://aka.ms/hs809p)使用 TLS <br/>  請參閱[Office 365 中的電子郵件加密](https://aka.ms/hic3f7)。  <br/> |
|檔案存取小組網站或文件庫 (OneDrive for Business 或 SharePoint Online)  <br/> |人員會使用檔案儲存至 OneDrive for Business 或 SharePoint Online、 時使用 TLS 連線。這是內建 Office 365 自動。請參閱[OneDrive for Business 和 SharePoint Online 中的資料加密](https://go.microsoft.com/fwlink/?linkid=526379)。<br/> |
|檔案共用的線上會議和 IM 交談 (Skype 商務 online)  <br/> |人員使用的商務 Online 使用 Skype 檔案、 時 TLS 用連線。這是內建 Office 365 自動。請參閱[安全性和封存 (Skype Online 企業版)](https://aka.ms/nuq4ws)。<br/> |
   
## <a name="additional-information"></a>其他資訊

若要深入了解包含加密選項的檔案保護方案，請參閱[Office 365 中的檔案保護解決方案](https://www.microsoft.com/en-us/download/details.aspx?id=55523)。
  

