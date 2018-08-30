---
title: 歐盟稅識別碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: 本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟稅識別碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
ms.openlocfilehash: 5192496b393d15fd6d063e09c9bfe1cb3dd7e2dd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526727"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="c1496-104">歐盟稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-104">EU Tax Identification Number</span></span>

<span data-ttu-id="c1496-p102">本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟稅識別號碼 （錫） 敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。</span><span class="sxs-lookup"><span data-stu-id="c1496-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="c1496-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="c1496-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="c1496-108">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-108">Format</span></span>

<span data-ttu-id="c1496-109">選擇性連字號和正斜線的九個位數</span><span class="sxs-lookup"><span data-stu-id="c1496-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-110">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-110">Pattern</span></span>

<span data-ttu-id="c1496-111">選擇性連字號和正斜線的九個位數：</span><span class="sxs-lookup"><span data-stu-id="c1496-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="c1496-112">兩位數</span><span class="sxs-lookup"><span data-stu-id="c1496-112">Two digits</span></span> 
    
- <span data-ttu-id="c1496-113">一個連字號 (選用)</span><span class="sxs-lookup"><span data-stu-id="c1496-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="c1496-114">三位數</span><span class="sxs-lookup"><span data-stu-id="c1496-114">Three digits</span></span>
    
- <span data-ttu-id="c1496-115">一個正斜線 (選用)</span><span class="sxs-lookup"><span data-stu-id="c1496-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="c1496-116">四位數</span><span class="sxs-lookup"><span data-stu-id="c1496-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-117">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-117">Checksum</span></span>

<span data-ttu-id="c1496-118">是</span><span class="sxs-lookup"><span data-stu-id="c1496-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-119">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-119">Definition</span></span>

<span data-ttu-id="c1496-120">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-121">此函數`Func_austria_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-122">從關鍵字`Keywords_austria_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-123">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-124">此函數`Func_austria_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-125">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="c1496-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-127">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-127">tax number</span></span>
  
<span data-ttu-id="c1496-128">數字</span><span class="sxs-lookup"><span data-stu-id="c1496-128">number</span></span>
  
<span data-ttu-id="c1496-129">稅註冊編號</span><span class="sxs-lookup"><span data-stu-id="c1496-129">tax registration number</span></span>
  
<span data-ttu-id="c1496-130">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-130">tax id</span></span>
  
<span data-ttu-id="c1496-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="c1496-131">st.nr.</span></span>
  
<span data-ttu-id="c1496-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="c1496-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="c1496-133">比利時</span><span class="sxs-lookup"><span data-stu-id="c1496-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="c1496-134">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-134">Format</span></span>

<span data-ttu-id="c1496-135">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="c1496-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-136">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-136">Pattern</span></span>

<span data-ttu-id="c1496-137">11 位數：</span><span class="sxs-lookup"><span data-stu-id="c1496-137">11 digits:</span></span>
  
- <span data-ttu-id="c1496-138">兩位數</span><span class="sxs-lookup"><span data-stu-id="c1496-138">Two digits</span></span>
    
- <span data-ttu-id="c1496-139">"0"或者"1"</span><span class="sxs-lookup"><span data-stu-id="c1496-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="c1496-140">一個數字</span><span class="sxs-lookup"><span data-stu-id="c1496-140">One digit</span></span>
    
- <span data-ttu-id="c1496-141">"0"或"1"或"2"或者"3"</span><span class="sxs-lookup"><span data-stu-id="c1496-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="c1496-142">六位數</span><span class="sxs-lookup"><span data-stu-id="c1496-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-143">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-143">Checksum</span></span>

<span data-ttu-id="c1496-144">不適用</span><span class="sxs-lookup"><span data-stu-id="c1496-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-145">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-145">Definition</span></span>

<span data-ttu-id="c1496-146">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-147">規則運算式`Regex_belgium_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-148">從關鍵字`Keywords_belgium_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-149">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="c1496-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-151">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-151">tax number</span></span>
  
<span data-ttu-id="c1496-152">國際號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-152">national registration number</span></span>
  
<span data-ttu-id="c1496-153">稅註冊編號</span><span class="sxs-lookup"><span data-stu-id="c1496-153">tax registration number</span></span>
  
<span data-ttu-id="c1496-154">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-154">tax id</span></span>
  
<span data-ttu-id="c1496-155">n 如果</span><span class="sxs-lookup"><span data-stu-id="c1496-155">nif</span></span>
  
<span data-ttu-id="c1496-156">n 如果 #</span><span class="sxs-lookup"><span data-stu-id="c1496-156">nif#</span></span>
  
<span data-ttu-id="c1496-157">numéro de registre national</span><span class="sxs-lookup"><span data-stu-id="c1496-157">numéro de registre national</span></span>
  
<span data-ttu-id="c1496-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="c1496-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="c1496-159">保加利亞</span><span class="sxs-lookup"><span data-stu-id="c1496-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="c1496-160">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-160">Format</span></span>

<span data-ttu-id="c1496-161">十位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="c1496-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-162">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-162">Pattern</span></span>

<span data-ttu-id="c1496-163">10 位數</span><span class="sxs-lookup"><span data-stu-id="c1496-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c1496-164">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-164">Checksum</span></span>

<span data-ttu-id="c1496-165">是</span><span class="sxs-lookup"><span data-stu-id="c1496-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-166">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-166">Definition</span></span>

<span data-ttu-id="c1496-167">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-168">此函數`Func_bulgaria_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-169">從關鍵字`Keywords_bulgaria_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-170">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-171">此函數`Func_bulgaria_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-172">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="c1496-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-174">bucn</span><span class="sxs-lookup"><span data-stu-id="c1496-174">bucn</span></span>
  
<span data-ttu-id="c1496-175">統一民事數目</span><span class="sxs-lookup"><span data-stu-id="c1496-175">uniform civil number</span></span>
  
<span data-ttu-id="c1496-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="c1496-176">bucn#</span></span>
  
<span data-ttu-id="c1496-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="c1496-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="c1496-178">統一民事識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-178">uniform civil id</span></span>
  
<span data-ttu-id="c1496-179">統一民事否</span><span class="sxs-lookup"><span data-stu-id="c1496-179">uniform civil no</span></span>
  
<span data-ttu-id="c1496-180">egn</span><span class="sxs-lookup"><span data-stu-id="c1496-180">egn</span></span>
  
<span data-ttu-id="c1496-181">保加利亞統一民事數目</span><span class="sxs-lookup"><span data-stu-id="c1496-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="c1496-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="c1496-182">uniformcivilno#</span></span>
  
<span data-ttu-id="c1496-183">egn #</span><span class="sxs-lookup"><span data-stu-id="c1496-183">egn#</span></span>
  
<span data-ttu-id="c1496-184">УНИФОРМ ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="c1496-184">униформ граждански номер</span></span>
  
<span data-ttu-id="c1496-185">Униформ 識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-185">униформ id</span></span>
  
<span data-ttu-id="c1496-186">Униформ граждански 識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-186">униформ граждански id</span></span>
  
<span data-ttu-id="c1496-187">УНИФОРМ ГРАЖДАНСКИ НЕ</span><span class="sxs-lookup"><span data-stu-id="c1496-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="c1496-188">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="c1496-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="c1496-189">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-189">Format</span></span>

<span data-ttu-id="c1496-190">任何空格或分隔符號 11 位數</span><span class="sxs-lookup"><span data-stu-id="c1496-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-191">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-191">Pattern</span></span>

<span data-ttu-id="c1496-192">11 位數：</span><span class="sxs-lookup"><span data-stu-id="c1496-192">11 digits:</span></span>
  
- <span data-ttu-id="c1496-193">十位數，隨機選擇</span><span class="sxs-lookup"><span data-stu-id="c1496-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="c1496-194">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="c1496-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-195">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-195">Checksum</span></span>

<span data-ttu-id="c1496-196">是</span><span class="sxs-lookup"><span data-stu-id="c1496-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-197">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-197">Definition</span></span>

<span data-ttu-id="c1496-198">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-199">此函數`Func_croatia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-200">從關鍵字`Keywords_croatia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-201">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-202">此函數`Func_croatia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-203">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="c1496-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-205">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-205">tax number</span></span>
  
<span data-ttu-id="c1496-206">稅</span><span class="sxs-lookup"><span data-stu-id="c1496-206">tax</span></span>
  
<span data-ttu-id="c1496-207">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-207">tax id</span></span>
  
<span data-ttu-id="c1496-208">oid</span><span class="sxs-lookup"><span data-stu-id="c1496-208">oid</span></span>
  
<span data-ttu-id="c1496-209">oid #</span><span class="sxs-lookup"><span data-stu-id="c1496-209">oid#</span></span>
  
<span data-ttu-id="c1496-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="c1496-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="c1496-211">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="c1496-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="c1496-212">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-212">Format</span></span>

<span data-ttu-id="c1496-213">八個位數和指定的型態的其中一個字母</span><span class="sxs-lookup"><span data-stu-id="c1496-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-214">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-214">Pattern</span></span>

<span data-ttu-id="c1496-215">八個位數和一個字母：</span><span class="sxs-lookup"><span data-stu-id="c1496-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="c1496-216">"0"</span><span class="sxs-lookup"><span data-stu-id="c1496-216">A "0"</span></span> 
    
- <span data-ttu-id="c1496-217">七位數</span><span class="sxs-lookup"><span data-stu-id="c1496-217">Seven digits</span></span>
    
- <span data-ttu-id="c1496-218">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c1496-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-219">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-219">Checksum</span></span>

<span data-ttu-id="c1496-220">不適用</span><span class="sxs-lookup"><span data-stu-id="c1496-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-221">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-221">Definition</span></span>

<span data-ttu-id="c1496-222">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-223">此函數`Func_cyprus_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-224">從關鍵字`Keywords_cyprus_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-225">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-226">此函數`Func_cyprus_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="c1496-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-229">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-229">tax number</span></span>
  
<span data-ttu-id="c1496-230">稅</span><span class="sxs-lookup"><span data-stu-id="c1496-230">tax</span></span>
  
<span data-ttu-id="c1496-231">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-231">tax id</span></span>
  
<span data-ttu-id="c1496-232">稅識別程式碼</span><span class="sxs-lookup"><span data-stu-id="c1496-232">tax identification code</span></span>
  
<span data-ttu-id="c1496-233">tic</span><span class="sxs-lookup"><span data-stu-id="c1496-233">tic</span></span>
  
<span data-ttu-id="c1496-234">tic #</span><span class="sxs-lookup"><span data-stu-id="c1496-234">tic#</span></span>
  
<span data-ttu-id="c1496-235">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="c1496-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="c1496-236">ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ</span><span class="sxs-lookup"><span data-stu-id="c1496-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="c1496-237">ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="c1496-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="c1496-238">捷克</span><span class="sxs-lookup"><span data-stu-id="c1496-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="c1496-239">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-239">Format</span></span>

<span data-ttu-id="c1496-240">使用選用的反斜線的九個或十位數</span><span class="sxs-lookup"><span data-stu-id="c1496-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-241">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-241">Pattern</span></span>

<span data-ttu-id="c1496-242">具有選用 backslashl 9 或 10 位數：</span><span class="sxs-lookup"><span data-stu-id="c1496-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="c1496-243">六位數</span><span class="sxs-lookup"><span data-stu-id="c1496-243">Six digits</span></span> 
    
- <span data-ttu-id="c1496-244">反斜線 （選用）</span><span class="sxs-lookup"><span data-stu-id="c1496-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="c1496-245">三個或四位數字</span><span class="sxs-lookup"><span data-stu-id="c1496-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-246">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-246">Checksum</span></span>

<span data-ttu-id="c1496-247">不適用</span><span class="sxs-lookup"><span data-stu-id="c1496-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-248">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-248">Definition</span></span>

<span data-ttu-id="c1496-249">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-250">規則運算式`Regex_czech_republic_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-251">從關鍵字`Keywords_czech_republic_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-252">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="c1496-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-254">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-254">tax number</span></span>
  
<span data-ttu-id="c1496-255">稅</span><span class="sxs-lookup"><span data-stu-id="c1496-255">tax</span></span>
  
<span data-ttu-id="c1496-256">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-256">tax id</span></span>
  
<span data-ttu-id="c1496-257">個人的數字</span><span class="sxs-lookup"><span data-stu-id="c1496-257">personal number</span></span>
  
<span data-ttu-id="c1496-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="c1496-258">daňové číslo</span></span>
  
<span data-ttu-id="c1496-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="c1496-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="c1496-260">丹麥</span><span class="sxs-lookup"><span data-stu-id="c1496-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="c1496-261">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-261">Format</span></span>

<span data-ttu-id="c1496-262">十個包含連字號的數字</span><span class="sxs-lookup"><span data-stu-id="c1496-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-263">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-263">Pattern</span></span>

<span data-ttu-id="c1496-264">包含 hyphenl 十位數：</span><span class="sxs-lookup"><span data-stu-id="c1496-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="c1496-265">會對應至出生日期 (DDMMYY) 的六個數字</span><span class="sxs-lookup"><span data-stu-id="c1496-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="c1496-266">一個連字號</span><span class="sxs-lookup"><span data-stu-id="c1496-266">A hyphen</span></span>
    
- <span data-ttu-id="c1496-267">會對應至其中的第一個數字會對應至出生的 century 序號的四個字和最後一個數字會對應至個人的性別 （2 男和即使女性奇數）</span><span class="sxs-lookup"><span data-stu-id="c1496-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-268">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-268">Checksum</span></span>

<span data-ttu-id="c1496-269">是</span><span class="sxs-lookup"><span data-stu-id="c1496-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-270">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-270">Definition</span></span>

<span data-ttu-id="c1496-271">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-272">此函數`Func_denmark_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-273">從關鍵字`Keywords_denmark_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-274">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-275">此函數`Func_denmark_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-276">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="c1496-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-278">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-278">tax number</span></span>
  
<span data-ttu-id="c1496-279">稅</span><span class="sxs-lookup"><span data-stu-id="c1496-279">tax</span></span>
  
<span data-ttu-id="c1496-280">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-280">tax id</span></span>
  
<span data-ttu-id="c1496-281">cpr 數目</span><span class="sxs-lookup"><span data-stu-id="c1496-281">cpr number</span></span>
  
<span data-ttu-id="c1496-282">cpr #</span><span class="sxs-lookup"><span data-stu-id="c1496-282">cpr#</span></span>
  
<span data-ttu-id="c1496-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="c1496-283">skat nummer</span></span>
  
<span data-ttu-id="c1496-284">skat 識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="c1496-285">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="c1496-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="c1496-286">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-286">Format</span></span>

<span data-ttu-id="c1496-287">任何空格或分隔符號 11 位數</span><span class="sxs-lookup"><span data-stu-id="c1496-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-288">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-288">Pattern</span></span>

<span data-ttu-id="c1496-289">11 位數：</span><span class="sxs-lookup"><span data-stu-id="c1496-289">11 digits:</span></span>
  
-  <span data-ttu-id="c1496-290">會對應至性別和出生其中奇數指出 2 男和偶數指出女性，如下所示的 century 的一個數字： 1，2 19 的 century;3、 4 20 的 century;與 5、 6 第 21 世紀</span><span class="sxs-lookup"><span data-stu-id="c1496-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="c1496-291">會對應至出生日期 (YYMMDD) 的六個數字</span><span class="sxs-lookup"><span data-stu-id="c1496-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="c1496-292">會對應至分隔出生日期相同的人員序號的三個位數</span><span class="sxs-lookup"><span data-stu-id="c1496-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="c1496-293">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="c1496-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-294">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-294">Checksum</span></span>

<span data-ttu-id="c1496-295">是</span><span class="sxs-lookup"><span data-stu-id="c1496-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-296">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-296">Definition</span></span>

<span data-ttu-id="c1496-297">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-298">此函數`Func_estonia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-299">從關鍵字`Keywords_estonia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-300">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-301">此函數`Func_estonia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-302">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="c1496-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-304">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-304">tax number</span></span>
  
<span data-ttu-id="c1496-305">稅</span><span class="sxs-lookup"><span data-stu-id="c1496-305">tax</span></span>
  
<span data-ttu-id="c1496-306">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-306">tax id</span></span>
  
<span data-ttu-id="c1496-307">個人的程式碼</span><span class="sxs-lookup"><span data-stu-id="c1496-307">personal code</span></span>
  
<span data-ttu-id="c1496-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="c1496-308">maksunumber</span></span>
  
<span data-ttu-id="c1496-309">maksu 識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-309">maksu id</span></span>
  
<span data-ttu-id="c1496-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="c1496-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="c1496-311">芬蘭</span><span class="sxs-lookup"><span data-stu-id="c1496-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="c1496-312">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-312">Format</span></span>

<span data-ttu-id="c1496-313">信件的數字，11 個字元組合，並加號與減號</span><span class="sxs-lookup"><span data-stu-id="c1496-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-314">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-314">Pattern</span></span>

<span data-ttu-id="c1496-315">信件的數字，11 個字元組合，並加號與減號：</span><span class="sxs-lookup"><span data-stu-id="c1496-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="c1496-316">六位數</span><span class="sxs-lookup"><span data-stu-id="c1496-316">Six digits</span></span>
    
- <span data-ttu-id="c1496-317">下列其中之一： 加號、 減號、 或字母"A"（不區分大小寫） 其中加號表示出生 1800年 1899年之間減號登入表示出生之間 1900年-1999年和"A"表示出生 2000年及之後</span><span class="sxs-lookup"><span data-stu-id="c1496-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="c1496-318">三位數</span><span class="sxs-lookup"><span data-stu-id="c1496-318">Three digits</span></span>
    
- <span data-ttu-id="c1496-319">一個字母或一個數字</span><span class="sxs-lookup"><span data-stu-id="c1496-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-320">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-320">Checksum</span></span>

<span data-ttu-id="c1496-321">是</span><span class="sxs-lookup"><span data-stu-id="c1496-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-322">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-322">Definition</span></span>

<span data-ttu-id="c1496-323">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-324">此函數`Func_finland_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-325">從關鍵字`Keywords_finland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-326">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-327">此函數`Func_finland_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-328">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="c1496-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-330">identification number
</span><span class="sxs-lookup"><span data-stu-id="c1496-330">identification number</span></span>
  
<span data-ttu-id="c1496-331">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-331">personal id</span></span>
  
<span data-ttu-id="c1496-332">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-332">identity number</span></span>
  
<span data-ttu-id="c1496-333">芬蘭國家識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-333">finnish national id number</span></span>
  
<span data-ttu-id="c1496-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="c1496-334">personalidnumber#</span></span>
  
<span data-ttu-id="c1496-335">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-335">national identification number</span></span>
  
<span data-ttu-id="c1496-336">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-336">id number</span></span>
  
<span data-ttu-id="c1496-337">國家識別碼沒有。</span><span class="sxs-lookup"><span data-stu-id="c1496-337">national id no.</span></span>
  
<span data-ttu-id="c1496-338">國家識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-338">national id number</span></span>
  
<span data-ttu-id="c1496-339">識別碼沒有</span><span class="sxs-lookup"><span data-stu-id="c1496-339">id no</span></span>
  
<span data-ttu-id="c1496-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="c1496-340">tunnistenumero</span></span>
  
<span data-ttu-id="c1496-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="c1496-341">henkilötunnus</span></span>
  
<span data-ttu-id="c1496-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="c1496-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="c1496-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="c1496-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="c1496-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="c1496-344">identiteetti numero</span></span>
  
<span data-ttu-id="c1496-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="c1496-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="c1496-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="c1496-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="c1496-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="c1496-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="c1496-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="c1496-348">tunnusnumero</span></span>
  
<span data-ttu-id="c1496-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="c1496-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="c1496-350">法國</span><span class="sxs-lookup"><span data-stu-id="c1496-350">France</span></span>

### <a name="format"></a><span data-ttu-id="c1496-351">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-351">Format</span></span>

<span data-ttu-id="c1496-352">13 個人和實體的九個位數的數字</span><span class="sxs-lookup"><span data-stu-id="c1496-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-353">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-353">Pattern</span></span>

<span data-ttu-id="c1496-354">針對個人的數字 13:</span><span class="sxs-lookup"><span data-stu-id="c1496-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="c1496-355">必須是 0、 1、 2 或 3 的一個數字</span><span class="sxs-lookup"><span data-stu-id="c1496-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="c1496-356">12 位數</span><span class="sxs-lookup"><span data-stu-id="c1496-356">12 digits</span></span>
    
<span data-ttu-id="c1496-357">實體的九個位數</span><span class="sxs-lookup"><span data-stu-id="c1496-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c1496-358">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-358">Checksum</span></span>

<span data-ttu-id="c1496-359">不適用</span><span class="sxs-lookup"><span data-stu-id="c1496-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-360">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-360">Definition</span></span>

<span data-ttu-id="c1496-361">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-362">此函數`Func_france_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-363">從關鍵字`Keywords_france_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-364">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-365">此函數`Func_france_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-366">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="c1496-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-368">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-368">tax identification number</span></span>
  
<span data-ttu-id="c1496-369">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-369">tax number</span></span>
  
<span data-ttu-id="c1496-370">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-370">tax id</span></span>
  
<span data-ttu-id="c1496-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="c1496-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="c1496-372">德國</span><span class="sxs-lookup"><span data-stu-id="c1496-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="c1496-373">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-373">Format</span></span>

<span data-ttu-id="c1496-374">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="c1496-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-375">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-375">Pattern</span></span>

<span data-ttu-id="c1496-376">11 位數：</span><span class="sxs-lookup"><span data-stu-id="c1496-376">11 digits :</span></span>
  
-  <span data-ttu-id="c1496-377">十位數</span><span class="sxs-lookup"><span data-stu-id="c1496-377">Ten digits</span></span> 
    
- <span data-ttu-id="c1496-378">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="c1496-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-379">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-379">Checksum</span></span>

<span data-ttu-id="c1496-380">是</span><span class="sxs-lookup"><span data-stu-id="c1496-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-381">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-381">Definition</span></span>

<span data-ttu-id="c1496-382">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-383">此函數`Func_germany_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-384">從關鍵字`Keywords_germany_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-385">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-386">此函數`Func_germany_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-387">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="c1496-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-389">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-389">tax number</span></span>
  
<span data-ttu-id="c1496-390">稅否]。</span><span class="sxs-lookup"><span data-stu-id="c1496-390">tax no.</span></span>
  
<span data-ttu-id="c1496-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="c1496-391">taxno#</span></span>
  
<span data-ttu-id="c1496-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c1496-392">taxnumber#</span></span>
  
<span data-ttu-id="c1496-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c1496-393">taxnumber</span></span>
  
<span data-ttu-id="c1496-394">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-394">tax id</span></span>
  
<span data-ttu-id="c1496-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="c1496-395">taxid#</span></span>
  
<span data-ttu-id="c1496-396">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-396">tax identification number</span></span>
  
<span data-ttu-id="c1496-397">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1496-397">tax identification no.</span></span>
  
<span data-ttu-id="c1496-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="c1496-398">steuernummer</span></span>
  
<span data-ttu-id="c1496-399">steuer 識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-399">steuer id</span></span>
  
<span data-ttu-id="c1496-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="c1496-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="c1496-401">希臘</span><span class="sxs-lookup"><span data-stu-id="c1496-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="c1496-402">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-402">Format</span></span>

<span data-ttu-id="c1496-403">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="c1496-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-404">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-404">Pattern</span></span>

<span data-ttu-id="c1496-405">九位數</span><span class="sxs-lookup"><span data-stu-id="c1496-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c1496-406">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-406">Checksum</span></span>

<span data-ttu-id="c1496-407">不適用</span><span class="sxs-lookup"><span data-stu-id="c1496-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-408">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-408">Definition</span></span>

<span data-ttu-id="c1496-409">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-410">規則運算式`Regex_greece_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-411">從關鍵字`Keywords_greece_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-412">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="c1496-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-414">afm</span><span class="sxs-lookup"><span data-stu-id="c1496-414">afm</span></span>
  
<span data-ttu-id="c1496-415">tin
</span><span class="sxs-lookup"><span data-stu-id="c1496-415">tin</span></span>
  
<span data-ttu-id="c1496-416">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1496-416">tax id no.</span></span>
  
<span data-ttu-id="c1496-417">無法稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-417">tax id no</span></span>
  
<span data-ttu-id="c1496-418">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-418">tax identification number</span></span>
  
<span data-ttu-id="c1496-419">稅登錄編號</span><span class="sxs-lookup"><span data-stu-id="c1496-419">tax registry number</span></span>
  
<span data-ttu-id="c1496-420">無法稅登錄。</span><span class="sxs-lookup"><span data-stu-id="c1496-420">tax registry no.</span></span>
  
<span data-ttu-id="c1496-421">afm #</span><span class="sxs-lookup"><span data-stu-id="c1496-421">afm#</span></span>
  
<span data-ttu-id="c1496-422">錫 #</span><span class="sxs-lookup"><span data-stu-id="c1496-422">tin#</span></span>
  
<span data-ttu-id="c1496-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="c1496-423">taxidno#</span></span>
  
<span data-ttu-id="c1496-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="c1496-424">taxregistryno#</span></span>
  
<span data-ttu-id="c1496-425">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="c1496-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="c1496-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="c1496-426">aφμ</span></span>
  
<span data-ttu-id="c1496-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="c1496-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="c1496-428">ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ。</span><span class="sxs-lookup"><span data-stu-id="c1496-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="c1496-429">ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="c1496-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="c1496-430">匈牙利</span><span class="sxs-lookup"><span data-stu-id="c1496-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="c1496-431">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-431">Format</span></span>

<span data-ttu-id="c1496-432">任何空格或分隔符號十位數</span><span class="sxs-lookup"><span data-stu-id="c1496-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-433">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-433">Pattern</span></span>

<span data-ttu-id="c1496-434">十位數：</span><span class="sxs-lookup"><span data-stu-id="c1496-434">Ten digits:</span></span>
  
-  <span data-ttu-id="c1496-435">必須是"8"的一個數字</span><span class="sxs-lookup"><span data-stu-id="c1496-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="c1496-436">會對應至日期之間的天數的五個位數 01/01/1867年和個別的出生的日期</span><span class="sxs-lookup"><span data-stu-id="c1496-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="c1496-437">三個對應來區分個人在同一天出生依照機率產生的號碼的數字</span><span class="sxs-lookup"><span data-stu-id="c1496-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="c1496-438">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="c1496-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-439">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-439">Checksum</span></span>

<span data-ttu-id="c1496-440">是</span><span class="sxs-lookup"><span data-stu-id="c1496-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-441">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-441">Definition</span></span>

<span data-ttu-id="c1496-442">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-443">此函數`Func_hungary_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-444">從關鍵字`Keywords_hungary_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-445">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-446">此函數`Func_hungary_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-447">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="c1496-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-449">匈牙利文稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="c1496-450">匈牙利文錫</span><span class="sxs-lookup"><span data-stu-id="c1496-450">hungarian tin</span></span>
  
<span data-ttu-id="c1496-451">稅 id 號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-451">tax id number</span></span>
  
<span data-ttu-id="c1496-452">vat 編號</span><span class="sxs-lookup"><span data-stu-id="c1496-452">vat number</span></span>
  
<span data-ttu-id="c1496-453">無法稅授權單位</span><span class="sxs-lookup"><span data-stu-id="c1496-453">tax authority no</span></span>
  
<span data-ttu-id="c1496-454">稅識別碼稅身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-454">tax id tax identity number</span></span>
  
<span data-ttu-id="c1496-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="c1496-455">taxidnumber#</span></span>
  
<span data-ttu-id="c1496-456">錫 #</span><span class="sxs-lookup"><span data-stu-id="c1496-456">tin#</span></span>
  
<span data-ttu-id="c1496-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="c1496-457">hungatiantin#</span></span>
  
<span data-ttu-id="c1496-458">無法稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-458">tax identification no</span></span>
  
<span data-ttu-id="c1496-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="c1496-459">taxidno#</span></span>
  
<span data-ttu-id="c1496-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="c1496-460">adóazonosító szám</span></span>
  
<span data-ttu-id="c1496-461">adószám</span><span class="sxs-lookup"><span data-stu-id="c1496-461">adószám</span></span>
  
<span data-ttu-id="c1496-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="c1496-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="c1496-463">Ireland</span><span class="sxs-lookup"><span data-stu-id="c1496-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="c1496-464">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-464">Format</span></span>

<span data-ttu-id="c1496-465">後面接著任何空格或分隔符號信件的七位數字</span><span class="sxs-lookup"><span data-stu-id="c1496-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-466">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-466">Pattern</span></span>

<span data-ttu-id="c1496-467">後面接著一個字母的七位數字：</span><span class="sxs-lookup"><span data-stu-id="c1496-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="c1496-468">七位數</span><span class="sxs-lookup"><span data-stu-id="c1496-468">Seven digits</span></span> 
    
- <span data-ttu-id="c1496-469">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c1496-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-470">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-470">Checksum</span></span>

<span data-ttu-id="c1496-471">不適用</span><span class="sxs-lookup"><span data-stu-id="c1496-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-472">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-472">Definition</span></span>

<span data-ttu-id="c1496-473">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-474">此函數`Func_ireland_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-475">從關鍵字`Keywords_ireland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-476">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-477">此函數`Func_ireland_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="c1496-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-480">公共服務沒有</span><span class="sxs-lookup"><span data-stu-id="c1496-480">public service no</span></span>
  
<span data-ttu-id="c1496-481">個人公用服務沒有</span><span class="sxs-lookup"><span data-stu-id="c1496-481">personal public service no</span></span>
  
<span data-ttu-id="c1496-482">pps 無</span><span class="sxs-lookup"><span data-stu-id="c1496-482">pps no</span></span>
  
<span data-ttu-id="c1496-483">個人服務否</span><span class="sxs-lookup"><span data-stu-id="c1496-483">personal service no</span></span>
  
<span data-ttu-id="c1496-484">pps service 否</span><span class="sxs-lookup"><span data-stu-id="c1496-484">pps service no</span></span>
  
<span data-ttu-id="c1496-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="c1496-485">ppsno#</span></span>
  
<span data-ttu-id="c1496-486">愛爾蘭 pps 無</span><span class="sxs-lookup"><span data-stu-id="c1496-486">irish pps no</span></span>
  
<span data-ttu-id="c1496-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="c1496-487">publicserviceno#</span></span>
  
<span data-ttu-id="c1496-488">個人公用健保號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-488">personal public service number</span></span>
  
<span data-ttu-id="c1496-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="c1496-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="c1496-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="c1496-490">pps uimh</span></span>
  
<span data-ttu-id="c1496-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="c1496-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="c1496-492">義大利</span><span class="sxs-lookup"><span data-stu-id="c1496-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="c1496-493">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-493">Format</span></span>

<span data-ttu-id="c1496-494">16 信件與指定的型態的數字</span><span class="sxs-lookup"><span data-stu-id="c1496-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-495">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-495">Pattern</span></span>

<span data-ttu-id="c1496-496">16 字母和數字：</span><span class="sxs-lookup"><span data-stu-id="c1496-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="c1496-497">會對應至系列名稱中前三個母音的三個字母</span><span class="sxs-lookup"><span data-stu-id="c1496-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="c1496-498">會對應至第一個、 第三和第四的三個字母母音中第一個名稱</span><span class="sxs-lookup"><span data-stu-id="c1496-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="c1496-499">會對應至最後一出生年的數字的兩位數</span><span class="sxs-lookup"><span data-stu-id="c1496-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="c1496-500">一個數字對應至出生月 — 字母依字母順序使用，但僅限字母 A 到 E、 H、 L、 M、 P、 R 以 T 可用 （即得出年 1 月是 A 及年 10 月為 R）</span><span class="sxs-lookup"><span data-stu-id="c1496-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="c1496-501">會對應至出生 40 其中加入來區分與男生女生成績的出生的一天的每月一天的兩位數</span><span class="sxs-lookup"><span data-stu-id="c1496-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="c1496-502">會對應至特定出生人員 municipality 區碼的四個字 — 外部的國家/地區使用全國家/地區碼</span><span class="sxs-lookup"><span data-stu-id="c1496-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="c1496-503">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="c1496-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-504">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-504">Checksum</span></span>

<span data-ttu-id="c1496-505">是</span><span class="sxs-lookup"><span data-stu-id="c1496-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-506">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-506">Definition</span></span>

<span data-ttu-id="c1496-507">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-508">此函數`Func_italy_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-509">從關鍵字`Keywords_italy_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-510">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-511">此函數`Func_italy_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-512">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="c1496-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-514">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-514">tax number</span></span>
  
<span data-ttu-id="c1496-515">稅否]。</span><span class="sxs-lookup"><span data-stu-id="c1496-515">tax no.</span></span>
  
<span data-ttu-id="c1496-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="c1496-516">taxno#</span></span>
  
<span data-ttu-id="c1496-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c1496-517">taxnumber#</span></span>
  
<span data-ttu-id="c1496-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c1496-518">taxnumber</span></span>
  
<span data-ttu-id="c1496-519">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-519">tax id</span></span>
  
<span data-ttu-id="c1496-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="c1496-520">taxid#</span></span>
  
<span data-ttu-id="c1496-521">會計程式碼</span><span class="sxs-lookup"><span data-stu-id="c1496-521">fiscal code</span></span>
  
<span data-ttu-id="c1496-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="c1496-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="c1496-523">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="c1496-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="c1496-524">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-524">Format</span></span>

<span data-ttu-id="c1496-525">任何空格或分隔符號 11 位數</span><span class="sxs-lookup"><span data-stu-id="c1496-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-526">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-526">Pattern</span></span>

<span data-ttu-id="c1496-527">在指定的型態 11 位數</span><span class="sxs-lookup"><span data-stu-id="c1496-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="c1496-528">會對應至出生 (DDMMYY) 的日期的六個數字</span><span class="sxs-lookup"><span data-stu-id="c1496-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="c1496-529">會對應至其中"0"會對應至 19 century、"1"會對應至 20 century 及"2"會對應至第 21 世紀出生的 century 的一個數字</span><span class="sxs-lookup"><span data-stu-id="c1496-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="c1496-530">四位數</span><span class="sxs-lookup"><span data-stu-id="c1496-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-531">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-531">Checksum</span></span>

<span data-ttu-id="c1496-532">是</span><span class="sxs-lookup"><span data-stu-id="c1496-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-533">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-533">Definition</span></span>

<span data-ttu-id="c1496-534">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-535">此函數`Func_latvia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-536">從關鍵字`Keywords_latvia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-537">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-538">此函數`Func_latvia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-539">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="c1496-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-541">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-541">tax number</span></span>
  
<span data-ttu-id="c1496-542">稅否]。</span><span class="sxs-lookup"><span data-stu-id="c1496-542">tax no.</span></span>
  
<span data-ttu-id="c1496-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="c1496-543">taxno#</span></span>
  
<span data-ttu-id="c1496-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c1496-544">taxnumber#</span></span>
  
<span data-ttu-id="c1496-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c1496-545">taxnumber</span></span>
  
<span data-ttu-id="c1496-546">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-546">tax id</span></span>
  
<span data-ttu-id="c1496-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="c1496-547">taxid#</span></span>
  
<span data-ttu-id="c1496-548">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-548">tax identification number</span></span>
  
<span data-ttu-id="c1496-549">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1496-549">tax identification no.</span></span>
  
<span data-ttu-id="c1496-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="c1496-550">nodokļa numurs</span></span>
  
<span data-ttu-id="c1496-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="c1496-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="c1496-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="c1496-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="c1496-553">立陶宛</span><span class="sxs-lookup"><span data-stu-id="c1496-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="c1496-554">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-554">Format</span></span>

<span data-ttu-id="c1496-555">不含空格或分隔符號 11 位數</span><span class="sxs-lookup"><span data-stu-id="c1496-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-556">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-556">Pattern</span></span>

<span data-ttu-id="c1496-557">11 位數</span><span class="sxs-lookup"><span data-stu-id="c1496-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c1496-558">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-558">Checksum</span></span>

<span data-ttu-id="c1496-559">不適用</span><span class="sxs-lookup"><span data-stu-id="c1496-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-560">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-560">Definition</span></span>

<span data-ttu-id="c1496-561">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-562">此函數`Func_lithuania_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-563">從關鍵字`Keywords_lithuania_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-564">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-565">此函數`Func_lithuania_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-566">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="c1496-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-568">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-568">tax number</span></span>
  
<span data-ttu-id="c1496-569">稅否]。</span><span class="sxs-lookup"><span data-stu-id="c1496-569">tax no.</span></span>
  
<span data-ttu-id="c1496-570">稅否 #</span><span class="sxs-lookup"><span data-stu-id="c1496-570">tax no#</span></span>
  
<span data-ttu-id="c1496-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c1496-571">taxnumber#</span></span>
  
<span data-ttu-id="c1496-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c1496-572">taxnumber</span></span>
  
<span data-ttu-id="c1496-573">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-573">tax id</span></span>
  
<span data-ttu-id="c1496-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="c1496-574">taxid#</span></span>
  
<span data-ttu-id="c1496-575">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-575">tax identification number</span></span>
  
<span data-ttu-id="c1496-576">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1496-576">tax identification no.</span></span>
  
<span data-ttu-id="c1496-577">mokesčių 識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-577">mokesčių id</span></span>
  
<span data-ttu-id="c1496-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="c1496-578">mokesčių numeris</span></span>
  
<span data-ttu-id="c1496-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="c1496-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="c1496-580">盧森堡</span><span class="sxs-lookup"><span data-stu-id="c1496-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="c1496-581">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-581">Format</span></span>

<span data-ttu-id="c1496-582">任何空格或分隔字元 13 數字</span><span class="sxs-lookup"><span data-stu-id="c1496-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-583">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-583">Pattern</span></span>

<span data-ttu-id="c1496-584">13 位數：</span><span class="sxs-lookup"><span data-stu-id="c1496-584">13 digits:</span></span>
  
-  <span data-ttu-id="c1496-585">11 位數</span><span class="sxs-lookup"><span data-stu-id="c1496-585">11 digits</span></span> 
    
- <span data-ttu-id="c1496-586">二位數檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-587">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-587">Checksum</span></span>

<span data-ttu-id="c1496-588">是</span><span class="sxs-lookup"><span data-stu-id="c1496-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-589">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-589">Definition</span></span>

<span data-ttu-id="c1496-590">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-591">此函數`Func_luxemburg_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-592">從關鍵字`Keywords_luxemburg_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-593">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-594">此函數`Func_luxemburg_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-595">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="c1496-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-597">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-597">tax number</span></span>
  
<span data-ttu-id="c1496-598">稅否]。</span><span class="sxs-lookup"><span data-stu-id="c1496-598">tax no.</span></span>
  
<span data-ttu-id="c1496-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="c1496-599">taxno#</span></span>
  
<span data-ttu-id="c1496-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c1496-600">taxnumber#</span></span>
  
<span data-ttu-id="c1496-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c1496-601">taxnumber</span></span>
  
<span data-ttu-id="c1496-602">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-602">tax id</span></span>
  
<span data-ttu-id="c1496-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="c1496-603">taxid#</span></span>
  
<span data-ttu-id="c1496-604">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-604">tax identification number</span></span>
  
<span data-ttu-id="c1496-605">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1496-605">tax identification no.</span></span>
  
<span data-ttu-id="c1496-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="c1496-606">steuernummer</span></span>
  
<span data-ttu-id="c1496-607">steuer 識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-607">steuer id</span></span>
  
<span data-ttu-id="c1496-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="c1496-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="c1496-609">馬爾他</span><span class="sxs-lookup"><span data-stu-id="c1496-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="c1496-610">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-610">Format</span></span>

<span data-ttu-id="c1496-611">馬爾他 nationals 的： 7 位數和指定的型態的其中一個字母</span><span class="sxs-lookup"><span data-stu-id="c1496-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="c1496-612">非馬爾他文 nationals 和馬爾他實體： 9 的數字</span><span class="sxs-lookup"><span data-stu-id="c1496-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-613">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-613">Pattern</span></span>

<span data-ttu-id="c1496-614">馬爾他 nationals: 7 位數和一個字母</span><span class="sxs-lookup"><span data-stu-id="c1496-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="c1496-615">七位數</span><span class="sxs-lookup"><span data-stu-id="c1496-615">Seven digits</span></span> 
    
- <span data-ttu-id="c1496-616">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c1496-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="c1496-617">非馬爾他文 nationals 和馬爾他實體： 9 的數字</span><span class="sxs-lookup"><span data-stu-id="c1496-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="c1496-618">九位數</span><span class="sxs-lookup"><span data-stu-id="c1496-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c1496-619">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-619">Checksum</span></span>

<span data-ttu-id="c1496-620">不適用</span><span class="sxs-lookup"><span data-stu-id="c1496-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-621">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-621">Definition</span></span>

<span data-ttu-id="c1496-622">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-623">此函數`Func_malta_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-624">從關鍵字`Keywords_malta_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-625">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="c1496-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-626">此函數`Func_malta_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-627">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="c1496-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-629">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-629">tax number</span></span>
  
<span data-ttu-id="c1496-630">稅否]。</span><span class="sxs-lookup"><span data-stu-id="c1496-630">tax no.</span></span>
  
<span data-ttu-id="c1496-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="c1496-631">taxno#</span></span>
  
<span data-ttu-id="c1496-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c1496-632">taxnumber#</span></span>
  
<span data-ttu-id="c1496-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c1496-633">taxnumber</span></span>
  
<span data-ttu-id="c1496-634">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-634">tax id</span></span>
  
<span data-ttu-id="c1496-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="c1496-635">taxid#</span></span>
  
<span data-ttu-id="c1496-636">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-636">tax identification number</span></span>
  
<span data-ttu-id="c1496-637">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1496-637">tax identification no.</span></span>
  
<span data-ttu-id="c1496-638">numru 且 taxxa</span><span class="sxs-lookup"><span data-stu-id="c1496-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="c1496-639">識別碼且 taxxa</span><span class="sxs-lookup"><span data-stu-id="c1496-639">id tat-taxxa</span></span>
  
<span data-ttu-id="c1496-640">numru 東西 ' identifikazzjoni 且 taxxa</span><span class="sxs-lookup"><span data-stu-id="c1496-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="c1496-641">荷蘭</span><span class="sxs-lookup"><span data-stu-id="c1496-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="c1496-642">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-642">Format</span></span>

<span data-ttu-id="c1496-643">不含空格或分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="c1496-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-644">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-644">Pattern</span></span>

<span data-ttu-id="c1496-645">九位數</span><span class="sxs-lookup"><span data-stu-id="c1496-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c1496-646">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-646">Checksum</span></span>

<span data-ttu-id="c1496-647">是</span><span class="sxs-lookup"><span data-stu-id="c1496-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-648">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-648">Definition</span></span>

<span data-ttu-id="c1496-649">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-650">此函數`Func_netherlands_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-651">從關鍵字`Keywords_netherlands_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-652">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-653">此函數`Func_netherlands_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-654">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="c1496-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-656">荷蘭稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="c1496-657">荷蘭稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-657">netherlands tax identification</span></span>
  
<span data-ttu-id="c1496-658">荷屬安的稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="c1496-659">荷屬安的稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-659">netherland's tax identification</span></span>
  
<span data-ttu-id="c1496-660">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-660">tax identification number</span></span>
  
<span data-ttu-id="c1496-661">荷蘭文稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-661">dutch tax id</span></span>
  
<span data-ttu-id="c1496-662">荷蘭文稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-662">dutch tax identification number</span></span>
  
<span data-ttu-id="c1496-663">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-663">tax id</span></span>
  
<span data-ttu-id="c1496-664">稅識別碼 #</span><span class="sxs-lookup"><span data-stu-id="c1496-664">tax id#</span></span>
  
<span data-ttu-id="c1496-665">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-665">tax number</span></span>
  
<span data-ttu-id="c1496-666">稅否 #</span><span class="sxs-lookup"><span data-stu-id="c1496-666">tax no#</span></span>
  
<span data-ttu-id="c1496-667">稅 #</span><span class="sxs-lookup"><span data-stu-id="c1496-667">tax#</span></span>
  
<span data-ttu-id="c1496-668">tin
</span><span class="sxs-lookup"><span data-stu-id="c1496-668">tin</span></span>
  
<span data-ttu-id="c1496-669">錫 #</span><span class="sxs-lookup"><span data-stu-id="c1496-669">tin#</span></span>
  
<span data-ttu-id="c1496-670">荷蘭錫</span><span class="sxs-lookup"><span data-stu-id="c1496-670">netherlands tin</span></span>
  
<span data-ttu-id="c1496-671">荷屬安的錫</span><span class="sxs-lookup"><span data-stu-id="c1496-671">netherland's tin</span></span>
  
<span data-ttu-id="c1496-672">荷蘭 belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="c1496-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="c1496-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="c1496-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="c1496-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="c1496-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="c1496-675">荷蘭 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="c1496-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="c1496-676">荷蘭 belasting 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="c1496-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="c1496-677">荷蘭 belastingnummer</span><span class="sxs-lookup"><span data-stu-id="c1496-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="c1496-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="c1496-678">btw nummer</span></span>
  
<span data-ttu-id="c1496-679">文拚字檢查 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="c1496-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="c1496-680">波蘭</span><span class="sxs-lookup"><span data-stu-id="c1496-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="c1496-681">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-681">Format</span></span>

<span data-ttu-id="c1496-682">任何空格或分隔符號十一份數字</span><span class="sxs-lookup"><span data-stu-id="c1496-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-683">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-683">Pattern</span></span>

<span data-ttu-id="c1496-684">另外的數字</span><span class="sxs-lookup"><span data-stu-id="c1496-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c1496-685">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-685">Checksum</span></span>

<span data-ttu-id="c1496-686">是</span><span class="sxs-lookup"><span data-stu-id="c1496-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-687">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-687">Definition</span></span>

<span data-ttu-id="c1496-688">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-689">此函數`Func_poland_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-690">從關鍵字`Keywords_poland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-691">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-692">此函數`Func_poland_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-693">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="c1496-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-695">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-695">tax number</span></span>
  
<span data-ttu-id="c1496-696">稅否]。</span><span class="sxs-lookup"><span data-stu-id="c1496-696">tax no.</span></span>
  
<span data-ttu-id="c1496-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="c1496-697">taxno#</span></span>
  
<span data-ttu-id="c1496-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c1496-698">taxnumber#</span></span>
  
<span data-ttu-id="c1496-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c1496-699">taxnumber</span></span>
  
<span data-ttu-id="c1496-700">nip</span><span class="sxs-lookup"><span data-stu-id="c1496-700">nip</span></span>
  
<span data-ttu-id="c1496-701">nip #</span><span class="sxs-lookup"><span data-stu-id="c1496-701">nip#</span></span>
  
<span data-ttu-id="c1496-702">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-702">tax id</span></span>
  
<span data-ttu-id="c1496-703">稅識別碼 #</span><span class="sxs-lookup"><span data-stu-id="c1496-703">tax id#</span></span>
  
<span data-ttu-id="c1496-704">nip 識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-704">nip id</span></span>
  
<span data-ttu-id="c1496-705">nip 識別碼 #</span><span class="sxs-lookup"><span data-stu-id="c1496-705">nip id#</span></span>
  
<span data-ttu-id="c1496-706">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-706">tax identification number</span></span>
  
<span data-ttu-id="c1496-707">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1496-707">tax identification no.</span></span>
  
<span data-ttu-id="c1496-708">vat 編號</span><span class="sxs-lookup"><span data-stu-id="c1496-708">vat number</span></span>
  
<span data-ttu-id="c1496-709">vat 否]。</span><span class="sxs-lookup"><span data-stu-id="c1496-709">vat no.</span></span>
  
<span data-ttu-id="c1496-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="c1496-710">vatno#</span></span>
  
<span data-ttu-id="c1496-711">增值稅識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-711">vat id</span></span>
  
<span data-ttu-id="c1496-712">增值稅識別碼 #</span><span class="sxs-lookup"><span data-stu-id="c1496-712">vat id#</span></span>
  
<span data-ttu-id="c1496-713">數目 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="c1496-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="c1496-714">polski 數目 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="c1496-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="c1496-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="c1496-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="c1496-716">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="c1496-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="c1496-717">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-717">Format</span></span>

<span data-ttu-id="c1496-718">任何空格或分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="c1496-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-719">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-719">Pattern</span></span>

<span data-ttu-id="c1496-720">九位數</span><span class="sxs-lookup"><span data-stu-id="c1496-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c1496-721">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-721">Checksum</span></span>

<span data-ttu-id="c1496-722">是</span><span class="sxs-lookup"><span data-stu-id="c1496-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-723">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-723">Definition</span></span>

<span data-ttu-id="c1496-724">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-725">此函數`Func_portugal_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-726">從關鍵字`Keywords_portugal_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-727">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-728">此函數`Func_portugal_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-729">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="c1496-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-731">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-731">tax number</span></span>
  
<span data-ttu-id="c1496-732">稅否]。</span><span class="sxs-lookup"><span data-stu-id="c1496-732">tax no.</span></span>
  
<span data-ttu-id="c1496-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="c1496-733">taxno#</span></span>
  
<span data-ttu-id="c1496-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="c1496-734">taxnumber#</span></span>
  
<span data-ttu-id="c1496-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c1496-735">taxnumber</span></span>
  
<span data-ttu-id="c1496-736">n 如果</span><span class="sxs-lookup"><span data-stu-id="c1496-736">nif</span></span>
  
<span data-ttu-id="c1496-737">n 如果 #</span><span class="sxs-lookup"><span data-stu-id="c1496-737">nif#</span></span>
  
<span data-ttu-id="c1496-738">numero 會計</span><span class="sxs-lookup"><span data-stu-id="c1496-738">numero fiscal</span></span>
  
<span data-ttu-id="c1496-739">número de identificação 會計</span><span class="sxs-lookup"><span data-stu-id="c1496-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="c1496-740">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="c1496-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="c1496-741">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-741">Format</span></span>

<span data-ttu-id="c1496-742">任何空格或分隔字元 13 數字</span><span class="sxs-lookup"><span data-stu-id="c1496-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-743">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-743">Pattern</span></span>

<span data-ttu-id="c1496-744">13 位數</span><span class="sxs-lookup"><span data-stu-id="c1496-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c1496-745">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-745">Checksum</span></span>

<span data-ttu-id="c1496-746">不適用</span><span class="sxs-lookup"><span data-stu-id="c1496-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-747">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-747">Definition</span></span>

<span data-ttu-id="c1496-748">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-749">規則運算式`Regex_romania_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-750">從關鍵字`Keywords_romania_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-751">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="c1496-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-753">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-753">tax id</span></span>
  
<span data-ttu-id="c1496-754">稅 id 號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-754">tax id number</span></span>
  
<span data-ttu-id="c1496-755">無法稅檔案</span><span class="sxs-lookup"><span data-stu-id="c1496-755">tax file no</span></span>
  
<span data-ttu-id="c1496-756">

tax file number</span><span class="sxs-lookup"><span data-stu-id="c1496-756">tax file number</span></span>
  
<span data-ttu-id="c1496-757">稅否</span><span class="sxs-lookup"><span data-stu-id="c1496-757">tax no</span></span>
  
<span data-ttu-id="c1496-758">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-758">tax number</span></span>
  
<span data-ttu-id="c1496-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="c1496-759">taxid#</span></span>
  
<span data-ttu-id="c1496-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="c1496-760">taxno#</span></span>
  
<span data-ttu-id="c1496-761">識別碼 ul taxei</span><span class="sxs-lookup"><span data-stu-id="c1496-761">id-ul taxei</span></span>
  
<span data-ttu-id="c1496-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="c1496-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="c1496-763">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="c1496-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="c1496-764">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-764">Format</span></span>

<span data-ttu-id="c1496-765">任何空格或分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="c1496-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-766">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-766">Pattern</span></span>

<span data-ttu-id="c1496-767">10 位數</span><span class="sxs-lookup"><span data-stu-id="c1496-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c1496-768">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-768">Checksum</span></span>

<span data-ttu-id="c1496-769">不適用</span><span class="sxs-lookup"><span data-stu-id="c1496-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-770">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-770">Definition</span></span>

<span data-ttu-id="c1496-771">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-772">規則運算式`Regex_slovakia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-773">從關鍵字`Keywords_slovakia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-774">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="c1496-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-776">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-776">tax id</span></span>
  
<span data-ttu-id="c1496-777">稅 id 號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-777">tax id number</span></span>
  
<span data-ttu-id="c1496-778">鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-778">tin id</span></span>
  
<span data-ttu-id="c1496-779">鐵皮否</span><span class="sxs-lookup"><span data-stu-id="c1496-779">tin no</span></span>
  
<span data-ttu-id="c1496-780">斯洛伐克鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-780">slovakian tin id</span></span>
  
<span data-ttu-id="c1496-781">tin
</span><span class="sxs-lookup"><span data-stu-id="c1496-781">tin</span></span>
  
<span data-ttu-id="c1496-782">無法稅檔案</span><span class="sxs-lookup"><span data-stu-id="c1496-782">tax file no</span></span>
  
<span data-ttu-id="c1496-783">

tax file number</span><span class="sxs-lookup"><span data-stu-id="c1496-783">tax file number</span></span>
  
<span data-ttu-id="c1496-784">稅否</span><span class="sxs-lookup"><span data-stu-id="c1496-784">tax no</span></span>
  
<span data-ttu-id="c1496-785">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-785">tax number</span></span>
  
<span data-ttu-id="c1496-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="c1496-786">taxid#</span></span>
  
<span data-ttu-id="c1496-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="c1496-787">taxno#</span></span>
  
<span data-ttu-id="c1496-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="c1496-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="c1496-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="c1496-789">daňové číslo</span></span>
  
<span data-ttu-id="c1496-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="c1496-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="c1496-791">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="c1496-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="c1496-792">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-792">Format</span></span>

<span data-ttu-id="c1496-793">任何空格或分隔字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="c1496-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-794">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-794">Pattern</span></span>

<span data-ttu-id="c1496-795">八位數</span><span class="sxs-lookup"><span data-stu-id="c1496-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c1496-796">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-796">Checksum</span></span>

<span data-ttu-id="c1496-797">是</span><span class="sxs-lookup"><span data-stu-id="c1496-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-798">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-798">Definition</span></span>

<span data-ttu-id="c1496-799">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-800">此函數`Func_slovenia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-801">從關鍵字`Keywords_slovenia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-802">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-803">此函數`Func_slovenia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-804">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="c1496-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-806">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-806">tax id</span></span>
  
<span data-ttu-id="c1496-807">稅 id 號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-807">tax id number</span></span>
  
<span data-ttu-id="c1496-808">鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-808">tin id</span></span>
  
<span data-ttu-id="c1496-809">鐵皮否</span><span class="sxs-lookup"><span data-stu-id="c1496-809">tin no</span></span>
  
<span data-ttu-id="c1496-810">斯洛維尼亞文鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-810">slovenian tin id</span></span>
  
<span data-ttu-id="c1496-811">tin
</span><span class="sxs-lookup"><span data-stu-id="c1496-811">tin</span></span>
  
<span data-ttu-id="c1496-812">無法稅檔案</span><span class="sxs-lookup"><span data-stu-id="c1496-812">tax file no</span></span>
  
<span data-ttu-id="c1496-813">

tax file number</span><span class="sxs-lookup"><span data-stu-id="c1496-813">tax file number</span></span>
  
<span data-ttu-id="c1496-814">稅否</span><span class="sxs-lookup"><span data-stu-id="c1496-814">tax no</span></span>
  
<span data-ttu-id="c1496-815">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-815">tax number</span></span>
  
<span data-ttu-id="c1496-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="c1496-816">taxid#</span></span>
  
<span data-ttu-id="c1496-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="c1496-817">taxno#</span></span>
  
<span data-ttu-id="c1496-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="c1496-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="c1496-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="c1496-819">davčna številka</span></span>
  
<span data-ttu-id="c1496-820">Številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="c1496-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="c1496-821">西班牙</span><span class="sxs-lookup"><span data-stu-id="c1496-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="c1496-822">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-822">Format</span></span>

<span data-ttu-id="c1496-823">七個或八個位數和中指定的型態的一或兩個字母</span><span class="sxs-lookup"><span data-stu-id="c1496-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-824">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-824">Pattern</span></span>

<span data-ttu-id="c1496-825">西班牙文自然資料提供者與西班牙國民身分識別卡：</span><span class="sxs-lookup"><span data-stu-id="c1496-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="c1496-826">八位數</span><span class="sxs-lookup"><span data-stu-id="c1496-826">Eight digits</span></span> 
    
- <span data-ttu-id="c1496-827">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c1496-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="c1496-828">西班牙國民身分識別卡而非駐留西班牙人</span><span class="sxs-lookup"><span data-stu-id="c1496-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="c1496-829">一個大寫字母"L"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c1496-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="c1496-830">七位數</span><span class="sxs-lookup"><span data-stu-id="c1496-830">Seven digits</span></span>
    
- <span data-ttu-id="c1496-831">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c1496-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="c1496-832">底下的年齡 14 年不含西班牙國民身分識別卡駐留西班牙人：</span><span class="sxs-lookup"><span data-stu-id="c1496-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="c1496-833">一個大寫字母"K"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c1496-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="c1496-834">七位數</span><span class="sxs-lookup"><span data-stu-id="c1496-834">Seven digits</span></span> 
    
- <span data-ttu-id="c1496-835">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c1496-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="c1496-836">外國人與因此識別號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="c1496-837">一個大寫也就是字母"X"、"Y"或"Z"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c1496-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="c1496-838">七位數</span><span class="sxs-lookup"><span data-stu-id="c1496-838">Seven digits</span></span>
    
- <span data-ttu-id="c1496-839">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c1496-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="c1496-840">外國人沒有因此識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="c1496-841">一個大寫字母的"M"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c1496-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="c1496-842">七位數</span><span class="sxs-lookup"><span data-stu-id="c1496-842">Seven digits</span></span>
    
- <span data-ttu-id="c1496-843">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="c1496-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c1496-844">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-844">Checksum</span></span>

<span data-ttu-id="c1496-845">是</span><span class="sxs-lookup"><span data-stu-id="c1496-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-846">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-846">Definition</span></span>

<span data-ttu-id="c1496-847">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-848">此函數`Func_spain_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-849">從關鍵字`Keywords_spain_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-850">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-851">此函數`Func_spain_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-852">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="c1496-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-854">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-854">tax id</span></span>
  
<span data-ttu-id="c1496-855">稅 id 號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-855">tax id number</span></span>
  
<span data-ttu-id="c1496-856">cif 識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-856">cif id</span></span>
  
<span data-ttu-id="c1496-857">cif 沒有</span><span class="sxs-lookup"><span data-stu-id="c1496-857">cif no</span></span>
  
<span data-ttu-id="c1496-858">西班牙文 cif 識別碼</span><span class="sxs-lookup"><span data-stu-id="c1496-858">spanish cif id</span></span>
  
<span data-ttu-id="c1496-859">cif</span><span class="sxs-lookup"><span data-stu-id="c1496-859">cif</span></span>
  
<span data-ttu-id="c1496-860">無法稅檔案</span><span class="sxs-lookup"><span data-stu-id="c1496-860">tax file no</span></span>
  
<span data-ttu-id="c1496-861">西班牙文 cif 數目</span><span class="sxs-lookup"><span data-stu-id="c1496-861">spanish cif number</span></span>
  
<span data-ttu-id="c1496-862">

tax file number</span><span class="sxs-lookup"><span data-stu-id="c1496-862">tax file number</span></span>
  
<span data-ttu-id="c1496-863">西班牙文 cif 沒有</span><span class="sxs-lookup"><span data-stu-id="c1496-863">spanish cif no</span></span>
  
<span data-ttu-id="c1496-864">稅否</span><span class="sxs-lookup"><span data-stu-id="c1496-864">tax no</span></span>
  
<span data-ttu-id="c1496-865">稅編號</span><span class="sxs-lookup"><span data-stu-id="c1496-865">tax number</span></span>
  
<span data-ttu-id="c1496-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="c1496-866">taxid#</span></span>
  
<span data-ttu-id="c1496-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="c1496-867">taxno#</span></span>
  
<span data-ttu-id="c1496-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="c1496-868">cifid#</span></span>
  
<span data-ttu-id="c1496-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="c1496-869">spanishcifid#</span></span>
  
<span data-ttu-id="c1496-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="c1496-870">spanishcifno#</span></span>
  
<span data-ttu-id="c1496-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="c1496-871">número de contribuyente</span></span>
  
<span data-ttu-id="c1496-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="c1496-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="c1496-873">número de identificación 會計</span><span class="sxs-lookup"><span data-stu-id="c1496-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="c1496-874">cif número</span><span class="sxs-lookup"><span data-stu-id="c1496-874">cif número</span></span>
  
<span data-ttu-id="c1496-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="c1496-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="c1496-876">瑞典</span><span class="sxs-lookup"><span data-stu-id="c1496-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="c1496-877">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-877">Format</span></span>

<span data-ttu-id="c1496-878">十位數和中指定的型態的符號</span><span class="sxs-lookup"><span data-stu-id="c1496-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-879">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-879">Pattern</span></span>

<span data-ttu-id="c1496-880">十位數和符號：</span><span class="sxs-lookup"><span data-stu-id="c1496-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="c1496-881">會對應至出生日期 (YYMMDD) 的六個數字</span><span class="sxs-lookup"><span data-stu-id="c1496-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="c1496-882">加號、 減號、 或反斜線</span><span class="sxs-lookup"><span data-stu-id="c1496-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="c1496-883">進行識別的三個位數字唯一的位置：</span><span class="sxs-lookup"><span data-stu-id="c1496-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="c1496-884">對於 1990年之前發行的數字、 第七個和第八個位數識別出生或 foreign-born 人員郡</span><span class="sxs-lookup"><span data-stu-id="c1496-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="c1496-885">第九個位置中的數字表示任一奇數女性 2 男或甚至是依性別</span><span class="sxs-lookup"><span data-stu-id="c1496-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="c1496-886">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="c1496-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c1496-887">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-887">Checksum</span></span>

<span data-ttu-id="c1496-888">是</span><span class="sxs-lookup"><span data-stu-id="c1496-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-889">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-889">Definition</span></span>

<span data-ttu-id="c1496-890">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="c1496-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-891">此函數`Func_sweden_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-892">從關鍵字`Keywords_sweden_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c1496-893">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-894">此函數`Func_sweden_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-895">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="c1496-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-897">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-897">tax id</span></span>
  
<span data-ttu-id="c1496-898">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1496-898">tax id no.</span></span>
  
<span data-ttu-id="c1496-899">稅 id 號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-899">tax id number</span></span>
  
<span data-ttu-id="c1496-900">tax identification
</span><span class="sxs-lookup"><span data-stu-id="c1496-900">tax identification</span></span>
  
<span data-ttu-id="c1496-901">稅識別 #</span><span class="sxs-lookup"><span data-stu-id="c1496-901">tax identification#</span></span>
  
<span data-ttu-id="c1496-902">稅否]。</span><span class="sxs-lookup"><span data-stu-id="c1496-902">tax no.</span></span>
  
<span data-ttu-id="c1496-903">稅 #</span><span class="sxs-lookup"><span data-stu-id="c1496-903">tax#</span></span>
  
<span data-ttu-id="c1496-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="c1496-904">taxid#</span></span>
  
<span data-ttu-id="c1496-905">稅檔案</span><span class="sxs-lookup"><span data-stu-id="c1496-905">tax file</span></span>
  
<span data-ttu-id="c1496-906">無法稅檔案。</span><span class="sxs-lookup"><span data-stu-id="c1496-906">tax file no.</span></span>
  
<span data-ttu-id="c1496-907">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-907">personal id number</span></span>
  
<span data-ttu-id="c1496-908">skatt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="c1496-908">skatt id nummer</span></span>
  
<span data-ttu-id="c1496-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="c1496-909">skatt identifikation</span></span>
  
<span data-ttu-id="c1496-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="c1496-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="c1496-911">英國</span><span class="sxs-lookup"><span data-stu-id="c1496-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="c1496-912">格式</span><span class="sxs-lookup"><span data-stu-id="c1496-912">Format</span></span>

<span data-ttu-id="c1496-913">唯一 Taxpayer 參照 (UTR)： 10 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="c1496-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="c1496-p103">國家保險號碼 (NINO)： 如需詳細資訊，請參閱區段"英國 National 保險數 (NINO)"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="c1496-p103">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c1496-916">模式</span><span class="sxs-lookup"><span data-stu-id="c1496-916">Pattern</span></span>

<span data-ttu-id="c1496-917">唯一 Taxpayer 參照 (UTR)： 10 位數</span><span class="sxs-lookup"><span data-stu-id="c1496-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="c1496-p104">國家保險號碼 (NINO)： 如需詳細資訊，請參閱區段"英國 National 保險數 (NINO)"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="c1496-p104">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c1496-920">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="c1496-920">Checksum</span></span>

<span data-ttu-id="c1496-921">是</span><span class="sxs-lookup"><span data-stu-id="c1496-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c1496-922">定義</span><span class="sxs-lookup"><span data-stu-id="c1496-922">Definition</span></span>

<span data-ttu-id="c1496-923">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="c1496-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c1496-924">此函數`Func_uk_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="c1496-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c1496-925">從關鍵字`Keywords_uk_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="c1496-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c1496-926">關鍵字</span><span class="sxs-lookup"><span data-stu-id="c1496-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="c1496-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c1496-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="c1496-928">tax id
</span><span class="sxs-lookup"><span data-stu-id="c1496-928">tax id</span></span>
  
<span data-ttu-id="c1496-929">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1496-929">tax id no.</span></span>
  
<span data-ttu-id="c1496-930">稅 id 號碼</span><span class="sxs-lookup"><span data-stu-id="c1496-930">tax id number</span></span>
  
<span data-ttu-id="c1496-931">tax identification
</span><span class="sxs-lookup"><span data-stu-id="c1496-931">tax identification</span></span>
  
<span data-ttu-id="c1496-932">稅識別 #</span><span class="sxs-lookup"><span data-stu-id="c1496-932">tax identification#</span></span>
  
<span data-ttu-id="c1496-933">稅否]。</span><span class="sxs-lookup"><span data-stu-id="c1496-933">tax no.</span></span>
  
<span data-ttu-id="c1496-934">稅 #</span><span class="sxs-lookup"><span data-stu-id="c1496-934">tax#</span></span>
  
<span data-ttu-id="c1496-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="c1496-935">taxid#</span></span>
  
<span data-ttu-id="c1496-936">稅檔案</span><span class="sxs-lookup"><span data-stu-id="c1496-936">tax file</span></span>
  
<span data-ttu-id="c1496-937">無法稅檔案。</span><span class="sxs-lookup"><span data-stu-id="c1496-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c1496-938">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c1496-938">See also</span></span>

[<span data-ttu-id="c1496-939">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="c1496-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

