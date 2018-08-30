---
title: 歐盟國家識別碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 2ea971bf-9434-4b61-b825-2bbd28ae6064
description: 本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟國家識別碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
ms.openlocfilehash: 29d2126b937ff46039284a74eb2a84f2ebbacb41
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526694"
---
# <a name="eu-national-identification-number"></a>歐盟國家識別碼

本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟國家識別碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
  
## <a name="austria"></a>奧地利

### <a name="format"></a>格式

24 個字元之字母、 數字和組合特殊字元
  
### <a name="pattern"></a>模式

24 個字元：
  
-  22 字母 （不區分大小寫）、 數字、 反斜線、 正斜線或加號 
    
- 兩個字母 （不區分大小寫）、 數字、 反斜線、 正斜線、 加號或等號
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_austria_eu_national_id_card`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_austria_eu_national_id_card`找到。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsaustriaeunationalidcard"></a>Keywords_austria_eu_national_id_card

奧地利身分識別號碼
  
國民身分識別號碼
  
身分識別號碼
  

national id
  
personalausweis republik österreich
  
## <a name="belgium"></a>比利時

如需詳細資訊，請參閱節"比利時國民 Number"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="bulgaria"></a>保加利亞

### <a name="format"></a>格式

十位數不含空格和分隔符號
  
### <a name="pattern"></a>模式

十位數不含空格和分隔符號
  
-  會對應至出生日期 (YYMMDD) 的六個數字 
    
- 會對應至出生順序的最上層的兩位數
    
- 會對應至性別的一個數字： 偶數數字 2 男和女性奇數數字
    
- 一次檢查數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_bulgaria_national_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_bulgaria_national_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_bulgaria_national_number`會找出符合模式的內容。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsbulgarianationalnumber"></a>Keywords_bulgaria_national_number

egn
  
egn #
  
保加利亞國際號碼
  
國際號碼
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
nationalnumber
  
bnn #
  
bnn
  
個人識別碼號碼
  
personalidnumber #
  
ЕДИНЕН ГРАЖДАНСКИ НОМЕР
  
edinen grazhdanski nomer
  
ЕГН
  
ЕГН #
  
## <a name="croatia"></a>克羅埃西亞

如需詳細資訊，請參閱節"克羅埃西亞 Identity Number"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="cyprus"></a>賽普勒斯

### <a name="format"></a>格式

十位數不含空格和分隔符號
  
### <a name="pattern"></a>模式

 十位數 
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_cyprus_eu_national_id_card`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_cyprus_eu_national_id_card`找到。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordscypruseunationalidcard"></a>Keywords_cyprus_eu_national_id_card

識別碼卡卡號
  
國家識別碼
  
個人識別碼號碼
  
身分識別卡卡號
  
ΤΑΥΤΟΤΗΤΑΣ
  
## <a name="czech-republic"></a>捷克

如需詳細資訊，請參閱節"捷克文國民身分識別 Number"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="denmark"></a>丹麥

如需詳細資訊，請參閱節"丹麥個人識別碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="estonia"></a>愛沙尼亞

### <a name="format"></a>格式

11 位數不含空格和分隔符號
  
### <a name="pattern"></a>模式

11 位數：
  
- 會對應至性別和出生的 century 的一個數字 (奇數的數字 2 男，偶數女性、 1-2: 19 century ； 3-4： 20 century; 5-6： 第 21 世紀)
    
- 會對應至出生 (YYMMDD) 的日期的六個數字
    
- 會對應至分隔出生日期相同的人員序號的三個位數
    
- 一次檢查數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_estonia_eu_national_id_card`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_estonia_eu_national_id_card`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_estonia_eu_national_id_card`會找出符合模式的內容。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsestoniaeunationalidcard"></a>Keywords_estonia_eu_national_id_card

個人識別碼的程式碼
  
個人識別碼
  
國家識別碼
  
國際號碼
  
個人識別碼號碼
  
personalidnumber #
  
ik
  
isikukood
  
識別碼 kaart
  
## <a name="finland"></a>芬蘭

如需詳細資訊，請參閱節"芬蘭國家識別碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="france"></a>法國

如需詳細資訊，請參閱節"法國國民識別碼卡片 (CNI)"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="germany"></a>德國

如需詳細資訊，請參閱節"德國識別卡 Number"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="greece"></a>希臘

如需詳細資訊，請參閱節"希臘國家識別碼卡片"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

11 位數
  
### <a name="pattern"></a>模式

11 位數：
  
-  會對應至性別 （1-2 男 2 女性、 其他號碼是也可能的市民出生 1900年之前或具有雙公民公民） 的一個數字 
    
- 會對應至出生日期 (YYMMDD) 的六個數字
    
- 會對應到序號的三個位數
    
- 一次檢查數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_hungary_eu_national_id_card`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_hungary_eu_national_id_card`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_hungary_eu_national_id_card`會找出符合模式的內容。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordshungaryeunationalidcard"></a>Keywords_hungary_eu_national_id_card

個人識別碼
  
identification number

  
個人識別碼號碼
  
személyazonosító igazolvány
  
## <a name="ireland"></a>Ireland

### <a name="format"></a>格式

九個字元之字母、 數字和組合中所指定的型態的空間
  
### <a name="pattern"></a>模式

九個字元之字母、 數字和組合中所指定的型態的空間
  
從到現在的年 1 月 2013 01 日
  
-  七位數 
    
- 一次檢查數字
    
- 一個空格或大寫字母"W"（區分大小寫）
    
01 年 1 月 2013年前的：
  
-  七位數 
    
- 一次檢查數字
    
- 一個空格或大寫字母 （區分大小寫）
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數會找出符合模式的內容。
    
- 從關鍵字是找到。
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數會找出符合模式的內容。
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsirelandeunationalidcard"></a>Keywords_ireland_eu_national_id_card

個人公用健保號碼
  
pps 無
  
收益及社會保險號碼
  
rsi 無
  
個人識別碼
  
identification number

  
個人識別碼號碼
  
uimhir phearsanta seirbhíse poiblí
  
uimh。psp
  
## <a name="italy"></a>義大利

### <a name="format"></a>格式

16 個字元之字母和組合中所指定的型態的數字
  
### <a name="pattern"></a>模式

16 個字元字母和數字的組合：
  
- 會對應至系列名稱中前三個母音的三個字母
    
- 會對應至第一個、 第三和第四的三個字母母音中第一個名稱
    
- 會對應至最後一出生年的數字的兩位數
    
- 對應於信件的月出生的一個字母 — 字母依字母順序使用，但僅限字母 A 到 E、 H、 L、 M、 P、 R 以 T 可用 （即得出年 1 月是 A 及年 10 月為 R）
    
- 會對應至出生的月的一天的兩個位數 — 以區分 genders、 40 新增的女性出生的天
    
- 會對應至區碼出生人員 municipality 特有的四個位數 （國家全代碼可用外部的國家/地區）
    
- 一個同位數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_italy_eu_national_id_card`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_italy_eu_national_id_card`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_italy_eu_national_id_card`會找出符合模式的內容。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsitalyeunationalidcard"></a>Keywords_italy_eu_national_id_card

個人的程式碼
  
個人的程式碼數目
  
個人憑證數目
  
會計程式碼
  
personalcodeno #
  
個人識別碼號碼
  
個人識別碼的程式碼
  
codice personale
  
numero certificato personale
  
numero personale
  
numero 識別碼 personale
  
codice 識別碼 personale
  
codice fiscale
  
## <a name="italy"></a>義大利

### <a name="format"></a>格式

11 位數與指定之格式的連字號
  
### <a name="pattern"></a>模式

11 位數和連字號：
  
-  會對應至出生日期 (DDMMYY) 的六個數字 
    
- 一個連字號
    
- 會對應至出生 （"0"的 19 century、 20 century 為"1"和"2"第 21 世紀） 的 century 的一個數字
    
- 隨機產生的四位數
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_latvia_eu_national_id_card`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_latvia_eu_national_id_card`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_latvia_eu_national_id_card`會找出符合模式的內容。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordslatviaeunationalidcard"></a>Keywords_latvia_eu_national_id_card

個人的程式碼
  
個人的程式碼數目
  
個人憑證數目
  
personalcodeno #
  
個人識別碼號碼
  
個人識別碼的程式碼
  
人物代表 kods
  
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

11 位數不含空格和分隔符號
  
### <a name="pattern"></a>模式

不含空格和分隔符號的 11 位數：
  
- 會對應至這個人性別和出生的 century 的一個數字
    
-  會對應至出生日期 (YYMMDD) 的六個數字 
    
- 會對應至出生的日期序號的三個位數
    
- 一次檢查數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_lithuania_eu_national_id_card`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_lithuania_eu_national_id_card`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_lithuania_eu_national_id_card`會找出符合模式的內容。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordslithuaniaeunationalidcard"></a>Keywords_lithuania_eu_national_id_card

個人數字碼
  
唯一識別數字
  
市民健保號碼
  
唯一識別數字
  
uniqueidentityno #
  
個人的程式碼。
  
asmeninis skaitmeninis kodas
  
unikalus identifikavimo numeris
  
piliečio paslaugos numeris
  
unikalus identifikavimo kodas
  
asmens kodas。
  
## <a name="luxemburg"></a>盧森堡

### <a name="format"></a>格式

11 位數不含空格和分隔符號
  
### <a name="pattern"></a>模式

11 位數
  
- 會對應至這個人性別和出生的 century 的一個數字
    
-  會對應至出生日期 (YYMMDD) 的六個數字 
    
- 會對應至出生的日期序號的三個位數
    
- 一次檢查數字
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_luxemburg_eu_national_id_card`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_luxemburg_eu_national_id_card`找到。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsluxemburgeunationalidcard"></a>Keywords_luxemburg_eu_national_id_card

個人識別碼
  
個人識別碼號碼
  
personalidno #
  
唯一識別碼
  
personalidnumber #
  
唯一識別碼機碼
  
個人識別碼的程式碼
  
uniqueidkey #
  
個別的程式碼
  
個別的識別碼
  
eindeutige 識別碼 nummer
  
eindeutige 識別碼
  
識別碼 personnelle
  
numéro d'identification 人員
  
idpersonnelle #
  
persönliche identifikationsnummer
  
eindeutigeid #
  
## <a name="malta"></a>馬爾他

### <a name="format"></a>格式

後面接著一個字母的七位數字
  
### <a name="pattern"></a>模式

後面接著一個字母的七位數字：
  
-  七位數 
    
- 一個大寫字母 （區分大小寫）
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_malta_eu_national_id_card`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_malta_eu_national_id_card`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：
  
- 規則運算式`Regex_malta_eu_national_id_card`會找出符合模式的內容。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsmaltaeunationalidcard"></a>Keywords_malta_eu_national_id_card

個人數字碼
  
唯一識別數字
  
市民健保號碼
  
唯一識別數字
  
uniqueidentityno #
  
kodiċi numerali personali
  
numru 東西 ' identifikazzjoni uniku
  
numru tas servizz taċ ċittadin
  
numru 東西 ' identità uniku
  
## <a name="netherlands"></a>荷蘭

### <a name="format"></a>格式

不含空格或分隔符號的九個位數
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_netherlands_eu_national_id_card`會找出符合模式的內容。 
    
- 從關鍵字是找到。
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_netherlands_eu_national_id_card`會找出符合模式的內容。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsnetherlandseunationalidcard"></a>Keywords_netherlands_eu_national_id_card

個人數字碼
  
唯一識別數字
  
市民健保號碼
  
唯一識別數字
  
uniqueidentityno #
  
bsn
  
bsn #
  
persoonlijke numerieke 程式碼
  
uniek identificatienummer
  
burgerservicenummer
  
uniek identiteitsnummer
  
## <a name="poland"></a>波蘭

如需詳細資訊，請參閱節"波蘭國家識別碼 (PESEL)"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="portugal"></a>葡萄牙

如需詳細資訊，請參閱節"葡萄牙市民卡卡號"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="romania"></a>羅馬尼亞

### <a name="format"></a>格式

不含空格和分隔字元 13 數字
  
### <a name="pattern"></a>模式

13 位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_romania_eu_national_id_card`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_romania_eu_national_id_card`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_romania_eu_national_id_card`會找出符合模式的內容。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsromaniaeunationalidcard"></a>Keywords_romania_eu_national_id_card

個人數字碼
  
唯一識別數字
  
cnp
  
cnp #
  
釘選
  
pin #
  
保險數目
  
insurancenumber #
  
唯一識別數字
  
uniqueidentityno #
  
cod 數值個人
  
cod identificare 個人
  
cod unic identificare
  
număr 個人 unic
  
număr identitate
  
număr identificare 個人
  
număridentitate #
  
codnumericpersonal #
  
numărpersonalunic #
  
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

包含一個反斜線的十位數
  
### <a name="pattern"></a>模式

包含一個反斜線十位數：
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_slovakia_eu_national_id_card`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_slovakia_eu_national_id_card`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_slovakia_eu_national_id_card`會找出符合模式的內容。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsslovakiaeunationalidcard"></a>Keywords_slovakia_eu_national_id_card

出生數目
  
國家識別碼
  
個人識別碼
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
國際號碼
  
個人識別碼號碼
  
personalidnumber #
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="slovenia"></a>斯洛維尼亞

### <a name="format"></a>格式

不含空格或分隔字元 13 數字
  
### <a name="pattern"></a>模式

在指定的型態的數字 13:
  
-  會對應至出生日期 (DDMMLLL)"LLL"對應至最後一出生年的三個字的七位數字 
    
- 會對應至出生的區域的兩位數
    
- 針對的人員在同一天 (000-為 2 男的 499) 和 500 位 999 的女性出生對應的性別與序號組合的三個位數
    
- 一次檢查數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_slovenia_eu_national_id_card`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_slovenia_eu_national_id_card`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_slovenia_eu_national_id_card`會找出符合模式的內容。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordssloveniaeunationalidcard"></a>Keywords_slovenia_eu_national_id_card

個人數字碼
  
唯一識別數字
  
註冊的唯一號碼
  
唯一識別數字
  
uniqueidentityno #
  
唯一的主要市民數
  
edinstvena identifikacijska številka
  
uniqueidentityno #
  
edinstvena številka glavnega državljana
  
emšo
  
## <a name="spain"></a>西班牙

### <a name="format"></a>格式

後面接著一個字元的七位數字
  
### <a name="pattern"></a>模式

後面接著一個字元的七位數字
  
- 七位數
    
- 一個數字或字母 （不區分大小寫）
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_spain_eu_national_id_card`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_spain_eu_national_id_card"`找到。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsspaineunationalidcard"></a>Keywords_spain_eu_national_id_card

dni
  
國家識別碼
  
國民身分識別號碼
  
保險數目
  
個人識別碼
  
國民身分識別
  
個人身分識別沒有
  
唯一識別數字
  
nationalidno #
  
uniqueid #
  
dni #
  
nationalid #
  
nie #
  
nie
  
nienúmero #
  
nie número
  
documento nacional de identidad
  
identidad único
  
número nacional identidad
  
dni número
  
dninúmero #
  
identidadúnico #
  
## <a name="sweden"></a>瑞典

如需詳細資訊，請參閱節"瑞典國民身分證號"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="see-also"></a>另請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

