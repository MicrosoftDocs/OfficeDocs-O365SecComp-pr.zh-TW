---
title: '安裝 Outlook 電腦版的監督增益集 '
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- ZOL160
ms.assetid: 6c5620e6-aba3-4910-8f3a-b55451656ff7
description: 安裝 Office 365 監督增益集的桌面的 Outlook 版本
ms.openlocfilehash: b0cb0d78ab5f8887628528dd53b49fb15de44126
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180863"
---
# <a name="install-the-supervision-add-in-for-outlook-desktop"></a>安裝 Outlook 電腦版的監督增益集 

若要檢閱監督原則所識別的通訊，請檢閱者使用的監督增益集 Outlook 和 Outlook web app。增益集會自動安裝 Outlook web app 中所指定之原則的所有檢閱者的。不過，檢閱者必須執行完成某些步驟，以安裝在桌面的 Outlook 版本。
  
> [!NOTE]
> 監督原則受監控的使用者必須具有進階規範附加元件可以是 Office 365 企業版 E3 授權或包含在 Office 365 企業版 E5 訂閱。如果您未有現有的企業 E5 計劃以及要嘗試監督，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。
  
## <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>步驟 1： 將複製的監督信箱的地址

若要安裝的 Outlook 桌面增益集，您將需要位址監督信箱建立為監督原則安裝程式的一部分。
  
> [!NOTE]
> 如果別人建立原則，您需要從其安裝增益集取得此位址。
 
 **若要尋找的監督信箱地址**
  
1. 登入[安全性&amp;規範中心](https://protection.office.com)使用 Office 365 組織中的管理帳戶的認證。
    
2. 移至 [**資料控管** \> **監督**。
    
3. 按一下 [收集您想要檢閱的通訊的監督原則。
    
4. 在原則中詳述彈出式、 底下 * * 監督信箱 * *、 複製的位址。<br/>!['監督信箱'] 區段中的監督原則的詳細資訊彈出式顯示醒目提示的監督信箱地址](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
## <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a>步驟 2： 設定 Outlook 桌面 access 監督信箱

接下來，檢閱者需要讓他們可以將 Outlook 連接到監督信箱執行幾個的 Exchange Online PowerShell 命令。
  
1. 連線到 Exchange Online PowerShell。[如何執行這？](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
    
2. 執行下列命令，其中*SupervisoryReview{GUID}@domain.onmicrosoft.com*是您在上述步驟 1 中複製的地址和*使用者*是檢閱者都要連線至步驟 3 中的監督信箱的名稱。
    - ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```<br/>
    - ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```
    
3. 等待至少一小時前將移至下的步驟 3。
    
## <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>步驟 3： 建立 Outlook 設定檔連線至監督信箱

最後一個步驟中，檢閱者必須建立 Outlook 設定檔連線至監督信箱。
 
> [!NOTE]
> 若要建立新的 Outlook 設定檔，您將在 Windows 控制台中使用 [郵件設定。您需要以取得這些設定的路徑可能會取決於您正在使用的 Windows 作業系統 （Windows 7、 Windows 8 或 Windows 10） 及安裝的 Outlook 版本。
  
1. 開啟 [控制台] 中，並在視窗頂端的 [**搜尋**] 方塊中輸入**郵件**。<br/>(不確定如何取得 Control panel？請參閱[所在控制台吗？](https://support.microsoft.com/help/13764/windows-where-is-control-panel))
  
2. 開啟**郵件**應用程式。
    
3. 在 [**郵件設定-Outlook**中，按一下 [**顯示設定檔**]。<br/>!['郵件安裝-Outlook'' 顯示設定檔 」 按鈕醒目提示] 對話方塊](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. 在 [**郵件**] 按一下 [**新增**]。然後，在**新的設定檔**、 輸入的名稱 （例如**監督**） 監督信箱。<br/>![在 [設定檔名稱] 方塊中顯示名稱 '監督' ' 新設定檔 」 對話方塊](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. 在 [**連線至 Office 365 的 Outlook**中，按一下 [**連接到不同的帳戶**。<br/>![' 連線至 Office 365 Outlook' 郵件與反白顯示 「 連接至不同的帳戶' 連結](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. 在 [**自動帳戶設定**] 選擇**手動安裝程式] 或 [其他伺服器類型**，並再按 [**下一步**。
    
7. 在 [**選擇您的帳戶類型**，選擇 [ **Office 365**]。然後，在 [**電子郵件地址**] 方塊中輸入您在先前複製監督信箱的地址。<br/>![Outlook 顯示醒目提示 [' 電子郵件地址 」] 方塊中的 [新增帳戶] 對話方塊的 「 選擇您的帳戶類型 」 頁面。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. 出現提示時，輸入您的 Office 365 認證。
    
9. 如果成功，您會看見**監督-\<原則名稱\>** 在 Outlook 中的資料夾清單檢視中列出的資料夾。