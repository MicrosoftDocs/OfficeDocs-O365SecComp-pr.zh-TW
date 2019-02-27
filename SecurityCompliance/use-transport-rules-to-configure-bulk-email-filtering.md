---
title: 使用郵件流程規則來設定 Exchange Online Protection 中篩選大量電子郵件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 系統管理員可以了解如何使用 Exchange Online Protection 中的郵件流程規則的大量電子郵件篩選。
ms.openlocfilehash: b7144f16df3e7b9f90a24f1ac224ccb20287d918
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275683"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a>使用郵件流程規則來設定 Exchange Online Protection 中篩選大量電子郵件

您可以設定為使用預設的垃圾郵件的內容篩選原則的垃圾郵件和大量電子郵件的全公司的內容篩選器。如何設定內容篩選原則查看[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)和[Set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) 。 
  
如果您想要更多選項] 以篩選大量郵件，您可以建立搜尋的文字模式或片語經常找到大量電子郵件中的郵件流程規則 （也稱為傳輸規則）。包含下列特性任何訊息將標記為垃圾郵件。使用這些規則可以協助減少組織會收到不想要的大量電子郵件。

> [!IMPORTANT]
> 建立郵件流程規則記載本主題之前，建議您先閱讀[垃圾郵件與大量電子郵件之間的差異為何吗？](what-s-the-difference-between-junk-email-and-bulk-email.md)和[大量抱怨層級的值](bulk-complaint-level-values.md)。<br>下列程序會將郵件標示為整個組織的垃圾郵件。不過，您可以新增至這些規則僅適用於您組織中特定收件者的另一個條件。如此一來，篩選設定可以套用到高度目標的一些使用者不積極的大量電子郵件時您使用者 （多半要取得其簽署向上的大量電子郵件） 的其餘部分不會影響。 
  
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>建立篩選根據文字模式的大量電子郵件的郵件流程規則

1. 在Exchange 系統管理中心 (EAC)，請移至 [ **郵件流程**\> **規則**。
    
2. 按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 [**建立新的規則**。
    
3. 指定規則的名稱。
    
4. 按一下 [**更多選項]**。在**套用此規則情況**] 下選取 [**在主旨或本文** \> **主旨或內文符合這些文字模式**。
    
5. 在 [**指定單字或片語**] 對話方塊中，新增下列的規則運算式通常位於第一次大量電子郵件和完成時按一下 [**確定]** ： 
    
   - `If you are unable to view the content of this email\, please`
    
   - `\>(safe )?unsubscribe( here)?\</a\>`
    
   - `If you do not wish to receive further communications like this\, please`
    
   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
    
   - `To stop receiving these+emails\:http\://`
    
   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
    
   - `no longer (wish )?(to )?(be sent|receive) w+ email`
    
   - `If you are unable to view the content of this email\, please click here`
    
   - `To ensure you receive (your daily deals|our e-?mails)\, add`
    
   - `If you no longer wish to receive these emails`
    
   - `to change your (subscription preferences|preferences or unsubscribe)`
    
   - `click (here to|the) unsubscribe`
    
   上述清單不是大量電子郵件 ； 中找到的規則運算式的詳盡集更多可以新增或移除視。不過，它是很好的起點。<br>搜尋字詞或主旨中的文字模式或其他郵件中的標頭欄位發生已從 MIME 內容傳輸編碼方法用來傳輸 ASCII 文字中的 SMTP 伺服器之間的二進位郵件解碼*之後*郵件。您無法搜尋的原始使用條件或例外狀況 (通常 Base64) 編碼的主旨或其他訊息中的標頭欄位的值。 
    
6. 在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。
    
7. 在 [**指定 SCL** ] 對話方塊中，將 SCL 設定為**5**、 **6**或**9**，並按一下 [**確定]**。
    
   將 SCL 設定為 5 或 6 採用的**垃圾郵件**動作、 時設定為 9 SCL 採取**高信賴垃圾郵件**動作，設定的內容篩選原則。此服務會執行巨集指令中的內容篩選原則設定。預設動作是要將郵件傳遞給收件者的垃圾郵件] 資料夾，但是您可以設定不同的動作，[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)所述。
    
   如果您已設定的動作是要隔離郵件而不是將其傳送給收件者的垃圾郵件] 資料夾，就會傳送訊息到管理員隔離如郵件流程規則比對及它將無法使用使用者垃圾郵件隔離區中或透過使用者垃圾郵件通知。 
  
   如需服務中各 SCL 值的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。
    
8. 儲存規則。
    
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a>建立篩選根據片語的大量電子郵件的郵件流程規則

1. 在 EAC 中，移至 [**郵件流程** \> **規則**。
    
2. 按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 [**建立新的規則**。
    
3. 指定規則的名稱。
    
4. 按一下 [**更多選項]**。在**套用此規則情況**] 下選取 [**在主旨或本文** \> **主旨或內文中包含任何這些字詞**。
    
5. 在 [**指定單字或片語**] 對話方塊中，新增下列常見於大量電子郵件，一次一個中然後在完成時按一下 [**確定]** ： 
    
   - `to change your preferences or unsubscribe`
    
   - `Modify email preferences or unsubscribe`
    
   - `This is a promotional email`
    
   - `You are receiving this email because you requested a subscription`
    
   - `click here to unsubscribe`
    
   - `You have received this email because you are subscribed`
    
   - `If you no longer wish to receive our email newsletter`
    
   - `to unsubscribe from this newsletter`
    
   - `If you have trouble viewing this email`
    
   - `This is an advertisement`
    
   - `you would like to unsubscribe or change your`
    
   - `view this email as a webpage`
    
   - `You are receiving this email because you are subscribed`
    
   這份清單不是大量電子郵件 ； 中找到的片語的詳盡集更多可以新增或移除視。不過，它是很好的起點。
    
6. 在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。
    
7. 在 [**指定 SCL** ] 對話方塊中，將 SCL 設定為**5**、 **6**或**9**，並按一下 [**確定]**。
    
   將 SCL 設定為 5 或 6 採用的**垃圾郵件**動作、 時設定為 9 SCL 採取**高信賴垃圾郵件**動作，設定的內容篩選原則。此服務會執行巨集指令中的內容篩選原則設定。預設動作是要將郵件傳遞給收件者的垃圾郵件] 資料夾，但是您可以設定不同的動作，[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)所述。
    
   如果您已設定的動作是要隔離郵件而不是將其傳送給收件者的垃圾郵件] 資料夾，就會傳送訊息到管理員隔離如郵件流程規則比對及它將無法使用使用者垃圾郵件隔離區中或透過使用者垃圾郵件通知。 
  
   如需服務中各 SCL 值的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。

8. 儲存規則。

## <a name="for-more-information"></a>相關資訊

[垃圾郵件和大量電子郵件有什麼不同?](what-s-the-difference-between-junk-email-and-bulk-email.md)

[大量抱怨層級值](bulk-complaint-level-values.md)

[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)

[進階垃圾郵件篩選選項](advanced-spam-filtering-asf-options.md)
