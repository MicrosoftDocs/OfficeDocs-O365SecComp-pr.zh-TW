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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256821"
---
# <a name="eu-passport-number"></a><span data-ttu-id="da311-104">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-104">EU Passport Number</span></span>

<span data-ttu-id="da311-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟護照號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="da311-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="da311-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="da311-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="da311-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="da311-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="da311-108">格式</span><span class="sxs-lookup"><span data-stu-id="da311-108">Format</span></span>

<span data-ttu-id="da311-109">一個字母後尾隨一個選用空格和七位數</span><span class="sxs-lookup"><span data-stu-id="da311-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-110">模式</span><span class="sxs-lookup"><span data-stu-id="da311-110">Pattern</span></span>

<span data-ttu-id="da311-111">一個字母、 七位數和一個空格的組合：</span><span class="sxs-lookup"><span data-stu-id="da311-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="da311-112">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="da311-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="da311-113">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="da311-113">One space (optional)</span></span>
    
- <span data-ttu-id="da311-114">七位數</span><span class="sxs-lookup"><span data-stu-id="da311-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="da311-115">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-115">Checksum</span></span>

<span data-ttu-id="da311-116">不適用</span><span class="sxs-lookup"><span data-stu-id="da311-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-117">定義</span><span class="sxs-lookup"><span data-stu-id="da311-117">Definition</span></span>

<span data-ttu-id="da311-118">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-119">規則運算式`Regex_austria_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-120">從關鍵字`Keywords_austria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-121">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-121">Keywords</span></span>

<span data-ttu-id="da311-122">| |</span><span class="sxs-lookup"><span data-stu-id="da311-122"></span></span>
|<span data-ttu-id="da311-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-124">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-124">passport number</span></span>  <br/> <span data-ttu-id="da311-125">奧地利護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-125">austrian passport number</span></span>  <br/> <span data-ttu-id="da311-126">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-126">passport no</span></span>  <br/> <span data-ttu-id="da311-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="da311-127">reisepass</span></span>  <br/> <span data-ttu-id="da311-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="da311-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="da311-129">比利時</span><span class="sxs-lookup"><span data-stu-id="da311-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="da311-130">格式</span><span class="sxs-lookup"><span data-stu-id="da311-130">Format</span></span>

<span data-ttu-id="da311-131">兩個字母後尾隨六位數，代表不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="da311-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-132">模式</span><span class="sxs-lookup"><span data-stu-id="da311-132">Pattern</span></span>

<span data-ttu-id="da311-133">兩個字母後尾隨六位數和</span><span class="sxs-lookup"><span data-stu-id="da311-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="da311-134">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-134">Checksum</span></span>

<span data-ttu-id="da311-135">不適用</span><span class="sxs-lookup"><span data-stu-id="da311-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-136">定義</span><span class="sxs-lookup"><span data-stu-id="da311-136">Definition</span></span>

<span data-ttu-id="da311-137">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-138">規則運算式`Regex_belgium_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-139">從關鍵字`Keywords_belgium_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-140">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-140">Keywords</span></span>

<span data-ttu-id="da311-141">| |</span><span class="sxs-lookup"><span data-stu-id="da311-141"></span></span>
|<span data-ttu-id="da311-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-143">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-143">passport number</span></span>  <br/> <span data-ttu-id="da311-144">比利時護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-144">belgian passport number</span></span>  <br/> <span data-ttu-id="da311-145">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-145">passport no</span></span>  <br/> <span data-ttu-id="da311-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="da311-146">paspoort</span></span>  <br/> <span data-ttu-id="da311-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="da311-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="da311-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="da311-148">reisepass kein</span></span>  <br/> <span data-ttu-id="da311-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="da311-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="da311-150">保加利亞</span><span class="sxs-lookup"><span data-stu-id="da311-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="da311-151">格式</span><span class="sxs-lookup"><span data-stu-id="da311-151">Format</span></span>

<span data-ttu-id="da311-152">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="da311-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-153">模式</span><span class="sxs-lookup"><span data-stu-id="da311-153">Pattern</span></span>

 <span data-ttu-id="da311-154">九位數</span><span class="sxs-lookup"><span data-stu-id="da311-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="da311-155">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-155">Checksum</span></span>

<span data-ttu-id="da311-156">否</span><span class="sxs-lookup"><span data-stu-id="da311-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-157">定義</span><span class="sxs-lookup"><span data-stu-id="da311-157">Definition</span></span>

<span data-ttu-id="da311-158">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-159">規則運算式`Regex_bulgaria_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-160">從關鍵字`Keywords_bulgaria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-161">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-161">Keywords</span></span>

<span data-ttu-id="da311-162">| |</span><span class="sxs-lookup"><span data-stu-id="da311-162"></span></span>
|<span data-ttu-id="da311-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-164">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-164">passport number</span></span>  <br/> <span data-ttu-id="da311-165">保加利亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="da311-166">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-166">passport no</span></span>  <br/> <span data-ttu-id="da311-167">НОМЕР НА ПАСПОРТА</span><span class="sxs-lookup"><span data-stu-id="da311-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="da311-168">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="da311-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="da311-169">格式</span><span class="sxs-lookup"><span data-stu-id="da311-169">Format</span></span>

<span data-ttu-id="da311-170">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="da311-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-171">模式</span><span class="sxs-lookup"><span data-stu-id="da311-171">Pattern</span></span>

 <span data-ttu-id="da311-172">九位數</span><span class="sxs-lookup"><span data-stu-id="da311-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="da311-173">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-173">Checksum</span></span>

<span data-ttu-id="da311-174">否</span><span class="sxs-lookup"><span data-stu-id="da311-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-175">定義</span><span class="sxs-lookup"><span data-stu-id="da311-175">Definition</span></span>

<span data-ttu-id="da311-176">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-177">規則運算式`Regex_croatia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-178">從關鍵字`Keywords_croatia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-179">Keywords</span></span>

<span data-ttu-id="da311-180">| |</span><span class="sxs-lookup"><span data-stu-id="da311-180"></span></span>
|<span data-ttu-id="da311-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-182">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-182">passport number</span></span>  <br/> <span data-ttu-id="da311-183">克羅埃西亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-183">croatian passport number</span></span>  <br/> <span data-ttu-id="da311-184">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-184">passport no</span></span>  <br/> <span data-ttu-id="da311-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="da311-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="da311-186">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="da311-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="da311-187">格式</span><span class="sxs-lookup"><span data-stu-id="da311-187">Format</span></span>

<span data-ttu-id="da311-188">一個字母後尾隨不含空格或分隔符號 6-8 位數</span><span class="sxs-lookup"><span data-stu-id="da311-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-189">模式</span><span class="sxs-lookup"><span data-stu-id="da311-189">Pattern</span></span>

<span data-ttu-id="da311-190">一個字母後尾隨六至八位數</span><span class="sxs-lookup"><span data-stu-id="da311-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="da311-191">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-191">Checksum</span></span>

<span data-ttu-id="da311-192">否</span><span class="sxs-lookup"><span data-stu-id="da311-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-193">定義</span><span class="sxs-lookup"><span data-stu-id="da311-193">Definition</span></span>

<span data-ttu-id="da311-194">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-195">規則運算式`Regex_cyprus_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-196">從關鍵字`Keywords_cyprus_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-197">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-197">Keywords</span></span>

<span data-ttu-id="da311-198">| |</span><span class="sxs-lookup"><span data-stu-id="da311-198"></span></span>
|<span data-ttu-id="da311-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-200">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-200">passport number</span></span>  <br/> <span data-ttu-id="da311-201">賽普勒斯護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="da311-202">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-202">passport no</span></span>  <br/> <span data-ttu-id="da311-203">ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ</span><span class="sxs-lookup"><span data-stu-id="da311-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="da311-204">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="da311-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="da311-205">格式</span><span class="sxs-lookup"><span data-stu-id="da311-205">Format</span></span>

<span data-ttu-id="da311-206">不含空格或分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="da311-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-207">模式</span><span class="sxs-lookup"><span data-stu-id="da311-207">Pattern</span></span>

<span data-ttu-id="da311-208">不含空格或分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="da311-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="da311-209">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-209">Checksum</span></span>

<span data-ttu-id="da311-210">否</span><span class="sxs-lookup"><span data-stu-id="da311-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-211">定義</span><span class="sxs-lookup"><span data-stu-id="da311-211">Definition</span></span>

<span data-ttu-id="da311-212">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-213">規則運算式`Regex_czech_republic_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-214">從關鍵字`Keywords_czech_republic_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-215">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-215">Keywords</span></span>

<span data-ttu-id="da311-216">| |</span><span class="sxs-lookup"><span data-stu-id="da311-216"></span></span>
|<span data-ttu-id="da311-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-218">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-218">passport number</span></span>  <br/> <span data-ttu-id="da311-219">捷克護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-219">czech passport number</span></span>  <br/> <span data-ttu-id="da311-220">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-220">passport no</span></span>  <br/> <span data-ttu-id="da311-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="da311-221">cestovní pas</span></span>  <br/> <span data-ttu-id="da311-222">pas</span><span class="sxs-lookup"><span data-stu-id="da311-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="da311-223">丹麥</span><span class="sxs-lookup"><span data-stu-id="da311-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="da311-224">格式</span><span class="sxs-lookup"><span data-stu-id="da311-224">Format</span></span>

<span data-ttu-id="da311-225">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="da311-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-226">模式</span><span class="sxs-lookup"><span data-stu-id="da311-226">Pattern</span></span>

 <span data-ttu-id="da311-227">九位數</span><span class="sxs-lookup"><span data-stu-id="da311-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="da311-228">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-228">Checksum</span></span>

<span data-ttu-id="da311-229">否</span><span class="sxs-lookup"><span data-stu-id="da311-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-230">定義</span><span class="sxs-lookup"><span data-stu-id="da311-230">Definition</span></span>

<span data-ttu-id="da311-231">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-232">規則運算式`Regex_denmark_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-233">從關鍵字`Keywords_denmark_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-234">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-234">Keywords</span></span>

<span data-ttu-id="da311-235">| |</span><span class="sxs-lookup"><span data-stu-id="da311-235"></span></span>
|<span data-ttu-id="da311-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-237">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-237">passport number</span></span>  <br/> <span data-ttu-id="da311-238">丹麥文護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-238">danish passport number</span></span>  <br/> <span data-ttu-id="da311-239">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-239">passport no</span></span>  <br/> <span data-ttu-id="da311-240">pas</span><span class="sxs-lookup"><span data-stu-id="da311-240">pas</span></span>  <br/> <span data-ttu-id="da311-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="da311-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="da311-242">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="da311-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="da311-243">格式</span><span class="sxs-lookup"><span data-stu-id="da311-243">Format</span></span>

<span data-ttu-id="da311-244">一個字母後尾隨七位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="da311-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-245">模式</span><span class="sxs-lookup"><span data-stu-id="da311-245">Pattern</span></span>

<span data-ttu-id="da311-246">一個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="da311-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="da311-247">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-247">Checksum</span></span>

<span data-ttu-id="da311-248">否</span><span class="sxs-lookup"><span data-stu-id="da311-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-249">定義</span><span class="sxs-lookup"><span data-stu-id="da311-249">Definition</span></span>

<span data-ttu-id="da311-250">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-251">規則運算式`Regex_estonia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-252">從關鍵字`Keywords_estonia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-253">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-253">Keywords</span></span>

<span data-ttu-id="da311-254">| |</span><span class="sxs-lookup"><span data-stu-id="da311-254"></span></span>
|<span data-ttu-id="da311-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-256">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-256">passport number</span></span>  <br/> <span data-ttu-id="da311-257">愛沙尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-257">estonian passport number</span></span>  <br/> <span data-ttu-id="da311-258">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-258">passport no</span></span>  <br/> <span data-ttu-id="da311-259">eesti kodaniku 複雜</span><span class="sxs-lookup"><span data-stu-id="da311-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="da311-260">芬蘭</span><span class="sxs-lookup"><span data-stu-id="da311-260">Finland</span></span>

<span data-ttu-id="da311-261">如需詳細資訊，請參閱 「 芬蘭護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="da311-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="da311-262">法國</span><span class="sxs-lookup"><span data-stu-id="da311-262">France</span></span>

<span data-ttu-id="da311-263">如需詳細資訊，請參閱 「 法國護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="da311-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="da311-264">德國</span><span class="sxs-lookup"><span data-stu-id="da311-264">Germany</span></span>

<span data-ttu-id="da311-265">如需詳細資訊，請參閱 「 德國護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="da311-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="da311-266">希臘</span><span class="sxs-lookup"><span data-stu-id="da311-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="da311-267">格式</span><span class="sxs-lookup"><span data-stu-id="da311-267">Format</span></span>

<span data-ttu-id="da311-268">兩個字母後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="da311-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-269">模式</span><span class="sxs-lookup"><span data-stu-id="da311-269">Pattern</span></span>

<span data-ttu-id="da311-270">兩個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="da311-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="da311-271">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-271">Checksum</span></span>

<span data-ttu-id="da311-272">否</span><span class="sxs-lookup"><span data-stu-id="da311-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-273">定義</span><span class="sxs-lookup"><span data-stu-id="da311-273">Definition</span></span>

<span data-ttu-id="da311-274">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-275">規則運算式`Regex_greece_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-276">從關鍵字`Keywords_greece_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-277">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-277">Keywords</span></span>

<span data-ttu-id="da311-278">| |</span><span class="sxs-lookup"><span data-stu-id="da311-278"></span></span>
|<span data-ttu-id="da311-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-280">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-280">passport number</span></span>  <br/> <span data-ttu-id="da311-281">希臘文護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-281">greek passport number</span></span>  <br/> <span data-ttu-id="da311-282">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-282">passport no</span></span>  <br/> <span data-ttu-id="da311-283">ΔΙΑΒΑΤΗΡΙΟ</span><span class="sxs-lookup"><span data-stu-id="da311-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="da311-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="da311-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="da311-285">格式</span><span class="sxs-lookup"><span data-stu-id="da311-285">Format</span></span>

<span data-ttu-id="da311-286">兩個字母後尾隨六個或七位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="da311-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-287">模式</span><span class="sxs-lookup"><span data-stu-id="da311-287">Pattern</span></span>

<span data-ttu-id="da311-288">兩個字母後尾隨六個或七位數</span><span class="sxs-lookup"><span data-stu-id="da311-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="da311-289">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-289">Checksum</span></span>

<span data-ttu-id="da311-290">否</span><span class="sxs-lookup"><span data-stu-id="da311-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-291">定義</span><span class="sxs-lookup"><span data-stu-id="da311-291">Definition</span></span>

<span data-ttu-id="da311-292">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-293">規則運算式`Regex_hungary_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-294">從關鍵字`Keywords_hungary_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-295">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-295">Keywords</span></span>

<span data-ttu-id="da311-296">| |</span><span class="sxs-lookup"><span data-stu-id="da311-296"></span></span>
|<span data-ttu-id="da311-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-298">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-298">passport number</span></span>  <br/> <span data-ttu-id="da311-299">匈牙利文護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="da311-300">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-300">passport no</span></span>  <br/> <span data-ttu-id="da311-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="da311-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="da311-302">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="da311-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="da311-303">格式</span><span class="sxs-lookup"><span data-stu-id="da311-303">Format</span></span>

<span data-ttu-id="da311-304">兩個字母或位數後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="da311-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-305">模式</span><span class="sxs-lookup"><span data-stu-id="da311-305">Pattern</span></span>

<span data-ttu-id="da311-306">兩個字母或位數後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="da311-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="da311-307">兩個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="da311-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="da311-308">七位數</span><span class="sxs-lookup"><span data-stu-id="da311-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="da311-309">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-309">Checksum</span></span>

<span data-ttu-id="da311-310">否</span><span class="sxs-lookup"><span data-stu-id="da311-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-311">定義</span><span class="sxs-lookup"><span data-stu-id="da311-311">Definition</span></span>

<span data-ttu-id="da311-312">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-313">規則運算式`Regex_ireland_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-314">從關鍵字`Keywords_ireland_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-315">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-315">Keywords</span></span>

<span data-ttu-id="da311-316">| |</span><span class="sxs-lookup"><span data-stu-id="da311-316"></span></span>
|<span data-ttu-id="da311-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-318">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-318">passport number</span></span>  <br/> <span data-ttu-id="da311-319">愛爾蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-319">irish passport number</span></span>  <br/> <span data-ttu-id="da311-320">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-320">passport no</span></span>  <br/> <span data-ttu-id="da311-321">pas</span><span class="sxs-lookup"><span data-stu-id="da311-321">pas</span></span>  <br/> <span data-ttu-id="da311-322">passport</span><span class="sxs-lookup"><span data-stu-id="da311-322">passport</span></span>  <br/> <span data-ttu-id="da311-323">passeport</span><span class="sxs-lookup"><span data-stu-id="da311-323">passeport</span></span>  <br/> <span data-ttu-id="da311-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="da311-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="da311-325">義大利</span><span class="sxs-lookup"><span data-stu-id="da311-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="da311-326">格式</span><span class="sxs-lookup"><span data-stu-id="da311-326">Format</span></span>

<span data-ttu-id="da311-327">兩個字母或位數後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="da311-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-328">模式</span><span class="sxs-lookup"><span data-stu-id="da311-328">Pattern</span></span>

<span data-ttu-id="da311-329">兩個字母或位數後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="da311-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="da311-330">兩個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="da311-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="da311-331">七位數</span><span class="sxs-lookup"><span data-stu-id="da311-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="da311-332">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-332">Checksum</span></span>

<span data-ttu-id="da311-333">不適用</span><span class="sxs-lookup"><span data-stu-id="da311-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-334">定義</span><span class="sxs-lookup"><span data-stu-id="da311-334">Definition</span></span>

<span data-ttu-id="da311-335">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-336">規則運算式`Regex_italy_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-337">從關鍵字`Keywords_italy_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-338">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-338">Keywords</span></span>

<span data-ttu-id="da311-339">| |</span><span class="sxs-lookup"><span data-stu-id="da311-339"></span></span>
|<span data-ttu-id="da311-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-341">義大利文護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-341">italian passport number</span></span>  <br/> <span data-ttu-id="da311-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="da311-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="da311-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="da311-343">passaporto</span></span>  <br/> <span data-ttu-id="da311-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="da311-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="da311-345">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-345">passport number</span></span>  <br/> <span data-ttu-id="da311-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="da311-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="da311-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="da311-347">passaporto numero</span></span>  <br/> <span data-ttu-id="da311-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="da311-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="da311-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="da311-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="da311-350">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="da311-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="da311-351">格式</span><span class="sxs-lookup"><span data-stu-id="da311-351">Format</span></span>

<span data-ttu-id="da311-352">兩個字母或位數後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="da311-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-353">模式</span><span class="sxs-lookup"><span data-stu-id="da311-353">Pattern</span></span>

<span data-ttu-id="da311-354">兩個字母或位數後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="da311-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="da311-355">兩個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="da311-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="da311-356">七位數</span><span class="sxs-lookup"><span data-stu-id="da311-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="da311-357">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-357">Checksum</span></span>

<span data-ttu-id="da311-358">否</span><span class="sxs-lookup"><span data-stu-id="da311-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-359">定義</span><span class="sxs-lookup"><span data-stu-id="da311-359">Definition</span></span>

<span data-ttu-id="da311-360">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-361">規則運算式`Regex_latvia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-362">從關鍵字`Keywords_latvia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-363">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-363">Keywords</span></span>

<span data-ttu-id="da311-364">| |</span><span class="sxs-lookup"><span data-stu-id="da311-364"></span></span>
|<span data-ttu-id="da311-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-366">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-366">passport number</span></span>  <br/> <span data-ttu-id="da311-367">拉脫維亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-367">latvian passport number</span></span>  <br/> <span data-ttu-id="da311-368">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-368">passport no</span></span>  <br/> <span data-ttu-id="da311-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="da311-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="da311-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="da311-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="da311-371">格式</span><span class="sxs-lookup"><span data-stu-id="da311-371">Format</span></span>

<span data-ttu-id="da311-372">八個個數字或字母不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="da311-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-373">模式</span><span class="sxs-lookup"><span data-stu-id="da311-373">Pattern</span></span>

<span data-ttu-id="da311-374">八個個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="da311-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="da311-375">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-375">Checksum</span></span>

<span data-ttu-id="da311-376">不適用</span><span class="sxs-lookup"><span data-stu-id="da311-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-377">定義</span><span class="sxs-lookup"><span data-stu-id="da311-377">Definition</span></span>

<span data-ttu-id="da311-378">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-379">規則運算式`Regex_lithuania_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-380">從關鍵字`Keywords_lithuania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-381">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-381">Keywords</span></span>

<span data-ttu-id="da311-382">| |</span><span class="sxs-lookup"><span data-stu-id="da311-382"></span></span>
|<span data-ttu-id="da311-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-384">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-384">passport number</span></span>  <br/> <span data-ttu-id="da311-385">lithunian 護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="da311-386">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-386">passport no</span></span>  <br/> <span data-ttu-id="da311-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="da311-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="da311-388">盧森堡</span><span class="sxs-lookup"><span data-stu-id="da311-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="da311-389">格式</span><span class="sxs-lookup"><span data-stu-id="da311-389">Format</span></span>

<span data-ttu-id="da311-390">八個個數字或字母不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="da311-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-391">模式</span><span class="sxs-lookup"><span data-stu-id="da311-391">Pattern</span></span>

<span data-ttu-id="da311-392">八個個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="da311-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="da311-393">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-393">Checksum</span></span>

<span data-ttu-id="da311-394">否</span><span class="sxs-lookup"><span data-stu-id="da311-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-395">定義</span><span class="sxs-lookup"><span data-stu-id="da311-395">Definition</span></span>

<span data-ttu-id="da311-396">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-397">規則運算式`Regex_nation_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-398">從關鍵字`Keywords_nation_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-399">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-399">Keywords</span></span>

<span data-ttu-id="da311-400">| |</span><span class="sxs-lookup"><span data-stu-id="da311-400"></span></span>
|<span data-ttu-id="da311-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-402">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-402">passport number</span></span>  <br/> <span data-ttu-id="da311-403">拉脫維亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-403">latvian passport number</span></span>  <br/> <span data-ttu-id="da311-404">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-404">passport no</span></span>  <br/> <span data-ttu-id="da311-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="da311-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="da311-406">馬爾他</span><span class="sxs-lookup"><span data-stu-id="da311-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="da311-407">格式</span><span class="sxs-lookup"><span data-stu-id="da311-407">Format</span></span>

<span data-ttu-id="da311-408">不含空格或分隔符號七位數</span><span class="sxs-lookup"><span data-stu-id="da311-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-409">模式</span><span class="sxs-lookup"><span data-stu-id="da311-409">Pattern</span></span>

 <span data-ttu-id="da311-410">七位數</span><span class="sxs-lookup"><span data-stu-id="da311-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="da311-411">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-411">Checksum</span></span>

<span data-ttu-id="da311-412">否</span><span class="sxs-lookup"><span data-stu-id="da311-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-413">定義</span><span class="sxs-lookup"><span data-stu-id="da311-413">Definition</span></span>

<span data-ttu-id="da311-414">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-415">規則運算式`Regex_malta_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-416">從關鍵字`Keywords_malta_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-417">Keywords</span></span>

<span data-ttu-id="da311-418">| |</span><span class="sxs-lookup"><span data-stu-id="da311-418"></span></span>
|<span data-ttu-id="da311-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-420">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-420">passport number</span></span>  <br/> <span data-ttu-id="da311-421">馬爾他護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-421">maltese passport number</span></span>  <br/> <span data-ttu-id="da311-422">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-422">passport no</span></span>  <br/> <span data-ttu-id="da311-423">numru tal passaport</span><span class="sxs-lookup"><span data-stu-id="da311-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="da311-424">荷蘭</span><span class="sxs-lookup"><span data-stu-id="da311-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="da311-425">格式</span><span class="sxs-lookup"><span data-stu-id="da311-425">Format</span></span>

<span data-ttu-id="da311-426">九個字母或不含空格或分隔符號的數字</span><span class="sxs-lookup"><span data-stu-id="da311-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-427">模式</span><span class="sxs-lookup"><span data-stu-id="da311-427">Pattern</span></span>

<span data-ttu-id="da311-428">九個字母或四位數</span><span class="sxs-lookup"><span data-stu-id="da311-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="da311-429">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-429">Checksum</span></span>

<span data-ttu-id="da311-430">不適用</span><span class="sxs-lookup"><span data-stu-id="da311-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-431">定義</span><span class="sxs-lookup"><span data-stu-id="da311-431">Definition</span></span>

<span data-ttu-id="da311-432">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-433">規則運算式`Regex_netherlands_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-434">從關鍵字`Keywords_netherlands_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-435">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-435">Keywords</span></span>

<span data-ttu-id="da311-436">| |</span><span class="sxs-lookup"><span data-stu-id="da311-436"></span></span>
|<span data-ttu-id="da311-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-438">荷蘭文護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-438">dutch passport number</span></span>  <br/> <span data-ttu-id="da311-439">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-439">passport number</span></span>  <br/> <span data-ttu-id="da311-440">荷蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="da311-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="da311-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="da311-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="da311-442">paspoort</span></span>  <br/> <span data-ttu-id="da311-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="da311-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="da311-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="da311-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="da311-445">波蘭</span><span class="sxs-lookup"><span data-stu-id="da311-445">Poland</span></span>

<span data-ttu-id="da311-446">如需詳細資訊，請參閱 「 波蘭護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="da311-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="da311-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="da311-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="da311-448">格式</span><span class="sxs-lookup"><span data-stu-id="da311-448">Format</span></span>

<span data-ttu-id="da311-449">一個字母後尾隨六位數，代表不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="da311-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-450">模式</span><span class="sxs-lookup"><span data-stu-id="da311-450">Pattern</span></span>

<span data-ttu-id="da311-451">一個字母後尾隨六位數：</span><span class="sxs-lookup"><span data-stu-id="da311-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="da311-452">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="da311-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="da311-453">六位數</span><span class="sxs-lookup"><span data-stu-id="da311-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="da311-454">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-454">Checksum</span></span>

<span data-ttu-id="da311-455">否</span><span class="sxs-lookup"><span data-stu-id="da311-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-456">定義</span><span class="sxs-lookup"><span data-stu-id="da311-456">Definition</span></span>

<span data-ttu-id="da311-457">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-458">規則運算式`Regex_portugal_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-459">從關鍵字`Keywords_portugal_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-460">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-460">Keywords</span></span>

<span data-ttu-id="da311-461">| |</span><span class="sxs-lookup"><span data-stu-id="da311-461"></span></span>
|<span data-ttu-id="da311-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-463">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-463">passport number</span></span>  <br/> <span data-ttu-id="da311-464">葡萄牙文護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="da311-465">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-465">passport no</span></span>  <br/> <span data-ttu-id="da311-466">número 不要 passaporte</span><span class="sxs-lookup"><span data-stu-id="da311-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="da311-467">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="da311-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="da311-468">格式</span><span class="sxs-lookup"><span data-stu-id="da311-468">Format</span></span>

<span data-ttu-id="da311-469">不含空格，並讓分隔字元的八個或九位數</span><span class="sxs-lookup"><span data-stu-id="da311-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-470">模式</span><span class="sxs-lookup"><span data-stu-id="da311-470">Pattern</span></span>

<span data-ttu-id="da311-471">八個或九位數</span><span class="sxs-lookup"><span data-stu-id="da311-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="da311-472">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-472">Checksum</span></span>

<span data-ttu-id="da311-473">否</span><span class="sxs-lookup"><span data-stu-id="da311-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-474">定義</span><span class="sxs-lookup"><span data-stu-id="da311-474">Definition</span></span>

<span data-ttu-id="da311-475">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-476">規則運算式`Regex_romania_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-477">從關鍵字`Keywords_romania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-478">Keywords</span></span>

<span data-ttu-id="da311-479">| |</span><span class="sxs-lookup"><span data-stu-id="da311-479"></span></span>
|<span data-ttu-id="da311-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-481">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-481">passport number</span></span>  <br/> <span data-ttu-id="da311-482">羅馬尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-482">romanian passport number</span></span>  <br/> <span data-ttu-id="da311-483">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-483">passport no</span></span>  <br/> <span data-ttu-id="da311-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="da311-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="da311-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="da311-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="da311-486">格式</span><span class="sxs-lookup"><span data-stu-id="da311-486">Format</span></span>

<span data-ttu-id="da311-487">一個數字或字母後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="da311-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-488">模式</span><span class="sxs-lookup"><span data-stu-id="da311-488">Pattern</span></span>

<span data-ttu-id="da311-489">一個數字或字母 （不區分大小寫） 後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="da311-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="da311-490">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-490">Checksum</span></span>

<span data-ttu-id="da311-491">否</span><span class="sxs-lookup"><span data-stu-id="da311-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-492">定義</span><span class="sxs-lookup"><span data-stu-id="da311-492">Definition</span></span>

<span data-ttu-id="da311-493">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-494">規則運算式`Regex_slovakia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-495">從關鍵字`Keywords_slovakia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-496">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-496">Keywords</span></span>

<span data-ttu-id="da311-497">| |</span><span class="sxs-lookup"><span data-stu-id="da311-497"></span></span>
|<span data-ttu-id="da311-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-499">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-499">passport number</span></span>  <br/> <span data-ttu-id="da311-500">斯洛伐克護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="da311-501">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-501">passport no</span></span>  <br/> <span data-ttu-id="da311-502">Číslo pasu</span><span class="sxs-lookup"><span data-stu-id="da311-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="da311-503">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="da311-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="da311-504">格式</span><span class="sxs-lookup"><span data-stu-id="da311-504">Format</span></span>

<span data-ttu-id="da311-505">兩個字母後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="da311-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-506">模式</span><span class="sxs-lookup"><span data-stu-id="da311-506">Pattern</span></span>

<span data-ttu-id="da311-507">兩個字母後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="da311-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="da311-508">字母"P"</span><span class="sxs-lookup"><span data-stu-id="da311-508">The letter "P"</span></span>
    
- <span data-ttu-id="da311-509">一個大寫字母</span><span class="sxs-lookup"><span data-stu-id="da311-509">One uppercase letter</span></span>
    
- <span data-ttu-id="da311-510">七位數</span><span class="sxs-lookup"><span data-stu-id="da311-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="da311-511">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-511">Checksum</span></span>

<span data-ttu-id="da311-512">否</span><span class="sxs-lookup"><span data-stu-id="da311-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-513">定義</span><span class="sxs-lookup"><span data-stu-id="da311-513">Definition</span></span>

<span data-ttu-id="da311-514">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-515">規則運算式`Regex_slovenia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-516">從關鍵字`Keywords_slovenia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-517">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-517">Keywords</span></span>

<span data-ttu-id="da311-518">| |</span><span class="sxs-lookup"><span data-stu-id="da311-518"></span></span>
|<span data-ttu-id="da311-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-520">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-520">passport number</span></span>  <br/> <span data-ttu-id="da311-521">斯洛維尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="da311-522">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-522">passport no</span></span>  <br/> <span data-ttu-id="da311-523">Številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="da311-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="da311-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="da311-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="da311-525">格式</span><span class="sxs-lookup"><span data-stu-id="da311-525">Format</span></span>

<span data-ttu-id="da311-526">八個或九個字元組合的字母和數字不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="da311-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="da311-527">模式</span><span class="sxs-lookup"><span data-stu-id="da311-527">Pattern</span></span>

<span data-ttu-id="da311-528">字母和數字 8 或九個字元組合：</span><span class="sxs-lookup"><span data-stu-id="da311-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="da311-529">兩個數字或字母</span><span class="sxs-lookup"><span data-stu-id="da311-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="da311-530">一個數字或字母 （選用）</span><span class="sxs-lookup"><span data-stu-id="da311-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="da311-531">六位數</span><span class="sxs-lookup"><span data-stu-id="da311-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="da311-532">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="da311-532">Checksum</span></span>

<span data-ttu-id="da311-533">不適用</span><span class="sxs-lookup"><span data-stu-id="da311-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="da311-534">定義</span><span class="sxs-lookup"><span data-stu-id="da311-534">Definition</span></span>

<span data-ttu-id="da311-535">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="da311-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="da311-536">規則運算式`Regex_spain_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="da311-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="da311-537">從關鍵字`Keywords_spain_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="da311-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="da311-538">關鍵字</span><span class="sxs-lookup"><span data-stu-id="da311-538">Keywords</span></span>

<span data-ttu-id="da311-539">| |</span><span class="sxs-lookup"><span data-stu-id="da311-539"></span></span>
|<span data-ttu-id="da311-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="da311-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="da311-541">passport</span><span class="sxs-lookup"><span data-stu-id="da311-541">passport</span></span>  <br/> <span data-ttu-id="da311-542">西班牙 passport</span><span class="sxs-lookup"><span data-stu-id="da311-542">spain passport</span></span>  <br/> <span data-ttu-id="da311-543">passport 活頁簿</span><span class="sxs-lookup"><span data-stu-id="da311-543">passport book</span></span>  <br/> <span data-ttu-id="da311-544">護照號碼</span><span class="sxs-lookup"><span data-stu-id="da311-544">passport number</span></span>  <br/> <span data-ttu-id="da311-545">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="da311-545">passport no</span></span>  <br/> <span data-ttu-id="da311-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="da311-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="da311-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="da311-547">número pasaporte</span></span>  <br/> <span data-ttu-id="da311-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="da311-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="da311-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="da311-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="da311-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="da311-550">Sweden</span></span>

<span data-ttu-id="da311-551">如需詳細資訊，請參閱 「 瑞典護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="da311-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="da311-552">英國</span><span class="sxs-lookup"><span data-stu-id="da311-552">UK</span></span>

<span data-ttu-id="da311-553">如需詳細資訊，請參閱 「 美國/英國的區段</span><span class="sxs-lookup"><span data-stu-id="da311-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="da311-554">護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="da311-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="da311-555">另請參閱</span><span class="sxs-lookup"><span data-stu-id="da311-555">See also</span></span>

[<span data-ttu-id="da311-556">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="da311-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

