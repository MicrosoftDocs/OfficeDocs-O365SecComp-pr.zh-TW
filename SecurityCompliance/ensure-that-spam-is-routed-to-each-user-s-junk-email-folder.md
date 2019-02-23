---
title: 確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 7/16/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: EOP 客戶的預設反垃圾郵件動作是要將垃圾郵件移至 [收件者的垃圾郵件] 資料夾。為了讓此巨集指令來搭配內部部署信箱，您必須設定 Exchange 傳輸規則來偵測垃圾郵件標頭新增的 EOP 與內部邊緣] 或 [集線伺服器上。這些傳輸規則設定由 SclJunkThreshold 屬性使用 Set-organizationconfig 指令程式將垃圾郵件移至每個信箱的垃圾郵件] 資料夾的垃圾郵件信賴等級 (SCL)。
ms.openlocfilehash: f712e66934956bcf46215e4016501003ce9b1725
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222882"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾

> [!IMPORTANT]
> 本主題僅適用於 Exchange Online Protection (EOP) 主控信箱內部部署混合部署中的客戶。信箱已在 Office 365 中完全託管的 Exchange Online 客戶不需要執行下列命令。 
  
EOP 客戶的預設反垃圾郵件動作是要將垃圾郵件移至 [收件者的垃圾郵件] 資料夾。為了讓此巨集指令來搭配內部部署信箱，您必須設定 Exchange 傳輸規則來偵測垃圾郵件標頭新增的 EOP 與內部邊緣] 或 [集線伺服器上。這些傳輸規則設定由 SclJunkThreshold 屬性使用 Set-organizationconfig 指令程式將垃圾郵件移至每個信箱的垃圾郵件] 資料夾的垃圾郵件信賴等級 (SCL)。 
  
### <a name="to-add-transport-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a>若要新增傳輸規則來確定垃圾郵件移至 [垃圾郵件] 資料夾使用 Windows PowerShell

1. 存取您的內部部署 Exchange server 的 Exchange 管理命令介面。若要了解如何在內部部署 Exchange 組織中開啟 Exchange 管理命令介面，請參閱**開啟命令介面**。
    
2. 執行下列命令，將經過內容篩選的垃圾郵件路由傳送至 [垃圾郵件] 資料夾：
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    其中_NameForRule_是新規則，例如 JunkContentFilteredMail 的名稱。 
    
3. 執行下列命令，讓標示為垃圾郵件的郵件在抵達內容篩選器之前路由傳送至 [垃圾郵件] 資料夾：
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    其中_NameForRule_是新規則，例如 JunkMailBeforeReachingContentFilter 的名稱。 
    
4. 執行下列命令，以確定寄件者封鎖清單中的垃圾郵件篩選器原則，例如**寄件者封鎖**清單中的訊息會路由傳送至 [垃圾郵件] 資料夾： 
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    其中_NameForRule_是新規則，例如 JunkMailInSenderBlockList 的名稱。 
    
如果您不想使用**移至 [垃圾郵件] 資料夾的郵件**巨集指令，您可以選擇您在 Exchange 系統管理中心中的內容篩選器原則中的另一個巨集指令。如需詳細資訊，請參閱[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)。如需這些郵件標頭中的欄位的詳細資訊，請參閱[反垃圾郵件郵件標頭](anti-spam-message-headers.md)。
  
## <a name="see-also"></a>另請參閱

[New-transportrule 指令程式](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

