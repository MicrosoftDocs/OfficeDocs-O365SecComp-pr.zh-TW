---
title: 使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 系統管理員可以了解如何在 Exchange Online Protection 設定郵件的 SCL。
ms.openlocfilehash: 48569087fe8455dbb5500add435430ec8e78ea30
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341344"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)

您可以建立郵件流程規則 （也稱為傳輸規則），設定電子郵件的垃圾郵件信賴等級 (SCL)。SCL 為量值的方式可能郵件是垃圾郵件。垃圾郵件是來路不明 （和通常不想要） 的電子郵件訊息。服務上根據其 SCL 分級的郵件採取不同的動作。例如，您可能想要略過垃圾郵件內容篩選的郵件，因為您信任從同事內部傳送的郵件不是垃圾郵件傳送來自組織內部的人員。使用郵件流程規則來設定郵件的 SCL 值可讓您增加中處理垃圾郵件的控制項。 
  
 **開始之前有哪些須知？**
  
- 完成此程序預估時間： 10 分鐘。
    
- 您必須獲指派權限，才能執行此程序或各個程序。若要查看您需要的權限，請參閱[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)或[EOP 中的權限的功能](eop/feature-permissions-in-eop.md)中的 「 郵件流程規則 」 項目。 
    
- 如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Exchange 系統管理中心的鍵盤快速鍵**。
    
### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>若要建立將郵件的 SCL 設定郵件流程規則

1. 在 Exchange 系統管理中心 (EAC) 中，選擇 [**郵件流程** \> **規則**。
    
2. 選擇 [**新增**![加入圖示](media/ITPro-EAC-AddIcon.gif)，然後選取 [**建立新的規則**。
    
3. 指定規則的名稱。
    
4. 選擇 [**更多選項**]，然後在 [**如果套用此規則**，請指定會觸發此規則 （也就是可設定的 SCL 值） 將設定的巨集指令的條件。
    
    例如，您可以設定**寄件者** \> **內部/外部**，然後在 [**選取寄件者位置**] 對話方塊中，選取**在組織內**，並選擇 [**確定]**。<br/>
    ![選取寄件者位置](media/EOP-ETR-SetSCL-1.jpg)
  
5. 在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。
  
6. 在 [**指定 SCL** ] 對話方塊中，選取下列其中一個下列值，並選擇 [**確定]**:
    
  - **略過垃圾郵件篩選**-將 SCL 設為-1，表示內容篩選不會執行此設定。 
    
  - **0-4** -當您將 SCL 設定為下列其中一個這些值時，郵件會傳遞沿著做其他處理的 「 內容篩選器。 
    
  - **5、 6** -當您將 SCL 設定為其中一個值，指定**垃圾郵件**的適用的內容篩選器原則中的動作將會套用。根據預設，動作是要將郵件傳送至收件者的垃圾郵件] 資料夾。 
    
  - **7-9** -當您將 SCL 設定為其中一個值，指定**高信賴度垃圾郵件**的適用的內容篩選器原則中的巨集指令將會套用。根據預設，動作是要將郵件傳送至收件者的垃圾郵件] 資料夾。 
    
    如需設定內容篩選原則的詳細資訊，請參閱<b0>設定垃圾郵件篩選原則</b0>。如需服務中各 SCL 值的詳細資訊，請參閱 <<c1>垃圾郵件信賴等級。
    
7. 指定規則的其他屬性，然後選擇 [**儲存]**。
    
    > [!TIP]
    > 如需其他屬性，您可以選取或指定為此規則的詳細資訊，請參閱 <<c0>使用 EAC 來建立郵件流程規則。 
  
## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認此程序正常運作，電子郵件傳送給組織內的人員，並確認已如預期般地對郵件執行的巨集指令。例如，如果您**略過垃圾郵件篩選**，然後將郵件的 [**設定垃圾郵件信賴等級 (SCL)** 應該傳送給指定收件者的收件匣。不過，如果您**設定垃圾郵件信賴等級 (SCL)** 設為**9**，以及針對適用的內容篩選器原則**高信賴度垃圾郵件**動作是要將郵件移至 [垃圾郵件] 資料夾，然後應該訊息傳送至指定之收件者的垃圾郵件] 資料夾。 
  

