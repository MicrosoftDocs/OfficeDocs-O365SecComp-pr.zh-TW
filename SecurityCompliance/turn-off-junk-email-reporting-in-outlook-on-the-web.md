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
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="da890-103">關閉垃圾郵件回報網路上的 outlook</span><span class="sxs-lookup"><span data-stu-id="da890-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="da890-p101">您可以將傳送垃圾郵件]、 [網路釣魚、 及 [非垃圾郵件給 Microsoft 進行分析使用網頁的垃圾郵件回報選項，在 Outlook 中[報告垃圾郵件和網路釣魚詐騙在網路上的 Outlook 中](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)所述。如果您不想要使用這些選項，系統管理員可以關閉其透過[Set-owamailboxpolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)指令程式。</span><span class="sxs-lookup"><span data-stu-id="da890-p101">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) cmdlet.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="da890-106">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="da890-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="da890-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="da890-107"></span></span>

- <span data-ttu-id="da890-108">預估完成時間：5 分鐘</span><span class="sxs-lookup"><span data-stu-id="da890-108">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="da890-p102">您必須獲得權限才能執行此程序或程序。若您需要哪些權限，請參閱[Outlook Web App permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp)主題中的 「 Outlook Web App 信箱原則 」 項目。</span><span class="sxs-lookup"><span data-stu-id="da890-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Outlook Web App mailbox policies" entry in the [Outlook Web App permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) topic.</span></span> 
    
- <span data-ttu-id="da890-111">在執行關閉垃圾郵件報告所需的 cmdlet 之前，您可能很有幫助檢閱[Get-owamailboxpolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx)和[Set-owamailboxpolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)主題中的參考資訊。</span><span class="sxs-lookup"><span data-stu-id="da890-111">Before you run the cmdlets required to turn off junk email reporting, it might be helpful to review the reference information in the [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) and [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) topics.</span></span> 
    
## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="da890-112">關閉垃圾郵件的網路釣魚和非垃圾郵件報告給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="da890-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="da890-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="da890-113"></span></span>

<span data-ttu-id="da890-114">首先，執行下列指令程式來取得想要關閉報告的虛擬目錄：</span><span class="sxs-lookup"><span data-stu-id="da890-114">First, run the following cmdlet to get the virtual directories for which you want to turn off reporting:</span></span>
  
```
Get-OwaMailboxPolicy -Identity <parameter>
```

<span data-ttu-id="da890-115">接著，執行下列指令程式來關閉 Microsoft 的垃圾郵件和非垃圾郵件報告：</span><span class="sxs-lookup"><span data-stu-id="da890-115">Next, run the following cmdlet to turn off junk and not junk reporting to Microsoft:</span></span>
  
```
Set-OwaMailboxPolicy -Identity <parameter> -ReportJunkEmailEnabled $false
```

<span data-ttu-id="da890-116">例如，下列指令程式會關閉虛擬目錄 Contoso\owa 的報告：</span><span class="sxs-lookup"><span data-stu-id="da890-116">For example, the following cmdlet turns off reporting for virtual directory Contoso\owa:</span></span>
  
```
Set-OwaMailboxPolicy -Identity Default -ReportJunkEmailEnabled $false
```

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="da890-117">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="da890-117">How do you know this worked?</span></span>
<span data-ttu-id="da890-118"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="da890-118"></span></span>

<span data-ttu-id="da890-p103">執行檢查參數的值，並再存取 Outlook web 上的 Get-owamailboxpolicy 並確認 [回報垃圾郵件、 網路釣魚、 和非垃圾郵件選項不提供。您仍必須能夠將郵件標示為垃圾郵件的網路釣魚和非垃圾郵件，但您不能回報這些。</span><span class="sxs-lookup"><span data-stu-id="da890-p103">Run Get-OWAMailboxPolicy to check the parameter values, and then access Outlook on the web and verify that the options to report junk, phishing, and not junk are not available. You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span> 
  

