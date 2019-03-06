---
title: 歐盟駕照編號
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟駕駛執照號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: be9497c325866a670dff8d82b5170f4ca947c4ad
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410748"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="dedf0-104">歐盟駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-104">EU Driver's License Number</span></span>

<span data-ttu-id="dedf0-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟駕駛執照號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="dedf0-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="dedf0-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="dedf0-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="dedf0-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="dedf0-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-108">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-108">Format</span></span>

<span data-ttu-id="dedf0-109">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-110">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-110">Pattern</span></span>

<span data-ttu-id="dedf0-111">八位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dedf0-112">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-112">Checksum</span></span>

<span data-ttu-id="dedf0-113">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-114">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-114">Definition</span></span>

<span data-ttu-id="dedf0-115">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-116">規則運算式`Regex_austria_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-117">從關鍵字`Keywords_austria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="dedf0-118">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-118">Keywords</span></span>

<span data-ttu-id="dedf0-119">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-119"></span></span>
|<span data-ttu-id="dedf0-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-121">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-121">dl#</span></span>  <br/> <span data-ttu-id="dedf0-122">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-122">driver license</span></span>  <br/> <span data-ttu-id="dedf0-123">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-123">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-124">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-124">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-125">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-125">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-126">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-126">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-127">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-127">driver's licence</span></span>  <br/> <span data-ttu-id="dedf0-128">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-128">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-129">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-129">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-130">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="dedf0-131">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-131">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-132">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="dedf0-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="dedf0-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="dedf0-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="dedf0-135">比利時</span><span class="sxs-lookup"><span data-stu-id="dedf0-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-136">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-136">Format</span></span>

<span data-ttu-id="dedf0-137">如果沒有空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-138">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-138">Pattern</span></span>

<span data-ttu-id="dedf0-139">10 位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dedf0-140">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-140">Checksum</span></span>

<span data-ttu-id="dedf0-141">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-142">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-142">Definition</span></span>

<span data-ttu-id="dedf0-143">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-144">規則運算式`Regex_belgium_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-145">從關鍵字`Keywords_belgium_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="dedf0-146">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-146">Keywords</span></span>

<span data-ttu-id="dedf0-147">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-147"></span></span>
|<span data-ttu-id="dedf0-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-149">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-149">dl#</span></span>  <br/> <span data-ttu-id="dedf0-150">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-150">driver license</span></span>  <br/> <span data-ttu-id="dedf0-151">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-151">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-152">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-152">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-153">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-153">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-154">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-154">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-155">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-155">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-156">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-156">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-157">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-157">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-158">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-158">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-159">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="dedf0-160">rijbewijs</span></span>  <br/> <span data-ttu-id="dedf0-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="dedf0-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="dedf0-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="dedf0-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="dedf0-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="dedf0-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="dedf0-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="dedf0-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="dedf0-165">führerschein 編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="dedf0-166">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="dedf0-167">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="dedf0-168">保加利亞</span><span class="sxs-lookup"><span data-stu-id="dedf0-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-169">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-169">Format</span></span>

<span data-ttu-id="dedf0-170">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-171">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-171">Pattern</span></span>

<span data-ttu-id="dedf0-172">九位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dedf0-173">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-173">Checksum</span></span>

<span data-ttu-id="dedf0-174">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-175">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-175">Definition</span></span>

<span data-ttu-id="dedf0-176">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-177">規則運算式`Regex_bulgaria_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-178">從關鍵字`Keywords_bulgaria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="dedf0-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-179">Keywords</span></span>

<span data-ttu-id="dedf0-180">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-180"></span></span>
|<span data-ttu-id="dedf0-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-182">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-182">dl#</span></span>  <br/> <span data-ttu-id="dedf0-183">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-183">driver license</span></span>  <br/> <span data-ttu-id="dedf0-184">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-184">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-185">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-185">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-186">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-186">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-187">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-187">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-188">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-188">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-189">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-189">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-190">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-190">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-191">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-191">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-192">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-192">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-193">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-194">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МПС</span><span class="sxs-lookup"><span data-stu-id="dedf0-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="dedf0-195">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО</span><span class="sxs-lookup"><span data-stu-id="dedf0-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="dedf0-196">СУМПС</span><span class="sxs-lookup"><span data-stu-id="dedf0-196">сумпс</span></span>  <br/> <span data-ttu-id="dedf0-197">ШОФЬОРСКА КНИЖКА</span><span class="sxs-lookup"><span data-stu-id="dedf0-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="dedf0-198">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="dedf0-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-199">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-199">Format</span></span>

<span data-ttu-id="dedf0-200">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-201">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-201">Pattern</span></span>

<span data-ttu-id="dedf0-202">八位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dedf0-203">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-203">Checksum</span></span>

<span data-ttu-id="dedf0-204">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-205">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-205">Definition</span></span>

<span data-ttu-id="dedf0-206">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-207">規則運算式`Regex_croatia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-208">從關鍵字`Keywords_croatia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="dedf0-209">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-209">Keywords</span></span>

<span data-ttu-id="dedf0-210">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-210"></span></span>
|<span data-ttu-id="dedf0-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-212">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-212">dl#</span></span>  <br/> <span data-ttu-id="dedf0-213">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-213">driver license</span></span>  <br/> <span data-ttu-id="dedf0-214">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-214">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-215">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-215">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-216">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-216">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-217">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-217">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-218">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-218">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-219">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-219">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-220">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-220">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-221">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-221">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-222">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-222">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-223">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="dedf0-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="dedf0-225">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="dedf0-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-226">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-226">Format</span></span>

<span data-ttu-id="dedf0-227">如果沒有空格和分隔符號的 12 位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-228">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-228">Pattern</span></span>

<span data-ttu-id="dedf0-229">12 位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dedf0-230">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-230">Checksum</span></span>

<span data-ttu-id="dedf0-231">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-232">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-232">Definition</span></span>

<span data-ttu-id="dedf0-233">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-234">規則運算式`Regex_cyprus_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-235">從關鍵字`Keywords_cyprus_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-236">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-236">Keywords</span></span>

<span data-ttu-id="dedf0-237">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-237"></span></span>
|<span data-ttu-id="dedf0-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-239">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-239">dl#</span></span>  <br/> <span data-ttu-id="dedf0-240">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-240">driver license</span></span>  <br/> <span data-ttu-id="dedf0-241">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-241">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-242">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-242">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-243">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-243">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-244">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-244">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-245">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-245">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-246">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-246">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-247">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-247">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-248">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-248">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-249">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-250">ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="dedf0-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="dedf0-251">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="dedf0-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-252">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-252">Format</span></span>

<span data-ttu-id="dedf0-253">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-254">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-254">Pattern</span></span>

<span data-ttu-id="dedf0-255">八個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="dedf0-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="dedf0-256">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="dedf0-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="dedf0-257">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="dedf0-257">A space (optional)</span></span>
    
- <span data-ttu-id="dedf0-258">六位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dedf0-259">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-259">Checksum</span></span>

<span data-ttu-id="dedf0-260">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-261">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-261">Definition</span></span>

<span data-ttu-id="dedf0-262">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-263">規則運算式`Regex_czech_republic_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-264">從關鍵字`Keywords_czech_republic_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="dedf0-265">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-265">Keywords</span></span>

<span data-ttu-id="dedf0-266">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-266"></span></span>
|<span data-ttu-id="dedf0-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-268">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-268">dl#</span></span>  <br/> <span data-ttu-id="dedf0-269">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-269">driver license</span></span>  <br/> <span data-ttu-id="dedf0-270">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-270">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-271">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-271">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-272">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-272">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-273">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-273">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-274">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-274">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-275">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-275">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-276">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-276">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-277">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-277">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-278">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-278">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-279">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-279">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-280">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-281">Řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="dedf0-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="dedf0-282">丹麥</span><span class="sxs-lookup"><span data-stu-id="dedf0-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-283">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-283">Format</span></span>

<span data-ttu-id="dedf0-284">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-285">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-285">Pattern</span></span>

<span data-ttu-id="dedf0-286">八位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dedf0-287">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-287">Checksum</span></span>

<span data-ttu-id="dedf0-288">是</span><span class="sxs-lookup"><span data-stu-id="dedf0-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-289">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-289">Definition</span></span>

<span data-ttu-id="dedf0-290">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-291">規則運算式`Regex_denmark_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-292">從關鍵字`Keywords_denmark_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="dedf0-293">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-293">Keywords</span></span>

<span data-ttu-id="dedf0-294">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-294"></span></span>
|<span data-ttu-id="dedf0-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-296">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-296">dl#</span></span>  <br/> <span data-ttu-id="dedf0-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-297">driver license</span></span>  <br/> <span data-ttu-id="dedf0-298">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-298">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-299">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-299">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-300">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-300">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-301">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-301">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-302">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-302">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-303">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-303">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-304">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-304">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-305">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-305">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-306">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-306">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-307">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="dedf0-308">kørekort</span></span>  <br/> <span data-ttu-id="dedf0-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="dedf0-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="dedf0-310">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="dedf0-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-311">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-311">Format</span></span>

<span data-ttu-id="dedf0-312">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-313">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-313">Pattern</span></span>

<span data-ttu-id="dedf0-314">兩個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="dedf0-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="dedf0-315">字母"ET 」 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="dedf0-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="dedf0-316">六位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dedf0-317">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-317">Checksum</span></span>

<span data-ttu-id="dedf0-318">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-319">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-319">Definition</span></span>

<span data-ttu-id="dedf0-320">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-321">規則運算式`Regex_estonia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-322">從關鍵字`Keywords_estonia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-323">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-323">Keywords</span></span>

<span data-ttu-id="dedf0-324">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-324"></span></span>
|<span data-ttu-id="dedf0-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-326">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-326">dl#</span></span>  <br/> <span data-ttu-id="dedf0-327">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-327">driver license</span></span>  <br/> <span data-ttu-id="dedf0-328">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-328">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-329">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-329">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-330">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-330">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-331">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-331">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-332">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-332">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-333">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-333">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-334">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-334">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-335">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-335">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-336">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-336">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-337">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="dedf0-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="dedf0-339">芬蘭</span><span class="sxs-lookup"><span data-stu-id="dedf0-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-340">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-340">Format</span></span>

<span data-ttu-id="dedf0-341">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="dedf0-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-342">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-342">Pattern</span></span>

<span data-ttu-id="dedf0-343">10 位數包含連字號：</span><span class="sxs-lookup"><span data-stu-id="dedf0-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="dedf0-344">六位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-344">Six digits</span></span> 
    
- <span data-ttu-id="dedf0-345">連字號</span><span class="sxs-lookup"><span data-stu-id="dedf0-345">A hyphen</span></span>
    
-  <span data-ttu-id="dedf0-346">四位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="dedf0-347">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-347">Checksum</span></span>

<span data-ttu-id="dedf0-348">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-349">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-349">Definition</span></span>

<span data-ttu-id="dedf0-350">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-351">規則運算式`Regex_finland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-352">從關鍵字`Keywords_finland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-353">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-353">Keywords</span></span>

<span data-ttu-id="dedf0-354">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-354"></span></span>
|<span data-ttu-id="dedf0-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-356">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-356">dl#</span></span>  <br/> <span data-ttu-id="dedf0-357">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-357">driver license</span></span>  <br/> <span data-ttu-id="dedf0-358">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-358">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-359">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-359">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-360">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-360">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-361">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-361">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-362">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-362">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-363">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-363">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-364">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-364">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-365">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-365">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-366">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-366">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-367">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="dedf0-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="dedf0-369">法國</span><span class="sxs-lookup"><span data-stu-id="dedf0-369">France</span></span>

<span data-ttu-id="dedf0-370">如需詳細資訊，請參閱 「 法國駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="dedf0-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="dedf0-371">德國</span><span class="sxs-lookup"><span data-stu-id="dedf0-371">Germany</span></span>

<span data-ttu-id="dedf0-372">如需詳細資訊，請參閱 「 德國駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="dedf0-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="dedf0-373">希臘</span><span class="sxs-lookup"><span data-stu-id="dedf0-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-374">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-374">Format</span></span>

<span data-ttu-id="dedf0-375">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-376">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-376">Pattern</span></span>

 <span data-ttu-id="dedf0-377">九位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="dedf0-378">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-378">Checksum</span></span>

<span data-ttu-id="dedf0-379">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-380">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-380">Definition</span></span>

<span data-ttu-id="dedf0-381">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-382">規則運算式`Regex_greece_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-383">從關鍵字`Keywords_greece_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-384">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-384">Keywords</span></span>

<span data-ttu-id="dedf0-385">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-385"></span></span>
|<span data-ttu-id="dedf0-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="dedf0-387">dlL#</span></span>  <br/> <span data-ttu-id="dedf0-388">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-388">driver license</span></span>  <br/> <span data-ttu-id="dedf0-389">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-389">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-390">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-390">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-391">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-391">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-392">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-392">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-393">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-393">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-394">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-394">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-395">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-395">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-396">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-396">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-397">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-397">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-398">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-399">ΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="dedf0-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="dedf0-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="dedf0-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="dedf0-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="dedf0-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-402">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-402">Format</span></span>

<span data-ttu-id="dedf0-403">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-404">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-404">Pattern</span></span>

<span data-ttu-id="dedf0-405">兩個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="dedf0-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="dedf0-406">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="dedf0-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="dedf0-407">六位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dedf0-408">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-408">Checksum</span></span>

<span data-ttu-id="dedf0-409">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-410">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-410">Definition</span></span>

<span data-ttu-id="dedf0-411">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-412">規則運算式`Regex_hungary_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-413">從關鍵字`Keywords_hungary_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-414">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-414">Keywords</span></span>

<span data-ttu-id="dedf0-415">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-415"></span></span>
|<span data-ttu-id="dedf0-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-417">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-417">dl#</span></span>  <br/> <span data-ttu-id="dedf0-418">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-418">driver license</span></span>  <br/> <span data-ttu-id="dedf0-419">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-419">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-420">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-420">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-421">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-421">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-422">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-422">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-423">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-423">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-424">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-424">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-425">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-425">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-426">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-426">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-427">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-427">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-428">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="dedf0-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="dedf0-430">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="dedf0-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-431">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-431">Format</span></span>

<span data-ttu-id="dedf0-432">四個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-433">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-433">Pattern</span></span>

<span data-ttu-id="dedf0-434">六位數和四個字母：</span><span class="sxs-lookup"><span data-stu-id="dedf0-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="dedf0-435">六位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-435">Six digits</span></span>
    
- <span data-ttu-id="dedf0-436">四個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="dedf0-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dedf0-437">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-437">Checksum</span></span>

<span data-ttu-id="dedf0-438">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-439">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-439">Definition</span></span>

<span data-ttu-id="dedf0-440">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-441">規則運算式`Regex_ireland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-442">從關鍵字`Keywords_ireland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-443">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-443">Keywords</span></span>

<span data-ttu-id="dedf0-444">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-444"></span></span>
|<span data-ttu-id="dedf0-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-446">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-446">dl#</span></span>  <br/> <span data-ttu-id="dedf0-447">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-447">driver license</span></span>  <br/> <span data-ttu-id="dedf0-448">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-448">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-449">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-449">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-450">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-450">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-451">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-451">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-452">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-452">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-453">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-453">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-454">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-454">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-455">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-455">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-456">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-456">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-457">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="dedf0-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="dedf0-459">義大利</span><span class="sxs-lookup"><span data-stu-id="dedf0-459">Italy</span></span>

<span data-ttu-id="dedf0-460">如需詳細資訊，請參閱 「 義大利駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="dedf0-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="dedf0-461">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="dedf0-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-462">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-462">Format</span></span>

<span data-ttu-id="dedf0-463">三個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-464">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-464">Pattern</span></span>

<span data-ttu-id="dedf0-465">三個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="dedf0-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="dedf0-466">三個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="dedf0-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="dedf0-467">六位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dedf0-468">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-468">Checksum</span></span>

<span data-ttu-id="dedf0-469">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-470">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-470">Definition</span></span>

<span data-ttu-id="dedf0-471">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-472">規則運算式`Regex_latvia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-473">從關鍵字`Keywords_latvia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-474">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-474">Keywords</span></span>

<span data-ttu-id="dedf0-475">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-475"></span></span>
|<span data-ttu-id="dedf0-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-477">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-477">dl#</span></span>  <br/> <span data-ttu-id="dedf0-478">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-478">driver license</span></span>  <br/> <span data-ttu-id="dedf0-479">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-479">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-480">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-480">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-481">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-481">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-482">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-482">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-483">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-483">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-484">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-484">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-485">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-485">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-486">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-486">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-487">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-487">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-488">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="dedf0-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="dedf0-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="dedf0-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-491">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-491">Format</span></span>

<span data-ttu-id="dedf0-492">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-493">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-493">Pattern</span></span>

 <span data-ttu-id="dedf0-494">八位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="dedf0-495">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-495">Checksum</span></span>

<span data-ttu-id="dedf0-496">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-497">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-497">Definition</span></span>

<span data-ttu-id="dedf0-498">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-499">規則運算式`Regex_lithuania_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-500">從關鍵字`Keywords_lithuania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-501">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-501">Keywords</span></span>

<span data-ttu-id="dedf0-502">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-502"></span></span>
|<span data-ttu-id="dedf0-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-504">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-504">dl#</span></span>  <br/> <span data-ttu-id="dedf0-505">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-505">driver license</span></span>  <br/> <span data-ttu-id="dedf0-506">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-506">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-507">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-507">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-508">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-508">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-509">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-509">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-510">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-510">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-511">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-511">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-512">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-512">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-513">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-513">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-514">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-514">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-515">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="dedf0-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="dedf0-517">盧森堡</span><span class="sxs-lookup"><span data-stu-id="dedf0-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-518">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-518">Format</span></span>

<span data-ttu-id="dedf0-519">六位數，代表不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="dedf0-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-520">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-520">Pattern</span></span>

 <span data-ttu-id="dedf0-521">六位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="dedf0-522">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-522">Checksum</span></span>

<span data-ttu-id="dedf0-523">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-524">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-524">Definition</span></span>

<span data-ttu-id="dedf0-525">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-526">規則運算式`Regex_luxemburg_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-527">從關鍵字`Keywords_luxemburg_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-528">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-528">Keywords</span></span>

<span data-ttu-id="dedf0-529">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-529"></span></span>
|<span data-ttu-id="dedf0-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-531">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-531">dl#</span></span>  <br/> <span data-ttu-id="dedf0-532">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-532">driver license</span></span>  <br/> <span data-ttu-id="dedf0-533">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-533">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-534">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-534">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-535">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-535">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-536">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-536">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-537">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-537">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-538">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-538">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-539">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-539">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-540">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-540">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-541">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-541">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-542">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="dedf0-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="dedf0-544">馬爾他</span><span class="sxs-lookup"><span data-stu-id="dedf0-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-545">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-545">Format</span></span>

<span data-ttu-id="dedf0-546">兩個字元和六位數，代表所指定的型態的組合</span><span class="sxs-lookup"><span data-stu-id="dedf0-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-547">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-547">Pattern</span></span>

<span data-ttu-id="dedf0-548">兩個字元和六位數的組合：</span><span class="sxs-lookup"><span data-stu-id="dedf0-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="dedf0-549">兩個字元 （數字或字母、 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="dedf0-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="dedf0-550">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="dedf0-550">A space (optional)</span></span>
    
- <span data-ttu-id="dedf0-551">三位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-551">Three digits</span></span>
    
- <span data-ttu-id="dedf0-552">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="dedf0-552">A space (optional)</span></span>
    
- <span data-ttu-id="dedf0-553">三位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dedf0-554">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-554">Checksum</span></span>

<span data-ttu-id="dedf0-555">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-556">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-556">Definition</span></span>

<span data-ttu-id="dedf0-557">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-558">規則運算式`Regex_malta_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-559">從關鍵字`Keywords_malta_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-560">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-560">Keywords</span></span>

<span data-ttu-id="dedf0-561">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-561"></span></span>
|<span data-ttu-id="dedf0-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-563">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-563">dl#</span></span>  <br/> <span data-ttu-id="dedf0-564">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-564">driver license</span></span>  <br/> <span data-ttu-id="dedf0-565">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-565">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-566">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-566">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-567">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-567">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-568">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-568">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-569">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-569">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-570">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-570">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-571">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-571">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-572">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-572">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-573">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-573">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-574">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-575">liċenzja 塔司 sewqan</span><span class="sxs-lookup"><span data-stu-id="dedf0-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="dedf0-576">荷蘭</span><span class="sxs-lookup"><span data-stu-id="dedf0-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-577">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-577">Format</span></span>

<span data-ttu-id="dedf0-578">如果沒有空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-579">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-579">Pattern</span></span>

<span data-ttu-id="dedf0-580">10 位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dedf0-581">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-581">Checksum</span></span>

<span data-ttu-id="dedf0-582">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-583">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-583">Definition</span></span>

<span data-ttu-id="dedf0-584">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-585">規則運算式`Regex_netherlands_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-586">從關鍵字`Keywords_netherlands_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-587">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-587">Keywords</span></span>

<span data-ttu-id="dedf0-588">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-588"></span></span>
|<span data-ttu-id="dedf0-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-590">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-590">dl#</span></span>  <br/> <span data-ttu-id="dedf0-591">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-591">driver license</span></span>  <br/> <span data-ttu-id="dedf0-592">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-592">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-593">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-593">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-594">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-594">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-595">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-595">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-596">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-596">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-597">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-597">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-598">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-598">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-599">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-599">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-600">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-600">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-601">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="dedf0-602">permis de conduire</span></span>  <br/> <span data-ttu-id="dedf0-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="dedf0-603">rijbewijs</span></span>  <br/> <span data-ttu-id="dedf0-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="dedf0-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="dedf0-605">波蘭</span><span class="sxs-lookup"><span data-stu-id="dedf0-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-606">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-606">Format</span></span>

<span data-ttu-id="dedf0-607">14 位數包含正斜線，2</span><span class="sxs-lookup"><span data-stu-id="dedf0-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-608">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-608">Pattern</span></span>

<span data-ttu-id="dedf0-609">14 位數和 2 的正斜線：</span><span class="sxs-lookup"><span data-stu-id="dedf0-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="dedf0-610">五位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-610">Five digits</span></span> 
    
- <span data-ttu-id="dedf0-611">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="dedf0-611">A forward slash</span></span>
    
- <span data-ttu-id="dedf0-612">兩位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-612">Two digits</span></span>
    
- <span data-ttu-id="dedf0-613">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="dedf0-613">A forward slash</span></span>
    
- <span data-ttu-id="dedf0-614">七位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dedf0-615">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-615">Checksum</span></span>

<span data-ttu-id="dedf0-616">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-617">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-617">Definition</span></span>

<span data-ttu-id="dedf0-618">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-619">規則運算式`Regex_poland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-620">從關鍵字`Keywords_poland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-621">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-621">Keywords</span></span>

<span data-ttu-id="dedf0-622">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-622"></span></span>
|<span data-ttu-id="dedf0-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-624">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-624">dl#</span></span>  <br/> <span data-ttu-id="dedf0-625">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-625">driver license</span></span>  <br/> <span data-ttu-id="dedf0-626">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-626">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-627">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-627">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-628">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-628">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-629">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-629">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-630">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-630">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-631">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-631">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-632">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-632">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-633">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-633">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-634">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-634">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-635">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="dedf0-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="dedf0-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="dedf0-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-638">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-638">Format</span></span>

<span data-ttu-id="dedf0-639">兩個字母後尾隨七個的數字中指定的型態</span><span class="sxs-lookup"><span data-stu-id="dedf0-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-640">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-640">Pattern</span></span>

<span data-ttu-id="dedf0-641">兩個字母後尾隨七個具有特殊字元的數字：</span><span class="sxs-lookup"><span data-stu-id="dedf0-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="dedf0-642">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="dedf0-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="dedf0-643">連字號</span><span class="sxs-lookup"><span data-stu-id="dedf0-643">A hyphen</span></span>
    
- <span data-ttu-id="dedf0-644">六位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-644">Six digits</span></span>
    
- <span data-ttu-id="dedf0-645">一個空格</span><span class="sxs-lookup"><span data-stu-id="dedf0-645">A space</span></span>
    
- <span data-ttu-id="dedf0-646">一位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dedf0-647">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-647">Checksum</span></span>

<span data-ttu-id="dedf0-648">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-649">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-649">Definition</span></span>

<span data-ttu-id="dedf0-650">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-651">規則運算式`Regex_portugal_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-652">從關鍵字`Keywords_portugal_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-653">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-653">Keywords</span></span>

<span data-ttu-id="dedf0-654">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-654"></span></span>
|<span data-ttu-id="dedf0-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-656">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-656">dl#</span></span>  <br/> <span data-ttu-id="dedf0-657">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-657">driver license</span></span>  <br/> <span data-ttu-id="dedf0-658">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-658">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-659">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-659">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-660">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-660">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-661">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-661">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-662">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-662">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-663">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-663">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-664">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-664">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-665">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-665">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-666">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-666">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-667">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="dedf0-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="dedf0-669">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="dedf0-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-670">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-670">Format</span></span>

<span data-ttu-id="dedf0-671">一個字元尾隨八位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-672">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-672">Pattern</span></span>

<span data-ttu-id="dedf0-673">尾隨八位數的一個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="dedf0-674">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="dedf0-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="dedf0-675">八位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dedf0-676">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-676">Checksum</span></span>

<span data-ttu-id="dedf0-677">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-678">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-678">Definition</span></span>

<span data-ttu-id="dedf0-679">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-680">規則運算式`Regex_romania_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-681">從關鍵字`Keywords_romania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-682">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-682">Keywords</span></span>

<span data-ttu-id="dedf0-683">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-683"></span></span>
|<span data-ttu-id="dedf0-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-685">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-685">dl#</span></span>  <br/> <span data-ttu-id="dedf0-686">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-686">driver license</span></span>  <br/> <span data-ttu-id="dedf0-687">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-687">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-688">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-688">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-689">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-689">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-690">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-690">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-691">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-691">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-692">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-692">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-693">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-693">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-694">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-694">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-695">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-695">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-696">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="dedf0-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="dedf0-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="dedf0-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-699">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-699">Format</span></span>

<span data-ttu-id="dedf0-700">一個字元尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-701">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-701">Pattern</span></span>

<span data-ttu-id="dedf0-702">一個字元尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="dedf0-703">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="dedf0-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="dedf0-704">七位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="dedf0-705">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-705">Checksum</span></span>

<span data-ttu-id="dedf0-706">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-707">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-707">Definition</span></span>

<span data-ttu-id="dedf0-708">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-709">規則運算式`Regex_slovakia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-710">從關鍵字`Keywords_slovakia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-711">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-711">Keywords</span></span>

<span data-ttu-id="dedf0-712">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-712"></span></span>
|<span data-ttu-id="dedf0-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-714">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-714">dl#</span></span>  <br/> <span data-ttu-id="dedf0-715">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-715">driver license</span></span>  <br/> <span data-ttu-id="dedf0-716">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-716">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-717">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-717">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-718">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-718">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-719">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-719">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-720">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-720">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-721">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-721">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-722">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-722">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-723">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-723">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-724">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-724">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-725">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="dedf0-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="dedf0-727">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="dedf0-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-728">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-728">Format</span></span>

<span data-ttu-id="dedf0-729">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-730">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-730">Pattern</span></span>

<span data-ttu-id="dedf0-731">九位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dedf0-732">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-732">Checksum</span></span>

<span data-ttu-id="dedf0-733">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-734">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-734">Definition</span></span>

<span data-ttu-id="dedf0-735">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-736">規則運算式`Regex_slovenia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-737">從關鍵字`Keywords_slovenia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-738">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-738">Keywords</span></span>

<span data-ttu-id="dedf0-739">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-739"></span></span>
|<span data-ttu-id="dedf0-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-741">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-741">dl#</span></span>  <br/> <span data-ttu-id="dedf0-742">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-742">driver license</span></span>  <br/> <span data-ttu-id="dedf0-743">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-743">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-744">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-744">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-745">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-745">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-746">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-746">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-747">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-747">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-748">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-748">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-749">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-749">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-750">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-750">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-751">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-751">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-752">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="dedf0-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="dedf0-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="dedf0-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-755">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-755">Format</span></span>

<span data-ttu-id="dedf0-756">後面接著一個字元的八位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-757">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-757">Pattern</span></span>

<span data-ttu-id="dedf0-758">後面接著一個字元的八位數：</span><span class="sxs-lookup"><span data-stu-id="dedf0-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="dedf0-759">八位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-759">Eight digits</span></span> 
    
- <span data-ttu-id="dedf0-760">一個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="dedf0-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dedf0-761">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-761">Checksum</span></span>

<span data-ttu-id="dedf0-762">是</span><span class="sxs-lookup"><span data-stu-id="dedf0-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-763">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-763">Definition</span></span>

<span data-ttu-id="dedf0-764">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-765">函式`Func_spain_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-766">從關鍵字`Keywords_spain_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dedf0-767">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-767">Keywords</span></span>

<span data-ttu-id="dedf0-768">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-768"></span></span>
|<span data-ttu-id="dedf0-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-770">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-771">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-771">dl#</span></span>  <br/> <span data-ttu-id="dedf0-772">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-772">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-773">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-773">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-774">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-774">driver license</span></span>  <br/> <span data-ttu-id="dedf0-775">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-775">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-776">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-776">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-777">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-777">driver's licence</span></span>  <br/> <span data-ttu-id="dedf0-778">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-778">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-779">driving 授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-779">driving licence</span></span>  <br/> <span data-ttu-id="dedf0-780">主導授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-780">driving license</span></span>  <br/> <span data-ttu-id="dedf0-781">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-781">driver licence number</span></span>  <br/> <span data-ttu-id="dedf0-782">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-782">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-783">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-783">drivers licence number</span></span>  <br/> <span data-ttu-id="dedf0-784">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-784">drivers license number</span></span>  <br/> <span data-ttu-id="dedf0-785">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-785">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-786">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-786">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-787">driving 授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-787">driving licence number</span></span>  <br/> <span data-ttu-id="dedf0-788">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-788">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-789">主導允許</span><span class="sxs-lookup"><span data-stu-id="dedf0-789">driving permit</span></span>  <br/> <span data-ttu-id="dedf0-790">主導允許數字</span><span class="sxs-lookup"><span data-stu-id="dedf0-790">driving permit number</span></span>  <br/> <span data-ttu-id="dedf0-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="dedf0-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="dedf0-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="dedf0-792">permiso conducción</span></span>  <br/> <span data-ttu-id="dedf0-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="dedf0-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="dedf0-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="dedf0-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="dedf0-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="dedf0-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="dedf0-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="dedf0-796">licencia conducir</span></span>  <br/> <span data-ttu-id="dedf0-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="dedf0-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="dedf0-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="dedf0-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="dedf0-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="dedf0-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="dedf0-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="dedf0-800">permiso conducir</span></span>  <br/> <span data-ttu-id="dedf0-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="dedf0-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="dedf0-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="dedf0-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="dedf0-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="dedf0-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="dedf0-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="dedf0-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="dedf0-805">Format</span><span class="sxs-lookup"><span data-stu-id="dedf0-805">Format</span></span>

<span data-ttu-id="dedf0-806">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="dedf0-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dedf0-807">模式</span><span class="sxs-lookup"><span data-stu-id="dedf0-807">Pattern</span></span>

<span data-ttu-id="dedf0-808">10 位數包含連字號：</span><span class="sxs-lookup"><span data-stu-id="dedf0-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="dedf0-809">六位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-809">Six digits</span></span> 
    
- <span data-ttu-id="dedf0-810">連字號</span><span class="sxs-lookup"><span data-stu-id="dedf0-810">A hyphen</span></span>
    
- <span data-ttu-id="dedf0-811">四位數</span><span class="sxs-lookup"><span data-stu-id="dedf0-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dedf0-812">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-812">Checksum</span></span>

<span data-ttu-id="dedf0-813">否</span><span class="sxs-lookup"><span data-stu-id="dedf0-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dedf0-814">定義</span><span class="sxs-lookup"><span data-stu-id="dedf0-814">Definition</span></span>

<span data-ttu-id="dedf0-815">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="dedf0-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dedf0-816">規則運算式`Regex_sweden_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="dedf0-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dedf0-817">從關鍵字`Keywords_sweden_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="dedf0-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="dedf0-818">關鍵字</span><span class="sxs-lookup"><span data-stu-id="dedf0-818">Keywords</span></span>

<span data-ttu-id="dedf0-819">| |</span><span class="sxs-lookup"><span data-stu-id="dedf0-819"></span></span>
|<span data-ttu-id="dedf0-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dedf0-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dedf0-821">dl #</span><span class="sxs-lookup"><span data-stu-id="dedf0-821">dl#</span></span>  <br/> <span data-ttu-id="dedf0-822">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-822">driver license</span></span>  <br/> <span data-ttu-id="dedf0-823">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-823">driver license number</span></span>  <br/> <span data-ttu-id="dedf0-824">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-824">driver licence</span></span>  <br/> <span data-ttu-id="dedf0-825">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="dedf0-825">drivers lic.</span></span>  <br/> <span data-ttu-id="dedf0-826">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-826">drivers license</span></span>  <br/> <span data-ttu-id="dedf0-827">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="dedf0-827">drivers licence</span></span>  <br/> <span data-ttu-id="dedf0-828">駕照</span><span class="sxs-lookup"><span data-stu-id="dedf0-828">driver's license</span></span>  <br/> <span data-ttu-id="dedf0-829">駕照編號</span><span class="sxs-lookup"><span data-stu-id="dedf0-829">driver's license number</span></span>  <br/> <span data-ttu-id="dedf0-830">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="dedf0-830">driver's licence number</span></span>  <br/> <span data-ttu-id="dedf0-831">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="dedf0-831">driving license number</span></span>  <br/> <span data-ttu-id="dedf0-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="dedf0-832">dlno#</span></span>  <br/> <span data-ttu-id="dedf0-833">körkort</span><span class="sxs-lookup"><span data-stu-id="dedf0-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="dedf0-834">英國</span><span class="sxs-lookup"><span data-stu-id="dedf0-834">UK</span></span>

<span data-ttu-id="dedf0-835">如需詳細資訊，請參閱區段 」 英國</span><span class="sxs-lookup"><span data-stu-id="dedf0-835">For details, see the section "U.K.</span></span> <span data-ttu-id="dedf0-836">驅動程式的授權數目 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="dedf0-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dedf0-837">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dedf0-837">See also</span></span>

[<span data-ttu-id="dedf0-838">機密資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="dedf0-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

