---
title: 使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
description: 您可以建立的傳輸規則會將電子郵件的垃圾郵件信賴等級 (SCL)。SCL 為量值的方式有可能郵件為垃圾郵件。垃圾郵件是來路不明的 （且通常不想要的） 的電子郵件訊息。服務會根據其 scl 郵件上採取不同的動作。例如，您可能會想略過垃圾郵件內容之郵件的傳送來自組織內的人員因為您信任從同事內部傳送的訊息不是垃圾郵件篩選。您使用傳輸規則將郵件的 SCL 值提供增加處理垃圾郵件中的控制項。
ms.openlocfilehash: ad89230dac9de668488b40090d70d2b697a86edd
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026730"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)

您可以建立的傳輸規則會將電子郵件的垃圾郵件信賴等級 (SCL)。SCL 為量值的方式有可能郵件為垃圾郵件。垃圾郵件是來路不明的 （且通常不想要的） 的電子郵件訊息。服務會根據其 scl 郵件上採取不同的動作。例如，您可能會想略過垃圾郵件內容之郵件的傳送來自組織內的人員因為您信任從同事內部傳送的訊息不是垃圾郵件篩選。您使用傳輸規則將郵件的 SCL 值提供增加處理垃圾郵件中的控制項。 
  
 **開始之前有哪些須知？**
  
- 完成此程序預估時間： 10 分鐘。
    
- 您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)或[功能 EOP 中的權限](eop/feature-permissions-in-eop.md)中的 「 傳輸規則 」 項目。 
    
- 如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。
    
### <a name="to-create-a-transport-rule-that-sets-the-scl-of-a-message"></a>若要建立的傳輸規則會將郵件的 SCL

1. 在 Exchange 系統管理中心 (EAC) 中，選擇 [**郵件流程** \> **規則**。
    
2. 選擇 [**新增**![新增圖示](media/ITPro-EAC-AddIcon.png)，然後選取 [**建立新的規則**。
    
3. 指定規則的名稱。
    
4. 選擇 [**更多選項**]，然後在 [**套用此規則**，指定 [會觸發此規則 （這是設定 SCL 值） 將設定的巨集指令的條件。
    
    例如，您可以設定**寄件者** \> **內部/外部**，然後**選取 [寄件者位置**] 對話方塊中，選取**在組織內**，並選擇 [**確定]**。</br>
    ![選取寄件者位置](media/EOP-ETR-SetSCL-1.jpg)
  
5. 在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。
  
6. 在 [**指定 SCL** ] 對話方塊中，選取下列其中一個的下列值並選擇 [**確定]**：
    
  - **略過垃圾郵件篩選**-將不會執行為-1、 內容篩選這表示 SCL 此設定。 
    
  - **0-4** -當您將 SCL 設定為下列值之一，將郵件傳遞沿著以做其他處理的內容篩選器。 
    
  - 會套用**5、 6** -當您將 SCL 設定為其中一個值，可用的內容篩選器原則中指定的**垃圾郵件**的動作。根據預設，動作是要將郵件傳送給收件者的垃圾郵件] 資料夾。 
    
  - 會套用**7-9** -當您將 SCL 設定為其中一個值，指定**高信賴垃圾郵件**的適用的內容篩選器原則中的巨集指令。根據預設，動作是要將郵件傳送給收件者的垃圾郵件] 資料夾。 
    
    如需設定內容篩選原則的詳細資訊，請參閱[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)。如需服務中各 SCL 值的詳細資訊，請參閱[Spam confidence levels](spam-confidence-levels.md)。
    
7. 指定規則的其他屬性，並選擇 [**儲存]**。
    
    > [!TIP]
    > 如需您可以選取或指定為此規則的其他屬性的詳細資訊，請參閱[使用 EAC 建立傳輸規則](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx#CreateEAC)。 
  
## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認此程序運作正常，請傳送電子郵件訊息給您的組織內的某個人並確認訊息上執行的動作如預期般運作。例如，如果您為**略過垃圾郵件篩選**，則郵件的 [**設定垃圾郵件信賴等級 (SCL)** 應該傳送給指定之收件者的收件匣。不過，如果您**設定垃圾郵件信賴等級 (SCL)** **9**、 及適用的內容篩選器原則的**高信賴垃圾郵件**動作是要將郵件移至 [垃圾郵件] 資料夾，然後應該訊息傳送至指定之收件者的垃圾郵件] 資料夾。 
  

