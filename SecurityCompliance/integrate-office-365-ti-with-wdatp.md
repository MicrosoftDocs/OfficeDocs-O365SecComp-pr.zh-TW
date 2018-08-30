---
title: 整合 Office 365 威脅情報與 Windows Defender 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: 整合 Office 365 進階威脅保護與 Windows 防禦者進階威脅保護查看 threat management 的詳細的資訊。
ms.openlocfilehash: 574594d5881853b268713e0bb74444ae80ffcf46
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526462"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a>整合 Office 365 威脅情報與 Windows Defender 進階威脅防護

如果您組織的安全性小組的一部分，可以整合 Office 365 與 Windows 防禦者進階威脅保護 (ATP)。這可協助您快速了解當您正在調查 Office 365 中的潛在威脅是否使用者的機器是否在風險。例如，啟用整合後，您將能夠如何許多最近提醒那些傳真機具有 Windows 防禦者 ATP 中也會看見機器偵測到的電子郵件之郵件的收件者所使用的清單。
  
下圖顯示 [**裝置**] 索引標籤您會看見時有啟用 Windows 防禦者 ATP 整合： 
  
![啟用 Windows 防禦者 ATP 時，您可以看到機器提醒的清單。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
在這個範例中，您可以看到電子郵件之收件者有四部機器和一個具有 Windows 防禦者 ATP 通知。按一下機器連結會開啟 [電腦] 頁面上的 Windows 防禦者 ATP 新的索引標籤中。
  
## <a name="requirements"></a>需求

- 您的組織必須具有 Office 365 威脅智慧及 Windows 防禦者 ATP。
    
- 您必須是 Office 365 全域管理員或已指派安全性的安全性管理員角色&amp;規範中心。(請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md))
    
- 您必須具有 Office 365 威脅智慧及 Windows 防禦者 ATP 入口網站存取權。
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a>整合 Windows 防禦者 ATP Office 365 威脅智慧

整合 Office 365 威脅智慧與 Windows 防禦者 ATP 已設定在 Office 365 和 Windows 防禦者 ATP 入口網站中。
  
1. 為 Office 365 全域或安全性管理員，請移至[https://portal.office.com](https://portal.office.com)和登入 Office 365 您工作或學校的帳戶。 
    
2. 選擇 [ **Threat management** \> **威脅瀏覽器**。
    
3. 按一下 [**更多**] 功能表選擇**WDATP 設定**。
    
4. 選取 [**連線至 Windows ATP**。
    
您已變更 Office 365 中的設定之後，您必須啟用 Windows 防禦者 ATP 的連線。若要這樣做，請參閱 ＜ [Use Windows 防禦者進階威脅保護入口網站](https://go.microsoft.com/fwlink/?linkid=859690)。
  
## <a name="related-topics"></a>相關主題

[Office 365 威脅情報](office-365-ti.md)
  
[Office 365 進階威脅防護](office-365-atp.md)
  

