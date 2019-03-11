---
title: 整合 Office 365 進階的威脅防護與 Windows Defender 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: 整合 Windows Defender 進階威脅防護來威脅管理的詳細的資訊請參閱 < Office 365 進階威脅防護。
ms.openlocfilehash: bbbb42c9d0f37ab33323b2fa1dd071bd5ee16829
ms.sourcegitcommit: 74ad22a5c6c3c9d9324f0f97070909e323a4e9cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2019
ms.locfileid: "30523977"
---
# <a name="integrate-office-365-advanced-threat-protection-with-windows-defender-advanced-threat-protection"></a>整合 Office 365 進階的威脅防護與 Windows Defender 進階威脅防護

如果您是貴組織的安全性小組的一部分，您可以使用 Windows Defender 進階威脅防護整合 Office 365 進階威脅防護和回應功能相關的調查。 這可協助您快速了解您正在調查 Office 365 中的威脅時是否使用者的電腦是否處於風險。 例如，一旦啟用整合，您將能夠查看機器所使用的郵件收件者偵測到的電子郵件，以及如何在 Windows Defender 進階威脅防護中的許多最近的通知這些機器有。
  
下圖顯示 [**裝置**] 索引標籤，您會看到已啟用 Windows Defender 進階威脅防護整合的時機： 
  
![啟用 Windows Defender ATP 時，您可以看到機器警示的清單。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
在這個範例中，您可以看到電子郵件的收件者有四種裝置，以及其他有警示。 Windows Defender 進階威脅防護入口網站中，按一下 [裝置] 連結開啟其頁面。
  
## <a name="requirements"></a>需求

- 您的組織必須擁有 Office 365 進階的威脅防護方案 2 （或 Office 365 E5） 以及 Windows Defender ATP。
    
- 您必須是 Office 365 全域管理員或具有安全性系統管理員角色 （例如安全性管理員） 中指派[安全性&amp;合規性中心](https://protection.office.com)。 (請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md))
    
- 您必須具有安全性 & 合規性中心中的 Office 365 威脅總管和 Windows Defender 進階威脅防護入口網站存取權。
    
## <a name="to-integrate-office-365-advanced-threat-protection-with-windows-defender-atp"></a>將 Windows Defender ATP 與整合 Office 365 進階威脅防護

整合 Office 365 進階威脅防護與 Windows Defender 進階威脅防護會設定使用這兩個 Office 365 安全性 & 合規性中心與 Windows Defender 進階威脅防護入口網站。
  
1. 為 Office 365 全域系統管理員或安全性系統管理員，請移至[https://protection.office.com](https://protection.office.com)並以 Office 365 您公司或學校帳戶登入。 
    
2. 選擇 [**威脅管理** \> **總管**。<br>![威脅管理] 功能表中的 explorer](media/ThreatMgmt-Explorer-nav.png)<br>
    
3. 在螢幕的右上角，選擇 [ **WDATP 設定**。
    
4. 在 [Windows Defender ATP 連線] 對話方塊中，開啟連線到 Windows ATP。<br>![Windows Defender ATP 連線](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. 啟用 Windows Defender 進階威脅防護中的連線。 請參閱[使用 Windows Defender 進階威脅防護入口網站](https://go.microsoft.com/fwlink/?linkid=859690)。

  
## <a name="related-topics"></a>相關主題

[Office 365 威脅調查及回應](office-365-ti.md)
  
[Office 365 進階威脅防護](office-365-atp.md)
  

