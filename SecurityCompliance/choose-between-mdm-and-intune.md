---
title: 選擇 office 365 MDM 或 Microsoft Intune
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 10/3/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: c93d9ab9-efb2-4349-9b93-30c30562ee22
description: Microsoft Intune 與 Office 365 的內建行動裝置管理可讓您管理組織中的行動裝置。但此主題中所述的主要差異。
ms.openlocfilehash: 339399e2e518c22fa9f0f7482fc527990f1a8541
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526218"
---
# <a name="choose-between-mdm-for-office-365-and-microsoft-intune"></a>選擇 office 365 MDM 或 Microsoft Intune

Microsoft Intune 與 Office 365 的內建行動裝置管理可讓您管理組織中的行動裝置。但有主要差異，如下表所示。
  
> [!NOTE]
> 您可以管理使用者與在相同的 Office 365 租用戶中使用 Intune 與 Office 365 與其行動裝置。設定 Intune 及 MDM 可讓您決定哪一個解決方案是最適合的特定使用者和其裝置。如果您有兩個可用的選項，您可以選擇是否針對 Office 365 或更豐富的功能 Intune 解決方案管理 MDM 使用者的裝置。 
  
||||
|:-----|:-----|:-----|
|**功能區** <br/> |**MDM for Office 365** <br/> |**Microsoft Intune** <br/> |
|成本  <br/> |包含許多 Office 365 商業訂閱。  <br/> |需要 Microsoft Intune 付費的訂閱或可購買與企業行動性套件。  <br/> |
|管理裝置的方式  <br/> |管理裝置使用[移至 Office 365 安全性&amp;規範中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)Office 365。  <br/> |如果您使用 Intune 本身，管理裝置使用 Intune 系統管理主控台。  <br/> 如果您使用 System Center 2012 Configuration Manager 整合 Intune，您會使用 Configuration Manager console 來管理裝置內部部署與雲端中。  <br/> |
|您可以管理的裝置  <br/> |IOS、 Android、 及 Windows 雲端式管理裝置  <br/> |雲端管理的 iOS、 Mac OS X、 Android、 Windows 8.1 （電話和 PC） 及稍後要包含 Windows 10。 <br/> |
|主要功能  <br/> |協助確保可以存取 Office 365 公司電子郵件和文件只有在電話或平板電腦的管理您的公司以及 IT 原則符合上。  <br/> 設定和管理安全性原則層級的 pin 鎖定及 jailbreak 偵測裝置，以協助防止未經授權的使用者存取公司的電子郵件和裝置上的資料遺失或竊時類似。  <br/> 移除員工的裝置的 Office 365 公司資料時備妥離開其個人的資料。  <br/> [Office 365 的內建行動裝置管理功能](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0)中所包含的詳細資訊。  <br/> |Office 365 功能的 MDM 加上：  <br/> 協助使用者在安全地存取公司資源與憑證、 Wi-fi、 VPN 和電子郵件設定檔。  <br/> 註冊並管理的公司擁有的裝置，簡化原則和應用程式部署的集合。  <br/> 對使用者部署您的內部企業營運系統應用程式和存放區中的應用程式。  <br/> 讓使用者更安全地存取公司資訊使用 Office 行動裝置及線條的商務應用程式其了解，同時限制協助確保資料的安全性動作想要複製、 剪下、 貼上另存為，由 Intune 管理這些應用程式。  <br/> 可讓更安全 web 瀏覽使用 Intune 受管理的瀏覽器應用程式。  <br/> 從雲端管理的 Pc 與任何基礎結構所需使用 Intune，或連線 Intune 至 Configuration Manager 來管理您的裝置包括 Pc、 Mac、 Linux 以及 UNIX 的所有伺服器及單一管理主控台從行動裝置。  <br/> Intune 訂閱也可讓您設定 MAM （行動裝置應用程式管理） 原則使用 Azure 入口網站中，即使人的裝置不會註冊 Intune。請參閱 ＜ [Protect 應用程式資料 MAM 原則 （英文）](https://go.microsoft.com/fwlink/?LinkId=825439)。<br/> |


## <a name="related-topics"></a>相關主題
   
深入了解 Microsoft Intune 影片訓練課程[Microsoft 雲端服務： 管理 Office 365 和 Intune](https://support.office.com/article/c1224e20-3d49-4f40-99ee-fd0991880376.aspx)、 LinkedIn 學習由致力提供給您。
  

