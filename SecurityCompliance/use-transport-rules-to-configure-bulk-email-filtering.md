---
title: 使用郵件流程規則來設定 Exchange Online Protection 中篩選大量電子郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
description: 系統管理員可以了解如何使用 Exchange Online Protection 中的郵件流程規則的大量電子郵件篩選。
ms.openlocfilehash: ce95872d3d80436dce4c62037caea9a5f735726d
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "27382804"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a>使用郵件流程規則來設定 Exchange Online Protection 中篩選大量電子郵件

您可以設定為使用預設的垃圾郵件的內容篩選原則的垃圾郵件和大量電子郵件的全公司的內容篩選器。如何設定內容篩選原則查看[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)和[Set-hostedcontentfilterpolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) 。 
  
如果您想要更多選項] 以篩選大量郵件，您可以建立搜尋的文字模式或片語經常找到大量電子郵件中的郵件流程規則 （也稱為傳輸規則）。包含下列特性任何訊息將標記為垃圾郵件。使用這些規則可以協助減少組織會收到不想要的大量電子郵件。
  
**附註**：

- 建立郵件流程規則記載本主題之前，建議您先閱讀[垃圾郵件與大量電子郵件之間的差異為何吗？](what-s-the-difference-between-junk-email-and-bulk-email.md)和[大量抱怨層級的值](bulk-complaint-level-values.md)。 
  
- 下列程序會將郵件標示為整個組織的垃圾郵件。不過，您可以新增至這些規則僅適用於您組織中特定收件者的另一個條件。如此一來，篩選設定可以套用到高度目標的一些使用者不積極的大量電子郵件時您使用者 （多半要取得其簽署向上的大量電子郵件） 的其餘部分不會影響。 
  
### <a name="create-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>建立郵件流程規則來篩選大量電子郵件根據文字模式

1. 在Exchange 系統管理中心 (EAC)，請移至 [ **郵件流程**\> **規則**。
    
2. 按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 [**建立新的規則**。
    
3. 指定規則的名稱。
    
4. 按一下 [**更多選項]**。在**套用此規則情況**] 下選取 [**在主旨或本文** \> **主旨或內文符合這些文字模式**。
    
5. 在 [**指定單字或片語**] 對話方塊中，新增下列的規則運算式通常位於第一次大量電子郵件和完成時按一下 [**確定]** ： 
    
   - 如果您是無法檢視此電子郵件的內容\,請
    
   - \\>(安全)?取消訂閱 (這裡)?\\</a\\>
    
   - 如果您不想要接收像這樣的進一步通訊\,請
    
   - \\<img height\="?1"? width\="?1"? src\=.?http\://
    
   - 若要停止接收這些電子郵件\:http\://
    
   - 若要取消訂閱 \w+ (e\-?letter|e?-?mail|newsletter)
    
   - 不再 (想)?(要)?(傳送|接收) \w+ 電子郵件
    
   - 如果您是無法檢視此電子郵件的內容\,請按一下這裡
    
   - 若要確保您收到 (每日的處理 | 我們 e ?mails)\,新增
    
   - 如果您不想要再收到這些電子郵件
    
   - 變更您的 (訂閱喜好設定或取消訂閱)
    
   - 按一下 (這裡) 以取消訂閱
    
   **附註**：

   - 上述清單不是大量電子郵件 ； 中找到的規則運算式的詳盡集更多可以新增或移除視。不過，它是很好的起點。
    
   - 搜尋字詞或主旨中的文字模式或其他郵件中的標頭欄位發生已從 MIME 內容傳輸編碼方法用來傳輸 ASCII 文字中的 SMTP 伺服器之間的二進位郵件解碼*之後*郵件。您無法搜尋的原始使用條件或例外狀況 (通常 Base64) 編碼的主旨或其他訊息中的標頭欄位的值。 
    
6. 在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。
    
7. 在 [**指定 SCL** ] 對話方塊中，將 SCL 設定為**5**、 **6**或**9**，並按一下 [**確定]**。
    
   將 SCL 設定為 5 或 6 採用的**垃圾郵件**動作、 時設定為 9 SCL 採取**高信賴垃圾郵件**動作，設定的內容篩選原則。此服務會執行巨集指令中的內容篩選原則設定。預設動作是要將郵件傳遞給收件者的垃圾郵件] 資料夾，但是您可以設定不同的動作，[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)所述。
    
   > [!NOTE]
   > 如果您已設定的動作是要隔離郵件而不是將其傳送給收件者的垃圾郵件] 資料夾，就會傳送訊息到管理員隔離如郵件流程規則比對及它將無法使用使用者垃圾郵件隔離區中或透過使用者垃圾郵件通知。 
  
   如需服務中各 SCL 值的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。
    
8. 儲存規則。
    
### <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a>建立篩選根據片語的大量電子郵件的郵件流程規則

1. 在 EAC 中，移至 [**郵件流程** \> **規則**。
    
2. 按一下 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 [**建立新的規則**。
    
3. 指定規則的名稱。
    
4. 按一下 [**更多選項]**。在**套用此規則情況**] 下選取 [**在主旨或本文** \> **主旨或內文中包含任何這些字詞**。
    
5. 在 [**指定單字或片語**] 對話方塊中，新增下列常見於大量電子郵件，一次一個中然後在完成時按一下 [**確定]** ： 
    
   - 變更您的喜好設定或取消訂閱
    
   - 修改電子郵件喜好設定或取消訂閱
    
   - 這是促銷電子郵件
    
   - 您會收到此電子郵件是因為您已要求訂閱
    
   - 按一下這裡以取消訂閱
    
   - 您會收到此電子郵件是因為您已訂閱
    
   - 如果您不想要再收到我們的電子報
    
   - 取消訂閱此電子報
    
   - 如果您無法檢視此電子郵件
    
   - 這是廣告
    
   - 您想要取消訂閱或變更您的
    
   - 檢視此電子郵件的網頁版
    
   - 您會收到此電子郵件是因為您已訂閱
    
   **請注意**： 再次這份清單不是大量電子郵件 ； 中找到的片語的詳盡集更多可以新增或移除視。不過，它是很好的起點。
    
6. 在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。
    
7. 在 [**指定 SCL** ] 對話方塊中，將 SCL 設定為**5**、 **6**或**9**，並按一下 [**確定]**。
    
   將 SCL 設定為 5 或 6 採用的**垃圾郵件**動作、 時設定為 9 SCL 採取**高信賴垃圾郵件**動作，設定的內容篩選原則。此服務會執行巨集指令中的內容篩選原則設定。預設動作是要將郵件傳遞給收件者的垃圾郵件] 資料夾，但是您可以設定不同的動作，[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)所述。
    
   > [!NOTE]
   > 如果您已設定的動作是要隔離郵件而不是將其傳送給收件者的垃圾郵件] 資料夾，就會傳送訊息到管理員隔離如郵件流程規則比對及它將無法使用使用者垃圾郵件隔離區中或透過使用者垃圾郵件通知。 
  
   如需服務中各 SCL 值的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。

8. 儲存規則。

## <a name="for-more-information"></a>相關資訊

[垃圾郵件和大量電子郵件有什麼不同?](what-s-the-difference-between-junk-email-and-bulk-email.md)

[大量抱怨層級值](bulk-complaint-level-values.md)

[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)

[進階垃圾郵件篩選選項](advanced-spam-filtering-asf-options.md)
