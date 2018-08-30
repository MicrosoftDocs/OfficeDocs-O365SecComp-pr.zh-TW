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
# <a name="eu-phone-number"></a><span data-ttu-id="2f2d5-104">歐盟電話號碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-104">EU Phone Number</span></span>

<span data-ttu-id="2f2d5-p102">Office 365 安全性的資料遺失防護 (DLP)&amp;規範中心包含許多可供您使用 DLP 原則中的敏感資訊類型。本主題說明歐盟電話號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU Phone Number sensitive information type.</span></span> 
  
## <a name="austria"></a><span data-ttu-id="2f2d5-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="2f2d5-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="2f2d5-108">格式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-108">Format</span></span>

<span data-ttu-id="2f2d5-109">不標準的長度</span><span class="sxs-lookup"><span data-stu-id="2f2d5-109">No standard length</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2f2d5-110">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-110">Pattern</span></span>

- <span data-ttu-id="2f2d5-111">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-111">Digits</span></span> 
    
- <span data-ttu-id="2f2d5-112">只適用於行動電話號碼開頭的數字"6"</span><span class="sxs-lookup"><span data-stu-id="2f2d5-112">Only mobile phone numbers begin with the digit "6"</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-113">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-113">Checksum</span></span>

<span data-ttu-id="2f2d5-114">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-114">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-115">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-115">Definition</span></span>

<span data-ttu-id="2f2d5-116">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-117">規則運算式`Regex_austria_eu_telephone_number_1`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-117">The regular expression  `Regex_austria_eu_telephone_number_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-118">從關鍵字`Keywords_austria_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-118">A keyword from  `Keywords_austria_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-119">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-119">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-120">規則運算式`Regex_austria_eu_telephone_number_2`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-120">The regular expression  `Regex_austria_eu_telephone_number_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-121">從關鍵字`Keywords_austria_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-121">A keyword from  `Keywords_austria_eu_telephone_number` is found.</span></span> 
    
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

## <a name="belgium"></a><span data-ttu-id="2f2d5-122">比利時</span><span class="sxs-lookup"><span data-stu-id="2f2d5-122">Belgium</span></span>

### <a name="definition"></a><span data-ttu-id="2f2d5-123">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-123">Definition</span></span>

<span data-ttu-id="2f2d5-124">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-125">規則運算式`Regex_belgium_eu_telephone_number_1`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-125">The regular expression  `Regex_belgium_eu_telephone_number_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-126">從關鍵字`Keywords_belgium_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-126">A keyword from  `Keywords_belgium_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-127">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-127">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-128">規則運算式`Regex_belgium_eu_telephone_number_2`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-128">The regular expression  `Regex_belgium_eu_telephone_number_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-129">從關鍵字`Keywords_belgium_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-129">A keyword from  `Keywords_belgium_eu_telephone_number` is found.</span></span> 
    
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

## <a name="bulgaria"></a><span data-ttu-id="2f2d5-130">保加利亞</span><span class="sxs-lookup"><span data-stu-id="2f2d5-130">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-131">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-131">Pattern</span></span>

- <span data-ttu-id="2f2d5-132">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-132">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-133">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-133">Checksum</span></span>

<span data-ttu-id="2f2d5-134">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-134">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-135">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-135">Definition</span></span>

<span data-ttu-id="2f2d5-136">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-136">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-137">規則運算式`Regex_bulgaria_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-137">The regular expression  `Regex_bulgaria_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-138">從關鍵字`Keywords_bulgaria_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-138">A keyword from  `Keywords_bulgaria_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-139">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-139">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-140">規則運算式`Regex_bulgaria_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-140">The regular expression  `Regex_bulgaria_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="croatia"></a><span data-ttu-id="2f2d5-141">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="2f2d5-141">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-142">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-142">Pattern</span></span>

- <span data-ttu-id="2f2d5-143">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-143">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-144">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-144">Checksum</span></span>

<span data-ttu-id="2f2d5-145">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-145">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-146">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-146">Definition</span></span>

<span data-ttu-id="2f2d5-147">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-148">規則運算式`Regex_croatia_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-148">The regular expression  `Regex_croatia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-149">從關鍵字`Keywords_croatia_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-149">A keyword from  `Keywords_croatia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-150">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-150">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-151">規則運算式`Regex_croatia_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-151">The regular expression  `Regex_croatia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="cyprus"></a><span data-ttu-id="2f2d5-152">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="2f2d5-152">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-153">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-153">Pattern</span></span>

- <span data-ttu-id="2f2d5-154">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-154">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-155">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-155">Checksum</span></span>

<span data-ttu-id="2f2d5-156">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-156">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-157">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-157">Definition</span></span>

<span data-ttu-id="2f2d5-158">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-159">規則運算式`Regex_cyprus_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-159">The regular expression  `Regex_cyprus_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-160">從關鍵字`Keywords_cyprus_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-160">A keyword from  `Keywords_cyprus_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-161">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-161">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-162">規則運算式`Regex_cyprus_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-162">The regular expression  `Regex_cyprus_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="czech-republic"></a><span data-ttu-id="2f2d5-163">捷克</span><span class="sxs-lookup"><span data-stu-id="2f2d5-163">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-164">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-164">Pattern</span></span>

- <span data-ttu-id="2f2d5-165">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-165">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-166">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-166">Checksum</span></span>

<span data-ttu-id="2f2d5-167">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-167">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-168">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-168">Definition</span></span>

<span data-ttu-id="2f2d5-169">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-169">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-170">規則運算式`Regex_czech_republic_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-170">The regular expression  `Regex_czech_republic_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-171">從關鍵字`Keywords_czech_republic_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-171">A keyword from  `Keywords_czech_republic_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-172">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-172">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-173">規則運算式`Regex_czech_republic_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-173">The regular expression  `Regex_czech_republic_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="denmark"></a><span data-ttu-id="2f2d5-174">丹麥</span><span class="sxs-lookup"><span data-stu-id="2f2d5-174">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-175">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-175">Pattern</span></span>

- <span data-ttu-id="2f2d5-176">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-176">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-177">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-177">Checksum</span></span>

<span data-ttu-id="2f2d5-178">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-178">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-179">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-179">Definition</span></span>

<span data-ttu-id="2f2d5-180">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-180">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-181">規則運算式`Regex_denmark_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-181">The regular expression  `Regex_denmark_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-182">從關鍵字`Keywords_denmark_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-182">A keyword from  `Keywords_denmark_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-183">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-184">規則運算式`Regex_denmark_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-184">The regular expression  `Regex_denmark_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="estonia"></a><span data-ttu-id="2f2d5-185">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="2f2d5-185">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-186">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-186">Pattern</span></span>

- <span data-ttu-id="2f2d5-187">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-187">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-188">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-188">Checksum</span></span>

<span data-ttu-id="2f2d5-189">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-189">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-190">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-190">Definition</span></span>

<span data-ttu-id="2f2d5-191">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-191">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-192">規則運算式`Regex_estonia_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-192">The regular expression  `Regex_estonia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-193">從關鍵字`Keywords_estonia_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-193">A keyword from  `Keywords_estonia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-194">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-195">規則運算式`Regex_estonia_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-195">The regular expression  `Regex_estonia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="finland"></a><span data-ttu-id="2f2d5-196">芬蘭</span><span class="sxs-lookup"><span data-stu-id="2f2d5-196">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-197">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-197">Pattern</span></span>

- <span data-ttu-id="2f2d5-198">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-198">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-199">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-199">Checksum</span></span>

<span data-ttu-id="2f2d5-200">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-200">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-201">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-201">Definition</span></span>

<span data-ttu-id="2f2d5-202">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-203">規則運算式`Regex_finland_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-203">The regular expression  `Regex_finland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-204">從關鍵字`Keywords_finland_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-204">A keyword from  `Keywords_finland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-205">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-205">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-206">規則運算式`Regex_finland_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-206">The regular expression  `Regex_finland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="france"></a><span data-ttu-id="2f2d5-207">法國</span><span class="sxs-lookup"><span data-stu-id="2f2d5-207">France</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-208">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-208">Pattern</span></span>

- <span data-ttu-id="2f2d5-209">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-209">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-210">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-210">Checksum</span></span>

<span data-ttu-id="2f2d5-211">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-211">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-212">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-212">Definition</span></span>

<span data-ttu-id="2f2d5-213">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-213">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-214">規則運算式`Regex_france_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-214">The regular expression  `Regex_france_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-215">從關鍵字`Keywords_france_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-215">A keyword from  `Keywords_france_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-216">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-217">規則運算式`Regex_france_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-217">The regular expression  `Regex_france_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="germany"></a><span data-ttu-id="2f2d5-218">德國</span><span class="sxs-lookup"><span data-stu-id="2f2d5-218">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-219">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-219">Pattern</span></span>

- <span data-ttu-id="2f2d5-220">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-220">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-221">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-221">Checksum</span></span>

<span data-ttu-id="2f2d5-222">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-222">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-223">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-223">Definition</span></span>

<span data-ttu-id="2f2d5-224">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-224">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-225">規則運算式`Regex_germany_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-225">The regular expression  `Regex_germany_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-226">從關鍵字`Keywords_germany_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-226">A keyword from  `Keywords_germany_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-227">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-227">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-228">規則運算式`Regex_germany_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-228">The regular expression  `Regex_germany_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="greece"></a><span data-ttu-id="2f2d5-229">希臘</span><span class="sxs-lookup"><span data-stu-id="2f2d5-229">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-230">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-230">Pattern</span></span>

- <span data-ttu-id="2f2d5-231">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-231">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-232">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-232">Checksum</span></span>

<span data-ttu-id="2f2d5-233">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-233">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-234">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-234">Definition</span></span>

<span data-ttu-id="2f2d5-235">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-235">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-236">規則運算式`Regex_greece_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-236">The regular expression  `Regex_greece_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-237">從關鍵字`Keywords_greece_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-237">A keyword from  `Keywords_greece_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-238">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-238">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-239">規則運算式`Regex_greece_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-239">The regular expression  `Regex_greece_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="hungary"></a><span data-ttu-id="2f2d5-240">匈牙利</span><span class="sxs-lookup"><span data-stu-id="2f2d5-240">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-241">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-241">Pattern</span></span>

- <span data-ttu-id="2f2d5-242">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-242">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-243">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-243">Checksum</span></span>

<span data-ttu-id="2f2d5-244">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-244">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-245">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-245">Definition</span></span>

<span data-ttu-id="2f2d5-246">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-247">規則運算式`Regex_hungary_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-247">The regular expression  `Regex_hungary_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-248">從關鍵字`Keywords_hungary_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-248">A keyword from  `Keywords_hungary_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-249">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-250">規則運算式`Regex_hungary_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-250">The regular expression  `Regex_hungary_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="ireland"></a><span data-ttu-id="2f2d5-251">Ireland</span><span class="sxs-lookup"><span data-stu-id="2f2d5-251">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-252">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-252">Pattern</span></span>

- <span data-ttu-id="2f2d5-253">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-253">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-254">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-254">Checksum</span></span>

<span data-ttu-id="2f2d5-255">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-255">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-256">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-256">Definition</span></span>

<span data-ttu-id="2f2d5-257">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-257">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-258">規則運算式`Regex_ireland_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-258">The regular expression  `Regex_ireland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-259">從關鍵字`Keywords_ireland_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-259">A keyword from  `Keywords_ireland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-260">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-260">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-261">規則運算式`Regex_ireland_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-261">The regular expression  `Regex_ireland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="italy"></a><span data-ttu-id="2f2d5-262">義大利</span><span class="sxs-lookup"><span data-stu-id="2f2d5-262">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-263">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-263">Pattern</span></span>

- <span data-ttu-id="2f2d5-264">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-264">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-265">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-265">Checksum</span></span>

<span data-ttu-id="2f2d5-266">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-266">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-267">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-267">Definition</span></span>

<span data-ttu-id="2f2d5-268">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-268">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-269">規則運算式`Regex_italy_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-269">The regular expression  `Regex_italy_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-270">從關鍵字`Keywords_italy_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-270">A keyword from  `Keywords_italy_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-271">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-271">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-272">規則運算式`Regex_italy_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-272">The regular expression  `Regex_italy_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="latvia"></a><span data-ttu-id="2f2d5-273">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="2f2d5-273">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-274">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-274">Pattern</span></span>

- <span data-ttu-id="2f2d5-275">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-275">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-276">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-276">Checksum</span></span>

<span data-ttu-id="2f2d5-277">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-277">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-278">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-278">Definition</span></span>

<span data-ttu-id="2f2d5-279">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-279">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-280">規則運算式`Regex_latvia_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-280">The regular expression  `Regex_latvia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-281">從關鍵字`Keywords_latvia_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-281">A keyword from  `Keywords_latvia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-282">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-283">規則運算式`Regex_latvia_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-283">The regular expression  `Regex_latvia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="lithuania"></a><span data-ttu-id="2f2d5-284">立陶宛</span><span class="sxs-lookup"><span data-stu-id="2f2d5-284">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-285">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-285">Pattern</span></span>

- <span data-ttu-id="2f2d5-286">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-286">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-287">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-287">Checksum</span></span>

<span data-ttu-id="2f2d5-288">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-288">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-289">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-289">Definition</span></span>

<span data-ttu-id="2f2d5-290">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-291">規則運算式`Regex_lithuania_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-291">The regular expression  `Regex_lithuania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-292">從關鍵字`Keywords_lithuania_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-292">A keyword from  `Keywords_lithuania_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-293">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-293">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-294">規則運算式`Regex_lithuania_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-294">The regular expression  `Regex_lithuania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="luxemburg"></a><span data-ttu-id="2f2d5-295">盧森堡</span><span class="sxs-lookup"><span data-stu-id="2f2d5-295">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-296">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-296">Pattern</span></span>

- <span data-ttu-id="2f2d5-297">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-297">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-298">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-298">Checksum</span></span>

<span data-ttu-id="2f2d5-299">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-299">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-300">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-300">Definition</span></span>

<span data-ttu-id="2f2d5-301">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-301">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-302">規則運算式`Regex_luxemburg_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-302">The regular expression  `Regex_luxemburg_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-303">從關鍵字`Keywords_luxemburg_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-303">A keyword from  `Keywords_luxemburg_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-304">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-304">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-305">規則運算式`Regex_luxemburg_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-305">The regular expression  `Regex_luxemburg_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="malta"></a><span data-ttu-id="2f2d5-306">馬爾他</span><span class="sxs-lookup"><span data-stu-id="2f2d5-306">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-307">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-307">Pattern</span></span>

- <span data-ttu-id="2f2d5-308">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-308">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-309">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-309">Checksum</span></span>

<span data-ttu-id="2f2d5-310">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-310">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-311">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-311">Definition</span></span>

<span data-ttu-id="2f2d5-312">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-313">規則運算式`Regex_malta_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-313">The regular expression  `Regex_malta_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-314">從關鍵字`Keywords_malta_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-314">A keyword from  `Keywords_malta_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-315">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-315">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-316">規則運算式`Regex_malta_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-316">The regular expression  `Regex_malta_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="netherlands"></a><span data-ttu-id="2f2d5-317">荷蘭</span><span class="sxs-lookup"><span data-stu-id="2f2d5-317">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-318">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-318">Pattern</span></span>

- <span data-ttu-id="2f2d5-319">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-319">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-320">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-320">Checksum</span></span>

<span data-ttu-id="2f2d5-321">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-321">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-322">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-322">Definition</span></span>

<span data-ttu-id="2f2d5-323">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-323">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-324">規則運算式`Regex_netherlands_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-324">The regular expression  `Regex_netherlands_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-325">從關鍵字`Keywords_netherlands_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-325">A keyword from  `Keywords_netherlands_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-326">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-327">規則運算式`Regex_netherlands_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-327">The regular expression  `Regex_netherlands_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="poland"></a><span data-ttu-id="2f2d5-328">波蘭</span><span class="sxs-lookup"><span data-stu-id="2f2d5-328">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-329">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-329">Pattern</span></span>

- <span data-ttu-id="2f2d5-330">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-330">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-331">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-331">Checksum</span></span>

<span data-ttu-id="2f2d5-332">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-332">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-333">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-333">Definition</span></span>

<span data-ttu-id="2f2d5-334">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-334">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-335">規則運算式`Regex_poland_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-335">The regular expression  `Regex_poland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-336">從關鍵字`Keywords_poland_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-336">A keyword from  `Keywords_poland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-337">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-337">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-338">規則運算式`Regex_poland_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-338">The regular expression  `Regex_poland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="portugal"></a><span data-ttu-id="2f2d5-339">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="2f2d5-339">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-340">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-340">Pattern</span></span>

- <span data-ttu-id="2f2d5-341">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-341">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-342">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-342">Checksum</span></span>

<span data-ttu-id="2f2d5-343">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-343">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-344">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-344">Definition</span></span>

<span data-ttu-id="2f2d5-345">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-345">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-346">規則運算式`Regex_portugal_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-346">The regular expression  `Regex_portugal_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-347">從關鍵字`Keywords_portugal_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-347">A keyword from  `Keywords_portugal_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-348">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-349">規則運算式`Regex_portugal_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-349">The regular expression  `Regex_portugal_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="romania"></a><span data-ttu-id="2f2d5-350">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="2f2d5-350">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-351">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-351">Pattern</span></span>

- <span data-ttu-id="2f2d5-352">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-352">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-353">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-353">Checksum</span></span>

<span data-ttu-id="2f2d5-354">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-354">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-355">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-355">Definition</span></span>

<span data-ttu-id="2f2d5-356">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-356">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-357">規則運算式`Regex_romania_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-357">The regular expression  `Regex_romania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-358">從關鍵字`Keywords_romania_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-358">A keyword from  `Keywords_romania_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-359">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-359">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-360">規則運算式`Regex_romania_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-360">The regular expression  `Regex_romania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="slovakia"></a><span data-ttu-id="2f2d5-361">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="2f2d5-361">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-362">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-362">Pattern</span></span>

- <span data-ttu-id="2f2d5-363">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-363">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-364">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-364">Checksum</span></span>

<span data-ttu-id="2f2d5-365">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-365">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-366">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-366">Definition</span></span>

<span data-ttu-id="2f2d5-367">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-367">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-368">規則運算式`Regex_slovakia_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-368">The regular expression  `Regex_slovakia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-369">從關鍵字`Keywords_slovakia_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-369">A keyword from  `Keywords_slovakia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-370">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-370">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-371">規則運算式`Regex_slovakia_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-371">The regular expression  `Regex_slovakia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="slovenia"></a><span data-ttu-id="2f2d5-372">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="2f2d5-372">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-373">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-373">Pattern</span></span>

- <span data-ttu-id="2f2d5-374">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-374">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-375">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-375">Checksum</span></span>

<span data-ttu-id="2f2d5-376">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-377">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-377">Definition</span></span>

<span data-ttu-id="2f2d5-378">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-379">規則運算式`Regex_slovenia_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-379">The regular expression  `Regex_slovenia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-380">從關鍵字`Keywords_slovenia_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-380">A keyword from  `Keywords_slovenia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-381">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-382">規則運算式`Regex_slovenia_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-382">The regular expression  `Regex_slovenia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="spain"></a><span data-ttu-id="2f2d5-383">西班牙</span><span class="sxs-lookup"><span data-stu-id="2f2d5-383">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-384">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-384">Pattern</span></span>

- <span data-ttu-id="2f2d5-385">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-385">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-386">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-386">Checksum</span></span>

<span data-ttu-id="2f2d5-387">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-387">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-388">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-388">Definition</span></span>

<span data-ttu-id="2f2d5-389">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-389">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-390">規則運算式`Regex_spain_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-390">The regular expression  `Regex_spain_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-391">從關鍵字`Keywords_spain_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-391">A keyword from  `Keywords_spain_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-392">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-392">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-393">規則運算式`Regex_spain_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-393">The regular expression  `Regex_spain_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="sweden"></a><span data-ttu-id="2f2d5-394">瑞典</span><span class="sxs-lookup"><span data-stu-id="2f2d5-394">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-395">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-395">Pattern</span></span>

- <span data-ttu-id="2f2d5-396">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-396">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-397">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-397">Checksum</span></span>

<span data-ttu-id="2f2d5-398">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-398">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-399">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-399">Definition</span></span>

<span data-ttu-id="2f2d5-400">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-400">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-401">規則運算式`Regex_sweden_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-401">The regular expression  `Regex_sweden_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-402">從關鍵字`Keywords_sweden_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-402">A keyword from  `Keywords_sweden_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-403">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-403">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-404">規則運算式`Regex_sweden_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-404">The regular expression  `Regex_sweden_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="uk"></a><span data-ttu-id="2f2d5-405">英國</span><span class="sxs-lookup"><span data-stu-id="2f2d5-405">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="2f2d5-406">模式</span><span class="sxs-lookup"><span data-stu-id="2f2d5-406">Pattern</span></span>

- <span data-ttu-id="2f2d5-407">數字</span><span class="sxs-lookup"><span data-stu-id="2f2d5-407">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2f2d5-408">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-408">Checksum</span></span>

<span data-ttu-id="2f2d5-409">不適用</span><span class="sxs-lookup"><span data-stu-id="2f2d5-409">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2f2d5-410">定義</span><span class="sxs-lookup"><span data-stu-id="2f2d5-410">Definition</span></span>

<span data-ttu-id="2f2d5-411">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-412">規則運算式`Regex_uk_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-412">The regular expression  `Regex_uk_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2f2d5-413">從關鍵字`Keywords_uk_eu_telephone_number`找到。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-413">A keyword from  `Keywords_uk_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="2f2d5-414">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="2f2d5-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2f2d5-415">規則運算式`Regex_uk_eu_telephone_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="2f2d5-415">The regular expression  `Regex_uk_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
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

## <a name="see-also"></a><span data-ttu-id="2f2d5-416">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2f2d5-416">See also</span></span>

[<span data-ttu-id="2f2d5-417">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="2f2d5-417">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

