---
title: 使用取消列出入口網站，將您自己從 Office 365 封鎖寄件者清單中移除
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/18/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
description: 當您嘗試將電子郵件傳送給其電子郵件地址是在 Office 365 中的收件者時，是否收到錯誤？如果您認為您不應該收到錯誤訊息，您可以使用取消列出入口網站，將您自己從 Office 365 封鎖寄件者清單中移除。
ms.openlocfilehash: 127b305cdb27cffadc7ad6a43a5d2db2440365ca
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026230"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a>使用取消列出入口網站，將您自己從 Office 365 封鎖寄件者清單中移除

當您嘗試將電子郵件傳送給其電子郵件地址是在 Office 365 中的收件者時，是否收到錯誤？如果您認為您不應該收到錯誤訊息，您可以使用取消列出入口網站，將您自己從 Office 365 封鎖寄件者清單中移除。
  
## <a name="what-is-the-office-365-blocked-senders-list"></a>什麼是 Office 365 封鎖寄件者清單？

Microsoft 會使用封鎖寄件者清單，來保護其客戶避免垃圾郵件、詐騙和網路釣魚攻擊。您的郵件伺服器的 IP 位址，也就是您的郵件伺服器用來在網際網路上識別其本身的位址，因為其中一個原因，已標記為 Office 365 的潛在威脅。當 Office 365 將 IP 位址新增至清單時，它會防止 IP 位址和透過我們的資料中心的任何客戶之間的所有進一步通訊。
  
當您收到包含錯誤如下的郵件訊息時，您就會知道您已新增至清單：
  
「 拒絕存取 」、 550 5.7.606-649 禁止傳送 IP [ _IP 位址_];若要要求從此清單移除請造訪https://sender.office.com/並遵循指示。如需詳細資訊請參閱[Office 365 中的電子郵件未傳遞回報](http://go.microsoft.com/fwlink/?LinkID=526653)。
  
其中  _IP address_ 是郵件伺服器執行所在之電腦的 IP 位址。 
  
### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>若要使用 Office 365 取消列出入口網站將您自己從封鎖寄件者清單中移除

1. 在 Web 瀏覽器中，移至 [https://sender.office.com](https://sender.office.com)。
    
2. 遵循頁面中的指示。請確定您使用被傳送錯誤訊息的電子郵件地址，以及在錯誤訊息中指定的 IP 位址。您每次造訪只能輸入一個電子郵件地址及一個 IP 位址。
    
3. 按一下 **[送出]**。
    
    入口網站會將電子郵件傳送至您所提供的電子郵件地址。電子郵件將看起來類似下列：![送出要求透過 delist 入口網站時所接收的電子郵件的螢幕擷取畫面](media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)
  
4. 按一下取消列出入口網站傳送給您的電子郵件中的確認連結。
    
    這可以讓您回到取消列出入口網站。
    
5. 在取消列出入口網站中，按一下 **[取消列出 IP]**。
    
    從封鎖寄件者清單移除 IP 位址後，來自該 IP 位址的電子郵件訊息將會傳遞給使用 Office 365 的收件者。因此，請確認您確信從該 IP 位址傳送的電子郵件沒有不當或惡意，否則，可能會再度封鎖 IP 位址。
    

