---
title: 歐盟駕照編號
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟駕駛執照號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152975"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="78aa8-104">歐盟駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-104">EU Driver's License Number</span></span>

<span data-ttu-id="78aa8-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟駕駛執照號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="78aa8-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="78aa8-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="78aa8-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="78aa8-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="78aa8-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-108">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-108">Format</span></span>

<span data-ttu-id="78aa8-109">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-110">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-110">Pattern</span></span>

<span data-ttu-id="78aa8-111">八位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="78aa8-112">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-112">Checksum</span></span>

<span data-ttu-id="78aa8-113">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-114">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-114">Definition</span></span>

<span data-ttu-id="78aa8-115">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-116">規則運算式`Regex_austria_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-117">從關鍵字`Keywords_austria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="78aa8-118">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-118">Keywords</span></span>

<span data-ttu-id="78aa8-119">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-119"></span></span>
|<span data-ttu-id="78aa8-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-121">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-121">dl#</span></span>  <br/> <span data-ttu-id="78aa8-122">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-122">driver license</span></span>  <br/> <span data-ttu-id="78aa8-123">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-123">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-124">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-124">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-125">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-125">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-126">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-126">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-127">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-127">driver's licence</span></span>  <br/> <span data-ttu-id="78aa8-128">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-128">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-129">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-129">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-130">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="78aa8-131">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-131">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-132">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="78aa8-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="78aa8-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="78aa8-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="78aa8-135">比利時</span><span class="sxs-lookup"><span data-stu-id="78aa8-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-136">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-136">Format</span></span>

<span data-ttu-id="78aa8-137">如果沒有空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-138">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-138">Pattern</span></span>

<span data-ttu-id="78aa8-139">10 位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="78aa8-140">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-140">Checksum</span></span>

<span data-ttu-id="78aa8-141">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-142">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-142">Definition</span></span>

<span data-ttu-id="78aa8-143">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-144">規則運算式`Regex_belgium_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-145">從關鍵字`Keywords_belgium_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="78aa8-146">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-146">Keywords</span></span>

<span data-ttu-id="78aa8-147">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-147"></span></span>
|<span data-ttu-id="78aa8-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-149">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-149">dl#</span></span>  <br/> <span data-ttu-id="78aa8-150">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-150">driver license</span></span>  <br/> <span data-ttu-id="78aa8-151">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-151">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-152">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-152">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-153">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-153">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-154">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-154">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-155">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-155">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-156">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-156">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-157">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-157">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-158">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-158">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-159">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="78aa8-160">rijbewijs</span></span>  <br/> <span data-ttu-id="78aa8-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="78aa8-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="78aa8-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="78aa8-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="78aa8-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="78aa8-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="78aa8-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="78aa8-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="78aa8-165">führerschein 編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="78aa8-166">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="78aa8-167">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="78aa8-168">保加利亞</span><span class="sxs-lookup"><span data-stu-id="78aa8-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-169">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-169">Format</span></span>

<span data-ttu-id="78aa8-170">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-171">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-171">Pattern</span></span>

<span data-ttu-id="78aa8-172">九位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="78aa8-173">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-173">Checksum</span></span>

<span data-ttu-id="78aa8-174">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-175">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-175">Definition</span></span>

<span data-ttu-id="78aa8-176">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-177">規則運算式`Regex_bulgaria_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-178">從關鍵字`Keywords_bulgaria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="78aa8-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-179">Keywords</span></span>

<span data-ttu-id="78aa8-180">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-180"></span></span>
|<span data-ttu-id="78aa8-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-182">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-182">dl#</span></span>  <br/> <span data-ttu-id="78aa8-183">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-183">driver license</span></span>  <br/> <span data-ttu-id="78aa8-184">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-184">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-185">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-185">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-186">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-186">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-187">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-187">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-188">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-188">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-189">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-189">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-190">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-190">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-191">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-191">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-192">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-192">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-193">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-194">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МПС</span><span class="sxs-lookup"><span data-stu-id="78aa8-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="78aa8-195">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО</span><span class="sxs-lookup"><span data-stu-id="78aa8-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="78aa8-196">СУМПС</span><span class="sxs-lookup"><span data-stu-id="78aa8-196">сумпс</span></span>  <br/> <span data-ttu-id="78aa8-197">ШОФЬОРСКА КНИЖКА</span><span class="sxs-lookup"><span data-stu-id="78aa8-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="78aa8-198">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="78aa8-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-199">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-199">Format</span></span>

<span data-ttu-id="78aa8-200">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-201">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-201">Pattern</span></span>

<span data-ttu-id="78aa8-202">八位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="78aa8-203">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-203">Checksum</span></span>

<span data-ttu-id="78aa8-204">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-205">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-205">Definition</span></span>

<span data-ttu-id="78aa8-206">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-207">規則運算式`Regex_croatia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-208">從關鍵字`Keywords_croatia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="78aa8-209">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-209">Keywords</span></span>

<span data-ttu-id="78aa8-210">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-210"></span></span>
|<span data-ttu-id="78aa8-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-212">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-212">dl#</span></span>  <br/> <span data-ttu-id="78aa8-213">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-213">driver license</span></span>  <br/> <span data-ttu-id="78aa8-214">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-214">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-215">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-215">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-216">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-216">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-217">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-217">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-218">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-218">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-219">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-219">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-220">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-220">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-221">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-221">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-222">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-222">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-223">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="78aa8-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="78aa8-225">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="78aa8-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-226">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-226">Format</span></span>

<span data-ttu-id="78aa8-227">如果沒有空格和分隔符號的 12 位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-228">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-228">Pattern</span></span>

<span data-ttu-id="78aa8-229">12 位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="78aa8-230">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-230">Checksum</span></span>

<span data-ttu-id="78aa8-231">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-232">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-232">Definition</span></span>

<span data-ttu-id="78aa8-233">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-234">規則運算式`Regex_cyprus_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-235">從關鍵字`Keywords_cyprus_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-236">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-236">Keywords</span></span>

<span data-ttu-id="78aa8-237">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-237"></span></span>
|<span data-ttu-id="78aa8-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-239">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-239">dl#</span></span>  <br/> <span data-ttu-id="78aa8-240">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-240">driver license</span></span>  <br/> <span data-ttu-id="78aa8-241">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-241">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-242">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-242">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-243">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-243">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-244">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-244">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-245">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-245">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-246">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-246">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-247">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-247">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-248">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-248">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-249">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-250">ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="78aa8-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="78aa8-251">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="78aa8-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-252">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-252">Format</span></span>

<span data-ttu-id="78aa8-253">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-254">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-254">Pattern</span></span>

<span data-ttu-id="78aa8-255">八個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="78aa8-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="78aa8-256">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="78aa8-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="78aa8-257">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="78aa8-257">A space (optional)</span></span>
    
- <span data-ttu-id="78aa8-258">六位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="78aa8-259">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-259">Checksum</span></span>

<span data-ttu-id="78aa8-260">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-261">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-261">Definition</span></span>

<span data-ttu-id="78aa8-262">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-263">規則運算式`Regex_czech_republic_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-264">從關鍵字`Keywords_czech_republic_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="78aa8-265">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-265">Keywords</span></span>

<span data-ttu-id="78aa8-266">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-266"></span></span>
|<span data-ttu-id="78aa8-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-268">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-268">dl#</span></span>  <br/> <span data-ttu-id="78aa8-269">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-269">driver license</span></span>  <br/> <span data-ttu-id="78aa8-270">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-270">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-271">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-271">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-272">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-272">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-273">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-273">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-274">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-274">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-275">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-275">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-276">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-276">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-277">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-277">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-278">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-278">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-279">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-279">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-280">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-281">Řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="78aa8-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="78aa8-282">丹麥</span><span class="sxs-lookup"><span data-stu-id="78aa8-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-283">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-283">Format</span></span>

<span data-ttu-id="78aa8-284">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-285">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-285">Pattern</span></span>

<span data-ttu-id="78aa8-286">八位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="78aa8-287">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-287">Checksum</span></span>

<span data-ttu-id="78aa8-288">是</span><span class="sxs-lookup"><span data-stu-id="78aa8-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-289">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-289">Definition</span></span>

<span data-ttu-id="78aa8-290">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-291">規則運算式`Regex_denmark_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-292">從關鍵字`Keywords_denmark_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="78aa8-293">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-293">Keywords</span></span>

<span data-ttu-id="78aa8-294">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-294"></span></span>
|<span data-ttu-id="78aa8-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-296">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-296">dl#</span></span>  <br/> <span data-ttu-id="78aa8-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-297">driver license</span></span>  <br/> <span data-ttu-id="78aa8-298">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-298">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-299">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-299">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-300">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-300">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-301">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-301">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-302">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-302">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-303">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-303">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-304">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-304">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-305">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-305">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-306">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-306">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-307">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="78aa8-308">kørekort</span></span>  <br/> <span data-ttu-id="78aa8-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="78aa8-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="78aa8-310">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="78aa8-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-311">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-311">Format</span></span>

<span data-ttu-id="78aa8-312">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-313">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-313">Pattern</span></span>

<span data-ttu-id="78aa8-314">兩個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="78aa8-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="78aa8-315">字母"ET 」 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="78aa8-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="78aa8-316">六位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="78aa8-317">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-317">Checksum</span></span>

<span data-ttu-id="78aa8-318">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-319">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-319">Definition</span></span>

<span data-ttu-id="78aa8-320">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-321">規則運算式`Regex_estonia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-322">從關鍵字`Keywords_estonia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-323">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-323">Keywords</span></span>

<span data-ttu-id="78aa8-324">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-324"></span></span>
|<span data-ttu-id="78aa8-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-326">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-326">dl#</span></span>  <br/> <span data-ttu-id="78aa8-327">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-327">driver license</span></span>  <br/> <span data-ttu-id="78aa8-328">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-328">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-329">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-329">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-330">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-330">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-331">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-331">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-332">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-332">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-333">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-333">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-334">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-334">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-335">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-335">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-336">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-336">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-337">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="78aa8-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="78aa8-339">芬蘭</span><span class="sxs-lookup"><span data-stu-id="78aa8-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-340">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-340">Format</span></span>

<span data-ttu-id="78aa8-341">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="78aa8-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-342">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-342">Pattern</span></span>

<span data-ttu-id="78aa8-343">10 位數包含連字號：</span><span class="sxs-lookup"><span data-stu-id="78aa8-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="78aa8-344">六位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-344">Six digits</span></span> 
    
- <span data-ttu-id="78aa8-345">連字號</span><span class="sxs-lookup"><span data-stu-id="78aa8-345">A hyphen</span></span>
    
-  <span data-ttu-id="78aa8-346">四位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="78aa8-347">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-347">Checksum</span></span>

<span data-ttu-id="78aa8-348">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-349">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-349">Definition</span></span>

<span data-ttu-id="78aa8-350">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-351">規則運算式`Regex_finland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-352">從關鍵字`Keywords_finland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-353">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-353">Keywords</span></span>

<span data-ttu-id="78aa8-354">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-354"></span></span>
|<span data-ttu-id="78aa8-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-356">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-356">dl#</span></span>  <br/> <span data-ttu-id="78aa8-357">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-357">driver license</span></span>  <br/> <span data-ttu-id="78aa8-358">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-358">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-359">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-359">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-360">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-360">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-361">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-361">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-362">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-362">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-363">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-363">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-364">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-364">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-365">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-365">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-366">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-366">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-367">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="78aa8-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="78aa8-369">法國</span><span class="sxs-lookup"><span data-stu-id="78aa8-369">France</span></span>

<span data-ttu-id="78aa8-370">如需詳細資訊，請參閱 「 法國駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="78aa8-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="78aa8-371">德國</span><span class="sxs-lookup"><span data-stu-id="78aa8-371">Germany</span></span>

<span data-ttu-id="78aa8-372">如需詳細資訊，請參閱 「 德國駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="78aa8-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="78aa8-373">希臘</span><span class="sxs-lookup"><span data-stu-id="78aa8-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-374">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-374">Format</span></span>

<span data-ttu-id="78aa8-375">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-376">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-376">Pattern</span></span>

 <span data-ttu-id="78aa8-377">九位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="78aa8-378">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-378">Checksum</span></span>

<span data-ttu-id="78aa8-379">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-380">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-380">Definition</span></span>

<span data-ttu-id="78aa8-381">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-382">規則運算式`Regex_greece_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-383">從關鍵字`Keywords_greece_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-384">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-384">Keywords</span></span>

<span data-ttu-id="78aa8-385">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-385"></span></span>
|<span data-ttu-id="78aa8-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="78aa8-387">dlL#</span></span>  <br/> <span data-ttu-id="78aa8-388">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-388">driver license</span></span>  <br/> <span data-ttu-id="78aa8-389">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-389">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-390">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-390">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-391">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-391">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-392">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-392">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-393">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-393">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-394">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-394">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-395">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-395">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-396">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-396">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-397">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-397">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-398">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-399">ΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="78aa8-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="78aa8-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="78aa8-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="78aa8-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="78aa8-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-402">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-402">Format</span></span>

<span data-ttu-id="78aa8-403">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-404">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-404">Pattern</span></span>

<span data-ttu-id="78aa8-405">兩個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="78aa8-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="78aa8-406">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="78aa8-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="78aa8-407">六位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="78aa8-408">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-408">Checksum</span></span>

<span data-ttu-id="78aa8-409">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-410">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-410">Definition</span></span>

<span data-ttu-id="78aa8-411">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-412">規則運算式`Regex_hungary_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-413">從關鍵字`Keywords_hungary_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-414">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-414">Keywords</span></span>

<span data-ttu-id="78aa8-415">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-415"></span></span>
|<span data-ttu-id="78aa8-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-417">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-417">dl#</span></span>  <br/> <span data-ttu-id="78aa8-418">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-418">driver license</span></span>  <br/> <span data-ttu-id="78aa8-419">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-419">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-420">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-420">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-421">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-421">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-422">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-422">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-423">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-423">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-424">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-424">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-425">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-425">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-426">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-426">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-427">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-427">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-428">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="78aa8-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="78aa8-430">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="78aa8-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-431">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-431">Format</span></span>

<span data-ttu-id="78aa8-432">四個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-433">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-433">Pattern</span></span>

<span data-ttu-id="78aa8-434">六位數和四個字母：</span><span class="sxs-lookup"><span data-stu-id="78aa8-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="78aa8-435">六位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-435">Six digits</span></span>
    
- <span data-ttu-id="78aa8-436">四個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="78aa8-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="78aa8-437">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-437">Checksum</span></span>

<span data-ttu-id="78aa8-438">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-439">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-439">Definition</span></span>

<span data-ttu-id="78aa8-440">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-441">規則運算式`Regex_ireland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-442">從關鍵字`Keywords_ireland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-443">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-443">Keywords</span></span>

<span data-ttu-id="78aa8-444">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-444"></span></span>
|<span data-ttu-id="78aa8-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-446">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-446">dl#</span></span>  <br/> <span data-ttu-id="78aa8-447">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-447">driver license</span></span>  <br/> <span data-ttu-id="78aa8-448">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-448">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-449">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-449">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-450">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-450">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-451">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-451">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-452">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-452">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-453">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-453">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-454">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-454">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-455">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-455">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-456">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-456">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-457">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="78aa8-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="78aa8-459">義大利</span><span class="sxs-lookup"><span data-stu-id="78aa8-459">Italy</span></span>

<span data-ttu-id="78aa8-460">如需詳細資訊，請參閱 「 義大利駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="78aa8-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="78aa8-461">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="78aa8-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-462">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-462">Format</span></span>

<span data-ttu-id="78aa8-463">三個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-464">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-464">Pattern</span></span>

<span data-ttu-id="78aa8-465">三個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="78aa8-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="78aa8-466">三個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="78aa8-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="78aa8-467">六位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="78aa8-468">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-468">Checksum</span></span>

<span data-ttu-id="78aa8-469">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-470">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-470">Definition</span></span>

<span data-ttu-id="78aa8-471">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-472">規則運算式`Regex_latvia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-473">從關鍵字`Keywords_latvia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-474">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-474">Keywords</span></span>

<span data-ttu-id="78aa8-475">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-475"></span></span>
|<span data-ttu-id="78aa8-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-477">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-477">dl#</span></span>  <br/> <span data-ttu-id="78aa8-478">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-478">driver license</span></span>  <br/> <span data-ttu-id="78aa8-479">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-479">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-480">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-480">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-481">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-481">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-482">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-482">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-483">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-483">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-484">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-484">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-485">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-485">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-486">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-486">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-487">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-487">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-488">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="78aa8-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="78aa8-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="78aa8-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-491">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-491">Format</span></span>

<span data-ttu-id="78aa8-492">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-493">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-493">Pattern</span></span>

 <span data-ttu-id="78aa8-494">八位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="78aa8-495">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-495">Checksum</span></span>

<span data-ttu-id="78aa8-496">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-497">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-497">Definition</span></span>

<span data-ttu-id="78aa8-498">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-499">規則運算式`Regex_lithuania_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-500">從關鍵字`Keywords_lithuania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-501">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-501">Keywords</span></span>

<span data-ttu-id="78aa8-502">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-502"></span></span>
|<span data-ttu-id="78aa8-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-504">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-504">dl#</span></span>  <br/> <span data-ttu-id="78aa8-505">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-505">driver license</span></span>  <br/> <span data-ttu-id="78aa8-506">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-506">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-507">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-507">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-508">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-508">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-509">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-509">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-510">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-510">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-511">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-511">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-512">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-512">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-513">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-513">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-514">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-514">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-515">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="78aa8-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="78aa8-517">盧森堡</span><span class="sxs-lookup"><span data-stu-id="78aa8-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-518">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-518">Format</span></span>

<span data-ttu-id="78aa8-519">六位數，代表不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="78aa8-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-520">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-520">Pattern</span></span>

 <span data-ttu-id="78aa8-521">六位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="78aa8-522">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-522">Checksum</span></span>

<span data-ttu-id="78aa8-523">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-524">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-524">Definition</span></span>

<span data-ttu-id="78aa8-525">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-526">規則運算式`Regex_luxemburg_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-527">從關鍵字`Keywords_luxemburg_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-528">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-528">Keywords</span></span>

<span data-ttu-id="78aa8-529">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-529"></span></span>
|<span data-ttu-id="78aa8-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-531">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-531">dl#</span></span>  <br/> <span data-ttu-id="78aa8-532">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-532">driver license</span></span>  <br/> <span data-ttu-id="78aa8-533">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-533">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-534">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-534">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-535">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-535">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-536">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-536">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-537">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-537">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-538">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-538">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-539">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-539">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-540">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-540">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-541">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-541">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-542">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="78aa8-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="78aa8-544">馬爾他</span><span class="sxs-lookup"><span data-stu-id="78aa8-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-545">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-545">Format</span></span>

<span data-ttu-id="78aa8-546">兩個字元和六位數，代表所指定的型態的組合</span><span class="sxs-lookup"><span data-stu-id="78aa8-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-547">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-547">Pattern</span></span>

<span data-ttu-id="78aa8-548">兩個字元和六位數的組合：</span><span class="sxs-lookup"><span data-stu-id="78aa8-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="78aa8-549">兩個字元 （數字或字母、 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="78aa8-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="78aa8-550">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="78aa8-550">A space (optional)</span></span>
    
- <span data-ttu-id="78aa8-551">三位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-551">Three digits</span></span>
    
- <span data-ttu-id="78aa8-552">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="78aa8-552">A space (optional)</span></span>
    
- <span data-ttu-id="78aa8-553">三位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="78aa8-554">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-554">Checksum</span></span>

<span data-ttu-id="78aa8-555">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-556">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-556">Definition</span></span>

<span data-ttu-id="78aa8-557">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-558">規則運算式`Regex_malta_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-559">從關鍵字`Keywords_malta_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-560">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-560">Keywords</span></span>

<span data-ttu-id="78aa8-561">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-561"></span></span>
|<span data-ttu-id="78aa8-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-563">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-563">dl#</span></span>  <br/> <span data-ttu-id="78aa8-564">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-564">driver license</span></span>  <br/> <span data-ttu-id="78aa8-565">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-565">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-566">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-566">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-567">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-567">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-568">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-568">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-569">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-569">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-570">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-570">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-571">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-571">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-572">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-572">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-573">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-573">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-574">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-575">liċenzja 塔司 sewqan</span><span class="sxs-lookup"><span data-stu-id="78aa8-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="78aa8-576">荷蘭</span><span class="sxs-lookup"><span data-stu-id="78aa8-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-577">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-577">Format</span></span>

<span data-ttu-id="78aa8-578">如果沒有空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-579">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-579">Pattern</span></span>

<span data-ttu-id="78aa8-580">10 位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="78aa8-581">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-581">Checksum</span></span>

<span data-ttu-id="78aa8-582">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-583">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-583">Definition</span></span>

<span data-ttu-id="78aa8-584">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-585">規則運算式`Regex_netherlands_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-586">從關鍵字`Keywords_netherlands_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-587">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-587">Keywords</span></span>

<span data-ttu-id="78aa8-588">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-588"></span></span>
|<span data-ttu-id="78aa8-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-590">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-590">dl#</span></span>  <br/> <span data-ttu-id="78aa8-591">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-591">driver license</span></span>  <br/> <span data-ttu-id="78aa8-592">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-592">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-593">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-593">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-594">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-594">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-595">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-595">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-596">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-596">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-597">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-597">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-598">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-598">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-599">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-599">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-600">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-600">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-601">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="78aa8-602">permis de conduire</span></span>  <br/> <span data-ttu-id="78aa8-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="78aa8-603">rijbewijs</span></span>  <br/> <span data-ttu-id="78aa8-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="78aa8-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="78aa8-605">波蘭</span><span class="sxs-lookup"><span data-stu-id="78aa8-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-606">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-606">Format</span></span>

<span data-ttu-id="78aa8-607">14 位數包含正斜線，2</span><span class="sxs-lookup"><span data-stu-id="78aa8-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-608">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-608">Pattern</span></span>

<span data-ttu-id="78aa8-609">14 位數和 2 的正斜線：</span><span class="sxs-lookup"><span data-stu-id="78aa8-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="78aa8-610">五位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-610">Five digits</span></span> 
    
- <span data-ttu-id="78aa8-611">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="78aa8-611">A forward slash</span></span>
    
- <span data-ttu-id="78aa8-612">兩位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-612">Two digits</span></span>
    
- <span data-ttu-id="78aa8-613">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="78aa8-613">A forward slash</span></span>
    
- <span data-ttu-id="78aa8-614">七位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="78aa8-615">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-615">Checksum</span></span>

<span data-ttu-id="78aa8-616">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-617">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-617">Definition</span></span>

<span data-ttu-id="78aa8-618">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-619">規則運算式`Regex_poland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-620">從關鍵字`Keywords_poland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-621">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-621">Keywords</span></span>

<span data-ttu-id="78aa8-622">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-622"></span></span>
|<span data-ttu-id="78aa8-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-624">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-624">dl#</span></span>  <br/> <span data-ttu-id="78aa8-625">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-625">driver license</span></span>  <br/> <span data-ttu-id="78aa8-626">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-626">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-627">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-627">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-628">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-628">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-629">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-629">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-630">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-630">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-631">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-631">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-632">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-632">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-633">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-633">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-634">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-634">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-635">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="78aa8-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="78aa8-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="78aa8-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-638">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-638">Format</span></span>

<span data-ttu-id="78aa8-639">兩個字母後尾隨七個的數字中指定的型態</span><span class="sxs-lookup"><span data-stu-id="78aa8-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-640">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-640">Pattern</span></span>

<span data-ttu-id="78aa8-641">兩個字母後尾隨七個具有特殊字元的數字：</span><span class="sxs-lookup"><span data-stu-id="78aa8-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="78aa8-642">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="78aa8-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="78aa8-643">連字號</span><span class="sxs-lookup"><span data-stu-id="78aa8-643">A hyphen</span></span>
    
- <span data-ttu-id="78aa8-644">六位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-644">Six digits</span></span>
    
- <span data-ttu-id="78aa8-645">一個空格</span><span class="sxs-lookup"><span data-stu-id="78aa8-645">A space</span></span>
    
- <span data-ttu-id="78aa8-646">一位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="78aa8-647">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-647">Checksum</span></span>

<span data-ttu-id="78aa8-648">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-649">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-649">Definition</span></span>

<span data-ttu-id="78aa8-650">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-651">規則運算式`Regex_portugal_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-652">從關鍵字`Keywords_portugal_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-653">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-653">Keywords</span></span>

<span data-ttu-id="78aa8-654">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-654"></span></span>
|<span data-ttu-id="78aa8-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-656">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-656">dl#</span></span>  <br/> <span data-ttu-id="78aa8-657">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-657">driver license</span></span>  <br/> <span data-ttu-id="78aa8-658">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-658">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-659">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-659">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-660">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-660">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-661">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-661">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-662">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-662">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-663">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-663">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-664">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-664">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-665">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-665">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-666">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-666">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-667">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="78aa8-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="78aa8-669">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="78aa8-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-670">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-670">Format</span></span>

<span data-ttu-id="78aa8-671">一個字元尾隨八位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-672">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-672">Pattern</span></span>

<span data-ttu-id="78aa8-673">尾隨八位數的一個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="78aa8-674">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="78aa8-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="78aa8-675">八位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="78aa8-676">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-676">Checksum</span></span>

<span data-ttu-id="78aa8-677">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-678">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-678">Definition</span></span>

<span data-ttu-id="78aa8-679">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-680">規則運算式`Regex_romania_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-681">從關鍵字`Keywords_romania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-682">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-682">Keywords</span></span>

<span data-ttu-id="78aa8-683">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-683"></span></span>
|<span data-ttu-id="78aa8-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-685">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-685">dl#</span></span>  <br/> <span data-ttu-id="78aa8-686">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-686">driver license</span></span>  <br/> <span data-ttu-id="78aa8-687">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-687">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-688">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-688">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-689">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-689">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-690">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-690">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-691">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-691">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-692">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-692">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-693">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-693">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-694">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-694">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-695">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-695">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-696">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="78aa8-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="78aa8-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="78aa8-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-699">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-699">Format</span></span>

<span data-ttu-id="78aa8-700">一個字元尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-701">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-701">Pattern</span></span>

<span data-ttu-id="78aa8-702">一個字元尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="78aa8-703">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="78aa8-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="78aa8-704">七位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="78aa8-705">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-705">Checksum</span></span>

<span data-ttu-id="78aa8-706">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-707">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-707">Definition</span></span>

<span data-ttu-id="78aa8-708">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-709">規則運算式`Regex_slovakia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-710">從關鍵字`Keywords_slovakia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-711">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-711">Keywords</span></span>

<span data-ttu-id="78aa8-712">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-712"></span></span>
|<span data-ttu-id="78aa8-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-714">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-714">dl#</span></span>  <br/> <span data-ttu-id="78aa8-715">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-715">driver license</span></span>  <br/> <span data-ttu-id="78aa8-716">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-716">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-717">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-717">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-718">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-718">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-719">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-719">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-720">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-720">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-721">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-721">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-722">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-722">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-723">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-723">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-724">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-724">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-725">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="78aa8-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="78aa8-727">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="78aa8-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-728">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-728">Format</span></span>

<span data-ttu-id="78aa8-729">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-730">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-730">Pattern</span></span>

<span data-ttu-id="78aa8-731">九位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="78aa8-732">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-732">Checksum</span></span>

<span data-ttu-id="78aa8-733">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-734">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-734">Definition</span></span>

<span data-ttu-id="78aa8-735">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-736">規則運算式`Regex_slovenia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-737">從關鍵字`Keywords_slovenia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-738">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-738">Keywords</span></span>

<span data-ttu-id="78aa8-739">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-739"></span></span>
|<span data-ttu-id="78aa8-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-741">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-741">dl#</span></span>  <br/> <span data-ttu-id="78aa8-742">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-742">driver license</span></span>  <br/> <span data-ttu-id="78aa8-743">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-743">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-744">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-744">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-745">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-745">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-746">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-746">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-747">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-747">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-748">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-748">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-749">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-749">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-750">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-750">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-751">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-751">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-752">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="78aa8-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="78aa8-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="78aa8-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-755">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-755">Format</span></span>

<span data-ttu-id="78aa8-756">後面接著一個字元的八位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-757">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-757">Pattern</span></span>

<span data-ttu-id="78aa8-758">後面接著一個字元的八位數：</span><span class="sxs-lookup"><span data-stu-id="78aa8-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="78aa8-759">八位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-759">Eight digits</span></span> 
    
- <span data-ttu-id="78aa8-760">一個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="78aa8-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="78aa8-761">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-761">Checksum</span></span>

<span data-ttu-id="78aa8-762">是</span><span class="sxs-lookup"><span data-stu-id="78aa8-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-763">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-763">Definition</span></span>

<span data-ttu-id="78aa8-764">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-765">函式`Func_spain_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-766">從關鍵字`Keywords_spain_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78aa8-767">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-767">Keywords</span></span>

<span data-ttu-id="78aa8-768">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-768"></span></span>
|<span data-ttu-id="78aa8-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-770">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-771">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-771">dl#</span></span>  <br/> <span data-ttu-id="78aa8-772">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-772">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-773">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-773">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-774">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-774">driver license</span></span>  <br/> <span data-ttu-id="78aa8-775">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-775">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-776">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-776">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-777">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-777">driver's licence</span></span>  <br/> <span data-ttu-id="78aa8-778">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-778">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-779">driving 授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-779">driving licence</span></span>  <br/> <span data-ttu-id="78aa8-780">主導授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-780">driving license</span></span>  <br/> <span data-ttu-id="78aa8-781">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-781">driver licence number</span></span>  <br/> <span data-ttu-id="78aa8-782">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-782">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-783">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-783">drivers licence number</span></span>  <br/> <span data-ttu-id="78aa8-784">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-784">drivers license number</span></span>  <br/> <span data-ttu-id="78aa8-785">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-785">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-786">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-786">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-787">driving 授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-787">driving licence number</span></span>  <br/> <span data-ttu-id="78aa8-788">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-788">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-789">主導允許</span><span class="sxs-lookup"><span data-stu-id="78aa8-789">driving permit</span></span>  <br/> <span data-ttu-id="78aa8-790">主導允許數字</span><span class="sxs-lookup"><span data-stu-id="78aa8-790">driving permit number</span></span>  <br/> <span data-ttu-id="78aa8-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="78aa8-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="78aa8-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="78aa8-792">permiso conducción</span></span>  <br/> <span data-ttu-id="78aa8-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="78aa8-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="78aa8-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="78aa8-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="78aa8-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="78aa8-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="78aa8-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="78aa8-796">licencia conducir</span></span>  <br/> <span data-ttu-id="78aa8-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="78aa8-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="78aa8-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="78aa8-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="78aa8-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="78aa8-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="78aa8-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="78aa8-800">permiso conducir</span></span>  <br/> <span data-ttu-id="78aa8-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="78aa8-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="78aa8-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="78aa8-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="78aa8-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="78aa8-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="78aa8-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="78aa8-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="78aa8-805">格式</span><span class="sxs-lookup"><span data-stu-id="78aa8-805">Format</span></span>

<span data-ttu-id="78aa8-806">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="78aa8-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="78aa8-807">模式</span><span class="sxs-lookup"><span data-stu-id="78aa8-807">Pattern</span></span>

<span data-ttu-id="78aa8-808">10 位數包含連字號：</span><span class="sxs-lookup"><span data-stu-id="78aa8-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="78aa8-809">六位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-809">Six digits</span></span> 
    
- <span data-ttu-id="78aa8-810">連字號</span><span class="sxs-lookup"><span data-stu-id="78aa8-810">A hyphen</span></span>
    
- <span data-ttu-id="78aa8-811">四位數</span><span class="sxs-lookup"><span data-stu-id="78aa8-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="78aa8-812">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-812">Checksum</span></span>

<span data-ttu-id="78aa8-813">否</span><span class="sxs-lookup"><span data-stu-id="78aa8-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="78aa8-814">定義</span><span class="sxs-lookup"><span data-stu-id="78aa8-814">Definition</span></span>

<span data-ttu-id="78aa8-815">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="78aa8-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="78aa8-816">規則運算式`Regex_sweden_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="78aa8-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="78aa8-817">從關鍵字`Keywords_sweden_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="78aa8-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="78aa8-818">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78aa8-818">Keywords</span></span>

<span data-ttu-id="78aa8-819">| |</span><span class="sxs-lookup"><span data-stu-id="78aa8-819"></span></span>
|<span data-ttu-id="78aa8-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="78aa8-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="78aa8-821">dl #</span><span class="sxs-lookup"><span data-stu-id="78aa8-821">dl#</span></span>  <br/> <span data-ttu-id="78aa8-822">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-822">driver license</span></span>  <br/> <span data-ttu-id="78aa8-823">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-823">driver license number</span></span>  <br/> <span data-ttu-id="78aa8-824">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-824">driver licence</span></span>  <br/> <span data-ttu-id="78aa8-825">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="78aa8-825">drivers lic.</span></span>  <br/> <span data-ttu-id="78aa8-826">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-826">drivers license</span></span>  <br/> <span data-ttu-id="78aa8-827">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="78aa8-827">drivers licence</span></span>  <br/> <span data-ttu-id="78aa8-828">駕照</span><span class="sxs-lookup"><span data-stu-id="78aa8-828">driver's license</span></span>  <br/> <span data-ttu-id="78aa8-829">駕照編號</span><span class="sxs-lookup"><span data-stu-id="78aa8-829">driver's license number</span></span>  <br/> <span data-ttu-id="78aa8-830">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="78aa8-830">driver's licence number</span></span>  <br/> <span data-ttu-id="78aa8-831">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="78aa8-831">driving license number</span></span>  <br/> <span data-ttu-id="78aa8-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="78aa8-832">dlno#</span></span>  <br/> <span data-ttu-id="78aa8-833">körkort</span><span class="sxs-lookup"><span data-stu-id="78aa8-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="78aa8-834">英國</span><span class="sxs-lookup"><span data-stu-id="78aa8-834">UK</span></span>

<span data-ttu-id="78aa8-835">如需詳細資訊，請參閱區段 」 英國</span><span class="sxs-lookup"><span data-stu-id="78aa8-835">For details, see the section "U.K.</span></span> <span data-ttu-id="78aa8-836">驅動程式的授權數目 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="78aa8-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="78aa8-837">另請參閱</span><span class="sxs-lookup"><span data-stu-id="78aa8-837">See also</span></span>

[<span data-ttu-id="78aa8-838">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="78aa8-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

