---
title: 歐盟護照號碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: 本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟護照號碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
ms.openlocfilehash: c46f683bd1baf651bcf13c1766dfff3cb953b341
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218263"
---
# <a name="eu-passport-number"></a><span data-ttu-id="8508e-104">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-104">EU Passport Number</span></span>

<span data-ttu-id="8508e-p102">本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟護照號碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。</span><span class="sxs-lookup"><span data-stu-id="8508e-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="8508e-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="8508e-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="8508e-108">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-108">Format</span></span>

<span data-ttu-id="8508e-109">後面接著選用的空間和七位數字的一個字母</span><span class="sxs-lookup"><span data-stu-id="8508e-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-110">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-110">Pattern</span></span>

<span data-ttu-id="8508e-111">一個字母、 七位數字和一個空格的組合：</span><span class="sxs-lookup"><span data-stu-id="8508e-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="8508e-112">一個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="8508e-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="8508e-113">一個空格 （選擇性）</span><span class="sxs-lookup"><span data-stu-id="8508e-113">One space (optional)</span></span>
    
- <span data-ttu-id="8508e-114">七位數</span><span class="sxs-lookup"><span data-stu-id="8508e-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8508e-115">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-115">Checksum</span></span>

<span data-ttu-id="8508e-116">不適用</span><span class="sxs-lookup"><span data-stu-id="8508e-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-117">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-117">Definition</span></span>

<span data-ttu-id="8508e-118">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-119">規則運算式`Regex_austria_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-120">從關鍵字`Keywords_austria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-121">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-121">Keywords</span></span>

<span data-ttu-id="8508e-122">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-122"></span></span>
|<span data-ttu-id="8508e-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-124">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-124">passport number</span></span>  <br/> <span data-ttu-id="8508e-125">奧地利護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-125">austrian passport number</span></span>  <br/> <span data-ttu-id="8508e-126">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-126">passport no</span></span>  <br/> <span data-ttu-id="8508e-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="8508e-127">reisepass</span></span>  <br/> <span data-ttu-id="8508e-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="8508e-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="8508e-129">比利時</span><span class="sxs-lookup"><span data-stu-id="8508e-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="8508e-130">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-130">Format</span></span>

<span data-ttu-id="8508e-131">後面接著任何空格或分隔符號的六個位數字的兩個字母</span><span class="sxs-lookup"><span data-stu-id="8508e-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-132">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-132">Pattern</span></span>

<span data-ttu-id="8508e-133">兩個字母和後面接著 6 位數</span><span class="sxs-lookup"><span data-stu-id="8508e-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8508e-134">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-134">Checksum</span></span>

<span data-ttu-id="8508e-135">不適用</span><span class="sxs-lookup"><span data-stu-id="8508e-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-136">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-136">Definition</span></span>

<span data-ttu-id="8508e-137">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-138">規則運算式`Regex_belgium_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-139">從關鍵字`Keywords_belgium_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-140">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-140">Keywords</span></span>

<span data-ttu-id="8508e-141">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-141"></span></span>
|<span data-ttu-id="8508e-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-143">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-143">passport number</span></span>  <br/> <span data-ttu-id="8508e-144">比利時護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-144">belgian passport number</span></span>  <br/> <span data-ttu-id="8508e-145">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-145">passport no</span></span>  <br/> <span data-ttu-id="8508e-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="8508e-146">paspoort</span></span>  <br/> <span data-ttu-id="8508e-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8508e-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="8508e-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="8508e-148">reisepass kein</span></span>  <br/> <span data-ttu-id="8508e-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="8508e-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="8508e-150">保加利亞</span><span class="sxs-lookup"><span data-stu-id="8508e-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="8508e-151">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-151">Format</span></span>

<span data-ttu-id="8508e-152">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="8508e-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-153">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-153">Pattern</span></span>

 <span data-ttu-id="8508e-154">九位數</span><span class="sxs-lookup"><span data-stu-id="8508e-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8508e-155">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-155">Checksum</span></span>

<span data-ttu-id="8508e-156">否</span><span class="sxs-lookup"><span data-stu-id="8508e-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-157">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-157">Definition</span></span>

<span data-ttu-id="8508e-158">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-159">規則運算式`Regex_bulgaria_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-160">從關鍵字`Keywords_bulgaria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-161">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-161">Keywords</span></span>

<span data-ttu-id="8508e-162">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-162"></span></span>
|<span data-ttu-id="8508e-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-164">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-164">passport number</span></span>  <br/> <span data-ttu-id="8508e-165">保加利亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="8508e-166">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-166">passport no</span></span>  <br/> <span data-ttu-id="8508e-167">НОМЕР НА ПАСПОРТА</span><span class="sxs-lookup"><span data-stu-id="8508e-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="8508e-168">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="8508e-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="8508e-169">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-169">Format</span></span>

<span data-ttu-id="8508e-170">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="8508e-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-171">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-171">Pattern</span></span>

 <span data-ttu-id="8508e-172">九位數</span><span class="sxs-lookup"><span data-stu-id="8508e-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8508e-173">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-173">Checksum</span></span>

<span data-ttu-id="8508e-174">否</span><span class="sxs-lookup"><span data-stu-id="8508e-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-175">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-175">Definition</span></span>

<span data-ttu-id="8508e-176">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-177">規則運算式`Regex_croatia_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-178">從關鍵字`Keywords_croatia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-179">Keywords</span></span>

<span data-ttu-id="8508e-180">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-180"></span></span>
|<span data-ttu-id="8508e-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-182">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-182">passport number</span></span>  <br/> <span data-ttu-id="8508e-183">克羅埃西亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-183">croatian passport number</span></span>  <br/> <span data-ttu-id="8508e-184">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-184">passport no</span></span>  <br/> <span data-ttu-id="8508e-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="8508e-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="8508e-186">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="8508e-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="8508e-187">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-187">Format</span></span>

<span data-ttu-id="8508e-188">後面接著任何空格或分隔符號 6-8 位數字的一個字母</span><span class="sxs-lookup"><span data-stu-id="8508e-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-189">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-189">Pattern</span></span>

<span data-ttu-id="8508e-190">後面接著六到八個位數字的一個字母</span><span class="sxs-lookup"><span data-stu-id="8508e-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8508e-191">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-191">Checksum</span></span>

<span data-ttu-id="8508e-192">否</span><span class="sxs-lookup"><span data-stu-id="8508e-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-193">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-193">Definition</span></span>

<span data-ttu-id="8508e-194">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-195">規則運算式`Regex_cyprus_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-196">從關鍵字`Keywords_cyprus_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-197">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-197">Keywords</span></span>

<span data-ttu-id="8508e-198">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-198"></span></span>
|<span data-ttu-id="8508e-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-200">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-200">passport number</span></span>  <br/> <span data-ttu-id="8508e-201">賽普勒斯護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="8508e-202">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-202">passport no</span></span>  <br/> <span data-ttu-id="8508e-203">ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ</span><span class="sxs-lookup"><span data-stu-id="8508e-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="8508e-204">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="8508e-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="8508e-205">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-205">Format</span></span>

<span data-ttu-id="8508e-206">不含空格或分隔字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="8508e-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-207">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-207">Pattern</span></span>

<span data-ttu-id="8508e-208">不含空格或分隔字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="8508e-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8508e-209">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-209">Checksum</span></span>

<span data-ttu-id="8508e-210">否</span><span class="sxs-lookup"><span data-stu-id="8508e-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-211">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-211">Definition</span></span>

<span data-ttu-id="8508e-212">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-213">規則運算式`Regex_czech_republic_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-214">從關鍵字`Keywords_czech_republic_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-215">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-215">Keywords</span></span>

<span data-ttu-id="8508e-216">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-216"></span></span>
|<span data-ttu-id="8508e-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-218">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-218">passport number</span></span>  <br/> <span data-ttu-id="8508e-219">捷克護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-219">czech passport number</span></span>  <br/> <span data-ttu-id="8508e-220">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-220">passport no</span></span>  <br/> <span data-ttu-id="8508e-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="8508e-221">cestovní pas</span></span>  <br/> <span data-ttu-id="8508e-222">pas</span><span class="sxs-lookup"><span data-stu-id="8508e-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="8508e-223">丹麥</span><span class="sxs-lookup"><span data-stu-id="8508e-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="8508e-224">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-224">Format</span></span>

<span data-ttu-id="8508e-225">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="8508e-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-226">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-226">Pattern</span></span>

 <span data-ttu-id="8508e-227">九位數</span><span class="sxs-lookup"><span data-stu-id="8508e-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8508e-228">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-228">Checksum</span></span>

<span data-ttu-id="8508e-229">否</span><span class="sxs-lookup"><span data-stu-id="8508e-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-230">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-230">Definition</span></span>

<span data-ttu-id="8508e-231">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-232">規則運算式`Regex_denmark_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-233">從關鍵字`Keywords_denmark_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-234">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-234">Keywords</span></span>

<span data-ttu-id="8508e-235">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-235"></span></span>
|<span data-ttu-id="8508e-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-237">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-237">passport number</span></span>  <br/> <span data-ttu-id="8508e-238">丹麥文護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-238">danish passport number</span></span>  <br/> <span data-ttu-id="8508e-239">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-239">passport no</span></span>  <br/> <span data-ttu-id="8508e-240">pas</span><span class="sxs-lookup"><span data-stu-id="8508e-240">pas</span></span>  <br/> <span data-ttu-id="8508e-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="8508e-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="8508e-242">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="8508e-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="8508e-243">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-243">Format</span></span>

<span data-ttu-id="8508e-244">後面接著任何空格或分隔符號七位數字的一個字母</span><span class="sxs-lookup"><span data-stu-id="8508e-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-245">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-245">Pattern</span></span>

<span data-ttu-id="8508e-246">後面七位數字的一個字母</span><span class="sxs-lookup"><span data-stu-id="8508e-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8508e-247">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-247">Checksum</span></span>

<span data-ttu-id="8508e-248">否</span><span class="sxs-lookup"><span data-stu-id="8508e-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-249">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-249">Definition</span></span>

<span data-ttu-id="8508e-250">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-251">規則運算式`Regex_estonia_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-252">從關鍵字`Keywords_estonia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-253">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-253">Keywords</span></span>

<span data-ttu-id="8508e-254">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-254"></span></span>
|<span data-ttu-id="8508e-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-256">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-256">passport number</span></span>  <br/> <span data-ttu-id="8508e-257">愛沙尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-257">estonian passport number</span></span>  <br/> <span data-ttu-id="8508e-258">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-258">passport no</span></span>  <br/> <span data-ttu-id="8508e-259">eesti kodaniku 複雜</span><span class="sxs-lookup"><span data-stu-id="8508e-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="8508e-260">芬蘭</span><span class="sxs-lookup"><span data-stu-id="8508e-260">Finland</span></span>

<span data-ttu-id="8508e-261">如需詳細資訊，請參閱節"芬蘭護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="8508e-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="8508e-262">法國</span><span class="sxs-lookup"><span data-stu-id="8508e-262">France</span></span>

<span data-ttu-id="8508e-263">如需詳細資訊，請參閱節"法國護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="8508e-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="8508e-264">德國</span><span class="sxs-lookup"><span data-stu-id="8508e-264">Germany</span></span>

<span data-ttu-id="8508e-265">如需詳細資訊，請參閱節"德國護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="8508e-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="8508e-266">希臘</span><span class="sxs-lookup"><span data-stu-id="8508e-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="8508e-267">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-267">Format</span></span>

<span data-ttu-id="8508e-268">後面接著任何空格或分隔符號七位數字的兩個字母</span><span class="sxs-lookup"><span data-stu-id="8508e-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-269">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-269">Pattern</span></span>

<span data-ttu-id="8508e-270">兩個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="8508e-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8508e-271">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-271">Checksum</span></span>

<span data-ttu-id="8508e-272">否</span><span class="sxs-lookup"><span data-stu-id="8508e-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-273">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-273">Definition</span></span>

<span data-ttu-id="8508e-274">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-275">規則運算式`Regex_greece_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-276">從關鍵字`Keywords_greece_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-277">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-277">Keywords</span></span>

<span data-ttu-id="8508e-278">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-278"></span></span>
|<span data-ttu-id="8508e-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-280">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-280">passport number</span></span>  <br/> <span data-ttu-id="8508e-281">希臘文護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-281">greek passport number</span></span>  <br/> <span data-ttu-id="8508e-282">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-282">passport no</span></span>  <br/> <span data-ttu-id="8508e-283">ΔΙΑΒΑΤΗΡΙΟ</span><span class="sxs-lookup"><span data-stu-id="8508e-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="8508e-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="8508e-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="8508e-285">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-285">Format</span></span>

<span data-ttu-id="8508e-286">後面接著任何空格或分隔符號的六個或七位數字的兩個字母</span><span class="sxs-lookup"><span data-stu-id="8508e-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-287">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-287">Pattern</span></span>

<span data-ttu-id="8508e-288">後面接著六個或七位數字的兩個字母</span><span class="sxs-lookup"><span data-stu-id="8508e-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8508e-289">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-289">Checksum</span></span>

<span data-ttu-id="8508e-290">否</span><span class="sxs-lookup"><span data-stu-id="8508e-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-291">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-291">Definition</span></span>

<span data-ttu-id="8508e-292">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-293">規則運算式`Regex_hungary_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-294">從關鍵字`Keywords_hungary_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-295">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-295">Keywords</span></span>

<span data-ttu-id="8508e-296">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-296"></span></span>
|<span data-ttu-id="8508e-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-298">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-298">passport number</span></span>  <br/> <span data-ttu-id="8508e-299">匈牙利文護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="8508e-300">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-300">passport no</span></span>  <br/> <span data-ttu-id="8508e-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="8508e-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="8508e-302">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="8508e-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="8508e-303">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-303">Format</span></span>

<span data-ttu-id="8508e-304">兩個字母或數字後面接著任何空格或分隔符號七位數字</span><span class="sxs-lookup"><span data-stu-id="8508e-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-305">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-305">Pattern</span></span>

<span data-ttu-id="8508e-306">兩個字母或數字後面七位數字：</span><span class="sxs-lookup"><span data-stu-id="8508e-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8508e-307">兩個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="8508e-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8508e-308">七位數</span><span class="sxs-lookup"><span data-stu-id="8508e-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8508e-309">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-309">Checksum</span></span>

<span data-ttu-id="8508e-310">否</span><span class="sxs-lookup"><span data-stu-id="8508e-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-311">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-311">Definition</span></span>

<span data-ttu-id="8508e-312">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-313">規則運算式`Regex_ireland_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-314">從關鍵字`Keywords_ireland_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-315">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-315">Keywords</span></span>

<span data-ttu-id="8508e-316">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-316"></span></span>
|<span data-ttu-id="8508e-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-318">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-318">passport number</span></span>  <br/> <span data-ttu-id="8508e-319">愛爾蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-319">irish passport number</span></span>  <br/> <span data-ttu-id="8508e-320">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-320">passport no</span></span>  <br/> <span data-ttu-id="8508e-321">pas</span><span class="sxs-lookup"><span data-stu-id="8508e-321">pas</span></span>  <br/> <span data-ttu-id="8508e-322">passport</span><span class="sxs-lookup"><span data-stu-id="8508e-322">passport</span></span>  <br/> <span data-ttu-id="8508e-323">passeport</span><span class="sxs-lookup"><span data-stu-id="8508e-323">passeport</span></span>  <br/> <span data-ttu-id="8508e-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="8508e-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="8508e-325">義大利</span><span class="sxs-lookup"><span data-stu-id="8508e-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="8508e-326">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-326">Format</span></span>

<span data-ttu-id="8508e-327">兩個字母或數字後面接著任何空格或分隔符號七位數字</span><span class="sxs-lookup"><span data-stu-id="8508e-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-328">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-328">Pattern</span></span>

<span data-ttu-id="8508e-329">兩個字母或數字後面七位數字：</span><span class="sxs-lookup"><span data-stu-id="8508e-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8508e-330">兩個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="8508e-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8508e-331">七位數</span><span class="sxs-lookup"><span data-stu-id="8508e-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8508e-332">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-332">Checksum</span></span>

<span data-ttu-id="8508e-333">不適用</span><span class="sxs-lookup"><span data-stu-id="8508e-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-334">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-334">Definition</span></span>

<span data-ttu-id="8508e-335">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-336">規則運算式`Regex_italy_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-337">從關鍵字`Keywords_italy_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-338">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-338">Keywords</span></span>

<span data-ttu-id="8508e-339">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-339"></span></span>
|<span data-ttu-id="8508e-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-341">義大利護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-341">italian passport number</span></span>  <br/> <span data-ttu-id="8508e-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="8508e-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="8508e-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="8508e-343">passaporto</span></span>  <br/> <span data-ttu-id="8508e-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="8508e-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="8508e-345">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-345">passport number</span></span>  <br/> <span data-ttu-id="8508e-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="8508e-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="8508e-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="8508e-347">passaporto numero</span></span>  <br/> <span data-ttu-id="8508e-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="8508e-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="8508e-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="8508e-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="8508e-350">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="8508e-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="8508e-351">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-351">Format</span></span>

<span data-ttu-id="8508e-352">兩個字母或數字後面接著任何空格或分隔符號七位數字</span><span class="sxs-lookup"><span data-stu-id="8508e-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-353">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-353">Pattern</span></span>

<span data-ttu-id="8508e-354">兩個字母或數字後面七位數字：</span><span class="sxs-lookup"><span data-stu-id="8508e-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8508e-355">兩個數字或字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="8508e-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8508e-356">七位數</span><span class="sxs-lookup"><span data-stu-id="8508e-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8508e-357">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-357">Checksum</span></span>

<span data-ttu-id="8508e-358">否</span><span class="sxs-lookup"><span data-stu-id="8508e-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-359">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-359">Definition</span></span>

<span data-ttu-id="8508e-360">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-361">規則運算式`Regex_latvia_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-362">從關鍵字`Keywords_latvia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-363">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-363">Keywords</span></span>

<span data-ttu-id="8508e-364">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-364"></span></span>
|<span data-ttu-id="8508e-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-366">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-366">passport number</span></span>  <br/> <span data-ttu-id="8508e-367">拉脫維亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-367">latvian passport number</span></span>  <br/> <span data-ttu-id="8508e-368">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-368">passport no</span></span>  <br/> <span data-ttu-id="8508e-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="8508e-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="8508e-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="8508e-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="8508e-371">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-371">Format</span></span>

<span data-ttu-id="8508e-372">八個任何空格或分隔符號的字母或數字</span><span class="sxs-lookup"><span data-stu-id="8508e-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-373">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-373">Pattern</span></span>

<span data-ttu-id="8508e-374">八個字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="8508e-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8508e-375">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-375">Checksum</span></span>

<span data-ttu-id="8508e-376">不適用</span><span class="sxs-lookup"><span data-stu-id="8508e-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-377">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-377">Definition</span></span>

<span data-ttu-id="8508e-378">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-379">規則運算式`Regex_lithuania_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-380">從關鍵字`Keywords_lithuania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-381">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-381">Keywords</span></span>

<span data-ttu-id="8508e-382">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-382"></span></span>
|<span data-ttu-id="8508e-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-384">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-384">passport number</span></span>  <br/> <span data-ttu-id="8508e-385">lithunian 護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="8508e-386">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-386">passport no</span></span>  <br/> <span data-ttu-id="8508e-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="8508e-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="8508e-388">盧森堡</span><span class="sxs-lookup"><span data-stu-id="8508e-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="8508e-389">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-389">Format</span></span>

<span data-ttu-id="8508e-390">八個任何空格或分隔符號的字母或數字</span><span class="sxs-lookup"><span data-stu-id="8508e-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-391">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-391">Pattern</span></span>

<span data-ttu-id="8508e-392">八個字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="8508e-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8508e-393">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-393">Checksum</span></span>

<span data-ttu-id="8508e-394">否</span><span class="sxs-lookup"><span data-stu-id="8508e-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-395">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-395">Definition</span></span>

<span data-ttu-id="8508e-396">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-397">規則運算式`Regex_nation_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-398">從關鍵字`Keywords_nation_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-399">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-399">Keywords</span></span>

<span data-ttu-id="8508e-400">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-400"></span></span>
|<span data-ttu-id="8508e-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-402">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-402">passport number</span></span>  <br/> <span data-ttu-id="8508e-403">拉脫維亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-403">latvian passport number</span></span>  <br/> <span data-ttu-id="8508e-404">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-404">passport no</span></span>  <br/> <span data-ttu-id="8508e-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="8508e-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="8508e-406">馬爾他</span><span class="sxs-lookup"><span data-stu-id="8508e-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="8508e-407">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-407">Format</span></span>

<span data-ttu-id="8508e-408">不含空格或分隔符號七位數字</span><span class="sxs-lookup"><span data-stu-id="8508e-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-409">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-409">Pattern</span></span>

 <span data-ttu-id="8508e-410">七位數</span><span class="sxs-lookup"><span data-stu-id="8508e-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8508e-411">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-411">Checksum</span></span>

<span data-ttu-id="8508e-412">否</span><span class="sxs-lookup"><span data-stu-id="8508e-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-413">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-413">Definition</span></span>

<span data-ttu-id="8508e-414">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-415">規則運算式`Regex_malta_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-416">從關鍵字`Keywords_malta_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-417">Keywords</span></span>

<span data-ttu-id="8508e-418">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-418"></span></span>
|<span data-ttu-id="8508e-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-420">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-420">passport number</span></span>  <br/> <span data-ttu-id="8508e-421">馬爾他護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-421">maltese passport number</span></span>  <br/> <span data-ttu-id="8508e-422">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-422">passport no</span></span>  <br/> <span data-ttu-id="8508e-423">numru tal passaport</span><span class="sxs-lookup"><span data-stu-id="8508e-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="8508e-424">荷蘭</span><span class="sxs-lookup"><span data-stu-id="8508e-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="8508e-425">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-425">Format</span></span>

<span data-ttu-id="8508e-426">九個字母或數字與任何空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="8508e-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-427">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-427">Pattern</span></span>

<span data-ttu-id="8508e-428">九個字母或數字</span><span class="sxs-lookup"><span data-stu-id="8508e-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8508e-429">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-429">Checksum</span></span>

<span data-ttu-id="8508e-430">不適用</span><span class="sxs-lookup"><span data-stu-id="8508e-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-431">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-431">Definition</span></span>

<span data-ttu-id="8508e-432">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-433">規則運算式`Regex_netherlands_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-434">從關鍵字`Keywords_netherlands_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-435">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-435">Keywords</span></span>

<span data-ttu-id="8508e-436">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-436"></span></span>
|<span data-ttu-id="8508e-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-438">荷蘭文護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-438">dutch passport number</span></span>  <br/> <span data-ttu-id="8508e-439">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-439">passport number</span></span>  <br/> <span data-ttu-id="8508e-440">荷蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="8508e-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="8508e-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="8508e-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="8508e-442">paspoort</span></span>  <br/> <span data-ttu-id="8508e-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8508e-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="8508e-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8508e-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="8508e-445">波蘭</span><span class="sxs-lookup"><span data-stu-id="8508e-445">Poland</span></span>

<span data-ttu-id="8508e-446">如需詳細資訊，請參閱節"波蘭護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="8508e-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="8508e-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="8508e-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="8508e-448">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-448">Format</span></span>

<span data-ttu-id="8508e-449">一個字母後面接著任何空格或分隔符號 6 位數</span><span class="sxs-lookup"><span data-stu-id="8508e-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-450">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-450">Pattern</span></span>

<span data-ttu-id="8508e-451">一個字母後面接著 6 位數：</span><span class="sxs-lookup"><span data-stu-id="8508e-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="8508e-452">一個字母 (不區分大小寫)</span><span class="sxs-lookup"><span data-stu-id="8508e-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="8508e-453">六位數</span><span class="sxs-lookup"><span data-stu-id="8508e-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8508e-454">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-454">Checksum</span></span>

<span data-ttu-id="8508e-455">否</span><span class="sxs-lookup"><span data-stu-id="8508e-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-456">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-456">Definition</span></span>

<span data-ttu-id="8508e-457">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-458">規則運算式`Regex_portugal_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-459">從關鍵字`Keywords_portugal_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-460">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-460">Keywords</span></span>

<span data-ttu-id="8508e-461">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-461"></span></span>
|<span data-ttu-id="8508e-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-463">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-463">passport number</span></span>  <br/> <span data-ttu-id="8508e-464">葡萄牙文護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="8508e-465">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-465">passport no</span></span>  <br/> <span data-ttu-id="8508e-466">número 不要 passaporte</span><span class="sxs-lookup"><span data-stu-id="8508e-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="8508e-467">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="8508e-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="8508e-468">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-468">Format</span></span>

<span data-ttu-id="8508e-469">不含空格和分隔字元的八個或九個位數</span><span class="sxs-lookup"><span data-stu-id="8508e-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-470">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-470">Pattern</span></span>

<span data-ttu-id="8508e-471">八個或 9 的數字</span><span class="sxs-lookup"><span data-stu-id="8508e-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8508e-472">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-472">Checksum</span></span>

<span data-ttu-id="8508e-473">否</span><span class="sxs-lookup"><span data-stu-id="8508e-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-474">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-474">Definition</span></span>

<span data-ttu-id="8508e-475">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-476">規則運算式`Regex_romania_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-477">從關鍵字`Keywords_romania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-478">Keywords</span></span>

<span data-ttu-id="8508e-479">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-479"></span></span>
|<span data-ttu-id="8508e-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-481">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-481">passport number</span></span>  <br/> <span data-ttu-id="8508e-482">羅馬尼亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-482">romanian passport number</span></span>  <br/> <span data-ttu-id="8508e-483">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-483">passport no</span></span>  <br/> <span data-ttu-id="8508e-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="8508e-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="8508e-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="8508e-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="8508e-486">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-486">Format</span></span>

<span data-ttu-id="8508e-487">一個數字或字母後面接著任何空格或分隔符號七位數字</span><span class="sxs-lookup"><span data-stu-id="8508e-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-488">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-488">Pattern</span></span>

<span data-ttu-id="8508e-489">一個數字或字母後面七位數字 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="8508e-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8508e-490">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-490">Checksum</span></span>

<span data-ttu-id="8508e-491">否</span><span class="sxs-lookup"><span data-stu-id="8508e-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-492">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-492">Definition</span></span>

<span data-ttu-id="8508e-493">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-494">規則運算式`Regex_slovakia_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-495">從關鍵字`Keywords_slovakia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-496">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-496">Keywords</span></span>

<span data-ttu-id="8508e-497">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-497"></span></span>
|<span data-ttu-id="8508e-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-499">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-499">passport number</span></span>  <br/> <span data-ttu-id="8508e-500">斯洛伐克護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="8508e-501">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-501">passport no</span></span>  <br/> <span data-ttu-id="8508e-502">Číslo pasu</span><span class="sxs-lookup"><span data-stu-id="8508e-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="8508e-503">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="8508e-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="8508e-504">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-504">Format</span></span>

<span data-ttu-id="8508e-505">後面接著任何空格或分隔符號七位數字的兩個字母</span><span class="sxs-lookup"><span data-stu-id="8508e-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-506">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-506">Pattern</span></span>

<span data-ttu-id="8508e-507">後面七位數字的兩個字母：</span><span class="sxs-lookup"><span data-stu-id="8508e-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="8508e-508">字母"P"</span><span class="sxs-lookup"><span data-stu-id="8508e-508">The letter "P"</span></span>
    
- <span data-ttu-id="8508e-509">一個大寫字母</span><span class="sxs-lookup"><span data-stu-id="8508e-509">One uppercase letter</span></span>
    
- <span data-ttu-id="8508e-510">七位數</span><span class="sxs-lookup"><span data-stu-id="8508e-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8508e-511">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-511">Checksum</span></span>

<span data-ttu-id="8508e-512">否</span><span class="sxs-lookup"><span data-stu-id="8508e-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-513">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-513">Definition</span></span>

<span data-ttu-id="8508e-514">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-515">規則運算式`Regex_slovenia_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-516">從關鍵字`Keywords_slovenia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-517">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-517">Keywords</span></span>

<span data-ttu-id="8508e-518">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-518"></span></span>
|<span data-ttu-id="8508e-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-520">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-520">passport number</span></span>  <br/> <span data-ttu-id="8508e-521">斯洛維尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="8508e-522">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-522">passport no</span></span>  <br/> <span data-ttu-id="8508e-523">Številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="8508e-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="8508e-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="8508e-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="8508e-525">格式</span><span class="sxs-lookup"><span data-stu-id="8508e-525">Format</span></span>

<span data-ttu-id="8508e-526">字母及號碼與任何空格或分隔符號八個或九個字元組合</span><span class="sxs-lookup"><span data-stu-id="8508e-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8508e-527">模式</span><span class="sxs-lookup"><span data-stu-id="8508e-527">Pattern</span></span>

<span data-ttu-id="8508e-528">字母及數字 8 或九個字元組合：</span><span class="sxs-lookup"><span data-stu-id="8508e-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="8508e-529">兩個字母或數字</span><span class="sxs-lookup"><span data-stu-id="8508e-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="8508e-530">一個數字或字母 （選用）</span><span class="sxs-lookup"><span data-stu-id="8508e-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="8508e-531">六位數</span><span class="sxs-lookup"><span data-stu-id="8508e-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8508e-532">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="8508e-532">Checksum</span></span>

<span data-ttu-id="8508e-533">不適用</span><span class="sxs-lookup"><span data-stu-id="8508e-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8508e-534">定義</span><span class="sxs-lookup"><span data-stu-id="8508e-534">Definition</span></span>

<span data-ttu-id="8508e-535">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="8508e-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8508e-536">規則運算式`Regex_spain_eu_passport_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="8508e-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8508e-537">從關鍵字`Keywords_spain_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8508e-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8508e-538">關鍵字</span><span class="sxs-lookup"><span data-stu-id="8508e-538">Keywords</span></span>

<span data-ttu-id="8508e-539">| |</span><span class="sxs-lookup"><span data-stu-id="8508e-539"></span></span>
|<span data-ttu-id="8508e-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8508e-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8508e-541">passport</span><span class="sxs-lookup"><span data-stu-id="8508e-541">passport</span></span>  <br/> <span data-ttu-id="8508e-542">西班牙 passport</span><span class="sxs-lookup"><span data-stu-id="8508e-542">spain passport</span></span>  <br/> <span data-ttu-id="8508e-543">passport 活頁簿</span><span class="sxs-lookup"><span data-stu-id="8508e-543">passport book</span></span>  <br/> <span data-ttu-id="8508e-544">護照號碼</span><span class="sxs-lookup"><span data-stu-id="8508e-544">passport number</span></span>  <br/> <span data-ttu-id="8508e-545">passport 無</span><span class="sxs-lookup"><span data-stu-id="8508e-545">passport no</span></span>  <br/> <span data-ttu-id="8508e-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="8508e-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="8508e-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="8508e-547">número pasaporte</span></span>  <br/> <span data-ttu-id="8508e-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="8508e-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="8508e-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="8508e-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="8508e-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="8508e-550">Sweden</span></span>

<span data-ttu-id="8508e-551">如需詳細資訊，請參閱節"瑞典護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="8508e-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="8508e-552">英國</span><span class="sxs-lookup"><span data-stu-id="8508e-552">UK</span></span>

<span data-ttu-id="8508e-p103">如需詳細資訊，請參閱節"US/英國護照號碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="8508e-p103">For details, see the section "U.S. / U.K. Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8508e-555">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8508e-555">See also</span></span>

[<span data-ttu-id="8508e-556">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="8508e-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

