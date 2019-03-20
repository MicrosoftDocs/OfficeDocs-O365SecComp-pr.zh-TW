---
title: 設定您的垃圾郵件篩選原則
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 基本的垃圾郵件篩選設定包含選取的郵件，會被識別為垃圾郵件所採取的動作，然後選擇是否要篩選以特定語言撰寫或從特定國家或地區傳送的郵件。
ms.openlocfilehash: 9cfccc3602758de2426940cea1c6abd91871d7c2
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693472"
---
# <a name="configure-your-spam-filter-policies"></a>設定您的垃圾郵件篩選原則
  
基本的垃圾郵件篩選設定包含選取的郵件，會被識別為垃圾郵件所採取的動作。 垃圾郵件篩選原則設定會套用至內送的郵件。 您可以編輯預設垃圾郵件篩選原則來設定您的全公司的垃圾郵件篩選設定和建立自訂垃圾郵件篩選原則，並再將它們套用至特定使用者、 群組或組織中的網域。 自訂原則的優先順序永遠高於預設原則。 您可以變更自訂原則執行藉由變更的每個自訂原則; 優先順序的順序不過，如果多個原則符合的準則集，將套用的最高優先順序原則。 
  
> [!IMPORTANT]
> Exchange Online Protection (EOP) 獨立客戶： 根據預設，EOP 垃圾郵件篩選垃圾郵件偵測到郵件傳送至每個收件者的垃圾郵件] 資料夾。 不過，為了確保**移至垃圾郵件] 資料夾的郵件**巨集指令適用於內部部署信箱，您必須設定 Exchange 郵件流程規則 （也稱為傳輸規則） 來新增您的內部伺服器來偵測垃圾郵件標頭EOP。 如需詳細資訊，請參閱[確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 
  
## <a name="what-you-must-know-before-you-begin"></a>您必須知道您開始之前

預估完成時間：30 分鐘
  
您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要的權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題中的反垃圾郵件項目。 
  
如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。
  
## <a name="use-the-security--compliance-center-scc-to-configure-spam-filter-policies"></a>使用安全性 & 合規性中心 (SCC) 來設定垃圾郵件篩選原則

1. 在 [安全性 & 合規性中心 (SCC) 中，瀏覽至 [**威脅管理，** \> **原則** \> **反垃圾郵件**。
    
2. 執行**反垃圾郵件設定**] 頁面上的下列其中一項： 
    
      - 檢閱預設的全公司原則，[一般設定] 下。
    
      - 按一下 [**自訂**] 索引標籤上的 [、 將**自訂設定**選取器**上**，並按一下 [![加入圖示](media/ITPro-EAC-AddIcon.gif)**建立原則**] 按鈕，以建立新的自訂垃圾郵件篩選器原則可以套用至使用者、 群組和您組織中的網域。 您也可以按兩下現有的自訂原則來編輯它們。 
    
3. 只針對自訂原則，指定原則的名稱。 或者，您也可以指定更詳細的描述。 您無法重新命名預設原則。<br/><br/>附註： 當您建立原則時，在單一畫面上會出現的所有組態設定。 相反地，當您編輯原則時，您必須瀏覽多個畫面。 設定是在任一情況中，相同，但此程序的其餘部分說明如何在編輯原則時存取這些設定。 
  
4. 在 **[垃圾郵件和大量電子郵件動作]** 頁面上，在 **[垃圾郵件]** 和 **[高信賴度垃圾郵件]** 底下，選取要為內送的垃圾郵件和大量電子郵件採取的動作。根據預設，會選取 **[將郵件移至垃圾郵件資料夾]**。其他可能的值為： 
    
      - **刪除郵件：** 會刪除整個郵件，包括所有附件。 
        
      - **隔離郵件：** 傳送至隔離而不是預定的收件者的訊息。 If you select this option, in the **Retain spam for (days)** input box, specify the number of days during which the spam message will be quarantined. (It will automatically be deleted after the time elapses. The default value is 15 days which is the maximum value. The minimum value is 1 day.)<br/><br/>秘訣： 如需系統管理員可以如何管理位於隔離信箱在 EAC 中的電子郵件訊息的資訊，請參閱[隔離](quarantine.md)和[身分找到並釋放被隔離的郵件，身為系統管理員](find-and-release-quarantined-messages-as-an-administrator.md)。 > 如需如何設定垃圾郵件通知訊息傳送給使用者，請參閱[設定使用者垃圾郵件通知中 EOP](configure-end-user-spam-notifications-in-eop.md)或[設定使用者垃圾郵件通知中 Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md)。 
  
      - **將郵件移至垃圾郵件] 資料夾：** 會將郵件傳送至指定的收件者的垃圾郵件資料夾。 這是兩種信賴閾值等級的預設動作。 <br/><br/>**重要**： 針對 Exchange Online Protection (EOP) 客戶： 為了讓此動作可搭配內部部署信箱，您必須設定兩個 Exchange 郵件流程規則，在您的內部部署伺服器，以偵測 EOP 所新增的垃圾郵件標頭。 如需詳細資訊，請參閱[確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。
  
      - **新增 X 標頭：** 將郵件傳送給指定的收件者，但將 X 標頭文字新增至郵件標頭中，以識別為垃圾郵件訊息。 使用這段文字做為識別碼，您可以選擇性地建立收件匣規則或下游裝置對郵件採取動作。 The default X-header text is **This message appears to be spam**.<br/>您可以使用 [**新增此 x-header 文字**] 輸入的方塊自訂 x-header 文字。 如果您自訂 x-header 文字，請留意下列條件： 
    
      - 如果您指定的標頭格式\<*標頭*\>，其中內沒有空格\<*標頭*\>、 冒號將要新增至自訂的文字，後面接著預設文字。       例如，如果您指定 「 此-是-「 我的自訂-標頭 」，x-header 文字會顯示為 「 此是-「 我的自訂-標頭： 這封郵件看起來垃圾郵件。 」 
        
      - 如果自訂標頭文字內包含空格，或者您加上冒號自行 (例如 「 X 這是我自訂標頭 」 或 「 X-This-is-my-custom-header: 」)，x-header 文字會還原成預設值為 「 X-此-是-垃圾郵件： 這封郵件看起來垃圾郵件。 」
    
      - 您無法指定的標頭文字格式\<*標頭*\>:\<*值*\>。       如果您這麼做時，兩者的值前面和後面冒號都會被忽略，以及預設 X 標頭文字會出現在改為:"X-此-是-垃圾郵件： 這封郵件看起來垃圾郵件。 」 
      
      - 請注意此 X 標頭與郵件可能仍移至信箱垃圾郵件資料夾，因為信箱垃圾郵件組態。 您可以變更此設定來停用使用 Set-mailboxjunkemailconfiguration 這項功能。
        
      - **前面加上主旨行文字：** 將郵件傳送給預定的收件者，但前面加上主旨行使用**與此文字的主旨行字首**的輸入方塊中指定的文字。 使用這段文字做為識別碼，您可以選擇性地建立篩選或視路由傳送郵件的規則。 
        
      - **重新導向郵件給電子郵件地址：** 會將郵件傳送給預定的收件者而非指定的電子郵件地址。 **重新導向到這個電子郵件地址**輸入方塊中指定的 「 重新導向 」 地址。 <br/><br/>附註： 如需垃圾郵件信賴等級的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。 
  
5. 在 **[大量電子郵件]** 底下，您可以選取要將大量電子郵件視為垃圾郵件的臨界值。 這個臨界值是根據訊息的大量抱怨層級。 您可以選擇 1 的臨界值設定為 9，其中 1 表示大部分的大量電子郵件為垃圾郵件，而 9 允許傳遞最大量電子郵件。 服務則會執行已設定的動作 (例如將郵件傳送至收件者的 [垃圾郵件] 資料夾)。 請參閱[大量抱怨層級值](bulk-complaint-level-values.md)和[垃圾郵件和大量電子郵件之間的差異為何？](what-s-the-difference-between-junk-email-and-bulk-email.md)如需詳細資訊。 
    
6. 在 [ **封鎖清單**] 頁面上，您可以指定一律會標記為垃圾郵件的項目，例如寄件者或網域。此服務將會在符合這些項目的電子郵件上套用高信賴垃圾郵件動作。 
    
      - 將不想要的寄件者新增到「寄件者」封鎖清單。按一下 **[新增]**![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要封鎖的寄件者地址。您可以使用分號或新行區隔多個項目。按一下 [ **確定**] 回到 [ **封鎖清單**] 頁面。 
        
      - 將不想要的網域新增到「網域」封鎖清單。按一下 [ **新增**] ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要封鎖的網域。您可以使用分號或新行區隔多個項目。按一下 [ **確定**] 回到 [ **封鎖清單**] 頁面。<br/><br/>**注意： 如果您封鎖頂層網域，它可能是您想要的電子郵件會被標示為垃圾郵件。** 
  
7. 在 [**允許清單**] 頁面上，您可以指定一律會傳遞到收件匣的項目，例如寄件者或網域。來自這些項目的電子郵件不會由垃圾郵件篩選器處理。 
    
      - 將受信任的寄件者新增到寄件者允許清單。按一下 [ **新增**] ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要允許的寄件者地址。您可以使用分號或新行區隔多個項目。按一下 [確定] 回到 [ **允許清單**] 頁面。 
        
      - 將受信任的網域新增到網域允許清單。按一下 [ **新增**] ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要允許的網域。您可以使用分號或新行區隔多個項目。按一下 [確定] 回到 [ **允許清單**] 頁面。<br/><br/>**注意： 如果您允許頂層網域，很可能不想要的電子郵件將會傳遞至收件匣。** 
  
8. [**國際垃圾郵件**] 頁面上，您可以篩選以特定語言撰寫或從特定國家或地區傳送的電子郵件訊息。 您可以設定高達 86 種不同語言和 250 個不同地區。 此服務會套用高信賴度垃圾郵件的 [設定] 動作。 
    
9. Select the **Filter email messages written in the following languages** check box to enable this functionality. 按一下 [![加入圖示](media/ITPro-EAC-AddIcon.gif)，並接著，在選取項目] 對話方塊中，選擇 （支援多重選取項目）。 例如，如果您選取來篩選郵件撰寫在阿拉伯文 (AR)，和**隔離郵件**是您設定的動作，高信賴度垃圾郵件，以阿拉伯文撰寫任何郵件會被隔離。 Click **ok** to return to the **International Spam** pane. 
    
10. Select the **Filter email messages sent from the following countries or regions** check box to enable this functionality. 按一下 [![加入圖示](media/ITPro-EAC-AddIcon.gif)，並接著，在選取項目] 對話方塊中，選擇 （支援多重選取項目）。 例如，如果您選取篩選所有郵件傳送從澳洲 (AU)，和**隔離郵件**是從澳洲傳送您設定的動作的高信賴垃圾郵件，則任何郵件會被隔離。 Click **ok** to return to the **International Spam** pane. <br/><br/>如果未選取國際垃圾郵件選項，則服務預設會對以所有語言傳送以及來自所有地區的郵件執行標準垃圾郵件篩選。郵件會經過分析，並在經判定為垃圾郵件或高信賴度垃圾郵件時，套用設定的動作。 
  
11. 在 [**進階選項**] 頁面上，您可以選取**上**、**關閉**，或**測試**的每個進階垃圾郵件篩選選項。 
    
12. **在**根據與該選項關聯的規則來積極地篩選的郵件。 視您開啟的選項而定，郵件會標示為垃圾郵件，或是增加其垃圾郵件分數。 
    
13. **關閉** 不會對符合垃圾郵件篩選條件的郵件採取任何動作。 預設會關閉所有選項。 
    
14. **測試** 不會對符合垃圾郵件篩選條件的郵件採取任何動作。 不過，郵件可以標記新增 X 標頭，然後才傳遞給預定的收件者。 此 x-header 可讓您知道符合哪個 ASF 選項。 如果您為任何進階選項指定 **[測試]**，則可以設定下列測試模式設定，以便在比對啟用測試之選項時套用： 
    
      - **無** 不對郵件採取任何測試模式動作。 此為預設值。 
        
      - **新增預設的測試 x-header 文字**選取此選項會將郵件傳送給指定的收件者，但也會新增到訊息，以識別為符合特定的進階垃圾郵件篩選選項的特殊 X 標頭。 
        
      - **傳送密件副本郵件到這個地址**選取此選項會傳送郵件的密件副本到輸入方塊中指定的電子郵件地址。 <br/><br/>如需進階垃圾郵件篩選選項，包括每個與相關聯的 X 標頭文字及各選項的相關說明請參閱 <<c0>進階垃圾郵件篩選選項。 
  
15. 針對自訂原則只，按一下 [**套用至**功能表項目，然後建立條件式規則，以指定使用者、 群組及要套用此原則的網域。 如果它們都是唯一，您可以建立多個條件。 
    
      - 若要選取使用者，請選取 **[收件者是]**。 在後續的對話方塊中，從您的公司，從使用者選擇器清單中，選取一或多個寄件者，然後按一下 [**新增**。 若要新增寄件者不在清單上，輸入其電子郵件地址，然後按一下 [**檢查名稱**。 在此方塊中，您也可以使用萬用字元來代表多個電子郵件地址 (例如：\*@ _domainname_)。 當您完成可供選時，按一下 [**確定]** 回到主畫面。 
        
      - 若要選取群組]，選取 [**收件者是的成員**。 然後，在後續的對話方塊中，選取或指定群組。 按一下 **[確定]** 回到主畫面。 
        
      - 若要選取網域，請選取 [**收件者網域是**。 然後，在後續的對話方塊新增網域。 按一下 **[確定]** 回到主畫面。 <br/><br/>您可以建立內之規則的例外狀況。 例如，您可以篩選來自某個網域以外之所有網域的郵件。 按一下 [**新增例外狀況**]，然後建立例外狀況條件類似於您建立其他種條件的方式。<br/><br/>將垃圾郵件原則套用至群組支援僅適用於**郵件啟用安全性群組**。 
  
16. 按一下 **[儲存]**。 原則設定的摘要隨即出現在右側窗格中。

無法停用或刪除預設原則和自訂原則一律優先於預設原則。 針對自訂原則，您可以選取或清除核取方塊來啟用或停用它們的 [**啟用**] 欄中。 根據預設，會啟用所有原則。 若要刪除自訂原則，請選取原則，請按一下 [![刪除圖示](media/ITPro-EAC-DeleteIcon.gif)**刪除**] 圖示，然後確認您想要刪除原則。

> [!TIP]
>  您可以變更自訂原則的優先順序 （執行順序），即可![向上箭號圖示](media/ITPro-EAC-UpArrowIcon.gif)向上鍵和![向下箭號圖示](media/ITPro-EAC-DownArrowIcon.gif)向下箭號。 有的**優先順序**為**0**的原則會執行第一個，後面接著**1**，然後**2**，依此類推。 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a>使用遠端 PowerShell 設定垃圾郵件篩選原則

您也可以在 PowerShell 中設定和套用垃圾郵件篩選原則。 若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。 若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱[Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。
  
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
   
## <a name="for-more-information"></a>相關資訊
<a name="sectionSection6"> </a>

[設定連線篩選原則](configure-the-connection-filter-policy.md)
  
[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)
  
[隔離](quarantine.md)
  
[使用安全清單或其他技術防止誤判電子郵件標示為垃圾郵件](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件以避免誤判正常](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

