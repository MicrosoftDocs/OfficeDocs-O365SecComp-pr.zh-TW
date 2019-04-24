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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255771"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="eaa56-104">歐盟駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-104">EU Driver's License Number</span></span>

<span data-ttu-id="eaa56-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟駕駛執照號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="eaa56-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="eaa56-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="eaa56-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="eaa56-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="eaa56-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-108">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-108">Format</span></span>

<span data-ttu-id="eaa56-109">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-110">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-110">Pattern</span></span>

<span data-ttu-id="eaa56-111">八位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eaa56-112">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-112">Checksum</span></span>

<span data-ttu-id="eaa56-113">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-114">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-114">Definition</span></span>

<span data-ttu-id="eaa56-115">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-116">規則運算式`Regex_austria_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-117">從關鍵字`Keywords_austria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="eaa56-118">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-118">Keywords</span></span>

<span data-ttu-id="eaa56-119">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-119"></span></span>
|<span data-ttu-id="eaa56-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-121">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-121">dl#</span></span>  <br/> <span data-ttu-id="eaa56-122">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-122">driver license</span></span>  <br/> <span data-ttu-id="eaa56-123">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-123">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-124">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-124">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-125">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-125">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-126">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-126">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-127">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-127">driver's licence</span></span>  <br/> <span data-ttu-id="eaa56-128">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-128">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-129">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-129">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-130">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="eaa56-131">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-131">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-132">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="eaa56-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="eaa56-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="eaa56-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="eaa56-135">比利時</span><span class="sxs-lookup"><span data-stu-id="eaa56-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-136">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-136">Format</span></span>

<span data-ttu-id="eaa56-137">如果沒有空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-138">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-138">Pattern</span></span>

<span data-ttu-id="eaa56-139">10 位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eaa56-140">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-140">Checksum</span></span>

<span data-ttu-id="eaa56-141">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-142">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-142">Definition</span></span>

<span data-ttu-id="eaa56-143">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-144">規則運算式`Regex_belgium_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-145">從關鍵字`Keywords_belgium_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="eaa56-146">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-146">Keywords</span></span>

<span data-ttu-id="eaa56-147">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-147"></span></span>
|<span data-ttu-id="eaa56-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-149">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-149">dl#</span></span>  <br/> <span data-ttu-id="eaa56-150">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-150">driver license</span></span>  <br/> <span data-ttu-id="eaa56-151">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-151">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-152">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-152">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-153">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-153">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-154">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-154">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-155">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-155">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-156">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-156">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-157">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-157">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-158">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-158">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-159">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="eaa56-160">rijbewijs</span></span>  <br/> <span data-ttu-id="eaa56-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="eaa56-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="eaa56-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="eaa56-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="eaa56-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="eaa56-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="eaa56-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="eaa56-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="eaa56-165">führerschein 編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="eaa56-166">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="eaa56-167">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="eaa56-168">保加利亞</span><span class="sxs-lookup"><span data-stu-id="eaa56-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-169">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-169">Format</span></span>

<span data-ttu-id="eaa56-170">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-171">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-171">Pattern</span></span>

<span data-ttu-id="eaa56-172">九位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eaa56-173">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-173">Checksum</span></span>

<span data-ttu-id="eaa56-174">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-175">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-175">Definition</span></span>

<span data-ttu-id="eaa56-176">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-177">規則運算式`Regex_bulgaria_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-178">從關鍵字`Keywords_bulgaria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="eaa56-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-179">Keywords</span></span>

<span data-ttu-id="eaa56-180">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-180"></span></span>
|<span data-ttu-id="eaa56-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-182">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-182">dl#</span></span>  <br/> <span data-ttu-id="eaa56-183">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-183">driver license</span></span>  <br/> <span data-ttu-id="eaa56-184">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-184">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-185">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-185">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-186">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-186">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-187">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-187">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-188">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-188">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-189">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-189">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-190">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-190">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-191">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-191">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-192">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-192">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-193">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-194">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МПС</span><span class="sxs-lookup"><span data-stu-id="eaa56-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="eaa56-195">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО</span><span class="sxs-lookup"><span data-stu-id="eaa56-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="eaa56-196">СУМПС</span><span class="sxs-lookup"><span data-stu-id="eaa56-196">сумпс</span></span>  <br/> <span data-ttu-id="eaa56-197">ШОФЬОРСКА КНИЖКА</span><span class="sxs-lookup"><span data-stu-id="eaa56-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="eaa56-198">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="eaa56-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-199">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-199">Format</span></span>

<span data-ttu-id="eaa56-200">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-201">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-201">Pattern</span></span>

<span data-ttu-id="eaa56-202">八位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eaa56-203">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-203">Checksum</span></span>

<span data-ttu-id="eaa56-204">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-205">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-205">Definition</span></span>

<span data-ttu-id="eaa56-206">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-207">規則運算式`Regex_croatia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-208">從關鍵字`Keywords_croatia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="eaa56-209">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-209">Keywords</span></span>

<span data-ttu-id="eaa56-210">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-210"></span></span>
|<span data-ttu-id="eaa56-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-212">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-212">dl#</span></span>  <br/> <span data-ttu-id="eaa56-213">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-213">driver license</span></span>  <br/> <span data-ttu-id="eaa56-214">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-214">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-215">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-215">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-216">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-216">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-217">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-217">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-218">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-218">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-219">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-219">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-220">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-220">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-221">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-221">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-222">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-222">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-223">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="eaa56-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="eaa56-225">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="eaa56-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-226">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-226">Format</span></span>

<span data-ttu-id="eaa56-227">如果沒有空格和分隔符號的 12 位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-228">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-228">Pattern</span></span>

<span data-ttu-id="eaa56-229">12 位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eaa56-230">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-230">Checksum</span></span>

<span data-ttu-id="eaa56-231">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-232">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-232">Definition</span></span>

<span data-ttu-id="eaa56-233">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-234">規則運算式`Regex_cyprus_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-235">從關鍵字`Keywords_cyprus_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-236">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-236">Keywords</span></span>

<span data-ttu-id="eaa56-237">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-237"></span></span>
|<span data-ttu-id="eaa56-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-239">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-239">dl#</span></span>  <br/> <span data-ttu-id="eaa56-240">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-240">driver license</span></span>  <br/> <span data-ttu-id="eaa56-241">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-241">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-242">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-242">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-243">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-243">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-244">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-244">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-245">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-245">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-246">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-246">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-247">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-247">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-248">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-248">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-249">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-250">ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="eaa56-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="eaa56-251">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="eaa56-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-252">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-252">Format</span></span>

<span data-ttu-id="eaa56-253">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-254">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-254">Pattern</span></span>

<span data-ttu-id="eaa56-255">八個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="eaa56-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="eaa56-256">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="eaa56-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="eaa56-257">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="eaa56-257">A space (optional)</span></span>
    
- <span data-ttu-id="eaa56-258">六位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eaa56-259">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-259">Checksum</span></span>

<span data-ttu-id="eaa56-260">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-261">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-261">Definition</span></span>

<span data-ttu-id="eaa56-262">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-263">規則運算式`Regex_czech_republic_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-264">從關鍵字`Keywords_czech_republic_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="eaa56-265">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-265">Keywords</span></span>

<span data-ttu-id="eaa56-266">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-266"></span></span>
|<span data-ttu-id="eaa56-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-268">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-268">dl#</span></span>  <br/> <span data-ttu-id="eaa56-269">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-269">driver license</span></span>  <br/> <span data-ttu-id="eaa56-270">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-270">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-271">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-271">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-272">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-272">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-273">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-273">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-274">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-274">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-275">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-275">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-276">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-276">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-277">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-277">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-278">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-278">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-279">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-279">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-280">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-281">Řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="eaa56-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="eaa56-282">丹麥</span><span class="sxs-lookup"><span data-stu-id="eaa56-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-283">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-283">Format</span></span>

<span data-ttu-id="eaa56-284">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-285">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-285">Pattern</span></span>

<span data-ttu-id="eaa56-286">八位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eaa56-287">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-287">Checksum</span></span>

<span data-ttu-id="eaa56-288">是</span><span class="sxs-lookup"><span data-stu-id="eaa56-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-289">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-289">Definition</span></span>

<span data-ttu-id="eaa56-290">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-291">規則運算式`Regex_denmark_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-292">從關鍵字`Keywords_denmark_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="eaa56-293">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-293">Keywords</span></span>

<span data-ttu-id="eaa56-294">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-294"></span></span>
|<span data-ttu-id="eaa56-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-296">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-296">dl#</span></span>  <br/> <span data-ttu-id="eaa56-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-297">driver license</span></span>  <br/> <span data-ttu-id="eaa56-298">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-298">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-299">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-299">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-300">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-300">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-301">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-301">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-302">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-302">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-303">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-303">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-304">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-304">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-305">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-305">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-306">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-306">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-307">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="eaa56-308">kørekort</span></span>  <br/> <span data-ttu-id="eaa56-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="eaa56-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="eaa56-310">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="eaa56-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-311">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-311">Format</span></span>

<span data-ttu-id="eaa56-312">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-313">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-313">Pattern</span></span>

<span data-ttu-id="eaa56-314">兩個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="eaa56-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="eaa56-315">字母"ET 」 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="eaa56-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="eaa56-316">六位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eaa56-317">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-317">Checksum</span></span>

<span data-ttu-id="eaa56-318">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-319">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-319">Definition</span></span>

<span data-ttu-id="eaa56-320">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-321">規則運算式`Regex_estonia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-322">從關鍵字`Keywords_estonia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-323">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-323">Keywords</span></span>

<span data-ttu-id="eaa56-324">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-324"></span></span>
|<span data-ttu-id="eaa56-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-326">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-326">dl#</span></span>  <br/> <span data-ttu-id="eaa56-327">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-327">driver license</span></span>  <br/> <span data-ttu-id="eaa56-328">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-328">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-329">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-329">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-330">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-330">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-331">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-331">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-332">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-332">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-333">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-333">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-334">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-334">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-335">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-335">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-336">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-336">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-337">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="eaa56-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="eaa56-339">芬蘭</span><span class="sxs-lookup"><span data-stu-id="eaa56-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-340">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-340">Format</span></span>

<span data-ttu-id="eaa56-341">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="eaa56-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-342">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-342">Pattern</span></span>

<span data-ttu-id="eaa56-343">10 位數包含連字號：</span><span class="sxs-lookup"><span data-stu-id="eaa56-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="eaa56-344">六位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-344">Six digits</span></span> 
    
- <span data-ttu-id="eaa56-345">連字號</span><span class="sxs-lookup"><span data-stu-id="eaa56-345">A hyphen</span></span>
    
-  <span data-ttu-id="eaa56-346">四位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="eaa56-347">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-347">Checksum</span></span>

<span data-ttu-id="eaa56-348">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-349">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-349">Definition</span></span>

<span data-ttu-id="eaa56-350">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-351">規則運算式`Regex_finland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-352">從關鍵字`Keywords_finland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-353">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-353">Keywords</span></span>

<span data-ttu-id="eaa56-354">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-354"></span></span>
|<span data-ttu-id="eaa56-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-356">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-356">dl#</span></span>  <br/> <span data-ttu-id="eaa56-357">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-357">driver license</span></span>  <br/> <span data-ttu-id="eaa56-358">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-358">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-359">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-359">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-360">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-360">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-361">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-361">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-362">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-362">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-363">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-363">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-364">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-364">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-365">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-365">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-366">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-366">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-367">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="eaa56-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="eaa56-369">法國</span><span class="sxs-lookup"><span data-stu-id="eaa56-369">France</span></span>

<span data-ttu-id="eaa56-370">如需詳細資訊，請參閱 「 法國駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa56-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="eaa56-371">德國</span><span class="sxs-lookup"><span data-stu-id="eaa56-371">Germany</span></span>

<span data-ttu-id="eaa56-372">如需詳細資訊，請參閱 「 德國駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa56-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="eaa56-373">希臘</span><span class="sxs-lookup"><span data-stu-id="eaa56-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-374">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-374">Format</span></span>

<span data-ttu-id="eaa56-375">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-376">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-376">Pattern</span></span>

 <span data-ttu-id="eaa56-377">九位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="eaa56-378">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-378">Checksum</span></span>

<span data-ttu-id="eaa56-379">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-380">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-380">Definition</span></span>

<span data-ttu-id="eaa56-381">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-382">規則運算式`Regex_greece_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-383">從關鍵字`Keywords_greece_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-384">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-384">Keywords</span></span>

<span data-ttu-id="eaa56-385">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-385"></span></span>
|<span data-ttu-id="eaa56-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="eaa56-387">dlL#</span></span>  <br/> <span data-ttu-id="eaa56-388">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-388">driver license</span></span>  <br/> <span data-ttu-id="eaa56-389">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-389">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-390">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-390">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-391">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-391">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-392">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-392">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-393">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-393">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-394">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-394">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-395">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-395">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-396">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-396">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-397">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-397">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-398">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-399">ΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="eaa56-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="eaa56-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="eaa56-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="eaa56-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="eaa56-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-402">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-402">Format</span></span>

<span data-ttu-id="eaa56-403">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-404">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-404">Pattern</span></span>

<span data-ttu-id="eaa56-405">兩個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="eaa56-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="eaa56-406">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="eaa56-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="eaa56-407">六位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eaa56-408">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-408">Checksum</span></span>

<span data-ttu-id="eaa56-409">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-410">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-410">Definition</span></span>

<span data-ttu-id="eaa56-411">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-412">規則運算式`Regex_hungary_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-413">從關鍵字`Keywords_hungary_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-414">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-414">Keywords</span></span>

<span data-ttu-id="eaa56-415">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-415"></span></span>
|<span data-ttu-id="eaa56-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-417">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-417">dl#</span></span>  <br/> <span data-ttu-id="eaa56-418">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-418">driver license</span></span>  <br/> <span data-ttu-id="eaa56-419">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-419">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-420">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-420">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-421">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-421">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-422">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-422">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-423">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-423">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-424">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-424">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-425">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-425">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-426">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-426">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-427">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-427">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-428">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="eaa56-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="eaa56-430">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="eaa56-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-431">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-431">Format</span></span>

<span data-ttu-id="eaa56-432">四個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-433">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-433">Pattern</span></span>

<span data-ttu-id="eaa56-434">六位數和四個字母：</span><span class="sxs-lookup"><span data-stu-id="eaa56-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="eaa56-435">六位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-435">Six digits</span></span>
    
- <span data-ttu-id="eaa56-436">四個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="eaa56-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eaa56-437">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-437">Checksum</span></span>

<span data-ttu-id="eaa56-438">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-439">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-439">Definition</span></span>

<span data-ttu-id="eaa56-440">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-441">規則運算式`Regex_ireland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-442">從關鍵字`Keywords_ireland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-443">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-443">Keywords</span></span>

<span data-ttu-id="eaa56-444">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-444"></span></span>
|<span data-ttu-id="eaa56-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-446">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-446">dl#</span></span>  <br/> <span data-ttu-id="eaa56-447">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-447">driver license</span></span>  <br/> <span data-ttu-id="eaa56-448">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-448">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-449">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-449">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-450">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-450">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-451">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-451">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-452">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-452">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-453">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-453">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-454">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-454">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-455">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-455">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-456">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-456">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-457">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="eaa56-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="eaa56-459">義大利</span><span class="sxs-lookup"><span data-stu-id="eaa56-459">Italy</span></span>

<span data-ttu-id="eaa56-460">如需詳細資訊，請參閱 「 義大利駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa56-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="eaa56-461">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="eaa56-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-462">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-462">Format</span></span>

<span data-ttu-id="eaa56-463">三個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-464">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-464">Pattern</span></span>

<span data-ttu-id="eaa56-465">三個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="eaa56-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="eaa56-466">三個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="eaa56-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="eaa56-467">六位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eaa56-468">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-468">Checksum</span></span>

<span data-ttu-id="eaa56-469">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-470">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-470">Definition</span></span>

<span data-ttu-id="eaa56-471">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-472">規則運算式`Regex_latvia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-473">從關鍵字`Keywords_latvia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-474">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-474">Keywords</span></span>

<span data-ttu-id="eaa56-475">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-475"></span></span>
|<span data-ttu-id="eaa56-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-477">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-477">dl#</span></span>  <br/> <span data-ttu-id="eaa56-478">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-478">driver license</span></span>  <br/> <span data-ttu-id="eaa56-479">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-479">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-480">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-480">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-481">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-481">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-482">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-482">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-483">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-483">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-484">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-484">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-485">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-485">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-486">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-486">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-487">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-487">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-488">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="eaa56-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="eaa56-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="eaa56-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-491">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-491">Format</span></span>

<span data-ttu-id="eaa56-492">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-493">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-493">Pattern</span></span>

 <span data-ttu-id="eaa56-494">八位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="eaa56-495">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-495">Checksum</span></span>

<span data-ttu-id="eaa56-496">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-497">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-497">Definition</span></span>

<span data-ttu-id="eaa56-498">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-499">規則運算式`Regex_lithuania_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-500">從關鍵字`Keywords_lithuania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-501">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-501">Keywords</span></span>

<span data-ttu-id="eaa56-502">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-502"></span></span>
|<span data-ttu-id="eaa56-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-504">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-504">dl#</span></span>  <br/> <span data-ttu-id="eaa56-505">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-505">driver license</span></span>  <br/> <span data-ttu-id="eaa56-506">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-506">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-507">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-507">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-508">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-508">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-509">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-509">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-510">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-510">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-511">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-511">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-512">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-512">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-513">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-513">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-514">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-514">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-515">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="eaa56-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="eaa56-517">盧森堡</span><span class="sxs-lookup"><span data-stu-id="eaa56-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-518">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-518">Format</span></span>

<span data-ttu-id="eaa56-519">六位數，代表不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="eaa56-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-520">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-520">Pattern</span></span>

 <span data-ttu-id="eaa56-521">六位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="eaa56-522">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-522">Checksum</span></span>

<span data-ttu-id="eaa56-523">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-524">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-524">Definition</span></span>

<span data-ttu-id="eaa56-525">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-526">規則運算式`Regex_luxemburg_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-527">從關鍵字`Keywords_luxemburg_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-528">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-528">Keywords</span></span>

<span data-ttu-id="eaa56-529">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-529"></span></span>
|<span data-ttu-id="eaa56-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-531">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-531">dl#</span></span>  <br/> <span data-ttu-id="eaa56-532">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-532">driver license</span></span>  <br/> <span data-ttu-id="eaa56-533">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-533">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-534">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-534">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-535">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-535">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-536">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-536">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-537">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-537">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-538">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-538">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-539">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-539">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-540">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-540">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-541">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-541">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-542">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="eaa56-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="eaa56-544">馬爾他</span><span class="sxs-lookup"><span data-stu-id="eaa56-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-545">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-545">Format</span></span>

<span data-ttu-id="eaa56-546">兩個字元和六位數，代表所指定的型態的組合</span><span class="sxs-lookup"><span data-stu-id="eaa56-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-547">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-547">Pattern</span></span>

<span data-ttu-id="eaa56-548">兩個字元和六位數的組合：</span><span class="sxs-lookup"><span data-stu-id="eaa56-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="eaa56-549">兩個字元 （數字或字母、 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="eaa56-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="eaa56-550">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="eaa56-550">A space (optional)</span></span>
    
- <span data-ttu-id="eaa56-551">三位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-551">Three digits</span></span>
    
- <span data-ttu-id="eaa56-552">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="eaa56-552">A space (optional)</span></span>
    
- <span data-ttu-id="eaa56-553">三位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eaa56-554">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-554">Checksum</span></span>

<span data-ttu-id="eaa56-555">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-556">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-556">Definition</span></span>

<span data-ttu-id="eaa56-557">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-558">規則運算式`Regex_malta_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-559">從關鍵字`Keywords_malta_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-560">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-560">Keywords</span></span>

<span data-ttu-id="eaa56-561">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-561"></span></span>
|<span data-ttu-id="eaa56-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-563">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-563">dl#</span></span>  <br/> <span data-ttu-id="eaa56-564">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-564">driver license</span></span>  <br/> <span data-ttu-id="eaa56-565">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-565">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-566">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-566">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-567">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-567">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-568">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-568">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-569">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-569">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-570">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-570">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-571">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-571">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-572">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-572">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-573">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-573">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-574">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-575">liċenzja 塔司 sewqan</span><span class="sxs-lookup"><span data-stu-id="eaa56-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="eaa56-576">荷蘭</span><span class="sxs-lookup"><span data-stu-id="eaa56-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-577">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-577">Format</span></span>

<span data-ttu-id="eaa56-578">如果沒有空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-579">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-579">Pattern</span></span>

<span data-ttu-id="eaa56-580">10 位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eaa56-581">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-581">Checksum</span></span>

<span data-ttu-id="eaa56-582">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-583">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-583">Definition</span></span>

<span data-ttu-id="eaa56-584">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-585">規則運算式`Regex_netherlands_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-586">從關鍵字`Keywords_netherlands_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-587">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-587">Keywords</span></span>

<span data-ttu-id="eaa56-588">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-588"></span></span>
|<span data-ttu-id="eaa56-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-590">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-590">dl#</span></span>  <br/> <span data-ttu-id="eaa56-591">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-591">driver license</span></span>  <br/> <span data-ttu-id="eaa56-592">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-592">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-593">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-593">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-594">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-594">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-595">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-595">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-596">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-596">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-597">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-597">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-598">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-598">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-599">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-599">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-600">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-600">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-601">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="eaa56-602">permis de conduire</span></span>  <br/> <span data-ttu-id="eaa56-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="eaa56-603">rijbewijs</span></span>  <br/> <span data-ttu-id="eaa56-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="eaa56-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="eaa56-605">波蘭</span><span class="sxs-lookup"><span data-stu-id="eaa56-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-606">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-606">Format</span></span>

<span data-ttu-id="eaa56-607">14 位數包含正斜線，2</span><span class="sxs-lookup"><span data-stu-id="eaa56-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-608">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-608">Pattern</span></span>

<span data-ttu-id="eaa56-609">14 位數和 2 的正斜線：</span><span class="sxs-lookup"><span data-stu-id="eaa56-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="eaa56-610">五位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-610">Five digits</span></span> 
    
- <span data-ttu-id="eaa56-611">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="eaa56-611">A forward slash</span></span>
    
- <span data-ttu-id="eaa56-612">兩位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-612">Two digits</span></span>
    
- <span data-ttu-id="eaa56-613">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="eaa56-613">A forward slash</span></span>
    
- <span data-ttu-id="eaa56-614">七位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eaa56-615">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-615">Checksum</span></span>

<span data-ttu-id="eaa56-616">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-617">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-617">Definition</span></span>

<span data-ttu-id="eaa56-618">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-619">規則運算式`Regex_poland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-620">從關鍵字`Keywords_poland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-621">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-621">Keywords</span></span>

<span data-ttu-id="eaa56-622">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-622"></span></span>
|<span data-ttu-id="eaa56-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-624">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-624">dl#</span></span>  <br/> <span data-ttu-id="eaa56-625">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-625">driver license</span></span>  <br/> <span data-ttu-id="eaa56-626">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-626">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-627">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-627">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-628">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-628">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-629">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-629">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-630">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-630">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-631">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-631">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-632">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-632">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-633">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-633">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-634">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-634">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-635">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="eaa56-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="eaa56-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="eaa56-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-638">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-638">Format</span></span>

<span data-ttu-id="eaa56-639">兩個字母後尾隨七個的數字中指定的型態</span><span class="sxs-lookup"><span data-stu-id="eaa56-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-640">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-640">Pattern</span></span>

<span data-ttu-id="eaa56-641">兩個字母後尾隨七個具有特殊字元的數字：</span><span class="sxs-lookup"><span data-stu-id="eaa56-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="eaa56-642">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="eaa56-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="eaa56-643">連字號</span><span class="sxs-lookup"><span data-stu-id="eaa56-643">A hyphen</span></span>
    
- <span data-ttu-id="eaa56-644">六位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-644">Six digits</span></span>
    
- <span data-ttu-id="eaa56-645">一個空格</span><span class="sxs-lookup"><span data-stu-id="eaa56-645">A space</span></span>
    
- <span data-ttu-id="eaa56-646">一位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eaa56-647">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-647">Checksum</span></span>

<span data-ttu-id="eaa56-648">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-649">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-649">Definition</span></span>

<span data-ttu-id="eaa56-650">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-651">規則運算式`Regex_portugal_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-652">從關鍵字`Keywords_portugal_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-653">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-653">Keywords</span></span>

<span data-ttu-id="eaa56-654">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-654"></span></span>
|<span data-ttu-id="eaa56-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-656">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-656">dl#</span></span>  <br/> <span data-ttu-id="eaa56-657">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-657">driver license</span></span>  <br/> <span data-ttu-id="eaa56-658">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-658">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-659">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-659">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-660">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-660">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-661">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-661">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-662">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-662">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-663">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-663">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-664">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-664">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-665">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-665">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-666">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-666">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-667">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="eaa56-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="eaa56-669">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="eaa56-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-670">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-670">Format</span></span>

<span data-ttu-id="eaa56-671">一個字元尾隨八位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-672">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-672">Pattern</span></span>

<span data-ttu-id="eaa56-673">尾隨八位數的一個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="eaa56-674">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="eaa56-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="eaa56-675">八位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eaa56-676">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-676">Checksum</span></span>

<span data-ttu-id="eaa56-677">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-678">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-678">Definition</span></span>

<span data-ttu-id="eaa56-679">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-680">規則運算式`Regex_romania_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-681">從關鍵字`Keywords_romania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-682">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-682">Keywords</span></span>

<span data-ttu-id="eaa56-683">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-683"></span></span>
|<span data-ttu-id="eaa56-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-685">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-685">dl#</span></span>  <br/> <span data-ttu-id="eaa56-686">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-686">driver license</span></span>  <br/> <span data-ttu-id="eaa56-687">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-687">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-688">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-688">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-689">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-689">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-690">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-690">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-691">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-691">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-692">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-692">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-693">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-693">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-694">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-694">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-695">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-695">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-696">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="eaa56-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="eaa56-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="eaa56-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-699">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-699">Format</span></span>

<span data-ttu-id="eaa56-700">一個字元尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-701">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-701">Pattern</span></span>

<span data-ttu-id="eaa56-702">一個字元尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="eaa56-703">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="eaa56-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="eaa56-704">七位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="eaa56-705">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-705">Checksum</span></span>

<span data-ttu-id="eaa56-706">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-707">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-707">Definition</span></span>

<span data-ttu-id="eaa56-708">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-709">規則運算式`Regex_slovakia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-710">從關鍵字`Keywords_slovakia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-711">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-711">Keywords</span></span>

<span data-ttu-id="eaa56-712">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-712"></span></span>
|<span data-ttu-id="eaa56-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-714">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-714">dl#</span></span>  <br/> <span data-ttu-id="eaa56-715">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-715">driver license</span></span>  <br/> <span data-ttu-id="eaa56-716">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-716">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-717">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-717">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-718">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-718">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-719">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-719">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-720">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-720">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-721">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-721">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-722">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-722">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-723">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-723">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-724">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-724">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-725">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="eaa56-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="eaa56-727">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="eaa56-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-728">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-728">Format</span></span>

<span data-ttu-id="eaa56-729">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-730">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-730">Pattern</span></span>

<span data-ttu-id="eaa56-731">九位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="eaa56-732">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-732">Checksum</span></span>

<span data-ttu-id="eaa56-733">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-734">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-734">Definition</span></span>

<span data-ttu-id="eaa56-735">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-736">規則運算式`Regex_slovenia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-737">從關鍵字`Keywords_slovenia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-738">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-738">Keywords</span></span>

<span data-ttu-id="eaa56-739">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-739"></span></span>
|<span data-ttu-id="eaa56-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-741">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-741">dl#</span></span>  <br/> <span data-ttu-id="eaa56-742">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-742">driver license</span></span>  <br/> <span data-ttu-id="eaa56-743">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-743">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-744">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-744">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-745">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-745">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-746">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-746">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-747">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-747">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-748">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-748">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-749">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-749">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-750">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-750">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-751">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-751">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-752">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="eaa56-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="eaa56-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="eaa56-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-755">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-755">Format</span></span>

<span data-ttu-id="eaa56-756">後面接著一個字元的八位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-757">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-757">Pattern</span></span>

<span data-ttu-id="eaa56-758">後面接著一個字元的八位數：</span><span class="sxs-lookup"><span data-stu-id="eaa56-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="eaa56-759">八位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-759">Eight digits</span></span> 
    
- <span data-ttu-id="eaa56-760">一個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="eaa56-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eaa56-761">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-761">Checksum</span></span>

<span data-ttu-id="eaa56-762">是</span><span class="sxs-lookup"><span data-stu-id="eaa56-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-763">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-763">Definition</span></span>

<span data-ttu-id="eaa56-764">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-765">函式`Func_spain_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-766">從關鍵字`Keywords_spain_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="eaa56-767">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-767">Keywords</span></span>

<span data-ttu-id="eaa56-768">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-768"></span></span>
|<span data-ttu-id="eaa56-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-770">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-771">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-771">dl#</span></span>  <br/> <span data-ttu-id="eaa56-772">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-772">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-773">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-773">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-774">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-774">driver license</span></span>  <br/> <span data-ttu-id="eaa56-775">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-775">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-776">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-776">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-777">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-777">driver's licence</span></span>  <br/> <span data-ttu-id="eaa56-778">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-778">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-779">driving 授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-779">driving licence</span></span>  <br/> <span data-ttu-id="eaa56-780">主導授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-780">driving license</span></span>  <br/> <span data-ttu-id="eaa56-781">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-781">driver licence number</span></span>  <br/> <span data-ttu-id="eaa56-782">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-782">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-783">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-783">drivers licence number</span></span>  <br/> <span data-ttu-id="eaa56-784">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-784">drivers license number</span></span>  <br/> <span data-ttu-id="eaa56-785">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-785">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-786">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-786">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-787">driving 授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-787">driving licence number</span></span>  <br/> <span data-ttu-id="eaa56-788">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-788">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-789">主導允許</span><span class="sxs-lookup"><span data-stu-id="eaa56-789">driving permit</span></span>  <br/> <span data-ttu-id="eaa56-790">主導允許數字</span><span class="sxs-lookup"><span data-stu-id="eaa56-790">driving permit number</span></span>  <br/> <span data-ttu-id="eaa56-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="eaa56-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="eaa56-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="eaa56-792">permiso conducción</span></span>  <br/> <span data-ttu-id="eaa56-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="eaa56-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="eaa56-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="eaa56-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="eaa56-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="eaa56-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="eaa56-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="eaa56-796">licencia conducir</span></span>  <br/> <span data-ttu-id="eaa56-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="eaa56-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="eaa56-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="eaa56-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="eaa56-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="eaa56-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="eaa56-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="eaa56-800">permiso conducir</span></span>  <br/> <span data-ttu-id="eaa56-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="eaa56-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="eaa56-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="eaa56-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="eaa56-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="eaa56-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="eaa56-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="eaa56-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="eaa56-805">格式</span><span class="sxs-lookup"><span data-stu-id="eaa56-805">Format</span></span>

<span data-ttu-id="eaa56-806">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="eaa56-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="eaa56-807">模式</span><span class="sxs-lookup"><span data-stu-id="eaa56-807">Pattern</span></span>

<span data-ttu-id="eaa56-808">10 位數包含連字號：</span><span class="sxs-lookup"><span data-stu-id="eaa56-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="eaa56-809">六位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-809">Six digits</span></span> 
    
- <span data-ttu-id="eaa56-810">連字號</span><span class="sxs-lookup"><span data-stu-id="eaa56-810">A hyphen</span></span>
    
- <span data-ttu-id="eaa56-811">四位數</span><span class="sxs-lookup"><span data-stu-id="eaa56-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="eaa56-812">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-812">Checksum</span></span>

<span data-ttu-id="eaa56-813">否</span><span class="sxs-lookup"><span data-stu-id="eaa56-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="eaa56-814">定義</span><span class="sxs-lookup"><span data-stu-id="eaa56-814">Definition</span></span>

<span data-ttu-id="eaa56-815">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="eaa56-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="eaa56-816">規則運算式`Regex_sweden_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="eaa56-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="eaa56-817">從關鍵字`Keywords_sweden_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="eaa56-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="eaa56-818">關鍵字</span><span class="sxs-lookup"><span data-stu-id="eaa56-818">Keywords</span></span>

<span data-ttu-id="eaa56-819">| |</span><span class="sxs-lookup"><span data-stu-id="eaa56-819"></span></span>
|<span data-ttu-id="eaa56-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="eaa56-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="eaa56-821">dl #</span><span class="sxs-lookup"><span data-stu-id="eaa56-821">dl#</span></span>  <br/> <span data-ttu-id="eaa56-822">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-822">driver license</span></span>  <br/> <span data-ttu-id="eaa56-823">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-823">driver license number</span></span>  <br/> <span data-ttu-id="eaa56-824">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-824">driver licence</span></span>  <br/> <span data-ttu-id="eaa56-825">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="eaa56-825">drivers lic.</span></span>  <br/> <span data-ttu-id="eaa56-826">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-826">drivers license</span></span>  <br/> <span data-ttu-id="eaa56-827">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="eaa56-827">drivers licence</span></span>  <br/> <span data-ttu-id="eaa56-828">駕照</span><span class="sxs-lookup"><span data-stu-id="eaa56-828">driver's license</span></span>  <br/> <span data-ttu-id="eaa56-829">駕照編號</span><span class="sxs-lookup"><span data-stu-id="eaa56-829">driver's license number</span></span>  <br/> <span data-ttu-id="eaa56-830">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="eaa56-830">driver's licence number</span></span>  <br/> <span data-ttu-id="eaa56-831">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="eaa56-831">driving license number</span></span>  <br/> <span data-ttu-id="eaa56-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="eaa56-832">dlno#</span></span>  <br/> <span data-ttu-id="eaa56-833">körkort</span><span class="sxs-lookup"><span data-stu-id="eaa56-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="eaa56-834">英國</span><span class="sxs-lookup"><span data-stu-id="eaa56-834">UK</span></span>

<span data-ttu-id="eaa56-835">如需詳細資訊，請參閱區段 」 英國</span><span class="sxs-lookup"><span data-stu-id="eaa56-835">For details, see the section "U.K.</span></span> <span data-ttu-id="eaa56-836">驅動程式的授權數目 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa56-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eaa56-837">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eaa56-837">See also</span></span>

[<span data-ttu-id="eaa56-838">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="eaa56-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

