---
title: 歐盟稅識別碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: 本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟稅識別碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
ms.openlocfilehash: f851cce4be70fd41c24a7876d97c452f0a738eda
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213823"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="b65f0-104">歐盟稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-104">EU Tax Identification Number</span></span>

<span data-ttu-id="b65f0-p102">本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟稅識別號碼 （錫） 敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。</span><span class="sxs-lookup"><span data-stu-id="b65f0-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="b65f0-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="b65f0-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-108">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-108">Format</span></span>

<span data-ttu-id="b65f0-109">選擇性連字號和正斜線的九個位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-110">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-110">Pattern</span></span>

<span data-ttu-id="b65f0-111">選擇性連字號和正斜線的九個位數：</span><span class="sxs-lookup"><span data-stu-id="b65f0-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="b65f0-112">兩位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-112">Two digits</span></span> 
    
- <span data-ttu-id="b65f0-113">一個連字號 (選用)</span><span class="sxs-lookup"><span data-stu-id="b65f0-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="b65f0-114">三位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-114">Three digits</span></span>
    
- <span data-ttu-id="b65f0-115">一個正斜線 (選用)</span><span class="sxs-lookup"><span data-stu-id="b65f0-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="b65f0-116">四位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-117">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-117">Checksum</span></span>

<span data-ttu-id="b65f0-118">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-119">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-119">Definition</span></span>

<span data-ttu-id="b65f0-120">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-121">此函數`Func_austria_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-122">從關鍵字`Keywords_austria_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-123">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-124">此函數`Func_austria_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-125">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="b65f0-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-127">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-127">tax number</span></span>
  
<span data-ttu-id="b65f0-128">數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-128">number</span></span>
  
<span data-ttu-id="b65f0-129">稅註冊編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-129">tax registration number</span></span>
  
<span data-ttu-id="b65f0-130">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-130">tax id</span></span>
  
<span data-ttu-id="b65f0-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="b65f0-131">st.nr.</span></span>
  
<span data-ttu-id="b65f0-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="b65f0-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="b65f0-133">比利時</span><span class="sxs-lookup"><span data-stu-id="b65f0-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-134">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-134">Format</span></span>

<span data-ttu-id="b65f0-135">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="b65f0-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-136">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-136">Pattern</span></span>

<span data-ttu-id="b65f0-137">11 位數：</span><span class="sxs-lookup"><span data-stu-id="b65f0-137">11 digits:</span></span>
  
- <span data-ttu-id="b65f0-138">兩位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-138">Two digits</span></span>
    
- <span data-ttu-id="b65f0-139">"0"或者"1"</span><span class="sxs-lookup"><span data-stu-id="b65f0-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="b65f0-140">一個數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-140">One digit</span></span>
    
- <span data-ttu-id="b65f0-141">"0"或"1"或"2"或者"3"</span><span class="sxs-lookup"><span data-stu-id="b65f0-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="b65f0-142">六位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-143">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-143">Checksum</span></span>

<span data-ttu-id="b65f0-144">不適用</span><span class="sxs-lookup"><span data-stu-id="b65f0-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-145">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-145">Definition</span></span>

<span data-ttu-id="b65f0-146">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-147">規則運算式`Regex_belgium_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-148">從關鍵字`Keywords_belgium_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b65f0-149">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="b65f0-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-151">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-151">tax number</span></span>
  
<span data-ttu-id="b65f0-152">國際號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-152">national registration number</span></span>
  
<span data-ttu-id="b65f0-153">稅註冊編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-153">tax registration number</span></span>
  
<span data-ttu-id="b65f0-154">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-154">tax id</span></span>
  
<span data-ttu-id="b65f0-155">n 如果</span><span class="sxs-lookup"><span data-stu-id="b65f0-155">nif</span></span>
  
<span data-ttu-id="b65f0-156">n 如果 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-156">nif#</span></span>
  
<span data-ttu-id="b65f0-157">numéro de registre national</span><span class="sxs-lookup"><span data-stu-id="b65f0-157">numéro de registre national</span></span>
  
<span data-ttu-id="b65f0-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="b65f0-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="b65f0-159">保加利亞</span><span class="sxs-lookup"><span data-stu-id="b65f0-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-160">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-160">Format</span></span>

<span data-ttu-id="b65f0-161">十位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="b65f0-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-162">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-162">Pattern</span></span>

<span data-ttu-id="b65f0-163">10 位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b65f0-164">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-164">Checksum</span></span>

<span data-ttu-id="b65f0-165">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-166">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-166">Definition</span></span>

<span data-ttu-id="b65f0-167">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-168">此函數`Func_bulgaria_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-169">從關鍵字`Keywords_bulgaria_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-170">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-171">此函數`Func_bulgaria_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-172">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="b65f0-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-174">bucn</span><span class="sxs-lookup"><span data-stu-id="b65f0-174">bucn</span></span>
  
<span data-ttu-id="b65f0-175">統一民事數目</span><span class="sxs-lookup"><span data-stu-id="b65f0-175">uniform civil number</span></span>
  
<span data-ttu-id="b65f0-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="b65f0-176">bucn#</span></span>
  
<span data-ttu-id="b65f0-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="b65f0-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="b65f0-178">統一民事識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-178">uniform civil id</span></span>
  
<span data-ttu-id="b65f0-179">統一民事否</span><span class="sxs-lookup"><span data-stu-id="b65f0-179">uniform civil no</span></span>
  
<span data-ttu-id="b65f0-180">egn</span><span class="sxs-lookup"><span data-stu-id="b65f0-180">egn</span></span>
  
<span data-ttu-id="b65f0-181">保加利亞統一民事數目</span><span class="sxs-lookup"><span data-stu-id="b65f0-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="b65f0-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-182">uniformcivilno#</span></span>
  
<span data-ttu-id="b65f0-183">egn #</span><span class="sxs-lookup"><span data-stu-id="b65f0-183">egn#</span></span>
  
<span data-ttu-id="b65f0-184">УНИФОРМ ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="b65f0-184">униформ граждански номер</span></span>
  
<span data-ttu-id="b65f0-185">Униформ 識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-185">униформ id</span></span>
  
<span data-ttu-id="b65f0-186">Униформ граждански 識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-186">униформ граждански id</span></span>
  
<span data-ttu-id="b65f0-187">УНИФОРМ ГРАЖДАНСКИ НЕ</span><span class="sxs-lookup"><span data-stu-id="b65f0-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="b65f0-188">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="b65f0-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-189">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-189">Format</span></span>

<span data-ttu-id="b65f0-190">任何空格或分隔符號 11 位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-191">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-191">Pattern</span></span>

<span data-ttu-id="b65f0-192">11 位數：</span><span class="sxs-lookup"><span data-stu-id="b65f0-192">11 digits:</span></span>
  
- <span data-ttu-id="b65f0-193">十位數，隨機選擇</span><span class="sxs-lookup"><span data-stu-id="b65f0-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="b65f0-194">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-195">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-195">Checksum</span></span>

<span data-ttu-id="b65f0-196">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-197">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-197">Definition</span></span>

<span data-ttu-id="b65f0-198">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-199">此函數`Func_croatia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-200">從關鍵字`Keywords_croatia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-201">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-202">此函數`Func_croatia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-203">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="b65f0-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-205">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-205">tax number</span></span>
  
<span data-ttu-id="b65f0-206">稅</span><span class="sxs-lookup"><span data-stu-id="b65f0-206">tax</span></span>
  
<span data-ttu-id="b65f0-207">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-207">tax id</span></span>
  
<span data-ttu-id="b65f0-208">oid</span><span class="sxs-lookup"><span data-stu-id="b65f0-208">oid</span></span>
  
<span data-ttu-id="b65f0-209">oid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-209">oid#</span></span>
  
<span data-ttu-id="b65f0-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="b65f0-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="b65f0-211">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="b65f0-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-212">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-212">Format</span></span>

<span data-ttu-id="b65f0-213">八個位數和指定的型態的其中一個字母</span><span class="sxs-lookup"><span data-stu-id="b65f0-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-214">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-214">Pattern</span></span>

<span data-ttu-id="b65f0-215">八個位數和一個字母：</span><span class="sxs-lookup"><span data-stu-id="b65f0-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="b65f0-216">"0"</span><span class="sxs-lookup"><span data-stu-id="b65f0-216">A "0"</span></span> 
    
- <span data-ttu-id="b65f0-217">七位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-217">Seven digits</span></span>
    
- <span data-ttu-id="b65f0-218">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="b65f0-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-219">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-219">Checksum</span></span>

<span data-ttu-id="b65f0-220">不適用</span><span class="sxs-lookup"><span data-stu-id="b65f0-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-221">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-221">Definition</span></span>

<span data-ttu-id="b65f0-222">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-223">此函數`Func_cyprus_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-224">從關鍵字`Keywords_cyprus_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-225">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-226">此函數`Func_cyprus_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="b65f0-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-229">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-229">tax number</span></span>
  
<span data-ttu-id="b65f0-230">稅</span><span class="sxs-lookup"><span data-stu-id="b65f0-230">tax</span></span>
  
<span data-ttu-id="b65f0-231">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-231">tax id</span></span>
  
<span data-ttu-id="b65f0-232">稅識別程式碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-232">tax identification code</span></span>
  
<span data-ttu-id="b65f0-233">tic</span><span class="sxs-lookup"><span data-stu-id="b65f0-233">tic</span></span>
  
<span data-ttu-id="b65f0-234">tic #</span><span class="sxs-lookup"><span data-stu-id="b65f0-234">tic#</span></span>
  
<span data-ttu-id="b65f0-235">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="b65f0-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="b65f0-236">ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ</span><span class="sxs-lookup"><span data-stu-id="b65f0-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="b65f0-237">ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="b65f0-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="b65f0-238">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="b65f0-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-239">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-239">Format</span></span>

<span data-ttu-id="b65f0-240">使用選用的反斜線的九個或十位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-241">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-241">Pattern</span></span>

<span data-ttu-id="b65f0-242">具有選用 backslashl 9 或 10 位數：</span><span class="sxs-lookup"><span data-stu-id="b65f0-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="b65f0-243">六位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-243">Six digits</span></span> 
    
- <span data-ttu-id="b65f0-244">反斜線 （選用）</span><span class="sxs-lookup"><span data-stu-id="b65f0-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="b65f0-245">三個或四位數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-246">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-246">Checksum</span></span>

<span data-ttu-id="b65f0-247">不適用</span><span class="sxs-lookup"><span data-stu-id="b65f0-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-248">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-248">Definition</span></span>

<span data-ttu-id="b65f0-249">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-250">規則運算式`Regex_czech_republic_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-251">從關鍵字`Keywords_czech_republic_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b65f0-252">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="b65f0-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-254">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-254">tax number</span></span>
  
<span data-ttu-id="b65f0-255">稅</span><span class="sxs-lookup"><span data-stu-id="b65f0-255">tax</span></span>
  
<span data-ttu-id="b65f0-256">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-256">tax id</span></span>
  
<span data-ttu-id="b65f0-257">個人的數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-257">personal number</span></span>
  
<span data-ttu-id="b65f0-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="b65f0-258">daňové číslo</span></span>
  
<span data-ttu-id="b65f0-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="b65f0-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="b65f0-260">丹麥</span><span class="sxs-lookup"><span data-stu-id="b65f0-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-261">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-261">Format</span></span>

<span data-ttu-id="b65f0-262">十個包含連字號的數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-263">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-263">Pattern</span></span>

<span data-ttu-id="b65f0-264">包含 hyphenl 十位數：</span><span class="sxs-lookup"><span data-stu-id="b65f0-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="b65f0-265">會對應至出生日期 (DDMMYY) 的六個數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="b65f0-266">一個連字號</span><span class="sxs-lookup"><span data-stu-id="b65f0-266">A hyphen</span></span>
    
- <span data-ttu-id="b65f0-267">會對應至其中的第一個數字會對應至出生的 century 序號的四個字和最後一個數字會對應至個人的性別 （2 男和即使女性奇數）</span><span class="sxs-lookup"><span data-stu-id="b65f0-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-268">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-268">Checksum</span></span>

<span data-ttu-id="b65f0-269">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-270">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-270">Definition</span></span>

<span data-ttu-id="b65f0-271">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-272">此函數`Func_denmark_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-273">從關鍵字`Keywords_denmark_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-274">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-275">此函數`Func_denmark_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-276">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="b65f0-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-278">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-278">tax number</span></span>
  
<span data-ttu-id="b65f0-279">稅</span><span class="sxs-lookup"><span data-stu-id="b65f0-279">tax</span></span>
  
<span data-ttu-id="b65f0-280">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-280">tax id</span></span>
  
<span data-ttu-id="b65f0-281">cpr 數目</span><span class="sxs-lookup"><span data-stu-id="b65f0-281">cpr number</span></span>
  
<span data-ttu-id="b65f0-282">cpr #</span><span class="sxs-lookup"><span data-stu-id="b65f0-282">cpr#</span></span>
  
<span data-ttu-id="b65f0-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="b65f0-283">skat nummer</span></span>
  
<span data-ttu-id="b65f0-284">skat 識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="b65f0-285">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="b65f0-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-286">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-286">Format</span></span>

<span data-ttu-id="b65f0-287">任何空格或分隔符號 11 位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-288">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-288">Pattern</span></span>

<span data-ttu-id="b65f0-289">11 位數：</span><span class="sxs-lookup"><span data-stu-id="b65f0-289">11 digits:</span></span>
  
-  <span data-ttu-id="b65f0-290">會對應至性別和出生其中奇數指出 2 男和偶數指出女性，如下所示的 century 的一個數字： 1，2 19 的 century;3、 4 20 的 century;與 5、 6 第 21 世紀</span><span class="sxs-lookup"><span data-stu-id="b65f0-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="b65f0-291">會對應至出生日期 (YYMMDD) 的六個數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="b65f0-292">會對應至分隔出生日期相同的人員序號的三個位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="b65f0-293">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-294">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-294">Checksum</span></span>

<span data-ttu-id="b65f0-295">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-296">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-296">Definition</span></span>

<span data-ttu-id="b65f0-297">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-298">此函數`Func_estonia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-299">從關鍵字`Keywords_estonia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-300">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-301">此函數`Func_estonia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-302">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="b65f0-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-304">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-304">tax number</span></span>
  
<span data-ttu-id="b65f0-305">稅</span><span class="sxs-lookup"><span data-stu-id="b65f0-305">tax</span></span>
  
<span data-ttu-id="b65f0-306">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-306">tax id</span></span>
  
<span data-ttu-id="b65f0-307">個人的程式碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-307">personal code</span></span>
  
<span data-ttu-id="b65f0-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="b65f0-308">maksunumber</span></span>
  
<span data-ttu-id="b65f0-309">maksu 識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-309">maksu id</span></span>
  
<span data-ttu-id="b65f0-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="b65f0-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="b65f0-311">芬蘭</span><span class="sxs-lookup"><span data-stu-id="b65f0-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-312">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-312">Format</span></span>

<span data-ttu-id="b65f0-313">信件的數字，11 個字元組合，並加號與減號</span><span class="sxs-lookup"><span data-stu-id="b65f0-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-314">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-314">Pattern</span></span>

<span data-ttu-id="b65f0-315">信件的數字，11 個字元組合，並加號與減號：</span><span class="sxs-lookup"><span data-stu-id="b65f0-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="b65f0-316">六位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-316">Six digits</span></span>
    
- <span data-ttu-id="b65f0-317">下列其中之一： 加號、 減號、 或字母"A"（不區分大小寫） 其中加號表示出生 1800年 1899年之間減號登入表示出生之間 1900年-1999年和"A"表示出生 2000年及之後</span><span class="sxs-lookup"><span data-stu-id="b65f0-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="b65f0-318">三位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-318">Three digits</span></span>
    
- <span data-ttu-id="b65f0-319">一個字母或一個數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-320">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-320">Checksum</span></span>

<span data-ttu-id="b65f0-321">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-322">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-322">Definition</span></span>

<span data-ttu-id="b65f0-323">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-324">此函數`Func_finland_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-325">從關鍵字`Keywords_finland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-326">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-327">此函數`Func_finland_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-328">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="b65f0-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-330">identification number
</span><span class="sxs-lookup"><span data-stu-id="b65f0-330">identification number</span></span>
  
<span data-ttu-id="b65f0-331">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-331">personal id</span></span>
  
<span data-ttu-id="b65f0-332">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-332">identity number</span></span>
  
<span data-ttu-id="b65f0-333">芬蘭國家識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-333">finnish national id number</span></span>
  
<span data-ttu-id="b65f0-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="b65f0-334">personalidnumber#</span></span>
  
<span data-ttu-id="b65f0-335">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-335">national identification number</span></span>
  
<span data-ttu-id="b65f0-336">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-336">id number</span></span>
  
<span data-ttu-id="b65f0-337">國家識別碼沒有。</span><span class="sxs-lookup"><span data-stu-id="b65f0-337">national id no.</span></span>
  
<span data-ttu-id="b65f0-338">國家識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-338">national id number</span></span>
  
<span data-ttu-id="b65f0-339">識別碼沒有</span><span class="sxs-lookup"><span data-stu-id="b65f0-339">id no</span></span>
  
<span data-ttu-id="b65f0-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="b65f0-340">tunnistenumero</span></span>
  
<span data-ttu-id="b65f0-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="b65f0-341">henkilötunnus</span></span>
  
<span data-ttu-id="b65f0-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="b65f0-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="b65f0-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="b65f0-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="b65f0-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="b65f0-344">identiteetti numero</span></span>
  
<span data-ttu-id="b65f0-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="b65f0-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="b65f0-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="b65f0-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="b65f0-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="b65f0-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="b65f0-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="b65f0-348">tunnusnumero</span></span>
  
<span data-ttu-id="b65f0-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="b65f0-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="b65f0-350">法國</span><span class="sxs-lookup"><span data-stu-id="b65f0-350">France</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-351">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-351">Format</span></span>

<span data-ttu-id="b65f0-352">13 個人和實體的九個位數的數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-353">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-353">Pattern</span></span>

<span data-ttu-id="b65f0-354">針對個人的數字 13:</span><span class="sxs-lookup"><span data-stu-id="b65f0-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="b65f0-355">必須是 0、 1、 2 或 3 的一個數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="b65f0-356">12 位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-356">12 digits</span></span>
    
<span data-ttu-id="b65f0-357">實體的九個位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b65f0-358">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-358">Checksum</span></span>

<span data-ttu-id="b65f0-359">不適用</span><span class="sxs-lookup"><span data-stu-id="b65f0-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-360">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-360">Definition</span></span>

<span data-ttu-id="b65f0-361">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-362">此函數`Func_france_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-363">從關鍵字`Keywords_france_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-364">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-365">此函數`Func_france_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-366">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="b65f0-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-368">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-368">tax identification number</span></span>
  
<span data-ttu-id="b65f0-369">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-369">tax number</span></span>
  
<span data-ttu-id="b65f0-370">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-370">tax id</span></span>
  
<span data-ttu-id="b65f0-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="b65f0-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="b65f0-372">德國</span><span class="sxs-lookup"><span data-stu-id="b65f0-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-373">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-373">Format</span></span>

<span data-ttu-id="b65f0-374">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="b65f0-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-375">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-375">Pattern</span></span>

<span data-ttu-id="b65f0-376">11 位數：</span><span class="sxs-lookup"><span data-stu-id="b65f0-376">11 digits :</span></span>
  
-  <span data-ttu-id="b65f0-377">十位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-377">Ten digits</span></span> 
    
- <span data-ttu-id="b65f0-378">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-379">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-379">Checksum</span></span>

<span data-ttu-id="b65f0-380">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-381">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-381">Definition</span></span>

<span data-ttu-id="b65f0-382">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-383">此函數`Func_germany_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-384">從關鍵字`Keywords_germany_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-385">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-386">此函數`Func_germany_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-387">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="b65f0-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-389">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-389">tax number</span></span>
  
<span data-ttu-id="b65f0-390">稅否]。</span><span class="sxs-lookup"><span data-stu-id="b65f0-390">tax no.</span></span>
  
<span data-ttu-id="b65f0-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-391">taxno#</span></span>
  
<span data-ttu-id="b65f0-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b65f0-392">taxnumber#</span></span>
  
<span data-ttu-id="b65f0-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b65f0-393">taxnumber</span></span>
  
<span data-ttu-id="b65f0-394">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-394">tax id</span></span>
  
<span data-ttu-id="b65f0-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-395">taxid#</span></span>
  
<span data-ttu-id="b65f0-396">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-396">tax identification number</span></span>
  
<span data-ttu-id="b65f0-397">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="b65f0-397">tax identification no.</span></span>
  
<span data-ttu-id="b65f0-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="b65f0-398">steuernummer</span></span>
  
<span data-ttu-id="b65f0-399">steuer 識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-399">steuer id</span></span>
  
<span data-ttu-id="b65f0-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="b65f0-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="b65f0-401">希臘</span><span class="sxs-lookup"><span data-stu-id="b65f0-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-402">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-402">Format</span></span>

<span data-ttu-id="b65f0-403">不含空格和分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-404">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-404">Pattern</span></span>

<span data-ttu-id="b65f0-405">九位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b65f0-406">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-406">Checksum</span></span>

<span data-ttu-id="b65f0-407">不適用</span><span class="sxs-lookup"><span data-stu-id="b65f0-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-408">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-408">Definition</span></span>

<span data-ttu-id="b65f0-409">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-410">規則運算式`Regex_greece_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-411">從關鍵字`Keywords_greece_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b65f0-412">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="b65f0-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-414">afm</span><span class="sxs-lookup"><span data-stu-id="b65f0-414">afm</span></span>
  
<span data-ttu-id="b65f0-415">tin
</span><span class="sxs-lookup"><span data-stu-id="b65f0-415">tin</span></span>
  
<span data-ttu-id="b65f0-416">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="b65f0-416">tax id no.</span></span>
  
<span data-ttu-id="b65f0-417">無法稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-417">tax id no</span></span>
  
<span data-ttu-id="b65f0-418">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-418">tax identification number</span></span>
  
<span data-ttu-id="b65f0-419">稅登錄編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-419">tax registry number</span></span>
  
<span data-ttu-id="b65f0-420">無法稅登錄。</span><span class="sxs-lookup"><span data-stu-id="b65f0-420">tax registry no.</span></span>
  
<span data-ttu-id="b65f0-421">afm #</span><span class="sxs-lookup"><span data-stu-id="b65f0-421">afm#</span></span>
  
<span data-ttu-id="b65f0-422">錫 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-422">tin#</span></span>
  
<span data-ttu-id="b65f0-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-423">taxidno#</span></span>
  
<span data-ttu-id="b65f0-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-424">taxregistryno#</span></span>
  
<span data-ttu-id="b65f0-425">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="b65f0-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="b65f0-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="b65f0-426">aφμ</span></span>
  
<span data-ttu-id="b65f0-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="b65f0-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="b65f0-428">ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ。</span><span class="sxs-lookup"><span data-stu-id="b65f0-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="b65f0-429">ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="b65f0-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="b65f0-430">匈牙利</span><span class="sxs-lookup"><span data-stu-id="b65f0-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-431">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-431">Format</span></span>

<span data-ttu-id="b65f0-432">任何空格或分隔符號十位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-433">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-433">Pattern</span></span>

<span data-ttu-id="b65f0-434">十位數：</span><span class="sxs-lookup"><span data-stu-id="b65f0-434">Ten digits:</span></span>
  
-  <span data-ttu-id="b65f0-435">必須是"8"的一個數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="b65f0-436">會對應至日期之間的天數的五個位數 01/01/1867年和個別的出生的日期</span><span class="sxs-lookup"><span data-stu-id="b65f0-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="b65f0-437">三個對應來區分個人在同一天出生依照機率產生的號碼的數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="b65f0-438">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-439">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-439">Checksum</span></span>

<span data-ttu-id="b65f0-440">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-441">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-441">Definition</span></span>

<span data-ttu-id="b65f0-442">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-443">此函數`Func_hungary_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-444">從關鍵字`Keywords_hungary_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-445">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-446">此函數`Func_hungary_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-447">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="b65f0-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-449">匈牙利文稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="b65f0-450">匈牙利文錫</span><span class="sxs-lookup"><span data-stu-id="b65f0-450">hungarian tin</span></span>
  
<span data-ttu-id="b65f0-451">稅 id 號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-451">tax id number</span></span>
  
<span data-ttu-id="b65f0-452">vat 編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-452">vat number</span></span>
  
<span data-ttu-id="b65f0-453">無法稅授權單位</span><span class="sxs-lookup"><span data-stu-id="b65f0-453">tax authority no</span></span>
  
<span data-ttu-id="b65f0-454">稅識別碼稅身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-454">tax id tax identity number</span></span>
  
<span data-ttu-id="b65f0-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="b65f0-455">taxidnumber#</span></span>
  
<span data-ttu-id="b65f0-456">錫 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-456">tin#</span></span>
  
<span data-ttu-id="b65f0-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="b65f0-457">hungatiantin#</span></span>
  
<span data-ttu-id="b65f0-458">無法稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-458">tax identification no</span></span>
  
<span data-ttu-id="b65f0-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-459">taxidno#</span></span>
  
<span data-ttu-id="b65f0-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="b65f0-460">adóazonosító szám</span></span>
  
<span data-ttu-id="b65f0-461">adószám</span><span class="sxs-lookup"><span data-stu-id="b65f0-461">adószám</span></span>
  
<span data-ttu-id="b65f0-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="b65f0-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="b65f0-463">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="b65f0-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-464">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-464">Format</span></span>

<span data-ttu-id="b65f0-465">後面接著任何空格或分隔符號信件的七位數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-466">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-466">Pattern</span></span>

<span data-ttu-id="b65f0-467">後面接著一個字母的七位數字：</span><span class="sxs-lookup"><span data-stu-id="b65f0-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="b65f0-468">七位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-468">Seven digits</span></span> 
    
- <span data-ttu-id="b65f0-469">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="b65f0-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-470">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-470">Checksum</span></span>

<span data-ttu-id="b65f0-471">不適用</span><span class="sxs-lookup"><span data-stu-id="b65f0-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-472">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-472">Definition</span></span>

<span data-ttu-id="b65f0-473">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-474">此函數`Func_ireland_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-475">從關鍵字`Keywords_ireland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-476">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-477">此函數`Func_ireland_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="b65f0-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-480">公共服務沒有</span><span class="sxs-lookup"><span data-stu-id="b65f0-480">public service no</span></span>
  
<span data-ttu-id="b65f0-481">個人公用服務沒有</span><span class="sxs-lookup"><span data-stu-id="b65f0-481">personal public service no</span></span>
  
<span data-ttu-id="b65f0-482">pps 無</span><span class="sxs-lookup"><span data-stu-id="b65f0-482">pps no</span></span>
  
<span data-ttu-id="b65f0-483">個人服務否</span><span class="sxs-lookup"><span data-stu-id="b65f0-483">personal service no</span></span>
  
<span data-ttu-id="b65f0-484">pps service 否</span><span class="sxs-lookup"><span data-stu-id="b65f0-484">pps service no</span></span>
  
<span data-ttu-id="b65f0-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-485">ppsno#</span></span>
  
<span data-ttu-id="b65f0-486">愛爾蘭 pps 無</span><span class="sxs-lookup"><span data-stu-id="b65f0-486">irish pps no</span></span>
  
<span data-ttu-id="b65f0-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-487">publicserviceno#</span></span>
  
<span data-ttu-id="b65f0-488">個人公用健保號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-488">personal public service number</span></span>
  
<span data-ttu-id="b65f0-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="b65f0-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="b65f0-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="b65f0-490">pps uimh</span></span>
  
<span data-ttu-id="b65f0-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="b65f0-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="b65f0-492">義大利</span><span class="sxs-lookup"><span data-stu-id="b65f0-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-493">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-493">Format</span></span>

<span data-ttu-id="b65f0-494">16 信件與指定的型態的數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-495">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-495">Pattern</span></span>

<span data-ttu-id="b65f0-496">16 字母和數字：</span><span class="sxs-lookup"><span data-stu-id="b65f0-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="b65f0-497">會對應至系列名稱中前三個母音的三個字母</span><span class="sxs-lookup"><span data-stu-id="b65f0-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="b65f0-498">會對應至第一個、 第三和第四的三個字母母音中第一個名稱</span><span class="sxs-lookup"><span data-stu-id="b65f0-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="b65f0-499">會對應至最後一出生年的數字的兩位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="b65f0-500">一個數字對應至出生月 — 字母依字母順序使用，但僅限字母 A 到 E、 H、 L、 M、 P、 R 以 T 可用 （即得出年 1 月是 A 及年 10 月為 R）</span><span class="sxs-lookup"><span data-stu-id="b65f0-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="b65f0-501">會對應至出生 40 其中加入來區分與男生女生成績的出生的一天的每月一天的兩位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="b65f0-502">會對應至特定出生人員 municipality 區碼的四個字 — 外部的國家/地區使用全國家/地區碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="b65f0-503">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-504">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-504">Checksum</span></span>

<span data-ttu-id="b65f0-505">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-506">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-506">Definition</span></span>

<span data-ttu-id="b65f0-507">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-508">此函數`Func_italy_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-509">從關鍵字`Keywords_italy_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-510">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-511">此函數`Func_italy_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-512">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="b65f0-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-514">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-514">tax number</span></span>
  
<span data-ttu-id="b65f0-515">稅否]。</span><span class="sxs-lookup"><span data-stu-id="b65f0-515">tax no.</span></span>
  
<span data-ttu-id="b65f0-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-516">taxno#</span></span>
  
<span data-ttu-id="b65f0-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b65f0-517">taxnumber#</span></span>
  
<span data-ttu-id="b65f0-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b65f0-518">taxnumber</span></span>
  
<span data-ttu-id="b65f0-519">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-519">tax id</span></span>
  
<span data-ttu-id="b65f0-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-520">taxid#</span></span>
  
<span data-ttu-id="b65f0-521">會計程式碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-521">fiscal code</span></span>
  
<span data-ttu-id="b65f0-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b65f0-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="b65f0-523">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="b65f0-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-524">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-524">Format</span></span>

<span data-ttu-id="b65f0-525">任何空格或分隔符號 11 位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-526">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-526">Pattern</span></span>

<span data-ttu-id="b65f0-527">在指定的型態 11 位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="b65f0-528">會對應至出生 (DDMMYY) 的日期的六個數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="b65f0-529">會對應至其中"0"會對應至 19 century、"1"會對應至 20 century 及"2"會對應至第 21 世紀出生的 century 的一個數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="b65f0-530">四位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-531">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-531">Checksum</span></span>

<span data-ttu-id="b65f0-532">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-533">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-533">Definition</span></span>

<span data-ttu-id="b65f0-534">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-535">此函數`Func_latvia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-536">從關鍵字`Keywords_latvia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-537">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-538">此函數`Func_latvia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-539">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="b65f0-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-541">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-541">tax number</span></span>
  
<span data-ttu-id="b65f0-542">稅否]。</span><span class="sxs-lookup"><span data-stu-id="b65f0-542">tax no.</span></span>
  
<span data-ttu-id="b65f0-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-543">taxno#</span></span>
  
<span data-ttu-id="b65f0-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b65f0-544">taxnumber#</span></span>
  
<span data-ttu-id="b65f0-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b65f0-545">taxnumber</span></span>
  
<span data-ttu-id="b65f0-546">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-546">tax id</span></span>
  
<span data-ttu-id="b65f0-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-547">taxid#</span></span>
  
<span data-ttu-id="b65f0-548">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-548">tax identification number</span></span>
  
<span data-ttu-id="b65f0-549">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="b65f0-549">tax identification no.</span></span>
  
<span data-ttu-id="b65f0-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="b65f0-550">nodokļa numurs</span></span>
  
<span data-ttu-id="b65f0-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="b65f0-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="b65f0-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="b65f0-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="b65f0-553">立陶宛</span><span class="sxs-lookup"><span data-stu-id="b65f0-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-554">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-554">Format</span></span>

<span data-ttu-id="b65f0-555">不含空格或分隔符號 11 位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-556">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-556">Pattern</span></span>

<span data-ttu-id="b65f0-557">11 位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b65f0-558">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-558">Checksum</span></span>

<span data-ttu-id="b65f0-559">不適用</span><span class="sxs-lookup"><span data-stu-id="b65f0-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-560">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-560">Definition</span></span>

<span data-ttu-id="b65f0-561">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-562">此函數`Func_lithuania_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-563">從關鍵字`Keywords_lithuania_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-564">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-565">此函數`Func_lithuania_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-566">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="b65f0-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-568">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-568">tax number</span></span>
  
<span data-ttu-id="b65f0-569">稅否]。</span><span class="sxs-lookup"><span data-stu-id="b65f0-569">tax no.</span></span>
  
<span data-ttu-id="b65f0-570">稅否 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-570">tax no#</span></span>
  
<span data-ttu-id="b65f0-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b65f0-571">taxnumber#</span></span>
  
<span data-ttu-id="b65f0-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b65f0-572">taxnumber</span></span>
  
<span data-ttu-id="b65f0-573">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-573">tax id</span></span>
  
<span data-ttu-id="b65f0-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-574">taxid#</span></span>
  
<span data-ttu-id="b65f0-575">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-575">tax identification number</span></span>
  
<span data-ttu-id="b65f0-576">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="b65f0-576">tax identification no.</span></span>
  
<span data-ttu-id="b65f0-577">mokesčių 識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-577">mokesčių id</span></span>
  
<span data-ttu-id="b65f0-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="b65f0-578">mokesčių numeris</span></span>
  
<span data-ttu-id="b65f0-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="b65f0-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="b65f0-580">盧森堡</span><span class="sxs-lookup"><span data-stu-id="b65f0-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-581">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-581">Format</span></span>

<span data-ttu-id="b65f0-582">任何空格或分隔字元 13 數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-583">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-583">Pattern</span></span>

<span data-ttu-id="b65f0-584">13 位數：</span><span class="sxs-lookup"><span data-stu-id="b65f0-584">13 digits:</span></span>
  
-  <span data-ttu-id="b65f0-585">11 位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-585">11 digits</span></span> 
    
- <span data-ttu-id="b65f0-586">二位數檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-587">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-587">Checksum</span></span>

<span data-ttu-id="b65f0-588">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-589">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-589">Definition</span></span>

<span data-ttu-id="b65f0-590">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-591">此函數`Func_luxemburg_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-592">從關鍵字`Keywords_luxemburg_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-593">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-594">此函數`Func_luxemburg_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-595">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="b65f0-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-597">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-597">tax number</span></span>
  
<span data-ttu-id="b65f0-598">稅否]。</span><span class="sxs-lookup"><span data-stu-id="b65f0-598">tax no.</span></span>
  
<span data-ttu-id="b65f0-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-599">taxno#</span></span>
  
<span data-ttu-id="b65f0-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b65f0-600">taxnumber#</span></span>
  
<span data-ttu-id="b65f0-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b65f0-601">taxnumber</span></span>
  
<span data-ttu-id="b65f0-602">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-602">tax id</span></span>
  
<span data-ttu-id="b65f0-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-603">taxid#</span></span>
  
<span data-ttu-id="b65f0-604">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-604">tax identification number</span></span>
  
<span data-ttu-id="b65f0-605">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="b65f0-605">tax identification no.</span></span>
  
<span data-ttu-id="b65f0-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="b65f0-606">steuernummer</span></span>
  
<span data-ttu-id="b65f0-607">steuer 識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-607">steuer id</span></span>
  
<span data-ttu-id="b65f0-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="b65f0-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="b65f0-609">馬爾他</span><span class="sxs-lookup"><span data-stu-id="b65f0-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-610">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-610">Format</span></span>

<span data-ttu-id="b65f0-611">馬爾他 nationals 的： 7 位數和指定的型態的其中一個字母</span><span class="sxs-lookup"><span data-stu-id="b65f0-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="b65f0-612">非馬爾他文 nationals 和馬爾他實體： 9 的數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-613">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-613">Pattern</span></span>

<span data-ttu-id="b65f0-614">馬爾他 nationals: 7 位數和一個字母</span><span class="sxs-lookup"><span data-stu-id="b65f0-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="b65f0-615">七位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-615">Seven digits</span></span> 
    
- <span data-ttu-id="b65f0-616">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="b65f0-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="b65f0-617">非馬爾他文 nationals 和馬爾他實體： 9 的數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="b65f0-618">九位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="b65f0-619">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-619">Checksum</span></span>

<span data-ttu-id="b65f0-620">不適用</span><span class="sxs-lookup"><span data-stu-id="b65f0-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-621">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-621">Definition</span></span>

<span data-ttu-id="b65f0-622">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-623">此函數`Func_malta_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-624">從關鍵字`Keywords_malta_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-625">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-626">此函數`Func_malta_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-627">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="b65f0-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-629">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-629">tax number</span></span>
  
<span data-ttu-id="b65f0-630">稅否]。</span><span class="sxs-lookup"><span data-stu-id="b65f0-630">tax no.</span></span>
  
<span data-ttu-id="b65f0-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-631">taxno#</span></span>
  
<span data-ttu-id="b65f0-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b65f0-632">taxnumber#</span></span>
  
<span data-ttu-id="b65f0-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b65f0-633">taxnumber</span></span>
  
<span data-ttu-id="b65f0-634">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-634">tax id</span></span>
  
<span data-ttu-id="b65f0-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-635">taxid#</span></span>
  
<span data-ttu-id="b65f0-636">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-636">tax identification number</span></span>
  
<span data-ttu-id="b65f0-637">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="b65f0-637">tax identification no.</span></span>
  
<span data-ttu-id="b65f0-638">numru 且 taxxa</span><span class="sxs-lookup"><span data-stu-id="b65f0-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="b65f0-639">識別碼且 taxxa</span><span class="sxs-lookup"><span data-stu-id="b65f0-639">id tat-taxxa</span></span>
  
<span data-ttu-id="b65f0-640">numru 東西 ' identifikazzjoni 且 taxxa</span><span class="sxs-lookup"><span data-stu-id="b65f0-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="b65f0-641">荷蘭</span><span class="sxs-lookup"><span data-stu-id="b65f0-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-642">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-642">Format</span></span>

<span data-ttu-id="b65f0-643">不含空格或分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-644">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-644">Pattern</span></span>

<span data-ttu-id="b65f0-645">九位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="b65f0-646">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-646">Checksum</span></span>

<span data-ttu-id="b65f0-647">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-648">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-648">Definition</span></span>

<span data-ttu-id="b65f0-649">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-650">此函數`Func_netherlands_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-651">從關鍵字`Keywords_netherlands_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-652">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-653">此函數`Func_netherlands_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-654">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="b65f0-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-656">荷蘭稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="b65f0-657">荷蘭稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-657">netherlands tax identification</span></span>
  
<span data-ttu-id="b65f0-658">荷屬安的稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="b65f0-659">荷屬安的稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-659">netherland's tax identification</span></span>
  
<span data-ttu-id="b65f0-660">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-660">tax identification number</span></span>
  
<span data-ttu-id="b65f0-661">荷蘭文稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-661">dutch tax id</span></span>
  
<span data-ttu-id="b65f0-662">荷蘭文稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-662">dutch tax identification number</span></span>
  
<span data-ttu-id="b65f0-663">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-663">tax id</span></span>
  
<span data-ttu-id="b65f0-664">稅識別碼 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-664">tax id#</span></span>
  
<span data-ttu-id="b65f0-665">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-665">tax number</span></span>
  
<span data-ttu-id="b65f0-666">稅否 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-666">tax no#</span></span>
  
<span data-ttu-id="b65f0-667">稅 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-667">tax#</span></span>
  
<span data-ttu-id="b65f0-668">tin
</span><span class="sxs-lookup"><span data-stu-id="b65f0-668">tin</span></span>
  
<span data-ttu-id="b65f0-669">錫 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-669">tin#</span></span>
  
<span data-ttu-id="b65f0-670">荷蘭錫</span><span class="sxs-lookup"><span data-stu-id="b65f0-670">netherlands tin</span></span>
  
<span data-ttu-id="b65f0-671">荷屬安的錫</span><span class="sxs-lookup"><span data-stu-id="b65f0-671">netherland's tin</span></span>
  
<span data-ttu-id="b65f0-672">荷蘭 belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="b65f0-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="b65f0-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="b65f0-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="b65f0-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="b65f0-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="b65f0-675">荷蘭 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="b65f0-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="b65f0-676">荷蘭 belasting 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="b65f0-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="b65f0-677">荷蘭 belastingnummer</span><span class="sxs-lookup"><span data-stu-id="b65f0-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="b65f0-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="b65f0-678">btw nummer</span></span>
  
<span data-ttu-id="b65f0-679">文拚字檢查 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="b65f0-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="b65f0-680">波蘭</span><span class="sxs-lookup"><span data-stu-id="b65f0-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-681">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-681">Format</span></span>

<span data-ttu-id="b65f0-682">任何空格或分隔符號十一份數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-683">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-683">Pattern</span></span>

<span data-ttu-id="b65f0-684">另外的數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b65f0-685">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-685">Checksum</span></span>

<span data-ttu-id="b65f0-686">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-687">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-687">Definition</span></span>

<span data-ttu-id="b65f0-688">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-689">此函數`Func_poland_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-690">從關鍵字`Keywords_poland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-691">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-692">此函數`Func_poland_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-693">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="b65f0-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-695">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-695">tax number</span></span>
  
<span data-ttu-id="b65f0-696">稅否]。</span><span class="sxs-lookup"><span data-stu-id="b65f0-696">tax no.</span></span>
  
<span data-ttu-id="b65f0-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-697">taxno#</span></span>
  
<span data-ttu-id="b65f0-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b65f0-698">taxnumber#</span></span>
  
<span data-ttu-id="b65f0-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b65f0-699">taxnumber</span></span>
  
<span data-ttu-id="b65f0-700">nip</span><span class="sxs-lookup"><span data-stu-id="b65f0-700">nip</span></span>
  
<span data-ttu-id="b65f0-701">nip #</span><span class="sxs-lookup"><span data-stu-id="b65f0-701">nip#</span></span>
  
<span data-ttu-id="b65f0-702">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-702">tax id</span></span>
  
<span data-ttu-id="b65f0-703">稅識別碼 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-703">tax id#</span></span>
  
<span data-ttu-id="b65f0-704">nip 識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-704">nip id</span></span>
  
<span data-ttu-id="b65f0-705">nip 識別碼 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-705">nip id#</span></span>
  
<span data-ttu-id="b65f0-706">稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-706">tax identification number</span></span>
  
<span data-ttu-id="b65f0-707">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="b65f0-707">tax identification no.</span></span>
  
<span data-ttu-id="b65f0-708">vat 編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-708">vat number</span></span>
  
<span data-ttu-id="b65f0-709">vat 否]。</span><span class="sxs-lookup"><span data-stu-id="b65f0-709">vat no.</span></span>
  
<span data-ttu-id="b65f0-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-710">vatno#</span></span>
  
<span data-ttu-id="b65f0-711">增值稅識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-711">vat id</span></span>
  
<span data-ttu-id="b65f0-712">增值稅識別碼 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-712">vat id#</span></span>
  
<span data-ttu-id="b65f0-713">數目 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="b65f0-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="b65f0-714">polski 數目 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="b65f0-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="b65f0-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="b65f0-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="b65f0-716">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="b65f0-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-717">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-717">Format</span></span>

<span data-ttu-id="b65f0-718">任何空格或分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-719">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-719">Pattern</span></span>

<span data-ttu-id="b65f0-720">九位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b65f0-721">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-721">Checksum</span></span>

<span data-ttu-id="b65f0-722">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-723">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-723">Definition</span></span>

<span data-ttu-id="b65f0-724">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-725">此函數`Func_portugal_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-726">從關鍵字`Keywords_portugal_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-727">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-728">此函數`Func_portugal_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-729">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="b65f0-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-731">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-731">tax number</span></span>
  
<span data-ttu-id="b65f0-732">稅否]。</span><span class="sxs-lookup"><span data-stu-id="b65f0-732">tax no.</span></span>
  
<span data-ttu-id="b65f0-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-733">taxno#</span></span>
  
<span data-ttu-id="b65f0-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b65f0-734">taxnumber#</span></span>
  
<span data-ttu-id="b65f0-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b65f0-735">taxnumber</span></span>
  
<span data-ttu-id="b65f0-736">n 如果</span><span class="sxs-lookup"><span data-stu-id="b65f0-736">nif</span></span>
  
<span data-ttu-id="b65f0-737">n 如果 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-737">nif#</span></span>
  
<span data-ttu-id="b65f0-738">numero 會計</span><span class="sxs-lookup"><span data-stu-id="b65f0-738">numero fiscal</span></span>
  
<span data-ttu-id="b65f0-739">número de identificação 會計</span><span class="sxs-lookup"><span data-stu-id="b65f0-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="b65f0-740">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="b65f0-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-741">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-741">Format</span></span>

<span data-ttu-id="b65f0-742">任何空格或分隔字元 13 數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-743">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-743">Pattern</span></span>

<span data-ttu-id="b65f0-744">13 位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b65f0-745">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-745">Checksum</span></span>

<span data-ttu-id="b65f0-746">不適用</span><span class="sxs-lookup"><span data-stu-id="b65f0-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-747">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-747">Definition</span></span>

<span data-ttu-id="b65f0-748">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-749">規則運算式`Regex_romania_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-750">從關鍵字`Keywords_romania_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b65f0-751">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="b65f0-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-753">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-753">tax id</span></span>
  
<span data-ttu-id="b65f0-754">稅 id 號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-754">tax id number</span></span>
  
<span data-ttu-id="b65f0-755">無法稅檔案</span><span class="sxs-lookup"><span data-stu-id="b65f0-755">tax file no</span></span>
  
<span data-ttu-id="b65f0-756">

tax file number</span><span class="sxs-lookup"><span data-stu-id="b65f0-756">tax file number</span></span>
  
<span data-ttu-id="b65f0-757">稅否</span><span class="sxs-lookup"><span data-stu-id="b65f0-757">tax no</span></span>
  
<span data-ttu-id="b65f0-758">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-758">tax number</span></span>
  
<span data-ttu-id="b65f0-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-759">taxid#</span></span>
  
<span data-ttu-id="b65f0-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-760">taxno#</span></span>
  
<span data-ttu-id="b65f0-761">識別碼 ul taxei</span><span class="sxs-lookup"><span data-stu-id="b65f0-761">id-ul taxei</span></span>
  
<span data-ttu-id="b65f0-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="b65f0-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="b65f0-763">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="b65f0-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-764">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-764">Format</span></span>

<span data-ttu-id="b65f0-765">任何空格或分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-766">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-766">Pattern</span></span>

<span data-ttu-id="b65f0-767">10 位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b65f0-768">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-768">Checksum</span></span>

<span data-ttu-id="b65f0-769">不適用</span><span class="sxs-lookup"><span data-stu-id="b65f0-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-770">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-770">Definition</span></span>

<span data-ttu-id="b65f0-771">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-772">規則運算式`Regex_slovakia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-773">從關鍵字`Keywords_slovakia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b65f0-774">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="b65f0-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-776">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-776">tax id</span></span>
  
<span data-ttu-id="b65f0-777">稅 id 號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-777">tax id number</span></span>
  
<span data-ttu-id="b65f0-778">鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-778">tin id</span></span>
  
<span data-ttu-id="b65f0-779">鐵皮否</span><span class="sxs-lookup"><span data-stu-id="b65f0-779">tin no</span></span>
  
<span data-ttu-id="b65f0-780">斯洛伐克鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-780">slovakian tin id</span></span>
  
<span data-ttu-id="b65f0-781">tin
</span><span class="sxs-lookup"><span data-stu-id="b65f0-781">tin</span></span>
  
<span data-ttu-id="b65f0-782">無法稅檔案</span><span class="sxs-lookup"><span data-stu-id="b65f0-782">tax file no</span></span>
  
<span data-ttu-id="b65f0-783">

tax file number</span><span class="sxs-lookup"><span data-stu-id="b65f0-783">tax file number</span></span>
  
<span data-ttu-id="b65f0-784">稅否</span><span class="sxs-lookup"><span data-stu-id="b65f0-784">tax no</span></span>
  
<span data-ttu-id="b65f0-785">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-785">tax number</span></span>
  
<span data-ttu-id="b65f0-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-786">taxid#</span></span>
  
<span data-ttu-id="b65f0-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-787">taxno#</span></span>
  
<span data-ttu-id="b65f0-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="b65f0-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="b65f0-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="b65f0-789">daňové číslo</span></span>
  
<span data-ttu-id="b65f0-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="b65f0-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="b65f0-791">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="b65f0-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-792">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-792">Format</span></span>

<span data-ttu-id="b65f0-793">任何空格或分隔字元的八個位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-794">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-794">Pattern</span></span>

<span data-ttu-id="b65f0-795">八位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b65f0-796">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-796">Checksum</span></span>

<span data-ttu-id="b65f0-797">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-798">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-798">Definition</span></span>

<span data-ttu-id="b65f0-799">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-800">此函數`Func_slovenia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-801">從關鍵字`Keywords_slovenia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-802">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-803">此函數`Func_slovenia_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-804">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="b65f0-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-806">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-806">tax id</span></span>
  
<span data-ttu-id="b65f0-807">稅 id 號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-807">tax id number</span></span>
  
<span data-ttu-id="b65f0-808">鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-808">tin id</span></span>
  
<span data-ttu-id="b65f0-809">鐵皮否</span><span class="sxs-lookup"><span data-stu-id="b65f0-809">tin no</span></span>
  
<span data-ttu-id="b65f0-810">斯洛維尼亞文鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-810">slovenian tin id</span></span>
  
<span data-ttu-id="b65f0-811">tin
</span><span class="sxs-lookup"><span data-stu-id="b65f0-811">tin</span></span>
  
<span data-ttu-id="b65f0-812">無法稅檔案</span><span class="sxs-lookup"><span data-stu-id="b65f0-812">tax file no</span></span>
  
<span data-ttu-id="b65f0-813">

tax file number</span><span class="sxs-lookup"><span data-stu-id="b65f0-813">tax file number</span></span>
  
<span data-ttu-id="b65f0-814">稅否</span><span class="sxs-lookup"><span data-stu-id="b65f0-814">tax no</span></span>
  
<span data-ttu-id="b65f0-815">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-815">tax number</span></span>
  
<span data-ttu-id="b65f0-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-816">taxid#</span></span>
  
<span data-ttu-id="b65f0-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-817">taxno#</span></span>
  
<span data-ttu-id="b65f0-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="b65f0-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="b65f0-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="b65f0-819">davčna številka</span></span>
  
<span data-ttu-id="b65f0-820">Številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="b65f0-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="b65f0-821">西班牙</span><span class="sxs-lookup"><span data-stu-id="b65f0-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-822">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-822">Format</span></span>

<span data-ttu-id="b65f0-823">七個或八個位數和中指定的型態的一或兩個字母</span><span class="sxs-lookup"><span data-stu-id="b65f0-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-824">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-824">Pattern</span></span>

<span data-ttu-id="b65f0-825">西班牙文自然資料提供者與西班牙國民身分識別卡：</span><span class="sxs-lookup"><span data-stu-id="b65f0-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="b65f0-826">八位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-826">Eight digits</span></span> 
    
- <span data-ttu-id="b65f0-827">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="b65f0-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="b65f0-828">西班牙國民身分識別卡而非駐留西班牙人</span><span class="sxs-lookup"><span data-stu-id="b65f0-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="b65f0-829">一個大寫字母"L"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="b65f0-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="b65f0-830">七位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-830">Seven digits</span></span>
    
- <span data-ttu-id="b65f0-831">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="b65f0-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="b65f0-832">底下的年齡 14 年不含西班牙國民身分識別卡駐留西班牙人：</span><span class="sxs-lookup"><span data-stu-id="b65f0-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="b65f0-833">一個大寫字母"K"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="b65f0-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="b65f0-834">七位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-834">Seven digits</span></span> 
    
- <span data-ttu-id="b65f0-835">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="b65f0-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="b65f0-836">外國人與因此識別號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="b65f0-837">一個大寫也就是字母"X"、"Y"或"Z"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="b65f0-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="b65f0-838">七位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-838">Seven digits</span></span>
    
- <span data-ttu-id="b65f0-839">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="b65f0-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="b65f0-840">外國人沒有因此識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="b65f0-841">一個大寫字母的"M"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="b65f0-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="b65f0-842">七位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-842">Seven digits</span></span>
    
- <span data-ttu-id="b65f0-843">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="b65f0-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="b65f0-844">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-844">Checksum</span></span>

<span data-ttu-id="b65f0-845">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-846">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-846">Definition</span></span>

<span data-ttu-id="b65f0-847">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-848">此函數`Func_spain_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-849">從關鍵字`Keywords_spain_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-850">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-851">此函數`Func_spain_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-852">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="b65f0-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-854">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-854">tax id</span></span>
  
<span data-ttu-id="b65f0-855">稅 id 號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-855">tax id number</span></span>
  
<span data-ttu-id="b65f0-856">cif 識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-856">cif id</span></span>
  
<span data-ttu-id="b65f0-857">cif 沒有</span><span class="sxs-lookup"><span data-stu-id="b65f0-857">cif no</span></span>
  
<span data-ttu-id="b65f0-858">西班牙文 cif 識別碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-858">spanish cif id</span></span>
  
<span data-ttu-id="b65f0-859">cif</span><span class="sxs-lookup"><span data-stu-id="b65f0-859">cif</span></span>
  
<span data-ttu-id="b65f0-860">無法稅檔案</span><span class="sxs-lookup"><span data-stu-id="b65f0-860">tax file no</span></span>
  
<span data-ttu-id="b65f0-861">西班牙文 cif 數目</span><span class="sxs-lookup"><span data-stu-id="b65f0-861">spanish cif number</span></span>
  
<span data-ttu-id="b65f0-862">

tax file number</span><span class="sxs-lookup"><span data-stu-id="b65f0-862">tax file number</span></span>
  
<span data-ttu-id="b65f0-863">西班牙文 cif 沒有</span><span class="sxs-lookup"><span data-stu-id="b65f0-863">spanish cif no</span></span>
  
<span data-ttu-id="b65f0-864">稅否</span><span class="sxs-lookup"><span data-stu-id="b65f0-864">tax no</span></span>
  
<span data-ttu-id="b65f0-865">稅編號</span><span class="sxs-lookup"><span data-stu-id="b65f0-865">tax number</span></span>
  
<span data-ttu-id="b65f0-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-866">taxid#</span></span>
  
<span data-ttu-id="b65f0-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-867">taxno#</span></span>
  
<span data-ttu-id="b65f0-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-868">cifid#</span></span>
  
<span data-ttu-id="b65f0-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-869">spanishcifid#</span></span>
  
<span data-ttu-id="b65f0-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="b65f0-870">spanishcifno#</span></span>
  
<span data-ttu-id="b65f0-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="b65f0-871">número de contribuyente</span></span>
  
<span data-ttu-id="b65f0-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="b65f0-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="b65f0-873">número de identificación 會計</span><span class="sxs-lookup"><span data-stu-id="b65f0-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="b65f0-874">cif número</span><span class="sxs-lookup"><span data-stu-id="b65f0-874">cif número</span></span>
  
<span data-ttu-id="b65f0-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="b65f0-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="b65f0-876">瑞典</span><span class="sxs-lookup"><span data-stu-id="b65f0-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-877">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-877">Format</span></span>

<span data-ttu-id="b65f0-878">十位數和中指定的型態的符號</span><span class="sxs-lookup"><span data-stu-id="b65f0-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-879">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-879">Pattern</span></span>

<span data-ttu-id="b65f0-880">十位數和符號：</span><span class="sxs-lookup"><span data-stu-id="b65f0-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="b65f0-881">會對應至出生日期 (YYMMDD) 的六個數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="b65f0-882">加號、 減號、 或反斜線</span><span class="sxs-lookup"><span data-stu-id="b65f0-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="b65f0-883">進行識別的三個位數字唯一的位置：</span><span class="sxs-lookup"><span data-stu-id="b65f0-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="b65f0-884">對於 1990年之前發行的數字、 第七個和第八個位數識別出生或 foreign-born 人員郡</span><span class="sxs-lookup"><span data-stu-id="b65f0-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="b65f0-885">第九個位置中的數字表示任一奇數女性 2 男或甚至是依性別</span><span class="sxs-lookup"><span data-stu-id="b65f0-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="b65f0-886">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="b65f0-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b65f0-887">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-887">Checksum</span></span>

<span data-ttu-id="b65f0-888">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-889">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-889">Definition</span></span>

<span data-ttu-id="b65f0-890">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-891">此函數`Func_sweden_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-892">從關鍵字`Keywords_sweden_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b65f0-893">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-894">此函數`Func_sweden_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b65f0-895">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="b65f0-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-897">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-897">tax id</span></span>
  
<span data-ttu-id="b65f0-898">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="b65f0-898">tax id no.</span></span>
  
<span data-ttu-id="b65f0-899">稅 id 號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-899">tax id number</span></span>
  
<span data-ttu-id="b65f0-900">tax identification
</span><span class="sxs-lookup"><span data-stu-id="b65f0-900">tax identification</span></span>
  
<span data-ttu-id="b65f0-901">稅識別 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-901">tax identification#</span></span>
  
<span data-ttu-id="b65f0-902">稅否]。</span><span class="sxs-lookup"><span data-stu-id="b65f0-902">tax no.</span></span>
  
<span data-ttu-id="b65f0-903">稅 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-903">tax#</span></span>
  
<span data-ttu-id="b65f0-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-904">taxid#</span></span>
  
<span data-ttu-id="b65f0-905">稅檔案</span><span class="sxs-lookup"><span data-stu-id="b65f0-905">tax file</span></span>
  
<span data-ttu-id="b65f0-906">無法稅檔案。</span><span class="sxs-lookup"><span data-stu-id="b65f0-906">tax file no.</span></span>
  
<span data-ttu-id="b65f0-907">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-907">personal id number</span></span>
  
<span data-ttu-id="b65f0-908">skatt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="b65f0-908">skatt id nummer</span></span>
  
<span data-ttu-id="b65f0-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="b65f0-909">skatt identifikation</span></span>
  
<span data-ttu-id="b65f0-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="b65f0-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="b65f0-911">英國</span><span class="sxs-lookup"><span data-stu-id="b65f0-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="b65f0-912">格式</span><span class="sxs-lookup"><span data-stu-id="b65f0-912">Format</span></span>

<span data-ttu-id="b65f0-913">唯一 Taxpayer 參照 (UTR)： 10 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="b65f0-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="b65f0-p103">國家保險號碼 (NINO)： 如需詳細資訊，請參閱區段"英國 National 保險數 (NINO)"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b65f0-p103">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b65f0-916">模式</span><span class="sxs-lookup"><span data-stu-id="b65f0-916">Pattern</span></span>

<span data-ttu-id="b65f0-917">唯一 Taxpayer 參照 (UTR)： 10 位數</span><span class="sxs-lookup"><span data-stu-id="b65f0-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="b65f0-p104">國家保險號碼 (NINO)： 如需詳細資訊，請參閱區段"英國 National 保險數 (NINO)"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b65f0-p104">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b65f0-920">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-920">Checksum</span></span>

<span data-ttu-id="b65f0-921">是</span><span class="sxs-lookup"><span data-stu-id="b65f0-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b65f0-922">定義</span><span class="sxs-lookup"><span data-stu-id="b65f0-922">Definition</span></span>

<span data-ttu-id="b65f0-923">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="b65f0-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b65f0-924">此函數`Func_uk_eu_tax_file_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="b65f0-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b65f0-925">從關鍵字`Keywords_uk_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="b65f0-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b65f0-926">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b65f0-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="b65f0-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b65f0-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="b65f0-928">tax id
</span><span class="sxs-lookup"><span data-stu-id="b65f0-928">tax id</span></span>
  
<span data-ttu-id="b65f0-929">無法稅識別碼。</span><span class="sxs-lookup"><span data-stu-id="b65f0-929">tax id no.</span></span>
  
<span data-ttu-id="b65f0-930">稅 id 號碼</span><span class="sxs-lookup"><span data-stu-id="b65f0-930">tax id number</span></span>
  
<span data-ttu-id="b65f0-931">tax identification
</span><span class="sxs-lookup"><span data-stu-id="b65f0-931">tax identification</span></span>
  
<span data-ttu-id="b65f0-932">稅識別 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-932">tax identification#</span></span>
  
<span data-ttu-id="b65f0-933">稅否]。</span><span class="sxs-lookup"><span data-stu-id="b65f0-933">tax no.</span></span>
  
<span data-ttu-id="b65f0-934">稅 #</span><span class="sxs-lookup"><span data-stu-id="b65f0-934">tax#</span></span>
  
<span data-ttu-id="b65f0-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="b65f0-935">taxid#</span></span>
  
<span data-ttu-id="b65f0-936">稅檔案</span><span class="sxs-lookup"><span data-stu-id="b65f0-936">tax file</span></span>
  
<span data-ttu-id="b65f0-937">無法稅檔案。</span><span class="sxs-lookup"><span data-stu-id="b65f0-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b65f0-938">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b65f0-938">See also</span></span>

[<span data-ttu-id="b65f0-939">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="b65f0-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

