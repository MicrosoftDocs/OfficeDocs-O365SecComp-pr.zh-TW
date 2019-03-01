---
title: Exchange Online 中設定使用者垃圾郵件通知
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: 您可以設定使用者垃圾郵件通知的預設的全公司的垃圾郵件篩選原則或是網域所套用的自訂垃圾郵件篩選原則。
ms.openlocfilehash: e3e5ce044879318dab55f5d08ec2ee0e3379dfb2
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341364"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a>Exchange Online 中設定使用者垃圾郵件通知

> [!IMPORTANT]
> 本主題適用於 Exchange Online 客戶負責保護雲端託管信箱。保護內部部署信箱的 Exchange Online Protection (EOP) 獨立客戶應改閱讀下列主題： [EOP 中的設定使用者垃圾郵件通知](configure-end-user-spam-notifications-in-eop.md)。 
  
您可以設定使用者垃圾郵件通知的預設的全公司的垃圾郵件篩選原則或是網域所套用的自訂垃圾郵件篩選原則。啟用使用者垃圾郵件通知訊息，可讓您自行管理其自己的垃圾隔離郵件的使用者。使用者垃圾郵件通知不能與原則套用至使用者或群組，或具有例外狀況的原則。
  
使用者垃圾郵件通知包含使用者在您設定的時間期間 (您可指定 1 到 15 天之間的值) 內收到，被當成垃圾郵件隔離的所有郵件清單。您也可以設定用來撰寫通知郵件的語言。
  
之後收到通知郵件，使用者可以選擇下列選項：

**預覽**郵件如果您想要預覽的內容或之前採取動作的標頭。

**下載**郵件如果您想要檢閱的訊息和附件 （如果有的話） 之前採取行動裝置上。

**版本**如果郵件不是垃圾郵件，而且您希望 Office 365 將郵件傳送至您的信箱。

**釋出 & 允許寄件者**如果郵件不是垃圾郵件和您想要新增至安全的寄件者和收件者清單的未來的電子郵件的寄件者的 Office 365。請記住您的系統管理員可能會有您的安全寄件者清單會覆寫其他組織整體允許/封鎖組態。

**版本 & 報表**，如果郵件不是垃圾郵件和您想要將郵件傳送至您的信箱及該問題報告給 Microsoft 進行分析。

**封鎖**如果您希望 Office 365 將寄件者新增至封鎖的寄件者清單。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

預估完成時間：2 分鐘
  
您必須獲指派權限，才能執行此程序或各個程序。若要查看您需要的權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題中的 「 反垃圾郵件 」 項目。 
  
如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Keyboard shortcuts in Exchange 2013**。
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>使用 EAC 來設定使用者垃圾郵件通知

1. 在 Exchange 系統管理中心 (EAC)，瀏覽至 **[保護]** \> **[垃圾郵件篩選]**。
    
2. 選取您要啟用使用者垃圾郵件通知 （其預設會停用） 的垃圾郵件篩選原則。
    
3. 在右窗格中，您的原則摘要資訊出現的位置，按一下 [**設定使用者垃圾郵件通知**] 連結。 
    
4. 在後續的對話方塊中，您可以設定下列選項：
    
1. **啟用使用者垃圾郵件通知** 選取此核取方塊，以啟用此原則的使用者垃圾郵件通知。(反之，如果此原則已啟用，您可以清除此核取方塊，以停用此原則的使用者垃圾郵件通知。) 
    
2. **傳送使用者垃圾郵件通知的間隔時間 (天數)** 指定傳送使用者垃圾郵件通知的頻率。預設值為 3 天。您可以指定 1 到 15 天之間的值。例如，如果您指定 7 天，則此通知將包含在過去 7 天內對象為該使用者，卻被當成垃圾郵件隔離的所有郵件的清單。 
    
3. **通知語言** 您可以使用下拉式清單，選取用來撰寫此原則之使用者垃圾郵件通知的語言。 
    
5. 按一下 [**儲存**]。垃圾郵件篩選原則設定，包括您使用者的垃圾郵件通知設定的摘要隨即出現在右側窗格中。
    
> [!NOTE]
>  使用者垃圾郵件通知才會正常運作的已啟用的垃圾郵件篩選原則。每天一次只能傳送 > 使用者垃圾郵件通知。傳送通知的時間無法向任何特定客戶保證且無法加以設定。 
  
 **提示：** 如果您想要完全實作它們之前將它們傳送到一組有限的使用者，以測試使用者垃圾郵件通知，建立可讓使用者都位於的網域之使用者垃圾郵件通知的自訂垃圾郵件篩選原則。接著，在 EAC 中，[**郵件流程\>規則**，且您想要的使用者的例外狀況從 quarantine@messaging.microsoft.com （傳送通知電子郵件通訊） 建立郵件流程規則 （也稱為傳輸規則） 來封鎖郵件若要收到通知。下圖是來自網域 Contoso.com 建立兩個使用者 （SaraD 和 AlexD） 例外狀況的範例： 
  
![測試使用者垃圾郵件通知的傳輸規則](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a>相關資訊

[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)
  
