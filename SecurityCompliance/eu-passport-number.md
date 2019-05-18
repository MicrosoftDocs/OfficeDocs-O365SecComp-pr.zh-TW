---
title: 歐盟護照號碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟護照號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: fa3be04dec0f71a2568e046abd6b0af3e20181c5
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152965"
---
# <a name="eu-passport-number"></a><span data-ttu-id="835a8-104">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-104">EU Passport Number</span></span>

<span data-ttu-id="835a8-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟護照號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="835a8-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="835a8-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="835a8-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="835a8-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="835a8-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="835a8-108">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-108">Format</span></span>

<span data-ttu-id="835a8-109">一個字母後尾隨一個選用空格和七位數</span><span class="sxs-lookup"><span data-stu-id="835a8-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-110">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-110">Pattern</span></span>

<span data-ttu-id="835a8-111">一個字母、 七位數和一個空格的組合：</span><span class="sxs-lookup"><span data-stu-id="835a8-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="835a8-112">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="835a8-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="835a8-113">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="835a8-113">One space (optional)</span></span>
    
- <span data-ttu-id="835a8-114">七位數</span><span class="sxs-lookup"><span data-stu-id="835a8-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="835a8-115">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-115">Checksum</span></span>

<span data-ttu-id="835a8-116">不適用</span><span class="sxs-lookup"><span data-stu-id="835a8-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-117">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-117">Definition</span></span>

<span data-ttu-id="835a8-118">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-119">規則運算式`Regex_austria_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-120">從關鍵字`Keywords_austria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-121">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-121">Keywords</span></span>

<span data-ttu-id="835a8-122">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-122"></span></span>
|<span data-ttu-id="835a8-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-124">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-124">passport number</span></span>  <br/> <span data-ttu-id="835a8-125">奧地利護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-125">austrian passport number</span></span>  <br/> <span data-ttu-id="835a8-126">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-126">passport no</span></span>  <br/> <span data-ttu-id="835a8-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="835a8-127">reisepass</span></span>  <br/> <span data-ttu-id="835a8-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="835a8-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="835a8-129">比利時</span><span class="sxs-lookup"><span data-stu-id="835a8-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="835a8-130">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-130">Format</span></span>

<span data-ttu-id="835a8-131">兩個字母後尾隨六位數，代表不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="835a8-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-132">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-132">Pattern</span></span>

<span data-ttu-id="835a8-133">兩個字母後尾隨六位數和</span><span class="sxs-lookup"><span data-stu-id="835a8-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="835a8-134">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-134">Checksum</span></span>

<span data-ttu-id="835a8-135">不適用</span><span class="sxs-lookup"><span data-stu-id="835a8-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-136">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-136">Definition</span></span>

<span data-ttu-id="835a8-137">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-138">規則運算式`Regex_belgium_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-139">從關鍵字`Keywords_belgium_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-140">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-140">Keywords</span></span>

<span data-ttu-id="835a8-141">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-141"></span></span>
|<span data-ttu-id="835a8-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-143">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-143">passport number</span></span>  <br/> <span data-ttu-id="835a8-144">比利時護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-144">belgian passport number</span></span>  <br/> <span data-ttu-id="835a8-145">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-145">passport no</span></span>  <br/> <span data-ttu-id="835a8-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="835a8-146">paspoort</span></span>  <br/> <span data-ttu-id="835a8-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="835a8-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="835a8-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="835a8-148">reisepass kein</span></span>  <br/> <span data-ttu-id="835a8-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="835a8-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="835a8-150">保加利亞</span><span class="sxs-lookup"><span data-stu-id="835a8-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="835a8-151">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-151">Format</span></span>

<span data-ttu-id="835a8-152">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="835a8-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-153">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-153">Pattern</span></span>

 <span data-ttu-id="835a8-154">九位數</span><span class="sxs-lookup"><span data-stu-id="835a8-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="835a8-155">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-155">Checksum</span></span>

<span data-ttu-id="835a8-156">否</span><span class="sxs-lookup"><span data-stu-id="835a8-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-157">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-157">Definition</span></span>

<span data-ttu-id="835a8-158">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-159">規則運算式`Regex_bulgaria_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-160">從關鍵字`Keywords_bulgaria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-161">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-161">Keywords</span></span>

<span data-ttu-id="835a8-162">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-162"></span></span>
|<span data-ttu-id="835a8-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-164">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-164">passport number</span></span>  <br/> <span data-ttu-id="835a8-165">保加利亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="835a8-166">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-166">passport no</span></span>  <br/> <span data-ttu-id="835a8-167">НОМЕР НА ПАСПОРТА</span><span class="sxs-lookup"><span data-stu-id="835a8-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="835a8-168">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="835a8-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="835a8-169">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-169">Format</span></span>

<span data-ttu-id="835a8-170">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="835a8-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-171">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-171">Pattern</span></span>

 <span data-ttu-id="835a8-172">九位數</span><span class="sxs-lookup"><span data-stu-id="835a8-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="835a8-173">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-173">Checksum</span></span>

<span data-ttu-id="835a8-174">否</span><span class="sxs-lookup"><span data-stu-id="835a8-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-175">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-175">Definition</span></span>

<span data-ttu-id="835a8-176">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-177">規則運算式`Regex_croatia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-178">從關鍵字`Keywords_croatia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-179">Keywords</span></span>

<span data-ttu-id="835a8-180">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-180"></span></span>
|<span data-ttu-id="835a8-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-182">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-182">passport number</span></span>  <br/> <span data-ttu-id="835a8-183">克羅埃西亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-183">croatian passport number</span></span>  <br/> <span data-ttu-id="835a8-184">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-184">passport no</span></span>  <br/> <span data-ttu-id="835a8-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="835a8-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="835a8-186">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="835a8-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="835a8-187">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-187">Format</span></span>

<span data-ttu-id="835a8-188">一個字母後尾隨不含空格或分隔符號 6-8 位數</span><span class="sxs-lookup"><span data-stu-id="835a8-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-189">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-189">Pattern</span></span>

<span data-ttu-id="835a8-190">一個字母後尾隨六至八位數</span><span class="sxs-lookup"><span data-stu-id="835a8-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="835a8-191">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-191">Checksum</span></span>

<span data-ttu-id="835a8-192">否</span><span class="sxs-lookup"><span data-stu-id="835a8-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-193">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-193">Definition</span></span>

<span data-ttu-id="835a8-194">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-195">規則運算式`Regex_cyprus_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-196">從關鍵字`Keywords_cyprus_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-197">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-197">Keywords</span></span>

<span data-ttu-id="835a8-198">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-198"></span></span>
|<span data-ttu-id="835a8-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-200">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-200">passport number</span></span>  <br/> <span data-ttu-id="835a8-201">賽普勒斯護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="835a8-202">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-202">passport no</span></span>  <br/> <span data-ttu-id="835a8-203">ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ</span><span class="sxs-lookup"><span data-stu-id="835a8-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="835a8-204">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="835a8-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="835a8-205">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-205">Format</span></span>

<span data-ttu-id="835a8-206">不含空格或分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="835a8-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-207">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-207">Pattern</span></span>

<span data-ttu-id="835a8-208">不含空格或分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="835a8-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="835a8-209">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-209">Checksum</span></span>

<span data-ttu-id="835a8-210">否</span><span class="sxs-lookup"><span data-stu-id="835a8-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-211">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-211">Definition</span></span>

<span data-ttu-id="835a8-212">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-213">規則運算式`Regex_czech_republic_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-214">從關鍵字`Keywords_czech_republic_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-215">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-215">Keywords</span></span>

<span data-ttu-id="835a8-216">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-216"></span></span>
|<span data-ttu-id="835a8-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-218">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-218">passport number</span></span>  <br/> <span data-ttu-id="835a8-219">捷克護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-219">czech passport number</span></span>  <br/> <span data-ttu-id="835a8-220">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-220">passport no</span></span>  <br/> <span data-ttu-id="835a8-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="835a8-221">cestovní pas</span></span>  <br/> <span data-ttu-id="835a8-222">pas</span><span class="sxs-lookup"><span data-stu-id="835a8-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="835a8-223">丹麥</span><span class="sxs-lookup"><span data-stu-id="835a8-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="835a8-224">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-224">Format</span></span>

<span data-ttu-id="835a8-225">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="835a8-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-226">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-226">Pattern</span></span>

 <span data-ttu-id="835a8-227">九位數</span><span class="sxs-lookup"><span data-stu-id="835a8-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="835a8-228">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-228">Checksum</span></span>

<span data-ttu-id="835a8-229">否</span><span class="sxs-lookup"><span data-stu-id="835a8-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-230">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-230">Definition</span></span>

<span data-ttu-id="835a8-231">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-232">規則運算式`Regex_denmark_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-233">從關鍵字`Keywords_denmark_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-234">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-234">Keywords</span></span>

<span data-ttu-id="835a8-235">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-235"></span></span>
|<span data-ttu-id="835a8-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-237">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-237">passport number</span></span>  <br/> <span data-ttu-id="835a8-238">丹麥文護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-238">danish passport number</span></span>  <br/> <span data-ttu-id="835a8-239">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-239">passport no</span></span>  <br/> <span data-ttu-id="835a8-240">pas</span><span class="sxs-lookup"><span data-stu-id="835a8-240">pas</span></span>  <br/> <span data-ttu-id="835a8-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="835a8-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="835a8-242">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="835a8-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="835a8-243">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-243">Format</span></span>

<span data-ttu-id="835a8-244">一個字母後尾隨七位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="835a8-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-245">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-245">Pattern</span></span>

<span data-ttu-id="835a8-246">一個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="835a8-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="835a8-247">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-247">Checksum</span></span>

<span data-ttu-id="835a8-248">否</span><span class="sxs-lookup"><span data-stu-id="835a8-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-249">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-249">Definition</span></span>

<span data-ttu-id="835a8-250">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-251">規則運算式`Regex_estonia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-252">從關鍵字`Keywords_estonia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-253">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-253">Keywords</span></span>

<span data-ttu-id="835a8-254">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-254"></span></span>
|<span data-ttu-id="835a8-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-256">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-256">passport number</span></span>  <br/> <span data-ttu-id="835a8-257">愛沙尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-257">estonian passport number</span></span>  <br/> <span data-ttu-id="835a8-258">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-258">passport no</span></span>  <br/> <span data-ttu-id="835a8-259">eesti kodaniku 複雜</span><span class="sxs-lookup"><span data-stu-id="835a8-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="835a8-260">芬蘭</span><span class="sxs-lookup"><span data-stu-id="835a8-260">Finland</span></span>

<span data-ttu-id="835a8-261">如需詳細資訊，請參閱 「 芬蘭護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="835a8-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="835a8-262">法國</span><span class="sxs-lookup"><span data-stu-id="835a8-262">France</span></span>

<span data-ttu-id="835a8-263">如需詳細資訊，請參閱 「 法國護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="835a8-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="835a8-264">德國</span><span class="sxs-lookup"><span data-stu-id="835a8-264">Germany</span></span>

<span data-ttu-id="835a8-265">如需詳細資訊，請參閱 「 德國護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="835a8-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="835a8-266">希臘</span><span class="sxs-lookup"><span data-stu-id="835a8-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="835a8-267">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-267">Format</span></span>

<span data-ttu-id="835a8-268">兩個字母後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="835a8-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-269">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-269">Pattern</span></span>

<span data-ttu-id="835a8-270">兩個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="835a8-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="835a8-271">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-271">Checksum</span></span>

<span data-ttu-id="835a8-272">否</span><span class="sxs-lookup"><span data-stu-id="835a8-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-273">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-273">Definition</span></span>

<span data-ttu-id="835a8-274">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-275">規則運算式`Regex_greece_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-276">從關鍵字`Keywords_greece_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-277">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-277">Keywords</span></span>

<span data-ttu-id="835a8-278">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-278"></span></span>
|<span data-ttu-id="835a8-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-280">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-280">passport number</span></span>  <br/> <span data-ttu-id="835a8-281">希臘文護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-281">greek passport number</span></span>  <br/> <span data-ttu-id="835a8-282">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-282">passport no</span></span>  <br/> <span data-ttu-id="835a8-283">ΔΙΑΒΑΤΗΡΙΟ</span><span class="sxs-lookup"><span data-stu-id="835a8-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="835a8-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="835a8-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="835a8-285">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-285">Format</span></span>

<span data-ttu-id="835a8-286">兩個字母後尾隨六個或七位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="835a8-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-287">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-287">Pattern</span></span>

<span data-ttu-id="835a8-288">兩個字母後尾隨六個或七位數</span><span class="sxs-lookup"><span data-stu-id="835a8-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="835a8-289">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-289">Checksum</span></span>

<span data-ttu-id="835a8-290">否</span><span class="sxs-lookup"><span data-stu-id="835a8-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-291">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-291">Definition</span></span>

<span data-ttu-id="835a8-292">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-293">規則運算式`Regex_hungary_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-294">從關鍵字`Keywords_hungary_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-295">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-295">Keywords</span></span>

<span data-ttu-id="835a8-296">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-296"></span></span>
|<span data-ttu-id="835a8-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-298">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-298">passport number</span></span>  <br/> <span data-ttu-id="835a8-299">匈牙利文護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="835a8-300">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-300">passport no</span></span>  <br/> <span data-ttu-id="835a8-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="835a8-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="835a8-302">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="835a8-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="835a8-303">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-303">Format</span></span>

<span data-ttu-id="835a8-304">兩個字母或位數後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="835a8-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-305">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-305">Pattern</span></span>

<span data-ttu-id="835a8-306">兩個字母或位數後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="835a8-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="835a8-307">兩個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="835a8-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="835a8-308">七位數</span><span class="sxs-lookup"><span data-stu-id="835a8-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="835a8-309">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-309">Checksum</span></span>

<span data-ttu-id="835a8-310">否</span><span class="sxs-lookup"><span data-stu-id="835a8-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-311">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-311">Definition</span></span>

<span data-ttu-id="835a8-312">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-313">規則運算式`Regex_ireland_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-314">從關鍵字`Keywords_ireland_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-315">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-315">Keywords</span></span>

<span data-ttu-id="835a8-316">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-316"></span></span>
|<span data-ttu-id="835a8-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-318">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-318">passport number</span></span>  <br/> <span data-ttu-id="835a8-319">愛爾蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-319">irish passport number</span></span>  <br/> <span data-ttu-id="835a8-320">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-320">passport no</span></span>  <br/> <span data-ttu-id="835a8-321">pas</span><span class="sxs-lookup"><span data-stu-id="835a8-321">pas</span></span>  <br/> <span data-ttu-id="835a8-322">passport</span><span class="sxs-lookup"><span data-stu-id="835a8-322">passport</span></span>  <br/> <span data-ttu-id="835a8-323">passeport</span><span class="sxs-lookup"><span data-stu-id="835a8-323">passeport</span></span>  <br/> <span data-ttu-id="835a8-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="835a8-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="835a8-325">義大利</span><span class="sxs-lookup"><span data-stu-id="835a8-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="835a8-326">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-326">Format</span></span>

<span data-ttu-id="835a8-327">兩個字母或位數後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="835a8-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-328">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-328">Pattern</span></span>

<span data-ttu-id="835a8-329">兩個字母或位數後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="835a8-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="835a8-330">兩個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="835a8-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="835a8-331">七位數</span><span class="sxs-lookup"><span data-stu-id="835a8-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="835a8-332">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-332">Checksum</span></span>

<span data-ttu-id="835a8-333">不適用</span><span class="sxs-lookup"><span data-stu-id="835a8-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-334">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-334">Definition</span></span>

<span data-ttu-id="835a8-335">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-336">規則運算式`Regex_italy_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-337">從關鍵字`Keywords_italy_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-338">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-338">Keywords</span></span>

<span data-ttu-id="835a8-339">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-339"></span></span>
|<span data-ttu-id="835a8-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-341">義大利文護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-341">italian passport number</span></span>  <br/> <span data-ttu-id="835a8-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="835a8-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="835a8-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="835a8-343">passaporto</span></span>  <br/> <span data-ttu-id="835a8-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="835a8-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="835a8-345">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-345">passport number</span></span>  <br/> <span data-ttu-id="835a8-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="835a8-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="835a8-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="835a8-347">passaporto numero</span></span>  <br/> <span data-ttu-id="835a8-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="835a8-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="835a8-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="835a8-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="835a8-350">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="835a8-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="835a8-351">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-351">Format</span></span>

<span data-ttu-id="835a8-352">兩個字母或位數後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="835a8-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-353">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-353">Pattern</span></span>

<span data-ttu-id="835a8-354">兩個字母或位數後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="835a8-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="835a8-355">兩個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="835a8-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="835a8-356">七位數</span><span class="sxs-lookup"><span data-stu-id="835a8-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="835a8-357">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-357">Checksum</span></span>

<span data-ttu-id="835a8-358">否</span><span class="sxs-lookup"><span data-stu-id="835a8-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-359">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-359">Definition</span></span>

<span data-ttu-id="835a8-360">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-361">規則運算式`Regex_latvia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-362">從關鍵字`Keywords_latvia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-363">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-363">Keywords</span></span>

<span data-ttu-id="835a8-364">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-364"></span></span>
|<span data-ttu-id="835a8-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-366">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-366">passport number</span></span>  <br/> <span data-ttu-id="835a8-367">拉脫維亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-367">latvian passport number</span></span>  <br/> <span data-ttu-id="835a8-368">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-368">passport no</span></span>  <br/> <span data-ttu-id="835a8-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="835a8-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="835a8-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="835a8-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="835a8-371">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-371">Format</span></span>

<span data-ttu-id="835a8-372">八個個數字或字母不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="835a8-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-373">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-373">Pattern</span></span>

<span data-ttu-id="835a8-374">八個個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="835a8-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="835a8-375">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-375">Checksum</span></span>

<span data-ttu-id="835a8-376">不適用</span><span class="sxs-lookup"><span data-stu-id="835a8-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-377">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-377">Definition</span></span>

<span data-ttu-id="835a8-378">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-379">規則運算式`Regex_lithuania_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-380">從關鍵字`Keywords_lithuania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-381">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-381">Keywords</span></span>

<span data-ttu-id="835a8-382">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-382"></span></span>
|<span data-ttu-id="835a8-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-384">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-384">passport number</span></span>  <br/> <span data-ttu-id="835a8-385">lithunian 護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="835a8-386">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-386">passport no</span></span>  <br/> <span data-ttu-id="835a8-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="835a8-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="835a8-388">盧森堡</span><span class="sxs-lookup"><span data-stu-id="835a8-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="835a8-389">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-389">Format</span></span>

<span data-ttu-id="835a8-390">八個個數字或字母不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="835a8-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-391">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-391">Pattern</span></span>

<span data-ttu-id="835a8-392">八個個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="835a8-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="835a8-393">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-393">Checksum</span></span>

<span data-ttu-id="835a8-394">否</span><span class="sxs-lookup"><span data-stu-id="835a8-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-395">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-395">Definition</span></span>

<span data-ttu-id="835a8-396">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-397">規則運算式`Regex_nation_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-398">從關鍵字`Keywords_nation_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-399">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-399">Keywords</span></span>

<span data-ttu-id="835a8-400">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-400"></span></span>
|<span data-ttu-id="835a8-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-402">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-402">passport number</span></span>  <br/> <span data-ttu-id="835a8-403">拉脫維亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-403">latvian passport number</span></span>  <br/> <span data-ttu-id="835a8-404">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-404">passport no</span></span>  <br/> <span data-ttu-id="835a8-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="835a8-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="835a8-406">馬爾他</span><span class="sxs-lookup"><span data-stu-id="835a8-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="835a8-407">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-407">Format</span></span>

<span data-ttu-id="835a8-408">不含空格或分隔符號七位數</span><span class="sxs-lookup"><span data-stu-id="835a8-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-409">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-409">Pattern</span></span>

 <span data-ttu-id="835a8-410">七位數</span><span class="sxs-lookup"><span data-stu-id="835a8-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="835a8-411">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-411">Checksum</span></span>

<span data-ttu-id="835a8-412">否</span><span class="sxs-lookup"><span data-stu-id="835a8-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-413">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-413">Definition</span></span>

<span data-ttu-id="835a8-414">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-415">規則運算式`Regex_malta_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-416">從關鍵字`Keywords_malta_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-417">Keywords</span></span>

<span data-ttu-id="835a8-418">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-418"></span></span>
|<span data-ttu-id="835a8-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-420">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-420">passport number</span></span>  <br/> <span data-ttu-id="835a8-421">馬爾他護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-421">maltese passport number</span></span>  <br/> <span data-ttu-id="835a8-422">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-422">passport no</span></span>  <br/> <span data-ttu-id="835a8-423">numru tal passaport</span><span class="sxs-lookup"><span data-stu-id="835a8-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="835a8-424">荷蘭</span><span class="sxs-lookup"><span data-stu-id="835a8-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="835a8-425">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-425">Format</span></span>

<span data-ttu-id="835a8-426">九個字母或不含空格或分隔符號的數字</span><span class="sxs-lookup"><span data-stu-id="835a8-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-427">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-427">Pattern</span></span>

<span data-ttu-id="835a8-428">九個字母或四位數</span><span class="sxs-lookup"><span data-stu-id="835a8-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="835a8-429">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-429">Checksum</span></span>

<span data-ttu-id="835a8-430">不適用</span><span class="sxs-lookup"><span data-stu-id="835a8-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-431">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-431">Definition</span></span>

<span data-ttu-id="835a8-432">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-433">規則運算式`Regex_netherlands_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-434">從關鍵字`Keywords_netherlands_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-435">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-435">Keywords</span></span>

<span data-ttu-id="835a8-436">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-436"></span></span>
|<span data-ttu-id="835a8-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-438">荷蘭文護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-438">dutch passport number</span></span>  <br/> <span data-ttu-id="835a8-439">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-439">passport number</span></span>  <br/> <span data-ttu-id="835a8-440">荷蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="835a8-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="835a8-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="835a8-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="835a8-442">paspoort</span></span>  <br/> <span data-ttu-id="835a8-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="835a8-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="835a8-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="835a8-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="835a8-445">波蘭</span><span class="sxs-lookup"><span data-stu-id="835a8-445">Poland</span></span>

<span data-ttu-id="835a8-446">如需詳細資訊，請參閱 「 波蘭護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="835a8-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="835a8-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="835a8-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="835a8-448">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-448">Format</span></span>

<span data-ttu-id="835a8-449">一個字母後尾隨六位數，代表不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="835a8-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-450">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-450">Pattern</span></span>

<span data-ttu-id="835a8-451">一個字母後尾隨六位數：</span><span class="sxs-lookup"><span data-stu-id="835a8-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="835a8-452">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="835a8-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="835a8-453">六位數</span><span class="sxs-lookup"><span data-stu-id="835a8-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="835a8-454">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-454">Checksum</span></span>

<span data-ttu-id="835a8-455">否</span><span class="sxs-lookup"><span data-stu-id="835a8-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-456">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-456">Definition</span></span>

<span data-ttu-id="835a8-457">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-458">規則運算式`Regex_portugal_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-459">從關鍵字`Keywords_portugal_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-460">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-460">Keywords</span></span>

<span data-ttu-id="835a8-461">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-461"></span></span>
|<span data-ttu-id="835a8-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-463">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-463">passport number</span></span>  <br/> <span data-ttu-id="835a8-464">葡萄牙文護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="835a8-465">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-465">passport no</span></span>  <br/> <span data-ttu-id="835a8-466">número 不要 passaporte</span><span class="sxs-lookup"><span data-stu-id="835a8-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="835a8-467">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="835a8-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="835a8-468">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-468">Format</span></span>

<span data-ttu-id="835a8-469">不含空格，並讓分隔字元的八個或九位數</span><span class="sxs-lookup"><span data-stu-id="835a8-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-470">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-470">Pattern</span></span>

<span data-ttu-id="835a8-471">八個或九位數</span><span class="sxs-lookup"><span data-stu-id="835a8-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="835a8-472">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-472">Checksum</span></span>

<span data-ttu-id="835a8-473">否</span><span class="sxs-lookup"><span data-stu-id="835a8-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-474">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-474">Definition</span></span>

<span data-ttu-id="835a8-475">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-476">規則運算式`Regex_romania_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-477">從關鍵字`Keywords_romania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-478">Keywords</span></span>

<span data-ttu-id="835a8-479">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-479"></span></span>
|<span data-ttu-id="835a8-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-481">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-481">passport number</span></span>  <br/> <span data-ttu-id="835a8-482">羅馬尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-482">romanian passport number</span></span>  <br/> <span data-ttu-id="835a8-483">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-483">passport no</span></span>  <br/> <span data-ttu-id="835a8-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="835a8-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="835a8-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="835a8-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="835a8-486">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-486">Format</span></span>

<span data-ttu-id="835a8-487">一個數字或字母後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="835a8-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-488">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-488">Pattern</span></span>

<span data-ttu-id="835a8-489">一個數字或字母 （不區分大小寫） 後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="835a8-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="835a8-490">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-490">Checksum</span></span>

<span data-ttu-id="835a8-491">否</span><span class="sxs-lookup"><span data-stu-id="835a8-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-492">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-492">Definition</span></span>

<span data-ttu-id="835a8-493">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-494">規則運算式`Regex_slovakia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-495">從關鍵字`Keywords_slovakia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-496">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-496">Keywords</span></span>

<span data-ttu-id="835a8-497">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-497"></span></span>
|<span data-ttu-id="835a8-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-499">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-499">passport number</span></span>  <br/> <span data-ttu-id="835a8-500">斯洛伐克護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="835a8-501">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-501">passport no</span></span>  <br/> <span data-ttu-id="835a8-502">Číslo pasu</span><span class="sxs-lookup"><span data-stu-id="835a8-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="835a8-503">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="835a8-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="835a8-504">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-504">Format</span></span>

<span data-ttu-id="835a8-505">兩個字母後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="835a8-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-506">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-506">Pattern</span></span>

<span data-ttu-id="835a8-507">兩個字母後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="835a8-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="835a8-508">字母"P"</span><span class="sxs-lookup"><span data-stu-id="835a8-508">The letter "P"</span></span>
    
- <span data-ttu-id="835a8-509">一個大寫字母</span><span class="sxs-lookup"><span data-stu-id="835a8-509">One uppercase letter</span></span>
    
- <span data-ttu-id="835a8-510">七位數</span><span class="sxs-lookup"><span data-stu-id="835a8-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="835a8-511">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-511">Checksum</span></span>

<span data-ttu-id="835a8-512">否</span><span class="sxs-lookup"><span data-stu-id="835a8-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-513">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-513">Definition</span></span>

<span data-ttu-id="835a8-514">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-515">規則運算式`Regex_slovenia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-516">從關鍵字`Keywords_slovenia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-517">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-517">Keywords</span></span>

<span data-ttu-id="835a8-518">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-518"></span></span>
|<span data-ttu-id="835a8-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-520">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-520">passport number</span></span>  <br/> <span data-ttu-id="835a8-521">斯洛維尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="835a8-522">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-522">passport no</span></span>  <br/> <span data-ttu-id="835a8-523">Številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="835a8-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="835a8-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="835a8-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="835a8-525">格式</span><span class="sxs-lookup"><span data-stu-id="835a8-525">Format</span></span>

<span data-ttu-id="835a8-526">八個或九個字元組合的字母和數字不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="835a8-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="835a8-527">模式</span><span class="sxs-lookup"><span data-stu-id="835a8-527">Pattern</span></span>

<span data-ttu-id="835a8-528">字母和數字 8 或九個字元組合：</span><span class="sxs-lookup"><span data-stu-id="835a8-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="835a8-529">兩個數字或字母</span><span class="sxs-lookup"><span data-stu-id="835a8-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="835a8-530">一個數字或字母 （選用）</span><span class="sxs-lookup"><span data-stu-id="835a8-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="835a8-531">六位數</span><span class="sxs-lookup"><span data-stu-id="835a8-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="835a8-532">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="835a8-532">Checksum</span></span>

<span data-ttu-id="835a8-533">不適用</span><span class="sxs-lookup"><span data-stu-id="835a8-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="835a8-534">定義</span><span class="sxs-lookup"><span data-stu-id="835a8-534">Definition</span></span>

<span data-ttu-id="835a8-535">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="835a8-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="835a8-536">規則運算式`Regex_spain_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="835a8-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="835a8-537">從關鍵字`Keywords_spain_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="835a8-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="835a8-538">關鍵字</span><span class="sxs-lookup"><span data-stu-id="835a8-538">Keywords</span></span>

<span data-ttu-id="835a8-539">| |</span><span class="sxs-lookup"><span data-stu-id="835a8-539"></span></span>
|<span data-ttu-id="835a8-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="835a8-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="835a8-541">passport</span><span class="sxs-lookup"><span data-stu-id="835a8-541">passport</span></span>  <br/> <span data-ttu-id="835a8-542">西班牙 passport</span><span class="sxs-lookup"><span data-stu-id="835a8-542">spain passport</span></span>  <br/> <span data-ttu-id="835a8-543">passport 活頁簿</span><span class="sxs-lookup"><span data-stu-id="835a8-543">passport book</span></span>  <br/> <span data-ttu-id="835a8-544">護照號碼</span><span class="sxs-lookup"><span data-stu-id="835a8-544">passport number</span></span>  <br/> <span data-ttu-id="835a8-545">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="835a8-545">passport no</span></span>  <br/> <span data-ttu-id="835a8-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="835a8-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="835a8-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="835a8-547">número pasaporte</span></span>  <br/> <span data-ttu-id="835a8-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="835a8-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="835a8-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="835a8-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="835a8-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="835a8-550">Sweden</span></span>

<span data-ttu-id="835a8-551">如需詳細資訊，請參閱 「 瑞典護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="835a8-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="835a8-552">英國</span><span class="sxs-lookup"><span data-stu-id="835a8-552">UK</span></span>

<span data-ttu-id="835a8-553">如需詳細資訊，請參閱 「 美國/英國的區段</span><span class="sxs-lookup"><span data-stu-id="835a8-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="835a8-554">護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="835a8-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="835a8-555">另請參閱</span><span class="sxs-lookup"><span data-stu-id="835a8-555">See also</span></span>

[<span data-ttu-id="835a8-556">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="835a8-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

