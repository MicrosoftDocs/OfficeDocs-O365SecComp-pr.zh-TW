---
title: Office 365 中的攻擊模擬器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/13/2019
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: 作為 Office 365 全域系統管理員, 您可以使用攻擊模擬器, 在您的組織中執行實際的攻擊案例。 這可協助您找出並尋找有漏洞的使用者, 然後才會真正受到攻擊。
ms.openlocfilehash: 938a8f944fee22fb16b87923d7608b3bfcfee0fb
ms.sourcegitcommit: 62447503300376aa95dd05fb5276f93a9f6a20b6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2019
ms.locfileid: "34927566"
---
# <a name="attack-simulator-in-office-365"></a>Office 365 中的攻擊模擬器

**摘要**如果您是 Office 365 全域系統管理員或安全性系統管理員, 而且您的組織有[office 365 威脅調查和回應功能](office-365-ti.md), 您可以使用攻擊模擬器, 在您的組織中執行實際的攻擊案例。 這可協助您找出並尋找有漏洞的使用者, 而真正的攻擊會影響您的底部線路。 若要深入瞭解, 請閱讀本文。

> [!IMPORTANT]
> Office 365 Advanced 威脅防護和威脅調查與回應 (先前稱為威脅情報) 是 Office 365 高級威脅防護計畫2的一部分, 以及額外的威脅防護功能。 若要深入瞭解, 請參閱[office 365 高級威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection), 以及[Office 365 高級威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。
  
## <a name="the-attacks"></a>攻擊

目前有三種攻擊模擬類型:
  
- [顯示名稱 spear-網路釣魚攻擊](#display-name-spear-phishing-attack)
- [密碼噴塗攻擊](#password-spray-attack)
- [強力密碼攻擊](#brute-force-password-attack)
    
若要成功啟動攻擊, 請確定用來執行模擬攻擊的帳戶是使用多重要素驗證。 此外, 您必須是 Office 365 全域系統管理員或安全性系統管理員。 (若要深入瞭解角色和許可權, 請參閱[Office 365 安全性 & 規範中心中的許可權](permissions-in-the-security-and-compliance-center.md)。)
    
若要存取攻擊模擬器, 請在&amp;安全性與合規性中心中選擇 [**威脅管理** \> **攻擊模擬器**]。
  
## <a name="before-you-begin"></a>開始之前 .。。

請確定您和您的組織符合下列攻擊模擬器的需求:
      
- **貴組織的電子郵件裝載于 Exchange Online 中**。 (內部部署電子郵件伺服器無法使用攻擊模擬器)。
    
- **您是 Office 365 全域系統管理員或安全性系統管理員**
    
- **已開啟[多重要素驗證/條件式存取](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide), 至少適用于 Office 365 全域系統管理員帳戶和安全性系統管理員**。 (理想情況下, 您組織中的所有使用者都已開啟多重要素驗證/條件式存取)。
 
- **您的組織有[Office 365 Advanced 威脅防護方案 2](office-365-ti.md)**, 在安全性&amp;與合規性中心中會顯示攻擊模擬器 (移至**威脅管理** \> **攻擊模擬器**)<br/>![威脅管理-攻擊模擬器](media/ThreatMgmt-AttackSimulator.png)

## <a name="display-name-spear-phishing-attack"></a>顯示名稱 spear-網路釣魚攻擊

網路釣魚是一種廣泛的攻擊 classed, 作為社交工程風格的攻擊。 此攻擊的重點是 spear 網路釣魚, 是一種更具針對性的攻擊, 是針對特定的個人或組織群組。 一般來說, 已執行某些偵測的自訂攻擊, 並使用將在收件者中產生信任的顯示名稱, 例如看起來像是來自組織內執行者的電子郵件。
  
此攻擊的重點是讓您可以透過變更顯示名稱和來源位址, 來操縱訊息似乎來自何處。 當 spear 網路釣魚攻擊成功時, 網路罪犯就能存取使用者的認證。
  
### <a name="to-simulate-a-spear-phishing-attack"></a>模擬 spear 網路釣魚攻擊

![撰寫電子郵件本文](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
您可以直接在**電子郵件**內文欄位中手工製作 rich HTML 編輯器, 或使用 HTML 來源。
  
1. 在[安全性&amp;與合規性中心](https://protection.office.com)中, 選擇 [**威脅管理** \> **攻擊模擬器**]。
    
2. 指定攻擊的有意義的活動名稱, 或選取範本。 <br/>![[網路釣魚開始] 頁面](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. 指定目標收件者。 這可以是組織中的個人或群組。 每個目標收件者都必須有 Exchange Online 信箱, 攻擊才會成功。 <br/>![收件者選取](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. 設定網路釣魚電子郵件詳細資料。 <br/>![設定電子郵件詳細資料](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/>HTML 格式設定可以像是您的市場活動需求一樣複雜或基本。 電子郵件格式為 HTML 時, 您可以插入影像和文字以增強 believability。 您可以控制接收到的郵件在接收的電子郵件用戶端中的外觀。
    
5. 指定 [**寄件者] (名稱)** 欄位的文字。 這是在接收電子郵件客戶程式的**顯示名稱**中顯示的欄位。 
    
6. 指定文字或 [**寄件者**] 欄位。 此欄位會顯示為接收電子郵件用戶端中寄件者的電子郵件地址。 <br/>您可以在組織內輸入現有的電子郵件命名空間 (這樣做會讓電子郵件地址在接收用戶端中實際解析, 採用非常高的信任模型), 也可以輸入外部電子郵件地址。 您指定的電子郵件地址不一定確實存在, 但是必須遵循有效的 SMTP 位址格式, 例如使用者 @ domainname。 
  
7. 使用下拉式選擇器, 選取一個網路釣魚登入伺服器 URL, 以反映您在攻擊中所擁有的內容類型。 有幾個主題 Url 可供您選擇, 例如檔傳遞、技術、薪資等。這實際上就是要求目標使用者按一下的 URL。
    
8. 指定自訂登陸頁面 URL。 使用這會將使用者重新導向至您在成功攻擊結束時指定的 URL。 例如, 如果您有內部的認識訓練, 您可以在這裡指定。
    
9. 指定 [主旨] **** 欄位的文字。 此欄位顯示為接收電子郵件客戶程式中的**主體名稱**。 
    
10. 撰寫目標將會接收的**電子郵件**內文。 <br/>`${username}`將目標名稱插入電子郵件內文。 <br/>`${loginserverurl}`插入想要讓目標使用者按一下的 URL 
    
11. 選擇 [**下一步],** 然後按一下 **[完成]** 以啟動攻擊。 Spear 網路釣魚電子郵件會傳遞至您的目標收件者的信箱。 
    
## <a name="password-spray-attack"></a>密碼噴塗攻擊

在不良參與者從租使用者成功取得有效使用者清單之後, 通常會使用組織的密碼噴塗攻擊。 不良參與者知道人們所使用的一般密碼。 這是一種廣泛使用的攻擊, 因為這是執行的廉價攻擊, 而且難以偵測到蠻力方法。
  
這個攻擊的重點是讓您針對大型使用者的使用者指定一般密碼。
  
### <a name="to-simulate-a-password-spray-attack"></a>模擬密碼噴塗攻擊

1. 在[安全性&amp;與合規性中心](https://protection.office.com)中, 選擇 [**威脅管理** \> **攻擊模擬器**]。
    
2. 指定攻擊的有意義的活動名稱。
    
3. 指定目標收件者。 這可以是組織中的個人或群組。 目標收件者必須有 Exchange Online 信箱, 攻擊才會成功。
    
4. 指定要用於攻擊的密碼。 例如, 您可以嘗試的一種常見的相關密碼`Fall2017`。 另一個可能`Spring2018`是或`Password1`。
    
5. 選擇 **[完成]** 以啟動攻擊。 
    
## <a name="brute-force-password-attack"></a>強力密碼攻擊

在不良參與者從租使用者成功取得主要使用者清單之後, 通常會使用對組織進行強力密碼攻擊。 此攻擊著重于嘗試單一使用者帳戶上的一組密碼。
  
### <a name="to-simulate-a-brute-force-password-attack"></a>模擬蠻力密碼攻擊

1. 在[安全性&amp;與合規性中心](https://protection.office.com)中, 選擇 [**威脅管理** \> **攻擊模擬器**]。
    
2. 指定攻擊的有意義的活動名稱。
    
3. 指定目標收件者。 目標收件者必須有 Exchange Online 信箱, 攻擊才會成功。
    
4. 指定要用於攻擊的一組密碼。 若要這麼做, 您可以使用文字檔 (.txt) 來做為您的密碼清單。 檔案大小的文字檔不能超過 10 MB。 每行使用一個密碼, 並確定在清單中的最後一個密碼之後包含強制換行。
    
5. 選擇 **[完成]** 以啟動攻擊。 
    
## <a name="new-features-in-attack-simulator"></a>攻擊模擬器中的新功能

最近新增功能已新增至攻擊模擬器。 這些包括：

- **高級報告功能**。 查看資料 (如最快 (或最慢) 時間) 開啟攻擊模擬電子郵件訊息的功能、最快 (或最慢) 的時間, 以按一下郵件中的連結, 以及更多的視覺效果。

- **電子郵件範本編輯器**。 建立自訂且可重複使用的電子郵件範本的功能, 可用於未來的攻擊模擬。

- **CSV 收件**者匯入。 使用 CSV 檔案來匯入目標收件者清單, 而不是使用通訊錄選擇器的功能。

**有更多新功能會在攻擊模擬器之後推出**。 這些包括：

- **附件負載網路釣魚模擬模擬**。 使用附件做為網路釣魚模擬的負載, 以取代 URL 的功能。

請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap), 以查看正在開發的專案、正在進行的功能以及已啟動的功能。

## <a name="see-also"></a>另請參閱

[Office 365 Advanced 威脅防護服務 Desription](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[Office 365 進階威脅防護](office-365-atp.md)



