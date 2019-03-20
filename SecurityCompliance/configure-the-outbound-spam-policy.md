---
title: 設定輸出垃圾郵件原則
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/10/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 如果您使用該服務來傳送輸出電子郵件，便會一律啟用輸出垃圾郵件篩選功能，從而保護使用該服務的組織及其預期的收件者。
ms.openlocfilehash: af48962879dd4ee1e5bbbe832f221e88900faa75
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692802"
---
# <a name="configure-the-outbound-spam-policy"></a>設定輸出垃圾郵件原則

如果您使用該服務來傳送輸出電子郵件，便會一律啟用輸出垃圾郵件篩選功能，從而保護使用該服務的組織及其預期的收件者。與輸入篩選類似，輸出垃圾郵件篩選也包括連線篩選和內容篩選，但是輸出篩選器設定不可設定。如果輸出郵件被判定為垃圾郵件，就會透過較高風險傳遞集區路由傳送，以降低正常輸出 IP 集區被加入封鎖清單的可能性。如果客戶繼續透過服務傳送輸出垃圾郵件，則會被封鎖而無法傳送郵件。雖然您無法停用或變更輸出垃圾郵件篩選，但您可透過預設的輸出垃圾郵件原則，設定數個全公司適用的輸出垃圾郵件設定。 
  
下列影片顯示如何設定輸出垃圾郵件原則：
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1f20d655-0d3d-4141-9cae-e57f5a6cffe8?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

預估完成時間：5 分鐘
  
您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要哪些權限，請參閱 「 反垃圾郵件中的項目[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題。 
  
如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Keyboard shortcuts in Exchange 2013**。
  
您也可以透過遠端 PowerShell 執行下列程序。 使用[Get-hostedoutboundspamfilterpolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) cmdlet 來檢閱您的設定，以及[Set-hostedoutboundspamfilterpolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx)編輯您的輸出垃圾郵件原則設定。 若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱[Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。 若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。
  
## <a name="use-the-eac-to-edit-the-default-outbound-spam-policy"></a>使用 EAC 編輯預設輸出垃圾郵件原則
<a name="sectionSection1"> </a>

使用下列程序編輯預設輸出垃圾郵件原則：
  
### <a name="to-configure-the-default-outbound-spam-policy"></a>設定預設輸出垃圾郵件原則

1. 在 Exchange 系統管理中心 (EAC) 中，瀏覽至 **[保護]** \> **[輸出垃圾郵件]**，然後連按兩下預設原則。
    
2. 選取 **[輸出垃圾郵件喜好設定]** 功能表選項。 
    
3. 選取輸出郵件的下列附屬核取方塊，然後在隨附的輸入方塊中指定關聯的電子郵件地址 (如果它們解析為有效的 SMTP 目的地，則這可以是通訊群組清單)：
    
1. **傳送所有可疑輸出電子郵件的副本至下列一或多個電子郵件地址**。這些是被篩選器標示為垃圾郵件的郵件 (不管其 SCL 分級)。篩選器不會拒絕這些郵件，而是會透過較高風險傳遞集區路由傳送這些郵件。請以分號分隔多個地址。請注意，指定的收件者會當作密件副本 (Bcc) 地址收到郵件 ([寄件者] 和 [收件者] 欄位為原始寄件者和收件者)。
    
2. **當寄件者被封鎖無法傳送輸出垃圾郵件，傳送通知至下列電子郵件地址**。請以分號分隔多個地址。
    
    當特定使用者發出大量垃圾郵件時，該使用者會被停用且無法再傳送電子郵件。 網域的系統管理員 (使用此設定指定) 會收到通知，告知已封鎖該使用者的輸出郵件。 若要查看此通知的外觀，請參閱[當封鎖寄件者時傳送輸出垃圾郵件的範例通知](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)。 如需加以重新啟用的詳細資訊，請參閱 <<c0>移除使用者、 網域或 IP 位址從封鎖清單傳送過垃圾。
    
4. 按一下 **[儲存]**。 預設原則設定的摘要隨即出現在右側窗格中。
    
## <a name="for-more-information"></a>相關資訊
<a name="sectionSection2"> </a>

[高風險傳遞集區的外寄郵件](high-risk-delivery-pool-for-outbound-messages.md)
  
[反垃圾郵件保護常見問題集](anti-spam-protection-faq.md)
  

