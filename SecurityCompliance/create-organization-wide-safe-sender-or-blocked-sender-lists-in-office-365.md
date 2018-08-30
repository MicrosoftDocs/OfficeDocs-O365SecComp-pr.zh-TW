---
title: 在 Office 365 中建立整個組織的安全寄件者或封鎖的寄件者清單
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/8/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: 如果您想要確定您從特定寄件者收到郵件因為您信任他們和其訊息，您可以調整您允許在 Exchange 系統管理中心中的垃圾郵件篩選器原則中的清單。
ms.openlocfilehash: a90679fc900ca5695904898af3627fc1900a8545
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003162"
---
# <a name="create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365"></a>在 Office 365 中建立整個組織的安全寄件者或封鎖的寄件者清單
  
如果您想要確定您從特定寄件者收到郵件因為您信任他們和其訊息，您可以調整您允許在**保護**Exchange 系統管理中心 (EAC) 中的垃圾郵件篩選器原則中的清單\>**垃圾郵件篩選器**。深入了解這在[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)。另一個作法是建立 Exchange 傳輸規則 works like 網域或使用者型的允許在垃圾郵件篩選清單。您可封鎖郵件從特定的網域或使用者傳來的類似的方式太。
  
傳輸規則就會有幫助在此情況下若您要篩選的複雜的準則如檢查郵件標頭或附件的名稱或如果您想要新增複雜動作，例如將免責聲明新增至郵件或套用一段時間其中 rule 才有作用。不過，若要確定電子郵件從特定的寄件者或網域略過垃圾郵件篩選器的慣用的方法是將它們新增至您的垃圾郵件篩選器原則。快速入門這在 EAC 中移至 [**保護** \> **垃圾郵件篩選器**。深入瞭解如何[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)。
  
> [!TIP]
> 網域型清單中的傳輸規則不是以安全為 IP 位址為基礎清單，因為可以詐騙網域。此外，在封鎖清單上的傳送端 IP 位址時，它仍然會被封鎖即使篩選網域或使用者已被略過。這是因為在某個網域或使用者的傳輸規則不會覆寫全域的 IP 封鎖清單。我們建議在大多數情況下使用的 IP 位址為基礎清單。若要建立的 IP 位址為基礎清單，您可以使用的 IP 允許清單或 IP 封鎖清單中連線篩選器。從這些 IP 位址傳送任何郵件未由內容篩選檢查。如需如何設定連線篩選原則的 IP 位址新增至 IP 允許清單或 IP 封鎖清單的指示，請參閱[設定連線篩選原則](configure-the-connection-filter-policy.md)。 
  
如需與傳輸規則相關的其他管理工作，請參閱[Transport Rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)。
  
## <a name="use-the-eac-to-customize-a-block-or-allow-list-to-prevent-or-receive-email-from-a-domain-or-user"></a>使用 EAC 來自訂封鎖或允許清單，以防止或從某個網域或使用者會收到電子郵件

1. 在 EAC 中，移至 [**保護** \> **垃圾郵件篩選器**。 
    
2. 在 [**一般**] 頁面上執行下列其中一項： 
    
  - 按兩下預設原則或現有的原則，以啟動加以編輯。
    
  - 按一下 [**新增**] 以建立新的自訂垃圾郵件篩選器原則可套用至使用者、 群組及組織中的網域。 
    
3. 在 [**允許清單**] 頁面上，您可以指定項目，例如寄件者或一律會傳遞至收件匣的網域。垃圾郵件篩選器無法處理電子郵件從這些項目。執行下列動作： 
    
  - 新增信任的寄件者寄件者至允許清單。按一下 [**新增**]，並接著在選取項目] 對話方塊中，新增您想要允許的寄件者地址。您可以分隔多個項目使用分號分隔或新列。按一下 [確定] 回到 「**允許清單**」 頁面。 
    
  - 新增至網域的信任的網域允許清單。按一下 [**新增**]，並接著在選取項目] 對話方塊中，新增您想要允許的網域。您可以分隔多個項目使用分號分隔或新列。按一下 [確定] 回到 「**允許清單**」 頁面。 
    
    > [!CAUTION]
    > 如果您允許頂層網域，您不想要的電子郵件可能會傳遞至收件匣。 
  
4. 在 [ **封鎖清單**] 頁面上，您可以指定一律會標記為垃圾郵件的項目，例如寄件者或網域。此服務將會在符合這些項目的電子郵件上套用高信賴垃圾郵件動作。 
    
  - 將不想要的寄件者新增到「寄件者」封鎖清單。按一下 **[新增]**![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要封鎖的寄件者地址。您可以使用分號或新行區隔多個項目。按一下 [ **確定**] 回到 [ **封鎖清單**] 頁面。 
    
  - 將不想要的網域新增到「網域」封鎖清單。按一下 [ **新增**] ![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要封鎖的網域。您可以使用分號或新行區隔多個項目。按一下 [ **確定**] 回到 [ **封鎖清單**] 頁面。 
    
    > [!CAUTION]
    > 如果您封鎖頂層網域，您想要的電子郵件可能會標示為垃圾郵件。 
  
## <a name="what-do-you-need-to-know-before-you-begin-creating-a-transport-rule"></a>您需要知道之前建立傳輸規則什麼？
    
- 您不需要建立傳輸規則，以略過垃圾郵件篩選功能或標示為垃圾郵件的寄件者或網域的電子郵件。使用 Exchange Online Protection 封鎖及允許清單中，而不是此傳輸規則的垃圾郵件原則，如果您只想要封鎖或允許特定寄件者或網域並沒有附加任何額外的條件。深入了解這在[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)。
    
- 您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主題中的「傳輸規則」項目。 
    
- 如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。
    
> [!TIP]
> 有問題嗎？尋求 Exchange 論壇中的協助。請造訪在[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、 [Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)論壇。 
  
## <a name="use-the-eac-to-create-a-transport-rule-to-bypass-spam-filtering-for-a-domain-or-user"></a>使用 EAC 來建立傳輸規則，以略過網域或使用者的垃圾郵件篩選

1. 在 EAC 中，瀏覽至 [**郵件流程** \> **規則**。選擇 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)然後選擇 [**略過垃圾郵件篩選**。
    
2. 為規則命名。在 **[套用此規則，如果]** 下，選擇 **[寄件者]**，然後選取下列其中一個條件： 
    
  - 如果您想要指定的網域，選擇 [**網域**]。在 [**指定網域**] 對話方塊中，輸入您想要指定為安全，例如 contoso.com 的寄件者的網域。**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)將移至的片語清單。如果您想要新增其他的網域，並按一下 [**確定]** 完成時，重複此步驟。 
    
  - 如果您要指定使用者，請選擇 **[是此人]**。在 **[選取成員]** 對話方塊中，新增清單中的使用者，或輸入使用者並按一下 **[檢查名稱]**。如果要新增其他使用者，請重複此步驟，並在完成後按一下 **[確定]**。 
    
3. 選取 [**停止處理其他規則**] 核取方塊以確保沒有其他規則可以回復略過巨集指令 
    
4. **在郵件中的比對寄件者地址**] 選項中，選取 [**標頭或信封**。
    
5. 如果您想要您可以讓選取項目稽核規則、 測試規則、 特定時間期間啟動規則和其他選取項目。建議您測試規則的一段之前強制您組織中的時間。如需這些選項的詳細資訊，請參閱[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)。
    
6. 選擇 **[儲存]** 儲存規則。 
    
建立並強制執行規則後，垃圾郵件篩選就會略過您指定的網域或使用者。
  
## <a name="use-the-eac-to-create-a-transport-rule-that-blocks-messages-sent-from-a-domain-or-user"></a>使用 EAC 來建立傳輸規則封鎖從某個網域或使用者傳來的訊息

1. 在 EAC 中，瀏覽至 [**郵件流程** \> **規則**。選擇 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)然後選擇 [**建立新的規則**。
    
2. 命名規則，然後按一下 **[更多選項]**。 
    
3. 在 **[套用此規則，如果]** 下，選擇 **[寄件者]**，然後選取下列其中一個條件： 
    
  - 如果您想要指定的網域，選擇 [**網域**]。在 [指定網域] 對話方塊中，輸入您要封鎖郵件，例如 contoso.com 的寄件者網域。按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)將移至的片語清單。如果您想要新增其他的網域，並按一下 [**確定]** 完成時，重複此步驟。 
    
  - 如果您要指定使用者，請選擇 **[是此人]**。在 **[選取成員]** 對話方塊中，新增清單中的使用者，或輸入使用者並按一下 **[檢查名稱]**。如果要新增其他使用者，請重複此步驟，並在完成後按一下 **[確定]**。 
    
4. 在 **[執行下列作業]** 下方，選擇 **[封鎖郵件]**，然後按其餘選項之一，例如 **[刪除郵件而不通知任何人]**。
    
5. 按一下 [**更多選項**]，然後**在訊息中的比對寄件者地址**] 選項，選取 [**標頭或信封**。
    
6. 如果您想要您可以讓選取項目稽核規則、 測試規則、 特定時間期間啟動規則和其他選取項目。建議您測試規則的一段之前強制您組織中的時間。如需這些選項的詳細資訊，請參閱[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)。
    
7. 選擇 **[儲存]** 儲存規則。 
    
建立並強制執行規則後，將會封鎖從您指定的網域或使用者傳來的任何郵件。
  
## <a name="see-also"></a>另請參閱

[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)
  
[使用傳輸規則來設定大量電子郵件篩選](use-transport-rules-to-configure-bulk-email-filtering.md)

