---
title: Office 365 中的攻擊模擬器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/09/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: 身為 Office 365 全域管理員，您可以使用攻擊模擬器您組織中執行真實感化的攻擊案例。這可協助您識別及之前實際攻擊拜訪人次業務找出遭到入侵的使用者。
ms.openlocfilehash: ccef127c4ce4d806ef9af04673b8c68d82ce9ec6
ms.sourcegitcommit: 7c55721b51b2f321537a0cdad6644abf91996710
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2018
ms.locfileid: "26256438"
---
# <a name="attack-simulator-in-office-365"></a>Office 365 中的攻擊模擬器

**摘要**如果您的組織具有[Office 365 威脅智慧](office-365-ti.md)Office 365 全域管理員，您可以使用攻擊模擬器您組織中執行真實感化的攻擊案例。這可協助您識別並尋找遭到入侵的使用者才能實際攻擊影響底部線條。請閱讀本篇文章以深入了解。
  
## <a name="the-attacks"></a>攻擊

目前攻擊模擬的三種可用：
  
- [顯示名稱矛網路釣魚攻擊](attack-simulator.md#spearphish)
    
- [密碼噴灑攻擊](attack-simulator.md#passwordspray)
    
- [暴力密碼攻擊](attack-simulator.md#bruteforce)
    
若要成功啟動攻擊，您使用多重要素驗證您用來執行模擬的攻擊的帳戶。此外，您必須是 Office 365 全域管理員。
  
> [!NOTE]
> 條件式存取的支援即將推出。 
  
若要存取安全性的攻擊模擬器&amp;規範中心選擇**Threat management** \> **攻擊模擬器**。
  
## <a name="before-you-begin"></a>開始之前...]

請確定您和您的組織符合攻擊模擬器的需求如下：
      
- 貴組織的電子郵件裝載於 Exchange Online。（攻擊模擬器不適用於內部部署電子郵件伺服器。）
    
- 您是 Office 365 全域管理員
    
- 您的組織使用[的 Office 365 使用者的多重要素驗證](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication&view=o365-worldwide)
 
- 您的組織具有[Office 365 威脅智慧](office-365-ti.md)與可見安全性攻擊模擬器&amp;規範中心 (移至 [ **Threat management** \> **攻擊模擬器**)<br/>![Threat management-攻擊模擬器](media/ThreatMgmt-AttackSimulator.png)

    
## <a name="display-name-spear-phishing-attack"></a>顯示名稱矛網路釣魚攻擊

網路釣魚是歸類為社交樣式攻擊的攻擊廣泛套件泛用詞。此攻擊著重於矛網路釣魚，旨在一組特定個人或組織更目標攻擊。通常具有某些偵察自訂的攻擊執行及使用會產生信任的收件者的顯示名稱，例如看起來像其電子郵件是來自組織內的主管。
  
此攻擊著重於可讓您管理者會出現訊息至郵件來自透過變更顯示名稱和來源地址。當矛網路釣魚攻擊都成功時，cybercriminals 存取使用者的認證。
  
### <a name="to-simulate-a-spear-phishing-attack"></a>若要模擬矛網路釣魚攻擊

![撰寫電子郵件內文](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
您可以製作直接在**電子郵件內文**] 欄位中本身豐富的 HTML 編輯器或與 HTML 來源搭配使用。有兩個重要納入 HTML 欄位： 
  
1. 安全性&amp;規範中心選擇**Threat management** \> **攻擊模擬器**。
    
2. 指定攻擊的有意義的行銷活動名稱或選取範本。 <br/>![網路釣魚起始頁面](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. 指定的目標收件者。這可以是個人或組織中的群組。每個目標的收件者必須有 Exchange Online 信箱的攻擊順序設為 [成功。 <br/>![收件者的選取項目](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. 設定網路釣魚電子郵件的詳細資訊。 <br/>![設定電子郵件的詳細資訊](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/>HTML 格式可為複雜或基本您 campaign 需求。為電子郵件格式是 HTML，您可以插入影像和文字來加強 believability。您必須上接收的郵件中接收的電子郵件用戶端會尋找控制項。
    
5. 指定文字**的 (Name)** ] 欄位。這是顯示在接收的電子郵件用戶端中的**顯示名稱**] 欄位。 
    
6. 指定的文字或 [**從**] 欄位。這是電子郵件地址接收的電子郵件用戶端的寄件者顯示的欄位。<br/>您可以在組織內輸入現有的電子郵件命名空間 （執行此動作會使實際解決接收的用戶端，協助非常高信任模型中的電子郵件地址），或者您也可以輸入的外部電子郵件地址。電子郵件地址所指定並沒有實際存在，但它沒有需要遵循的有效的 SMTP 位址，例如 user@domainname.extension 格式。 
  
7. 使用下拉式選取器，請選取 [以反映您必須在您攻擊內的內容類型的網路釣魚登入伺服器 URL。您可以選擇的例如文件傳遞、 技術、 薪資等提供數個佈景主題的 Url。這實際上是按一下 [要求目標的使用者的 URL。
    
8. 指定自訂登陸頁面 URL]。使用這會將使用者重新導向至您指定成功攻擊結尾處的 URL。如果您有內部認識訓練，例如，您可以指定的以下。
    
9. 指定文字的 [**主旨**] 欄位。這是做為**主體名稱**接收的電子郵件用戶端中顯示的欄位。 
    
10. 撰寫目標會收到**電子郵件內文**。 <br/>`${username}`插入電子郵件內文中的目標名稱。 <br/>`${loginserverurl}`會插入我們想要按一下目標使用者的 URL 
    
11. 選擇 [**下一步]** [**完成]** 以啟動攻擊。矛網路釣魚電子郵件訊息會傳送到您目標收件者的信箱。 
    
## <a name="password-spray-attack"></a>密碼噴灑攻擊

組織密碼噴灑攻擊通常用後 bad 動作項目已成功取得承租人的有效使用者清單。關於人員使用的一般密碼知道 bad 動作項目。這是廣泛用的攻擊、 時執行，並更困難比暴力方法偵測便宜攻擊。
  
此攻擊著重於讓您指定要對使用者的大型目標基底的一般密碼。
  
### <a name="to-simulate-a-password-spray-attack"></a>若要模擬密碼噴灑攻擊

1. 安全性&amp;規範中心選擇**Threat management** \> **攻擊模擬器**。
    
2. 指定攻擊的有意義的行銷活動名稱。
    
3. 指定的目標收件者。這可以是個人或組織中的群組。目標的收件者必須有 Exchange Online 信箱的攻擊順序設為 [成功。
    
4. 指定要用於攻擊的密碼。例如，您可以嘗試的一個一般、 相關 password 是`Fall2017`。另一個可能`Spring2018`，或`Password1`。
    
5. 選擇 [**完成**] 以啟動攻擊。 
    
## <a name="brute-force-password-attack"></a>暴力密碼攻擊

組織暴力密碼攻擊通常用後 bad 動作項目已成功取得承租人的主要使用者清單。此攻擊著重在嘗試一組的單一使用者帳戶的密碼。
  
### <a name="to-simulate-a-brute-force-password-attack"></a>若要模擬暴力密碼攻擊

1. 安全性&amp;規範中心選擇**Threat management** \> **攻擊模擬器**。
    
2. 指定攻擊的有意義的行銷活動名稱。
    
3. 指定目標收件者。目標的收件者必須有 Exchange Online 信箱的攻擊順序設為 [成功。
    
4. 指定一組要用於攻擊的密碼。您可以使用的文字 (.txt) 檔案的清單中的密碼。將文字檔不可超過 10 MB 的檔案大小。使用一個密碼每行，並確認清單中的最後一個密碼之後加上固定傳回。
    
5. 選擇 [**完成**] 以啟動攻擊。 
    
## <a name="new-features-in-attack-simulator"></a>攻擊模擬器中的新功能

新功能會被新增至攻擊模擬器。這些包括：
- **進階報表功能**。您將能看到資料按一下中郵件等等的連結以開啟攻擊模擬電子郵件訊息、 最快 （或速度最慢） 時間最快 （或速度最慢） 的時間。
- **電子郵件範本編輯器**。您可以建立您可用於未來的攻擊模擬的自訂、 可重複使用的電子郵件範本。

請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)功能開發、 功能已啟用，並什麼已經啟動。



