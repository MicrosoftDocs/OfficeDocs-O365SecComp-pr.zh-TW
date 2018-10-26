---
title: 設定連線篩選原則
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
description: 若要確定未被封鎖從您信任的人員所傳送的電子郵件，您可以使用連線篩選原則建立允許清單中，也稱為安全寄件者清單中，您信任的 IP 位址。您也可以建立封鎖的寄件者清單。
ms.openlocfilehash: 2f8ec3d01de4358d7394c68d0efae9222db08282
ms.sourcegitcommit: a07b91723bae9ecee2cb092bfbc5b208b30b11a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/25/2018
ms.locfileid: "25793558"
---
# <a name="configure-the-connection-filter-policy"></a>設定連線篩選原則
 
充分運用我們要有朋友與業務合作夥伴我們信任。它可以是什麼在垃圾郵件] 資料夾中找到這些電子郵件或甚至封鎖完全由垃圾郵件篩選器。如果您想要確保不會封鎖從您信任的人員所傳送的電子郵件、 您可用來建立允許清單中，也稱為安全寄件者] 清單中，連線篩選原則的 IP 位址達到該您信任。您也可以從已知的垃圾郵件、 不屬於想要接收電子郵件訊息從通常是建立封鎖的寄件者清單中，這是 IP 位址清單。
  
 適用於整個組織的多個垃圾郵件設定，看看[如何協助確保郵件未標示為垃圾郵件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[封鎖郵件垃圾郵件與 Office 365 垃圾郵件篩選避免 false 負數的問題](https://go.microsoft.com/fwlink/p/?LinkId=534225)。如果您有管理員層級控制與您想要防止誤判或 false 負片，這些是很有幫助。
  
下列影片顯示連線篩選原則的組態步驟：
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

- 預估所需時間：15 分鐘
    
- 您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題中的 「 反垃圾郵件 」 項目。 
    
- 若要取得您想要允許或封鎖其郵件的寄件者的 IP 位址，您可以檢查網際網路郵件標頭。尋找[反垃圾郵件郵件標頭](anti-spam-message-headers.md)中所述的 CIP 標頭。如需如何在各種電子郵件用戶端檢視郵件標頭資訊，請參閱 ＜[郵件標頭 Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583)。 
    
- 拒絕來自 IP 位址在 IP 封鎖清單上傳送的電子郵件、 未標示為垃圾郵件和任何其他篩選會發生。
    
- 您也可以透過遠端 PowerShell 執行下列連線篩選程序。使用[Get HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx)指令程式來檢閱您的設定和[Set-hostedconnectionfilterpolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx)編輯您的連線篩選原則設定。若要了解如何使用 Windows PowerShell 連線至 Exchange Online Protection，請參閱[Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。若要了解如何使用 Windows PowerShell 連線至 Exchange Online，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>使用 EAC 編輯預設連線篩選原則
<a name="sectionSection1"> </a>

您可以在 Exchange 系統管理中心 (EAC) 編輯連線篩選原則，以建立 IP 允許清單或 IP 封鎖清單。連線篩選原則設定僅適用於輸入郵件。
  
1. 在 Exchange 系統管理中心 (EAC)，瀏覽至 **[保護]** \> **[連線篩選器]**，然後連按兩下預設原則。
    
2. 按一下 [連線篩選]**** 功能表項目，然後建立所需的清單：IP 允許清單、IP 封鎖清單或兩者。 
    
    若要建立這些清單，請按一下![加入圖示](media/ITPro-EAC-AddIcon.gif)。在後續對話方塊中，指定 IP 位址或位址範圍，然後按一下 **[確定]**。重複此程序來新增其他位址。(新增 IP 位址後，您也可以編輯或移除 IP 位址。)
    
    > [!NOTE]
    >  如果您將 IP 位址新增至兩個清單時，是否允許從該 IP 位址傳送的電子郵件。 

    在其中？ （\d{3}） 是從 0 到 255 的數字格式 nnn.nnn.nnn.nnn 指定 IPV4 IP 位址。您也可以在其中 rr 是從 24 到 32 的數字格式 nnn.nnn.nnn.nnn/rr 中指定無網域間路由選擇 (CIDR) 範圍。若要指定 24 至 32 範圍的範圍，請參閱 ＜[其他考量時設定 IP 允許清單](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists)。 

    您可以指定 1273年個項目，其中項目是單一 IP 位址或 CIDR 範圍的 IP 位址從/24 至/32 的最大值。> 如果您正在傳送 TLS 加密訊息，IPv6 位址與位址範圍不支援。 
  
3. （選用） 選取 [**啟用安全清單**] 核取方塊以避免遺失某些已知寄件者的電子郵件。如何？Microsoft 訂閱的受信任的寄件者的協力廠商來源。使用此安全清單表示這些受信任的寄件者未誤標示為垃圾郵件。建議您選取這個選項，因為它應該減少誤判 （歸類為垃圾郵件的良好郵件） 的數目，您會收到。 
    
4. 按一下 **[儲存]**。預設原則設定的摘要隨即出現在右側窗格中。
    
## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>設定 IP 允許清單時的其他考量
<a name="bkmk_addtionalconsiderationswhenconfiguringipallowlists"> </a>

以下是設定 IP 允許清單時需要考慮或應該注意的其他事項。
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>指定超出建議範圍的 CIDR 範圍

若要指定 /23 從/1 CIDR IP 位址範圍，您必須建立以設定垃圾郵件信賴等級 (SCL) 的 IP 位址範圍的郵件流程規則**略過垃圾郵件篩選**（這表示從收到此 IP 位址範圍內的所有訊息都設為"不垃圾郵件 」） 並無其他篩選服務執行)。不過，如果任何這些 IP 位址會出現在 Microsoft 的專屬封鎖的任何列出或在任何我們協力廠商封鎖清單，這些訊息仍然會被封鎖。因此強烈建議您使用/24 至/32 的 IP 位址範圍。 
  
若要建立此郵件流程規則，請執行下列步驟。
  
1. 在 EAC 中，瀏覽至 **[郵件流程]** \> **[規則]**。
    
2. 按一下 ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 **[建立新的規則]**。
    
3. 命名規則，然後按一下 **[更多選項]**。
    
4. 在 **[套用此規則情況]** 下，選取 **[寄件者]**，然後選擇 **[IP 位址在任何這些範圍中或完全符合]**。
    
5. 在 [**指定 IP 位址**，請指定 IP 位址範圍，按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後按一下 [**確定]**。
    
6. 在 **[執行下列動作]** 方塊下，選擇 **[修改訊息屬性]**，再選擇 **[設定垃圾郵件信賴等級 (SCL)]** 來設定動作。在 **[指定 SCL]** 方塊中，選取 **[略過垃圾郵件篩選]**，然後按一下 **[確定]**。
    
7. 如果您想要您可以讓選取項目稽核規則、 測試規則、 特定時間期間啟動規則和其他選取項目。建議您測試一段之前您強制執行規則。[郵件流程的程序規則在 Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)包含這些選項的詳細資訊。 
    
8. 按一下 [**儲存**] 以儲存規則。此規則會出現在清單中的規則。 
    
建立並強制執行規則後，服務略過您指定的 IP 位址範圍的垃圾郵件篩選。
  
### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>針對特定網域設定 IP 允許清單例外狀況

一般而言，建議將您認為安全的所有網域的 IP 位址 (或 IP 位址範圍) 新增至 IP 允許清單。不過，如果不要將 IP 允許清單項目套用至所有網域，您可以建立排除特定網域的傳輸規則。 
  
例如，假設您有三個網域：ContosoA.com、ContosoB.com 和 ContosoC.com，而您想要新增 IP 位址 (為了簡單起見，我們用 1.2.3.4)，並僅針對網域 ContosoB.com 來略過篩選。您可以建立 1.2.3.4 的 IP 允許清單，以針對所有網域將垃圾郵件信賴等級 (SCL) 設定為 -1 (表示歸類為非垃圾郵件)。接著，您可以建立一個傳輸規則，以針對 ContosoB.com 以外的所有網域將 SCL 設定為 0。這會導致針對與此 IP 位址相關聯的所有網域 (在規則中列為例外的 ContosoB.com 除外) 來重新掃描郵件。ContosoB.com 的 SCL 仍為 -1 (表示略過篩選)，然而 ContosoA.com 和 ContosoC.com 的 SCL 為 0 (表示將由內容篩選器進行重複掃描)。
  
若要執行此動作，請執行下列步驟：
  
1. 在 EAC 中，瀏覽至 **[郵件流程]** \> **[規則]**。
    
2. 按一下 ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 **[建立新的規則]**。
    
3. 命名規則，然後按一下 **[更多選項]**。
    
4. 在 **[套用此規則情況]** 下，選取 **[寄件者]**，然後選擇 **[IP 位址在任何這些範圍中或完全符合]**。
    
5. 在 [**指定 IP 位址**] 方塊中指定的 IP 位址或 IP 位址範圍新增您輸入的 IP 允許清單中，按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後按一下 [**確定]**。
    
6. 在 **[執行下列動作]** 下，選擇 **[修改訊息屬性]**，再選擇 **[設定垃圾郵件信賴等級 (SCL)]** 來設定動作。在 **[指定 SCL]** 方塊中，選取 **[0]**，然後按一下 **[確定]**。
    
7. 按一下 **[新增例外狀況]**，在 **[除非]** 下，選取 **[寄件者]**，然後選擇 **[網域是]**。 
    
8. 在**指定的網域**] 方塊中輸入您要略過垃圾郵件篩選功能，例如**contosob.com**的網域。按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)將移至的片語清單。如果您想要新增其他的網域為例外狀況，並完成時按一下 [**確定]** 重複此步驟。 
    
9. 如果您想要您可以讓選取項目稽核規則、 測試規則、 特定時間期間啟動規則和其他選取項目。建議您測試一段之前您強制執行規則。[郵件流程的程序規則在 Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)包含這些選項的詳細資訊。 
    
10. 按一下 [**儲存**] 以儲存規則。此規則會出現在清單中的規則。 
    
建立並強制執行規則後，系統就只會針對您輸入的例外網域，對您指定的 IP 位址或 IP 位址範圍略過垃圾郵件篩選。
  
## <a name="new-to-office-365"></a>初次使用 Office 365 嗎？
<a name="sectionSection3"> </a>

||
|:-----|
|![LinkedIn Learning 的短圖示](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **初次使用 Office 365？**         探索 LinkedIn Learning 提供的 **Office 365 admins and IT pros** 免費影片課程。 |
   
## <a name="for-more-information"></a>如需詳細資訊
<a name="sectionSection4"> </a>

[安全寄件者和封鎖寄件者清單在 Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)
  
[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)
  
[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)
  
[如何協助確保郵件不會標示為垃圾郵件](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件以避免誤判正常](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

