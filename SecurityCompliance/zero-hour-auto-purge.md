---
title: 零時差自動清除 - 防範垃圾郵件和惡意程式碼
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/9/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: 零小時自動清除 (ZAP) 是電子郵件保護功能，可偵測到的郵件垃圾郵件或惡意程式碼中已被傳送到使用者的收件匣，並再轉譯無害惡意的內容。如何 ZAP 執行此動作而定的偵測到惡意內容類型。
ms.openlocfilehash: dc8901dc7c1db5b323ccbeee610647b8a302fcb3
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526357"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>零時差自動清除 - 防範垃圾郵件和惡意程式碼

零小時自動清除 (ZAP) 是電子郵件保護功能，可偵測到的郵件垃圾郵件或惡意程式碼中已被傳送到使用者的收件匣，並再轉譯無害惡意的內容。如何 ZAP 執行此動作而定的偵測到惡意內容類型。
  
ZAP 皆可使用的預設值是包含任何包含 Exchange Online 信箱的 Office 365 訂閱的 Exchange Online Protection。
  
## <a name="how-does-zap-work"></a>ZAP 如何運作？

Office 365 更新反垃圾郵件引擎和惡意程式碼中的簽章即時每天。不過，您的使用者可能仍屬惡意郵件傳遞至其收件匣的各種包括當內容 weaponized 一次之後先傳遞給使用者的原因。ZAP 這持續監視更新至 Office 365 垃圾郵件和惡意程式碼簽章的地址與因此尋找和收件匣中已移除先前已傳遞的郵件。已識別為垃圾郵件的郵件，ZAP 會將未讀取的郵件移至使用者的垃圾郵件] 資料夾。針對新偵測到惡意程式碼、 ZAP 會移除電子郵件，不論郵件是否已讀取的附件。反向是已不正確地歸類為惡意的郵件，則為 true。
  
信箱使用者、 他就不通知郵件已經移動 ZAP 動作是相當順暢。
  
允許清單、[郵件流程規則](https://go.microsoft.com/fwlink/p/?LinkId=722755)及使用者的規則或其他篩選器優先於 ZAP。
  
 **本文內容：**
  
> [設定垃圾郵件篩選器原則](zero-hour-auto-purge.md#BK_SetSpam)
    
> [請參閱 ZAP 是否移動郵件](zero-hour-auto-purge.md#BK_DidZAPMove)
    
> [停用 ZAP](zero-hour-auto-purge.md#BK_Posh)
    
> [常見問題集](zero-hour-auto-purge.md#BK_FAQ)
    
## <a name="working-with-zap"></a>使用 ZAP

ZAP 會開啟依預設，但您必須確認符合條件一些：
  
- 垃圾郵件篩選器原則設為[移至 [垃圾郵件] 資料夾的郵件](zero-hour-auto-purge.md#BK_SetSpam)。
    
    您也可以建立新的垃圾郵件篩選器原則只套用一組使用者如果您不想要 ZAP 所篩選的所有信箱。
    
- 使用者的[選項\>垃圾郵件](https://support.office.com/article/068FA430-F8D7-4518-A8DA-8BC74958F05F)。
    
如果您想[要查看 ZAP 如果移動郵件](zero-hour-auto-purge.md#BK_DidZAPMove)，您可以使用 Exchange Online 的郵件追蹤工具。
  
系統管理員也可以[停用 ZAP](zero-hour-auto-purge.md#BK_Posh)使用 PowerShell。 
  
 **若要設定垃圾郵件篩選器原則**
  
1. 登入[登入 Office 365 企業版位置](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)並且選擇 [**保護** \> **垃圾郵件篩選器**。 
    
    ![在 EAC 中選擇 [保護，然後垃圾郵件篩選器](media/0463c879-63fa-4a6c-9b03-e980d5ef3954.PNG)
  
2. [選擇您要調整的篩選器原則或選擇 [**新增**![新增圖示](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)來建立新的專案。 
    
    在舊版的螢幕擷取畫面，原則名為"Default"，但如果您建立額外的垃圾郵件篩選器原則您可以授與不同的名稱。您也可以將原則套用至只有一組有限的使用者。
    
3. 在 [原則] 視窗中，選擇 [**垃圾郵件和大量動作**]，然後確定**垃圾郵件**設定為**將郵件移至 [垃圾郵件] 資料夾**。 
    
    如果您選擇**儲存**此時，原則可套用至 Office 365 租用戶。 
    
    ![設定垃圾郵件和大量 Mpve 郵件至垃圾郵件] 資料夾的動作](media/4332cfb3-89e1-48ba-8da8-9286f2fa1089.PNG)
  
4. 如果您建立新的原則，而您想要將原則套用至只有一組使用者，捲動至 [**套用至**] 區段中原則篩選器] 視窗中，與功能表控制項中選擇 [**收件者**、**網域**或**群組的成員資格**您要套用之原則。您也可以設定其他條件和例外狀況。 
    
    ![在 [套用] 區段中選擇 [收件者](media/19ca10db-c0f4-432c-b3de-ad4101a23de6.PNG)
  
    選擇 [**儲存**] 以將原則套用至選取的使用者。 
    
 **若要查看 ZAP 是否移動郵件**
  
- 您可以使用[找出並修正為商務系統的 Office 365 的電子郵件傳遞問題](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6)來決定 ZAP 已移動郵件： 
    
    尋找您追蹤詳細資料] 以找出 ZAP 已移動郵件中的文字"零小時自動清除 (ZAP)"。
    
 **若要停用 ZAP**
  
- 如果您想要停用您的 Office 365 租用戶的 ZAP 或一組使用者，使用[Set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)、 EOP 指令程式的**ZapEnabled**參數。
    
    在下列範例中，ZAP 已停用名為"Test"的內容篩選原則。
    
||
|:-----|
|
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

|
   
## <a name="faq"></a>常見問題集
<a name="BK_FAQ"> </a>

 **如果合法的訊息移至 [垃圾郵件] 資料夾發生什麼情況？**
  
您應該遵循 false 測的標準報表程序。郵件會從收件匣移至垃圾郵件資料夾的唯一原因是因為此服務已決定郵件是垃圾郵件或惡意。
  
 **如果使用 Office 365 隔離而不是垃圾郵件資料夾吗？**
  
ZAP 不會將郵件移至隔離區從收件匣這一次。
  
 **如果我有自訂郵件流程規則 （封鎖 / 允許規則） 吗？**
  
由系統管理員 （郵件流程規則） 或封鎖及允許規則建立的規則優先採用。這類郵件會排除功能準則。
  
## <a name="related-topics"></a>相關主題
<a name="BK_FAQ"> </a>

[Office 365 電子郵件反垃圾郵件保護](anti-spam-protection.md)
  
[利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件以避免誤判正常](block-email-spam-to-prevent-false-negatives.md)
  

