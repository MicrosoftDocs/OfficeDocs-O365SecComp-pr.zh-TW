---
title: DLP 功能所尋找的項目
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 敏感資訊類型會尋找特定模式, 並透過確保正確的格式設定、強制執行校驗和尋找相關的關鍵字或其他資訊來 corroborate 它。 某些功能是由內建函式執行。 本主題說明這些函數所尋找的內容, 以協助您瞭解預先定義的機密資訊類型的運作方式。
ms.openlocfilehash: 044920a7ff28ffc1c4338a642bc130ee07ef7264
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077999"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 功能所尋找的項目

資料遺失防護 (DLP) 包含敏感資訊類型, 例如信用卡號碼和歐盟借貸卡號碼, 可供您在 DLP 原則中使用。 這些機密資訊類型會尋找特定模式, 並透過確保正確的格式設定、強制執行校驗和尋找相關的關鍵字或其他資訊來 corroborate 它。 某些功能是由內建函式執行。 例如, 信用卡號碼敏感資訊類型會使用函數來尋找格式類似到期日的日期, 以協助 corroborate 號碼是信用卡號碼。
  
本主題說明這些函數所尋找的內容, 以協助您瞭解預先定義的機密資訊類型的運作方式。 如需詳細資訊, 請參閱[敏感資訊類型的外觀](what-the-sensitive-information-types-look-for.md)。
  
## <a name="funcusdate"></a>Func_us_date

此函數會以美國常用的格式來尋找日期。這包括格式「月/日/年」、「月-日-年」和「年月年」。 月份的名稱或縮寫不區分大小寫。 
  
範例:
  
- 2016年12月2日
    
- 2016年12月2日
    
- dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- 十二月-2-2016
    
- 12-2-16
    
公認的月份名稱:
  
- 英文
    
  - 一月份、二月、三月、四月、5、六月、七月、八月、九月、十二月、十二月、十二月、十二月、十二月、十二月、十二月、十二月
    
  - Jan 年3月4日當年5月11月11月。
    
## <a name="funceudate"></a>Func_eu_date

此函數會以歐盟常用的格式來尋找日期 (以及美國以外的大多數位置)。 這包括 [日/月/年]、[日-月-年] 和「日月年度」的格式。 月份的名稱或縮寫不區分大小寫。
  
範例:
  
- 2十二月2016
    
- 02十二月2016
    
- 2十二月16
    
- 2/12/2016
    
- 02/12/16
    
- 2-十二月-2016
    
- 2-12-16
    
公認的月份名稱:
  
- 英文
    
  - 一月份、二月、三月、四月、5、六月、七月、八月、九月、十二月、十二月、十二月、十二月、十二月、十二月、十二月、十二月
    
  - Jan 年3月4日當年5月11月11月。
    
- 荷蘭文
    
  - januari、februari、maart、四月、mei、juni、juli、augustus、九月、ocktober、十月、十二月、十二月
    
  - jan 二月 maart apr mei 年9月8日當年9月 okt 年11月
    
- 法文
    
  - janvier、février、火星、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre
    
  - janv. févr. 火星 avril mai juin juil。 août 年9月。 10. 11. déc.
    
- 德文
    
  - jänuar、februar、märz、四月、mai、juni juli、八月、九月、oktober、十一月、dezember
    
  - Jan./Jän。 März 年4月 Juli Juni。 Dez 年11月。
    
- 義大利文
    
  - gennaio、febbraio、marzo、aprile、maggio、giugno、luglio、agosto、settembre、ottobre、novembre、dicembre
    
  - genn. febbr. mar. 4. magg. giugno luglio ag。 sett. ott. 11. .dic.
    
- 葡萄牙文
    
  - janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - jan fev mar abr mai 06 年前設定11月 dez
    
- 西班牙文
    
  - enero、febrero、marzo、abril、mayo、junio、julio、agosto、septiembre、octubre、noviembre、diciembre
    
  - enero 年2月。 marzo abr。 mayo 年6月。 年7月. agosto/set。 10. 11. .dic.
    
## <a name="funceudate1-deprecated"></a>Func_eu_date1 (已過時)

> [!NOTE]
> 此函數已被取代, 因為它只支援葡萄牙文月份名稱, 而這些名稱現在`Func_eu_date`已包含于上述函數中。 
  
此函數會以葡萄牙文常用的格式來尋找日期。 此函數`Func_eu_date`的格式與使用的語言不同。
  
範例:
  
- 2 Dez 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
公認的月份名稱:
  
- 葡萄牙文
    
  - janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - jan fev mar abr mai 06 年前設定11月 dez
    
## <a name="funceudate2-deprecated"></a>Func_eu_date2 (已過時)

> [!NOTE]
> 此函數已被取代, 因為它只支援荷蘭月份名稱, 而該名稱現在`Func_eu_date`已包含于上述函數中。 
  
此函數會以荷蘭文常用的格式來尋找日期。 此函數`Func_eu_date`的格式與使用的語言不同。
  
範例:
  
- 2 Mei 2016
    
- 02 mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
公認的月份名稱:
  
- 荷蘭文
    
  - januari、februari、maart、四月、mei、juni、juli、augustus、九月、ocktober、十月、十二月、十二月
    
  - jan 二月 maart apr mei 年9月8日當年9月 okt 年11月
    
## <a name="funcexpirationdate"></a>Func_expiration_date

此函數會以信用卡和轉帳卡所使用的格式來尋找日期, 而不是以月為單位來排除天數。 此函數會比對 "month/year"、"month"、"[month] year" 和 "[month 縮略語] year" 格式的日期。 月份的名稱或縮寫不區分大小寫。
  
範例:
  
- MM/YY--例如, 01/11 或1/11
    
- MM/YYYY--例如, 01/2011 或1/2011
    
- MM-YY--例如, 01-22 或1-11
    
- MM-YYYY--例如, 01-2000 或1-2000
    
下列格式支援 YY 或 YYYY:
  
- Month--例如。Jan-2010 或一月-2010 或 Jan-10 或一月-10
    
- Month YYYY--例如, ' 一月份 2010 ' 或 ' Jan 2010 ' 或 ' 一月 10 ' 或 ' Jan 10 '
    
- MonthYYYY--例如 "january2010" 或 "Jan2010" 或 "january10" 或 "Jan10"
    
- Month/YYYY--例如, ' 一月份/2010 ' 或 ' Jan/2010 ' 或 ' Jan/10 ' 或 ' Jan/10 '
    
公認的月份名稱:
  
- 英文
    
  - 一月份、二月、三月、四月、5、六月、七月、八月、九月、十二月、十二月、十二月、十二月、十二月、十二月、十二月、十二月
    
  - Jan 年2月3月4日當年11月11月8月9日
    
## <a name="funcusaddress"></a>Func_us_address

此函數會尋找美國狀態名稱或郵政縮寫, 後面接著有效的郵遞區號, 就像在郵政位址中使用一樣。 郵遞區號必須是與美國狀態名稱或縮寫相關聯的正確郵遞區號之一。 美國的狀態名稱和郵遞區號不能以標點符號或字母隔開。
  
範例:
  
- 華盛頓98052
    
- 華盛頓98052-9998
    
- WA 98052
    
- WA 98052-9998
    

