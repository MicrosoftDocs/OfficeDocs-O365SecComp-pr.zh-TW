---
title: 歐盟護照號碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: 本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟護照號碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
ms.openlocfilehash: 71acc39b885c057e1771ec13b2f3c25017ac1bb6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526837"
---
# <a name="eu-passport-number"></a>歐盟護照號碼

本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟護照號碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
  
## <a name="austria"></a>奧地利

### <a name="format"></a>格式

後面接著選用的空間和七位數字的一個字母
  
### <a name="pattern"></a>模式

一個字母、 七位數字和一個空格的組合：
  
- 一個字母 (不區分大小寫)
    
- 一個空格 （選擇性）
    
- 七位數
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_austria_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_austria_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_austria_eu_passport_number**|
|:-----|
|護照號碼  <br/> 奧地利護照號碼  <br/> passport 無  <br/> reisepass  <br/> österreichisch reisepass  <br/> |
   
## <a name="belgium"></a>比利時

### <a name="format"></a>格式

後面接著任何空格或分隔符號的六個位數字的兩個字母
  
### <a name="pattern"></a>模式

兩個字母和後面接著 6 位數
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_belgium_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_belgium_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_belgium_eu_passport_number**|
|:-----|
|護照號碼  <br/> 比利時護照號碼  <br/> passport 無  <br/> paspoort  <br/> paspoortnummer  <br/> reisepass kein  <br/> reisepass  <br/> |
   
## <a name="bulgaria"></a>保加利亞

### <a name="format"></a>格式

不含空格和分隔符號的九個位數
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_bulgaria_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_bulgaria_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_bulgaria_eu_passport_number**|
|:-----|
|護照號碼  <br/> 保加利亞護照號碼  <br/> passport 無  <br/> НОМЕР НА ПАСПОРТА  <br/> |
   
## <a name="croatia"></a>克羅埃西亞

### <a name="format"></a>格式

不含空格和分隔符號的九個位數
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_croatia_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_croatia_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_croatia_eu_passport_number**|
|:-----|
|護照號碼  <br/> 克羅埃西亞文護照號碼  <br/> passport 無  <br/> broj putovnice  <br/> |
   
## <a name="cyprus"></a>賽普勒斯

### <a name="format"></a>格式

後面接著任何空格或分隔符號 6-8 位數字的一個字母
  
### <a name="pattern"></a>模式

後面接著六到八個位數字的一個字母
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_cyprus_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_cyprus_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_cyprus_eu_passport_number**|
|:-----|
|護照號碼  <br/> 賽普勒斯護照號碼  <br/> passport 無  <br/> ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ  <br/> |
   
## <a name="czech-republic"></a>捷克

### <a name="format"></a>格式

不含空格或分隔字元的八個位數
  
### <a name="pattern"></a>模式

不含空格或分隔字元的八個位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_czech_republic_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_czech_republic_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_czech_republic_eu_passport_number**|
|:-----|
|護照號碼  <br/> 捷克護照號碼  <br/> passport 無  <br/> cestovní pas  <br/> pas  <br/> |
   
## <a name="denmark"></a>丹麥

### <a name="format"></a>格式

不含空格和分隔符號的九個位數
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_denmark_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_denmark_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_denmark_eu_passport_number**|
|:-----|
|護照號碼  <br/> 丹麥文護照號碼  <br/> passport 無  <br/> pas  <br/> pasnummer  <br/> |
   
## <a name="estonia"></a>愛沙尼亞

### <a name="format"></a>格式

後面接著任何空格或分隔符號七位數字的一個字母
  
### <a name="pattern"></a>模式

後面七位數字的一個字母
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_estonia_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_estonia_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_estonia_eu_passport_number**|
|:-----|
|護照號碼  <br/> 愛沙尼亞文護照號碼  <br/> passport 無  <br/> eesti kodaniku 複雜  <br/> |
   
## <a name="finland"></a>芬蘭

如需詳細資訊，請參閱節"芬蘭護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="france"></a>法國

如需詳細資訊，請參閱節"法國護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="germany"></a>德國

如需詳細資訊，請參閱節"德國護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="greece"></a>希臘

### <a name="format"></a>格式

後面接著任何空格或分隔符號七位數字的兩個字母
  
### <a name="pattern"></a>模式

兩個字母後尾隨七位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_greece_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_greece_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_greece_eu_passport_number**|
|:-----|
|護照號碼  <br/> 希臘文護照號碼  <br/> passport 無  <br/> ΔΙΑΒΑΤΗΡΙΟ  <br/> |
   
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

後面接著任何空格或分隔符號的六個或七位數字的兩個字母
  
### <a name="pattern"></a>模式

後面接著六個或七位數字的兩個字母
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_hungary_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_hungary_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_hungary_eu_passport_number**|
|:-----|
|護照號碼  <br/> 匈牙利文護照號碼  <br/> passport 無  <br/> útlevél száma  <br/> |
   
## <a name="ireland"></a>Ireland

### <a name="format"></a>格式

兩個字母或數字後面接著任何空格或分隔符號七位數字
  
### <a name="pattern"></a>模式

兩個字母或數字後面七位數字：
  
- 兩個數字或字母 (不區分大小寫)
    
- 七位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_ireland_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_ireland_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_ireland_eu_passport_number**|
|:-----|
|護照號碼  <br/> 愛爾蘭護照號碼  <br/> passport 無  <br/> pas  <br/> passport  <br/> passeport  <br/> passeport numero  <br/> |
   
## <a name="italy"></a>義大利

### <a name="format"></a>格式

兩個字母或數字後面接著任何空格或分隔符號七位數字
  
### <a name="pattern"></a>模式

兩個字母或數字後面七位數字：
  
- 兩個數字或字母 (不區分大小寫)
    
- 七位數
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_italy_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_italy_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_italy_eu_passport_number**|
|:-----|
|義大利護照號碼  <br/> repubblica italiana passaporto  <br/> passaporto  <br/> passaporto italiana  <br/> 護照號碼  <br/> italiana passaporto numero  <br/> passaporto numero  <br/> numéro passeport italien  <br/> numéro passeport  <br/> |
   
## <a name="latvia"></a>拉脫維亞

### <a name="format"></a>格式

兩個字母或數字後面接著任何空格或分隔符號七位數字
  
### <a name="pattern"></a>模式

兩個字母或數字後面七位數字：
  
- 兩個數字或字母 (不區分大小寫)
    
- 七位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_latvia_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_latvia_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_latvia_eu_passport_number**|
|:-----|
|護照號碼  <br/> 拉脫維亞護照號碼  <br/> passport 無  <br/> pase numurs  <br/> |
   
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

八個任何空格或分隔符號的字母或數字
  
### <a name="pattern"></a>模式

八個字或字母 （不區分大小寫）
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_lithuania_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_lithuania_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_lithuania_eu_passport_number**|
|:-----|
|護照號碼  <br/> lithunian 護照號碼  <br/> passport 無  <br/> paso numeris  <br/> |
   
## <a name="luxemburg"></a>盧森堡

### <a name="format"></a>格式

八個任何空格或分隔符號的字母或數字
  
### <a name="pattern"></a>模式

八個字或字母 （不區分大小寫）
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_nation_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_nation_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_nation_eu_passport_number**|
|:-----|
|護照號碼  <br/> 拉脫維亞護照號碼  <br/> passport 無  <br/> passnummer  <br/> |
   
## <a name="malta"></a>馬爾他

### <a name="format"></a>格式

不含空格或分隔符號七位數字
  
### <a name="pattern"></a>模式

 七位數 
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_malta_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_malta_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_malta_eu_passport_number**|
|:-----|
|護照號碼  <br/> 馬爾他護照號碼  <br/> passport 無  <br/> numru tal passaport  <br/> |
   
## <a name="netherlands"></a>荷蘭

### <a name="format"></a>格式

九個字母或數字與任何空格或分隔符號
  
### <a name="pattern"></a>模式

九個字母或數字
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_netherlands_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_netherlands_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_netherlands_eu_passport_number**|
|:-----|
|荷蘭文護照號碼  <br/> 護照號碼  <br/> 荷蘭護照號碼  <br/> nederlanden paspoort nummer  <br/> paspoort  <br/> nederlanden paspoortnummer  <br/> paspoortnummer  <br/> |
   
## <a name="poland"></a>波蘭

如需詳細資訊，請參閱節"波蘭護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="portugal"></a>葡萄牙

### <a name="format"></a>格式

一個字母後面接著任何空格或分隔符號 6 位數
  
### <a name="pattern"></a>模式

一個字母後面接著 6 位數：
  
- 一個字母 (不區分大小寫)
    
- 六位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_portugal_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_portugal_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_portugal_eu_passport_number**|
|:-----|
|護照號碼  <br/> 葡萄牙護照號碼  <br/> passport 無  <br/> número 不要 passaporte  <br/> |
   
## <a name="romania"></a>羅馬尼亞

### <a name="format"></a>格式

不含空格和分隔字元的八個或九個位數
  
### <a name="pattern"></a>模式

八個或 9 的數字
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_romania_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_romania_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_romania_eu_passport_number**|
|:-----|
|護照號碼  <br/> 羅馬尼亞護照號碼  <br/> passport 無  <br/> numărul pașaportului  <br/> |
   
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

一個數字或字母後面接著任何空格或分隔符號七位數字
  
### <a name="pattern"></a>模式

一個數字或字母後面七位數字 （不區分大小寫）
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_slovakia_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_slovakia_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_slovakia_eu_passport_number**|
|:-----|
|護照號碼  <br/> 斯洛伐克護照號碼  <br/> passport 無  <br/> Číslo pasu  <br/> |
   
## <a name="slovenia"></a>斯洛維尼亞

### <a name="format"></a>格式

後面接著任何空格或分隔符號七位數字的兩個字母
  
### <a name="pattern"></a>模式

後面七位數字的兩個字母：
  
- 字母"P"
    
- 一個大寫字母
    
- 七位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_slovenia_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_slovenia_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_slovenia_eu_passport_number**|
|:-----|
|護照號碼  <br/> 斯洛維尼亞文護照號碼  <br/> passport 無  <br/> Številka potnega lista  <br/> |
   
## <a name="spain"></a>西班牙

### <a name="format"></a>格式

字母及號碼與任何空格或分隔符號八個或九個字元組合
  
### <a name="pattern"></a>模式

字母及數字 8 或九個字元組合：
  
-  兩個字母或數字 
    
- 一個數字或字母 （選用）
    
- 六位數
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_spain_eu_passport_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_spain_eu_passport_number`找到。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_spain_eu_passport_number**|
|:-----|
|passport  <br/> 西班牙 passport  <br/> passport 活頁簿  <br/> 護照號碼  <br/> passport 無  <br/> libreta pasaporte  <br/> número pasaporte  <br/> españa pasaporte  <br/> pasaporte  <br/> |
   
## <a name="sweden"></a>瑞典

如需詳細資訊，請參閱節"瑞典護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="uk"></a>英國

如需詳細資訊，請參閱節"US/英國護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。
  
## <a name="see-also"></a>另請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

