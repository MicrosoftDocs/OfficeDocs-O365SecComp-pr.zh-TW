---
title: 歐盟電話號碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1c90ca41-1681-46bf-8ad6-6bf4cec5c426
description: Office 365 安全性的資料遺失防護 (DLP)&amp;規範中心包含許多可供您使用 DLP 原則中的敏感資訊類型。本主題說明歐盟電話號碼敏感資訊類型。
ms.openlocfilehash: 9dd878e3385312982f9f3a4927205e3ebb27aabb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526826"
---
# <a name="eu-phone-number"></a>歐盟電話號碼

Office 365 安全性的資料遺失防護 (DLP)&amp;規範中心包含許多可供您使用 DLP 原則中的敏感資訊類型。本主題說明歐盟電話號碼敏感資訊類型。 
  
## <a name="austria"></a>奧地利

### <a name="format"></a>格式

不標準的長度
  
### <a name="pattern"></a>模式

- 數字 
    
- 只適用於行動電話號碼開頭的數字"6" 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_austria_eu_telephone_number_1`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_austria_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_austria_eu_telephone_number_2`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_austria_eu_telephone_number`找到。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_telephone_number_1" />
          <Match idRef="Keywords_austria_eu_telephone_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_telephone_number_2" />
          <Match idRef="Keywords_austria_eu_telephone_number" />
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_austria_eu_formatted_telephone_number_1" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_austria_eu_formatted_telephone_number_2" />
          </Pattern>
</Entity>
```

## <a name="belgium"></a>比利時

### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_belgium_eu_telephone_number_1`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_belgium_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_belgium_eu_telephone_number_2`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_belgium_eu_telephone_number`找到。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_telephone_number_1" />
          <Match idRef="Keywords_belgium_eu_telephone_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_telephone_number_2" />
          <Match idRef="Keywords_belgium_eu_telephone_number" />
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_belgium_eu_formatted_telephone_number_1" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_belgium_eu_formatted_telephone_number_2" />
          </Pattern></Entity>
```

## <a name="bulgaria"></a>保加利亞

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_bulgaria_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_bulgaria_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_bulgaria_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_telephone_number" />
          <Match idRef="Keywords_bulgaria_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_bulgaria_eu_formatted_telephone_number" />
          </Pattern>
          
</Entity>
```

## <a name="croatia"></a>克羅埃西亞

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_croatia_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_croatia_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_croatia_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_telephone_number" />
          <Match idRef="Keywords_croatia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_croatia_eu_formatted_telephone_number" />
          </Pattern>
         </Entity>
```

## <a name="cyprus"></a>賽普勒斯

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_cyprus_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_cyprus_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_cyprus_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_telephone_number" />
          <Match idRef="Keywords_cyprus_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_cyprus_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="czech-republic"></a>捷克

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_czech_republic_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_czech_republic_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_czech_republic_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_telephone_number" />
          <Match idRef="Keywords_czech_republic_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_czech_republic_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="denmark"></a>丹麥

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_denmark_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_denmark_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_denmark_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_telephone_number" />
          <Match idRef="Keywords_denmark_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_denmark_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="estonia"></a>愛沙尼亞

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_estonia_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_estonia_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_estonia_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_telephone_number" />
          <Match idRef="Keywords_estonia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_estonia_eu_formatted_telephone_number" />
          </Pattern>
       </Entity>
```

## <a name="finland"></a>芬蘭

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_finland_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_finland_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_finland_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_telephone_number" />
          <Match idRef="Keywords_finland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_finland_eu_formatted_telephone_number" />
             </Pattern>
</Entity>
```

## <a name="france"></a>法國

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_france_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_france_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_france_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_telephone_number" />
          <Match idRef="Keywords_france_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_france_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="germany"></a>德國

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_germany_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_germany_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_germany_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_telephone_number" />
          <Match idRef="Keywords_germany_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_germany_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="greece"></a>希臘

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_greece_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_greece_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_greece_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_telephone_number" />
          <Match idRef="Keywords_greece_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_greece_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="hungary"></a>匈牙利

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_hungary_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_hungary_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_hungary_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_telephone_number" />
          <Match idRef="Keywords_hungary_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_hungary_eu_formatted_telephone_number" />
          </Pattern>
       </Entity>
```

## <a name="ireland"></a>Ireland

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_ireland_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_ireland_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_ireland_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_telephone_number" />
          <Match idRef="Keywords_ireland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_ireland_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="italy"></a>義大利

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_italy_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_italy_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_italy_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_telephone_number" />
          <Match idRef="Keywords_italy_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_italy_eu_formatted_telephone_number" />
          </Pattern>
         </Entity>
```

## <a name="latvia"></a>拉脫維亞

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_latvia_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_latvia_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_latvia_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_telephone_number" />
          <Match idRef="Keywords_latvia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_latvia_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="lithuania"></a>立陶宛

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_lithuania_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_lithuania_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_lithuania_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_telephone_number" />
          <Match idRef="Keywords_lithuania_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_lithuania_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="luxemburg"></a>盧森堡

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_luxemburg_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_luxemburg_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_luxemburg_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_telephone_number" />
          <Match idRef="Keywords_luxemburg_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_luxemburg_eu_formatted_telephone_number" />
                  </Pattern>
</Entity>
```

## <a name="malta"></a>馬爾他

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_malta_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_malta_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_malta_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_telephone_number" />
          <Match idRef="Keywords_malta_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_malta_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="netherlands"></a>荷蘭

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_netherlands_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_netherlands_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_netherlands_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_telephone_number" />
          <Match idRef="Keywords_netherlands_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_netherlands_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="poland"></a>波蘭

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_poland_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_poland_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_poland_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_telephone_number" />
          <Match idRef="Keywords_poland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_poland_eu_formatted_telephone_number" />
             </Pattern>
</Entity>
```

## <a name="portugal"></a>葡萄牙

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_portugal_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_portugal_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_portugal_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_telephone_number" />
          <Match idRef="Keywords_portugal_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_portugal_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="romania"></a>羅馬尼亞

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_romania_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_romania_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_romania_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_telephone_number" />
          <Match idRef="Keywords_romania_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_romania_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="slovakia"></a>斯洛伐克

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_slovakia_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_slovakia_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_slovakia_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_telephone_number" />
          <Match idRef="Keywords_slovakia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_slovakia_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="slovenia"></a>斯洛維尼亞

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_slovenia_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_slovenia_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_slovenia_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_telephone_number" />
          <Match idRef="Keywords_slovenia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_slovenia_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="spain"></a>西班牙

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_spain_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_spain_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_spain_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_telephone_number" />
          <Match idRef="Keywords_spain_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_spain_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="sweden"></a>瑞典

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_sweden_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_sweden_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_sweden_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_telephone_number" />
          <Match idRef="Keywords_sweden_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_sweden_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="uk"></a>英國

### <a name="pattern"></a>模式

- 數字 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_uk_eu_telephone_number`會找出符合模式的內容。 
    
- 從關鍵字`Keywords_uk_eu_telephone_number`找到。 
    
如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：
  
- 規則運算式`Regex_uk_eu_telephone_number`會找出符合模式的內容。 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_telephone_number" />
          <Match idRef="Keywords_uk_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_uk_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="see-also"></a>另請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

