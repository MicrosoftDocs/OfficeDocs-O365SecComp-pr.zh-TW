---
title: 確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 系統管理員可以了解如何路由傳送垃圾郵件使用者垃圾郵件資料夾在 Exchange Online Protection。
ms.openlocfilehash: 390ba26167521ccea7b69e7fac21924c0b9ec7de
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153208"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾

> [!IMPORTANT]
> 本主題僅適用於主控信箱的內部混合部署中的 Exchange Online Protection (EOP) 客戶。 信箱已完全裝載於 Office 365 的 Exchange Online 客戶不需要執行下列命令。 
  
EOP 客戶的預設反垃圾郵件動作，就是將垃圾郵件移至收件者的 [垃圾郵件] 資料夾。 為了讓此動作可搭配內部部署信箱，您必須在您的內部邊緣] 或 [集線伺服器，以偵測 EOP 所新增的垃圾郵件標頭上設定 Exchange 郵件流程規則 （也稱為傳輸規則）。 這些郵件流程規則設定垃圾郵件信賴等級 (SCL) 的 Set-organizationconfig 指令程式的 SclJunkThreshold 內容所用來將垃圾郵件移至每個信箱的垃圾郵件] 資料夾。 
  
### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a>若要新增郵件流程規則，以確保垃圾郵件移至 [垃圾郵件] 資料夾使用 Windows PowerShell

1. 存取內部部署 Exchange 伺服器的 Exchange 管理命令介面。 若要了解如何在內部部署 Exchange 組織中開啟 Exchange 管理命令介面，請參閱 **Open the Shell** 。
    
2. 執行下列命令，將經過內容篩選的垃圾郵件路由傳送至 [垃圾郵件] 資料夾：
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    _NameForRule_所在的新規則，例如 JunkContentFilteredMail 的名稱。 
    
3. 執行下列命令，讓標示為垃圾郵件的郵件在抵達內容篩選器之前路由傳送至 [垃圾郵件] 資料夾：
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    _NameForRule_所在的新規則，例如 JunkMailBeforeReachingContentFilter 的名稱。 
    
4. 執行下列命令，以確定寄件者封鎖清單中的垃圾郵件篩選原則，例如**寄件者封鎖**清單中，郵件會路由傳送至 [垃圾郵件] 資料夾： 
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    _NameForRule_所在的新規則，例如 JunkMailInSenderBlockList 的名稱。 
    
如果您不想要使用 [**移至垃圾郵件] 資料夾的郵件**] 動作，您可以選擇另一個巨集指令中 Exchange 系統管理中心中內容篩選原則。 如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。 如需這些欄位中的郵件標頭的詳細資訊，請參閱 <<c0>反垃圾郵件郵件標頭。
  

> [!TIP]
> 如果您不想要使用 [**移至垃圾郵件] 資料夾的郵件**] 動作，您可以選擇另一個巨集指令中 Exchange 系統管理中心中內容篩選原則。 如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。 如需這些欄位中的郵件標頭的詳細資訊，請參閱 <<c0>反垃圾郵件郵件標頭。
> 
## <a name="see-also"></a>另請參閱

[New-transportrule 指令程式](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

