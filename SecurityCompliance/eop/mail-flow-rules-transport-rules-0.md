---
title: Exchange Online Protection 中的郵件流程規則 (傳輸規則)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/29/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: 您可以使用郵件流程規則 （傳輸規則） 來識別和對郵件採取動作的流程透過 Office 365 組織。
ms.openlocfilehash: a60035dc2ac17bcb944a5311827609381a7ed31e
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341204"
---
# <a name="mail-flow-rules-transport-rules-in-exchange-online-protection"></a>Exchange Online Protection 中的郵件流程規則 (傳輸規則)

您可以使用郵件流程規則 (也稱為傳輸規則)，找出經過 Office 365 組織的郵件並採取相應動作。郵件流程規則類似於 Outlook 和 網頁型 Outlook 中可用的收件匣規則。主要差異是郵件流程規則會在郵件傳輸期間採取動作，而不是在郵件傳遞至信箱之後。郵件流程規則包含一組更豐富的條件、例外狀況和行動，可讓您靈活地實作許多種郵件原則。
  
本文說明郵件流程規則的元件和它們的運作方式。
  
步驟來建立、 複製和管理郵件流程規則，請參閱<b0>管理郵件流程規則</b0>。針對每個規則，您可以選擇強制執行測試，或測試，通知寄件者。若要深入了解測試選項，請參閱 <<c1>測試郵件流程規則」 和 「<b2>原則提示</b2>。
  
如需符合郵件流程規則之訊息的摘要和詳細報告，請參閱 **使用 Office 365 的郵件保護報告以檢視有關惡意程式碼、垃圾郵件和規則偵測的資訊**。
  
若要使用郵件流程規則實作特定的訊息原則，請參閱下列主題︰
  
- [Use mail flow rules to inspect message attachments in Office 365](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)
    
- [設定 Office 365 企業版中的加密](https://support.office.com/article/e86fc991-0161-4f01-9c1c-d25e87733d06)
    
- [Organization-wide message disclaimers, signatures, footers, or headers in Office 365](http://technet.microsoft.com/library/29ac61c2-77f1-4071-b14e-8cc64e3e76ba.aspx)
    
- [Use mail flow rules to set the spam confidence level (SCL) in messages](../use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)
    
- [Create organization-wide safe sender or blocked sender lists in Office 365](../create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365.md)
    
- [透過 Exchange Online Protection 中的檔案附件封鎖功能來降低惡意軟體威脅](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)
    
- [定義加密或解密電子郵件訊息的規則](https://go.microsoft.com/fwlink/p/?Linkid=402846)
    
下列視訊提供示範設定郵件流程規則，在 Exchange Online Protection。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]
  
## <a name="mail-flow-rule-components"></a>郵件流程規則元件

郵件流程規則是由條件、例外狀況、動作和屬性所組成︰
  
- **條件** 識別您要套用動作的郵件。有些條件會檢查郵件標頭欄位 (例如 [收件者]、[寄件者] 或 [副本] 欄位)。有些條件則會檢查郵件屬性 (例如郵件主旨、內文、附件、郵件大小或郵件分類)。在使用大部分的條件時，您都必須指定比較運算子 (例如等於、不等於或包含) 以及要比對的值。如果沒有條件或例外狀況，則規則會套用至所有郵件。 
    
    如需有關 Exchange Online Protection 中郵件流程規則條件的詳細資訊，請參閱[中 Exchange Online 的郵件流程規則條件和例外狀況 （述詞）。](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。
    
- **例外狀況** 選擇性地識別不應該套用動作的郵件。可在條件中使用的訊息識別碼也可用於例外狀況。例外狀況可覆寫條件並防止規則動作套用到郵件，即使郵件符合所有設定的條件也是如此。 
    
- **動作** 指定對於符合規則中的條件，但不符合任何例外狀況的郵件，所應採取的動作。有許多動作可用，例如，拒絕、刪除或重新導向郵件、新增其他收件者、在郵件主旨中新增前置詞，或是將免責聲明插入郵件內文。 
    
    如需郵件流程規則動作可在 Exchange Online Protection，請參閱[郵件流程規則動作在 Exchange Online Protection](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)。
    
- **屬性** 指定其他不是條件、例外狀況或動作的規則設定。例如，何時應套用規則、是否強制執行或測試規則，以及規則作用中的時間週期。 
    
     如需詳細資訊，請參閱本主題中的 [郵件流程規則屬性](mail-flow-rules-transport-rules-0.md#Properties)一節。 
    
### <a name="multiple-conditions-exceptions-and-actions"></a>多個條件、例外狀況和動作

下表顯示規則中如何處理多個條件、條件值、例外狀況和動作。
  
|**元件**|**邏輯**|**註解**|
|:-----|:-----|:-----|
|多個條件  <br/> |AND  <br/> |郵件必須符合規則中的所有條件。如果您需要符合一個條件或另一個條件，請對每一個條件使用不同的規則。例如，若要將相同的免責聲明新增至附件和內容包含特定文字的郵件，請為每一個條件建立一個規則。在 EAC 中，您可以輕易地複製規則。  <br/> |
|具有多個值的一個條件  <br/> |或  <br/> |有些條件允許您指定多個值。郵件必須符合任何一個 (而非全部) 指定的值。例如，如果電子郵件的主旨為股票價格資訊，而 **[主旨包含任何這些字詞]** 條件設定為符合 Contoso 或 股票這些字，則此電子郵件滿足該條件，因為主旨至少包含其中一個指定的值。  <br/> |
|多個例外狀況  <br/> |OR  <br/> |如果郵件符合任何例外狀況，則動作不會套用到郵件。郵件不必符合所有例外狀況。  <br/> |
|多個動作  <br/> |AND  <br/> |符合規則條件的郵件會取得所有規則中指定的動作。例如，如果選取**的郵件主旨前面加上**和**新增收件者到 [密件副本] 方塊中**的動作，這兩個動作會套用至郵件。<br/> 請記住，某些動作 (例如， **[刪除郵件而不通知任何人]** 動作) 會阻止後續規則套用至郵件。其他動作 (例如 **[轉寄郵件]**) 則不允許額外的動作。  <br/> 您也可以在規則上設定動作，以便在套用該規則時，不要將後續的規則套件到郵件。  <br/> |
   
### <a name="mail-flow-rule-properties"></a>郵件流程規則屬性
<a name="Properties"> </a>

下表說明郵件流程規則中可用的規則屬性。
  
|**EAC 中的屬性名稱**|**PowerShell 中的參數名稱**|**描述**|
|:-----|:-----|:-----|
|**優先順序** <br/> | _Priority_ <br/> |表示規則套用到郵件的順序。預設優先順序是以規則的建立時間為基礎 (較舊規則的優先順序高於較新的規則，而較高優先順序的規則會在較低優先順序的規則之前處理)。    <br/> 您可以在規則清單中向上或向下移動規則，以變更 EAC 中的規則優先順序。在 PowerShell 中，您可設定優先順序號碼 (0 為最高優先順序)。    <br/> 例如，如果有一個規則是拒絕含有信用卡號碼的郵件，而另一個規則是需要核准，則您一定希望先執行拒絕規則，並停止套用其他規則。  |
|**模式** <br/> | _Mode_ <br/> |您可以指定是否要讓規則立即開始處理郵件，或您是否想要測試規則，而不影響郵件傳遞 (不論是否有資料遺失防護或 DLP 原則提示)。  <br/> 原則提示可在 Outlook 或 網頁型 Outlook 中呈現簡短附註，以提供可能原則違規的相關資訊給正在建立郵件的人員。如需詳細資訊，請參閱 **Policy Tips** 。  <br/> 如需模式的詳細資訊，請參閱＜**Test a mail flow rule**＞。  <br/> |
|**於下列日期啟用此規則** <br/> **於下列日期停用此規則** <br/> | _ActivationDate_ <br/>  _ExpiryDate_ <br/> |指定規則的有效日期範圍。  <br/> |
|**在 [上**] 核取方塊選取或未選取  <br/> |新規則： _New-TransportRule_ Cmdlet 上的  **Enabled** 參數。  <br/> 現有規則：使用 **Enable-TransportRule** 或 **Disable-TransportRule** Cmdlet。  <br/> 此值會顯示在規則的 **State** 屬性中。  <br/> |您可以建立已停用的規則，而在您準備進行測試時加以啟用。或者，您可以在不刪除規則的情況下進行停用，以保留設定。  <br/> |
|**如果無法完成規則處理時便順延郵件** <br/> | _RuleErrorAction_ <br/> |您可以指定如果無法完成規則處理時，應該如何處理郵件。預設會忽略此規則，但您可以選擇重新提交郵件進行處理。  <br/> |
|**符合郵件中的寄件者地址** <br/> | _SenderAddressLocation_ <br/> |如果此規則使用可檢查寄件者電子郵件地址的條件或例外狀況，您可以查看郵件標頭、郵件信封或這兩者的值。  <br/> |
|**停止處理其他規則** <br/> | _SenderAddressLocation_ <br/> |這是適用於規則的動作，但它看起來像是 EAC 中的屬性。您可以選擇在規則處理郵件之後，停止將其他規則套用至郵件。  <br/> |
|**註解** <br/> | _Comments_ <br/> |您可以輸入有關規則的描述性註解。  <br/> |
   
## <a name="how-mail-flow-rules-are-applied-to-messages"></a>郵件流程規則套用至訊息的方式

經過您組織的所有郵件進行都評估貴組織中已啟用的郵件流程規則。在 [**郵件流程**所列順序處理規則\>**規則**] 頁面上，在 EAC 中，或在 PowerShell 中的對應_優先順序_參數值為基礎。 
  
每個規則也提供選項可於符合規則時停止處理其他規則。對於符合多個郵件流程規則中條件的郵件而言，此設定很重要 (您想要將哪個規則套用到郵件？全部？僅只一個？）。
  
### <a name="differences-in-processing-based-on-message-type"></a>郵件類型引發的處理差異

通過組織的郵件有幾種類型。下表顯示郵件流程規則可處理的郵件類型。
  
****

|**郵件類型**|**可以套用規則嗎?**|
|:-----|:-----|
|**一般郵件** 包含單一 RTF 格式 (RTF)、HTML 或純文字郵件內文的郵件，或包含一組多部分或替代郵件內文的郵件。  <br/> |是  <br/> |
|**Office 365 郵件加密 ** Office 365 中 Office 365 郵件加密 所加密的郵件。如需詳細資訊，請參閱 [Office 365 郵件加密](https://go.microsoft.com/fwlink/p/?LinkId=392525)。  <br/> |規則永遠可以存取信封標頭，並根據可檢查這些標頭的條件來處理郵件。  <br/> 如需可檢查或修改加密郵件內容的規則，您必須確認已啟用傳輸解密 (強制或選擇性；預設值是選擇性)。如需詳細資訊，請參閱[啟用或停用傳輸解密](https://go.microsoft.com/fwlink/p/?linkid=848060)。  <br/> 您也可以建立規則以自動解密加密的郵件。如需詳細資訊，請參閱[定義將電子郵件加密或解密的規則](https://go.microsoft.com/fwlink/p/?Linkid=402846)。  <br/> |
|**S/MIME 加密的郵件** <br/> |規則只可以存取信封標頭，並根據可檢查這些標頭的條件來處理郵件。  <br/> 無法處理具有需要檢查郵件內容之條件的規則，或具有可以修改郵件內容之動作的規則。  <br/> |
|**RMS 保護的訊息** 已套件 Active Directory Rights Management Services(AD RMS) 或 Azure 版權管理 (RMS) 原則的郵件。  <br/> |規則永遠可以存取信封標頭，並根據可檢查這些標頭的條件來處理郵件。  <br/> 如需可檢查或修改 RMS 保護之郵件內容的規則，您必須確認已啟用傳輸解密 (強制或選擇性；預設值是選擇性)。如需詳細資訊，請參閱[啟用或停用傳輸解密](https://go.microsoft.com/fwlink/p/?linkid=848060)。  <br/> |
|**明文簽章的郵件** 已簽署但未加密的郵件。  <br/> |是  <br/> |
|**UM 郵件** 由整合通訊服務建立或處理的郵件 (如語音信箱、傳真、未接來電通知)，以及使用 Microsoft Outlook 語音存取 建立或轉寄的郵件。  <br/> |是  <br/> |
|**匿名郵件** 匿名寄件者所傳送的郵件。  <br/> |是  <br/> |
|**讀取報告** 為了回應寄件者的索取讀信回條而產生的報告。讀取內含  `IPM.Note*.MdnRead` 或  `IPM.Note*.MdnNotRead` 之郵件類別的報告。  <br/> |是  <br/> |
   
## <a name="what-else-should-i-know"></a>其他注意事項

- 規則的**版本**或**RuleVersion**屬性值不在 Exchange Online Protection 中重要的。 
    
- 在建立或修改郵件流程規則之後，可能需要 30 分鐘，以將新規則或更新的規則套用至訊息。
    
## <a name="for-more-information"></a>相關資訊
  
[使用郵件流程規則來 inspect message attachments 於 Exchange Online](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)
  
[Office 365 中的電子郵件加密](https://support.office.com/article/c0d87cbe-6d65-4c03-88ad-5216ea5564e8)
  
[日誌、 傳輸和收件匣規則限制](https://go.microsoft.com/fwlink/p/?LinkId=324584)
