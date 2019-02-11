---
title: 設定您的垃圾郵件篩選原則
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
description: 基本的垃圾郵件篩選設定包括選取會被識別為垃圾郵件的郵件上所採取的動作和選擇是否要篩選以特定語言編寫或寄自特定國家或地區的郵件。
ms.openlocfilehash: 64b66f53bb56c404acefebd4fa9d211f5458f29f
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29614477"
---
# <a name="configure-your-spam-filter-policies"></a>設定您的垃圾郵件篩選原則
  
基本的垃圾郵件篩選設定包括選取會被識別為垃圾郵件的郵件上所採取的動作和選擇是否要篩選以特定語言編寫或寄自特定國家或地區的郵件。垃圾郵件篩選器原則設定會套用至內送的郵件。您可以編輯預設垃圾郵件篩選器原則來設定全公司的垃圾郵件篩選器組態及建立自訂垃圾郵件篩選器原則，然後套用至特定使用者、 群組或組織中的網域。自訂原則一律優先預設原則。您可以變更您的自訂原則執行所變更的每個自訂原則優先順序的順序。
  
> [!IMPORTANT]
> Exchange Online Protection (EOP) 獨立客戶： 根據預設，EOP 垃圾郵件篩選器將垃圾郵件偵測到的郵件傳送至每個收件者的垃圾郵件] 資料夾。不過，以確保 [**移至 [垃圾郵件] 資料夾的郵件**] 動作運作的內部部署信箱，您必須設定 Exchange 傳輸規則來偵測新增的 EOP 的垃圾郵件標頭的內部伺服器上。如需詳細資訊，請參閱[確定垃圾郵件會路由傳送至每位使用者的垃圾郵件] 資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 
  
## <a name="what-you-must-know-before-you-begin"></a>您必須知道您開始之前

預估完成時間：30 分鐘
  
您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題中的反垃圾郵件項目。 
  
如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Keyboard shortcuts in Exchange 2013**。
  
## <a name="use-the-exchange-admin-center-eac-to-configure-spam-filter-policies"></a>使用 Exchange 系統管理中心 (EAC) 來設定垃圾郵件篩選原則

1. 在 Exchange 系統管理中心 (EAC)，瀏覽至 **[保護]** \> **[垃圾郵件篩選]**。
    
2. 在 **[一般]** 頁面上執行下列其中一項動作： 
    
      - 按兩下預設原則，以編輯這個全公司的原則。
    
      - 按一下 ![加入圖示](media/ITPro-EAC-AddIcon.gif) **[新建]** 圖示，建立新的自訂垃圾郵件篩選原則，此原則可以套用到組織內的使用者、群組和網域。您也可以按兩下現有的自訂原則來編輯它們。 
    
3. 僅限自訂原則，指定此原則的名稱。或者，您也可以指定詳細的說明。您不能重新命名的預設原則。<br/><br/>附註： 當您建立原則時，在單一畫面上會出現的所有組態設定。相反地，當您編輯原則，您必須瀏覽到多個畫面。設定都是相同的兩種情況，但此程序的其餘部分說明如何編輯原則時存取這些設定。 
  
4. 在 **[垃圾郵件和大量電子郵件動作]** 頁面上，在 **[垃圾郵件]** 和 **[高信賴度垃圾郵件]** 底下，選取要為內送的垃圾郵件和大量電子郵件採取的動作。根據預設，會選取 **[將郵件移至垃圾郵件資料夾]**。其他可能的值為： 
    
      - **刪除郵件** 刪除整個郵件，包括所有附件。 
        
      - **隔離郵件**傳送至隔離而不是預定的收件者的訊息。如果您選取這個選項，請輸入 **（天） 的保留天數垃圾郵件**] 方塊中，指定要垃圾郵件隔離的期間的天數。（它將自動刪除後經過的時間。預設值為 15 天這是最大值。最小值是 1 天）。<br/><br/>秘訣： 如需如何管理員可以管理位於隔離在 EAC 中信箱的電子郵件訊息，請參閱[隔離區](quarantine.md)並[尋找和釋出隔離的郵件系統管理員身分](find-and-release-quarantined-messages-as-an-administrator.md)。> 如需如何設定垃圾郵件通知訊息傳送給使用者，請參閱[設定使用者垃圾郵件通知中 EOP](configure-end-user-spam-notifications-in-eop.md)或[設定使用者垃圾郵件通知在 Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md)。 
  
      - **將郵件移動到 [垃圾郵件] 資料夾** 將郵件傳送到指定收件者的 [垃圾郵件] 資料夾。這是兩種信賴閾值等級的預設動作。<br/><br/>**重要： Exchange Online Protection (EOP) 客戶的： 若要讓此巨集指令來搭配內部部署信箱，您必須設定兩個 Exchange 傳輸規則來偵測垃圾郵件標頭新增 EOP 的內部部署伺服器上。如需詳細資訊，請參閱[確定垃圾郵件會路由傳送至每位使用者的垃圾郵件] 資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。**
  
      - **新增 x-header**將郵件傳送給指定的收件者，但以識別為垃圾郵件的郵件將 x-header 文字新增至郵件標頭。使用此文字做為識別碼，可以選擇性地建立收件匣規則或使用下游裝置來處理郵件。預設的 x-header 文字是**設為垃圾郵件出現這個訊息**。<br/>您可以使用 [**新增此 x-header 文字**輸入的方塊自訂 x-header 文字。如果您自訂 x-header 文字，請注意下列條件： 
    
      - 如果您指定的標頭的格式\<*標頭*\>、 沒有中的不含空白\<*標頭*\>、 冒號便會附加至自訂的文字，後面加上預設文字。例如，如果您指定"這是-我-自訂-標頭"，x-header 文字會顯示為 「 這是-我-自訂-標頭： This message 看起來垃圾郵件。 」       
        
      - 如果您包括空格內自訂的標題文字，或如果您新增冒號自行 (例如"X 這是我自訂的標頭"或"X-This-is-my-custom-header:")、 x-header 文字回復成預設值為"X 此-是-垃圾郵件： This message 看起來垃圾郵件。 」
    
      - 您無法指定的標題文字的格式\<*標頭*\>：\<*值*\>。如果您這樣做，同時值之前和之後冒號都會被忽略，並改用預設 x-header 文字出現:"X 此-是-垃圾郵件： This message 看起來垃圾郵件。 」       
      
      - 請注意此 x-header 與信箱可能仍移至信箱垃圾設定信箱的垃圾郵件資料夾。您可以藉由停用此功能與 Set-mailboxjunkemailconfiguration 變更此設定。
        
      - **Prepend 主旨行文字**將郵件傳送給預定的收件者，但是前面加上**前置詞與此文字的主旨行**輸入方塊中指定的文字具有的主旨行。使用此文字做為識別碼，您可以選擇性地建立篩選或路由傳送訊息所需的規則。 
        
      - **重新導向至電子郵件地址的郵件**將郵件傳送給預定的收件者而不是指定的電子郵件地址。**重新導向至這個電子郵件地址**輸入方塊中指定的"重新導向 」 地址。<br/><br/>附註： 如需垃圾郵件信賴等級的詳細資訊，請參閱[Spam confidence levels](spam-confidence-levels.md)。 
  
5. [**大量電子郵件**，您可以選取要將大量電子郵件視為垃圾郵件臨界值。此臨界值根據郵件的大量抱怨層級。您可以選擇 1 的臨界值設定為 9，其中 1 表示大部分的大量電子郵件為垃圾郵件和 9 允許大部分的大量電子郵件傳遞。服務再執行設定的動作，例如將郵件傳送給收件者的垃圾郵件] 資料夾。請參閱[大量抱怨層級值](bulk-complaint-level-values.md)和[垃圾郵件與大量電子郵件之間的差異為何吗？](what-s-the-difference-between-junk-email-and-bulk-email.md)如需詳細資訊。 
    
6. 在 [ **封鎖清單**] 頁面上，您可以指定一律會標記為垃圾郵件的項目，例如寄件者或網域。此服務將會在符合這些項目的電子郵件上套用高信賴垃圾郵件動作。 
    
      - 將不想要的寄件者新增到「寄件者」封鎖清單。按一下 **[新增]**![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要封鎖的寄件者地址。您可以使用分號或新行區隔多個項目。按一下 [ **確定**] 回到 [ **封鎖清單**] 頁面。 
        
      - 將不想要的網域新增到「網域」封鎖清單。按一下 [ **新增**] ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要封鎖的網域。您可以使用分號或新行區隔多個項目。按一下 [ **確定**] 回到 [ **封鎖清單**] 頁面。<br/><br/>**請小心： 如果您封鎖頂層網域，最好是有可能您想要的電子郵件將會標示為垃圾郵件。** 
  
7. 在 [ **允許清單**] 頁面上，您可以指定一律會傳遞到收件匣的項目，例如寄件者或網域。來自這些項目的電子郵件不會由垃圾郵件篩選器處理。 
    
      - 將受信任的寄件者新增到寄件者允許清單。按一下 [ **新增**] ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要允許的寄件者地址。您可以使用分號或新行區隔多個項目。按一下 [確定] 回到 [ **允許清單**] 頁面。 
        
      - 將受信任的網域新增到網域允許清單。按一下 [ **新增**] ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要允許的網域。您可以使用分號或新行區隔多個項目。按一下 [確定] 回到 [ **允許清單**] 頁面。<br/><br/>**請小心： 如果允許最上層網域，很有可能您不想要的電子郵件將會傳送到收件匣。** 
  
8. 您可在 「**國際垃圾郵件**」 頁面上篩選以特定語言編寫或寄自特定國家或地區的電子郵件訊息。您可以設定最多 86 不同語言和 250 不同的區域。此服務會套用高信賴垃圾郵件設定] 動作。 
    
9. 選取 [**以下列語言撰寫的篩選器電子郵件**] 核取方塊以啟用此功能。按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後在選取項目] 對話方塊中，進行您 （支援多重選取項目） 的選擇。例如，如果您選取篩選郵件寫入在阿拉伯文 (AR)，和**隔離郵件**是您設定高信賴垃圾郵件] 動作，將隔離阿拉伯文中寫入任何郵件。按一下 [**確定]** 回到 [**國際垃圾郵件**] 窗格。 
    
10. 選取 [**從下列的國家或地區的篩選電子郵件傳送**] 核取方塊以啟用此功能。按一下 [![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後在選取項目] 對話方塊中，進行您 （支援多重選取項目） 的選擇。例如，如果您選取篩選出傳送從澳洲 (AU)，所有郵件和**隔離郵件**是您設定巨集指令的高信賴垃圾郵件，則任何郵件從澳洲傳送會被隔離。按一下 [**確定]** 回到 [**國際垃圾郵件**] 窗格。<br/><br/>如果未選取國際垃圾郵件選項，則服務預設會對以所有語言傳送以及來自所有地區的郵件執行標準垃圾郵件篩選。郵件會經過分析，並在經判定為垃圾郵件或高信賴度垃圾郵件時，套用設定的動作。 
  
11. 在 [**進階選項**] 頁面上，您可以選取**上**、**關閉**，或**測試**的每個進階垃圾郵件篩選選項。 
    
12. **在**郵件進行主動篩選根據該選項與相關聯的規則。訊息也會標示為垃圾郵件或將會有其垃圾郵件分數增加，根據哪些選項您開啟。 
    
13. **關閉** 不會對符合垃圾郵件篩選條件的郵件採取任何動作。預設會關閉所有選項。 
    
14. **測試**在符合垃圾郵件篩選條件的郵件不採取任何動作。透過之前他們會傳遞至預定的收件者新增 x-header 但已標記的郵件。此 x-header 可讓您知道哪個 ASF 選項已符合。如果您指定**測試**任何進階選項，您可以設定相符項目進行測試已啟用] 選項時要套用的下列測試模式設定： 
    
      - **無** 不對郵件採取任何測試模式動作。此為預設值。 
        
      - **新增預設測試 x-header 文字**選取此選項可將郵件傳送給指定的收件者，但也將特殊的 x-header 新增至識別為具有符合特定的進階垃圾郵件篩選選項的訊息。 
        
      - **傳送密件副本郵件到這個地址**選取此選項將郵件的密件副本傳送給您在 [輸入] 方塊中指定的電子郵件地址。 <br/><br/>如需進階垃圾郵件篩選選項，包括說明每個、 相關聯的 x-header 文字及每個選項的詳細資訊請參閱[進階垃圾郵件篩選選項](advanced-spam-filtering-asf-options.md)。 
  
15. 自訂原則只，按一下 [**套用]** 功能表項目，並再建立 [條件式規則以指定的使用者、 群組及要套用此原則的網域。他們是唯一可以建立多個條件。 
    
      - 若要選取的使用者，請選取 [**收件者**。在隨後出現的對話方塊中，從您的公司從使用者選擇清單中選取一或多個寄件者] 和 [**新增**。若要新增寄件者不在清單上，輸入其電子郵件地址，然後按一下 [**檢查名稱**。在此方塊中，您也可以使用萬用字元的多個電子郵件地址 (例如： \* @  _domainname_)。當您完成進行選取，按一下 [**確定]** 回到主畫面。 
        
      - 若要選取群組，選取**收件者的成員**。然後，在隨後出現的對話方塊中，選取或指定群組。按一下 [**確定]** 回到主畫面。 
        
      - 若要選取的網域，請選取 [**收件者的網域是**。然後，在隨後出現的對話方塊中，新增網域。按一下 [**確定]** 回到主畫面。<br/><br/>您可以建立內之規則的例外狀況。例如，您可以篩選來自但不包括在特定網域的所有網域的郵件。按一下 [**新增例外狀況**，然後再建立例外條件類似於您建立其他條件的方式。<br/><br/>將垃圾郵件原則套用至群組僅適用於**擁有郵件功能的安全群組**的支援。 
  
16. 按一下 **[儲存]**。原則設定的摘要隨即出現在右側窗格中。

> [!TIP]
>  您可以選取或清除核取方塊以啟用或停用您的自訂原則的 [**啟用**] 欄中。根據預設，會啟用所有原則。無法停用預設原則。若要刪除的自訂原則、 選取的原則，按一下 [>![刪除圖示](media/ITPro-EAC-DeleteIcon.gif)**刪除**圖示，然後確認您想要刪除之原則。無法刪除預設原則。> 自訂原則一律優先預設原則。自訂原則執行相反順序在其中建立它們 （從最舊到最新），但您可以依序按一下 [變更您的自訂原則的優先順序 （執行順序）![向上箭號圖示](media/ITPro-EAC-UpArrowIcon.gif)向上鍵及![向下箭號圖示](media/ITPro-EAC-DownArrowIcon.gif)向下箭號。具有**優先順序** **0**的原則將會執行第一筆、 後面接著**1**，則**2**，依此類推。 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a>使用遠端 PowerShell 設定垃圾郵件篩選原則

您也可以設定並套用 PowerShell 中的垃圾郵件篩選器原則。若要了解如何使用 Windows PowerShell 連線至 Exchange Online，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。若要了解如何使用 Windows PowerShell 連線至 Exchange Online Protection，請參閱[Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。
  
- [Get-HostedContentFilterPolicy](http://technet.microsoft.com/library/d510471a-dda5-4df7-b3f8-2ee7a1948436.aspx) 檢視您的垃圾郵件篩選設定。 
    
- [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) 編輯您的垃圾郵件篩選設定。 
    
- [New-HostedContentFilterPolicy](http://technet.microsoft.com/library/4d15128d-9e16-42a1-8ac5-36f07d4bbbf0.aspx) 建立新的自訂垃圾郵件篩選原則。 
    
- [Remove-HostedContentFilterPolicy](http://technet.microsoft.com/library/9fe1fe03-8f83-41e3-9bf5-084a392784d6.aspx) 刪除新的自訂垃圾郵件篩選原則。 
    
若要將自訂垃圾郵件篩選原則套用至使用者、群組和 (或) 網域，請使用 [New-HostedContentFilterRule](http://technet.microsoft.com/library/2df13ba9-1eb0-4da3-bd72-a79d5fa15e26.aspx) Cmdlet (建立可套用至自訂原則的新篩選規則) 或 [Set-HostedContentFilterRule](http://technet.microsoft.com/library/ba259260-ffd3-43f3-8ef4-9d8659679d02.aspx) Cmdlet (編輯可套用至自訂原則的現有篩選規則)。使用 [Enable-HostedContentFilterRule](http://technet.microsoft.com/library/354ece28-dcde-4b5f-88ed-475115e7ea78.aspx) Cmdlet或 [Disable-HostedContentFilterRule](http://technet.microsoft.com/library/c1f8dafc-ef5d-47e3-b0fb-71a88e145fc5.aspx) Cmdlet 可以啟用或停用對原則套用的規則。 
  
## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確保已針對垃圾郵件進行適當偵測和採取行動，可以透過服務傳送 GTUBE 訊息。GTUBE 與 EICAR 防毒測試檔案類似，GTUBE 提供了一項測試，您可以用來確認服務正在偵測進入的垃圾郵件。GTUBE 訊息應該一律被垃圾郵件篩選器偵測為垃圾郵件，且對郵件執行的動作應該符合您進行的設定。
  
請在郵件訊息中，將下列 GTUBE 文字包含在單一行上，不加任何空格或換行：
  
```
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="fine-tuning-your-spam-filter-policy-to-prevent-false-positives-and-false-negatives"></a>調整您的垃圾郵件篩選原則，以避免誤判和漏報

如果想要使用積極的垃圾郵件篩選方法，您可以啟用進階的垃圾郵件篩選選項。如需套用至整個組織的一般垃圾郵件設定，請參閱[使用安全清單或其他技術防止誤判電子郵件標示為垃圾郵件](https://go.microsoft.com/fwlink/p/?LinkId=534224)，或[使用 Office 365 垃圾郵件篩選器封鎖垃圾郵件以避免漏報問題](https://go.microsoft.com/fwlink/p/?LinkId=534225)。如果您有系統管理員層級的控制權，且您想要避免誤判或漏報，這些內容很有幫助。
   
## <a name="for-more-information"></a>如需詳細資訊
<a name="sectionSection6"> </a>

[設定連線篩選原則](configure-the-connection-filter-policy.md)
  
[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)
  
[隔離](quarantine.md)
  
[使用安全清單或其他技術防止誤判電子郵件標示為垃圾郵件](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件以避免誤判正常](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

