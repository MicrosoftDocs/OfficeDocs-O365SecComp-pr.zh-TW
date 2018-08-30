---
title: 歐盟社會安全號碼或對等資格識別碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1fabd341-e594-4bfe-961c-62aa82893f60
description: 本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟社會安全號碼或對等識別碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
ms.openlocfilehash: 6f1027dcfb648ed937b8180d74d4bc6348dab650
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526634"
---
# <a name="eu-social-security-number-or-equivalent-id"></a>歐盟社會安全號碼或對等資格識別碼

本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟社會安全號碼 (SSN) 或對等識別碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
  
## <a name="austria"></a>奧地利

### <a name="format"></a>格式

指定之格式的 10 位數字
  
### <a name="pattern"></a>模式

10 位數：
  
-  會對應到序號的三個位數 
    
- 一次檢查數字
    
- 會對應至出生日期 (DDMMYY) 的六個數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_austria_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_austria_eu_ssn_or_equivalent`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_austria_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsaustriaeussnorequivalent"></a>Keywords_austria_eu_ssn_or_equivalent

社會安全沒有
  
social security number

  

social security code
  
保險數目
  
奧地利 ssn
  
ssn #
  
ssn
  
保險程式碼
  
保險程式碼 #
  
socialsecurityno #
  
sozialversicherungsnummer
  
soziale sicherheit kein
  
versicherungsnummer
  
## <a name="belgium"></a>比利時

### <a name="format"></a>格式

不含空格或分隔符號 11 位數
  
### <a name="pattern"></a>模式

11 位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_belgium_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_belgium_eu_ssn_or_equivalent`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_belgium_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsbelgiumeussnorequivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

比利時國際號碼
  
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
  
國際 numéro
  
numéro de sécurité

  
numéro d'assuré
  
國際 identifiant
  
identifiantnational #
  
numéronational #
  
## <a name="croatia"></a>克羅埃西亞

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
  
- 此函數`Func_croatia_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_croatia_eu_ssn_or_equivalent`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_croatia_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordscroatiaeussnorequivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

個人識別碼
  
主要市民數
  
國家識別碼
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
nationalnumber
  
bnn #
  
bnn
  
個人識別碼號碼
  
personalidnumber #
  
oib
  
osobni identifikacijski broj
  
## <a name="czech-republic"></a>捷克

### <a name="format"></a>格式

十位數和中指定的型態反斜線
  
### <a name="pattern"></a>模式

十位數和反斜線：
  
- 會對應至出生日期 (YYMMDD) 的六個位數： 
    
- 反斜線
    
- 會對應至分隔人員出生日期相同的序號的三個位數
    
- 一次檢查數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_czech_republic_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_czech_republic_eu_ssn_or_equivalent`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_czech_republic_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsczechrepubliceussnorequivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

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
  
## <a name="denmark"></a>丹麥

### <a name="format"></a>格式

十位數和中指定的型態連字號
  
### <a name="pattern"></a>模式

十位數和連字號：
  
- 會對應至出生日期 (DDMMYY) 的六個數字 
    
- 一個連字號
    
- 會對應到序號的四位數
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_denmark_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_denmark_eu_ssn_or_equivalent`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_denmark_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsdenmarkeussnorequivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

個人識別碼
  
國家識別碼
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
國際號碼
  
個人識別碼號碼
  
personalidnumber #
  
cpr nummer
  
personnummer
  
## <a name="finland"></a>芬蘭

### <a name="format"></a>格式

以指定的格式 11 個字元組合
  
### <a name="pattern"></a>模式

以指定的格式 11 個字元組合：
  
-  六位數 
    
- 一個執行個體其中一項：
    
  - 加上符號
    
  - 減去符號
    
  - 字母"A"（不區分大小寫）
    
- 三位數
    
- 一個字母或一個數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_finland_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_finland_eu_ssn_or_equivalent`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_finland_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsfinlandeussnorequivalent"></a>Keywords_finland_eu_ssn_or_equivalent

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
  
hetu
  
## <a name="france"></a>法國

如需詳細資訊，請參閱節"法國社會安全號碼 (INSEE)"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="germany"></a>德國

如需詳細資訊，請參閱節"德國識別卡 Number"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="greece"></a>希臘

如需詳細資訊，請參閱節"希臘國家識別碼卡片"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

不含空格和分隔符號的九個位數
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_hungary_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_hungary_eu_ssn_or_equivalent`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_hungary_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordshungaryeussnorequivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

匈牙利文社會安全號碼
  
social security number

  
socialsecuritynumber #
  
hssn #
  
socialsecuritynno
  
hssn
  
泰
  
泰 #
  
ssn
  
ssn #
  
社會安全沒有
  
áfa
  
közösségi adószám
  
általános forgalmi adó szám
  
hozzáadottérték adó
  
áfa szám
  
magyar áfa szám
  
## <a name="portugal"></a>葡萄牙

如需詳細資訊，請參閱節"葡萄牙市民卡卡號"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="spain"></a>西班牙

如需詳細資訊，請參閱節"西班牙社會安全號碼 (SSN)"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="sweden"></a>瑞典

### <a name="format"></a>格式

12 的數字不含空格和分隔符號
  
### <a name="pattern"></a>模式

12 位數：
  
-  八個對應至出生日期 (YYYYMMDD) 的數字 
    
- 會對應到序號的三個字其中： 
    
  - 序號中的最後一個數字表示性別因 2 男為奇數和偶數女性的工作分派
    
  - 序號的工作分派至郡號碼的承載出生或是 （如果出生之前 1947年），所通信最多個 1990，其中他有已住，根據稅記錄 1947 年 1 月 1 上具有特殊的程式碼 (通常為 7th 的數字 9) 的immigrants 
    
- 一次檢查數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：
  
- 此函數`Func_sweden_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_sweden_eu_ssn_or_equivalent`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 此函數`Func_sweden_eu_ssn_or_equivalent`會找出符合模式的內容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywordsswedeneussnorequivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

個人識別碼號碼
  
identification number

  
個人識別碼沒有
  
identity 為無
  
識別任何
  
個人識別碼沒有
  
personnummer 識別碼
  
personligt 識別碼 nummer
  
unikt 識別碼 nummer
  
personnummer
  
identifikationsnumret
  
personnummer #
  
identifikationsnumret #
  
## <a name="see-also"></a>另請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

