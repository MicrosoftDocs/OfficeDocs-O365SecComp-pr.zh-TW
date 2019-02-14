---
title: 整合 Office 365 威脅情報與 Windows Defender 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection: M365-security-compliance
description: 整合 Office 365 進階威脅保護與 Windows 防禦者進階威脅保護查看 threat management 的詳細的資訊。
ms.openlocfilehash: f8f5f50af10fb668aa67b68604e95e8dd19c9e69
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995204"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a>整合 Office 365 威脅情報與 Windows Defender 進階威脅防護

如果您組織的安全性小組的一部分，您可以使用 Windows 防禦者進階威脅保護整合 Office 365 進階威脅保護和威脅智慧功能。這可協助您快速了解當您正在調查 Office 365 中的潛在威脅是否使用者的機器是否在風險。例如，啟用整合後，您將能夠許多最近提醒那些傳真機有 Windows 防禦者進階威脅 Protection 中的方式，以及查看機器偵測到的電子郵件之郵件的收件者所使用的清單。
  
下圖顯示 [**裝置**] 索引標籤您會看見時有啟用 Windows 防禦者進階威脅保護整合： 
  
![啟用 Windows 防禦者 ATP 時，您可以看到機器提醒的清單。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
在這個範例中，您可以看到電子郵件之收件者有四種裝置和一個具有通知。按一下 [裝置] 連結 Windows 防禦者進階威脅保護入口網站中開啟其頁面。
  
## <a name="requirements"></a>需求

- 您的組織必須具有 Office 365 威脅智慧及 Windows 防禦者 ATP。
    
- 您必須是 Office 365 全域管理員或已指派中的安全性管理員角色 （例如安全性管理員）[安全性&amp;規範中心](https://protection.office.com)。(請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md))
    
- 您必須具有 Office 365 威脅智慧及 Windows 防禦者進階威脅保護入口網站存取權。
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a>整合 Windows 防禦者 ATP Office 365 威脅智慧

整合 Office 365 威脅智慧與 Windows 防禦者進階威脅保護會設定使用這兩種 Office 365 安全性 & 規範中心和 Windows 防禦者進階威脅保護入口網站。
  
1. 為 Office 365 全域管理員或安全性管理員，請移至[https://protection.office.com](https://protection.office.com)和登入 Office 365 您工作或學校的帳戶。 
    
2. 選擇 [ **Threat management** \> **瀏覽器**。<br>![Threat Management] 功能表中的瀏覽器](media/ThreatMgmt-Explorer-nav.png)<br>
    
3. 在螢幕右上角選擇**WDATP 設定**。
    
4. 在 [Windows 防禦者 ATP 連線] 對話方塊中，開啟連接到 Windows ATP。<br>![Windows 防禦者 ATP 連線](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. 啟用 Windows 防禦者進階威脅 Protection 中的連線。請參閱 ＜ [Use Windows 防禦者進階威脅保護入口網站](https://go.microsoft.com/fwlink/?linkid=859690)。

  
## <a name="related-topics"></a>相關主題

[Office 365 威脅情報](office-365-ti.md)
  
[Office 365 進階威脅防護](office-365-atp.md)
  

