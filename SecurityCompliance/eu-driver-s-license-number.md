---
title: 歐盟駕照編號
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: c3923cd3-ec84-435f-bf41-cadc37996a4b
description: 本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟駕照編號敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
ms.openlocfilehash: 065684249f9766d567c63e6b8170d36f56692e45
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526716"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="59260-104">歐盟駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-104">EU Driver's License Number</span></span>

<span data-ttu-id="59260-p102">本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟駕照編號敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。</span><span class="sxs-lookup"><span data-stu-id="59260-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="59260-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="59260-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="59260-108">格式</span><span class="sxs-lookup"><span data-stu-id="59260-108">Format</span></span>

<span data-ttu-id="59260-109">不含空格和分隔字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="59260-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-110">模式</span><span class="sxs-lookup"><span data-stu-id="59260-110">Pattern</span></span>

<span data-ttu-id="59260-111">八位數</span><span class="sxs-lookup"><span data-stu-id="59260-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="59260-112">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-112">Checksum</span></span>

<span data-ttu-id="59260-113">否</span><span class="sxs-lookup"><span data-stu-id="59260-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-114">定義</span><span class="sxs-lookup"><span data-stu-id="59260-114">Definition</span></span>

<span data-ttu-id="59260-115">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-116">規則運算式`Regex_austria_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-117">從關鍵字`Keywords_austria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="59260-118">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-118">Keywords</span></span>

<span data-ttu-id="59260-119">| |</span><span class="sxs-lookup"><span data-stu-id="59260-119"></span></span>
|<span data-ttu-id="59260-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-121">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-121">dl#</span></span>  <br/> <span data-ttu-id="59260-122">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-122">driver license</span></span>  <br/> <span data-ttu-id="59260-123">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-123">driver license number</span></span>  <br/> <span data-ttu-id="59260-124">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-124">driver licence</span></span>  <br/> <span data-ttu-id="59260-125">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-125">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-126">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-126">drivers license</span></span>  <br/> <span data-ttu-id="59260-127">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="59260-127">driver's licence</span></span>  <br/> <span data-ttu-id="59260-128">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-128">driver's license</span></span>  <br/> <span data-ttu-id="59260-129">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-129">driver's license number</span></span>  <br/> <span data-ttu-id="59260-130">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="59260-131">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-131">driving license number</span></span>  <br/> <span data-ttu-id="59260-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-132">dlno#</span></span>  <br/> <span data-ttu-id="59260-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="59260-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="59260-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="59260-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="59260-135">比利時</span><span class="sxs-lookup"><span data-stu-id="59260-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="59260-136">格式</span><span class="sxs-lookup"><span data-stu-id="59260-136">Format</span></span>

<span data-ttu-id="59260-137">不含空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="59260-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-138">模式</span><span class="sxs-lookup"><span data-stu-id="59260-138">Pattern</span></span>

<span data-ttu-id="59260-139">10 位數</span><span class="sxs-lookup"><span data-stu-id="59260-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="59260-140">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-140">Checksum</span></span>

<span data-ttu-id="59260-141">否</span><span class="sxs-lookup"><span data-stu-id="59260-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-142">定義</span><span class="sxs-lookup"><span data-stu-id="59260-142">Definition</span></span>

<span data-ttu-id="59260-143">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-144">規則運算式`Regex_belgium_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-145">從關鍵字`Keywords_belgium_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="59260-146">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-146">Keywords</span></span>

<span data-ttu-id="59260-147">| |</span><span class="sxs-lookup"><span data-stu-id="59260-147"></span></span>
|<span data-ttu-id="59260-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-149">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-149">dl#</span></span>  <br/> <span data-ttu-id="59260-150">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-150">driver license</span></span>  <br/> <span data-ttu-id="59260-151">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-151">driver license number</span></span>  <br/> <span data-ttu-id="59260-152">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-152">driver licence</span></span>  <br/> <span data-ttu-id="59260-153">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-153">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-154">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-154">drivers license</span></span>  <br/> <span data-ttu-id="59260-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-155">drivers licence</span></span>  <br/> <span data-ttu-id="59260-156">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-156">driver's license</span></span>  <br/> <span data-ttu-id="59260-157">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-157">driver's license number</span></span>  <br/> <span data-ttu-id="59260-158">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-158">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-159">dlno#</span></span>  <br/> <span data-ttu-id="59260-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="59260-160">rijbewijs</span></span>  <br/> <span data-ttu-id="59260-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="59260-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="59260-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="59260-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="59260-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="59260-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="59260-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="59260-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="59260-165">führerschein 編號</span><span class="sxs-lookup"><span data-stu-id="59260-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="59260-166">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="59260-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="59260-167">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="59260-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="59260-168">保加利亞</span><span class="sxs-lookup"><span data-stu-id="59260-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="59260-169">格式</span><span class="sxs-lookup"><span data-stu-id="59260-169">Format</span></span>

<span data-ttu-id="59260-170">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="59260-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-171">模式</span><span class="sxs-lookup"><span data-stu-id="59260-171">Pattern</span></span>

<span data-ttu-id="59260-172">九位數</span><span class="sxs-lookup"><span data-stu-id="59260-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="59260-173">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-173">Checksum</span></span>

<span data-ttu-id="59260-174">否</span><span class="sxs-lookup"><span data-stu-id="59260-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-175">定義</span><span class="sxs-lookup"><span data-stu-id="59260-175">Definition</span></span>

<span data-ttu-id="59260-176">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-177">規則運算式`Regex_bulgaria_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-178">從關鍵字`Keywords_bulgaria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="59260-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-179">Keywords</span></span>

<span data-ttu-id="59260-180">| |</span><span class="sxs-lookup"><span data-stu-id="59260-180"></span></span>
|<span data-ttu-id="59260-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-182">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-182">dl#</span></span>  <br/> <span data-ttu-id="59260-183">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-183">driver license</span></span>  <br/> <span data-ttu-id="59260-184">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-184">driver license number</span></span>  <br/> <span data-ttu-id="59260-185">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-185">driver licence</span></span>  <br/> <span data-ttu-id="59260-186">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-186">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-187">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-187">drivers license</span></span>  <br/> <span data-ttu-id="59260-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-188">drivers licence</span></span>  <br/> <span data-ttu-id="59260-189">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-189">driver's license</span></span>  <br/> <span data-ttu-id="59260-190">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-190">driver's license number</span></span>  <br/> <span data-ttu-id="59260-191">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-191">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-192">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-192">driving license number</span></span>  <br/> <span data-ttu-id="59260-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-193">dlno#</span></span>  <br/> <span data-ttu-id="59260-194">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МПС</span><span class="sxs-lookup"><span data-stu-id="59260-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="59260-195">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО</span><span class="sxs-lookup"><span data-stu-id="59260-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="59260-196">СУМПС</span><span class="sxs-lookup"><span data-stu-id="59260-196">сумпс</span></span>  <br/> <span data-ttu-id="59260-197">ШОФЬОРСКА КНИЖКА</span><span class="sxs-lookup"><span data-stu-id="59260-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="59260-198">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="59260-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="59260-199">格式</span><span class="sxs-lookup"><span data-stu-id="59260-199">Format</span></span>

<span data-ttu-id="59260-200">不含空格和分隔字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="59260-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-201">模式</span><span class="sxs-lookup"><span data-stu-id="59260-201">Pattern</span></span>

<span data-ttu-id="59260-202">八位數</span><span class="sxs-lookup"><span data-stu-id="59260-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="59260-203">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-203">Checksum</span></span>

<span data-ttu-id="59260-204">否</span><span class="sxs-lookup"><span data-stu-id="59260-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-205">定義</span><span class="sxs-lookup"><span data-stu-id="59260-205">Definition</span></span>

<span data-ttu-id="59260-206">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-207">規則運算式`Regex_croatia_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-208">從關鍵字`Keywords_croatia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="59260-209">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-209">Keywords</span></span>

<span data-ttu-id="59260-210">| |</span><span class="sxs-lookup"><span data-stu-id="59260-210"></span></span>
|<span data-ttu-id="59260-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-212">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-212">dl#</span></span>  <br/> <span data-ttu-id="59260-213">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-213">driver license</span></span>  <br/> <span data-ttu-id="59260-214">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-214">driver license number</span></span>  <br/> <span data-ttu-id="59260-215">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-215">driver licence</span></span>  <br/> <span data-ttu-id="59260-216">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-216">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-217">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-217">drivers license</span></span>  <br/> <span data-ttu-id="59260-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-218">drivers licence</span></span>  <br/> <span data-ttu-id="59260-219">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-219">driver's license</span></span>  <br/> <span data-ttu-id="59260-220">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-220">driver's license number</span></span>  <br/> <span data-ttu-id="59260-221">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-221">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-222">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-222">driving license number</span></span>  <br/> <span data-ttu-id="59260-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-223">dlno#</span></span>  <br/> <span data-ttu-id="59260-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="59260-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="59260-225">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="59260-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="59260-226">格式</span><span class="sxs-lookup"><span data-stu-id="59260-226">Format</span></span>

<span data-ttu-id="59260-227">12 的數字不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="59260-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-228">模式</span><span class="sxs-lookup"><span data-stu-id="59260-228">Pattern</span></span>

<span data-ttu-id="59260-229">12 位數</span><span class="sxs-lookup"><span data-stu-id="59260-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="59260-230">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-230">Checksum</span></span>

<span data-ttu-id="59260-231">否</span><span class="sxs-lookup"><span data-stu-id="59260-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-232">定義</span><span class="sxs-lookup"><span data-stu-id="59260-232">Definition</span></span>

<span data-ttu-id="59260-233">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-234">規則運算式`Regex_cyprus_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-235">從關鍵字`Keywords_cyprus_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-236">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-236">Keywords</span></span>

<span data-ttu-id="59260-237">| |</span><span class="sxs-lookup"><span data-stu-id="59260-237"></span></span>
|<span data-ttu-id="59260-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-239">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-239">dl#</span></span>  <br/> <span data-ttu-id="59260-240">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-240">driver license</span></span>  <br/> <span data-ttu-id="59260-241">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-241">driver license number</span></span>  <br/> <span data-ttu-id="59260-242">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-242">driver licence</span></span>  <br/> <span data-ttu-id="59260-243">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-243">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-244">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-244">drivers license</span></span>  <br/> <span data-ttu-id="59260-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-245">drivers licence</span></span>  <br/> <span data-ttu-id="59260-246">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-246">driver's license number</span></span>  <br/> <span data-ttu-id="59260-247">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-247">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-248">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-248">driving license number</span></span>  <br/> <span data-ttu-id="59260-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-249">dlno#</span></span>  <br/> <span data-ttu-id="59260-250">ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="59260-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="59260-251">捷克</span><span class="sxs-lookup"><span data-stu-id="59260-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="59260-252">格式</span><span class="sxs-lookup"><span data-stu-id="59260-252">Format</span></span>

<span data-ttu-id="59260-253">兩個字母後面接著 6 位數</span><span class="sxs-lookup"><span data-stu-id="59260-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-254">模式</span><span class="sxs-lookup"><span data-stu-id="59260-254">Pattern</span></span>

<span data-ttu-id="59260-255">八個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="59260-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="59260-256">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="59260-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="59260-257">一個空格 (選用)</span><span class="sxs-lookup"><span data-stu-id="59260-257">A space (optional)</span></span>
    
- <span data-ttu-id="59260-258">六位數</span><span class="sxs-lookup"><span data-stu-id="59260-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="59260-259">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-259">Checksum</span></span>

<span data-ttu-id="59260-260">否</span><span class="sxs-lookup"><span data-stu-id="59260-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-261">定義</span><span class="sxs-lookup"><span data-stu-id="59260-261">Definition</span></span>

<span data-ttu-id="59260-262">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-263">規則運算式`Regex_czech_republic_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-264">從關鍵字`Keywords_czech_republic_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="59260-265">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-265">Keywords</span></span>

<span data-ttu-id="59260-266">| |</span><span class="sxs-lookup"><span data-stu-id="59260-266"></span></span>
|<span data-ttu-id="59260-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-268">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-268">dl#</span></span>  <br/> <span data-ttu-id="59260-269">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-269">driver license</span></span>  <br/> <span data-ttu-id="59260-270">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-270">driver license number</span></span>  <br/> <span data-ttu-id="59260-271">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-271">driver licence</span></span>  <br/> <span data-ttu-id="59260-272">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-272">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-273">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-273">drivers license</span></span>  <br/> <span data-ttu-id="59260-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-274">drivers licence</span></span>  <br/> <span data-ttu-id="59260-275">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-275">driver's license</span></span>  <br/> <span data-ttu-id="59260-276">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-276">driver's license number</span></span>  <br/> <span data-ttu-id="59260-277">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-277">driver's license number</span></span>  <br/> <span data-ttu-id="59260-278">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-278">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-279">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-279">driving license number</span></span>  <br/> <span data-ttu-id="59260-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-280">dlno#</span></span>  <br/> <span data-ttu-id="59260-281">Řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="59260-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="59260-282">丹麥</span><span class="sxs-lookup"><span data-stu-id="59260-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="59260-283">格式</span><span class="sxs-lookup"><span data-stu-id="59260-283">Format</span></span>

<span data-ttu-id="59260-284">不含空格和分隔字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="59260-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-285">模式</span><span class="sxs-lookup"><span data-stu-id="59260-285">Pattern</span></span>

<span data-ttu-id="59260-286">八位數</span><span class="sxs-lookup"><span data-stu-id="59260-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="59260-287">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-287">Checksum</span></span>

<span data-ttu-id="59260-288">是</span><span class="sxs-lookup"><span data-stu-id="59260-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-289">定義</span><span class="sxs-lookup"><span data-stu-id="59260-289">Definition</span></span>

<span data-ttu-id="59260-290">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-291">規則運算式`Regex_denmark_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-292">從關鍵字`Keywords_denmark_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="59260-293">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-293">Keywords</span></span>

<span data-ttu-id="59260-294">| |</span><span class="sxs-lookup"><span data-stu-id="59260-294"></span></span>
|<span data-ttu-id="59260-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-296">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-296">dl#</span></span>  <br/> <span data-ttu-id="59260-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-297">driver license</span></span>  <br/> <span data-ttu-id="59260-298">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-298">driver license number</span></span>  <br/> <span data-ttu-id="59260-299">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-299">driver licence</span></span>  <br/> <span data-ttu-id="59260-300">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-300">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-301">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-301">drivers license</span></span>  <br/> <span data-ttu-id="59260-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-302">drivers licence</span></span>  <br/> <span data-ttu-id="59260-303">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-303">driver's license</span></span>  <br/> <span data-ttu-id="59260-304">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-304">driver's license number</span></span>  <br/> <span data-ttu-id="59260-305">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-305">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-306">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-306">driving license number</span></span>  <br/> <span data-ttu-id="59260-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-307">dlno#</span></span>  <br/> <span data-ttu-id="59260-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="59260-308">kørekort</span></span>  <br/> <span data-ttu-id="59260-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="59260-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="59260-310">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="59260-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="59260-311">格式</span><span class="sxs-lookup"><span data-stu-id="59260-311">Format</span></span>

<span data-ttu-id="59260-312">兩個字母後面接著 6 位數</span><span class="sxs-lookup"><span data-stu-id="59260-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-313">模式</span><span class="sxs-lookup"><span data-stu-id="59260-313">Pattern</span></span>

<span data-ttu-id="59260-314">兩個字母和 6 位數：</span><span class="sxs-lookup"><span data-stu-id="59260-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="59260-315">字母"ET"（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="59260-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="59260-316">六位數</span><span class="sxs-lookup"><span data-stu-id="59260-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="59260-317">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-317">Checksum</span></span>

<span data-ttu-id="59260-318">否</span><span class="sxs-lookup"><span data-stu-id="59260-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-319">定義</span><span class="sxs-lookup"><span data-stu-id="59260-319">Definition</span></span>

<span data-ttu-id="59260-320">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-321">規則運算式`Regex_estonia_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-322">從關鍵字`Keywords_estonia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-323">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-323">Keywords</span></span>

<span data-ttu-id="59260-324">| |</span><span class="sxs-lookup"><span data-stu-id="59260-324"></span></span>
|<span data-ttu-id="59260-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-326">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-326">dl#</span></span>  <br/> <span data-ttu-id="59260-327">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-327">driver license</span></span>  <br/> <span data-ttu-id="59260-328">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-328">driver license number</span></span>  <br/> <span data-ttu-id="59260-329">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-329">driver license number</span></span>  <br/> <span data-ttu-id="59260-330">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-330">driver licence</span></span>  <br/> <span data-ttu-id="59260-331">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-331">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-332">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-332">drivers license</span></span>  <br/> <span data-ttu-id="59260-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-333">drivers licence</span></span>  <br/> <span data-ttu-id="59260-334">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-334">driver's license</span></span>  <br/> <span data-ttu-id="59260-335">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-335">driver's license number</span></span>  <br/> <span data-ttu-id="59260-336">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-336">driving license number</span></span>  <br/> <span data-ttu-id="59260-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-337">dlno#</span></span>  <br/> <span data-ttu-id="59260-338">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="59260-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="59260-339">芬蘭</span><span class="sxs-lookup"><span data-stu-id="59260-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="59260-340">格式</span><span class="sxs-lookup"><span data-stu-id="59260-340">Format</span></span>

<span data-ttu-id="59260-341">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="59260-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-342">模式</span><span class="sxs-lookup"><span data-stu-id="59260-342">Pattern</span></span>

<span data-ttu-id="59260-343">包含連字號的數字 10：</span><span class="sxs-lookup"><span data-stu-id="59260-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="59260-344">六位數</span><span class="sxs-lookup"><span data-stu-id="59260-344">Six digits</span></span> 
    
- <span data-ttu-id="59260-345">一個連字號</span><span class="sxs-lookup"><span data-stu-id="59260-345">A hyphen</span></span>
    
-  <span data-ttu-id="59260-346">四位數</span><span class="sxs-lookup"><span data-stu-id="59260-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="59260-347">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-347">Checksum</span></span>

<span data-ttu-id="59260-348">否</span><span class="sxs-lookup"><span data-stu-id="59260-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-349">定義</span><span class="sxs-lookup"><span data-stu-id="59260-349">Definition</span></span>

<span data-ttu-id="59260-350">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-351">規則運算式`Regex_finland_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-352">從關鍵字`Keywords_finland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-353">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-353">Keywords</span></span>

<span data-ttu-id="59260-354">| |</span><span class="sxs-lookup"><span data-stu-id="59260-354"></span></span>
|<span data-ttu-id="59260-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-356">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-356">dl#</span></span>  <br/> <span data-ttu-id="59260-357">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-357">driver license</span></span>  <br/> <span data-ttu-id="59260-358">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-358">driver license number</span></span>  <br/> <span data-ttu-id="59260-359">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-359">driver licence</span></span>  <br/> <span data-ttu-id="59260-360">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-360">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-361">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-361">drivers license</span></span>  <br/> <span data-ttu-id="59260-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-362">drivers licence</span></span>  <br/> <span data-ttu-id="59260-363">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-363">driver's license</span></span>  <br/> <span data-ttu-id="59260-364">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-364">driver's license number</span></span>  <br/> <span data-ttu-id="59260-365">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-365">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-366">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-366">driving license number</span></span>  <br/> <span data-ttu-id="59260-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-367">dlno#</span></span>  <br/> <span data-ttu-id="59260-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="59260-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="59260-369">法國</span><span class="sxs-lookup"><span data-stu-id="59260-369">France</span></span>

<span data-ttu-id="59260-370">如需詳細資訊，請參閱節"法國駕照編號 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="59260-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="59260-371">德國</span><span class="sxs-lookup"><span data-stu-id="59260-371">Germany</span></span>

<span data-ttu-id="59260-372">如需詳細資訊，請參閱節"德國駕照編號 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="59260-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="59260-373">希臘</span><span class="sxs-lookup"><span data-stu-id="59260-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="59260-374">格式</span><span class="sxs-lookup"><span data-stu-id="59260-374">Format</span></span>

<span data-ttu-id="59260-375">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="59260-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-376">模式</span><span class="sxs-lookup"><span data-stu-id="59260-376">Pattern</span></span>

 <span data-ttu-id="59260-377">九位數</span><span class="sxs-lookup"><span data-stu-id="59260-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="59260-378">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-378">Checksum</span></span>

<span data-ttu-id="59260-379">否</span><span class="sxs-lookup"><span data-stu-id="59260-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-380">定義</span><span class="sxs-lookup"><span data-stu-id="59260-380">Definition</span></span>

<span data-ttu-id="59260-381">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-382">規則運算式`Regex_greece_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-383">從關鍵字`Keywords_greece_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-384">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-384">Keywords</span></span>

<span data-ttu-id="59260-385">| |</span><span class="sxs-lookup"><span data-stu-id="59260-385"></span></span>
|<span data-ttu-id="59260-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="59260-387">dlL#</span></span>  <br/> <span data-ttu-id="59260-388">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-388">driver license</span></span>  <br/> <span data-ttu-id="59260-389">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-389">driver license number</span></span>  <br/> <span data-ttu-id="59260-390">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-390">driver licence</span></span>  <br/> <span data-ttu-id="59260-391">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-391">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-392">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-392">drivers license</span></span>  <br/> <span data-ttu-id="59260-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-393">drivers licence</span></span>  <br/> <span data-ttu-id="59260-394">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-394">driver's license</span></span>  <br/> <span data-ttu-id="59260-395">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-395">driver's license number</span></span>  <br/> <span data-ttu-id="59260-396">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-396">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-397">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-397">driving license number</span></span>  <br/> <span data-ttu-id="59260-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-398">dlno#</span></span>  <br/> <span data-ttu-id="59260-399">ΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="59260-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="59260-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="59260-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="59260-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="59260-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="59260-402">格式</span><span class="sxs-lookup"><span data-stu-id="59260-402">Format</span></span>

<span data-ttu-id="59260-403">兩個字母後面接著 6 位數</span><span class="sxs-lookup"><span data-stu-id="59260-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-404">模式</span><span class="sxs-lookup"><span data-stu-id="59260-404">Pattern</span></span>

<span data-ttu-id="59260-405">兩個字母和 6 位數：</span><span class="sxs-lookup"><span data-stu-id="59260-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="59260-406">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="59260-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="59260-407">六位數</span><span class="sxs-lookup"><span data-stu-id="59260-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="59260-408">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-408">Checksum</span></span>

<span data-ttu-id="59260-409">否</span><span class="sxs-lookup"><span data-stu-id="59260-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-410">定義</span><span class="sxs-lookup"><span data-stu-id="59260-410">Definition</span></span>

<span data-ttu-id="59260-411">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-412">規則運算式`Regex_hungary_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-413">從關鍵字`Keywords_hungary_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-414">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-414">Keywords</span></span>

<span data-ttu-id="59260-415">| |</span><span class="sxs-lookup"><span data-stu-id="59260-415"></span></span>
|<span data-ttu-id="59260-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-417">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-417">dl#</span></span>  <br/> <span data-ttu-id="59260-418">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-418">driver license</span></span>  <br/> <span data-ttu-id="59260-419">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-419">driver license number</span></span>  <br/> <span data-ttu-id="59260-420">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-420">driver licence</span></span>  <br/> <span data-ttu-id="59260-421">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-421">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-422">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-422">drivers license</span></span>  <br/> <span data-ttu-id="59260-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-423">drivers licence</span></span>  <br/> <span data-ttu-id="59260-424">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-424">driver's license</span></span>  <br/> <span data-ttu-id="59260-425">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-425">driver's license number</span></span>  <br/> <span data-ttu-id="59260-426">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-426">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-427">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-427">driving license number</span></span>  <br/> <span data-ttu-id="59260-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-428">dlno#</span></span>  <br/> <span data-ttu-id="59260-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="59260-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="59260-430">Ireland</span><span class="sxs-lookup"><span data-stu-id="59260-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="59260-431">格式</span><span class="sxs-lookup"><span data-stu-id="59260-431">Format</span></span>

<span data-ttu-id="59260-432">後面接著四個字母的 6 位數</span><span class="sxs-lookup"><span data-stu-id="59260-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-433">模式</span><span class="sxs-lookup"><span data-stu-id="59260-433">Pattern</span></span>

<span data-ttu-id="59260-434">6 位數和四個字母：</span><span class="sxs-lookup"><span data-stu-id="59260-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="59260-435">六位數</span><span class="sxs-lookup"><span data-stu-id="59260-435">Six digits</span></span>
    
- <span data-ttu-id="59260-436">四個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="59260-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="59260-437">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-437">Checksum</span></span>

<span data-ttu-id="59260-438">否</span><span class="sxs-lookup"><span data-stu-id="59260-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-439">定義</span><span class="sxs-lookup"><span data-stu-id="59260-439">Definition</span></span>

<span data-ttu-id="59260-440">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-441">規則運算式`Regex_ireland_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-442">從關鍵字`Keywords_ireland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-443">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-443">Keywords</span></span>

<span data-ttu-id="59260-444">| |</span><span class="sxs-lookup"><span data-stu-id="59260-444"></span></span>
|<span data-ttu-id="59260-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-446">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-446">dl#</span></span>  <br/> <span data-ttu-id="59260-447">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-447">driver license</span></span>  <br/> <span data-ttu-id="59260-448">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-448">driver license number</span></span>  <br/> <span data-ttu-id="59260-449">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-449">driver licence</span></span>  <br/> <span data-ttu-id="59260-450">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-450">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-451">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-451">drivers license</span></span>  <br/> <span data-ttu-id="59260-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-452">drivers licence</span></span>  <br/> <span data-ttu-id="59260-453">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-453">driver's license</span></span>  <br/> <span data-ttu-id="59260-454">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-454">driver's license number</span></span>  <br/> <span data-ttu-id="59260-455">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-455">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-456">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-456">driving license number</span></span>  <br/> <span data-ttu-id="59260-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-457">dlno#</span></span>  <br/> <span data-ttu-id="59260-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="59260-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="59260-459">義大利</span><span class="sxs-lookup"><span data-stu-id="59260-459">Italy</span></span>

<span data-ttu-id="59260-460">如需詳細資訊，請參閱節"義大利駕照編號 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="59260-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="59260-461">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="59260-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="59260-462">格式</span><span class="sxs-lookup"><span data-stu-id="59260-462">Format</span></span>

<span data-ttu-id="59260-463">三個字母後面接著 6 位數</span><span class="sxs-lookup"><span data-stu-id="59260-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-464">模式</span><span class="sxs-lookup"><span data-stu-id="59260-464">Pattern</span></span>

<span data-ttu-id="59260-465">三個字母和 6 位數：</span><span class="sxs-lookup"><span data-stu-id="59260-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="59260-466">三個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="59260-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="59260-467">六位數</span><span class="sxs-lookup"><span data-stu-id="59260-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="59260-468">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-468">Checksum</span></span>

<span data-ttu-id="59260-469">否</span><span class="sxs-lookup"><span data-stu-id="59260-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-470">定義</span><span class="sxs-lookup"><span data-stu-id="59260-470">Definition</span></span>

<span data-ttu-id="59260-471">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-472">規則運算式`Regex_latvia_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-473">從關鍵字`Keywords_latvia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-474">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-474">Keywords</span></span>

<span data-ttu-id="59260-475">| |</span><span class="sxs-lookup"><span data-stu-id="59260-475"></span></span>
|<span data-ttu-id="59260-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-477">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-477">dl#</span></span>  <br/> <span data-ttu-id="59260-478">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-478">driver license</span></span>  <br/> <span data-ttu-id="59260-479">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-479">driver license number</span></span>  <br/> <span data-ttu-id="59260-480">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-480">driver licence</span></span>  <br/> <span data-ttu-id="59260-481">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-481">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-482">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-482">drivers license</span></span>  <br/> <span data-ttu-id="59260-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-483">drivers licence</span></span>  <br/> <span data-ttu-id="59260-484">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-484">driver's license</span></span>  <br/> <span data-ttu-id="59260-485">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-485">driver's license number</span></span>  <br/> <span data-ttu-id="59260-486">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-486">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-487">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-487">driving license number</span></span>  <br/> <span data-ttu-id="59260-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-488">dlno#</span></span>  <br/> <span data-ttu-id="59260-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="59260-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="59260-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="59260-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="59260-491">格式</span><span class="sxs-lookup"><span data-stu-id="59260-491">Format</span></span>

<span data-ttu-id="59260-492">不含空格和分隔字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="59260-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-493">模式</span><span class="sxs-lookup"><span data-stu-id="59260-493">Pattern</span></span>

 <span data-ttu-id="59260-494">八位數</span><span class="sxs-lookup"><span data-stu-id="59260-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="59260-495">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-495">Checksum</span></span>

<span data-ttu-id="59260-496">否</span><span class="sxs-lookup"><span data-stu-id="59260-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-497">定義</span><span class="sxs-lookup"><span data-stu-id="59260-497">Definition</span></span>

<span data-ttu-id="59260-498">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-499">規則運算式`Regex_lithuania_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-500">從關鍵字`Keywords_lithuania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-501">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-501">Keywords</span></span>

<span data-ttu-id="59260-502">| |</span><span class="sxs-lookup"><span data-stu-id="59260-502"></span></span>
|<span data-ttu-id="59260-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-504">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-504">dl#</span></span>  <br/> <span data-ttu-id="59260-505">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-505">driver license</span></span>  <br/> <span data-ttu-id="59260-506">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-506">driver license number</span></span>  <br/> <span data-ttu-id="59260-507">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-507">driver licence</span></span>  <br/> <span data-ttu-id="59260-508">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-508">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-509">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-509">drivers license</span></span>  <br/> <span data-ttu-id="59260-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-510">drivers licence</span></span>  <br/> <span data-ttu-id="59260-511">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-511">driver's license</span></span>  <br/> <span data-ttu-id="59260-512">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-512">driver's license number</span></span>  <br/> <span data-ttu-id="59260-513">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-513">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-514">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-514">driving license number</span></span>  <br/> <span data-ttu-id="59260-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-515">dlno#</span></span>  <br/> <span data-ttu-id="59260-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="59260-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="59260-517">盧森堡</span><span class="sxs-lookup"><span data-stu-id="59260-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="59260-518">格式</span><span class="sxs-lookup"><span data-stu-id="59260-518">Format</span></span>

<span data-ttu-id="59260-519">不含空格和分隔符號 6 位數</span><span class="sxs-lookup"><span data-stu-id="59260-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-520">模式</span><span class="sxs-lookup"><span data-stu-id="59260-520">Pattern</span></span>

 <span data-ttu-id="59260-521">六位數</span><span class="sxs-lookup"><span data-stu-id="59260-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="59260-522">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-522">Checksum</span></span>

<span data-ttu-id="59260-523">否</span><span class="sxs-lookup"><span data-stu-id="59260-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-524">定義</span><span class="sxs-lookup"><span data-stu-id="59260-524">Definition</span></span>

<span data-ttu-id="59260-525">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-526">規則運算式`Regex_luxemburg_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-527">從關鍵字`Keywords_luxemburg_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-528">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-528">Keywords</span></span>

<span data-ttu-id="59260-529">| |</span><span class="sxs-lookup"><span data-stu-id="59260-529"></span></span>
|<span data-ttu-id="59260-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-531">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-531">dl#</span></span>  <br/> <span data-ttu-id="59260-532">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-532">driver license</span></span>  <br/> <span data-ttu-id="59260-533">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-533">driver license number</span></span>  <br/> <span data-ttu-id="59260-534">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-534">driver licence</span></span>  <br/> <span data-ttu-id="59260-535">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-535">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-536">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-536">drivers license</span></span>  <br/> <span data-ttu-id="59260-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-537">drivers licence</span></span>  <br/> <span data-ttu-id="59260-538">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-538">driver's license</span></span>  <br/> <span data-ttu-id="59260-539">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-539">driver's license number</span></span>  <br/> <span data-ttu-id="59260-540">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-540">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-541">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-541">driving license number</span></span>  <br/> <span data-ttu-id="59260-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-542">dlno#</span></span>  <br/> <span data-ttu-id="59260-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="59260-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="59260-544">馬爾他</span><span class="sxs-lookup"><span data-stu-id="59260-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="59260-545">格式</span><span class="sxs-lookup"><span data-stu-id="59260-545">Format</span></span>

<span data-ttu-id="59260-546">兩個字元和六個中指定的型態的數字的組合</span><span class="sxs-lookup"><span data-stu-id="59260-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-547">模式</span><span class="sxs-lookup"><span data-stu-id="59260-547">Pattern</span></span>

<span data-ttu-id="59260-548">兩個字元和 6 位數的組合：</span><span class="sxs-lookup"><span data-stu-id="59260-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="59260-549">兩個字元 （數字或字母、 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="59260-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="59260-550">一個空格 (選用)</span><span class="sxs-lookup"><span data-stu-id="59260-550">A space (optional)</span></span>
    
- <span data-ttu-id="59260-551">三位數</span><span class="sxs-lookup"><span data-stu-id="59260-551">Three digits</span></span>
    
- <span data-ttu-id="59260-552">一個空格 (選用)</span><span class="sxs-lookup"><span data-stu-id="59260-552">A space (optional)</span></span>
    
- <span data-ttu-id="59260-553">三位數</span><span class="sxs-lookup"><span data-stu-id="59260-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="59260-554">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-554">Checksum</span></span>

<span data-ttu-id="59260-555">否</span><span class="sxs-lookup"><span data-stu-id="59260-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-556">定義</span><span class="sxs-lookup"><span data-stu-id="59260-556">Definition</span></span>

<span data-ttu-id="59260-557">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-558">規則運算式`Regex_malta_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-559">從關鍵字`Keywords_malta_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-560">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-560">Keywords</span></span>

<span data-ttu-id="59260-561">| |</span><span class="sxs-lookup"><span data-stu-id="59260-561"></span></span>
|<span data-ttu-id="59260-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-563">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-563">dl#</span></span>  <br/> <span data-ttu-id="59260-564">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-564">driver license</span></span>  <br/> <span data-ttu-id="59260-565">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-565">driver license number</span></span>  <br/> <span data-ttu-id="59260-566">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-566">driver licence</span></span>  <br/> <span data-ttu-id="59260-567">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-567">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-568">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-568">drivers license</span></span>  <br/> <span data-ttu-id="59260-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-569">drivers licence</span></span>  <br/> <span data-ttu-id="59260-570">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-570">driver's license</span></span>  <br/> <span data-ttu-id="59260-571">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-571">driver's license number</span></span>  <br/> <span data-ttu-id="59260-572">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-572">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-573">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-573">driving license number</span></span>  <br/> <span data-ttu-id="59260-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-574">dlno#</span></span>  <br/> <span data-ttu-id="59260-575">liċenzja tas sewqan</span><span class="sxs-lookup"><span data-stu-id="59260-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="59260-576">荷蘭</span><span class="sxs-lookup"><span data-stu-id="59260-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="59260-577">格式</span><span class="sxs-lookup"><span data-stu-id="59260-577">Format</span></span>

<span data-ttu-id="59260-578">不含空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="59260-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-579">模式</span><span class="sxs-lookup"><span data-stu-id="59260-579">Pattern</span></span>

<span data-ttu-id="59260-580">10 位數</span><span class="sxs-lookup"><span data-stu-id="59260-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="59260-581">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-581">Checksum</span></span>

<span data-ttu-id="59260-582">否</span><span class="sxs-lookup"><span data-stu-id="59260-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-583">定義</span><span class="sxs-lookup"><span data-stu-id="59260-583">Definition</span></span>

<span data-ttu-id="59260-584">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-585">規則運算式`Regex_netherlands_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-586">從關鍵字`Keywords_netherlands_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-587">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-587">Keywords</span></span>

<span data-ttu-id="59260-588">| |</span><span class="sxs-lookup"><span data-stu-id="59260-588"></span></span>
|<span data-ttu-id="59260-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-590">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-590">dl#</span></span>  <br/> <span data-ttu-id="59260-591">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-591">driver license</span></span>  <br/> <span data-ttu-id="59260-592">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-592">driver license number</span></span>  <br/> <span data-ttu-id="59260-593">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-593">driver licence</span></span>  <br/> <span data-ttu-id="59260-594">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-594">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-595">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-595">drivers license</span></span>  <br/> <span data-ttu-id="59260-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-596">drivers licence</span></span>  <br/> <span data-ttu-id="59260-597">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-597">driver's license</span></span>  <br/> <span data-ttu-id="59260-598">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-598">driver's license number</span></span>  <br/> <span data-ttu-id="59260-599">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-599">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-600">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-600">driving license number</span></span>  <br/> <span data-ttu-id="59260-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-601">dlno#</span></span>  <br/> <span data-ttu-id="59260-602">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="59260-602">permis de conduire</span></span>  <br/> <span data-ttu-id="59260-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="59260-603">rijbewijs</span></span>  <br/> <span data-ttu-id="59260-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="59260-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="59260-605">波蘭</span><span class="sxs-lookup"><span data-stu-id="59260-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="59260-606">格式</span><span class="sxs-lookup"><span data-stu-id="59260-606">Format</span></span>

<span data-ttu-id="59260-607">包含 2 正斜線的數字 14</span><span class="sxs-lookup"><span data-stu-id="59260-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-608">模式</span><span class="sxs-lookup"><span data-stu-id="59260-608">Pattern</span></span>

<span data-ttu-id="59260-609">14 的數字及 2 的正斜線：</span><span class="sxs-lookup"><span data-stu-id="59260-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="59260-610">五位數</span><span class="sxs-lookup"><span data-stu-id="59260-610">Five digits</span></span> 
    
- <span data-ttu-id="59260-611">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="59260-611">A forward slash</span></span>
    
- <span data-ttu-id="59260-612">兩位數</span><span class="sxs-lookup"><span data-stu-id="59260-612">Two digits</span></span>
    
- <span data-ttu-id="59260-613">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="59260-613">A forward slash</span></span>
    
- <span data-ttu-id="59260-614">七位數</span><span class="sxs-lookup"><span data-stu-id="59260-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="59260-615">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-615">Checksum</span></span>

<span data-ttu-id="59260-616">否</span><span class="sxs-lookup"><span data-stu-id="59260-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-617">定義</span><span class="sxs-lookup"><span data-stu-id="59260-617">Definition</span></span>

<span data-ttu-id="59260-618">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-619">規則運算式`Regex_poland_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-620">從關鍵字`Keywords_poland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-621">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-621">Keywords</span></span>

<span data-ttu-id="59260-622">| |</span><span class="sxs-lookup"><span data-stu-id="59260-622"></span></span>
|<span data-ttu-id="59260-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-624">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-624">dl#</span></span>  <br/> <span data-ttu-id="59260-625">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-625">driver license</span></span>  <br/> <span data-ttu-id="59260-626">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-626">driver license number</span></span>  <br/> <span data-ttu-id="59260-627">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-627">driver licence</span></span>  <br/> <span data-ttu-id="59260-628">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-628">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-629">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-629">drivers license</span></span>  <br/> <span data-ttu-id="59260-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-630">drivers licence</span></span>  <br/> <span data-ttu-id="59260-631">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-631">driver's license</span></span>  <br/> <span data-ttu-id="59260-632">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-632">driver's license number</span></span>  <br/> <span data-ttu-id="59260-633">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-633">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-634">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-634">driving license number</span></span>  <br/> <span data-ttu-id="59260-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-635">dlno#</span></span>  <br/> <span data-ttu-id="59260-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="59260-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="59260-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="59260-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="59260-638">格式</span><span class="sxs-lookup"><span data-stu-id="59260-638">Format</span></span>

<span data-ttu-id="59260-639">接在指定的型態七個字的兩個字母</span><span class="sxs-lookup"><span data-stu-id="59260-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-640">模式</span><span class="sxs-lookup"><span data-stu-id="59260-640">Pattern</span></span>

<span data-ttu-id="59260-641">兩個字母後面接著七個字特殊字元：</span><span class="sxs-lookup"><span data-stu-id="59260-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="59260-642">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="59260-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="59260-643">一個連字號</span><span class="sxs-lookup"><span data-stu-id="59260-643">A hyphen</span></span>
    
- <span data-ttu-id="59260-644">六位數</span><span class="sxs-lookup"><span data-stu-id="59260-644">Six digits</span></span>
    
- <span data-ttu-id="59260-645">一個空格</span><span class="sxs-lookup"><span data-stu-id="59260-645">A space</span></span>
    
- <span data-ttu-id="59260-646">一個數字</span><span class="sxs-lookup"><span data-stu-id="59260-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="59260-647">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-647">Checksum</span></span>

<span data-ttu-id="59260-648">否</span><span class="sxs-lookup"><span data-stu-id="59260-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-649">定義</span><span class="sxs-lookup"><span data-stu-id="59260-649">Definition</span></span>

<span data-ttu-id="59260-650">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-651">規則運算式`Regex_portugal_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-652">從關鍵字`Keywords_portugal_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-653">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-653">Keywords</span></span>

<span data-ttu-id="59260-654">| |</span><span class="sxs-lookup"><span data-stu-id="59260-654"></span></span>
|<span data-ttu-id="59260-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-656">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-656">dl#</span></span>  <br/> <span data-ttu-id="59260-657">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-657">driver license</span></span>  <br/> <span data-ttu-id="59260-658">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-658">driver license number</span></span>  <br/> <span data-ttu-id="59260-659">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-659">driver licence</span></span>  <br/> <span data-ttu-id="59260-660">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-660">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-661">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-661">drivers license</span></span>  <br/> <span data-ttu-id="59260-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-662">drivers licence</span></span>  <br/> <span data-ttu-id="59260-663">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-663">driver's license</span></span>  <br/> <span data-ttu-id="59260-664">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-664">driver's license number</span></span>  <br/> <span data-ttu-id="59260-665">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-665">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-666">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-666">driving license number</span></span>  <br/> <span data-ttu-id="59260-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-667">dlno#</span></span>  <br/> <span data-ttu-id="59260-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="59260-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="59260-669">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="59260-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="59260-670">格式</span><span class="sxs-lookup"><span data-stu-id="59260-670">Format</span></span>

<span data-ttu-id="59260-671">一個接八個字的字元</span><span class="sxs-lookup"><span data-stu-id="59260-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-672">模式</span><span class="sxs-lookup"><span data-stu-id="59260-672">Pattern</span></span>

<span data-ttu-id="59260-673">後面接著八個位數字的一個字元：</span><span class="sxs-lookup"><span data-stu-id="59260-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="59260-674">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="59260-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="59260-675">八位數</span><span class="sxs-lookup"><span data-stu-id="59260-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="59260-676">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-676">Checksum</span></span>

<span data-ttu-id="59260-677">否</span><span class="sxs-lookup"><span data-stu-id="59260-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-678">定義</span><span class="sxs-lookup"><span data-stu-id="59260-678">Definition</span></span>

<span data-ttu-id="59260-679">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-680">規則運算式`Regex_romania_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-681">從關鍵字`Keywords_romania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-682">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-682">Keywords</span></span>

<span data-ttu-id="59260-683">| |</span><span class="sxs-lookup"><span data-stu-id="59260-683"></span></span>
|<span data-ttu-id="59260-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-685">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-685">dl#</span></span>  <br/> <span data-ttu-id="59260-686">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-686">driver license</span></span>  <br/> <span data-ttu-id="59260-687">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-687">driver license number</span></span>  <br/> <span data-ttu-id="59260-688">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-688">driver licence</span></span>  <br/> <span data-ttu-id="59260-689">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-689">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-690">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-690">drivers license</span></span>  <br/> <span data-ttu-id="59260-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-691">drivers licence</span></span>  <br/> <span data-ttu-id="59260-692">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-692">driver's license</span></span>  <br/> <span data-ttu-id="59260-693">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-693">driver's license number</span></span>  <br/> <span data-ttu-id="59260-694">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-694">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-695">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-695">driving license number</span></span>  <br/> <span data-ttu-id="59260-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-696">dlno#</span></span>  <br/> <span data-ttu-id="59260-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="59260-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="59260-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="59260-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="59260-699">格式</span><span class="sxs-lookup"><span data-stu-id="59260-699">Format</span></span>

<span data-ttu-id="59260-700">一個後面七位數字的字元</span><span class="sxs-lookup"><span data-stu-id="59260-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-701">模式</span><span class="sxs-lookup"><span data-stu-id="59260-701">Pattern</span></span>

<span data-ttu-id="59260-702">一個後面七位數字的字元</span><span class="sxs-lookup"><span data-stu-id="59260-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="59260-703">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="59260-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="59260-704">七位數</span><span class="sxs-lookup"><span data-stu-id="59260-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="59260-705">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-705">Checksum</span></span>

<span data-ttu-id="59260-706">否</span><span class="sxs-lookup"><span data-stu-id="59260-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-707">定義</span><span class="sxs-lookup"><span data-stu-id="59260-707">Definition</span></span>

<span data-ttu-id="59260-708">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-709">規則運算式`Regex_slovakia_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-710">從關鍵字`Keywords_slovakia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-711">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-711">Keywords</span></span>

<span data-ttu-id="59260-712">| |</span><span class="sxs-lookup"><span data-stu-id="59260-712"></span></span>
|<span data-ttu-id="59260-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-714">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-714">dl#</span></span>  <br/> <span data-ttu-id="59260-715">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-715">driver license</span></span>  <br/> <span data-ttu-id="59260-716">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-716">driver license number</span></span>  <br/> <span data-ttu-id="59260-717">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-717">driver licence</span></span>  <br/> <span data-ttu-id="59260-718">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-718">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-719">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-719">drivers license</span></span>  <br/> <span data-ttu-id="59260-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-720">drivers licence</span></span>  <br/> <span data-ttu-id="59260-721">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-721">driver's license</span></span>  <br/> <span data-ttu-id="59260-722">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-722">driver's license number</span></span>  <br/> <span data-ttu-id="59260-723">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-723">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-724">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-724">driving license number</span></span>  <br/> <span data-ttu-id="59260-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-725">dlno#</span></span>  <br/> <span data-ttu-id="59260-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="59260-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="59260-727">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="59260-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="59260-728">格式</span><span class="sxs-lookup"><span data-stu-id="59260-728">Format</span></span>

<span data-ttu-id="59260-729">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="59260-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-730">模式</span><span class="sxs-lookup"><span data-stu-id="59260-730">Pattern</span></span>

<span data-ttu-id="59260-731">九位數</span><span class="sxs-lookup"><span data-stu-id="59260-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="59260-732">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-732">Checksum</span></span>

<span data-ttu-id="59260-733">否</span><span class="sxs-lookup"><span data-stu-id="59260-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-734">定義</span><span class="sxs-lookup"><span data-stu-id="59260-734">Definition</span></span>

<span data-ttu-id="59260-735">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-736">規則運算式`Regex_slovenia_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-737">從關鍵字`Keywords_slovenia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-738">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-738">Keywords</span></span>

<span data-ttu-id="59260-739">| |</span><span class="sxs-lookup"><span data-stu-id="59260-739"></span></span>
|<span data-ttu-id="59260-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-741">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-741">dl#</span></span>  <br/> <span data-ttu-id="59260-742">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-742">driver license</span></span>  <br/> <span data-ttu-id="59260-743">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-743">driver license number</span></span>  <br/> <span data-ttu-id="59260-744">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-744">driver licence</span></span>  <br/> <span data-ttu-id="59260-745">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-745">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-746">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-746">drivers license</span></span>  <br/> <span data-ttu-id="59260-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-747">drivers licence</span></span>  <br/> <span data-ttu-id="59260-748">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-748">driver's license</span></span>  <br/> <span data-ttu-id="59260-749">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-749">driver's license number</span></span>  <br/> <span data-ttu-id="59260-750">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-750">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-751">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-751">driving license number</span></span>  <br/> <span data-ttu-id="59260-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-752">dlno#</span></span>  <br/> <span data-ttu-id="59260-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="59260-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="59260-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="59260-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="59260-755">格式</span><span class="sxs-lookup"><span data-stu-id="59260-755">Format</span></span>

<span data-ttu-id="59260-756">後面接著一個字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="59260-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-757">模式</span><span class="sxs-lookup"><span data-stu-id="59260-757">Pattern</span></span>

<span data-ttu-id="59260-758">後面接著一個字元的八個位數：</span><span class="sxs-lookup"><span data-stu-id="59260-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="59260-759">八位數</span><span class="sxs-lookup"><span data-stu-id="59260-759">Eight digits</span></span> 
    
- <span data-ttu-id="59260-760">一個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="59260-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="59260-761">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-761">Checksum</span></span>

<span data-ttu-id="59260-762">是</span><span class="sxs-lookup"><span data-stu-id="59260-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-763">定義</span><span class="sxs-lookup"><span data-stu-id="59260-763">Definition</span></span>

<span data-ttu-id="59260-764">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-765">此函數`Func_spain_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-766">從關鍵字`Keywords_spain_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="59260-767">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-767">Keywords</span></span>

<span data-ttu-id="59260-768">| |</span><span class="sxs-lookup"><span data-stu-id="59260-768"></span></span>
|<span data-ttu-id="59260-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-770">dlno#</span></span>  <br/> <span data-ttu-id="59260-771">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-771">dl#</span></span>  <br/> <span data-ttu-id="59260-772">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-772">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-773">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-773">driver licence</span></span>  <br/> <span data-ttu-id="59260-774">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-774">driver license</span></span>  <br/> <span data-ttu-id="59260-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-775">drivers licence</span></span>  <br/> <span data-ttu-id="59260-776">
drivers license</span><span class="sxs-lookup"><span data-stu-id="59260-776">drivers license</span></span>  <br/> <span data-ttu-id="59260-777">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="59260-777">driver's licence</span></span>  <br/> <span data-ttu-id="59260-778">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-778">driver's license</span></span>  <br/> <span data-ttu-id="59260-779">driving licence
</span><span class="sxs-lookup"><span data-stu-id="59260-779">driving licence</span></span>  <br/> <span data-ttu-id="59260-780">主導授權</span><span class="sxs-lookup"><span data-stu-id="59260-780">driving license</span></span>  <br/> <span data-ttu-id="59260-781">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-781">driver licence number</span></span>  <br/> <span data-ttu-id="59260-782">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-782">driver license number</span></span>  <br/> <span data-ttu-id="59260-783">發行的驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-783">drivers licence number</span></span>  <br/> <span data-ttu-id="59260-784">發行的驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-784">drivers license number</span></span>  <br/> <span data-ttu-id="59260-785">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-785">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-786">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-786">driver's license number</span></span>  <br/> <span data-ttu-id="59260-787">driving 授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-787">driving licence number</span></span>  <br/> <span data-ttu-id="59260-788">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-788">driving license number</span></span>  <br/> <span data-ttu-id="59260-789">主導使用權限</span><span class="sxs-lookup"><span data-stu-id="59260-789">driving permit</span></span>  <br/> <span data-ttu-id="59260-790">主導使用權限數字</span><span class="sxs-lookup"><span data-stu-id="59260-790">driving permit number</span></span>  <br/> <span data-ttu-id="59260-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="59260-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="59260-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="59260-792">permiso conducción</span></span>  <br/> <span data-ttu-id="59260-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="59260-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="59260-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="59260-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="59260-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="59260-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="59260-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="59260-796">licencia conducir</span></span>  <br/> <span data-ttu-id="59260-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="59260-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="59260-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="59260-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="59260-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="59260-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="59260-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="59260-800">permiso conducir</span></span>  <br/> <span data-ttu-id="59260-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="59260-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="59260-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="59260-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="59260-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="59260-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="59260-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="59260-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="59260-805">格式</span><span class="sxs-lookup"><span data-stu-id="59260-805">Format</span></span>

<span data-ttu-id="59260-806">十個包含連字號的數字</span><span class="sxs-lookup"><span data-stu-id="59260-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="59260-807">模式</span><span class="sxs-lookup"><span data-stu-id="59260-807">Pattern</span></span>

<span data-ttu-id="59260-808">包含連字號十位數：</span><span class="sxs-lookup"><span data-stu-id="59260-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="59260-809">六位數</span><span class="sxs-lookup"><span data-stu-id="59260-809">Six digits</span></span> 
    
- <span data-ttu-id="59260-810">一個連字號</span><span class="sxs-lookup"><span data-stu-id="59260-810">A hyphen</span></span>
    
- <span data-ttu-id="59260-811">四位數</span><span class="sxs-lookup"><span data-stu-id="59260-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="59260-812">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="59260-812">Checksum</span></span>

<span data-ttu-id="59260-813">否</span><span class="sxs-lookup"><span data-stu-id="59260-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="59260-814">定義</span><span class="sxs-lookup"><span data-stu-id="59260-814">Definition</span></span>

<span data-ttu-id="59260-815">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="59260-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="59260-816">規則運算式`Regex_sweden_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="59260-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="59260-817">從關鍵字`Keywords_sweden_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="59260-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="59260-818">關鍵字</span><span class="sxs-lookup"><span data-stu-id="59260-818">Keywords</span></span>

<span data-ttu-id="59260-819">| |</span><span class="sxs-lookup"><span data-stu-id="59260-819"></span></span>
|<span data-ttu-id="59260-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="59260-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="59260-821">dl #</span><span class="sxs-lookup"><span data-stu-id="59260-821">dl#</span></span>  <br/> <span data-ttu-id="59260-822">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-822">driver license</span></span>  <br/> <span data-ttu-id="59260-823">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="59260-823">driver license number</span></span>  <br/> <span data-ttu-id="59260-824">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-824">driver licence</span></span>  <br/> <span data-ttu-id="59260-825">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="59260-825">drivers lic.</span></span>  <br/> <span data-ttu-id="59260-826">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="59260-826">drivers license</span></span>  <br/> <span data-ttu-id="59260-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="59260-827">drivers licence</span></span>  <br/> <span data-ttu-id="59260-828">駕照</span><span class="sxs-lookup"><span data-stu-id="59260-828">driver's license</span></span>  <br/> <span data-ttu-id="59260-829">駕照編號</span><span class="sxs-lookup"><span data-stu-id="59260-829">driver's license number</span></span>  <br/> <span data-ttu-id="59260-830">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="59260-830">driver's licence number</span></span>  <br/> <span data-ttu-id="59260-831">主導照編號</span><span class="sxs-lookup"><span data-stu-id="59260-831">driving license number</span></span>  <br/> <span data-ttu-id="59260-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="59260-832">dlno#</span></span>  <br/> <span data-ttu-id="59260-833">körkort</span><span class="sxs-lookup"><span data-stu-id="59260-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="59260-834">英國</span><span class="sxs-lookup"><span data-stu-id="59260-834">UK</span></span>

<span data-ttu-id="59260-p103">如需詳細資訊，請參閱節"英國駕照編號 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="59260-p103">For details, see the section "U.K. Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="59260-837">另請參閱</span><span class="sxs-lookup"><span data-stu-id="59260-837">See also</span></span>

[<span data-ttu-id="59260-838">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="59260-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

