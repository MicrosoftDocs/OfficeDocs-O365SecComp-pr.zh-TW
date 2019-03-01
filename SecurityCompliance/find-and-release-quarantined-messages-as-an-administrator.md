---
title: 以系統管理員身分找到並釋放被隔離的郵件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: 本主題說明如何 Exchange Online 和 Exchange Online Protection (EOP) 系統管理員可以尋找、 釋出，並回報被隔離的郵件在 Exchange 系統管理中心 (EAC) 上。
ms.openlocfilehash: aec067169b343ed186d506ed33c29385a7dc6450
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341784"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a>以系統管理員身分找到並釋放被隔離的郵件

本主題說明如何 Exchange Online 和 Exchange Online Protection (EOP) 系統管理員可以尋找、 釋出，並回報被隔離的郵件在 Exchange 系統管理中心 (EAC) 上。Office 365 會指示 [隔離郵件因為被判定為垃圾郵件或符合郵件流程規則 （也稱為傳輸規則）。 
  
使用安全性<b0></b0>合規性中心，而不是 EAC 中完成任何這些工作，以及檢視和使用已傳送至隔離區，因為它們包含惡意程式碼的郵件。如需詳細資訊，請參閱 < <b1>Office 365 中的隔離電子郵件</b1>。
  
隔離的郵件會列在 EAC 中的 [**隔離**] 頁面上。根據預設，郵件會依最新到最舊的在**收到日期**] 欄位。也列出每封郵件的**寄件者**、**主旨**及**到期日**的值。您可以排序這些任一欄位按一下欄標頭。如果您按一下欄標題，第二次，就會回復的排序順序。[**隔離**] 頁面上會顯示 500 封郵件的最大值。 
  
您可以檢視清單中的所有隔離的郵件，或者您可以藉由指定篩選準則搜尋特定郵件 （篩選也可以協助減少您結果集，如果您有超過 500 封郵件）。後搜尋並找到特定隔離的郵件，您可以檢視郵件的詳細資料。您還可以：
  
- 郵件釋出給一或多個收件者，並選擇性地向 Microsoft 垃圾郵件分析小組，小組會評估和分析此郵件為誤判 （非垃圾郵件） 的郵件報告。根據分析結果，您可能會調整全服務垃圾郵件內容篩選規則，以允許郵件通過。
    
- 釋出郵件並允許未來的所有郵件來自該寄件者。
    
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

- 您必須獲指派權限，才能執行此程序或各個程序。若要查看您需要的權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主題中的 「 隔離 」 項目。 
    
- 您可以釋出或多個郵件報告一次 [**隔離**] 頁面。或者您可以建立遠端 Windows PowerShell 指令碼，以完成這項工作。使用[Get-quarantinemessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx)指令程式來搜尋郵件，並釋放這些[Release-quarantinemessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx)指令程式。 
    
- 如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。
    
> [!TIP]
> 有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a>使用進階搜尋來篩選和尋找隔離郵件
<a name="BKMK_UseAdvancedSearchtoFilterMessages"> </a>

在 Exchange 系統管理中心 (EAC)，您可以使用進階搜尋，根據數個不同條件來篩選隔離的郵件。這些條件可以分開使用，也可以一起使用。搜尋將會提供符合所有篩選準則的郵件清單。
  
1. 在 EAC 中，瀏覽至 [**保護** \> **隔離區**，然後按一下 [**進階的搜尋**。
    
2. 在 [**進階搜尋**] 視窗中，選取下列條件的任何組合。選取 [關聯] 核取方塊以啟用每個條件。不支援萬用字元。 
    
1. **訊息識別碼**您可以使用此參數來執行特定郵件的目標式的搜尋。例如，如果特定郵件傳送者]，或適用於您組織中的使用者，但它永不到達其目的地，您可以搜尋使用郵件追蹤功能的郵件。如需詳細資訊，請參閱[執行訊息追蹤和檢視結果](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx)。如果您發現郵件已傳送至隔離區，可能是因為它符合規則，或已識別為垃圾郵件，您可以再輕鬆地此郵件中找到隔離區藉由指定其訊息識別碼。請務必包括完整的郵件識別碼字串。這可能包括角括弧 (\<\>)。 
    
2. **寄件者電子郵件地址** 指定寄送郵件人員的電子郵件地址。 
    
3. **收件者電子郵件地址** 指定郵件預定收件者的電子郵件地址。 
    
4. **主旨** 指定郵件的主旨行文字。 
    
5. **接收**您可以選取過去 24 小時 （**今天**）、 過去一週 （**最近 7 天**）、 過去 48 小時 （**最近 2 天**）、 內由隔離收到郵件，或者您可以選取的自訂時間間隔期間的郵件。接收到隔離區。 
    
6. **到期**您可以選取從隔離區在未來 24 小時 （**今天**）、 一週 （**未來 7 天**）、 未來 48 小時 （**未來 2 天**）、 內刪除的郵件，或您可以選取的自訂時間間隔期間的郵件將從隔離刪除。
    
    > [!IMPORTANT]
    > 根據預設，垃圾郵件隔離的郵件會保留在隔離區 15 天時符合郵件流程規則的隔離的郵件會保留在隔離區 7 天的。在這段時間後，Office 365 刪除郵件，而無法加以擷取。符合郵件流程規則的隔離郵件的保留期間不是可設定的。不過，可以降低垃圾郵件隔離的郵件的保留期間，透過內容篩選原則中的 [**保留垃圾郵件 （天） 的**設定。如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。 
  
7. **型別**您可以指定是否要搜尋被隔離的郵件會被識別為**垃圾郵件**，或是搜尋符合郵件流程規則 （**傳輸規則**） 的郵件。
    
3. 按一下 **[確定]**，開始執行進階搜尋。 
    
    > [!NOTE]
    > 若要清除搜尋準則並檢視隔離中的所有郵件，請清除 **[進階搜尋]** 視窗中的所有核取方塊，然後按一下 **[確定]**。 
  
搜尋郵件後，符合您指定之準則的結果會顯示在使用者介面中。EAC 中最多可以顯示 500 封郵件。 
  
## <a name="view-details-about-a-specific-quarantined-message"></a>檢視特定隔離郵件的詳細資料
<a name="BKMK_ViewDetailsAboutaSpecificQuarantinedMessage"> </a>

找到特定隔離的郵件之後 [**隔離**] 頁面上，您可以檢視其詳細資料。 
  
1. 在 [**隔離**] 頁面上，選取特定郵件，畫面右邊的詳細資料窗格中會顯示該郵件的屬性摘要。 
    
    **[郵件狀態]** 值如下： 
    
  - **型別**表示郵件是否已被識別為**垃圾郵件**或符合郵件流程規則 （**傳輸規則**）。
    
  - **到期** 將從隔離刪除此郵件的日期。 
    
    **[郵件詳細資料]** 值如下： 
    
  - **寄件者** 傳送郵件之人員的電子郵件地址。 
    
  - **主旨** 郵件的主旨行文字。 
    
  - **收到日期** 隔離收到郵件的日期。 
    
  - **大小** 郵件的大小，單位為 KB，如果郵件大小超過 999 KB 則為 MB。 
    
  - **檢視郵件標頭**按一下此連結以開啟 [**郵件標頭**] 對話方塊，可讓您檢視郵件標頭文字。您也可以將郵件標頭文字複製到剪貼簿，並將它貼到[郵件標頭分析器](https://testconnectivity.microsoft.com/?tabid=mha)。一次在郵件標頭分析器工具中，按一下 [**分析標頭**以便擷取標頭的相關資訊。 
    
    > [!TIP]
    > 如需服務所插入之特定反垃圾郵件郵件標頭欄位的相關資訊，請參閱[反垃圾郵件訊息標頭](anti-spam-message-headers.md)。 
  
  - **預覽電子郵件訊息**按一下此連結可以檢閱訊息的文字。 
    
2. 如果您按兩下隔離郵件，則會開啟 **[隔離郵件]** 視窗並顯示下列資訊： 
    
  - **已釋放** 已釋放其郵件的所有電子郵件地址清單 (若有的話)。 
    
  - **尚未發行至**對象不已釋放郵件，如果有任何的所有電子郵件地址清單。您可以按一下 [**發行**] 連結以釋出郵件;如需釋出郵件的詳細資訊，請參閱下一節。 
    
  - **郵件識別碼** 在郵件標頭中找到的網際網路郵件識別碼 (也稱為用戶端識別碼)。 
    
    按一下 **[關閉]** 返回主要隔離窗格。 
    
## <a name="release-messages-from-quarantine"></a>釋放隔離的郵件
<a name="sectionSection3"> </a>

如果您想要釋出到收件者的郵件，是您的選項：
  
- [釋出隔離的郵件，並允許將來的郵件寄件者](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessageallowfuturemessagesfromsender)
    
- [釋出隔離的郵件給特定收件者而不將其報告為誤判](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive)
    
- [釋出給所有收件者的一或多個隔離的郵件](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipients)
    
- [釋出給所有收件者及報告誤判的一或多個隔離的郵件](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives)
    
### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a>釋出隔離的郵件，並允許將來的郵件寄件者
<a name="Releasequarantinedmessageallowfuturemessagesfromsender"> </a>

1. 在 EAC 中，瀏覽至 [**保護** \> **隔離**。
    
2. 按一下以選取它，然後按一下 [**釋出郵件**] 圖示，如下列螢幕擷取畫面所示的郵件。 
  
![顯示隔離頁面，其中會反白顯示發行訊息圖示，並顯示發行選項](media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)
  
從下拉式清單中，按一下 [**選取的郵件釋出，並允許寄件者**。 
    
3. [**釋出郵件並允許寄件者**] 對話方塊隨即開啟。或者，您可以選擇以回報給 Microsoft，然後按一下 [**釋出，並允許**。郵件就會釋出給所有收件者地址來並將允許從此寄件者的所有未來郵件。不過，如果此郵件遭隔離因郵件流程規則或封鎖寄件者，寄件者將會繼續將來的郵件遭到封鎖。 
    
### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a>釋出隔離的郵件給特定收件者而不將其報告為誤判
<a name="Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive"> </a>

1. 在 EAC 中，瀏覽至 [**保護** \> **隔離**。
    
2. 選取一則訊息，按一下 [**釋出郵件**] 圖示，，然後從下拉式清單中按一下 [**郵件釋出給特定收件者**。 
    
3. 在 **[釋出郵件]** 對話方塊中，選取下列其中一個選項： 
    
  - **將郵件釋出給所有收件者** 如果您選取此選項，請注意，您只能將郵件釋出給同一位收件者一次。如果收件者先前已收到郵件，系統不會再將郵件釋出給該名收件者。 
    
  - **郵件釋出給指定收件者**選取 [對象可以釋出郵件的收件者]。由於每個收件者只發行一次一則訊息，只有中收件者對象發行會出現在此清單。支援多重選取範圍。您的收件者選擇之後，按一下 [**新增**]。
    
4. 按一下 **[釋出]**。 
    
如果您按一下 [**重新整理**![重新整理圖示](media/ITPro-EAC-RefreshIcon.gif)圖示來重新整理您的資料，然後連按兩下郵件，您應該會看到，它已釋出給預定的收件者。 
  
### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a>釋出給所有收件者的一或多個隔離的郵件
<a name="Releaseoneormorequarantinedmessagestoallrecipients"> </a>

1. 在 EAC 中，瀏覽至 [**保護** \> **隔離**。
    
2. 按一下以選取它，或使用 shift 鍵來選取多個郵件訊息。然後按一下 [**釋出郵件**] 圖示。 
    
3. 從下拉式清單中按一下 [**發行給所有收件者所選的郵件**]。 
    
4. [警告] 對話方塊隨即開啟。閱讀警告，如果您想要繼續，請選取 **[是]** 。當您選取此選項時，請注意，郵件無法再釋出一次以上相同的收件者。如果收件者先前已收到郵件，它將不會釋放再次給該收件者。 
    
### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a>釋出給所有收件者及報告誤判的一或多個隔離的郵件
<a name="Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives"> </a>

1. 在 EAC 中，瀏覽至 [**保護** \> **隔離**。
    
2. 按一下以選取它，或使用 shift 鍵來選取多個郵件訊息。然後按一下 [**釋出郵件**] 圖示。 
    
3. 從下拉式清單中，按一下 [**發行選取郵件並報告為誤判**。 
    
4. [警告] 對話方塊隨即開啟。閱讀警告，如果您想要繼續，請選取 **[是]** 。當您選取此選項時，請注意，郵件無法再釋出一次以上相同的收件者。如果收件者先前已收到郵件，它將不會釋放再次給該收件者。 
    
     當您選擇此選項時，郵件將會釋出給所有收件者未收到。如果是垃圾郵件隔離的郵件，它也會報告給 Microsoft 垃圾郵件分析小組，小組會評估和分析此郵件。根據分析結果，您可能會調整全服務垃圾郵件內容篩選規則，以允許郵件通過。 
    
> [!TIP]
> 協助確保郵件不會標示為垃圾郵件遵循[如何協助確保郵件不會標示為垃圾郵件](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md)中的步驟。 
  
如果您按一下 [**重新整理**![重新整理圖示](media/ITPro-EAC-RefreshIcon.gif)圖示來重新整理您的資料，然後連按兩下郵件，您應該會看到，它已釋出給預定的收件者。 
  
## <a name="for-more-information"></a>如需詳細資訊
<a name="sectionSection4"> </a>

[隔離常見問題集](quarantine-faq.md)
  

