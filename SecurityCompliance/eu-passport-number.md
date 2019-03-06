---
title: 歐盟護照號碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟護照號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: 3ab92e87607f41cffa8c15f1179a4eef5369cb29
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410928"
---
# <a name="eu-passport-number"></a><span data-ttu-id="6d360-104">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-104">EU Passport Number</span></span>

<span data-ttu-id="6d360-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟護照號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="6d360-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="6d360-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="6d360-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="6d360-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="6d360-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="6d360-108">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-108">Format</span></span>

<span data-ttu-id="6d360-109">一個字母後尾隨一個選用空格和七位數</span><span class="sxs-lookup"><span data-stu-id="6d360-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-110">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-110">Pattern</span></span>

<span data-ttu-id="6d360-111">一個字母、 七位數和一個空格的組合：</span><span class="sxs-lookup"><span data-stu-id="6d360-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="6d360-112">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="6d360-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="6d360-113">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="6d360-113">One space (optional)</span></span>
    
- <span data-ttu-id="6d360-114">七位數</span><span class="sxs-lookup"><span data-stu-id="6d360-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6d360-115">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-115">Checksum</span></span>

<span data-ttu-id="6d360-116">不適用</span><span class="sxs-lookup"><span data-stu-id="6d360-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-117">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-117">Definition</span></span>

<span data-ttu-id="6d360-118">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-119">規則運算式`Regex_austria_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-120">從關鍵字`Keywords_austria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-121">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-121">Keywords</span></span>

<span data-ttu-id="6d360-122">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-122"></span></span>
|<span data-ttu-id="6d360-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-124">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-124">passport number</span></span>  <br/> <span data-ttu-id="6d360-125">奧地利護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-125">austrian passport number</span></span>  <br/> <span data-ttu-id="6d360-126">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-126">passport no</span></span>  <br/> <span data-ttu-id="6d360-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="6d360-127">reisepass</span></span>  <br/> <span data-ttu-id="6d360-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="6d360-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="6d360-129">比利時</span><span class="sxs-lookup"><span data-stu-id="6d360-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="6d360-130">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-130">Format</span></span>

<span data-ttu-id="6d360-131">兩個字母後尾隨六位數，代表不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="6d360-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-132">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-132">Pattern</span></span>

<span data-ttu-id="6d360-133">兩個字母後尾隨六位數和</span><span class="sxs-lookup"><span data-stu-id="6d360-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6d360-134">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-134">Checksum</span></span>

<span data-ttu-id="6d360-135">不適用</span><span class="sxs-lookup"><span data-stu-id="6d360-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-136">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-136">Definition</span></span>

<span data-ttu-id="6d360-137">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-138">規則運算式`Regex_belgium_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-139">從關鍵字`Keywords_belgium_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-140">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-140">Keywords</span></span>

<span data-ttu-id="6d360-141">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-141"></span></span>
|<span data-ttu-id="6d360-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-143">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-143">passport number</span></span>  <br/> <span data-ttu-id="6d360-144">比利時護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-144">belgian passport number</span></span>  <br/> <span data-ttu-id="6d360-145">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-145">passport no</span></span>  <br/> <span data-ttu-id="6d360-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="6d360-146">paspoort</span></span>  <br/> <span data-ttu-id="6d360-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="6d360-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="6d360-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="6d360-148">reisepass kein</span></span>  <br/> <span data-ttu-id="6d360-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="6d360-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="6d360-150">保加利亞</span><span class="sxs-lookup"><span data-stu-id="6d360-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="6d360-151">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-151">Format</span></span>

<span data-ttu-id="6d360-152">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="6d360-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-153">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-153">Pattern</span></span>

 <span data-ttu-id="6d360-154">九位數</span><span class="sxs-lookup"><span data-stu-id="6d360-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6d360-155">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-155">Checksum</span></span>

<span data-ttu-id="6d360-156">否</span><span class="sxs-lookup"><span data-stu-id="6d360-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-157">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-157">Definition</span></span>

<span data-ttu-id="6d360-158">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-159">規則運算式`Regex_bulgaria_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-160">從關鍵字`Keywords_bulgaria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-161">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-161">Keywords</span></span>

<span data-ttu-id="6d360-162">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-162"></span></span>
|<span data-ttu-id="6d360-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-164">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-164">passport number</span></span>  <br/> <span data-ttu-id="6d360-165">保加利亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="6d360-166">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-166">passport no</span></span>  <br/> <span data-ttu-id="6d360-167">НОМЕР НА ПАСПОРТА</span><span class="sxs-lookup"><span data-stu-id="6d360-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="6d360-168">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="6d360-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="6d360-169">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-169">Format</span></span>

<span data-ttu-id="6d360-170">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="6d360-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-171">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-171">Pattern</span></span>

 <span data-ttu-id="6d360-172">九位數</span><span class="sxs-lookup"><span data-stu-id="6d360-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6d360-173">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-173">Checksum</span></span>

<span data-ttu-id="6d360-174">否</span><span class="sxs-lookup"><span data-stu-id="6d360-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-175">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-175">Definition</span></span>

<span data-ttu-id="6d360-176">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-177">規則運算式`Regex_croatia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-178">從關鍵字`Keywords_croatia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-179">Keywords</span></span>

<span data-ttu-id="6d360-180">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-180"></span></span>
|<span data-ttu-id="6d360-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-182">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-182">passport number</span></span>  <br/> <span data-ttu-id="6d360-183">克羅埃西亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-183">croatian passport number</span></span>  <br/> <span data-ttu-id="6d360-184">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-184">passport no</span></span>  <br/> <span data-ttu-id="6d360-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="6d360-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="6d360-186">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="6d360-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="6d360-187">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-187">Format</span></span>

<span data-ttu-id="6d360-188">一個字母後尾隨不含空格或分隔符號 6-8 位數</span><span class="sxs-lookup"><span data-stu-id="6d360-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-189">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-189">Pattern</span></span>

<span data-ttu-id="6d360-190">一個字母後尾隨六至八位數</span><span class="sxs-lookup"><span data-stu-id="6d360-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6d360-191">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-191">Checksum</span></span>

<span data-ttu-id="6d360-192">否</span><span class="sxs-lookup"><span data-stu-id="6d360-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-193">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-193">Definition</span></span>

<span data-ttu-id="6d360-194">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-195">規則運算式`Regex_cyprus_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-196">從關鍵字`Keywords_cyprus_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-197">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-197">Keywords</span></span>

<span data-ttu-id="6d360-198">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-198"></span></span>
|<span data-ttu-id="6d360-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-200">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-200">passport number</span></span>  <br/> <span data-ttu-id="6d360-201">賽普勒斯護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="6d360-202">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-202">passport no</span></span>  <br/> <span data-ttu-id="6d360-203">ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ</span><span class="sxs-lookup"><span data-stu-id="6d360-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="6d360-204">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="6d360-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="6d360-205">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-205">Format</span></span>

<span data-ttu-id="6d360-206">不含空格或分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="6d360-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-207">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-207">Pattern</span></span>

<span data-ttu-id="6d360-208">不含空格或分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="6d360-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6d360-209">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-209">Checksum</span></span>

<span data-ttu-id="6d360-210">否</span><span class="sxs-lookup"><span data-stu-id="6d360-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-211">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-211">Definition</span></span>

<span data-ttu-id="6d360-212">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-213">規則運算式`Regex_czech_republic_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-214">從關鍵字`Keywords_czech_republic_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-215">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-215">Keywords</span></span>

<span data-ttu-id="6d360-216">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-216"></span></span>
|<span data-ttu-id="6d360-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-218">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-218">passport number</span></span>  <br/> <span data-ttu-id="6d360-219">捷克護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-219">czech passport number</span></span>  <br/> <span data-ttu-id="6d360-220">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-220">passport no</span></span>  <br/> <span data-ttu-id="6d360-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="6d360-221">cestovní pas</span></span>  <br/> <span data-ttu-id="6d360-222">pas</span><span class="sxs-lookup"><span data-stu-id="6d360-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="6d360-223">丹麥</span><span class="sxs-lookup"><span data-stu-id="6d360-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="6d360-224">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-224">Format</span></span>

<span data-ttu-id="6d360-225">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="6d360-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-226">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-226">Pattern</span></span>

 <span data-ttu-id="6d360-227">九位數</span><span class="sxs-lookup"><span data-stu-id="6d360-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6d360-228">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-228">Checksum</span></span>

<span data-ttu-id="6d360-229">否</span><span class="sxs-lookup"><span data-stu-id="6d360-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-230">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-230">Definition</span></span>

<span data-ttu-id="6d360-231">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-232">規則運算式`Regex_denmark_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-233">從關鍵字`Keywords_denmark_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-234">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-234">Keywords</span></span>

<span data-ttu-id="6d360-235">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-235"></span></span>
|<span data-ttu-id="6d360-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-237">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-237">passport number</span></span>  <br/> <span data-ttu-id="6d360-238">丹麥文護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-238">danish passport number</span></span>  <br/> <span data-ttu-id="6d360-239">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-239">passport no</span></span>  <br/> <span data-ttu-id="6d360-240">pas</span><span class="sxs-lookup"><span data-stu-id="6d360-240">pas</span></span>  <br/> <span data-ttu-id="6d360-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="6d360-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="6d360-242">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="6d360-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="6d360-243">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-243">Format</span></span>

<span data-ttu-id="6d360-244">一個字母後尾隨七位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="6d360-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-245">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-245">Pattern</span></span>

<span data-ttu-id="6d360-246">一個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="6d360-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6d360-247">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-247">Checksum</span></span>

<span data-ttu-id="6d360-248">否</span><span class="sxs-lookup"><span data-stu-id="6d360-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-249">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-249">Definition</span></span>

<span data-ttu-id="6d360-250">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-251">規則運算式`Regex_estonia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-252">從關鍵字`Keywords_estonia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-253">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-253">Keywords</span></span>

<span data-ttu-id="6d360-254">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-254"></span></span>
|<span data-ttu-id="6d360-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-256">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-256">passport number</span></span>  <br/> <span data-ttu-id="6d360-257">愛沙尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-257">estonian passport number</span></span>  <br/> <span data-ttu-id="6d360-258">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-258">passport no</span></span>  <br/> <span data-ttu-id="6d360-259">eesti kodaniku 複雜</span><span class="sxs-lookup"><span data-stu-id="6d360-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="6d360-260">芬蘭</span><span class="sxs-lookup"><span data-stu-id="6d360-260">Finland</span></span>

<span data-ttu-id="6d360-261">如需詳細資訊，請參閱 「 芬蘭護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="6d360-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="6d360-262">法國</span><span class="sxs-lookup"><span data-stu-id="6d360-262">France</span></span>

<span data-ttu-id="6d360-263">如需詳細資訊，請參閱 「 法國護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="6d360-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="6d360-264">德國</span><span class="sxs-lookup"><span data-stu-id="6d360-264">Germany</span></span>

<span data-ttu-id="6d360-265">如需詳細資訊，請參閱 「 德國護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="6d360-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="6d360-266">希臘</span><span class="sxs-lookup"><span data-stu-id="6d360-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="6d360-267">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-267">Format</span></span>

<span data-ttu-id="6d360-268">兩個字母後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="6d360-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-269">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-269">Pattern</span></span>

<span data-ttu-id="6d360-270">兩個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="6d360-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6d360-271">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-271">Checksum</span></span>

<span data-ttu-id="6d360-272">否</span><span class="sxs-lookup"><span data-stu-id="6d360-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-273">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-273">Definition</span></span>

<span data-ttu-id="6d360-274">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-275">規則運算式`Regex_greece_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-276">從關鍵字`Keywords_greece_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-277">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-277">Keywords</span></span>

<span data-ttu-id="6d360-278">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-278"></span></span>
|<span data-ttu-id="6d360-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-280">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-280">passport number</span></span>  <br/> <span data-ttu-id="6d360-281">希臘文護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-281">greek passport number</span></span>  <br/> <span data-ttu-id="6d360-282">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-282">passport no</span></span>  <br/> <span data-ttu-id="6d360-283">ΔΙΑΒΑΤΗΡΙΟ</span><span class="sxs-lookup"><span data-stu-id="6d360-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="6d360-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="6d360-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="6d360-285">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-285">Format</span></span>

<span data-ttu-id="6d360-286">兩個字母後尾隨六個或七位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="6d360-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-287">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-287">Pattern</span></span>

<span data-ttu-id="6d360-288">兩個字母後尾隨六個或七位數</span><span class="sxs-lookup"><span data-stu-id="6d360-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6d360-289">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-289">Checksum</span></span>

<span data-ttu-id="6d360-290">否</span><span class="sxs-lookup"><span data-stu-id="6d360-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-291">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-291">Definition</span></span>

<span data-ttu-id="6d360-292">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-293">規則運算式`Regex_hungary_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-294">從關鍵字`Keywords_hungary_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-295">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-295">Keywords</span></span>

<span data-ttu-id="6d360-296">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-296"></span></span>
|<span data-ttu-id="6d360-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-298">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-298">passport number</span></span>  <br/> <span data-ttu-id="6d360-299">匈牙利文護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="6d360-300">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-300">passport no</span></span>  <br/> <span data-ttu-id="6d360-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="6d360-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="6d360-302">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="6d360-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="6d360-303">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-303">Format</span></span>

<span data-ttu-id="6d360-304">兩個字母或位數後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="6d360-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-305">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-305">Pattern</span></span>

<span data-ttu-id="6d360-306">兩個字母或位數後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="6d360-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="6d360-307">兩個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="6d360-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="6d360-308">七位數</span><span class="sxs-lookup"><span data-stu-id="6d360-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6d360-309">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-309">Checksum</span></span>

<span data-ttu-id="6d360-310">否</span><span class="sxs-lookup"><span data-stu-id="6d360-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-311">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-311">Definition</span></span>

<span data-ttu-id="6d360-312">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-313">規則運算式`Regex_ireland_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-314">從關鍵字`Keywords_ireland_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-315">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-315">Keywords</span></span>

<span data-ttu-id="6d360-316">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-316"></span></span>
|<span data-ttu-id="6d360-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-318">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-318">passport number</span></span>  <br/> <span data-ttu-id="6d360-319">愛爾蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-319">irish passport number</span></span>  <br/> <span data-ttu-id="6d360-320">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-320">passport no</span></span>  <br/> <span data-ttu-id="6d360-321">pas</span><span class="sxs-lookup"><span data-stu-id="6d360-321">pas</span></span>  <br/> <span data-ttu-id="6d360-322">passport</span><span class="sxs-lookup"><span data-stu-id="6d360-322">passport</span></span>  <br/> <span data-ttu-id="6d360-323">passeport</span><span class="sxs-lookup"><span data-stu-id="6d360-323">passeport</span></span>  <br/> <span data-ttu-id="6d360-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="6d360-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="6d360-325">義大利</span><span class="sxs-lookup"><span data-stu-id="6d360-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="6d360-326">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-326">Format</span></span>

<span data-ttu-id="6d360-327">兩個字母或位數後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="6d360-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-328">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-328">Pattern</span></span>

<span data-ttu-id="6d360-329">兩個字母或位數後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="6d360-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="6d360-330">兩個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="6d360-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="6d360-331">七位數</span><span class="sxs-lookup"><span data-stu-id="6d360-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6d360-332">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-332">Checksum</span></span>

<span data-ttu-id="6d360-333">不適用</span><span class="sxs-lookup"><span data-stu-id="6d360-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-334">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-334">Definition</span></span>

<span data-ttu-id="6d360-335">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-336">規則運算式`Regex_italy_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-337">從關鍵字`Keywords_italy_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-338">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-338">Keywords</span></span>

<span data-ttu-id="6d360-339">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-339"></span></span>
|<span data-ttu-id="6d360-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-341">義大利文護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-341">italian passport number</span></span>  <br/> <span data-ttu-id="6d360-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="6d360-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="6d360-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="6d360-343">passaporto</span></span>  <br/> <span data-ttu-id="6d360-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="6d360-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="6d360-345">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-345">passport number</span></span>  <br/> <span data-ttu-id="6d360-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="6d360-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="6d360-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="6d360-347">passaporto numero</span></span>  <br/> <span data-ttu-id="6d360-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="6d360-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="6d360-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="6d360-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="6d360-350">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="6d360-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="6d360-351">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-351">Format</span></span>

<span data-ttu-id="6d360-352">兩個字母或位數後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="6d360-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-353">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-353">Pattern</span></span>

<span data-ttu-id="6d360-354">兩個字母或位數後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="6d360-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="6d360-355">兩個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="6d360-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="6d360-356">七位數</span><span class="sxs-lookup"><span data-stu-id="6d360-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6d360-357">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-357">Checksum</span></span>

<span data-ttu-id="6d360-358">否</span><span class="sxs-lookup"><span data-stu-id="6d360-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-359">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-359">Definition</span></span>

<span data-ttu-id="6d360-360">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-361">規則運算式`Regex_latvia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-362">從關鍵字`Keywords_latvia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-363">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-363">Keywords</span></span>

<span data-ttu-id="6d360-364">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-364"></span></span>
|<span data-ttu-id="6d360-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-366">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-366">passport number</span></span>  <br/> <span data-ttu-id="6d360-367">拉脫維亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-367">latvian passport number</span></span>  <br/> <span data-ttu-id="6d360-368">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-368">passport no</span></span>  <br/> <span data-ttu-id="6d360-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="6d360-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="6d360-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="6d360-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="6d360-371">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-371">Format</span></span>

<span data-ttu-id="6d360-372">八個個數字或字母不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="6d360-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-373">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-373">Pattern</span></span>

<span data-ttu-id="6d360-374">八個個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="6d360-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6d360-375">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-375">Checksum</span></span>

<span data-ttu-id="6d360-376">不適用</span><span class="sxs-lookup"><span data-stu-id="6d360-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-377">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-377">Definition</span></span>

<span data-ttu-id="6d360-378">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-379">規則運算式`Regex_lithuania_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-380">從關鍵字`Keywords_lithuania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-381">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-381">Keywords</span></span>

<span data-ttu-id="6d360-382">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-382"></span></span>
|<span data-ttu-id="6d360-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-384">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-384">passport number</span></span>  <br/> <span data-ttu-id="6d360-385">lithunian 護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="6d360-386">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-386">passport no</span></span>  <br/> <span data-ttu-id="6d360-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="6d360-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="6d360-388">盧森堡</span><span class="sxs-lookup"><span data-stu-id="6d360-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="6d360-389">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-389">Format</span></span>

<span data-ttu-id="6d360-390">八個個數字或字母不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="6d360-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-391">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-391">Pattern</span></span>

<span data-ttu-id="6d360-392">八個個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="6d360-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6d360-393">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-393">Checksum</span></span>

<span data-ttu-id="6d360-394">否</span><span class="sxs-lookup"><span data-stu-id="6d360-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-395">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-395">Definition</span></span>

<span data-ttu-id="6d360-396">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-397">規則運算式`Regex_nation_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-398">從關鍵字`Keywords_nation_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-399">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-399">Keywords</span></span>

<span data-ttu-id="6d360-400">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-400"></span></span>
|<span data-ttu-id="6d360-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-402">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-402">passport number</span></span>  <br/> <span data-ttu-id="6d360-403">拉脫維亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-403">latvian passport number</span></span>  <br/> <span data-ttu-id="6d360-404">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-404">passport no</span></span>  <br/> <span data-ttu-id="6d360-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="6d360-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="6d360-406">馬爾他</span><span class="sxs-lookup"><span data-stu-id="6d360-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="6d360-407">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-407">Format</span></span>

<span data-ttu-id="6d360-408">不含空格或分隔符號七位數</span><span class="sxs-lookup"><span data-stu-id="6d360-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-409">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-409">Pattern</span></span>

 <span data-ttu-id="6d360-410">七位數</span><span class="sxs-lookup"><span data-stu-id="6d360-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6d360-411">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-411">Checksum</span></span>

<span data-ttu-id="6d360-412">否</span><span class="sxs-lookup"><span data-stu-id="6d360-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-413">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-413">Definition</span></span>

<span data-ttu-id="6d360-414">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-415">規則運算式`Regex_malta_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-416">從關鍵字`Keywords_malta_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-417">Keywords</span></span>

<span data-ttu-id="6d360-418">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-418"></span></span>
|<span data-ttu-id="6d360-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-420">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-420">passport number</span></span>  <br/> <span data-ttu-id="6d360-421">馬爾他護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-421">maltese passport number</span></span>  <br/> <span data-ttu-id="6d360-422">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-422">passport no</span></span>  <br/> <span data-ttu-id="6d360-423">numru tal passaport</span><span class="sxs-lookup"><span data-stu-id="6d360-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="6d360-424">荷蘭</span><span class="sxs-lookup"><span data-stu-id="6d360-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="6d360-425">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-425">Format</span></span>

<span data-ttu-id="6d360-426">九個字母或不含空格或分隔符號的數字</span><span class="sxs-lookup"><span data-stu-id="6d360-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-427">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-427">Pattern</span></span>

<span data-ttu-id="6d360-428">九個字母或四位數</span><span class="sxs-lookup"><span data-stu-id="6d360-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6d360-429">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-429">Checksum</span></span>

<span data-ttu-id="6d360-430">不適用</span><span class="sxs-lookup"><span data-stu-id="6d360-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-431">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-431">Definition</span></span>

<span data-ttu-id="6d360-432">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-433">規則運算式`Regex_netherlands_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-434">從關鍵字`Keywords_netherlands_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-435">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-435">Keywords</span></span>

<span data-ttu-id="6d360-436">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-436"></span></span>
|<span data-ttu-id="6d360-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-438">荷蘭文護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-438">dutch passport number</span></span>  <br/> <span data-ttu-id="6d360-439">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-439">passport number</span></span>  <br/> <span data-ttu-id="6d360-440">荷蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="6d360-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="6d360-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="6d360-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="6d360-442">paspoort</span></span>  <br/> <span data-ttu-id="6d360-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="6d360-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="6d360-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="6d360-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="6d360-445">波蘭</span><span class="sxs-lookup"><span data-stu-id="6d360-445">Poland</span></span>

<span data-ttu-id="6d360-446">如需詳細資訊，請參閱 「 波蘭護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="6d360-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="6d360-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="6d360-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="6d360-448">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-448">Format</span></span>

<span data-ttu-id="6d360-449">一個字母後尾隨六位數，代表不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="6d360-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-450">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-450">Pattern</span></span>

<span data-ttu-id="6d360-451">一個字母後尾隨六位數：</span><span class="sxs-lookup"><span data-stu-id="6d360-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="6d360-452">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="6d360-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="6d360-453">六位數</span><span class="sxs-lookup"><span data-stu-id="6d360-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6d360-454">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-454">Checksum</span></span>

<span data-ttu-id="6d360-455">否</span><span class="sxs-lookup"><span data-stu-id="6d360-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-456">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-456">Definition</span></span>

<span data-ttu-id="6d360-457">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-458">規則運算式`Regex_portugal_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-459">從關鍵字`Keywords_portugal_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-460">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-460">Keywords</span></span>

<span data-ttu-id="6d360-461">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-461"></span></span>
|<span data-ttu-id="6d360-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-463">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-463">passport number</span></span>  <br/> <span data-ttu-id="6d360-464">葡萄牙文護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="6d360-465">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-465">passport no</span></span>  <br/> <span data-ttu-id="6d360-466">número 不要 passaporte</span><span class="sxs-lookup"><span data-stu-id="6d360-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="6d360-467">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="6d360-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="6d360-468">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-468">Format</span></span>

<span data-ttu-id="6d360-469">不含空格，並讓分隔字元的八個或九位數</span><span class="sxs-lookup"><span data-stu-id="6d360-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-470">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-470">Pattern</span></span>

<span data-ttu-id="6d360-471">八個或九位數</span><span class="sxs-lookup"><span data-stu-id="6d360-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6d360-472">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-472">Checksum</span></span>

<span data-ttu-id="6d360-473">否</span><span class="sxs-lookup"><span data-stu-id="6d360-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-474">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-474">Definition</span></span>

<span data-ttu-id="6d360-475">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-476">規則運算式`Regex_romania_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-477">從關鍵字`Keywords_romania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-478">Keywords</span></span>

<span data-ttu-id="6d360-479">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-479"></span></span>
|<span data-ttu-id="6d360-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-481">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-481">passport number</span></span>  <br/> <span data-ttu-id="6d360-482">羅馬尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-482">romanian passport number</span></span>  <br/> <span data-ttu-id="6d360-483">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-483">passport no</span></span>  <br/> <span data-ttu-id="6d360-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="6d360-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="6d360-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="6d360-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="6d360-486">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-486">Format</span></span>

<span data-ttu-id="6d360-487">一個數字或字母後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="6d360-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-488">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-488">Pattern</span></span>

<span data-ttu-id="6d360-489">一個數字或字母 （不區分大小寫） 後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="6d360-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6d360-490">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-490">Checksum</span></span>

<span data-ttu-id="6d360-491">否</span><span class="sxs-lookup"><span data-stu-id="6d360-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-492">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-492">Definition</span></span>

<span data-ttu-id="6d360-493">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-494">規則運算式`Regex_slovakia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-495">從關鍵字`Keywords_slovakia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-496">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-496">Keywords</span></span>

<span data-ttu-id="6d360-497">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-497"></span></span>
|<span data-ttu-id="6d360-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-499">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-499">passport number</span></span>  <br/> <span data-ttu-id="6d360-500">斯洛伐克護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="6d360-501">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-501">passport no</span></span>  <br/> <span data-ttu-id="6d360-502">Číslo pasu</span><span class="sxs-lookup"><span data-stu-id="6d360-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="6d360-503">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="6d360-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="6d360-504">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-504">Format</span></span>

<span data-ttu-id="6d360-505">兩個字母後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="6d360-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-506">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-506">Pattern</span></span>

<span data-ttu-id="6d360-507">兩個字母後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="6d360-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="6d360-508">字母"P"</span><span class="sxs-lookup"><span data-stu-id="6d360-508">The letter "P"</span></span>
    
- <span data-ttu-id="6d360-509">一個大寫字母</span><span class="sxs-lookup"><span data-stu-id="6d360-509">One uppercase letter</span></span>
    
- <span data-ttu-id="6d360-510">七位數</span><span class="sxs-lookup"><span data-stu-id="6d360-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6d360-511">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-511">Checksum</span></span>

<span data-ttu-id="6d360-512">否</span><span class="sxs-lookup"><span data-stu-id="6d360-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-513">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-513">Definition</span></span>

<span data-ttu-id="6d360-514">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-515">規則運算式`Regex_slovenia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-516">從關鍵字`Keywords_slovenia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-517">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-517">Keywords</span></span>

<span data-ttu-id="6d360-518">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-518"></span></span>
|<span data-ttu-id="6d360-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-520">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-520">passport number</span></span>  <br/> <span data-ttu-id="6d360-521">斯洛維尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="6d360-522">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-522">passport no</span></span>  <br/> <span data-ttu-id="6d360-523">Številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="6d360-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="6d360-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="6d360-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="6d360-525">Format</span><span class="sxs-lookup"><span data-stu-id="6d360-525">Format</span></span>

<span data-ttu-id="6d360-526">八個或九個字元組合的字母和數字不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="6d360-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6d360-527">模式</span><span class="sxs-lookup"><span data-stu-id="6d360-527">Pattern</span></span>

<span data-ttu-id="6d360-528">字母和數字 8 或九個字元組合：</span><span class="sxs-lookup"><span data-stu-id="6d360-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="6d360-529">兩個數字或字母</span><span class="sxs-lookup"><span data-stu-id="6d360-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="6d360-530">一個數字或字母 （選用）</span><span class="sxs-lookup"><span data-stu-id="6d360-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="6d360-531">六位數</span><span class="sxs-lookup"><span data-stu-id="6d360-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6d360-532">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="6d360-532">Checksum</span></span>

<span data-ttu-id="6d360-533">不適用</span><span class="sxs-lookup"><span data-stu-id="6d360-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="6d360-534">定義</span><span class="sxs-lookup"><span data-stu-id="6d360-534">Definition</span></span>

<span data-ttu-id="6d360-535">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="6d360-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6d360-536">規則運算式`Regex_spain_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="6d360-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6d360-537">從關鍵字`Keywords_spain_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="6d360-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6d360-538">關鍵字</span><span class="sxs-lookup"><span data-stu-id="6d360-538">Keywords</span></span>

<span data-ttu-id="6d360-539">| |</span><span class="sxs-lookup"><span data-stu-id="6d360-539"></span></span>
|<span data-ttu-id="6d360-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="6d360-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="6d360-541">passport</span><span class="sxs-lookup"><span data-stu-id="6d360-541">passport</span></span>  <br/> <span data-ttu-id="6d360-542">西班牙 passport</span><span class="sxs-lookup"><span data-stu-id="6d360-542">spain passport</span></span>  <br/> <span data-ttu-id="6d360-543">passport 活頁簿</span><span class="sxs-lookup"><span data-stu-id="6d360-543">passport book</span></span>  <br/> <span data-ttu-id="6d360-544">護照號碼</span><span class="sxs-lookup"><span data-stu-id="6d360-544">passport number</span></span>  <br/> <span data-ttu-id="6d360-545">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="6d360-545">passport no</span></span>  <br/> <span data-ttu-id="6d360-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="6d360-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="6d360-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="6d360-547">número pasaporte</span></span>  <br/> <span data-ttu-id="6d360-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="6d360-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="6d360-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="6d360-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="6d360-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="6d360-550">Sweden</span></span>

<span data-ttu-id="6d360-551">如需詳細資訊，請參閱 「 瑞典護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="6d360-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="6d360-552">英國</span><span class="sxs-lookup"><span data-stu-id="6d360-552">UK</span></span>

<span data-ttu-id="6d360-553">如需詳細資訊，請參閱 「 美國/英國的區段</span><span class="sxs-lookup"><span data-stu-id="6d360-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="6d360-554">護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="6d360-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6d360-555">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6d360-555">See also</span></span>

[<span data-ttu-id="6d360-556">機密資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="6d360-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

