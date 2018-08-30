---
title: DLP 功能所尋找的項目
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/18/2016
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 94349ed4-5351-4ee2-bbda-70813c9ed693
description: 敏感資訊類型尋找特定模式與證實來確保適當格式、 強制執行總和檢查碼，以及尋找相關的關鍵字或其他資訊。某些這項功能是由內部函數執行。本主題說明這些函數外觀，以協助您瞭解預先定義的敏感資訊類型的運作方式。
ms.openlocfilehash: 510f98e2b4e1d2480550f11026cf445be6ffc931
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013757"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 功能所尋找的項目

資料外洩防護 (DLP) 包含敏感資訊類型 (例如信用卡號與歐盟轉帳卡號)，您可以將這些類型用於 DLP 原則。這些敏感資訊類型是透過確保適當的格式、強制執行總和檢查碼，以及尋找相關關鍵字與其他資訊來尋找特定模式並加以證實。此部分功能是由內部函數執行。例如，信用卡卡號敏感資訊類型會使用函數尋找類似到期日的日期格式，以協助證實出現的數字的確是信用卡號碼。
  
本主題會說明這些函數的功能，讓您能更了解預先定義的敏感資訊類型。如需詳細資訊，請參閱[What the sensitive information types look for](what-the-sensitive-information-types-look-for.md)。
  
## <a name="funcusdate"></a>Func_us_date

此函數會尋找在美國常使用的格式是日期這包括格式"month/日/年 」、 「 月-日-年 」 和 「 月日年 」。名稱或縮寫的月數不區分大小寫。 
  
範例：
  
- 2016 年 12 月 2 日
    
- 2016、 Dec 2、
    
- dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
接受的月份名稱：
  
- 英文
    
  - 1 月、 年 2 月、 march、 April、 may、 年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月、 年 12 月
    
  - 年 1 月 2005 年 2 月 Mar.2004 年 4 月可能 6 年 7 月 ie Sept.年 10 月 11 Dec。
    
## <a name="funceudate"></a>Func_eu_date

此函數尋找的是歐盟 (與美國之外大部分地區) 常用的日期格式。這包含了「日/月/年」、「日-月-年」和「日 月 年」的格式。月份的名稱或縮寫不區分大小寫。
  
範例：
  
- 2 Dec 2016
    
- 02 dec 2016
    
- 2 年 12 月 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dec-2016
    
- 2-12-16
    
接受的月份名稱：
  
- 英文
    
  - 1 月、 年 2 月、 march、 April、 may、 年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月、 年 12 月
    
  - 年 1 月 2005 年 2 月 Mar.2004 年 4 月可能 6 年 7 月 ie Sept.年 10 月 11 Dec。
    
- 荷蘭文
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan 2 maart apr mei 6 月 7 月 8 月 sep sept oct okt 11 月 dec
    
- 法文
    
  - janvier、 février、 mars、 avril、 郵件、 juin juillet、 août、 septembre、 octobre、 novembre、 décembre
    
  - janv。févr。mars avril 郵件 juin juil。août sept。年 10 月 11 月。déc。
    
- 德文
    
  - jänuar、 februar、 märz、 April、 郵件、 juni juli 年 8 月、 年 9 月、 oktober，11，dezember
    
  - Jan。 / Jän。2005 年 2 月 März 2004 年 4 月郵件 Juni Juli ie Sept.Okt。11 Dez。
    
- 義大利文
    
  - gennaio、 febbraio、 marzo、 aprile、 maggio、 giugno、 luglio、 agosto、 settembre、 ottobre、 novembre、 dicembre
    
  - genn。febbr。mar。apr。magg。giugno luglio ag。是家。ott。11 月。dic。
    
- 葡萄牙文
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr 郵件 6 月 7 月過去 11 月 dez 出設定
    
- 西班牙文
    
  - enero、 febrero、 marzo、 abril、 mayo、 junio、 羅、 agosto、 septiembre、 octubre、 noviembre、 diciembre
    
  - enero 2。marzo abr.mayo jun.年 7 月。agosto sept./集。年 10 月 11 月。dic。
    
## <a name="funceudate1-deprecated"></a>Func_eu_date1 (已過時)

> [!NOTE]
> 因為它可支援僅葡萄牙文月份名稱，現在包含中已被取代此函數`Func_eu_date`上述的函數。 
  
此函數會尋找格式通常用於葡萄牙文的日期。此函數的格式是相同`Func_eu_date`、 受限於較只能在所用的語言。
  
範例：
  
- 2 Dez 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
接受的月份名稱：
  
- 葡萄牙文
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr 郵件 6 月 7 月過去 11 月 dez 出設定
    
## <a name="funceudate2-deprecated"></a>Func_eu_date2 (已過時)

> [!NOTE]
> 因為它可支援僅荷蘭文月份名稱，現在包含中已被取代此函數`Func_eu_date`上述的函數。 
  
此函數會尋找格式通常用於荷蘭文的日期。此函數的格式是相同`Func_eu_date`、 受限於較只能在所用的語言。
  
範例：
  
- 2 Mei 2016
    
- 02 mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
接受的月份名稱：
  
- 荷蘭文
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan 2 maart apr mei 6 月 7 月 8 月 sep sept oct okt 11 月 dec
    
## <a name="funcexpirationdate"></a>Func_expiration_date

此函數會尋找格式通常由信用卡和金融卡、 排除偏好的月數天的日期。此函數會比對格式為 「 月/年 」、 「 月-年"、"[月份名稱] year"和"[月份縮寫] 年 」 日期。名稱或縮寫的月數不區分大小寫。
  
範例
  
- MM/YY -- 例如，01/11 或 1/11
    
- MM/YYYY -- 例如，01/2011 或 1/2011
    
- MM-YY -- 例如，01-22 或 1-11
    
- MM-YYYY -- 例如，01-2000 或 1-2000
    
下列格式支援 YY 或 YYYY：
  
- Month-YYYY -- 例如，Jan-2010、january-2010、Jan-10 或 january-10
    
- Month YYYY -- 例如，'january 2010'、'Jan 2010'、'january 10' 或 'Jan 10'
    
- MonthYYYY -- 例如，'january2010'、'Jan2010'、'january10' 或 'Jan10'
    
- Month/YYYY-例如，' 1 月/2010 '或' Jan/2010 '或' 年 1 月/10 '或' Jan/10 '
    
接受的月份名稱：
  
- 英文
    
  - 1 月、 年 2 月、 march、 April、 may、 年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月、 年 12 月
    
  - Jan 2 Mar Apr 可能年 6 月 7 日 Sept Oct 11 月 Dec
    
## <a name="funcusaddress"></a>Func_us_address

此函數會尋找美國州名稱或是郵政縮寫，其後面接著有效的郵遞區號，就像郵遞地址所用的一樣。郵遞區號必須是與美國州名稱或縮寫關聯的其中一種正確郵遞區號。不能用標點符號或字母將美國州名稱和郵遞區號隔開。
  
範例：
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    

