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
description: 使用 Office 365，有些加密功能會開啟預設值;其他功能可設定以滿足特定法規或法律需求。
ms.openlocfilehash: 1bc4ceb7762c96f55c03f89e7c448f9e4073063e
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260791"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>設定 Office 365 企業版中的加密

加密可以防止內容被讀取未經授權的使用者。 因為[Office 365 中的加密](encryption.md)可以完成使用各種技術和方法，沒有單一位置： 開啟或加密設定。 本文提供您可以設定或加密設定的資訊保護策略的一部分的各種方式的相關資訊。
  
> [!TIP]
> 如果您要尋找的加密的詳細技術資訊，請參閱[關於 Office 365 中加密的技術參考細節](technical-reference-details-about-encryption.md)。
  
使用 Office 365，多個加密功能，可依預設。 其他加密功能可設定以滿足特定法規或法律需求。 下表說明數個不同案例的加密方法。
  
|**案例**|**加密方法**|
|:-----|:-----|
|檔案都儲存在 Windows 電腦上  <br/> |在電腦層級的加密可以完成 Windows 裝置上使用 BitLocker。 為企業系統管理員或 IT 專業人員，您可以設定這使用 Microsoft 部署 Toolkit (MDT)。 請參閱 < <b0>Set up MDT 的 BitLocker</b0>。  <br/> |
|檔案都儲存在行動裝置上  <br/> |某些類型的行動裝置加密預設會儲存至那些裝置的檔案。 與[Office 365 的內建行動裝置管理功能](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0)，您可以設定原則，以決定是否允許行動裝置存取 Office 365 中的資料。 例如，您可以設定的原則，可讓裝置的加密來存取 Office 365 資料的內容。 請參閱[建立及部署裝置安全性原則](https://support.office.com/article/d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)。  <br/> 與 Office 365 進行互動的行動裝置要如何額外的控制權，您可以考慮加入[Microsoft Intune](https://aka.ms/qzln04)。 請參閱[Office 365 的 MDM 和 Microsoft Intune 之間選擇](https://support.office.com/article/c93d9ab9-efb2-4349-9b93-30c30562ee22)。  <br/> |
|您必須控制用來加密您在 Microsoft 資料中心中的資料的加密金鑰  <br/> | 是 Office 365 系統管理員，您可以控制您組織的加密金鑰，然後設定 [要用來加密存放在 Microsoft 資料中心中的 Office 365。  <br/> [使用客戶金鑰控制 Office 365 中的資料](controlling-your-data-using-customer-key.md) <br/> [Office 365 常見問題集的客戶金鑰](service-encryption-with-customer-key-faq.md) <br/> |
|人員進行通訊透過電子郵件 (Exchange Online)  <br/> | Exchange Online 的系統管理員，您必須設定電子郵件加密的數個選項。 這些包括：  <br/>  使用 Azure 版權管理 (Azure RMS) 中的[Office 365 郵件加密 (OME)](set-up-new-message-encryption-capabilities.md) ，以啟用傳送加密的郵件，您組織內部或外部的人員  <br/>  使用[為郵件簽章和加密的 S/MIME](https://aka.ms/c6dozg)加密及數位簽署電子郵件  <br/>  使用 TLS 來[設定與另一個組織的安全郵件流程的連接器](https://aka.ms/hs809p) <br/>  請參閱[Office 365 中的電子郵件加密](https://aka.ms/hic3f7)。  <br/> |
|從小組網站] 或 [文件庫 (商務用 OneDrive 或 SharePoint Online) 來存取檔案  <br/> |時的人正在使用檔案儲存到 OneDrive for Business 或 SharePoint Online，則會使用 TLS 連線。 這是內建 Office 365 自動。 請參閱[商務用 OneDrive 和 SharePoint Online 中的資料加密](https://go.microsoft.com/fwlink/?linkid=526379)。  <br/> |
|檔案共用的線上會議和 IM 交談 (Skype for Business Online)  <br/> |當人員使用的檔案使用商務用 Skype 時，使用 TLS 連線。 這是內建 Office 365 自動。 請參閱[安全性和封存 (商務用 Skype)](https://aka.ms/nuq4ws)。  <br/> |

## <a name="additional-information"></a>其他資訊

若要深入了解包含的加密選項的檔案保護解決方案，請參閱[在 Office 365 中的檔案保護解決方案](https://www.microsoft.com/en-us/download/details.aspx?id=55523)。