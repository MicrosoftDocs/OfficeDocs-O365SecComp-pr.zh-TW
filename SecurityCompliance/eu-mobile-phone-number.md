---
title: 歐盟行動電話號碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 555e7675-2ae8-42d1-9b8e-2c8f8cd21337
description: Office 365 安全性的資料遺失防護 (DLP)&amp;規範中心包含許多可供您使用 DLP 原則中的敏感資訊類型。本主題說明歐盟行動電話號碼敏感資訊類型。
ms.openlocfilehash: d0818759dae8ed86cc9aef6f7fad48cbd2acf24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526658"
---
# <a name="eu-mobile-phone-number"></a><span data-ttu-id="5988d-104">歐盟行動電話號碼</span><span class="sxs-lookup"><span data-stu-id="5988d-104">EU Mobile Phone Number</span></span>

<span data-ttu-id="5988d-p102">Office 365 安全性的資料遺失防護 (DLP)&amp;規範中心包含許多可供您使用 DLP 原則中的敏感資訊類型。本主題說明歐盟行動電話號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="5988d-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU Mobile Phone Number sensitive information type.</span></span> 
  
## <a name="austria"></a><span data-ttu-id="5988d-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="5988d-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="5988d-108">格式</span><span class="sxs-lookup"><span data-stu-id="5988d-108">Format</span></span>

<span data-ttu-id="5988d-109">數字不標準的長度</span><span class="sxs-lookup"><span data-stu-id="5988d-109">Digits without standard lengths</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5988d-110">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-110">Pattern</span></span>

-  <span data-ttu-id="5988d-111">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-111">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="5988d-112">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-112">Definition</span></span>

<span data-ttu-id="5988d-113">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-113">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-114">規則運算式`Regex_austria_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-114">The regular expression  `Regex_austria_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-115">規則運算式`Regex_austria_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-115">The regular expression  `Regex_austria_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-116">從關鍵字`Keywords_austria_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-116">A keyword from  `Keywords_austria_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_mobile_number"/>
          <Match idRef="Keywords_austria_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_austria_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="belgium"></a><span data-ttu-id="5988d-117">比利時</span><span class="sxs-lookup"><span data-stu-id="5988d-117">Belgium</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-118">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-118">Pattern</span></span>

-  <span data-ttu-id="5988d-119">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-119">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="5988d-120">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-120">Definition</span></span>

<span data-ttu-id="5988d-121">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-122">規則運算式`Regex_belgium_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-122">The regular expression  `Regex_belgium_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-123">規則運算式`Regex_belgium_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-123">The regular expression  `Regex_belgium_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-124">從關鍵字`Keywords_belgium_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-124">A keyword from  `Keywords_belgium_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_mobile_number"/>
          <Match idRef="Keywords_belgium_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_belgium_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="bulgaria"></a><span data-ttu-id="5988d-125">保加利亞</span><span class="sxs-lookup"><span data-stu-id="5988d-125">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-126">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-126">Pattern</span></span>

-  <span data-ttu-id="5988d-127">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-127">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="5988d-128">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-128">Definition</span></span>

<span data-ttu-id="5988d-129">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-129">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-130">規則運算式`Regex_bulgaria_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-130">The regular expression  `Regex_bulgaria_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-131">規則運算式`Regex_bulgaria_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-131">The regular expression  `Regex_bulgaria_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-132">從關鍵字`Keywords_bulgaria_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-132">A keyword from  `Keywords_bulgaria_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_mobile_number"/>
          <Match idRef="Keywords_bulgaria_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_bulgaria_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="croatia"></a><span data-ttu-id="5988d-133">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="5988d-133">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-134">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-134">Pattern</span></span>

-  <span data-ttu-id="5988d-135">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-135">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="5988d-136">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-136">Definition</span></span>

<span data-ttu-id="5988d-137">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-138">規則運算式`Regex_croatia_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-138">The regular expression  `Regex_croatia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-139">規則運算式`Regex_croatia_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-139">The regular expression  `Regex_croatia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-140">從關鍵字`Keywords_croatia_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-140">A keyword from  `Keywords_croatia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_mobile_number"/>
          <Match idRef="Keywords_croatia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_croatia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="cyprus"></a><span data-ttu-id="5988d-141">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="5988d-141">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-142">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-142">Pattern</span></span>

-  <span data-ttu-id="5988d-143">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-143">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-144">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-144">Checksum</span></span>

<span data-ttu-id="5988d-145">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-145">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-146">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-146">Definition</span></span>

<span data-ttu-id="5988d-147">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-148">規則運算式`Regex_cyprus_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-148">The regular expression  `Regex_cyprus_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-149">規則運算式`Regex_cyprus_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-149">The regular expression  `Regex_cyprus_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-150">從關鍵字`Keywords_cyprus_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-150">A keyword from  `Keywords_cyprus_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_mobile_number"/>
          <Match idRef="Keywords_cyprus_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_cyprus_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="czech-republic"></a><span data-ttu-id="5988d-151">捷克</span><span class="sxs-lookup"><span data-stu-id="5988d-151">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-152">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-152">Pattern</span></span>

-  <span data-ttu-id="5988d-153">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-153">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-154">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-154">Checksum</span></span>

<span data-ttu-id="5988d-155">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-155">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-156">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-156">Definition</span></span>

<span data-ttu-id="5988d-157">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-157">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-158">規則運算式`Regex_czech_republic_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-158">The regular expression  `Regex_czech_republic_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-159">規則運算式`Regex_czech_republic_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-159">The regular expression  `Regex_czech_republic_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-160">從關鍵字`Keywords_czech_republic_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-160">A keyword from  `Keywords_czech_republic_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_mobile_number"/>
          <Match idRef="Keywords_czech_republic_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_czech_republic_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="denmark"></a><span data-ttu-id="5988d-161">丹麥</span><span class="sxs-lookup"><span data-stu-id="5988d-161">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-162">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-162">Pattern</span></span>

-  <span data-ttu-id="5988d-163">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-163">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-164">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-164">Checksum</span></span>

<span data-ttu-id="5988d-165">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-165">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-166">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-166">Definition</span></span>

<span data-ttu-id="5988d-167">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-167">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-168">規則運算式`Regex_denmark_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-168">The regular expression  `Regex_denmark_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-169">規則運算式`Regex_denmark_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-169">The regular expression  `Regex_denmark_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-170">從關鍵字`Keywords_denmark_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-170">A keyword from  `Keywords_denmark_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_mobile_number"/>
          <Match idRef="Keywords_denmark_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_denmark_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="estonia"></a><span data-ttu-id="5988d-171">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="5988d-171">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-172">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-172">Pattern</span></span>

-  <span data-ttu-id="5988d-173">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-173">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-174">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-174">Checksum</span></span>

<span data-ttu-id="5988d-175">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-175">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-176">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-176">Definition</span></span>

<span data-ttu-id="5988d-177">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-177">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-178">規則運算式`Regex_estonia_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-178">The regular expression  `Regex_estonia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-179">規則運算式`Regex_estonia_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-179">The regular expression  `Regex_estonia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-180">從關鍵字`Keywords_estonia_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-180">A keyword from  `Keywords_estonia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_mobile_number"/>
          <Match idRef="Keywords_estonia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_estonia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="finland"></a><span data-ttu-id="5988d-181">芬蘭</span><span class="sxs-lookup"><span data-stu-id="5988d-181">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-182">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-182">Pattern</span></span>

-  <span data-ttu-id="5988d-183">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-183">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-184">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-184">Checksum</span></span>

<span data-ttu-id="5988d-185">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-185">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-186">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-186">Definition</span></span>

<span data-ttu-id="5988d-187">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-187">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-188">規則運算式`Regex_finland_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-188">The regular expression  `Regex_finland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-189">規則運算式`Regex_finland_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-189">The regular expression  `Regex_finland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-190">從關鍵字`Keywords_finland_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-190">A keyword from  `Keywords_finland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_mobile_number"/>
          <Match idRef="Keywords_finland_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_finland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="france"></a><span data-ttu-id="5988d-191">法國</span><span class="sxs-lookup"><span data-stu-id="5988d-191">France</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-192">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-192">Pattern</span></span>

-  <span data-ttu-id="5988d-193">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-193">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-194">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-194">Checksum</span></span>

<span data-ttu-id="5988d-195">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-195">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-196">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-196">Definition</span></span>

<span data-ttu-id="5988d-197">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-198">規則運算式`Regex_france_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-198">The regular expression  `Regex_france_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-199">規則運算式`Regex_france_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-199">The regular expression  `Regex_france_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-200">從關鍵字`Keywords_france_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-200">A keyword from  `Keywords_france_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_mobile_number"/>
          <Match idRef="Keywords_france_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_france_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="germany"></a><span data-ttu-id="5988d-201">德國</span><span class="sxs-lookup"><span data-stu-id="5988d-201">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-202">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-202">Pattern</span></span>

-  <span data-ttu-id="5988d-203">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-203">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-204">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-204">Checksum</span></span>

<span data-ttu-id="5988d-205">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-205">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-206">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-206">Definition</span></span>

<span data-ttu-id="5988d-207">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-207">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-208">規則運算式`Regex_germany_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-208">The regular expression  `Regex_germany_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-209">規則運算式`Regex_germany_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-209">The regular expression  `Regex_germany_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-210">從關鍵字`Keywords_germany_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-210">A keyword from  `Keywords_germany_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_mobile_number"/>
          <Match idRef="Keywords_germany_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_germany_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="greece"></a><span data-ttu-id="5988d-211">希臘</span><span class="sxs-lookup"><span data-stu-id="5988d-211">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-212">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-212">Pattern</span></span>

-  <span data-ttu-id="5988d-213">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-213">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-214">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-214">Checksum</span></span>

<span data-ttu-id="5988d-215">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-215">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-216">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-216">Definition</span></span>

<span data-ttu-id="5988d-217">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-217">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-218">規則運算式`Regex_greece_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-218">The regular expression  `Regex_greece_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-219">規則運算式`Regex_greece_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-219">The regular expression  `Regex_greece_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-220">從關鍵字`Keywords_greece_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-220">A keyword from  `Keywords_greece_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_mobile_number"/>
          <Match idRef="Keywords_greece_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_greece_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="hungary"></a><span data-ttu-id="5988d-221">匈牙利</span><span class="sxs-lookup"><span data-stu-id="5988d-221">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-222">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-222">Pattern</span></span>

-  <span data-ttu-id="5988d-223">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-223">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-224">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-224">Checksum</span></span>

<span data-ttu-id="5988d-225">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-225">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-226">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-226">Definition</span></span>

<span data-ttu-id="5988d-227">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-227">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-228">規則運算式`Regex_hungary_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-228">The regular expression  `Regex_hungary_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-229">規則運算式`Regex_hungary_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-229">The regular expression  `Regex_hungary_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-230">從關鍵字`Keywords_hungary_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-230">A keyword from  `Keywords_hungary_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_mobile_number"/>
          <Match idRef="Keywords_hungary_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_hungary_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="ireland"></a><span data-ttu-id="5988d-231">Ireland</span><span class="sxs-lookup"><span data-stu-id="5988d-231">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-232">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-232">Pattern</span></span>

-  <span data-ttu-id="5988d-233">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-233">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-234">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-234">Checksum</span></span>

<span data-ttu-id="5988d-235">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-235">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-236">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-236">Definition</span></span>

<span data-ttu-id="5988d-237">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-237">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-238">規則運算式`Regex_ireland_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-238">The regular expression  `Regex_ireland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-239">規則運算式`Regex_ireland_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-239">The regular expression  `Regex_ireland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-240">從關鍵字`Keywords_ireland_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-240">A keyword from  `Keywords_ireland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_mobile_number"/>
          <Match idRef="Keywords_ireland_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_ireland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="italy"></a><span data-ttu-id="5988d-241">義大利</span><span class="sxs-lookup"><span data-stu-id="5988d-241">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-242">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-242">Pattern</span></span>

-  <span data-ttu-id="5988d-243">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-243">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-244">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-244">Checksum</span></span>

<span data-ttu-id="5988d-245">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-245">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-246">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-246">Definition</span></span>

<span data-ttu-id="5988d-247">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-248">規則運算式`Regex_italy_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-248">The regular expression  `Regex_italy_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-249">規則運算式`Regex_italy_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-249">The regular expression  `Regex_italy_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-250">從關鍵字`Keywords_italy_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-250">A keyword from  `Keywords_italy_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_mobile_number"/>
          <Match idRef="Keywords_italy_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_italy_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="latvia"></a><span data-ttu-id="5988d-251">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="5988d-251">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-252">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-252">Pattern</span></span>

-  <span data-ttu-id="5988d-253">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-253">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-254">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-254">Checksum</span></span>

<span data-ttu-id="5988d-255">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-255">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-256">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-256">Definition</span></span>

<span data-ttu-id="5988d-257">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-257">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-258">規則運算式`Regex_latvia_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-258">The regular expression  `Regex_latvia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-259">規則運算式`Regex_latvia_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-259">The regular expression  `Regex_latvia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-260">從關鍵字`Keywords_latvia_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-260">A keyword from  `Keywords_latvia_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_mobile_number"/>
          <Match idRef="Keywords_latvia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_latvia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="lithuania"></a><span data-ttu-id="5988d-261">立陶宛</span><span class="sxs-lookup"><span data-stu-id="5988d-261">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-262">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-262">Pattern</span></span>

-  <span data-ttu-id="5988d-263">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-263">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-264">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-264">Checksum</span></span>

<span data-ttu-id="5988d-265">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-265">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-266">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-266">Definition</span></span>

<span data-ttu-id="5988d-267">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-268">規則運算式`Regex_lithuania_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-268">The regular expression  `Regex_lithuania_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-269">規則運算式`Regex_lithuania_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-269">The regular expression  `Regex_lithuania_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-270">從關鍵字`Keywords_lithuania_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-270">A keyword from  `Keywords_lithuania_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_mobile_number"/>
          <Match idRef="Keywords_lithuania_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_lithuania_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="luxemburg"></a><span data-ttu-id="5988d-271">盧森堡</span><span class="sxs-lookup"><span data-stu-id="5988d-271">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-272">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-272">Pattern</span></span>

-  <span data-ttu-id="5988d-273">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-273">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-274">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-274">Checksum</span></span>

<span data-ttu-id="5988d-275">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-275">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-276">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-276">Definition</span></span>

<span data-ttu-id="5988d-277">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-277">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-278">規則運算式`Regex_luxumburg_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-278">The regular expression  `Regex_luxumburg_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-279">規則運算式`Regex_luxumburg_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-279">The regular expression  `Regex_luxumburg_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-280">從關鍵字`Keywords_luxumburg_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-280">A keyword from  `Keywords_luxumburg_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxumburg_eu_mobile_number"/>
          <Match idRef="Keywords_luxumburg_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_luxumburg_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="malta"></a><span data-ttu-id="5988d-281">馬爾他</span><span class="sxs-lookup"><span data-stu-id="5988d-281">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-282">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-282">Pattern</span></span>

-  <span data-ttu-id="5988d-283">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-283">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-284">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-284">Checksum</span></span>

<span data-ttu-id="5988d-285">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-285">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-286">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-286">Definition</span></span>

<span data-ttu-id="5988d-287">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-287">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-288">規則運算式`Regex_malta_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-288">The regular expression  `Regex_malta_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-289">規則運算式`Regex_malta_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-289">The regular expression  `Regex_malta_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-290">從關鍵字`Keywords_malta_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-290">A keyword from  `Keywords_malta_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_mobile_number"/>
          <Match idRef="Keywords_malta_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_malta_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="netherlands"></a><span data-ttu-id="5988d-291">荷蘭</span><span class="sxs-lookup"><span data-stu-id="5988d-291">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-292">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-292">Pattern</span></span>

-  <span data-ttu-id="5988d-293">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-293">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-294">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-294">Checksum</span></span>

<span data-ttu-id="5988d-295">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-295">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-296">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-296">Definition</span></span>

<span data-ttu-id="5988d-297">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-297">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-298">規則運算式`Regex_netherlands_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-298">The regular expression  `Regex_netherlands_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-299">規則運算式`Regex_netherlands_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-299">The regular expression  `Regex_netherlands_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-300">從關鍵字`Keywords_netherlands_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-300">A keyword from  `Keywords_netherlands_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_mobile_number"/>
          <Match idRef="Keywords_netherlands_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_netherlands_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="poland"></a><span data-ttu-id="5988d-301">波蘭</span><span class="sxs-lookup"><span data-stu-id="5988d-301">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-302">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-302">Pattern</span></span>

-  <span data-ttu-id="5988d-303">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-303">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-304">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-304">Checksum</span></span>

<span data-ttu-id="5988d-305">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-305">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-306">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-306">Definition</span></span>

<span data-ttu-id="5988d-307">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-307">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-308">規則運算式`Regex_poland_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-308">The regular expression  `Regex_poland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-309">規則運算式`Regex_poland_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-309">The regular expression  `Regex_poland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-310">從關鍵字`Keywords_poland_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-310">A keyword from  `Keywords_poland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_mobile_number"/>
          <Match idRef="Keywords_poland_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_poland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="portugal"></a><span data-ttu-id="5988d-311">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="5988d-311">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-312">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-312">Pattern</span></span>

-  <span data-ttu-id="5988d-313">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-313">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-314">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-314">Checksum</span></span>

<span data-ttu-id="5988d-315">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-315">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-316">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-316">Definition</span></span>

<span data-ttu-id="5988d-317">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-317">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-318">規則運算式`Regex_portugal_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-318">The regular expression  `Regex_portugal_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-319">規則運算式`Regex_portugal_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-319">The regular expression  `Regex_portugal_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-320">從關鍵字`Keywords_portugal_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-320">A keyword from  `Keywords_portugal_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_mobile_number"/>
          <Match idRef="Keywords_portugal_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_portugal_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="romania"></a><span data-ttu-id="5988d-321">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="5988d-321">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-322">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-322">Pattern</span></span>

-  <span data-ttu-id="5988d-323">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-323">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-324">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-324">Checksum</span></span>

<span data-ttu-id="5988d-325">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-325">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-326">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-326">Definition</span></span>

<span data-ttu-id="5988d-327">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-327">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-328">規則運算式`Regex_romania_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-328">The regular expression  `Regex_romania_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-329">規則運算式`Regex_romania_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-329">The regular expression  `Regex_romania_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-330">從關鍵字`Keywords_romania_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-330">A keyword from  `Keywords_romania_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_mobile_number"/>
          <Match idRef="Keywords_romania_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_romania_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="slovakia"></a><span data-ttu-id="5988d-331">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="5988d-331">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-332">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-332">Pattern</span></span>

-  <span data-ttu-id="5988d-333">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-333">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-334">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-334">Checksum</span></span>

<span data-ttu-id="5988d-335">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-335">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-336">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-336">Definition</span></span>

<span data-ttu-id="5988d-337">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-337">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-338">規則運算式`Regex_slovakia_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-338">The regular expression  `Regex_slovakia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-339">規則運算式`Regex_slovakia_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-339">The regular expression  `Regex_slovakia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-340">從關鍵字`Keywords_slovakia_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-340">A keyword from  `Keywords_slovakia_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_mobile_number"/>
          <Match idRef="Keywords_slovakia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_slovakia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="slovenia"></a><span data-ttu-id="5988d-341">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="5988d-341">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-342">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-342">Pattern</span></span>

-  <span data-ttu-id="5988d-343">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-343">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-344">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-344">Checksum</span></span>

<span data-ttu-id="5988d-345">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-345">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-346">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-346">Definition</span></span>

<span data-ttu-id="5988d-347">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-347">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-348">規則運算式`Regex_slovenia_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-348">The regular expression  `Regex_slovenia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-349">規則運算式`Regex_slovenia_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-349">The regular expression  `Regex_slovenia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-350">從關鍵字`Keywords_slovenia_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-350">A keyword from  `Keywords_slovenia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_mobile_number"/>
          <Match idRef="Keywords_slovenia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_slovenia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="spain"></a><span data-ttu-id="5988d-351">西班牙</span><span class="sxs-lookup"><span data-stu-id="5988d-351">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-352">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-352">Pattern</span></span>

-  <span data-ttu-id="5988d-353">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-353">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-354">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-354">Checksum</span></span>

<span data-ttu-id="5988d-355">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-355">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-356">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-356">Definition</span></span>

<span data-ttu-id="5988d-357">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-358">規則運算式`Regex_spain_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-358">The regular expression  `Regex_spain_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-359">規則運算式`Regex_spain_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-359">The regular expression  `Regex_spain_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-360">從關鍵字`Keywords_spain_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-360">A keyword from  `Keywords_spain_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_mobile_number"/>
          <Match idRef="Keywords_spain_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_spain_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="sweden"></a><span data-ttu-id="5988d-361">瑞典</span><span class="sxs-lookup"><span data-stu-id="5988d-361">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-362">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-362">Pattern</span></span>

-  <span data-ttu-id="5988d-363">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-363">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-364">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-364">Checksum</span></span>

<span data-ttu-id="5988d-365">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-365">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-366">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-366">Definition</span></span>

<span data-ttu-id="5988d-367">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-367">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-368">規則運算式`Regex_sweden_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-368">The regular expression  `Regex_sweden_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-369">規則運算式`Regex_sweden_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-369">The regular expression  `Regex_sweden_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-370">從關鍵字`Keywords_sweden_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-370">A keyword from  `Keywords_sweden_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_mobile_number"/>
          <Match idRef="Keywords_sweden_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_sweden_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="uk"></a><span data-ttu-id="5988d-371">英國</span><span class="sxs-lookup"><span data-stu-id="5988d-371">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="5988d-372">模式</span><span class="sxs-lookup"><span data-stu-id="5988d-372">Pattern</span></span>

-  <span data-ttu-id="5988d-373">數字</span><span class="sxs-lookup"><span data-stu-id="5988d-373">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5988d-374">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="5988d-374">Checksum</span></span>

<span data-ttu-id="5988d-375">不適用</span><span class="sxs-lookup"><span data-stu-id="5988d-375">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5988d-376">定義</span><span class="sxs-lookup"><span data-stu-id="5988d-376">Definition</span></span>

<span data-ttu-id="5988d-377">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="5988d-377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5988d-378">規則運算式`Regex_uk_eu_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-378">The regular expression  `Regex_uk_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-379">規則運算式`Regex_uk_eu_formatted_mobile_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="5988d-379">The regular expression  `Regex_uk_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5988d-380">從關鍵字`Keywords_uk_eu_mobile_number`找到。</span><span class="sxs-lookup"><span data-stu-id="5988d-380">A keyword from  `Keywords_uk_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_mobile_number"/>
          <Match idRef="Keywords_uk_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_uk_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="see-also"></a><span data-ttu-id="5988d-381">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5988d-381">See also</span></span>

[<span data-ttu-id="5988d-382">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="5988d-382">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

