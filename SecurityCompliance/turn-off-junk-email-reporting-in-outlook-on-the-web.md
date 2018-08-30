---
title: 關閉垃圾郵件回報網路上的 outlook
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/9/2015
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
description: 為 Office 365 系統管理員，您可以關閉能力報告電子郵件的人員為垃圾郵件。
ms.openlocfilehash: 8ee5ff87408b80c443e4cf950ce49f624096becb
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272038"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>關閉垃圾郵件回報網路上的 outlook

您可以將傳送垃圾郵件]、 [網路釣魚、 及 [非垃圾郵件給 Microsoft 進行分析使用網頁的垃圾郵件回報選項，在 Outlook 中[報告垃圾郵件和網路釣魚詐騙在網路上的 Outlook 中](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)所述。如果您不想要使用這些選項，系統管理員可以關閉其透過[Set-owamailboxpolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)指令程式。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

- 預估完成時間：5 分鐘
    
- 您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[Outlook Web App permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp)主題中的 「 Outlook Web App 信箱原則 」 項目。 
    
- 在執行關閉垃圾郵件報告所需的 cmdlet 之前，您可能很有幫助檢閱[Get-owamailboxpolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx)和[Set-owamailboxpolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)主題中的參考資訊。 
    
## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>關閉垃圾郵件的網路釣魚和非垃圾郵件報告給 Microsoft
<a name="sectionSection1"> </a>

首先，執行下列指令程式來取得想要關閉報告的虛擬目錄：
  
```
Get-OwaMailboxPolicy -Identity <parameter>
```

接著，執行下列指令程式來關閉 Microsoft 的垃圾郵件和非垃圾郵件報告：
  
```
Set-OwaMailboxPolicy -Identity <parameter> -ReportJunkEmailEnabled $false
```

例如，下列指令程式會關閉虛擬目錄 Contoso\owa 的報告：
  
```
Set-OwaMailboxPolicy -Identity Default -ReportJunkEmailEnabled $false
```

## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？
<a name="sectionSection2"> </a>

執行檢查參數的值，並再存取 Outlook web 上的 Get-owamailboxpolicy 並確認 [回報垃圾郵件、 網路釣魚、 和非垃圾郵件選項不提供。您仍必須能夠將郵件標示為垃圾郵件的網路釣魚和非垃圾郵件，但您不能回報這些。 
  

