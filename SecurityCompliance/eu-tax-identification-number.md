---
title: 歐盟稅識別碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: 本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟稅識別碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
ms.openlocfilehash: 5192496b393d15fd6d063e09c9bfe1cb3dd7e2dd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526727"
---
# <a name="eu-tax-identification-number"></a>歐盟稅識別碼

本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟稅識別號碼 （錫） 敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
  
## <a name="austria"></a>奧地利

### <a name="format"></a>格式

選擇性連字號和正斜線的九個位數
  
### <a name="pattern"></a>模式

選擇性連字號和正斜線的九個位數：
  
-  兩位數 
    
- 一個連字號 (選用)
    
- 三位數
    
- 一個正斜線 (選用)
    
- 四位數
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_austria_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_austria_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_austria_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsaustriaeutaxfilenumber"></a>Keywords_austria_eu_tax_file_number

稅編號
  
數字
  
稅註冊編號
  
tax id

  
st.nr。
  
steuernummer
  
## <a name="belgium"></a>比利時

### <a name="format"></a>格式

11 位數不含空格和分隔符號
  
### <a name="pattern"></a>模式

11 位數：
  
- 兩位數
    
- "0"或者"1"
    
- 一個數字
    
- "0"或"1"或"2"或者"3" 
    
- 六位數
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_belgium_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_belgium_eu_tax_file_number`找到。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsbelgiumeutaxfilenumber"></a>Keywords_belgium_eu_tax_file_number

稅編號
  
國際號碼
  
稅註冊編號
  
tax id

  
n 如果
  
n 如果 #
  
numéro de registre national
  
numéro d'identification fiscale
  
## <a name="bulgaria"></a>保加利亞

### <a name="format"></a>格式

十位數不含空格和分隔符號
  
### <a name="pattern"></a>模式

10 位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_bulgaria_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_bulgaria_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_bulgaria_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsbulgariaeutaxfilenumber"></a>Keywords_bulgaria_eu_tax_file_number

bucn
  
統一民事數目
  
bucn #
  
uniformcivilnumber #
  
統一民事識別碼
  
統一民事否
  
egn
  
保加利亞統一民事數目
  
uniformcivilno #
  
egn #
  
УНИФОРМ ГРАЖДАНСКИ НОМЕР
  
Униформ 識別碼
  
Униформ граждански 識別碼
  
УНИФОРМ ГРАЖДАНСКИ НЕ
  
## <a name="croatia"></a>克羅埃西亞

### <a name="format"></a>格式

任何空格或分隔符號 11 位數
  
### <a name="pattern"></a>模式

11 位數：
  
- 十位數，隨機選擇
    
- 一次檢查數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_croatia_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_croatia_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_croatia_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordscroatiaeutaxfilenumber"></a>Keywords_croatia_eu_tax_file_number

稅編號
  
稅
  
tax id

  
oid
  
oid #
  
porezni broj
  
## <a name="cyprus"></a>賽普勒斯

### <a name="format"></a>格式

八個位數和指定的型態的其中一個字母
  
### <a name="pattern"></a>模式

八個位數和一個字母：
  
-  "0" 
    
- 七位數
    
- 一個字母 （不區分大小寫）
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_cyprus_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_cyprus_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_cyprus_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordscypruseutaxfilenumber"></a>Keywords_cyprus_eu_tax_file_number

稅編號
  
稅
  
tax id

  
稅識別程式碼
  
tic
  
tic #
  
ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ
  
ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
## <a name="czech-republic"></a>捷克

### <a name="format"></a>格式

使用選用的反斜線的九個或十位數
  
### <a name="pattern"></a>模式

具有選用 backslashl 9 或 10 位數：
  
- 六位數 
    
- 反斜線 （選用）
    
- 三個或四位數字
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_czech_republic_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_czech_republic_eu_tax_file_number`找到。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsczechrepubliceutaxfilenumber"></a>Keywords_czech_republic_eu_tax_file_number

稅編號
  
稅
  
tax id

  
個人的數字
  
daňové číslo
  
osobní číslo
  
## <a name="denmark"></a>丹麥

### <a name="format"></a>格式

十個包含連字號的數字
  
### <a name="pattern"></a>模式

包含 hyphenl 十位數：
  
-  會對應至出生日期 (DDMMYY) 的六個數字 
    
- 一個連字號
    
- 會對應至其中的第一個數字會對應至出生的 century 序號的四個字和最後一個數字會對應至個人的性別 （2 男和即使女性奇數）
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_denmark_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_denmark_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_denmark_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsdenmarkeutaxfilenumber"></a>Keywords_denmark_eu_tax_file_number

稅編號
  
稅
  
tax id

  
cpr 數目
  
cpr #
  
skat nummer
  
skat 識別碼
  
## <a name="estonia"></a>愛沙尼亞

### <a name="format"></a>格式

任何空格或分隔符號 11 位數
  
### <a name="pattern"></a>模式

11 位數：
  
-  會對應至性別和出生其中奇數指出 2 男和偶數指出女性，如下所示的 century 的一個數字： 1，2 19 的 century;3、 4 20 的 century;與 5、 6 第 21 世紀 
    
- 會對應至出生日期 (YYMMDD) 的六個數字
    
- 會對應至分隔出生日期相同的人員序號的三個位數
    
- 一次檢查數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_estonia_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_estonia_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_estonia_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsestoniaeutaxfilenumber"></a>Keywords_estonia_eu_tax_file_number

稅編號
  
稅
  
tax id

  
個人的程式碼
  
maksunumber
  
maksu 識別碼
  
isikukood
  
## <a name="finland"></a>芬蘭

### <a name="format"></a>格式

信件的數字，11 個字元組合，並加號與減號
  
### <a name="pattern"></a>模式

信件的數字，11 個字元組合，並加號與減號：
  
- 六位數
    
- 下列其中之一： 加號、 減號、 或字母"A"（不區分大小寫） 其中加號表示出生 1800年 1899年之間減號登入表示出生之間 1900年-1999年和"A"表示出生 2000年及之後
    
- 三位數
    
- 一個字母或一個數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_finland_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_finland_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_finland_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsfinlandeutaxfilenumber"></a>Keywords_finland_eu_tax_file_number

identification number

  
個人識別碼
  
身分識別號碼
  
芬蘭國家識別碼
  
personalidnumber #
  
國家識別碼
  
識別碼號碼
  
國家識別碼沒有。
  
國家識別碼號碼
  
識別碼沒有
  
tunnistenumero
  
henkilötunnus
  
yksilöllinen henkilökohtainen tunnistenumero
  
ainutlaatuinen henkilökohtainen tunnus
  
identiteetti numero
  
suomen kansallinen henkilötunnus
  
henkilötunnusnumero #
  
kansallisen tunnistenumero
  
tunnusnumero
  
kansallinen tunnus numero
  
## <a name="france"></a>法國

### <a name="format"></a>格式

13 個人和實體的九個位數的數字
  
### <a name="pattern"></a>模式

針對個人的數字 13:
  
- 必須是 0、 1、 2 或 3 的一個數字
    
- 12 位數
    
實體的九個位數
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_france_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_france_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_france_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsfranceeutaxfilenumber"></a>Keywords_france_eu_tax_file_number

稅識別碼
  
稅編號
  
tax id

  
numéro d'identification fiscale
  
## <a name="germany"></a>德國

### <a name="format"></a>格式

11 位數不含空格和分隔符號
  
### <a name="pattern"></a>模式

11 位數：
  
-  十位數 
    
- 一次檢查數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_germany_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_germany_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_germany_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsgermanyeutaxfilenumber"></a>Keywords_germany_eu_tax_file_number

稅編號
  
稅否]。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
稅識別碼
  
無法稅識別碼。
  
steuernummer
  
steuer 識別碼
  
steueridentifikationsnummer
  
## <a name="greece"></a>希臘

### <a name="format"></a>格式

不含空格和分隔符號的九個位數
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_greece_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_greece_eu_tax_file_number`找到。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsgreeceeutaxfilenumber"></a>Keywords_greece_eu_tax_file_number

afm
  
tin

  
無法稅識別碼。
  
無法稅識別碼
  
稅識別碼
  
稅登錄編號
  
無法稅登錄。
  
afm #
  
錫 #
  
taxidno #
  
taxregistryno #
  
ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
aφμ
  
aφμ αριθμός
  
ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ。
  
ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

任何空格或分隔符號十位數
  
### <a name="pattern"></a>模式

十位數：
  
-  必須是"8"的一個數字 
    
- 會對應至日期之間的天數的五個位數 01/01/1867年和個別的出生的日期
    
- 三個對應來區分個人在同一天出生依照機率產生的號碼的數字
    
- 一次檢查數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_hungary_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_hungary_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_hungary_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordshungaryeutaxfilenumber"></a>Keywords_hungary_eu_tax_file_number

匈牙利文稅識別碼
  
匈牙利文錫
  
稅 id 號碼
  
vat 編號
  
無法稅授權單位
  
稅識別碼稅身分識別號碼
  
taxidnumber #
  
錫 #
  
hungatiantin #
  
無法稅識別碼
  
taxidno #
  
adóazonosító szám
  
adószám
  
adóhatóság szám
  
## <a name="ireland"></a>Ireland

### <a name="format"></a>格式

後面接著任何空格或分隔符號信件的七位數字
  
### <a name="pattern"></a>模式

後面接著一個字母的七位數字：
  
-  七位數 
    
- 一個字母 （不區分大小寫）
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_ireland_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_ireland_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_ireland_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsirelandeutaxfilenumber"></a>Keywords_ireland_eu_tax_file_number

公共服務沒有
  
個人公用服務沒有
  
pps 無
  
個人服務否
  
pps service 否
  
ppsno #
  
愛爾蘭 pps 無
  
publicserviceno #
  
個人公用健保號碼
  
uimhir phearsanta seirbhíse poiblí
  
pps uimh
  
uimhir aitheantais phearsanta
  
## <a name="italy"></a>義大利

### <a name="format"></a>格式

16 信件與指定的型態的數字
  
### <a name="pattern"></a>模式

16 字母和數字：
  
-  會對應至系列名稱中前三個母音的三個字母 
    
- 會對應至第一個、 第三和第四的三個字母母音中第一個名稱
    
- 會對應至最後一出生年的數字的兩位數
    
- 一個數字對應至出生月 — 字母依字母順序使用，但僅限字母 A 到 E、 H、 L、 M、 P、 R 以 T 可用 （即得出年 1 月是 A 及年 10 月為 R）
    
- 會對應至出生 40 其中加入來區分與男生女生成績的出生的一天的每月一天的兩位數
    
- 會對應至特定出生人員 municipality 區碼的四個字 — 外部的國家/地區使用全國家/地區碼
    
- 一次檢查數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_italy_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_italy_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_italy_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsitalyeutaxfilenumber"></a>Keywords_italy_eu_tax_file_number

稅編號
  
稅否]。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
會計程式碼
  
codice fiscale
  
## <a name="latvia"></a>拉脫維亞

### <a name="format"></a>格式

任何空格或分隔符號 11 位數
  
### <a name="pattern"></a>模式

在指定的型態 11 位數
  
-  會對應至出生 (DDMMYY) 的日期的六個數字 
    
- 會對應至其中"0"會對應至 19 century、"1"會對應至 20 century 及"2"會對應至第 21 世紀出生的 century 的一個數字
    
- 四位數
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_latvia_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_latvia_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_latvia_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordslatviaeutaxfilenumber"></a>Keywords_latvia_eu_tax_file_number

稅編號
  
稅否]。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
稅識別碼
  
無法稅識別碼。
  
nodokļa numurs
  
nodokļu identifikācijas numurs
  
nodokļu identifikācija numurs
  
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

不含空格或分隔符號 11 位數
  
### <a name="pattern"></a>模式

11 位數
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_lithuania_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_lithuania_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_lithuania_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordslithuaniaeutaxfilenumber"></a>Keywords_lithuania_eu_tax_file_number

稅編號
  
稅否]。
  
稅否 #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
稅識別碼
  
無法稅識別碼。
  
mokesčių 識別碼
  
mokesčių numeris
  
mokesčių identifikavimas numeris
  
## <a name="luxemburg"></a>盧森堡

### <a name="format"></a>格式

任何空格或分隔字元 13 數字
  
### <a name="pattern"></a>模式

13 位數：
  
-  11 位數 
    
- 二位數檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_luxemburg_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_luxemburg_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_luxemburg_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsluxemburgeutaxfilenumber"></a>Keywords_luxemburg_eu_tax_file_number

稅編號
  
稅否]。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
稅識別碼
  
無法稅識別碼。
  
steuernummer
  
steuer 識別碼
  
steueridentifikationsnummer
  
## <a name="malta"></a>馬爾他

### <a name="format"></a>格式

馬爾他 nationals 的： 7 位數和指定的型態的其中一個字母
  
非馬爾他文 nationals 和馬爾他實體： 9 的數字
  
### <a name="pattern"></a>模式

馬爾他 nationals: 7 位數和一個字母
  
-  七位數 
    
- 一個字母 （不區分大小寫）
    
非馬爾他文 nationals 和馬爾他實體： 9 的數字
  
-  九位數 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_malta_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_malta_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：
  
- 此函數`Func_malta_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsmaltaeutaxfilenumber"></a>Keywords_malta_eu_tax_file_number

稅編號
  
稅否]。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
稅識別碼
  
無法稅識別碼。
  
numru 且 taxxa
  
識別碼且 taxxa
  
numru 東西 ' identifikazzjoni 且 taxxa
  
## <a name="netherlands"></a>荷蘭

### <a name="format"></a>格式

不含空格或分隔符號的九個位數
  
### <a name="pattern"></a>模式

九位數 
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_netherlands_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_netherlands_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_netherlands_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsnetherlandseutaxfilenumber"></a>Keywords_netherlands_eu_tax_file_number

荷蘭稅識別碼
  
荷蘭稅識別碼
  
荷屬安的稅識別碼
  
荷屬安的稅識別碼
  
稅識別碼
  
荷蘭文稅識別碼
  
荷蘭文稅識別碼
  
tax id

  
稅識別碼 #
  
稅編號
  
稅否 #
  
稅 #
  
tin

  
錫 #
  
荷蘭錫
  
荷屬安的錫
  
荷蘭 belasting identificatienummer
  
identificatienummer van belasting
  
identificatienummer belasting
  
荷蘭 belasting identificatie
  
荷蘭 belasting 識別碼 nummer
  
荷蘭 belastingnummer
  
btw nummer
  
文拚字檢查 belasting identificatie
  
## <a name="poland"></a>波蘭

### <a name="format"></a>格式

任何空格或分隔符號十一份數字
  
### <a name="pattern"></a>模式

另外的數字
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_poland_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_poland_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_poland_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordspolandeutaxfilenumber"></a>Keywords_poland_eu_tax_file_number

稅編號
  
稅否]。
  
taxno #
  
taxnumber #
  
taxnumber
  
nip
  
nip #
  
tax id

  
稅識別碼 #
  
nip 識別碼
  
nip 識別碼 #
  
稅識別碼
  
無法稅識別碼。
  
vat 編號
  
vat 否]。
  
vatno #
  
增值稅識別碼
  
增值稅識別碼 #
  
數目 identyfikacji podatkowej
  
polski 數目 identyfikacji podatkowej
  
numeridentyfikacjipodatkowej #
  
## <a name="portugal"></a>葡萄牙

### <a name="format"></a>格式

任何空格或分隔符號的九個位數
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_portugal_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_portugal_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_portugal_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsportugaleutaxfilenumber"></a>Keywords_portugal_eu_tax_file_number

稅編號
  
稅否]。
  
taxno #
  
taxnumber #
  
taxnumber
  
n 如果
  
n 如果 #
  
numero 會計
  
número de identificação 會計
  
## <a name="romania"></a>羅馬尼亞

### <a name="format"></a>格式

任何空格或分隔字元 13 數字
  
### <a name="pattern"></a>模式

13 位數
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_romania_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_romania_eu_tax_file_number`找到。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsromaniaeutaxfilenumber"></a>Keywords_romania_eu_tax_file_number

tax id

  
稅 id 號碼
  
無法稅檔案
  


tax file number
  
稅否
  
稅編號
  
taxid #
  
taxno #
  
識別碼 ul taxei
  
numărul de identificare fiscală
  
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

任何空格或分隔符號的 10 位數
  
### <a name="pattern"></a>模式

10 位數
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_slovakia_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_slovakia_eu_tax_file_number`找到。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsslovakiaeutaxfilenumber"></a>Keywords_slovakia_eu_tax_file_number

tax id

  
稅 id 號碼
  
鐵皮識別碼
  
鐵皮否
  
斯洛伐克鐵皮識別碼
  
tin

  
無法稅檔案
  


tax file number
  
稅否
  
稅編號
  
taxid #
  
taxno #
  
daňové identifikačné číslo
  
daňové číslo
  
daňové číslo súboru
  
## <a name="slovenia"></a>斯洛維尼亞

### <a name="format"></a>格式

任何空格或分隔字元的八個位數
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_slovenia_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_slovenia_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_slovenia_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordssloveniaeutaxfilenumber"></a>Keywords_slovenia_eu_tax_file_number

tax id

  
稅 id 號碼
  
鐵皮識別碼
  
鐵皮否
  
斯洛維尼亞文鐵皮識別碼
  
tin

  
無法稅檔案
  


tax file number
  
稅否
  
稅編號
  
taxid #
  
taxno #
  
identifikacijska številka davka
  
davčna številka
  
Številka davčne datoteke
  
## <a name="spain"></a>西班牙

### <a name="format"></a>格式

七個或八個位數和中指定的型態的一或兩個字母
  
### <a name="pattern"></a>模式

西班牙文自然資料提供者與西班牙國民身分識別卡：
  
-  八位數 
    
- 一個大寫字母 （區分大小寫） 
    
西班牙國民身分識別卡而非駐留西班牙人
  
- 一個大寫字母"L"（區分大小寫）
    
- 七位數
    
- 一個大寫字母 （區分大小寫） 
    
底下的年齡 14 年不含西班牙國民身分識別卡駐留西班牙人：
  
- 一個大寫字母"K"（區分大小寫）
    
-  七位數 
    
- 一個大寫字母 （區分大小寫）
    
外國人與因此識別號碼
  
- 一個大寫也就是字母"X"、"Y"或"Z"（區分大小寫） 
    
- 七位數
    
- 一個大寫字母 （區分大小寫） 
    
外國人沒有因此識別碼
  
- 一個大寫字母的"M"（區分大小寫） 
    
- 七位數
    
- 一個大寫字母 （區分大小寫） 
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_spain_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_spain_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_spain_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsspaineutaxfilenumber"></a>Keywords_spain_eu_tax_file_number

tax id

  
稅 id 號碼
  
cif 識別碼
  
cif 沒有
  
西班牙文 cif 識別碼
  
cif
  
無法稅檔案
  
西班牙文 cif 數目
  


tax file number
  
西班牙文 cif 沒有
  
稅否
  
稅編號
  
taxid #
  
taxno #
  
cifid #
  
spanishcifid #
  
spanishcifno #
  
número de contribuyente
  
número de impuesto corporativo
  
número de identificación 會計
  
cif número
  
cifnúmero #
  
## <a name="sweden"></a>瑞典

### <a name="format"></a>格式

十位數和中指定的型態的符號
  
### <a name="pattern"></a>模式

十位數和符號：
  
-  會對應至出生日期 (YYMMDD) 的六個數字 
    
- 加號、 減號、 或反斜線
    
- 進行識別的三個位數字唯一的位置： 
    
  - 對於 1990年之前發行的數字、 第七個和第八個位數識別出生或 foreign-born 人員郡
    
  - 第九個位置中的數字表示任一奇數女性 2 男或甚至是依性別
    
- 一次檢查數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_sweden_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_sweden_eu_tax_file_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_sweden_eu_tax_file_number`會找出符合模式的內容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsswedeneutaxfilenumber"></a>Keywords_sweden_eu_tax_file_number

tax id

  
無法稅識別碼。
  
稅 id 號碼
  
tax identification

  
稅識別 #
  
稅否]。
  
稅 #
  
taxid #
  
稅檔案
  
無法稅檔案。
  
個人識別碼號碼
  
skatt 識別碼 nummer
  
skatt identifikation
  
personnummer
  
## <a name="uk"></a>英國

### <a name="format"></a>格式

唯一 Taxpayer 參照 (UTR)： 10 位數不含空格和分隔符號
  
國家保險號碼 (NINO)： 如需詳細資訊，請參閱區段"英國 National 保險數 (NINO)"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
### <a name="pattern"></a>模式

唯一 Taxpayer 參照 (UTR)： 10 位數
  
國家保險號碼 (NINO)： 如需詳細資訊，請參閱區段"英國 National 保險數 (NINO)"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_uk_eu_tax_file_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_uk_eu_tax_file_number`找到。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsukeutaxfilenumber"></a>Keywords_uk_eu_tax_file_number

tax id

  
無法稅識別碼。
  
稅 id 號碼
  
tax identification

  
稅識別 #
  
稅否]。
  
稅 #
  
taxid #
  
稅檔案
  
無法稅檔案。
  
## <a name="see-also"></a>另請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

