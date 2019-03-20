---
title: 設定連線篩選原則
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
description: 若要確定，不會封鎖從您信任的人員傳送電子郵件，您可以使用連線篩選原則來建立一份允許清單，也就是安全的寄件者清單中，您信任的 IP 位址。 您也可以建立的封鎖寄件者清單。
ms.openlocfilehash: 5ca6ad6721ac03e5ae62b40dda219671bde3e1c1
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693542"
---
# <a name="configure-the-connection-filter-policy"></a>設定連線篩選原則
 
大多數的人都有信任的朋友和企業夥伴。 發現這些人寄送的電子郵件出現在垃圾郵件資料夾或甚至遭到垃圾郵件篩選器整個封鎖，會令人感覺不便。 如果您想要確定不會封鎖從您信任的人員傳送電子郵件，您可用來建立一份允許清單，也就是安全的寄件者] 清單中，連線篩選原則的 IP 位址，您信任。 您也可以建立不想收到電子郵件的封鎖寄件者清單，其中列出一般來自已知濫發垃圾郵件者的 IP 位址。
  
 如需更多套用到整個組織的垃圾郵件設定，請參閱[如何協助確保郵件不會標示為垃圾郵件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[利用 Office 365 垃圾郵件篩選器封鎖電子郵件的垃圾郵件，以避免誤判正常問題](https://go.microsoft.com/fwlink/p/?LinkId=534225)。 如果您有系統管理員層級的控制權，且您想要避免誤判或漏報，這些內容很有幫助。
  
下列影片顯示連線篩選原則的組態步驟：
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

- 預估完成時間：15 分鐘
    
- 您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要的權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題中的 「 反垃圾郵件 」 項目。 
    
- 若要取得寄件者的 IP 位址以允許或封鎖其郵件，您可以檢查郵件的 Internet 標頭。 如＜[反垃圾郵件訊息標頭](anti-spam-message-headers.md)＞所述尋找 CIP 標頭。 如需如何在各種電子郵件用戶端中檢視郵件標頭資訊，請參閱 <<c0>郵件標頭分析器。 
    
- 從 IP 封鎖清單上的 IP 位址傳送的電子郵件遭到拒絕，未標示為垃圾郵件，並沒有其他的篩選，就會發生。
    
- 下列連線篩選程序也可以透過遠端 PowerShell 執行。 使用 [Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) 指令程式可以檢閱您的設定，使用 [Set-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) 則可以編輯連線篩選原則設定。 若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱[Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。 若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>使用 EAC 編輯預設連線篩選原則
<a name="sectionSection1"> </a>

您可以在 Exchange 系統管理中心 (EAC) 編輯連線篩選原則，以建立 IP 允許清單或 IP 封鎖清單。連線篩選原則設定僅適用於輸入郵件。
  
1. 在 Exchange 系統管理中心 (EAC)，瀏覽至 **[保護]** \> **[連線篩選器]**，然後連按兩下預設原則。
    
2. Click the **Connection filtering** menu item and then create the lists you want: an IP Allow list, an IP Block list, or both. 
    
    若要建立這些清單，請按一下![加入圖示](media/ITPro-EAC-AddIcon.gif)。在後續對話方塊中，指定 IP 位址或位址範圍，然後按一下 **[確定]**。重複此程序來新增其他位址。(新增 IP 位址後，您也可以編輯或移除 IP 位址。)
    
    > [!NOTE]
    >  如果您將 IP 位址新增至兩個清單時，會允許來自該 IP 位址傳送的電子郵件。 

    指定其中 nnn 是 0 到 255 的數字格式以 IPV4 IP 位址。 您也可以用 nnn.nnn.nnn.nnn/rr 格式來指定無類別網域間路由選擇 (CIDR) 範圍，其中 rr 是 24 到 32 的數字。 若要指定 24 到 32 以外的範圍，請參閱 [設定 IP 允許清單時的其他考量](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists)。 

    您最多可以指定 1273 個項目，一個項目就是單一 IP 位址，或 IP 位址從 /24 至 /32 的 CIDR 範圍。 如果您正在傳送 TLS 加密訊息 >，IPv6 位址與位址範圍不受支援。 
  
3. 或者，選取 **[啟用安全清單]** 核取方塊避免某些已知寄件者的電子郵件遺失。 怎麼做？ Microsoft 會訂閱協力廠商來源的信任寄件者。 使用這份安全清單表示不會將信任的寄件者錯誤標記為垃圾郵件。 我們建議您選取此選項，因為它應該減少誤判 （歸類為垃圾郵件的良好郵件） 的數目，您會收到。 
    
4. 按一下 **[儲存]**。預設原則設定的摘要隨即出現在右側窗格中。
    
## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>設定 IP 允許清單時的其他考量
<a name="bkmk_addtionalconsiderationswhenconfiguringipallowlists"> </a>

以下是設定 IP 允許清單時需要考慮或應該注意的其他事項。
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>指定超出建議範圍的 CIDR 範圍

若要指定 /23 從/1 CIDR IP 位址範圍，您必須建立郵件流程規則的運作上設定垃圾郵件信賴等級 (SCL) 的 IP 位址範圍**略過垃圾郵件篩選**（亦即從收到此 IP 位址範圍內的所有郵件都都會設定為 「 非垃圾郵件 」） 和任何其他的篩選服務執行)。 However, if any of these IP addresses appear on any of Microsoft's proprietary block lists or on any of our third-party block lists, these messages will still be blocked. 因此強烈建議您使用/24 至/32 的 IP 位址範圍。 
  
若要建立此郵件流程規則，請執行下列步驟。
  
1. 在 EAC 中，瀏覽至 **[郵件流程]** \> **[規則]**。
    
2. 按一下 ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 **[建立新的規則]**。
    
3. 命名規則，然後按一下 **[更多選項]**。
    
4. 在 **[套用此規則情況]** 下，選取 **[寄件者]**，然後選擇 **[IP 位址在任何這些範圍中或完全符合]**。
    
5. 在 [**指定 IP 位址**，請指定 IP 位址範圍，按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後按一下 [**確定]**。
    
6. 在 **[執行下列動作]** 方塊下，選擇 **[修改訊息屬性]**，再選擇 **[設定垃圾郵件信賴等級 (SCL)]** 來設定動作。在 **[指定 SCL]** 方塊中，選取 **[略過垃圾郵件篩選]**，然後按一下 **[確定]**。
    
7. 您也可以視需要選取稽核規則、測試規則、在特定期間啟動規則等等選項。 施行規則之前，建議先測試規則一段時間。 [程序的郵件流程規則在 Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)包含這些選項的詳細資訊。 
    
8. 按一下 [**儲存**] 以儲存規則。 此規則會出現在規則清單。 
    
建立並強制執行規則後，此服務會略過垃圾郵件篩選，以便您所指定的 IP 位址範圍。
  
### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>針對特定網域設定 IP 允許清單例外狀況

一般而言，建議將您認為安全的所有網域的 IP 位址 (或 IP 位址範圍) 新增至 IP 允許清單。 不過，如果您不想要套用至所有網域 IP 允許清單項目，您可以建立排除特定網域的郵件流程規則 （也稱為傳輸規則）。 
  
例如，假設您有三個網域：ContosoA.com、ContosoB.com 和 ContosoC.com，而您想要新增 IP 位址 (為了簡單起見，我們用 1.2.3.4)，並僅針對網域 ContosoB.com 來略過篩選。 您可以建立 1.2.3.4 的 IP 允許清單，以針對所有網域將垃圾郵件信賴等級 (SCL) 設定為 -1 (表示歸類為非垃圾郵件)。 然後，您可以建立郵件流程規則，將以針對 ContosoB.com 以外的所有網域的 SCL 設定為 0。 這會導致針對與此 IP 位址相關聯的所有網域 (在規則中列為例外的 ContosoB.com 除外) 來重新掃描郵件。 ContosoB.com 的 SCL 仍為 -1 (表示略過篩選)，然而 ContosoA.com 和 ContosoC.com 的 SCL 為 0 (表示將由內容篩選器進行重複掃描)。
  
若要執行此動作，請執行下列步驟：
  
1. 在 EAC 中，瀏覽至 **[郵件流程]** \> **[規則]**。
    
2. 按一下 ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 **[建立新的規則]**。
    
3. 命名規則，然後按一下 **[更多選項]**。
    
4. 在 **[套用此規則情況]** 下，選取 **[寄件者]**，然後選擇 **[IP 位址在任何這些範圍中或完全符合]**。
    
5. 在 [**指定 IP 位址**] 方塊中，指定的 IP 位址或 IP 位址範圍，您輸入的 IP 允許清單中，按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後按一下 [**確定]**。
    
6. 在 **[執行下列動作]** 下，選擇 **[修改訊息屬性]**，再選擇 **[設定垃圾郵件信賴等級 (SCL)]** 來設定動作。在 **[指定 SCL]** 方塊中，選取 **[0]**，然後按一下 **[確定]**。
    
7. 按一下 **[新增例外狀況]**，在 **[除非]** 下，選取 **[寄件者]**，然後選擇 **[網域是]**。 
    
8. 在 **[指定網域]** 方塊中，輸入您要略過垃圾郵件篩選的網域，例如 **contosob.com**。 按一下 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)將其移至片語清單。 如果要新增其他網域當作例外狀況，請重複此步驟，完成時按一下 **[確定]**。 
    
9. 您也可以視需要選取稽核規則、測試規則、在特定期間啟動規則等等選項。 施行規則之前，建議先測試規則一段時間。 [程序的郵件流程規則在 Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)包含這些選項的詳細資訊。 
    
10. 按一下 [**儲存**] 以儲存規則。 此規則會出現在規則清單。 
    
建立並強制執行規則後，系統就只會針對您輸入的例外網域，對您指定的 IP 位址或 IP 位址範圍略過垃圾郵件篩選。
  
## <a name="new-to-office-365"></a>第一次使用 Office 365？
<a name="sectionSection3"> </a>

||
|:-----|
|![LinkedIn Learning 的短圖示](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **初次使用 Office 365？**         探索 LinkedIn Learning 提供的 **Office 365 admins and IT pros** 免費影片課程。 |
   
## <a name="for-more-information"></a>相關資訊
<a name="sectionSection4"> </a>

[安全寄件者和封鎖的寄件者會列出在 Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)
  
[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)
  
[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)
  
[如何協助確保郵件不會標示為垃圾郵件](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件以避免誤判正常](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

