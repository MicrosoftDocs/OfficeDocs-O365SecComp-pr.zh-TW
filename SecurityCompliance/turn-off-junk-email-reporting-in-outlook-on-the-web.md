---
title: 關閉垃圾郵件回報網路上的 outlook
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: 為 Office 365 系統管理員，您可以關閉能力報告電子郵件的人員為垃圾郵件。
ms.openlocfilehash: 1e45f258bea2ea75d9b4cabcacc43b54c44f83c3
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275583"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>關閉垃圾郵件回報網路上的 outlook

您可以將傳送垃圾郵件]、 [網路釣魚、 及 [非垃圾郵件給 Microsoft 進行分析使用網頁 （前身為 Outlook Web App） 的垃圾郵件回報選項，在 Outlook 中[回報垃圾郵件和網路釣魚詐騙在網路上的 Outlook 中](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)所述。如果您不想要使用這些選項，系統管理員可以關閉其透過[Set-owamailboxpolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)指令程式。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

- 預估完成時間：5 分鐘
    
- 您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[Outlook web 權限](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp)主題中的 「 web 信箱原則時 outlook 的 App 」 項目。 

- 若要連線至 Exchange Online PowerShell，請參閱[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>關閉垃圾郵件的網路釣魚和非垃圾郵件報告給 Microsoft
<a name="sectionSection1"> </a>

首先，執行下列命令以取得您可用的 Outlook web 上的名稱信箱原則：
  
```
Get-OwaMailboxPolicy | Format-Table Name
```

下一步] 以啟用或停用在網路上的 Outlook 中的 Microsoft 垃圾郵件和非垃圾郵件報告使用下列語法：
  
```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

本範例會關閉報表中的預設 Outlook web app 信箱原則：
  
```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

如需詳細的語法及參數資訊，請參閱[Get-owamailboxpolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx)和[Set-owamailboxpolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)。

## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？
<a name="sectionSection2"> </a>

執行**Get-owamailboxpolicy**檢查參數的值，然後再開啟 [網路上的受影響之使用者的 Outlook （誰具有 Outlook web 信箱原則上的套用至其） 並驗證不提供回報垃圾郵件、 網路釣魚，並不是垃圾郵件選項。您仍必須能夠將郵件標示為垃圾郵件的網路釣魚和非垃圾郵件，但您不能回報這些。 
