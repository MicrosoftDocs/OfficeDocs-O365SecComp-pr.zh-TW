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
# <a name="eu-passport-number"></a><span data-ttu-id="64647-104">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-104">EU Passport Number</span></span>

<span data-ttu-id="64647-p102">本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟護照號碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。</span><span class="sxs-lookup"><span data-stu-id="64647-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="64647-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="64647-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="64647-108">格式</span><span class="sxs-lookup"><span data-stu-id="64647-108">Format</span></span>

<span data-ttu-id="64647-109">後面接著選用的空間和七位數字的一個字母</span><span class="sxs-lookup"><span data-stu-id="64647-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-110">模式</span><span class="sxs-lookup"><span data-stu-id="64647-110">Pattern</span></span>

<span data-ttu-id="64647-111">一個字母、 七位數字和一個空格的組合：</span><span class="sxs-lookup"><span data-stu-id="64647-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="64647-112">一個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="64647-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="64647-113">一個空格 （選擇性）</span><span class="sxs-lookup"><span data-stu-id="64647-113">One space (optional)</span></span>
    
- <span data-ttu-id="64647-114">七位數</span><span class="sxs-lookup"><span data-stu-id="64647-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="64647-115">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-115">Checksum</span></span>

<span data-ttu-id="64647-116">不適用</span><span class="sxs-lookup"><span data-stu-id="64647-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-117">定義</span><span class="sxs-lookup"><span data-stu-id="64647-117">Definition</span></span>

<span data-ttu-id="64647-118">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-119">規則運算式`Regex_austria_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-120">從關鍵字`Keywords_austria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-121">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-121">Keywords</span></span>

<span data-ttu-id="64647-122">| |</span><span class="sxs-lookup"><span data-stu-id="64647-122"></span></span>
|<span data-ttu-id="64647-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-124">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-124">passport number</span></span>  <br/> <span data-ttu-id="64647-125">奧地利護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-125">austrian passport number</span></span>  <br/> <span data-ttu-id="64647-126">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-126">passport no</span></span>  <br/> <span data-ttu-id="64647-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="64647-127">reisepass</span></span>  <br/> <span data-ttu-id="64647-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="64647-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="64647-129">比利時</span><span class="sxs-lookup"><span data-stu-id="64647-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="64647-130">格式</span><span class="sxs-lookup"><span data-stu-id="64647-130">Format</span></span>

<span data-ttu-id="64647-131">後面接著任何空格或分隔符號的六個位數字的兩個字母</span><span class="sxs-lookup"><span data-stu-id="64647-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-132">模式</span><span class="sxs-lookup"><span data-stu-id="64647-132">Pattern</span></span>

<span data-ttu-id="64647-133">兩個字母和後面接著 6 位數</span><span class="sxs-lookup"><span data-stu-id="64647-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64647-134">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-134">Checksum</span></span>

<span data-ttu-id="64647-135">不適用</span><span class="sxs-lookup"><span data-stu-id="64647-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-136">定義</span><span class="sxs-lookup"><span data-stu-id="64647-136">Definition</span></span>

<span data-ttu-id="64647-137">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-138">規則運算式`Regex_belgium_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-139">從關鍵字`Keywords_belgium_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-140">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-140">Keywords</span></span>

<span data-ttu-id="64647-141">| |</span><span class="sxs-lookup"><span data-stu-id="64647-141"></span></span>
|<span data-ttu-id="64647-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-143">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-143">passport number</span></span>  <br/> <span data-ttu-id="64647-144">比利時護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-144">belgian passport number</span></span>  <br/> <span data-ttu-id="64647-145">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-145">passport no</span></span>  <br/> <span data-ttu-id="64647-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="64647-146">paspoort</span></span>  <br/> <span data-ttu-id="64647-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="64647-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="64647-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="64647-148">reisepass kein</span></span>  <br/> <span data-ttu-id="64647-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="64647-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="64647-150">保加利亞</span><span class="sxs-lookup"><span data-stu-id="64647-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="64647-151">格式</span><span class="sxs-lookup"><span data-stu-id="64647-151">Format</span></span>

<span data-ttu-id="64647-152">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="64647-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-153">模式</span><span class="sxs-lookup"><span data-stu-id="64647-153">Pattern</span></span>

 <span data-ttu-id="64647-154">九位數</span><span class="sxs-lookup"><span data-stu-id="64647-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="64647-155">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-155">Checksum</span></span>

<span data-ttu-id="64647-156">否</span><span class="sxs-lookup"><span data-stu-id="64647-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-157">定義</span><span class="sxs-lookup"><span data-stu-id="64647-157">Definition</span></span>

<span data-ttu-id="64647-158">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-159">規則運算式`Regex_bulgaria_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-160">從關鍵字`Keywords_bulgaria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-161">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-161">Keywords</span></span>

<span data-ttu-id="64647-162">| |</span><span class="sxs-lookup"><span data-stu-id="64647-162"></span></span>
|<span data-ttu-id="64647-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-164">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-164">passport number</span></span>  <br/> <span data-ttu-id="64647-165">保加利亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="64647-166">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-166">passport no</span></span>  <br/> <span data-ttu-id="64647-167">НОМЕР НА ПАСПОРТА</span><span class="sxs-lookup"><span data-stu-id="64647-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="64647-168">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="64647-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="64647-169">格式</span><span class="sxs-lookup"><span data-stu-id="64647-169">Format</span></span>

<span data-ttu-id="64647-170">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="64647-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-171">模式</span><span class="sxs-lookup"><span data-stu-id="64647-171">Pattern</span></span>

 <span data-ttu-id="64647-172">九位數</span><span class="sxs-lookup"><span data-stu-id="64647-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="64647-173">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-173">Checksum</span></span>

<span data-ttu-id="64647-174">否</span><span class="sxs-lookup"><span data-stu-id="64647-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-175">定義</span><span class="sxs-lookup"><span data-stu-id="64647-175">Definition</span></span>

<span data-ttu-id="64647-176">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-177">規則運算式`Regex_croatia_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-178">從關鍵字`Keywords_croatia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-179">Keywords</span></span>

<span data-ttu-id="64647-180">| |</span><span class="sxs-lookup"><span data-stu-id="64647-180"></span></span>
|<span data-ttu-id="64647-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-182">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-182">passport number</span></span>  <br/> <span data-ttu-id="64647-183">克羅埃西亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-183">croatian passport number</span></span>  <br/> <span data-ttu-id="64647-184">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-184">passport no</span></span>  <br/> <span data-ttu-id="64647-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="64647-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="64647-186">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="64647-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="64647-187">格式</span><span class="sxs-lookup"><span data-stu-id="64647-187">Format</span></span>

<span data-ttu-id="64647-188">後面接著任何空格或分隔符號 6-8 位數字的一個字母</span><span class="sxs-lookup"><span data-stu-id="64647-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-189">模式</span><span class="sxs-lookup"><span data-stu-id="64647-189">Pattern</span></span>

<span data-ttu-id="64647-190">後面接著六到八個位數字的一個字母</span><span class="sxs-lookup"><span data-stu-id="64647-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64647-191">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-191">Checksum</span></span>

<span data-ttu-id="64647-192">否</span><span class="sxs-lookup"><span data-stu-id="64647-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-193">定義</span><span class="sxs-lookup"><span data-stu-id="64647-193">Definition</span></span>

<span data-ttu-id="64647-194">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-195">規則運算式`Regex_cyprus_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-196">從關鍵字`Keywords_cyprus_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-197">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-197">Keywords</span></span>

<span data-ttu-id="64647-198">| |</span><span class="sxs-lookup"><span data-stu-id="64647-198"></span></span>
|<span data-ttu-id="64647-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-200">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-200">passport number</span></span>  <br/> <span data-ttu-id="64647-201">賽普勒斯護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="64647-202">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-202">passport no</span></span>  <br/> <span data-ttu-id="64647-203">ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ</span><span class="sxs-lookup"><span data-stu-id="64647-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="64647-204">捷克</span><span class="sxs-lookup"><span data-stu-id="64647-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="64647-205">格式</span><span class="sxs-lookup"><span data-stu-id="64647-205">Format</span></span>

<span data-ttu-id="64647-206">不含空格或分隔字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="64647-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-207">模式</span><span class="sxs-lookup"><span data-stu-id="64647-207">Pattern</span></span>

<span data-ttu-id="64647-208">不含空格或分隔字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="64647-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64647-209">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-209">Checksum</span></span>

<span data-ttu-id="64647-210">否</span><span class="sxs-lookup"><span data-stu-id="64647-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-211">定義</span><span class="sxs-lookup"><span data-stu-id="64647-211">Definition</span></span>

<span data-ttu-id="64647-212">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-213">規則運算式`Regex_czech_republic_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-214">從關鍵字`Keywords_czech_republic_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-215">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-215">Keywords</span></span>

<span data-ttu-id="64647-216">| |</span><span class="sxs-lookup"><span data-stu-id="64647-216"></span></span>
|<span data-ttu-id="64647-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-218">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-218">passport number</span></span>  <br/> <span data-ttu-id="64647-219">捷克護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-219">czech passport number</span></span>  <br/> <span data-ttu-id="64647-220">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-220">passport no</span></span>  <br/> <span data-ttu-id="64647-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="64647-221">cestovní pas</span></span>  <br/> <span data-ttu-id="64647-222">pas</span><span class="sxs-lookup"><span data-stu-id="64647-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="64647-223">丹麥</span><span class="sxs-lookup"><span data-stu-id="64647-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="64647-224">格式</span><span class="sxs-lookup"><span data-stu-id="64647-224">Format</span></span>

<span data-ttu-id="64647-225">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="64647-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-226">模式</span><span class="sxs-lookup"><span data-stu-id="64647-226">Pattern</span></span>

 <span data-ttu-id="64647-227">九位數</span><span class="sxs-lookup"><span data-stu-id="64647-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="64647-228">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-228">Checksum</span></span>

<span data-ttu-id="64647-229">否</span><span class="sxs-lookup"><span data-stu-id="64647-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-230">定義</span><span class="sxs-lookup"><span data-stu-id="64647-230">Definition</span></span>

<span data-ttu-id="64647-231">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-232">規則運算式`Regex_denmark_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-233">從關鍵字`Keywords_denmark_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-234">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-234">Keywords</span></span>

<span data-ttu-id="64647-235">| |</span><span class="sxs-lookup"><span data-stu-id="64647-235"></span></span>
|<span data-ttu-id="64647-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-237">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-237">passport number</span></span>  <br/> <span data-ttu-id="64647-238">丹麥文護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-238">danish passport number</span></span>  <br/> <span data-ttu-id="64647-239">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-239">passport no</span></span>  <br/> <span data-ttu-id="64647-240">pas</span><span class="sxs-lookup"><span data-stu-id="64647-240">pas</span></span>  <br/> <span data-ttu-id="64647-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="64647-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="64647-242">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="64647-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="64647-243">格式</span><span class="sxs-lookup"><span data-stu-id="64647-243">Format</span></span>

<span data-ttu-id="64647-244">後面接著任何空格或分隔符號七位數字的一個字母</span><span class="sxs-lookup"><span data-stu-id="64647-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-245">模式</span><span class="sxs-lookup"><span data-stu-id="64647-245">Pattern</span></span>

<span data-ttu-id="64647-246">後面七位數字的一個字母</span><span class="sxs-lookup"><span data-stu-id="64647-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64647-247">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-247">Checksum</span></span>

<span data-ttu-id="64647-248">否</span><span class="sxs-lookup"><span data-stu-id="64647-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-249">定義</span><span class="sxs-lookup"><span data-stu-id="64647-249">Definition</span></span>

<span data-ttu-id="64647-250">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-251">規則運算式`Regex_estonia_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-252">從關鍵字`Keywords_estonia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-253">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-253">Keywords</span></span>

<span data-ttu-id="64647-254">| |</span><span class="sxs-lookup"><span data-stu-id="64647-254"></span></span>
|<span data-ttu-id="64647-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-256">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-256">passport number</span></span>  <br/> <span data-ttu-id="64647-257">愛沙尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-257">estonian passport number</span></span>  <br/> <span data-ttu-id="64647-258">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-258">passport no</span></span>  <br/> <span data-ttu-id="64647-259">eesti kodaniku 複雜</span><span class="sxs-lookup"><span data-stu-id="64647-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="64647-260">芬蘭</span><span class="sxs-lookup"><span data-stu-id="64647-260">Finland</span></span>

<span data-ttu-id="64647-261">如需詳細資訊，請參閱節"芬蘭護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="64647-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="64647-262">法國</span><span class="sxs-lookup"><span data-stu-id="64647-262">France</span></span>

<span data-ttu-id="64647-263">如需詳細資訊，請參閱節"法國護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="64647-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="64647-264">德國</span><span class="sxs-lookup"><span data-stu-id="64647-264">Germany</span></span>

<span data-ttu-id="64647-265">如需詳細資訊，請參閱節"德國護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="64647-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="64647-266">希臘</span><span class="sxs-lookup"><span data-stu-id="64647-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="64647-267">格式</span><span class="sxs-lookup"><span data-stu-id="64647-267">Format</span></span>

<span data-ttu-id="64647-268">後面接著任何空格或分隔符號七位數字的兩個字母</span><span class="sxs-lookup"><span data-stu-id="64647-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-269">模式</span><span class="sxs-lookup"><span data-stu-id="64647-269">Pattern</span></span>

<span data-ttu-id="64647-270">兩個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="64647-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64647-271">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-271">Checksum</span></span>

<span data-ttu-id="64647-272">否</span><span class="sxs-lookup"><span data-stu-id="64647-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-273">定義</span><span class="sxs-lookup"><span data-stu-id="64647-273">Definition</span></span>

<span data-ttu-id="64647-274">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-275">規則運算式`Regex_greece_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-276">從關鍵字`Keywords_greece_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-277">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-277">Keywords</span></span>

<span data-ttu-id="64647-278">| |</span><span class="sxs-lookup"><span data-stu-id="64647-278"></span></span>
|<span data-ttu-id="64647-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-280">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-280">passport number</span></span>  <br/> <span data-ttu-id="64647-281">希臘文護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-281">greek passport number</span></span>  <br/> <span data-ttu-id="64647-282">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-282">passport no</span></span>  <br/> <span data-ttu-id="64647-283">ΔΙΑΒΑΤΗΡΙΟ</span><span class="sxs-lookup"><span data-stu-id="64647-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="64647-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="64647-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="64647-285">格式</span><span class="sxs-lookup"><span data-stu-id="64647-285">Format</span></span>

<span data-ttu-id="64647-286">後面接著任何空格或分隔符號的六個或七位數字的兩個字母</span><span class="sxs-lookup"><span data-stu-id="64647-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-287">模式</span><span class="sxs-lookup"><span data-stu-id="64647-287">Pattern</span></span>

<span data-ttu-id="64647-288">後面接著六個或七位數字的兩個字母</span><span class="sxs-lookup"><span data-stu-id="64647-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64647-289">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-289">Checksum</span></span>

<span data-ttu-id="64647-290">否</span><span class="sxs-lookup"><span data-stu-id="64647-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-291">定義</span><span class="sxs-lookup"><span data-stu-id="64647-291">Definition</span></span>

<span data-ttu-id="64647-292">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-293">規則運算式`Regex_hungary_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-294">從關鍵字`Keywords_hungary_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-295">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-295">Keywords</span></span>

<span data-ttu-id="64647-296">| |</span><span class="sxs-lookup"><span data-stu-id="64647-296"></span></span>
|<span data-ttu-id="64647-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-298">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-298">passport number</span></span>  <br/> <span data-ttu-id="64647-299">匈牙利文護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="64647-300">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-300">passport no</span></span>  <br/> <span data-ttu-id="64647-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="64647-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="64647-302">Ireland</span><span class="sxs-lookup"><span data-stu-id="64647-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="64647-303">格式</span><span class="sxs-lookup"><span data-stu-id="64647-303">Format</span></span>

<span data-ttu-id="64647-304">兩個字母或數字後面接著任何空格或分隔符號七位數字</span><span class="sxs-lookup"><span data-stu-id="64647-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-305">模式</span><span class="sxs-lookup"><span data-stu-id="64647-305">Pattern</span></span>

<span data-ttu-id="64647-306">兩個字母或數字後面七位數字：</span><span class="sxs-lookup"><span data-stu-id="64647-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="64647-307">兩個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="64647-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="64647-308">七位數</span><span class="sxs-lookup"><span data-stu-id="64647-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="64647-309">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-309">Checksum</span></span>

<span data-ttu-id="64647-310">否</span><span class="sxs-lookup"><span data-stu-id="64647-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-311">定義</span><span class="sxs-lookup"><span data-stu-id="64647-311">Definition</span></span>

<span data-ttu-id="64647-312">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-313">規則運算式`Regex_ireland_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-314">從關鍵字`Keywords_ireland_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-315">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-315">Keywords</span></span>

<span data-ttu-id="64647-316">| |</span><span class="sxs-lookup"><span data-stu-id="64647-316"></span></span>
|<span data-ttu-id="64647-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-318">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-318">passport number</span></span>  <br/> <span data-ttu-id="64647-319">愛爾蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-319">irish passport number</span></span>  <br/> <span data-ttu-id="64647-320">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-320">passport no</span></span>  <br/> <span data-ttu-id="64647-321">pas</span><span class="sxs-lookup"><span data-stu-id="64647-321">pas</span></span>  <br/> <span data-ttu-id="64647-322">passport</span><span class="sxs-lookup"><span data-stu-id="64647-322">passport</span></span>  <br/> <span data-ttu-id="64647-323">passeport</span><span class="sxs-lookup"><span data-stu-id="64647-323">passeport</span></span>  <br/> <span data-ttu-id="64647-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="64647-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="64647-325">義大利</span><span class="sxs-lookup"><span data-stu-id="64647-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="64647-326">格式</span><span class="sxs-lookup"><span data-stu-id="64647-326">Format</span></span>

<span data-ttu-id="64647-327">兩個字母或數字後面接著任何空格或分隔符號七位數字</span><span class="sxs-lookup"><span data-stu-id="64647-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-328">模式</span><span class="sxs-lookup"><span data-stu-id="64647-328">Pattern</span></span>

<span data-ttu-id="64647-329">兩個字母或數字後面七位數字：</span><span class="sxs-lookup"><span data-stu-id="64647-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="64647-330">兩個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="64647-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="64647-331">七位數</span><span class="sxs-lookup"><span data-stu-id="64647-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="64647-332">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-332">Checksum</span></span>

<span data-ttu-id="64647-333">不適用</span><span class="sxs-lookup"><span data-stu-id="64647-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-334">定義</span><span class="sxs-lookup"><span data-stu-id="64647-334">Definition</span></span>

<span data-ttu-id="64647-335">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-336">規則運算式`Regex_italy_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-337">從關鍵字`Keywords_italy_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-338">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-338">Keywords</span></span>

<span data-ttu-id="64647-339">| |</span><span class="sxs-lookup"><span data-stu-id="64647-339"></span></span>
|<span data-ttu-id="64647-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-341">義大利護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-341">italian passport number</span></span>  <br/> <span data-ttu-id="64647-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="64647-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="64647-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="64647-343">passaporto</span></span>  <br/> <span data-ttu-id="64647-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="64647-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="64647-345">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-345">passport number</span></span>  <br/> <span data-ttu-id="64647-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="64647-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="64647-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="64647-347">passaporto numero</span></span>  <br/> <span data-ttu-id="64647-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="64647-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="64647-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="64647-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="64647-350">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="64647-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="64647-351">格式</span><span class="sxs-lookup"><span data-stu-id="64647-351">Format</span></span>

<span data-ttu-id="64647-352">兩個字母或數字後面接著任何空格或分隔符號七位數字</span><span class="sxs-lookup"><span data-stu-id="64647-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-353">模式</span><span class="sxs-lookup"><span data-stu-id="64647-353">Pattern</span></span>

<span data-ttu-id="64647-354">兩個字母或數字後面七位數字：</span><span class="sxs-lookup"><span data-stu-id="64647-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="64647-355">兩個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="64647-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="64647-356">七位數</span><span class="sxs-lookup"><span data-stu-id="64647-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="64647-357">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-357">Checksum</span></span>

<span data-ttu-id="64647-358">否</span><span class="sxs-lookup"><span data-stu-id="64647-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-359">定義</span><span class="sxs-lookup"><span data-stu-id="64647-359">Definition</span></span>

<span data-ttu-id="64647-360">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-361">規則運算式`Regex_latvia_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-362">從關鍵字`Keywords_latvia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-363">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-363">Keywords</span></span>

<span data-ttu-id="64647-364">| |</span><span class="sxs-lookup"><span data-stu-id="64647-364"></span></span>
|<span data-ttu-id="64647-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-366">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-366">passport number</span></span>  <br/> <span data-ttu-id="64647-367">拉脫維亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-367">latvian passport number</span></span>  <br/> <span data-ttu-id="64647-368">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-368">passport no</span></span>  <br/> <span data-ttu-id="64647-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="64647-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="64647-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="64647-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="64647-371">格式</span><span class="sxs-lookup"><span data-stu-id="64647-371">Format</span></span>

<span data-ttu-id="64647-372">八個任何空格或分隔符號的字母或數字</span><span class="sxs-lookup"><span data-stu-id="64647-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-373">模式</span><span class="sxs-lookup"><span data-stu-id="64647-373">Pattern</span></span>

<span data-ttu-id="64647-374">八個字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="64647-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64647-375">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-375">Checksum</span></span>

<span data-ttu-id="64647-376">不適用</span><span class="sxs-lookup"><span data-stu-id="64647-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-377">定義</span><span class="sxs-lookup"><span data-stu-id="64647-377">Definition</span></span>

<span data-ttu-id="64647-378">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-379">規則運算式`Regex_lithuania_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-380">從關鍵字`Keywords_lithuania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-381">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-381">Keywords</span></span>

<span data-ttu-id="64647-382">| |</span><span class="sxs-lookup"><span data-stu-id="64647-382"></span></span>
|<span data-ttu-id="64647-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-384">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-384">passport number</span></span>  <br/> <span data-ttu-id="64647-385">lithunian 護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="64647-386">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-386">passport no</span></span>  <br/> <span data-ttu-id="64647-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="64647-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="64647-388">盧森堡</span><span class="sxs-lookup"><span data-stu-id="64647-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="64647-389">格式</span><span class="sxs-lookup"><span data-stu-id="64647-389">Format</span></span>

<span data-ttu-id="64647-390">八個任何空格或分隔符號的字母或數字</span><span class="sxs-lookup"><span data-stu-id="64647-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-391">模式</span><span class="sxs-lookup"><span data-stu-id="64647-391">Pattern</span></span>

<span data-ttu-id="64647-392">八個字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="64647-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64647-393">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-393">Checksum</span></span>

<span data-ttu-id="64647-394">否</span><span class="sxs-lookup"><span data-stu-id="64647-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-395">定義</span><span class="sxs-lookup"><span data-stu-id="64647-395">Definition</span></span>

<span data-ttu-id="64647-396">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-397">規則運算式`Regex_nation_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-398">從關鍵字`Keywords_nation_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-399">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-399">Keywords</span></span>

<span data-ttu-id="64647-400">| |</span><span class="sxs-lookup"><span data-stu-id="64647-400"></span></span>
|<span data-ttu-id="64647-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-402">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-402">passport number</span></span>  <br/> <span data-ttu-id="64647-403">拉脫維亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-403">latvian passport number</span></span>  <br/> <span data-ttu-id="64647-404">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-404">passport no</span></span>  <br/> <span data-ttu-id="64647-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="64647-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="64647-406">馬爾他</span><span class="sxs-lookup"><span data-stu-id="64647-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="64647-407">格式</span><span class="sxs-lookup"><span data-stu-id="64647-407">Format</span></span>

<span data-ttu-id="64647-408">不含空格或分隔符號七位數字</span><span class="sxs-lookup"><span data-stu-id="64647-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-409">模式</span><span class="sxs-lookup"><span data-stu-id="64647-409">Pattern</span></span>

 <span data-ttu-id="64647-410">七位數</span><span class="sxs-lookup"><span data-stu-id="64647-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="64647-411">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-411">Checksum</span></span>

<span data-ttu-id="64647-412">否</span><span class="sxs-lookup"><span data-stu-id="64647-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-413">定義</span><span class="sxs-lookup"><span data-stu-id="64647-413">Definition</span></span>

<span data-ttu-id="64647-414">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-415">規則運算式`Regex_malta_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-416">從關鍵字`Keywords_malta_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-417">Keywords</span></span>

<span data-ttu-id="64647-418">| |</span><span class="sxs-lookup"><span data-stu-id="64647-418"></span></span>
|<span data-ttu-id="64647-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-420">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-420">passport number</span></span>  <br/> <span data-ttu-id="64647-421">馬爾他護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-421">maltese passport number</span></span>  <br/> <span data-ttu-id="64647-422">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-422">passport no</span></span>  <br/> <span data-ttu-id="64647-423">numru tal passaport</span><span class="sxs-lookup"><span data-stu-id="64647-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="64647-424">荷蘭</span><span class="sxs-lookup"><span data-stu-id="64647-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="64647-425">格式</span><span class="sxs-lookup"><span data-stu-id="64647-425">Format</span></span>

<span data-ttu-id="64647-426">九個字母或數字與任何空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="64647-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-427">模式</span><span class="sxs-lookup"><span data-stu-id="64647-427">Pattern</span></span>

<span data-ttu-id="64647-428">九個字母或數字</span><span class="sxs-lookup"><span data-stu-id="64647-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64647-429">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-429">Checksum</span></span>

<span data-ttu-id="64647-430">不適用</span><span class="sxs-lookup"><span data-stu-id="64647-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-431">定義</span><span class="sxs-lookup"><span data-stu-id="64647-431">Definition</span></span>

<span data-ttu-id="64647-432">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-433">規則運算式`Regex_netherlands_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-434">從關鍵字`Keywords_netherlands_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-435">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-435">Keywords</span></span>

<span data-ttu-id="64647-436">| |</span><span class="sxs-lookup"><span data-stu-id="64647-436"></span></span>
|<span data-ttu-id="64647-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-438">荷蘭文護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-438">dutch passport number</span></span>  <br/> <span data-ttu-id="64647-439">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-439">passport number</span></span>  <br/> <span data-ttu-id="64647-440">荷蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="64647-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="64647-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="64647-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="64647-442">paspoort</span></span>  <br/> <span data-ttu-id="64647-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="64647-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="64647-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="64647-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="64647-445">波蘭</span><span class="sxs-lookup"><span data-stu-id="64647-445">Poland</span></span>

<span data-ttu-id="64647-446">如需詳細資訊，請參閱節"波蘭護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="64647-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="64647-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="64647-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="64647-448">格式</span><span class="sxs-lookup"><span data-stu-id="64647-448">Format</span></span>

<span data-ttu-id="64647-449">一個字母後面接著任何空格或分隔符號 6 位數</span><span class="sxs-lookup"><span data-stu-id="64647-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-450">模式</span><span class="sxs-lookup"><span data-stu-id="64647-450">Pattern</span></span>

<span data-ttu-id="64647-451">一個字母後面接著 6 位數：</span><span class="sxs-lookup"><span data-stu-id="64647-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="64647-452">一個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="64647-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="64647-453">六位數</span><span class="sxs-lookup"><span data-stu-id="64647-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="64647-454">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-454">Checksum</span></span>

<span data-ttu-id="64647-455">否</span><span class="sxs-lookup"><span data-stu-id="64647-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-456">定義</span><span class="sxs-lookup"><span data-stu-id="64647-456">Definition</span></span>

<span data-ttu-id="64647-457">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-458">規則運算式`Regex_portugal_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-459">從關鍵字`Keywords_portugal_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-460">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-460">Keywords</span></span>

<span data-ttu-id="64647-461">| |</span><span class="sxs-lookup"><span data-stu-id="64647-461"></span></span>
|<span data-ttu-id="64647-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-463">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-463">passport number</span></span>  <br/> <span data-ttu-id="64647-464">葡萄牙護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-464">portugese passport number</span></span>  <br/> <span data-ttu-id="64647-465">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-465">passport no</span></span>  <br/> <span data-ttu-id="64647-466">número 不要 passaporte</span><span class="sxs-lookup"><span data-stu-id="64647-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="64647-467">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="64647-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="64647-468">格式</span><span class="sxs-lookup"><span data-stu-id="64647-468">Format</span></span>

<span data-ttu-id="64647-469">不含空格和分隔字元的八個或九個位數</span><span class="sxs-lookup"><span data-stu-id="64647-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-470">模式</span><span class="sxs-lookup"><span data-stu-id="64647-470">Pattern</span></span>

<span data-ttu-id="64647-471">八個或 9 的數字</span><span class="sxs-lookup"><span data-stu-id="64647-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64647-472">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-472">Checksum</span></span>

<span data-ttu-id="64647-473">否</span><span class="sxs-lookup"><span data-stu-id="64647-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-474">定義</span><span class="sxs-lookup"><span data-stu-id="64647-474">Definition</span></span>

<span data-ttu-id="64647-475">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-476">規則運算式`Regex_romania_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-477">從關鍵字`Keywords_romania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-478">Keywords</span></span>

<span data-ttu-id="64647-479">| |</span><span class="sxs-lookup"><span data-stu-id="64647-479"></span></span>
|<span data-ttu-id="64647-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-481">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-481">passport number</span></span>  <br/> <span data-ttu-id="64647-482">羅馬尼亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-482">romanian passport number</span></span>  <br/> <span data-ttu-id="64647-483">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-483">passport no</span></span>  <br/> <span data-ttu-id="64647-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="64647-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="64647-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="64647-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="64647-486">格式</span><span class="sxs-lookup"><span data-stu-id="64647-486">Format</span></span>

<span data-ttu-id="64647-487">一個數字或字母後面接著任何空格或分隔符號七位數字</span><span class="sxs-lookup"><span data-stu-id="64647-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-488">模式</span><span class="sxs-lookup"><span data-stu-id="64647-488">Pattern</span></span>

<span data-ttu-id="64647-489">一個數字或字母後面七位數字 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="64647-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="64647-490">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-490">Checksum</span></span>

<span data-ttu-id="64647-491">否</span><span class="sxs-lookup"><span data-stu-id="64647-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-492">定義</span><span class="sxs-lookup"><span data-stu-id="64647-492">Definition</span></span>

<span data-ttu-id="64647-493">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-494">規則運算式`Regex_slovakia_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-495">從關鍵字`Keywords_slovakia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-496">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-496">Keywords</span></span>

<span data-ttu-id="64647-497">| |</span><span class="sxs-lookup"><span data-stu-id="64647-497"></span></span>
|<span data-ttu-id="64647-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-499">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-499">passport number</span></span>  <br/> <span data-ttu-id="64647-500">斯洛伐克護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="64647-501">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-501">passport no</span></span>  <br/> <span data-ttu-id="64647-502">Číslo pasu</span><span class="sxs-lookup"><span data-stu-id="64647-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="64647-503">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="64647-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="64647-504">格式</span><span class="sxs-lookup"><span data-stu-id="64647-504">Format</span></span>

<span data-ttu-id="64647-505">後面接著任何空格或分隔符號七位數字的兩個字母</span><span class="sxs-lookup"><span data-stu-id="64647-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-506">模式</span><span class="sxs-lookup"><span data-stu-id="64647-506">Pattern</span></span>

<span data-ttu-id="64647-507">後面七位數字的兩個字母：</span><span class="sxs-lookup"><span data-stu-id="64647-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="64647-508">字母"P"</span><span class="sxs-lookup"><span data-stu-id="64647-508">The letter "P"</span></span>
    
- <span data-ttu-id="64647-509">一個大寫字母</span><span class="sxs-lookup"><span data-stu-id="64647-509">One uppercase letter</span></span>
    
- <span data-ttu-id="64647-510">七位數</span><span class="sxs-lookup"><span data-stu-id="64647-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="64647-511">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-511">Checksum</span></span>

<span data-ttu-id="64647-512">否</span><span class="sxs-lookup"><span data-stu-id="64647-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-513">定義</span><span class="sxs-lookup"><span data-stu-id="64647-513">Definition</span></span>

<span data-ttu-id="64647-514">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-515">規則運算式`Regex_slovenia_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-516">從關鍵字`Keywords_slovenia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-517">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-517">Keywords</span></span>

<span data-ttu-id="64647-518">| |</span><span class="sxs-lookup"><span data-stu-id="64647-518"></span></span>
|<span data-ttu-id="64647-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-520">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-520">passport number</span></span>  <br/> <span data-ttu-id="64647-521">斯洛維尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="64647-522">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-522">passport no</span></span>  <br/> <span data-ttu-id="64647-523">Številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="64647-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="64647-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="64647-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="64647-525">格式</span><span class="sxs-lookup"><span data-stu-id="64647-525">Format</span></span>

<span data-ttu-id="64647-526">字母及號碼與任何空格或分隔符號八個或九個字元組合</span><span class="sxs-lookup"><span data-stu-id="64647-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="64647-527">模式</span><span class="sxs-lookup"><span data-stu-id="64647-527">Pattern</span></span>

<span data-ttu-id="64647-528">字母及數字 8 或九個字元組合：</span><span class="sxs-lookup"><span data-stu-id="64647-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="64647-529">兩個字母或數字</span><span class="sxs-lookup"><span data-stu-id="64647-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="64647-530">一個數字或字母 （選用）</span><span class="sxs-lookup"><span data-stu-id="64647-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="64647-531">六位數</span><span class="sxs-lookup"><span data-stu-id="64647-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="64647-532">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="64647-532">Checksum</span></span>

<span data-ttu-id="64647-533">不適用</span><span class="sxs-lookup"><span data-stu-id="64647-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="64647-534">定義</span><span class="sxs-lookup"><span data-stu-id="64647-534">Definition</span></span>

<span data-ttu-id="64647-535">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="64647-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="64647-536">規則運算式`Regex_spain_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="64647-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="64647-537">從關鍵字`Keywords_spain_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="64647-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="64647-538">關鍵字</span><span class="sxs-lookup"><span data-stu-id="64647-538">Keywords</span></span>

<span data-ttu-id="64647-539">| |</span><span class="sxs-lookup"><span data-stu-id="64647-539"></span></span>
|<span data-ttu-id="64647-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="64647-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="64647-541">passport</span><span class="sxs-lookup"><span data-stu-id="64647-541">passport</span></span>  <br/> <span data-ttu-id="64647-542">西班牙 passport</span><span class="sxs-lookup"><span data-stu-id="64647-542">spain passport</span></span>  <br/> <span data-ttu-id="64647-543">passport 活頁簿</span><span class="sxs-lookup"><span data-stu-id="64647-543">passport book</span></span>  <br/> <span data-ttu-id="64647-544">護照號碼</span><span class="sxs-lookup"><span data-stu-id="64647-544">passport number</span></span>  <br/> <span data-ttu-id="64647-545">passport 無</span><span class="sxs-lookup"><span data-stu-id="64647-545">passport no</span></span>  <br/> <span data-ttu-id="64647-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="64647-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="64647-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="64647-547">número pasaporte</span></span>  <br/> <span data-ttu-id="64647-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="64647-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="64647-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="64647-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="64647-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="64647-550">Sweden</span></span>

<span data-ttu-id="64647-551">如需詳細資訊，請參閱節"瑞典護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="64647-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="64647-552">英國</span><span class="sxs-lookup"><span data-stu-id="64647-552">UK</span></span>

<span data-ttu-id="64647-p103">如需詳細資訊，請參閱節"US/英國護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="64647-p103">For details, see the section "U.S. / U.K. Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="64647-555">另請參閱</span><span class="sxs-lookup"><span data-stu-id="64647-555">See also</span></span>

[<span data-ttu-id="64647-556">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="64647-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

