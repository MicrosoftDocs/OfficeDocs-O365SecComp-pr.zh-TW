---
title: 歐盟駕照編號
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: c3923cd3-ec84-435f-bf41-cadc37996a4b
description: 本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟駕照編號敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
ms.openlocfilehash: 86be7b52aed7581fd62ab595ac2c4b63ab33aab3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217743"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="13654-104">歐盟駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-104">EU Driver's License Number</span></span>

<span data-ttu-id="13654-p102">本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟駕照編號敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。</span><span class="sxs-lookup"><span data-stu-id="13654-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="13654-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="13654-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="13654-108">格式</span><span class="sxs-lookup"><span data-stu-id="13654-108">Format</span></span>

<span data-ttu-id="13654-109">不含空格和分隔字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="13654-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-110">模式</span><span class="sxs-lookup"><span data-stu-id="13654-110">Pattern</span></span>

<span data-ttu-id="13654-111">八位數</span><span class="sxs-lookup"><span data-stu-id="13654-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="13654-112">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-112">Checksum</span></span>

<span data-ttu-id="13654-113">否</span><span class="sxs-lookup"><span data-stu-id="13654-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-114">定義</span><span class="sxs-lookup"><span data-stu-id="13654-114">Definition</span></span>

<span data-ttu-id="13654-115">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-116">規則運算式`Regex_austria_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-117">從關鍵字`Keywords_austria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="13654-118">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-118">Keywords</span></span>

<span data-ttu-id="13654-119">| |</span><span class="sxs-lookup"><span data-stu-id="13654-119"></span></span>
|<span data-ttu-id="13654-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-121">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-121">dl#</span></span>  <br/> <span data-ttu-id="13654-122">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-122">driver license</span></span>  <br/> <span data-ttu-id="13654-123">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-123">driver license number</span></span>  <br/> <span data-ttu-id="13654-124">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-124">driver licence</span></span>  <br/> <span data-ttu-id="13654-125">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-125">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-126">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-126">drivers license</span></span>  <br/> <span data-ttu-id="13654-127">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="13654-127">driver's licence</span></span>  <br/> <span data-ttu-id="13654-128">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-128">driver's license</span></span>  <br/> <span data-ttu-id="13654-129">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-129">driver's license number</span></span>  <br/> <span data-ttu-id="13654-130">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="13654-131">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-131">driving license number</span></span>  <br/> <span data-ttu-id="13654-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-132">dlno#</span></span>  <br/> <span data-ttu-id="13654-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="13654-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="13654-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="13654-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="13654-135">比利時</span><span class="sxs-lookup"><span data-stu-id="13654-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="13654-136">格式</span><span class="sxs-lookup"><span data-stu-id="13654-136">Format</span></span>

<span data-ttu-id="13654-137">不含空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="13654-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-138">模式</span><span class="sxs-lookup"><span data-stu-id="13654-138">Pattern</span></span>

<span data-ttu-id="13654-139">10 位數</span><span class="sxs-lookup"><span data-stu-id="13654-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="13654-140">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-140">Checksum</span></span>

<span data-ttu-id="13654-141">否</span><span class="sxs-lookup"><span data-stu-id="13654-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-142">定義</span><span class="sxs-lookup"><span data-stu-id="13654-142">Definition</span></span>

<span data-ttu-id="13654-143">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-144">規則運算式`Regex_belgium_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-145">從關鍵字`Keywords_belgium_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="13654-146">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-146">Keywords</span></span>

<span data-ttu-id="13654-147">| |</span><span class="sxs-lookup"><span data-stu-id="13654-147"></span></span>
|<span data-ttu-id="13654-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-149">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-149">dl#</span></span>  <br/> <span data-ttu-id="13654-150">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-150">driver license</span></span>  <br/> <span data-ttu-id="13654-151">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-151">driver license number</span></span>  <br/> <span data-ttu-id="13654-152">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-152">driver licence</span></span>  <br/> <span data-ttu-id="13654-153">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-153">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-154">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-154">drivers license</span></span>  <br/> <span data-ttu-id="13654-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-155">drivers licence</span></span>  <br/> <span data-ttu-id="13654-156">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-156">driver's license</span></span>  <br/> <span data-ttu-id="13654-157">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-157">driver's license number</span></span>  <br/> <span data-ttu-id="13654-158">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-158">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-159">dlno#</span></span>  <br/> <span data-ttu-id="13654-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="13654-160">rijbewijs</span></span>  <br/> <span data-ttu-id="13654-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="13654-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="13654-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="13654-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="13654-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="13654-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="13654-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="13654-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="13654-165">führerschein 編號</span><span class="sxs-lookup"><span data-stu-id="13654-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="13654-166">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="13654-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="13654-167">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="13654-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="13654-168">保加利亞</span><span class="sxs-lookup"><span data-stu-id="13654-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="13654-169">格式</span><span class="sxs-lookup"><span data-stu-id="13654-169">Format</span></span>

<span data-ttu-id="13654-170">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="13654-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-171">模式</span><span class="sxs-lookup"><span data-stu-id="13654-171">Pattern</span></span>

<span data-ttu-id="13654-172">九位數</span><span class="sxs-lookup"><span data-stu-id="13654-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="13654-173">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-173">Checksum</span></span>

<span data-ttu-id="13654-174">否</span><span class="sxs-lookup"><span data-stu-id="13654-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-175">定義</span><span class="sxs-lookup"><span data-stu-id="13654-175">Definition</span></span>

<span data-ttu-id="13654-176">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-177">規則運算式`Regex_bulgaria_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-178">從關鍵字`Keywords_bulgaria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="13654-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-179">Keywords</span></span>

<span data-ttu-id="13654-180">| |</span><span class="sxs-lookup"><span data-stu-id="13654-180"></span></span>
|<span data-ttu-id="13654-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-182">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-182">dl#</span></span>  <br/> <span data-ttu-id="13654-183">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-183">driver license</span></span>  <br/> <span data-ttu-id="13654-184">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-184">driver license number</span></span>  <br/> <span data-ttu-id="13654-185">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-185">driver licence</span></span>  <br/> <span data-ttu-id="13654-186">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-186">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-187">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-187">drivers license</span></span>  <br/> <span data-ttu-id="13654-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-188">drivers licence</span></span>  <br/> <span data-ttu-id="13654-189">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-189">driver's license</span></span>  <br/> <span data-ttu-id="13654-190">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-190">driver's license number</span></span>  <br/> <span data-ttu-id="13654-191">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-191">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-192">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-192">driving license number</span></span>  <br/> <span data-ttu-id="13654-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-193">dlno#</span></span>  <br/> <span data-ttu-id="13654-194">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МПС</span><span class="sxs-lookup"><span data-stu-id="13654-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="13654-195">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО</span><span class="sxs-lookup"><span data-stu-id="13654-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="13654-196">СУМПС</span><span class="sxs-lookup"><span data-stu-id="13654-196">сумпс</span></span>  <br/> <span data-ttu-id="13654-197">ШОФЬОРСКА КНИЖКА</span><span class="sxs-lookup"><span data-stu-id="13654-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="13654-198">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="13654-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="13654-199">格式</span><span class="sxs-lookup"><span data-stu-id="13654-199">Format</span></span>

<span data-ttu-id="13654-200">不含空格和分隔字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="13654-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-201">模式</span><span class="sxs-lookup"><span data-stu-id="13654-201">Pattern</span></span>

<span data-ttu-id="13654-202">八位數</span><span class="sxs-lookup"><span data-stu-id="13654-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="13654-203">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-203">Checksum</span></span>

<span data-ttu-id="13654-204">否</span><span class="sxs-lookup"><span data-stu-id="13654-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-205">定義</span><span class="sxs-lookup"><span data-stu-id="13654-205">Definition</span></span>

<span data-ttu-id="13654-206">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-207">規則運算式`Regex_croatia_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-208">從關鍵字`Keywords_croatia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="13654-209">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-209">Keywords</span></span>

<span data-ttu-id="13654-210">| |</span><span class="sxs-lookup"><span data-stu-id="13654-210"></span></span>
|<span data-ttu-id="13654-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-212">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-212">dl#</span></span>  <br/> <span data-ttu-id="13654-213">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-213">driver license</span></span>  <br/> <span data-ttu-id="13654-214">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-214">driver license number</span></span>  <br/> <span data-ttu-id="13654-215">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-215">driver licence</span></span>  <br/> <span data-ttu-id="13654-216">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-216">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-217">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-217">drivers license</span></span>  <br/> <span data-ttu-id="13654-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-218">drivers licence</span></span>  <br/> <span data-ttu-id="13654-219">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-219">driver's license</span></span>  <br/> <span data-ttu-id="13654-220">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-220">driver's license number</span></span>  <br/> <span data-ttu-id="13654-221">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-221">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-222">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-222">driving license number</span></span>  <br/> <span data-ttu-id="13654-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-223">dlno#</span></span>  <br/> <span data-ttu-id="13654-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="13654-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="13654-225">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="13654-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="13654-226">格式</span><span class="sxs-lookup"><span data-stu-id="13654-226">Format</span></span>

<span data-ttu-id="13654-227">12 的數字不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="13654-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-228">模式</span><span class="sxs-lookup"><span data-stu-id="13654-228">Pattern</span></span>

<span data-ttu-id="13654-229">12 位數</span><span class="sxs-lookup"><span data-stu-id="13654-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="13654-230">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-230">Checksum</span></span>

<span data-ttu-id="13654-231">否</span><span class="sxs-lookup"><span data-stu-id="13654-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-232">定義</span><span class="sxs-lookup"><span data-stu-id="13654-232">Definition</span></span>

<span data-ttu-id="13654-233">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-234">規則運算式`Regex_cyprus_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-235">從關鍵字`Keywords_cyprus_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-236">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-236">Keywords</span></span>

<span data-ttu-id="13654-237">| |</span><span class="sxs-lookup"><span data-stu-id="13654-237"></span></span>
|<span data-ttu-id="13654-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-239">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-239">dl#</span></span>  <br/> <span data-ttu-id="13654-240">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-240">driver license</span></span>  <br/> <span data-ttu-id="13654-241">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-241">driver license number</span></span>  <br/> <span data-ttu-id="13654-242">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-242">driver licence</span></span>  <br/> <span data-ttu-id="13654-243">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-243">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-244">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-244">drivers license</span></span>  <br/> <span data-ttu-id="13654-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-245">drivers licence</span></span>  <br/> <span data-ttu-id="13654-246">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-246">driver's license number</span></span>  <br/> <span data-ttu-id="13654-247">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-247">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-248">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-248">driving license number</span></span>  <br/> <span data-ttu-id="13654-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-249">dlno#</span></span>  <br/> <span data-ttu-id="13654-250">ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="13654-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="13654-251">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="13654-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="13654-252">格式</span><span class="sxs-lookup"><span data-stu-id="13654-252">Format</span></span>

<span data-ttu-id="13654-253">兩個字母後面接著 6 位數</span><span class="sxs-lookup"><span data-stu-id="13654-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-254">模式</span><span class="sxs-lookup"><span data-stu-id="13654-254">Pattern</span></span>

<span data-ttu-id="13654-255">八個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="13654-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="13654-256">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="13654-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="13654-257">一個空格 (選用)</span><span class="sxs-lookup"><span data-stu-id="13654-257">A space (optional)</span></span>
    
- <span data-ttu-id="13654-258">六位數</span><span class="sxs-lookup"><span data-stu-id="13654-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="13654-259">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-259">Checksum</span></span>

<span data-ttu-id="13654-260">否</span><span class="sxs-lookup"><span data-stu-id="13654-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-261">定義</span><span class="sxs-lookup"><span data-stu-id="13654-261">Definition</span></span>

<span data-ttu-id="13654-262">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-263">規則運算式`Regex_czech_republic_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-264">從關鍵字`Keywords_czech_republic_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="13654-265">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-265">Keywords</span></span>

<span data-ttu-id="13654-266">| |</span><span class="sxs-lookup"><span data-stu-id="13654-266"></span></span>
|<span data-ttu-id="13654-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-268">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-268">dl#</span></span>  <br/> <span data-ttu-id="13654-269">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-269">driver license</span></span>  <br/> <span data-ttu-id="13654-270">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-270">driver license number</span></span>  <br/> <span data-ttu-id="13654-271">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-271">driver licence</span></span>  <br/> <span data-ttu-id="13654-272">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-272">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-273">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-273">drivers license</span></span>  <br/> <span data-ttu-id="13654-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-274">drivers licence</span></span>  <br/> <span data-ttu-id="13654-275">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-275">driver's license</span></span>  <br/> <span data-ttu-id="13654-276">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-276">driver's license number</span></span>  <br/> <span data-ttu-id="13654-277">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-277">driver's license number</span></span>  <br/> <span data-ttu-id="13654-278">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-278">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-279">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-279">driving license number</span></span>  <br/> <span data-ttu-id="13654-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-280">dlno#</span></span>  <br/> <span data-ttu-id="13654-281">Řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="13654-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="13654-282">丹麥</span><span class="sxs-lookup"><span data-stu-id="13654-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="13654-283">格式</span><span class="sxs-lookup"><span data-stu-id="13654-283">Format</span></span>

<span data-ttu-id="13654-284">不含空格和分隔字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="13654-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-285">模式</span><span class="sxs-lookup"><span data-stu-id="13654-285">Pattern</span></span>

<span data-ttu-id="13654-286">八位數</span><span class="sxs-lookup"><span data-stu-id="13654-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="13654-287">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-287">Checksum</span></span>

<span data-ttu-id="13654-288">是</span><span class="sxs-lookup"><span data-stu-id="13654-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-289">定義</span><span class="sxs-lookup"><span data-stu-id="13654-289">Definition</span></span>

<span data-ttu-id="13654-290">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-291">規則運算式`Regex_denmark_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-292">從關鍵字`Keywords_denmark_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="13654-293">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-293">Keywords</span></span>

<span data-ttu-id="13654-294">| |</span><span class="sxs-lookup"><span data-stu-id="13654-294"></span></span>
|<span data-ttu-id="13654-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-296">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-296">dl#</span></span>  <br/> <span data-ttu-id="13654-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-297">driver license</span></span>  <br/> <span data-ttu-id="13654-298">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-298">driver license number</span></span>  <br/> <span data-ttu-id="13654-299">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-299">driver licence</span></span>  <br/> <span data-ttu-id="13654-300">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-300">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-301">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-301">drivers license</span></span>  <br/> <span data-ttu-id="13654-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-302">drivers licence</span></span>  <br/> <span data-ttu-id="13654-303">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-303">driver's license</span></span>  <br/> <span data-ttu-id="13654-304">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-304">driver's license number</span></span>  <br/> <span data-ttu-id="13654-305">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-305">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-306">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-306">driving license number</span></span>  <br/> <span data-ttu-id="13654-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-307">dlno#</span></span>  <br/> <span data-ttu-id="13654-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="13654-308">kørekort</span></span>  <br/> <span data-ttu-id="13654-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="13654-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="13654-310">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="13654-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="13654-311">格式</span><span class="sxs-lookup"><span data-stu-id="13654-311">Format</span></span>

<span data-ttu-id="13654-312">兩個字母後面接著 6 位數</span><span class="sxs-lookup"><span data-stu-id="13654-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-313">模式</span><span class="sxs-lookup"><span data-stu-id="13654-313">Pattern</span></span>

<span data-ttu-id="13654-314">兩個字母和 6 位數：</span><span class="sxs-lookup"><span data-stu-id="13654-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="13654-315">字母"ET"（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="13654-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="13654-316">六位數</span><span class="sxs-lookup"><span data-stu-id="13654-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="13654-317">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-317">Checksum</span></span>

<span data-ttu-id="13654-318">否</span><span class="sxs-lookup"><span data-stu-id="13654-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-319">定義</span><span class="sxs-lookup"><span data-stu-id="13654-319">Definition</span></span>

<span data-ttu-id="13654-320">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-321">規則運算式`Regex_estonia_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-322">從關鍵字`Keywords_estonia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-323">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-323">Keywords</span></span>

<span data-ttu-id="13654-324">| |</span><span class="sxs-lookup"><span data-stu-id="13654-324"></span></span>
|<span data-ttu-id="13654-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-326">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-326">dl#</span></span>  <br/> <span data-ttu-id="13654-327">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-327">driver license</span></span>  <br/> <span data-ttu-id="13654-328">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-328">driver license number</span></span>  <br/> <span data-ttu-id="13654-329">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-329">driver license number</span></span>  <br/> <span data-ttu-id="13654-330">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-330">driver licence</span></span>  <br/> <span data-ttu-id="13654-331">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-331">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-332">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-332">drivers license</span></span>  <br/> <span data-ttu-id="13654-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-333">drivers licence</span></span>  <br/> <span data-ttu-id="13654-334">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-334">driver's license</span></span>  <br/> <span data-ttu-id="13654-335">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-335">driver's license number</span></span>  <br/> <span data-ttu-id="13654-336">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-336">driving license number</span></span>  <br/> <span data-ttu-id="13654-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-337">dlno#</span></span>  <br/> <span data-ttu-id="13654-338">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="13654-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="13654-339">芬蘭</span><span class="sxs-lookup"><span data-stu-id="13654-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="13654-340">格式</span><span class="sxs-lookup"><span data-stu-id="13654-340">Format</span></span>

<span data-ttu-id="13654-341">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="13654-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-342">模式</span><span class="sxs-lookup"><span data-stu-id="13654-342">Pattern</span></span>

<span data-ttu-id="13654-343">包含連字號的數字 10：</span><span class="sxs-lookup"><span data-stu-id="13654-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="13654-344">六位數</span><span class="sxs-lookup"><span data-stu-id="13654-344">Six digits</span></span> 
    
- <span data-ttu-id="13654-345">一個連字號</span><span class="sxs-lookup"><span data-stu-id="13654-345">A hyphen</span></span>
    
-  <span data-ttu-id="13654-346">四位數</span><span class="sxs-lookup"><span data-stu-id="13654-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="13654-347">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-347">Checksum</span></span>

<span data-ttu-id="13654-348">否</span><span class="sxs-lookup"><span data-stu-id="13654-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-349">定義</span><span class="sxs-lookup"><span data-stu-id="13654-349">Definition</span></span>

<span data-ttu-id="13654-350">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-351">規則運算式`Regex_finland_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-352">從關鍵字`Keywords_finland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-353">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-353">Keywords</span></span>

<span data-ttu-id="13654-354">| |</span><span class="sxs-lookup"><span data-stu-id="13654-354"></span></span>
|<span data-ttu-id="13654-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-356">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-356">dl#</span></span>  <br/> <span data-ttu-id="13654-357">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-357">driver license</span></span>  <br/> <span data-ttu-id="13654-358">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-358">driver license number</span></span>  <br/> <span data-ttu-id="13654-359">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-359">driver licence</span></span>  <br/> <span data-ttu-id="13654-360">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-360">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-361">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-361">drivers license</span></span>  <br/> <span data-ttu-id="13654-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-362">drivers licence</span></span>  <br/> <span data-ttu-id="13654-363">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-363">driver's license</span></span>  <br/> <span data-ttu-id="13654-364">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-364">driver's license number</span></span>  <br/> <span data-ttu-id="13654-365">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-365">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-366">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-366">driving license number</span></span>  <br/> <span data-ttu-id="13654-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-367">dlno#</span></span>  <br/> <span data-ttu-id="13654-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="13654-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="13654-369">法國</span><span class="sxs-lookup"><span data-stu-id="13654-369">France</span></span>

<span data-ttu-id="13654-370">如需詳細資訊，請參閱節"法國駕照編號 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="13654-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="13654-371">德國</span><span class="sxs-lookup"><span data-stu-id="13654-371">Germany</span></span>

<span data-ttu-id="13654-372">如需詳細資訊，請參閱節"德國駕照編號 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="13654-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="13654-373">希臘</span><span class="sxs-lookup"><span data-stu-id="13654-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="13654-374">格式</span><span class="sxs-lookup"><span data-stu-id="13654-374">Format</span></span>

<span data-ttu-id="13654-375">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="13654-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-376">模式</span><span class="sxs-lookup"><span data-stu-id="13654-376">Pattern</span></span>

 <span data-ttu-id="13654-377">九位數</span><span class="sxs-lookup"><span data-stu-id="13654-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="13654-378">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-378">Checksum</span></span>

<span data-ttu-id="13654-379">否</span><span class="sxs-lookup"><span data-stu-id="13654-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-380">定義</span><span class="sxs-lookup"><span data-stu-id="13654-380">Definition</span></span>

<span data-ttu-id="13654-381">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-382">規則運算式`Regex_greece_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-383">從關鍵字`Keywords_greece_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-384">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-384">Keywords</span></span>

<span data-ttu-id="13654-385">| |</span><span class="sxs-lookup"><span data-stu-id="13654-385"></span></span>
|<span data-ttu-id="13654-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="13654-387">dlL#</span></span>  <br/> <span data-ttu-id="13654-388">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-388">driver license</span></span>  <br/> <span data-ttu-id="13654-389">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-389">driver license number</span></span>  <br/> <span data-ttu-id="13654-390">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-390">driver licence</span></span>  <br/> <span data-ttu-id="13654-391">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-391">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-392">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-392">drivers license</span></span>  <br/> <span data-ttu-id="13654-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-393">drivers licence</span></span>  <br/> <span data-ttu-id="13654-394">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-394">driver's license</span></span>  <br/> <span data-ttu-id="13654-395">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-395">driver's license number</span></span>  <br/> <span data-ttu-id="13654-396">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-396">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-397">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-397">driving license number</span></span>  <br/> <span data-ttu-id="13654-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-398">dlno#</span></span>  <br/> <span data-ttu-id="13654-399">ΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="13654-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="13654-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="13654-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="13654-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="13654-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="13654-402">格式</span><span class="sxs-lookup"><span data-stu-id="13654-402">Format</span></span>

<span data-ttu-id="13654-403">兩個字母後面接著 6 位數</span><span class="sxs-lookup"><span data-stu-id="13654-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-404">模式</span><span class="sxs-lookup"><span data-stu-id="13654-404">Pattern</span></span>

<span data-ttu-id="13654-405">兩個字母和 6 位數：</span><span class="sxs-lookup"><span data-stu-id="13654-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="13654-406">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="13654-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="13654-407">六位數</span><span class="sxs-lookup"><span data-stu-id="13654-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="13654-408">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-408">Checksum</span></span>

<span data-ttu-id="13654-409">否</span><span class="sxs-lookup"><span data-stu-id="13654-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-410">定義</span><span class="sxs-lookup"><span data-stu-id="13654-410">Definition</span></span>

<span data-ttu-id="13654-411">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-412">規則運算式`Regex_hungary_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-413">從關鍵字`Keywords_hungary_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-414">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-414">Keywords</span></span>

<span data-ttu-id="13654-415">| |</span><span class="sxs-lookup"><span data-stu-id="13654-415"></span></span>
|<span data-ttu-id="13654-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-417">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-417">dl#</span></span>  <br/> <span data-ttu-id="13654-418">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-418">driver license</span></span>  <br/> <span data-ttu-id="13654-419">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-419">driver license number</span></span>  <br/> <span data-ttu-id="13654-420">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-420">driver licence</span></span>  <br/> <span data-ttu-id="13654-421">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-421">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-422">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-422">drivers license</span></span>  <br/> <span data-ttu-id="13654-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-423">drivers licence</span></span>  <br/> <span data-ttu-id="13654-424">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-424">driver's license</span></span>  <br/> <span data-ttu-id="13654-425">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-425">driver's license number</span></span>  <br/> <span data-ttu-id="13654-426">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-426">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-427">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-427">driving license number</span></span>  <br/> <span data-ttu-id="13654-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-428">dlno#</span></span>  <br/> <span data-ttu-id="13654-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="13654-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="13654-430">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="13654-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="13654-431">格式</span><span class="sxs-lookup"><span data-stu-id="13654-431">Format</span></span>

<span data-ttu-id="13654-432">後面接著四個字母的 6 位數</span><span class="sxs-lookup"><span data-stu-id="13654-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-433">模式</span><span class="sxs-lookup"><span data-stu-id="13654-433">Pattern</span></span>

<span data-ttu-id="13654-434">6 位數和四個字母：</span><span class="sxs-lookup"><span data-stu-id="13654-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="13654-435">六位數</span><span class="sxs-lookup"><span data-stu-id="13654-435">Six digits</span></span>
    
- <span data-ttu-id="13654-436">四個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="13654-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="13654-437">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-437">Checksum</span></span>

<span data-ttu-id="13654-438">否</span><span class="sxs-lookup"><span data-stu-id="13654-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-439">定義</span><span class="sxs-lookup"><span data-stu-id="13654-439">Definition</span></span>

<span data-ttu-id="13654-440">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-441">規則運算式`Regex_ireland_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-442">從關鍵字`Keywords_ireland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-443">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-443">Keywords</span></span>

<span data-ttu-id="13654-444">| |</span><span class="sxs-lookup"><span data-stu-id="13654-444"></span></span>
|<span data-ttu-id="13654-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-446">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-446">dl#</span></span>  <br/> <span data-ttu-id="13654-447">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-447">driver license</span></span>  <br/> <span data-ttu-id="13654-448">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-448">driver license number</span></span>  <br/> <span data-ttu-id="13654-449">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-449">driver licence</span></span>  <br/> <span data-ttu-id="13654-450">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-450">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-451">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-451">drivers license</span></span>  <br/> <span data-ttu-id="13654-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-452">drivers licence</span></span>  <br/> <span data-ttu-id="13654-453">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-453">driver's license</span></span>  <br/> <span data-ttu-id="13654-454">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-454">driver's license number</span></span>  <br/> <span data-ttu-id="13654-455">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-455">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-456">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-456">driving license number</span></span>  <br/> <span data-ttu-id="13654-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-457">dlno#</span></span>  <br/> <span data-ttu-id="13654-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="13654-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="13654-459">義大利</span><span class="sxs-lookup"><span data-stu-id="13654-459">Italy</span></span>

<span data-ttu-id="13654-460">如需詳細資訊，請參閱節"義大利駕照編號 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="13654-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="13654-461">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="13654-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="13654-462">格式</span><span class="sxs-lookup"><span data-stu-id="13654-462">Format</span></span>

<span data-ttu-id="13654-463">三個字母後面接著 6 位數</span><span class="sxs-lookup"><span data-stu-id="13654-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-464">模式</span><span class="sxs-lookup"><span data-stu-id="13654-464">Pattern</span></span>

<span data-ttu-id="13654-465">三個字母和 6 位數：</span><span class="sxs-lookup"><span data-stu-id="13654-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="13654-466">三個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="13654-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="13654-467">六位數</span><span class="sxs-lookup"><span data-stu-id="13654-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="13654-468">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-468">Checksum</span></span>

<span data-ttu-id="13654-469">否</span><span class="sxs-lookup"><span data-stu-id="13654-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-470">定義</span><span class="sxs-lookup"><span data-stu-id="13654-470">Definition</span></span>

<span data-ttu-id="13654-471">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-472">規則運算式`Regex_latvia_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-473">從關鍵字`Keywords_latvia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-474">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-474">Keywords</span></span>

<span data-ttu-id="13654-475">| |</span><span class="sxs-lookup"><span data-stu-id="13654-475"></span></span>
|<span data-ttu-id="13654-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-477">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-477">dl#</span></span>  <br/> <span data-ttu-id="13654-478">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-478">driver license</span></span>  <br/> <span data-ttu-id="13654-479">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-479">driver license number</span></span>  <br/> <span data-ttu-id="13654-480">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-480">driver licence</span></span>  <br/> <span data-ttu-id="13654-481">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-481">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-482">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-482">drivers license</span></span>  <br/> <span data-ttu-id="13654-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-483">drivers licence</span></span>  <br/> <span data-ttu-id="13654-484">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-484">driver's license</span></span>  <br/> <span data-ttu-id="13654-485">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-485">driver's license number</span></span>  <br/> <span data-ttu-id="13654-486">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-486">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-487">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-487">driving license number</span></span>  <br/> <span data-ttu-id="13654-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-488">dlno#</span></span>  <br/> <span data-ttu-id="13654-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="13654-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="13654-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="13654-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="13654-491">格式</span><span class="sxs-lookup"><span data-stu-id="13654-491">Format</span></span>

<span data-ttu-id="13654-492">不含空格和分隔字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="13654-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-493">模式</span><span class="sxs-lookup"><span data-stu-id="13654-493">Pattern</span></span>

 <span data-ttu-id="13654-494">八位數</span><span class="sxs-lookup"><span data-stu-id="13654-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="13654-495">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-495">Checksum</span></span>

<span data-ttu-id="13654-496">否</span><span class="sxs-lookup"><span data-stu-id="13654-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-497">定義</span><span class="sxs-lookup"><span data-stu-id="13654-497">Definition</span></span>

<span data-ttu-id="13654-498">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-499">規則運算式`Regex_lithuania_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-500">從關鍵字`Keywords_lithuania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-501">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-501">Keywords</span></span>

<span data-ttu-id="13654-502">| |</span><span class="sxs-lookup"><span data-stu-id="13654-502"></span></span>
|<span data-ttu-id="13654-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-504">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-504">dl#</span></span>  <br/> <span data-ttu-id="13654-505">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-505">driver license</span></span>  <br/> <span data-ttu-id="13654-506">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-506">driver license number</span></span>  <br/> <span data-ttu-id="13654-507">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-507">driver licence</span></span>  <br/> <span data-ttu-id="13654-508">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-508">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-509">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-509">drivers license</span></span>  <br/> <span data-ttu-id="13654-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-510">drivers licence</span></span>  <br/> <span data-ttu-id="13654-511">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-511">driver's license</span></span>  <br/> <span data-ttu-id="13654-512">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-512">driver's license number</span></span>  <br/> <span data-ttu-id="13654-513">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-513">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-514">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-514">driving license number</span></span>  <br/> <span data-ttu-id="13654-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-515">dlno#</span></span>  <br/> <span data-ttu-id="13654-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="13654-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="13654-517">盧森堡</span><span class="sxs-lookup"><span data-stu-id="13654-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="13654-518">格式</span><span class="sxs-lookup"><span data-stu-id="13654-518">Format</span></span>

<span data-ttu-id="13654-519">不含空格和分隔符號 6 位數</span><span class="sxs-lookup"><span data-stu-id="13654-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-520">模式</span><span class="sxs-lookup"><span data-stu-id="13654-520">Pattern</span></span>

 <span data-ttu-id="13654-521">六位數</span><span class="sxs-lookup"><span data-stu-id="13654-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="13654-522">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-522">Checksum</span></span>

<span data-ttu-id="13654-523">否</span><span class="sxs-lookup"><span data-stu-id="13654-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-524">定義</span><span class="sxs-lookup"><span data-stu-id="13654-524">Definition</span></span>

<span data-ttu-id="13654-525">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-526">規則運算式`Regex_luxemburg_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-527">從關鍵字`Keywords_luxemburg_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-528">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-528">Keywords</span></span>

<span data-ttu-id="13654-529">| |</span><span class="sxs-lookup"><span data-stu-id="13654-529"></span></span>
|<span data-ttu-id="13654-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-531">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-531">dl#</span></span>  <br/> <span data-ttu-id="13654-532">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-532">driver license</span></span>  <br/> <span data-ttu-id="13654-533">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-533">driver license number</span></span>  <br/> <span data-ttu-id="13654-534">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-534">driver licence</span></span>  <br/> <span data-ttu-id="13654-535">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-535">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-536">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-536">drivers license</span></span>  <br/> <span data-ttu-id="13654-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-537">drivers licence</span></span>  <br/> <span data-ttu-id="13654-538">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-538">driver's license</span></span>  <br/> <span data-ttu-id="13654-539">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-539">driver's license number</span></span>  <br/> <span data-ttu-id="13654-540">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-540">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-541">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-541">driving license number</span></span>  <br/> <span data-ttu-id="13654-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-542">dlno#</span></span>  <br/> <span data-ttu-id="13654-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="13654-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="13654-544">馬爾他</span><span class="sxs-lookup"><span data-stu-id="13654-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="13654-545">格式</span><span class="sxs-lookup"><span data-stu-id="13654-545">Format</span></span>

<span data-ttu-id="13654-546">兩個字元和六個中指定的型態的數字的組合</span><span class="sxs-lookup"><span data-stu-id="13654-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-547">模式</span><span class="sxs-lookup"><span data-stu-id="13654-547">Pattern</span></span>

<span data-ttu-id="13654-548">兩個字元和 6 位數的組合：</span><span class="sxs-lookup"><span data-stu-id="13654-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="13654-549">兩個字元 （數字或字母、 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="13654-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="13654-550">一個空格 (選用)</span><span class="sxs-lookup"><span data-stu-id="13654-550">A space (optional)</span></span>
    
- <span data-ttu-id="13654-551">三位數</span><span class="sxs-lookup"><span data-stu-id="13654-551">Three digits</span></span>
    
- <span data-ttu-id="13654-552">一個空格 (選用)</span><span class="sxs-lookup"><span data-stu-id="13654-552">A space (optional)</span></span>
    
- <span data-ttu-id="13654-553">三位數</span><span class="sxs-lookup"><span data-stu-id="13654-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="13654-554">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-554">Checksum</span></span>

<span data-ttu-id="13654-555">否</span><span class="sxs-lookup"><span data-stu-id="13654-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-556">定義</span><span class="sxs-lookup"><span data-stu-id="13654-556">Definition</span></span>

<span data-ttu-id="13654-557">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-558">規則運算式`Regex_malta_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-559">從關鍵字`Keywords_malta_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-560">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-560">Keywords</span></span>

<span data-ttu-id="13654-561">| |</span><span class="sxs-lookup"><span data-stu-id="13654-561"></span></span>
|<span data-ttu-id="13654-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-563">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-563">dl#</span></span>  <br/> <span data-ttu-id="13654-564">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-564">driver license</span></span>  <br/> <span data-ttu-id="13654-565">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-565">driver license number</span></span>  <br/> <span data-ttu-id="13654-566">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-566">driver licence</span></span>  <br/> <span data-ttu-id="13654-567">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-567">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-568">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-568">drivers license</span></span>  <br/> <span data-ttu-id="13654-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-569">drivers licence</span></span>  <br/> <span data-ttu-id="13654-570">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-570">driver's license</span></span>  <br/> <span data-ttu-id="13654-571">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-571">driver's license number</span></span>  <br/> <span data-ttu-id="13654-572">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-572">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-573">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-573">driving license number</span></span>  <br/> <span data-ttu-id="13654-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-574">dlno#</span></span>  <br/> <span data-ttu-id="13654-575">liċenzja tas sewqan</span><span class="sxs-lookup"><span data-stu-id="13654-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="13654-576">荷蘭</span><span class="sxs-lookup"><span data-stu-id="13654-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="13654-577">格式</span><span class="sxs-lookup"><span data-stu-id="13654-577">Format</span></span>

<span data-ttu-id="13654-578">不含空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="13654-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-579">模式</span><span class="sxs-lookup"><span data-stu-id="13654-579">Pattern</span></span>

<span data-ttu-id="13654-580">10 位數</span><span class="sxs-lookup"><span data-stu-id="13654-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="13654-581">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-581">Checksum</span></span>

<span data-ttu-id="13654-582">否</span><span class="sxs-lookup"><span data-stu-id="13654-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-583">定義</span><span class="sxs-lookup"><span data-stu-id="13654-583">Definition</span></span>

<span data-ttu-id="13654-584">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-585">規則運算式`Regex_netherlands_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-586">從關鍵字`Keywords_netherlands_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-587">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-587">Keywords</span></span>

<span data-ttu-id="13654-588">| |</span><span class="sxs-lookup"><span data-stu-id="13654-588"></span></span>
|<span data-ttu-id="13654-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-590">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-590">dl#</span></span>  <br/> <span data-ttu-id="13654-591">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-591">driver license</span></span>  <br/> <span data-ttu-id="13654-592">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-592">driver license number</span></span>  <br/> <span data-ttu-id="13654-593">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-593">driver licence</span></span>  <br/> <span data-ttu-id="13654-594">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-594">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-595">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-595">drivers license</span></span>  <br/> <span data-ttu-id="13654-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-596">drivers licence</span></span>  <br/> <span data-ttu-id="13654-597">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-597">driver's license</span></span>  <br/> <span data-ttu-id="13654-598">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-598">driver's license number</span></span>  <br/> <span data-ttu-id="13654-599">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-599">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-600">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-600">driving license number</span></span>  <br/> <span data-ttu-id="13654-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-601">dlno#</span></span>  <br/> <span data-ttu-id="13654-602">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="13654-602">permis de conduire</span></span>  <br/> <span data-ttu-id="13654-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="13654-603">rijbewijs</span></span>  <br/> <span data-ttu-id="13654-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="13654-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="13654-605">波蘭</span><span class="sxs-lookup"><span data-stu-id="13654-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="13654-606">格式</span><span class="sxs-lookup"><span data-stu-id="13654-606">Format</span></span>

<span data-ttu-id="13654-607">包含 2 正斜線的數字 14</span><span class="sxs-lookup"><span data-stu-id="13654-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-608">模式</span><span class="sxs-lookup"><span data-stu-id="13654-608">Pattern</span></span>

<span data-ttu-id="13654-609">14 的數字及 2 的正斜線：</span><span class="sxs-lookup"><span data-stu-id="13654-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="13654-610">五位數</span><span class="sxs-lookup"><span data-stu-id="13654-610">Five digits</span></span> 
    
- <span data-ttu-id="13654-611">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="13654-611">A forward slash</span></span>
    
- <span data-ttu-id="13654-612">兩位數</span><span class="sxs-lookup"><span data-stu-id="13654-612">Two digits</span></span>
    
- <span data-ttu-id="13654-613">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="13654-613">A forward slash</span></span>
    
- <span data-ttu-id="13654-614">七位數</span><span class="sxs-lookup"><span data-stu-id="13654-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="13654-615">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-615">Checksum</span></span>

<span data-ttu-id="13654-616">否</span><span class="sxs-lookup"><span data-stu-id="13654-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-617">定義</span><span class="sxs-lookup"><span data-stu-id="13654-617">Definition</span></span>

<span data-ttu-id="13654-618">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-619">規則運算式`Regex_poland_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-620">從關鍵字`Keywords_poland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-621">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-621">Keywords</span></span>

<span data-ttu-id="13654-622">| |</span><span class="sxs-lookup"><span data-stu-id="13654-622"></span></span>
|<span data-ttu-id="13654-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-624">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-624">dl#</span></span>  <br/> <span data-ttu-id="13654-625">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-625">driver license</span></span>  <br/> <span data-ttu-id="13654-626">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-626">driver license number</span></span>  <br/> <span data-ttu-id="13654-627">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-627">driver licence</span></span>  <br/> <span data-ttu-id="13654-628">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-628">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-629">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-629">drivers license</span></span>  <br/> <span data-ttu-id="13654-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-630">drivers licence</span></span>  <br/> <span data-ttu-id="13654-631">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-631">driver's license</span></span>  <br/> <span data-ttu-id="13654-632">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-632">driver's license number</span></span>  <br/> <span data-ttu-id="13654-633">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-633">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-634">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-634">driving license number</span></span>  <br/> <span data-ttu-id="13654-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-635">dlno#</span></span>  <br/> <span data-ttu-id="13654-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="13654-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="13654-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="13654-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="13654-638">格式</span><span class="sxs-lookup"><span data-stu-id="13654-638">Format</span></span>

<span data-ttu-id="13654-639">接在指定的型態七個字的兩個字母</span><span class="sxs-lookup"><span data-stu-id="13654-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-640">模式</span><span class="sxs-lookup"><span data-stu-id="13654-640">Pattern</span></span>

<span data-ttu-id="13654-641">兩個字母後面接著七個字特殊字元：</span><span class="sxs-lookup"><span data-stu-id="13654-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="13654-642">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="13654-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="13654-643">一個連字號</span><span class="sxs-lookup"><span data-stu-id="13654-643">A hyphen</span></span>
    
- <span data-ttu-id="13654-644">六位數</span><span class="sxs-lookup"><span data-stu-id="13654-644">Six digits</span></span>
    
- <span data-ttu-id="13654-645">一個空格</span><span class="sxs-lookup"><span data-stu-id="13654-645">A space</span></span>
    
- <span data-ttu-id="13654-646">一個數字</span><span class="sxs-lookup"><span data-stu-id="13654-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="13654-647">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-647">Checksum</span></span>

<span data-ttu-id="13654-648">否</span><span class="sxs-lookup"><span data-stu-id="13654-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-649">定義</span><span class="sxs-lookup"><span data-stu-id="13654-649">Definition</span></span>

<span data-ttu-id="13654-650">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-651">規則運算式`Regex_portugal_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-652">從關鍵字`Keywords_portugal_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-653">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-653">Keywords</span></span>

<span data-ttu-id="13654-654">| |</span><span class="sxs-lookup"><span data-stu-id="13654-654"></span></span>
|<span data-ttu-id="13654-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-656">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-656">dl#</span></span>  <br/> <span data-ttu-id="13654-657">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-657">driver license</span></span>  <br/> <span data-ttu-id="13654-658">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-658">driver license number</span></span>  <br/> <span data-ttu-id="13654-659">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-659">driver licence</span></span>  <br/> <span data-ttu-id="13654-660">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-660">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-661">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-661">drivers license</span></span>  <br/> <span data-ttu-id="13654-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-662">drivers licence</span></span>  <br/> <span data-ttu-id="13654-663">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-663">driver's license</span></span>  <br/> <span data-ttu-id="13654-664">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-664">driver's license number</span></span>  <br/> <span data-ttu-id="13654-665">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-665">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-666">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-666">driving license number</span></span>  <br/> <span data-ttu-id="13654-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-667">dlno#</span></span>  <br/> <span data-ttu-id="13654-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="13654-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="13654-669">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="13654-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="13654-670">格式</span><span class="sxs-lookup"><span data-stu-id="13654-670">Format</span></span>

<span data-ttu-id="13654-671">一個接八個字的字元</span><span class="sxs-lookup"><span data-stu-id="13654-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-672">模式</span><span class="sxs-lookup"><span data-stu-id="13654-672">Pattern</span></span>

<span data-ttu-id="13654-673">後面接著八個位數字的一個字元：</span><span class="sxs-lookup"><span data-stu-id="13654-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="13654-674">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="13654-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="13654-675">八位數</span><span class="sxs-lookup"><span data-stu-id="13654-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="13654-676">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-676">Checksum</span></span>

<span data-ttu-id="13654-677">否</span><span class="sxs-lookup"><span data-stu-id="13654-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-678">定義</span><span class="sxs-lookup"><span data-stu-id="13654-678">Definition</span></span>

<span data-ttu-id="13654-679">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-680">規則運算式`Regex_romania_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-681">從關鍵字`Keywords_romania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-682">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-682">Keywords</span></span>

<span data-ttu-id="13654-683">| |</span><span class="sxs-lookup"><span data-stu-id="13654-683"></span></span>
|<span data-ttu-id="13654-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-685">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-685">dl#</span></span>  <br/> <span data-ttu-id="13654-686">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-686">driver license</span></span>  <br/> <span data-ttu-id="13654-687">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-687">driver license number</span></span>  <br/> <span data-ttu-id="13654-688">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-688">driver licence</span></span>  <br/> <span data-ttu-id="13654-689">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-689">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-690">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-690">drivers license</span></span>  <br/> <span data-ttu-id="13654-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-691">drivers licence</span></span>  <br/> <span data-ttu-id="13654-692">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-692">driver's license</span></span>  <br/> <span data-ttu-id="13654-693">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-693">driver's license number</span></span>  <br/> <span data-ttu-id="13654-694">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-694">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-695">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-695">driving license number</span></span>  <br/> <span data-ttu-id="13654-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-696">dlno#</span></span>  <br/> <span data-ttu-id="13654-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="13654-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="13654-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="13654-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="13654-699">格式</span><span class="sxs-lookup"><span data-stu-id="13654-699">Format</span></span>

<span data-ttu-id="13654-700">一個後面七位數字的字元</span><span class="sxs-lookup"><span data-stu-id="13654-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-701">模式</span><span class="sxs-lookup"><span data-stu-id="13654-701">Pattern</span></span>

<span data-ttu-id="13654-702">一個後面七位數字的字元</span><span class="sxs-lookup"><span data-stu-id="13654-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="13654-703">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="13654-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="13654-704">七位數</span><span class="sxs-lookup"><span data-stu-id="13654-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="13654-705">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-705">Checksum</span></span>

<span data-ttu-id="13654-706">否</span><span class="sxs-lookup"><span data-stu-id="13654-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-707">定義</span><span class="sxs-lookup"><span data-stu-id="13654-707">Definition</span></span>

<span data-ttu-id="13654-708">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-709">規則運算式`Regex_slovakia_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-710">從關鍵字`Keywords_slovakia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-711">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-711">Keywords</span></span>

<span data-ttu-id="13654-712">| |</span><span class="sxs-lookup"><span data-stu-id="13654-712"></span></span>
|<span data-ttu-id="13654-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-714">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-714">dl#</span></span>  <br/> <span data-ttu-id="13654-715">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-715">driver license</span></span>  <br/> <span data-ttu-id="13654-716">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-716">driver license number</span></span>  <br/> <span data-ttu-id="13654-717">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-717">driver licence</span></span>  <br/> <span data-ttu-id="13654-718">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-718">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-719">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-719">drivers license</span></span>  <br/> <span data-ttu-id="13654-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-720">drivers licence</span></span>  <br/> <span data-ttu-id="13654-721">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-721">driver's license</span></span>  <br/> <span data-ttu-id="13654-722">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-722">driver's license number</span></span>  <br/> <span data-ttu-id="13654-723">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-723">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-724">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-724">driving license number</span></span>  <br/> <span data-ttu-id="13654-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-725">dlno#</span></span>  <br/> <span data-ttu-id="13654-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="13654-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="13654-727">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="13654-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="13654-728">格式</span><span class="sxs-lookup"><span data-stu-id="13654-728">Format</span></span>

<span data-ttu-id="13654-729">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="13654-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-730">模式</span><span class="sxs-lookup"><span data-stu-id="13654-730">Pattern</span></span>

<span data-ttu-id="13654-731">九位數</span><span class="sxs-lookup"><span data-stu-id="13654-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="13654-732">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-732">Checksum</span></span>

<span data-ttu-id="13654-733">否</span><span class="sxs-lookup"><span data-stu-id="13654-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-734">定義</span><span class="sxs-lookup"><span data-stu-id="13654-734">Definition</span></span>

<span data-ttu-id="13654-735">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-736">規則運算式`Regex_slovenia_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-737">從關鍵字`Keywords_slovenia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-738">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-738">Keywords</span></span>

<span data-ttu-id="13654-739">| |</span><span class="sxs-lookup"><span data-stu-id="13654-739"></span></span>
|<span data-ttu-id="13654-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-741">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-741">dl#</span></span>  <br/> <span data-ttu-id="13654-742">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-742">driver license</span></span>  <br/> <span data-ttu-id="13654-743">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-743">driver license number</span></span>  <br/> <span data-ttu-id="13654-744">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-744">driver licence</span></span>  <br/> <span data-ttu-id="13654-745">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-745">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-746">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-746">drivers license</span></span>  <br/> <span data-ttu-id="13654-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-747">drivers licence</span></span>  <br/> <span data-ttu-id="13654-748">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-748">driver's license</span></span>  <br/> <span data-ttu-id="13654-749">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-749">driver's license number</span></span>  <br/> <span data-ttu-id="13654-750">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-750">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-751">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-751">driving license number</span></span>  <br/> <span data-ttu-id="13654-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-752">dlno#</span></span>  <br/> <span data-ttu-id="13654-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="13654-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="13654-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="13654-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="13654-755">格式</span><span class="sxs-lookup"><span data-stu-id="13654-755">Format</span></span>

<span data-ttu-id="13654-756">後面接著一個字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="13654-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-757">模式</span><span class="sxs-lookup"><span data-stu-id="13654-757">Pattern</span></span>

<span data-ttu-id="13654-758">後面接著一個字元的八個位數：</span><span class="sxs-lookup"><span data-stu-id="13654-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="13654-759">八位數</span><span class="sxs-lookup"><span data-stu-id="13654-759">Eight digits</span></span> 
    
- <span data-ttu-id="13654-760">一個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="13654-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="13654-761">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-761">Checksum</span></span>

<span data-ttu-id="13654-762">是</span><span class="sxs-lookup"><span data-stu-id="13654-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-763">定義</span><span class="sxs-lookup"><span data-stu-id="13654-763">Definition</span></span>

<span data-ttu-id="13654-764">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-765">此函數`Func_spain_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-766">從關鍵字`Keywords_spain_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13654-767">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-767">Keywords</span></span>

<span data-ttu-id="13654-768">| |</span><span class="sxs-lookup"><span data-stu-id="13654-768"></span></span>
|<span data-ttu-id="13654-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-770">dlno#</span></span>  <br/> <span data-ttu-id="13654-771">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-771">dl#</span></span>  <br/> <span data-ttu-id="13654-772">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-772">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-773">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-773">driver licence</span></span>  <br/> <span data-ttu-id="13654-774">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-774">driver license</span></span>  <br/> <span data-ttu-id="13654-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-775">drivers licence</span></span>  <br/> <span data-ttu-id="13654-776">
drivers license</span><span class="sxs-lookup"><span data-stu-id="13654-776">drivers license</span></span>  <br/> <span data-ttu-id="13654-777">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="13654-777">driver's licence</span></span>  <br/> <span data-ttu-id="13654-778">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-778">driver's license</span></span>  <br/> <span data-ttu-id="13654-779">driving licence
</span><span class="sxs-lookup"><span data-stu-id="13654-779">driving licence</span></span>  <br/> <span data-ttu-id="13654-780">主導授權</span><span class="sxs-lookup"><span data-stu-id="13654-780">driving license</span></span>  <br/> <span data-ttu-id="13654-781">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-781">driver licence number</span></span>  <br/> <span data-ttu-id="13654-782">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-782">driver license number</span></span>  <br/> <span data-ttu-id="13654-783">發行的驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-783">drivers licence number</span></span>  <br/> <span data-ttu-id="13654-784">發行的驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-784">drivers license number</span></span>  <br/> <span data-ttu-id="13654-785">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-785">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-786">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-786">driver's license number</span></span>  <br/> <span data-ttu-id="13654-787">driving 授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-787">driving licence number</span></span>  <br/> <span data-ttu-id="13654-788">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-788">driving license number</span></span>  <br/> <span data-ttu-id="13654-789">主導使用權限</span><span class="sxs-lookup"><span data-stu-id="13654-789">driving permit</span></span>  <br/> <span data-ttu-id="13654-790">主導使用權限數字</span><span class="sxs-lookup"><span data-stu-id="13654-790">driving permit number</span></span>  <br/> <span data-ttu-id="13654-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="13654-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="13654-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="13654-792">permiso conducción</span></span>  <br/> <span data-ttu-id="13654-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="13654-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="13654-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="13654-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="13654-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="13654-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="13654-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="13654-796">licencia conducir</span></span>  <br/> <span data-ttu-id="13654-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="13654-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="13654-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="13654-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="13654-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="13654-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="13654-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="13654-800">permiso conducir</span></span>  <br/> <span data-ttu-id="13654-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="13654-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="13654-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="13654-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="13654-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="13654-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="13654-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="13654-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="13654-805">格式</span><span class="sxs-lookup"><span data-stu-id="13654-805">Format</span></span>

<span data-ttu-id="13654-806">十個包含連字號的數字</span><span class="sxs-lookup"><span data-stu-id="13654-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="13654-807">模式</span><span class="sxs-lookup"><span data-stu-id="13654-807">Pattern</span></span>

<span data-ttu-id="13654-808">包含連字號十位數：</span><span class="sxs-lookup"><span data-stu-id="13654-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="13654-809">六位數</span><span class="sxs-lookup"><span data-stu-id="13654-809">Six digits</span></span> 
    
- <span data-ttu-id="13654-810">一個連字號</span><span class="sxs-lookup"><span data-stu-id="13654-810">A hyphen</span></span>
    
- <span data-ttu-id="13654-811">四位數</span><span class="sxs-lookup"><span data-stu-id="13654-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="13654-812">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="13654-812">Checksum</span></span>

<span data-ttu-id="13654-813">否</span><span class="sxs-lookup"><span data-stu-id="13654-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="13654-814">定義</span><span class="sxs-lookup"><span data-stu-id="13654-814">Definition</span></span>

<span data-ttu-id="13654-815">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="13654-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="13654-816">規則運算式`Regex_sweden_eu_driver's_license_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="13654-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="13654-817">從關鍵字`Keywords_sweden_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="13654-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="13654-818">關鍵字</span><span class="sxs-lookup"><span data-stu-id="13654-818">Keywords</span></span>

<span data-ttu-id="13654-819">| |</span><span class="sxs-lookup"><span data-stu-id="13654-819"></span></span>
|<span data-ttu-id="13654-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="13654-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="13654-821">dl #</span><span class="sxs-lookup"><span data-stu-id="13654-821">dl#</span></span>  <br/> <span data-ttu-id="13654-822">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-822">driver license</span></span>  <br/> <span data-ttu-id="13654-823">驅動程式照編號</span><span class="sxs-lookup"><span data-stu-id="13654-823">driver license number</span></span>  <br/> <span data-ttu-id="13654-824">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-824">driver licence</span></span>  <br/> <span data-ttu-id="13654-825">發行的驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="13654-825">drivers lic.</span></span>  <br/> <span data-ttu-id="13654-826">發行的驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="13654-826">drivers license</span></span>  <br/> <span data-ttu-id="13654-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13654-827">drivers licence</span></span>  <br/> <span data-ttu-id="13654-828">駕照</span><span class="sxs-lookup"><span data-stu-id="13654-828">driver's license</span></span>  <br/> <span data-ttu-id="13654-829">駕照編號</span><span class="sxs-lookup"><span data-stu-id="13654-829">driver's license number</span></span>  <br/> <span data-ttu-id="13654-830">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="13654-830">driver's licence number</span></span>  <br/> <span data-ttu-id="13654-831">主導照編號</span><span class="sxs-lookup"><span data-stu-id="13654-831">driving license number</span></span>  <br/> <span data-ttu-id="13654-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="13654-832">dlno#</span></span>  <br/> <span data-ttu-id="13654-833">körkort</span><span class="sxs-lookup"><span data-stu-id="13654-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="13654-834">英國</span><span class="sxs-lookup"><span data-stu-id="13654-834">UK</span></span>

<span data-ttu-id="13654-p103">如需詳細資訊，請參閱節"英國駕照編號 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="13654-p103">For details, see the section "U.K. Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="13654-837">另請參閱</span><span class="sxs-lookup"><span data-stu-id="13654-837">See also</span></span>

[<span data-ttu-id="13654-838">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="13654-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

