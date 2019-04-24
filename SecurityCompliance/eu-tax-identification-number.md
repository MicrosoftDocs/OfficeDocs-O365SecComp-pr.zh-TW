---
title: 歐盟稅務識別碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟稅務識別號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: 4914ff078695519c2a298190d82c86a6abebceb9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255521"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="92b08-104">歐盟稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-104">EU Tax Identification Number</span></span>

<span data-ttu-id="92b08-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟稅務識別號碼 （錫） 敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="92b08-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="92b08-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="92b08-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="92b08-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="92b08-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="92b08-108">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-108">Format</span></span>

<span data-ttu-id="92b08-109">選擇性連字號和正斜線的九位數</span><span class="sxs-lookup"><span data-stu-id="92b08-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-110">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-110">Pattern</span></span>

<span data-ttu-id="92b08-111">選擇性連字號和正斜線的九位數：</span><span class="sxs-lookup"><span data-stu-id="92b08-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="92b08-112">兩位數</span><span class="sxs-lookup"><span data-stu-id="92b08-112">Two digits</span></span> 
    
- <span data-ttu-id="92b08-113">連字號 （選用）</span><span class="sxs-lookup"><span data-stu-id="92b08-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="92b08-114">三位數</span><span class="sxs-lookup"><span data-stu-id="92b08-114">Three digits</span></span>
    
- <span data-ttu-id="92b08-115">正斜線 （選用）</span><span class="sxs-lookup"><span data-stu-id="92b08-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="92b08-116">四位數</span><span class="sxs-lookup"><span data-stu-id="92b08-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-117">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-117">Checksum</span></span>

<span data-ttu-id="92b08-118">是</span><span class="sxs-lookup"><span data-stu-id="92b08-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-119">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-119">Definition</span></span>

<span data-ttu-id="92b08-120">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-121">函式`Func_austria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-122">從關鍵字`Keywords_austria_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-123">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-124">函式`Func_austria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-125">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="92b08-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-127">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-127">tax number</span></span>
  
<span data-ttu-id="92b08-128">number</span><span class="sxs-lookup"><span data-stu-id="92b08-128">number</span></span>
  
<span data-ttu-id="92b08-129">稅務登記號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-129">tax registration number</span></span>
  
<span data-ttu-id="92b08-130">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-130">tax id</span></span>
  
<span data-ttu-id="92b08-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="92b08-131">st.nr.</span></span>
  
<span data-ttu-id="92b08-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="92b08-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="92b08-133">比利時</span><span class="sxs-lookup"><span data-stu-id="92b08-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="92b08-134">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-134">Format</span></span>

<span data-ttu-id="92b08-135">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="92b08-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-136">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-136">Pattern</span></span>

<span data-ttu-id="92b08-137">11 位數：</span><span class="sxs-lookup"><span data-stu-id="92b08-137">11 digits:</span></span>
  
- <span data-ttu-id="92b08-138">兩位數</span><span class="sxs-lookup"><span data-stu-id="92b08-138">Two digits</span></span>
    
- <span data-ttu-id="92b08-139">「 0 」 或者 「 1 」</span><span class="sxs-lookup"><span data-stu-id="92b08-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="92b08-140">一位數</span><span class="sxs-lookup"><span data-stu-id="92b08-140">One digit</span></span>
    
- <span data-ttu-id="92b08-141">"0"或"1"或"2"或者"3"</span><span class="sxs-lookup"><span data-stu-id="92b08-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="92b08-142">六位數</span><span class="sxs-lookup"><span data-stu-id="92b08-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-143">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-143">Checksum</span></span>

<span data-ttu-id="92b08-144">不適用</span><span class="sxs-lookup"><span data-stu-id="92b08-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-145">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-145">Definition</span></span>

<span data-ttu-id="92b08-146">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-147">規則運算式`Regex_belgium_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-148">從關鍵字`Keywords_belgium_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="92b08-149">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="92b08-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-151">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-151">tax number</span></span>
  
<span data-ttu-id="92b08-152">國民登記號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-152">national registration number</span></span>
  
<span data-ttu-id="92b08-153">稅務登記號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-153">tax registration number</span></span>
  
<span data-ttu-id="92b08-154">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-154">tax id</span></span>
  
<span data-ttu-id="92b08-155">n 如果</span><span class="sxs-lookup"><span data-stu-id="92b08-155">nif</span></span>
  
<span data-ttu-id="92b08-156">n 如果 #</span><span class="sxs-lookup"><span data-stu-id="92b08-156">nif#</span></span>
  
<span data-ttu-id="92b08-157">numéro de registre 國際電話</span><span class="sxs-lookup"><span data-stu-id="92b08-157">numéro de registre national</span></span>
  
<span data-ttu-id="92b08-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="92b08-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="92b08-159">保加利亞</span><span class="sxs-lookup"><span data-stu-id="92b08-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="92b08-160">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-160">Format</span></span>

<span data-ttu-id="92b08-161">如果沒有空格和分隔符號十位數</span><span class="sxs-lookup"><span data-stu-id="92b08-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-162">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-162">Pattern</span></span>

<span data-ttu-id="92b08-163">10 位數</span><span class="sxs-lookup"><span data-stu-id="92b08-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="92b08-164">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-164">Checksum</span></span>

<span data-ttu-id="92b08-165">是</span><span class="sxs-lookup"><span data-stu-id="92b08-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-166">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-166">Definition</span></span>

<span data-ttu-id="92b08-167">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-168">函式`Func_bulgaria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-169">從關鍵字`Keywords_bulgaria_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-170">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-171">函式`Func_bulgaria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-172">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="92b08-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-174">bucn</span><span class="sxs-lookup"><span data-stu-id="92b08-174">bucn</span></span>
  
<span data-ttu-id="92b08-175">統一民事數目</span><span class="sxs-lookup"><span data-stu-id="92b08-175">uniform civil number</span></span>
  
<span data-ttu-id="92b08-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="92b08-176">bucn#</span></span>
  
<span data-ttu-id="92b08-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="92b08-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="92b08-178">統一民事識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-178">uniform civil id</span></span>
  
<span data-ttu-id="92b08-179">統一民事否</span><span class="sxs-lookup"><span data-stu-id="92b08-179">uniform civil no</span></span>
  
<span data-ttu-id="92b08-180">egn</span><span class="sxs-lookup"><span data-stu-id="92b08-180">egn</span></span>
  
<span data-ttu-id="92b08-181">保加利亞文統一民事數目</span><span class="sxs-lookup"><span data-stu-id="92b08-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="92b08-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="92b08-182">uniformcivilno#</span></span>
  
<span data-ttu-id="92b08-183">egn #</span><span class="sxs-lookup"><span data-stu-id="92b08-183">egn#</span></span>
  
<span data-ttu-id="92b08-184">УНИФОРМ ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="92b08-184">униформ граждански номер</span></span>
  
<span data-ttu-id="92b08-185">Униформ 識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-185">униформ id</span></span>
  
<span data-ttu-id="92b08-186">Униформ граждански 識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-186">униформ граждански id</span></span>
  
<span data-ttu-id="92b08-187">УНИФОРМ ГРАЖДАНСКИ НЕ</span><span class="sxs-lookup"><span data-stu-id="92b08-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="92b08-188">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="92b08-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="92b08-189">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-189">Format</span></span>

<span data-ttu-id="92b08-190">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="92b08-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-191">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-191">Pattern</span></span>

<span data-ttu-id="92b08-192">11 位數：</span><span class="sxs-lookup"><span data-stu-id="92b08-192">11 digits:</span></span>
  
- <span data-ttu-id="92b08-193">十位數，隨機選擇</span><span class="sxs-lookup"><span data-stu-id="92b08-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="92b08-194">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-195">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-195">Checksum</span></span>

<span data-ttu-id="92b08-196">是</span><span class="sxs-lookup"><span data-stu-id="92b08-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-197">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-197">Definition</span></span>

<span data-ttu-id="92b08-198">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-199">函式`Func_croatia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-200">從關鍵字`Keywords_croatia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-201">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-202">函式`Func_croatia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-203">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="92b08-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-205">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-205">tax number</span></span>
  
<span data-ttu-id="92b08-206">稅務</span><span class="sxs-lookup"><span data-stu-id="92b08-206">tax</span></span>
  
<span data-ttu-id="92b08-207">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-207">tax id</span></span>
  
<span data-ttu-id="92b08-208">OID</span><span class="sxs-lookup"><span data-stu-id="92b08-208">oid</span></span>
  
<span data-ttu-id="92b08-209">oid #</span><span class="sxs-lookup"><span data-stu-id="92b08-209">oid#</span></span>
  
<span data-ttu-id="92b08-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="92b08-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="92b08-211">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="92b08-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="92b08-212">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-212">Format</span></span>

<span data-ttu-id="92b08-213">八位數與所指定的型態的其中一個字母</span><span class="sxs-lookup"><span data-stu-id="92b08-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-214">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-214">Pattern</span></span>

<span data-ttu-id="92b08-215">八位數和一個字母：</span><span class="sxs-lookup"><span data-stu-id="92b08-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="92b08-216">「 0 」</span><span class="sxs-lookup"><span data-stu-id="92b08-216">A "0"</span></span> 
    
- <span data-ttu-id="92b08-217">七位數</span><span class="sxs-lookup"><span data-stu-id="92b08-217">Seven digits</span></span>
    
- <span data-ttu-id="92b08-218">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="92b08-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-219">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-219">Checksum</span></span>

<span data-ttu-id="92b08-220">不適用</span><span class="sxs-lookup"><span data-stu-id="92b08-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-221">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-221">Definition</span></span>

<span data-ttu-id="92b08-222">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-223">函式`Func_cyprus_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-224">從關鍵字`Keywords_cyprus_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-225">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-226">函式`Func_cyprus_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="92b08-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-229">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-229">tax number</span></span>
  
<span data-ttu-id="92b08-230">稅務</span><span class="sxs-lookup"><span data-stu-id="92b08-230">tax</span></span>
  
<span data-ttu-id="92b08-231">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-231">tax id</span></span>
  
<span data-ttu-id="92b08-232">稅務識別程式碼</span><span class="sxs-lookup"><span data-stu-id="92b08-232">tax identification code</span></span>
  
<span data-ttu-id="92b08-233">tic</span><span class="sxs-lookup"><span data-stu-id="92b08-233">tic</span></span>
  
<span data-ttu-id="92b08-234">tic #</span><span class="sxs-lookup"><span data-stu-id="92b08-234">tic#</span></span>
  
<span data-ttu-id="92b08-235">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="92b08-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="92b08-236">ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ</span><span class="sxs-lookup"><span data-stu-id="92b08-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="92b08-237">ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="92b08-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="92b08-238">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="92b08-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="92b08-239">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-239">Format</span></span>

<span data-ttu-id="92b08-240">具有選用反斜線的九個或十位數</span><span class="sxs-lookup"><span data-stu-id="92b08-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-241">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-241">Pattern</span></span>

<span data-ttu-id="92b08-242">具有選用 backslashl 九個或十位數：</span><span class="sxs-lookup"><span data-stu-id="92b08-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="92b08-243">六位數</span><span class="sxs-lookup"><span data-stu-id="92b08-243">Six digits</span></span> 
    
- <span data-ttu-id="92b08-244">反斜線 （選用）</span><span class="sxs-lookup"><span data-stu-id="92b08-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="92b08-245">三或四位數</span><span class="sxs-lookup"><span data-stu-id="92b08-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-246">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-246">Checksum</span></span>

<span data-ttu-id="92b08-247">不適用</span><span class="sxs-lookup"><span data-stu-id="92b08-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-248">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-248">Definition</span></span>

<span data-ttu-id="92b08-249">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-250">規則運算式`Regex_czech_republic_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-251">從關鍵字`Keywords_czech_republic_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="92b08-252">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="92b08-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-254">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-254">tax number</span></span>
  
<span data-ttu-id="92b08-255">稅務</span><span class="sxs-lookup"><span data-stu-id="92b08-255">tax</span></span>
  
<span data-ttu-id="92b08-256">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-256">tax id</span></span>
  
<span data-ttu-id="92b08-257">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-257">personal number</span></span>
  
<span data-ttu-id="92b08-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="92b08-258">daňové číslo</span></span>
  
<span data-ttu-id="92b08-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="92b08-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="92b08-260">丹麥</span><span class="sxs-lookup"><span data-stu-id="92b08-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="92b08-261">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-261">Format</span></span>

<span data-ttu-id="92b08-262">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="92b08-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-263">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-263">Pattern</span></span>

<span data-ttu-id="92b08-264">10 位數包含 hyphenl:</span><span class="sxs-lookup"><span data-stu-id="92b08-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="92b08-265">會對應至 (DDMMYY) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="92b08-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="92b08-266">連字號</span><span class="sxs-lookup"><span data-stu-id="92b08-266">A hyphen</span></span>
    
- <span data-ttu-id="92b08-267">會對應至其中的第一個數字會對應至的出生世紀序號的四位數，最後一個數字會對應至個別的性別 （如 1 女 2 男以及即使女性奇數）</span><span class="sxs-lookup"><span data-stu-id="92b08-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-268">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-268">Checksum</span></span>

<span data-ttu-id="92b08-269">是</span><span class="sxs-lookup"><span data-stu-id="92b08-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-270">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-270">Definition</span></span>

<span data-ttu-id="92b08-271">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-272">函式`Func_denmark_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-273">從關鍵字`Keywords_denmark_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-274">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-275">函式`Func_denmark_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-276">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="92b08-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-278">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-278">tax number</span></span>
  
<span data-ttu-id="92b08-279">稅務</span><span class="sxs-lookup"><span data-stu-id="92b08-279">tax</span></span>
  
<span data-ttu-id="92b08-280">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-280">tax id</span></span>
  
<span data-ttu-id="92b08-281">cpr 數目</span><span class="sxs-lookup"><span data-stu-id="92b08-281">cpr number</span></span>
  
<span data-ttu-id="92b08-282">cpr #</span><span class="sxs-lookup"><span data-stu-id="92b08-282">cpr#</span></span>
  
<span data-ttu-id="92b08-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="92b08-283">skat nummer</span></span>
  
<span data-ttu-id="92b08-284">skat 識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="92b08-285">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="92b08-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="92b08-286">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-286">Format</span></span>

<span data-ttu-id="92b08-287">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="92b08-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-288">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-288">Pattern</span></span>

<span data-ttu-id="92b08-289">11 位數：</span><span class="sxs-lookup"><span data-stu-id="92b08-289">11 digits:</span></span>
  
-  <span data-ttu-id="92b08-290">會對應至性別和世紀的出生其中奇數的數字表示 1 女 2 男並偶數指出女性，如下所示的一個數字： 1，2 代表 19 世紀;3、 4 20 的 century;5，6 第 21 世紀</span><span class="sxs-lookup"><span data-stu-id="92b08-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="92b08-291">會對應至 (YYMMDD) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="92b08-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="92b08-292">會對應至分隔出生日期相同的人員序號的三位數</span><span class="sxs-lookup"><span data-stu-id="92b08-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="92b08-293">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-294">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-294">Checksum</span></span>

<span data-ttu-id="92b08-295">是</span><span class="sxs-lookup"><span data-stu-id="92b08-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-296">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-296">Definition</span></span>

<span data-ttu-id="92b08-297">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-298">函式`Func_estonia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-299">從關鍵字`Keywords_estonia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-300">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-301">函式`Func_estonia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-302">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="92b08-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-304">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-304">tax number</span></span>
  
<span data-ttu-id="92b08-305">稅務</span><span class="sxs-lookup"><span data-stu-id="92b08-305">tax</span></span>
  
<span data-ttu-id="92b08-306">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-306">tax id</span></span>
  
<span data-ttu-id="92b08-307">個人的程式碼</span><span class="sxs-lookup"><span data-stu-id="92b08-307">personal code</span></span>
  
<span data-ttu-id="92b08-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="92b08-308">maksunumber</span></span>
  
<span data-ttu-id="92b08-309">maksu 識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-309">maksu id</span></span>
  
<span data-ttu-id="92b08-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="92b08-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="92b08-311">芬蘭</span><span class="sxs-lookup"><span data-stu-id="92b08-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="92b08-312">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-312">Format</span></span>

<span data-ttu-id="92b08-313">字母的數字，11 個字元組合，以及加號與減號</span><span class="sxs-lookup"><span data-stu-id="92b08-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-314">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-314">Pattern</span></span>

<span data-ttu-id="92b08-315">字母的數字，11 個字元組合，以及加號與減號：</span><span class="sxs-lookup"><span data-stu-id="92b08-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="92b08-316">六位數</span><span class="sxs-lookup"><span data-stu-id="92b08-316">Six digits</span></span>
    
- <span data-ttu-id="92b08-317">下列其中之一： 加上加號、 減號或其中加號表示字母"A"（不區分大小寫） 之間 1800年 1899 年出生減號登入表示出生之間 1999 1900 年和"A"表示出生 2000年和之後</span><span class="sxs-lookup"><span data-stu-id="92b08-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="92b08-318">三位數</span><span class="sxs-lookup"><span data-stu-id="92b08-318">Three digits</span></span>
    
- <span data-ttu-id="92b08-319">一個字母或一個數字</span><span class="sxs-lookup"><span data-stu-id="92b08-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-320">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-320">Checksum</span></span>

<span data-ttu-id="92b08-321">是</span><span class="sxs-lookup"><span data-stu-id="92b08-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-322">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-322">Definition</span></span>

<span data-ttu-id="92b08-323">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-324">函式`Func_finland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-325">從關鍵字`Keywords_finland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-326">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-327">函式`Func_finland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-328">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="92b08-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-330">識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-330">identification number</span></span>
  
<span data-ttu-id="92b08-331">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-331">personal id</span></span>
  
<span data-ttu-id="92b08-332">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-332">identity number</span></span>
  
<span data-ttu-id="92b08-333">芬蘭國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-333">finnish national id number</span></span>
  
<span data-ttu-id="92b08-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="92b08-334">personalidnumber#</span></span>
  
<span data-ttu-id="92b08-335">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-335">national identification number</span></span>
  
<span data-ttu-id="92b08-336">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-336">id number</span></span>
  
<span data-ttu-id="92b08-337">國民身分證沒有。</span><span class="sxs-lookup"><span data-stu-id="92b08-337">national id no.</span></span>
  
<span data-ttu-id="92b08-338">國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-338">national id number</span></span>
  
<span data-ttu-id="92b08-339">識別碼不</span><span class="sxs-lookup"><span data-stu-id="92b08-339">id no</span></span>
  
<span data-ttu-id="92b08-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="92b08-340">tunnistenumero</span></span>
  
<span data-ttu-id="92b08-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="92b08-341">henkilötunnus</span></span>
  
<span data-ttu-id="92b08-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="92b08-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="92b08-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="92b08-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="92b08-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="92b08-344">identiteetti numero</span></span>
  
<span data-ttu-id="92b08-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="92b08-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="92b08-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="92b08-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="92b08-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="92b08-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="92b08-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="92b08-348">tunnusnumero</span></span>
  
<span data-ttu-id="92b08-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="92b08-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="92b08-350">法國</span><span class="sxs-lookup"><span data-stu-id="92b08-350">France</span></span>

### <a name="format"></a><span data-ttu-id="92b08-351">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-351">Format</span></span>

<span data-ttu-id="92b08-352">13 位數個人與實體的九位數</span><span class="sxs-lookup"><span data-stu-id="92b08-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-353">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-353">Pattern</span></span>

<span data-ttu-id="92b08-354">針對個人的 13 位數：</span><span class="sxs-lookup"><span data-stu-id="92b08-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="92b08-355">必須是 0、 1、 2 或 3 的一個數字</span><span class="sxs-lookup"><span data-stu-id="92b08-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="92b08-356">12 位數</span><span class="sxs-lookup"><span data-stu-id="92b08-356">12 digits</span></span>
    
<span data-ttu-id="92b08-357">實體的九位數</span><span class="sxs-lookup"><span data-stu-id="92b08-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="92b08-358">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-358">Checksum</span></span>

<span data-ttu-id="92b08-359">不適用</span><span class="sxs-lookup"><span data-stu-id="92b08-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-360">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-360">Definition</span></span>

<span data-ttu-id="92b08-361">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-362">函式`Func_france_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-363">從關鍵字`Keywords_france_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-364">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-365">函式`Func_france_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-366">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="92b08-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-368">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-368">tax identification number</span></span>
  
<span data-ttu-id="92b08-369">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-369">tax number</span></span>
  
<span data-ttu-id="92b08-370">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-370">tax id</span></span>
  
<span data-ttu-id="92b08-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="92b08-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="92b08-372">德國</span><span class="sxs-lookup"><span data-stu-id="92b08-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="92b08-373">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-373">Format</span></span>

<span data-ttu-id="92b08-374">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="92b08-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-375">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-375">Pattern</span></span>

<span data-ttu-id="92b08-376">11 位數：</span><span class="sxs-lookup"><span data-stu-id="92b08-376">11 digits :</span></span>
  
-  <span data-ttu-id="92b08-377">十位數</span><span class="sxs-lookup"><span data-stu-id="92b08-377">Ten digits</span></span> 
    
- <span data-ttu-id="92b08-378">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-379">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-379">Checksum</span></span>

<span data-ttu-id="92b08-380">是</span><span class="sxs-lookup"><span data-stu-id="92b08-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-381">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-381">Definition</span></span>

<span data-ttu-id="92b08-382">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-383">函式`Func_germany_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-384">從關鍵字`Keywords_germany_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-385">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-386">函式`Func_germany_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-387">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="92b08-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-389">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-389">tax number</span></span>
  
<span data-ttu-id="92b08-390">稅務否。</span><span class="sxs-lookup"><span data-stu-id="92b08-390">tax no.</span></span>
  
<span data-ttu-id="92b08-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="92b08-391">taxno#</span></span>
  
<span data-ttu-id="92b08-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="92b08-392">taxnumber#</span></span>
  
<span data-ttu-id="92b08-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="92b08-393">taxnumber</span></span>
  
<span data-ttu-id="92b08-394">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-394">tax id</span></span>
  
<span data-ttu-id="92b08-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="92b08-395">taxid#</span></span>
  
<span data-ttu-id="92b08-396">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-396">tax identification number</span></span>
  
<span data-ttu-id="92b08-397">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="92b08-397">tax identification no.</span></span>
  
<span data-ttu-id="92b08-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="92b08-398">steuernummer</span></span>
  
<span data-ttu-id="92b08-399">steuer 識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-399">steuer id</span></span>
  
<span data-ttu-id="92b08-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="92b08-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="92b08-401">希臘</span><span class="sxs-lookup"><span data-stu-id="92b08-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="92b08-402">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-402">Format</span></span>

<span data-ttu-id="92b08-403">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="92b08-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-404">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-404">Pattern</span></span>

<span data-ttu-id="92b08-405">九位數</span><span class="sxs-lookup"><span data-stu-id="92b08-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="92b08-406">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-406">Checksum</span></span>

<span data-ttu-id="92b08-407">不適用</span><span class="sxs-lookup"><span data-stu-id="92b08-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-408">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-408">Definition</span></span>

<span data-ttu-id="92b08-409">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-410">規則運算式`Regex_greece_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-411">從關鍵字`Keywords_greece_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="92b08-412">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="92b08-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-414">afm</span><span class="sxs-lookup"><span data-stu-id="92b08-414">afm</span></span>
  
<span data-ttu-id="92b08-415">錫</span><span class="sxs-lookup"><span data-stu-id="92b08-415">tin</span></span>
  
<span data-ttu-id="92b08-416">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="92b08-416">tax id no.</span></span>
  
<span data-ttu-id="92b08-417">不稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-417">tax id no</span></span>
  
<span data-ttu-id="92b08-418">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-418">tax identification number</span></span>
  
<span data-ttu-id="92b08-419">稅務登錄編號</span><span class="sxs-lookup"><span data-stu-id="92b08-419">tax registry number</span></span>
  
<span data-ttu-id="92b08-420">不稅務登錄。</span><span class="sxs-lookup"><span data-stu-id="92b08-420">tax registry no.</span></span>
  
<span data-ttu-id="92b08-421">afm #</span><span class="sxs-lookup"><span data-stu-id="92b08-421">afm#</span></span>
  
<span data-ttu-id="92b08-422">錫 #</span><span class="sxs-lookup"><span data-stu-id="92b08-422">tin#</span></span>
  
<span data-ttu-id="92b08-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="92b08-423">taxidno#</span></span>
  
<span data-ttu-id="92b08-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="92b08-424">taxregistryno#</span></span>
  
<span data-ttu-id="92b08-425">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="92b08-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="92b08-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="92b08-426">aφμ</span></span>
  
<span data-ttu-id="92b08-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="92b08-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="92b08-428">ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ。</span><span class="sxs-lookup"><span data-stu-id="92b08-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="92b08-429">ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="92b08-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="92b08-430">匈牙利</span><span class="sxs-lookup"><span data-stu-id="92b08-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="92b08-431">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-431">Format</span></span>

<span data-ttu-id="92b08-432">不含空格或分隔符號十位數</span><span class="sxs-lookup"><span data-stu-id="92b08-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-433">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-433">Pattern</span></span>

<span data-ttu-id="92b08-434">十位數：</span><span class="sxs-lookup"><span data-stu-id="92b08-434">Ten digits:</span></span>
  
-  <span data-ttu-id="92b08-435">必須是"8"的一個數字</span><span class="sxs-lookup"><span data-stu-id="92b08-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="92b08-436">會對應至日期之間的天數的五位數 01/01/1867年和個別的出生日期</span><span class="sxs-lookup"><span data-stu-id="92b08-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="92b08-437">會對應至數來區分個人在同一天出生巧產生的三位數</span><span class="sxs-lookup"><span data-stu-id="92b08-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="92b08-438">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-439">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-439">Checksum</span></span>

<span data-ttu-id="92b08-440">是</span><span class="sxs-lookup"><span data-stu-id="92b08-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-441">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-441">Definition</span></span>

<span data-ttu-id="92b08-442">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-443">函式`Func_hungary_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-444">從關鍵字`Keywords_hungary_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-445">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-446">函式`Func_hungary_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-447">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="92b08-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-449">匈牙利文的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="92b08-450">匈牙利文錫</span><span class="sxs-lookup"><span data-stu-id="92b08-450">hungarian tin</span></span>
  
<span data-ttu-id="92b08-451">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-451">tax id number</span></span>
  
<span data-ttu-id="92b08-452">vat 編號</span><span class="sxs-lookup"><span data-stu-id="92b08-452">vat number</span></span>
  
<span data-ttu-id="92b08-453">不稅務授權單位</span><span class="sxs-lookup"><span data-stu-id="92b08-453">tax authority no</span></span>
  
<span data-ttu-id="92b08-454">稅務識別碼稅務身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-454">tax id tax identity number</span></span>
  
<span data-ttu-id="92b08-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="92b08-455">taxidnumber#</span></span>
  
<span data-ttu-id="92b08-456">錫 #</span><span class="sxs-lookup"><span data-stu-id="92b08-456">tin#</span></span>
  
<span data-ttu-id="92b08-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="92b08-457">hungatiantin#</span></span>
  
<span data-ttu-id="92b08-458">不稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-458">tax identification no</span></span>
  
<span data-ttu-id="92b08-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="92b08-459">taxidno#</span></span>
  
<span data-ttu-id="92b08-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="92b08-460">adóazonosító szám</span></span>
  
<span data-ttu-id="92b08-461">adószám</span><span class="sxs-lookup"><span data-stu-id="92b08-461">adószám</span></span>
  
<span data-ttu-id="92b08-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="92b08-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="92b08-463">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="92b08-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="92b08-464">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-464">Format</span></span>

<span data-ttu-id="92b08-465">七位數後尾隨不含空格或分隔符號的字母</span><span class="sxs-lookup"><span data-stu-id="92b08-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-466">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-466">Pattern</span></span>

<span data-ttu-id="92b08-467">七位數後尾隨字母：</span><span class="sxs-lookup"><span data-stu-id="92b08-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="92b08-468">七位數</span><span class="sxs-lookup"><span data-stu-id="92b08-468">Seven digits</span></span> 
    
- <span data-ttu-id="92b08-469">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="92b08-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-470">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-470">Checksum</span></span>

<span data-ttu-id="92b08-471">不適用</span><span class="sxs-lookup"><span data-stu-id="92b08-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-472">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-472">Definition</span></span>

<span data-ttu-id="92b08-473">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-474">函式`Func_ireland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-475">從關鍵字`Keywords_ireland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-476">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-477">函式`Func_ireland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="92b08-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-480">公用服務沒有</span><span class="sxs-lookup"><span data-stu-id="92b08-480">public service no</span></span>
  
<span data-ttu-id="92b08-481">個人公用服務沒有</span><span class="sxs-lookup"><span data-stu-id="92b08-481">personal public service no</span></span>
  
<span data-ttu-id="92b08-482">pps 沒有</span><span class="sxs-lookup"><span data-stu-id="92b08-482">pps no</span></span>
  
<span data-ttu-id="92b08-483">個人服務否</span><span class="sxs-lookup"><span data-stu-id="92b08-483">personal service no</span></span>
  
<span data-ttu-id="92b08-484">pps service 否</span><span class="sxs-lookup"><span data-stu-id="92b08-484">pps service no</span></span>
  
<span data-ttu-id="92b08-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="92b08-485">ppsno#</span></span>
  
<span data-ttu-id="92b08-486">愛爾蘭 pps 沒有</span><span class="sxs-lookup"><span data-stu-id="92b08-486">irish pps no</span></span>
  
<span data-ttu-id="92b08-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="92b08-487">publicserviceno#</span></span>
  
<span data-ttu-id="92b08-488">個人公用服務號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-488">personal public service number</span></span>
  
<span data-ttu-id="92b08-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="92b08-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="92b08-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="92b08-490">pps uimh</span></span>
  
<span data-ttu-id="92b08-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="92b08-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="92b08-492">義大利</span><span class="sxs-lookup"><span data-stu-id="92b08-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="92b08-493">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-493">Format</span></span>

<span data-ttu-id="92b08-494">16 個字母和數字中指定的型態</span><span class="sxs-lookup"><span data-stu-id="92b08-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-495">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-495">Pattern</span></span>

<span data-ttu-id="92b08-496">16 個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="92b08-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="92b08-497">會對應到前三個母音系列名稱中的三個字母</span><span class="sxs-lookup"><span data-stu-id="92b08-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="92b08-498">會對應至第一、 第三個和第四個的三個字母母音在名字</span><span class="sxs-lookup"><span data-stu-id="92b08-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="92b08-499">會對應至最後一位數的出生年份的兩位數</span><span class="sxs-lookup"><span data-stu-id="92b08-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="92b08-500">會對應至出生的月份的一個數字 — 字母可用依字母順序，但只字母 A 到 E、 H、 L、 M、 P、 R 以 T 可用 （因此，一月是的而且年 10 月 R）</span><span class="sxs-lookup"><span data-stu-id="92b08-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="92b08-501">會對應至出生其中 40 加入的來區分從男生女生出生日期的月份日期的兩位數</span><span class="sxs-lookup"><span data-stu-id="92b08-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="92b08-502">會對應至特定出生人員 municipality 區域代碼的四位數 — 全國家/地區的代碼可用外部國家/地區</span><span class="sxs-lookup"><span data-stu-id="92b08-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="92b08-503">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-504">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-504">Checksum</span></span>

<span data-ttu-id="92b08-505">是</span><span class="sxs-lookup"><span data-stu-id="92b08-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-506">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-506">Definition</span></span>

<span data-ttu-id="92b08-507">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-508">函式`Func_italy_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-509">從關鍵字`Keywords_italy_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-510">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-511">函式`Func_italy_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-512">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="92b08-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-514">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-514">tax number</span></span>
  
<span data-ttu-id="92b08-515">稅務否。</span><span class="sxs-lookup"><span data-stu-id="92b08-515">tax no.</span></span>
  
<span data-ttu-id="92b08-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="92b08-516">taxno#</span></span>
  
<span data-ttu-id="92b08-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="92b08-517">taxnumber#</span></span>
  
<span data-ttu-id="92b08-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="92b08-518">taxnumber</span></span>
  
<span data-ttu-id="92b08-519">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-519">tax id</span></span>
  
<span data-ttu-id="92b08-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="92b08-520">taxid#</span></span>
  
<span data-ttu-id="92b08-521">會計年度的程式碼</span><span class="sxs-lookup"><span data-stu-id="92b08-521">fiscal code</span></span>
  
<span data-ttu-id="92b08-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="92b08-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="92b08-523">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="92b08-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="92b08-524">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-524">Format</span></span>

<span data-ttu-id="92b08-525">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="92b08-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-526">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-526">Pattern</span></span>

<span data-ttu-id="92b08-527">11 位數，代表所指定模式</span><span class="sxs-lookup"><span data-stu-id="92b08-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="92b08-528">會對應至 (DDMMYY) 出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="92b08-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="92b08-529">會對應至的出生其中"0"會對應至 19 世紀"1"會對應至 20 世紀，，"2"會對應至第 21 世紀世紀的一個數字</span><span class="sxs-lookup"><span data-stu-id="92b08-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="92b08-530">四位數</span><span class="sxs-lookup"><span data-stu-id="92b08-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-531">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-531">Checksum</span></span>

<span data-ttu-id="92b08-532">是</span><span class="sxs-lookup"><span data-stu-id="92b08-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-533">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-533">Definition</span></span>

<span data-ttu-id="92b08-534">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-535">函式`Func_latvia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-536">從關鍵字`Keywords_latvia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-537">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-538">函式`Func_latvia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-539">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="92b08-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-541">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-541">tax number</span></span>
  
<span data-ttu-id="92b08-542">稅務否。</span><span class="sxs-lookup"><span data-stu-id="92b08-542">tax no.</span></span>
  
<span data-ttu-id="92b08-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="92b08-543">taxno#</span></span>
  
<span data-ttu-id="92b08-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="92b08-544">taxnumber#</span></span>
  
<span data-ttu-id="92b08-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="92b08-545">taxnumber</span></span>
  
<span data-ttu-id="92b08-546">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-546">tax id</span></span>
  
<span data-ttu-id="92b08-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="92b08-547">taxid#</span></span>
  
<span data-ttu-id="92b08-548">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-548">tax identification number</span></span>
  
<span data-ttu-id="92b08-549">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="92b08-549">tax identification no.</span></span>
  
<span data-ttu-id="92b08-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="92b08-550">nodokļa numurs</span></span>
  
<span data-ttu-id="92b08-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="92b08-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="92b08-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="92b08-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="92b08-553">立陶宛</span><span class="sxs-lookup"><span data-stu-id="92b08-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="92b08-554">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-554">Format</span></span>

<span data-ttu-id="92b08-555">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="92b08-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-556">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-556">Pattern</span></span>

<span data-ttu-id="92b08-557">11 位數</span><span class="sxs-lookup"><span data-stu-id="92b08-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="92b08-558">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-558">Checksum</span></span>

<span data-ttu-id="92b08-559">不適用</span><span class="sxs-lookup"><span data-stu-id="92b08-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-560">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-560">Definition</span></span>

<span data-ttu-id="92b08-561">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-562">函式`Func_lithuania_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-563">從關鍵字`Keywords_lithuania_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-564">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-565">函式`Func_lithuania_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-566">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="92b08-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-568">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-568">tax number</span></span>
  
<span data-ttu-id="92b08-569">稅務否。</span><span class="sxs-lookup"><span data-stu-id="92b08-569">tax no.</span></span>
  
<span data-ttu-id="92b08-570">稅務否 #</span><span class="sxs-lookup"><span data-stu-id="92b08-570">tax no#</span></span>
  
<span data-ttu-id="92b08-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="92b08-571">taxnumber#</span></span>
  
<span data-ttu-id="92b08-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="92b08-572">taxnumber</span></span>
  
<span data-ttu-id="92b08-573">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-573">tax id</span></span>
  
<span data-ttu-id="92b08-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="92b08-574">taxid#</span></span>
  
<span data-ttu-id="92b08-575">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-575">tax identification number</span></span>
  
<span data-ttu-id="92b08-576">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="92b08-576">tax identification no.</span></span>
  
<span data-ttu-id="92b08-577">mokesčių 識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-577">mokesčių id</span></span>
  
<span data-ttu-id="92b08-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="92b08-578">mokesčių numeris</span></span>
  
<span data-ttu-id="92b08-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="92b08-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="92b08-580">盧森堡</span><span class="sxs-lookup"><span data-stu-id="92b08-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="92b08-581">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-581">Format</span></span>

<span data-ttu-id="92b08-582">不含空格或分隔符號的 13 位數</span><span class="sxs-lookup"><span data-stu-id="92b08-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-583">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-583">Pattern</span></span>

<span data-ttu-id="92b08-584">13 位數：</span><span class="sxs-lookup"><span data-stu-id="92b08-584">13 digits:</span></span>
  
-  <span data-ttu-id="92b08-585">11 位數</span><span class="sxs-lookup"><span data-stu-id="92b08-585">11 digits</span></span> 
    
- <span data-ttu-id="92b08-586">二位數檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-587">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-587">Checksum</span></span>

<span data-ttu-id="92b08-588">是</span><span class="sxs-lookup"><span data-stu-id="92b08-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-589">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-589">Definition</span></span>

<span data-ttu-id="92b08-590">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-591">函式`Func_luxemburg_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-592">從關鍵字`Keywords_luxemburg_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-593">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-594">函式`Func_luxemburg_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-595">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="92b08-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-597">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-597">tax number</span></span>
  
<span data-ttu-id="92b08-598">稅務否。</span><span class="sxs-lookup"><span data-stu-id="92b08-598">tax no.</span></span>
  
<span data-ttu-id="92b08-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="92b08-599">taxno#</span></span>
  
<span data-ttu-id="92b08-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="92b08-600">taxnumber#</span></span>
  
<span data-ttu-id="92b08-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="92b08-601">taxnumber</span></span>
  
<span data-ttu-id="92b08-602">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-602">tax id</span></span>
  
<span data-ttu-id="92b08-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="92b08-603">taxid#</span></span>
  
<span data-ttu-id="92b08-604">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-604">tax identification number</span></span>
  
<span data-ttu-id="92b08-605">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="92b08-605">tax identification no.</span></span>
  
<span data-ttu-id="92b08-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="92b08-606">steuernummer</span></span>
  
<span data-ttu-id="92b08-607">steuer 識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-607">steuer id</span></span>
  
<span data-ttu-id="92b08-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="92b08-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="92b08-609">馬爾他</span><span class="sxs-lookup"><span data-stu-id="92b08-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="92b08-610">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-610">Format</span></span>

<span data-ttu-id="92b08-611">針對馬爾他 nationals: 7 位數與所指定的型態的其中一個字母</span><span class="sxs-lookup"><span data-stu-id="92b08-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="92b08-612">非馬爾他文 nationals 和馬爾他實體： 9 位數</span><span class="sxs-lookup"><span data-stu-id="92b08-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-613">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-613">Pattern</span></span>

<span data-ttu-id="92b08-614">馬爾他 nationals: 7 位數和一個字母</span><span class="sxs-lookup"><span data-stu-id="92b08-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="92b08-615">七位數</span><span class="sxs-lookup"><span data-stu-id="92b08-615">Seven digits</span></span> 
    
- <span data-ttu-id="92b08-616">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="92b08-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="92b08-617">非馬爾他文 nationals 和馬爾他實體： 9 位數</span><span class="sxs-lookup"><span data-stu-id="92b08-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="92b08-618">九位數</span><span class="sxs-lookup"><span data-stu-id="92b08-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="92b08-619">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-619">Checksum</span></span>

<span data-ttu-id="92b08-620">不適用</span><span class="sxs-lookup"><span data-stu-id="92b08-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-621">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-621">Definition</span></span>

<span data-ttu-id="92b08-622">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-623">函式`Func_malta_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-624">從關鍵字`Keywords_malta_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-625">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-626">函式`Func_malta_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-627">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="92b08-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-629">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-629">tax number</span></span>
  
<span data-ttu-id="92b08-630">稅務否。</span><span class="sxs-lookup"><span data-stu-id="92b08-630">tax no.</span></span>
  
<span data-ttu-id="92b08-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="92b08-631">taxno#</span></span>
  
<span data-ttu-id="92b08-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="92b08-632">taxnumber#</span></span>
  
<span data-ttu-id="92b08-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="92b08-633">taxnumber</span></span>
  
<span data-ttu-id="92b08-634">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-634">tax id</span></span>
  
<span data-ttu-id="92b08-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="92b08-635">taxid#</span></span>
  
<span data-ttu-id="92b08-636">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-636">tax identification number</span></span>
  
<span data-ttu-id="92b08-637">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="92b08-637">tax identification no.</span></span>
  
<span data-ttu-id="92b08-638">numru 且 taxxa</span><span class="sxs-lookup"><span data-stu-id="92b08-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="92b08-639">識別碼且 taxxa</span><span class="sxs-lookup"><span data-stu-id="92b08-639">id tat-taxxa</span></span>
  
<span data-ttu-id="92b08-640">numru 東西 ' identifikazzjoni 且 taxxa</span><span class="sxs-lookup"><span data-stu-id="92b08-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="92b08-641">荷蘭</span><span class="sxs-lookup"><span data-stu-id="92b08-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="92b08-642">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-642">Format</span></span>

<span data-ttu-id="92b08-643">不含空格或分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="92b08-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-644">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-644">Pattern</span></span>

<span data-ttu-id="92b08-645">九位數</span><span class="sxs-lookup"><span data-stu-id="92b08-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="92b08-646">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-646">Checksum</span></span>

<span data-ttu-id="92b08-647">是</span><span class="sxs-lookup"><span data-stu-id="92b08-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-648">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-648">Definition</span></span>

<span data-ttu-id="92b08-649">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-650">函式`Func_netherlands_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-651">從關鍵字`Keywords_netherlands_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-652">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-653">函式`Func_netherlands_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-654">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="92b08-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-656">荷蘭稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="92b08-657">荷蘭稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-657">netherlands tax identification</span></span>
  
<span data-ttu-id="92b08-658">荷屬安的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="92b08-659">荷屬安的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-659">netherland's tax identification</span></span>
  
<span data-ttu-id="92b08-660">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-660">tax identification number</span></span>
  
<span data-ttu-id="92b08-661">荷蘭文的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-661">dutch tax id</span></span>
  
<span data-ttu-id="92b08-662">荷蘭文的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-662">dutch tax identification number</span></span>
  
<span data-ttu-id="92b08-663">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-663">tax id</span></span>
  
<span data-ttu-id="92b08-664">稅務識別碼 #</span><span class="sxs-lookup"><span data-stu-id="92b08-664">tax id#</span></span>
  
<span data-ttu-id="92b08-665">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-665">tax number</span></span>
  
<span data-ttu-id="92b08-666">稅務否 #</span><span class="sxs-lookup"><span data-stu-id="92b08-666">tax no#</span></span>
  
<span data-ttu-id="92b08-667">稅務 #</span><span class="sxs-lookup"><span data-stu-id="92b08-667">tax#</span></span>
  
<span data-ttu-id="92b08-668">錫</span><span class="sxs-lookup"><span data-stu-id="92b08-668">tin</span></span>
  
<span data-ttu-id="92b08-669">錫 #</span><span class="sxs-lookup"><span data-stu-id="92b08-669">tin#</span></span>
  
<span data-ttu-id="92b08-670">荷蘭錫</span><span class="sxs-lookup"><span data-stu-id="92b08-670">netherlands tin</span></span>
  
<span data-ttu-id="92b08-671">荷屬安的錫</span><span class="sxs-lookup"><span data-stu-id="92b08-671">netherland's tin</span></span>
  
<span data-ttu-id="92b08-672">荷蘭 belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="92b08-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="92b08-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="92b08-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="92b08-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="92b08-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="92b08-675">荷蘭 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="92b08-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="92b08-676">荷蘭 belasting 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="92b08-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="92b08-677">荷蘭 belastingnummer</span><span class="sxs-lookup"><span data-stu-id="92b08-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="92b08-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="92b08-678">btw nummer</span></span>
  
<span data-ttu-id="92b08-679">文拚字檢查 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="92b08-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="92b08-680">波蘭</span><span class="sxs-lookup"><span data-stu-id="92b08-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="92b08-681">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-681">Format</span></span>

<span data-ttu-id="92b08-682">不含空格或分隔符號十一份數字</span><span class="sxs-lookup"><span data-stu-id="92b08-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-683">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-683">Pattern</span></span>

<span data-ttu-id="92b08-684">十一份數字</span><span class="sxs-lookup"><span data-stu-id="92b08-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="92b08-685">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-685">Checksum</span></span>

<span data-ttu-id="92b08-686">是</span><span class="sxs-lookup"><span data-stu-id="92b08-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-687">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-687">Definition</span></span>

<span data-ttu-id="92b08-688">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-689">函式`Func_poland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-690">從關鍵字`Keywords_poland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-691">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-692">函式`Func_poland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-693">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="92b08-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-695">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-695">tax number</span></span>
  
<span data-ttu-id="92b08-696">稅務否。</span><span class="sxs-lookup"><span data-stu-id="92b08-696">tax no.</span></span>
  
<span data-ttu-id="92b08-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="92b08-697">taxno#</span></span>
  
<span data-ttu-id="92b08-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="92b08-698">taxnumber#</span></span>
  
<span data-ttu-id="92b08-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="92b08-699">taxnumber</span></span>
  
<span data-ttu-id="92b08-700">nip</span><span class="sxs-lookup"><span data-stu-id="92b08-700">nip</span></span>
  
<span data-ttu-id="92b08-701">nip #</span><span class="sxs-lookup"><span data-stu-id="92b08-701">nip#</span></span>
  
<span data-ttu-id="92b08-702">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-702">tax id</span></span>
  
<span data-ttu-id="92b08-703">稅務識別碼 #</span><span class="sxs-lookup"><span data-stu-id="92b08-703">tax id#</span></span>
  
<span data-ttu-id="92b08-704">nip 識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-704">nip id</span></span>
  
<span data-ttu-id="92b08-705">nip 識別碼 #</span><span class="sxs-lookup"><span data-stu-id="92b08-705">nip id#</span></span>
  
<span data-ttu-id="92b08-706">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-706">tax identification number</span></span>
  
<span data-ttu-id="92b08-707">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="92b08-707">tax identification no.</span></span>
  
<span data-ttu-id="92b08-708">vat 編號</span><span class="sxs-lookup"><span data-stu-id="92b08-708">vat number</span></span>
  
<span data-ttu-id="92b08-709">vat 否。</span><span class="sxs-lookup"><span data-stu-id="92b08-709">vat no.</span></span>
  
<span data-ttu-id="92b08-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="92b08-710">vatno#</span></span>
  
<span data-ttu-id="92b08-711">vat 識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-711">vat id</span></span>
  
<span data-ttu-id="92b08-712">vat id #</span><span class="sxs-lookup"><span data-stu-id="92b08-712">vat id#</span></span>
  
<span data-ttu-id="92b08-713">數目 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="92b08-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="92b08-714">polski 數目 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="92b08-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="92b08-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="92b08-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="92b08-716">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="92b08-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="92b08-717">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-717">Format</span></span>

<span data-ttu-id="92b08-718">不含空格或分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="92b08-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-719">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-719">Pattern</span></span>

<span data-ttu-id="92b08-720">九位數</span><span class="sxs-lookup"><span data-stu-id="92b08-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="92b08-721">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-721">Checksum</span></span>

<span data-ttu-id="92b08-722">是</span><span class="sxs-lookup"><span data-stu-id="92b08-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-723">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-723">Definition</span></span>

<span data-ttu-id="92b08-724">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-725">函式`Func_portugal_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-726">從關鍵字`Keywords_portugal_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-727">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-728">函式`Func_portugal_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-729">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="92b08-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-731">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-731">tax number</span></span>
  
<span data-ttu-id="92b08-732">稅務否。</span><span class="sxs-lookup"><span data-stu-id="92b08-732">tax no.</span></span>
  
<span data-ttu-id="92b08-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="92b08-733">taxno#</span></span>
  
<span data-ttu-id="92b08-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="92b08-734">taxnumber#</span></span>
  
<span data-ttu-id="92b08-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="92b08-735">taxnumber</span></span>
  
<span data-ttu-id="92b08-736">n 如果</span><span class="sxs-lookup"><span data-stu-id="92b08-736">nif</span></span>
  
<span data-ttu-id="92b08-737">n 如果 #</span><span class="sxs-lookup"><span data-stu-id="92b08-737">nif#</span></span>
  
<span data-ttu-id="92b08-738">numero 會計</span><span class="sxs-lookup"><span data-stu-id="92b08-738">numero fiscal</span></span>
  
<span data-ttu-id="92b08-739">número de identificação 會計</span><span class="sxs-lookup"><span data-stu-id="92b08-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="92b08-740">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="92b08-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="92b08-741">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-741">Format</span></span>

<span data-ttu-id="92b08-742">不含空格或分隔符號的 13 位數</span><span class="sxs-lookup"><span data-stu-id="92b08-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-743">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-743">Pattern</span></span>

<span data-ttu-id="92b08-744">13 位數</span><span class="sxs-lookup"><span data-stu-id="92b08-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="92b08-745">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-745">Checksum</span></span>

<span data-ttu-id="92b08-746">不適用</span><span class="sxs-lookup"><span data-stu-id="92b08-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-747">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-747">Definition</span></span>

<span data-ttu-id="92b08-748">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-749">規則運算式`Regex_romania_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-750">從關鍵字`Keywords_romania_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="92b08-751">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="92b08-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-753">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-753">tax id</span></span>
  
<span data-ttu-id="92b08-754">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-754">tax id number</span></span>
  
<span data-ttu-id="92b08-755">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="92b08-755">tax file no</span></span>
  
<span data-ttu-id="92b08-756">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="92b08-756">tax file number</span></span>
  
<span data-ttu-id="92b08-757">稅務否</span><span class="sxs-lookup"><span data-stu-id="92b08-757">tax no</span></span>
  
<span data-ttu-id="92b08-758">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-758">tax number</span></span>
  
<span data-ttu-id="92b08-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="92b08-759">taxid#</span></span>
  
<span data-ttu-id="92b08-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="92b08-760">taxno#</span></span>
  
<span data-ttu-id="92b08-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="92b08-761">id-ul taxei</span></span>
  
<span data-ttu-id="92b08-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="92b08-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="92b08-763">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="92b08-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="92b08-764">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-764">Format</span></span>

<span data-ttu-id="92b08-765">不含空格或分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="92b08-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-766">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-766">Pattern</span></span>

<span data-ttu-id="92b08-767">10 位數</span><span class="sxs-lookup"><span data-stu-id="92b08-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="92b08-768">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-768">Checksum</span></span>

<span data-ttu-id="92b08-769">不適用</span><span class="sxs-lookup"><span data-stu-id="92b08-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-770">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-770">Definition</span></span>

<span data-ttu-id="92b08-771">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-772">規則運算式`Regex_slovakia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-773">從關鍵字`Keywords_slovakia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="92b08-774">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="92b08-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-776">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-776">tax id</span></span>
  
<span data-ttu-id="92b08-777">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-777">tax id number</span></span>
  
<span data-ttu-id="92b08-778">鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-778">tin id</span></span>
  
<span data-ttu-id="92b08-779">鐵皮否</span><span class="sxs-lookup"><span data-stu-id="92b08-779">tin no</span></span>
  
<span data-ttu-id="92b08-780">斯洛伐克鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-780">slovakian tin id</span></span>
  
<span data-ttu-id="92b08-781">錫</span><span class="sxs-lookup"><span data-stu-id="92b08-781">tin</span></span>
  
<span data-ttu-id="92b08-782">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="92b08-782">tax file no</span></span>
  
<span data-ttu-id="92b08-783">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="92b08-783">tax file number</span></span>
  
<span data-ttu-id="92b08-784">稅務否</span><span class="sxs-lookup"><span data-stu-id="92b08-784">tax no</span></span>
  
<span data-ttu-id="92b08-785">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-785">tax number</span></span>
  
<span data-ttu-id="92b08-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="92b08-786">taxid#</span></span>
  
<span data-ttu-id="92b08-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="92b08-787">taxno#</span></span>
  
<span data-ttu-id="92b08-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="92b08-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="92b08-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="92b08-789">daňové číslo</span></span>
  
<span data-ttu-id="92b08-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="92b08-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="92b08-791">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="92b08-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="92b08-792">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-792">Format</span></span>

<span data-ttu-id="92b08-793">不含空格或分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="92b08-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-794">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-794">Pattern</span></span>

<span data-ttu-id="92b08-795">八位數</span><span class="sxs-lookup"><span data-stu-id="92b08-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="92b08-796">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-796">Checksum</span></span>

<span data-ttu-id="92b08-797">是</span><span class="sxs-lookup"><span data-stu-id="92b08-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-798">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-798">Definition</span></span>

<span data-ttu-id="92b08-799">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-800">函式`Func_slovenia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-801">從關鍵字`Keywords_slovenia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-802">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-803">函式`Func_slovenia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-804">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="92b08-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-806">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-806">tax id</span></span>
  
<span data-ttu-id="92b08-807">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-807">tax id number</span></span>
  
<span data-ttu-id="92b08-808">鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-808">tin id</span></span>
  
<span data-ttu-id="92b08-809">鐵皮否</span><span class="sxs-lookup"><span data-stu-id="92b08-809">tin no</span></span>
  
<span data-ttu-id="92b08-810">斯洛維尼亞文鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-810">slovenian tin id</span></span>
  
<span data-ttu-id="92b08-811">錫</span><span class="sxs-lookup"><span data-stu-id="92b08-811">tin</span></span>
  
<span data-ttu-id="92b08-812">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="92b08-812">tax file no</span></span>
  
<span data-ttu-id="92b08-813">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="92b08-813">tax file number</span></span>
  
<span data-ttu-id="92b08-814">稅務否</span><span class="sxs-lookup"><span data-stu-id="92b08-814">tax no</span></span>
  
<span data-ttu-id="92b08-815">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-815">tax number</span></span>
  
<span data-ttu-id="92b08-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="92b08-816">taxid#</span></span>
  
<span data-ttu-id="92b08-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="92b08-817">taxno#</span></span>
  
<span data-ttu-id="92b08-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="92b08-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="92b08-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="92b08-819">davčna številka</span></span>
  
<span data-ttu-id="92b08-820">Številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="92b08-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="92b08-821">西班牙</span><span class="sxs-lookup"><span data-stu-id="92b08-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="92b08-822">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-822">Format</span></span>

<span data-ttu-id="92b08-823">7 或 8 位數與所指定的型態的一或兩個字母</span><span class="sxs-lookup"><span data-stu-id="92b08-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-824">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-824">Pattern</span></span>

<span data-ttu-id="92b08-825">西班牙文自然人西班牙國民身分證與：</span><span class="sxs-lookup"><span data-stu-id="92b08-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="92b08-826">八位數</span><span class="sxs-lookup"><span data-stu-id="92b08-826">Eight digits</span></span> 
    
- <span data-ttu-id="92b08-827">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="92b08-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="92b08-828">非駐留西班牙人沒有西班牙國民身分證</span><span class="sxs-lookup"><span data-stu-id="92b08-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="92b08-829">一個大寫字母"L"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="92b08-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="92b08-830">七位數</span><span class="sxs-lookup"><span data-stu-id="92b08-830">Seven digits</span></span>
    
- <span data-ttu-id="92b08-831">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="92b08-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="92b08-832">[] 下的保留天數 14 年沒有西班牙國民身分證駐留西班牙人：</span><span class="sxs-lookup"><span data-stu-id="92b08-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="92b08-833">一個大寫字母"K"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="92b08-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="92b08-834">七位數</span><span class="sxs-lookup"><span data-stu-id="92b08-834">Seven digits</span></span> 
    
- <span data-ttu-id="92b08-835">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="92b08-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="92b08-836">外國人與因此識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="92b08-837">一個大寫也就是字母 「 X 」、 「 Y"或"Z"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="92b08-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="92b08-838">七位數</span><span class="sxs-lookup"><span data-stu-id="92b08-838">Seven digits</span></span>
    
- <span data-ttu-id="92b08-839">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="92b08-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="92b08-840">外國人沒有因此識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="92b08-841">一個大寫字母，為 「 M 」 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="92b08-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="92b08-842">七位數</span><span class="sxs-lookup"><span data-stu-id="92b08-842">Seven digits</span></span>
    
- <span data-ttu-id="92b08-843">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="92b08-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="92b08-844">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-844">Checksum</span></span>

<span data-ttu-id="92b08-845">是</span><span class="sxs-lookup"><span data-stu-id="92b08-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-846">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-846">Definition</span></span>

<span data-ttu-id="92b08-847">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-848">函式`Func_spain_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-849">從關鍵字`Keywords_spain_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-850">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-851">函式`Func_spain_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-852">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="92b08-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-854">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-854">tax id</span></span>
  
<span data-ttu-id="92b08-855">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-855">tax id number</span></span>
  
<span data-ttu-id="92b08-856">cif 識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-856">cif id</span></span>
  
<span data-ttu-id="92b08-857">cif 沒有</span><span class="sxs-lookup"><span data-stu-id="92b08-857">cif no</span></span>
  
<span data-ttu-id="92b08-858">西班牙文的 cif 識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-858">spanish cif id</span></span>
  
<span data-ttu-id="92b08-859">cif</span><span class="sxs-lookup"><span data-stu-id="92b08-859">cif</span></span>
  
<span data-ttu-id="92b08-860">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="92b08-860">tax file no</span></span>
  
<span data-ttu-id="92b08-861">西班牙文的 cif 數目</span><span class="sxs-lookup"><span data-stu-id="92b08-861">spanish cif number</span></span>
  
<span data-ttu-id="92b08-862">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="92b08-862">tax file number</span></span>
  
<span data-ttu-id="92b08-863">西班牙文的 cif 沒有</span><span class="sxs-lookup"><span data-stu-id="92b08-863">spanish cif no</span></span>
  
<span data-ttu-id="92b08-864">稅務否</span><span class="sxs-lookup"><span data-stu-id="92b08-864">tax no</span></span>
  
<span data-ttu-id="92b08-865">稅務編號</span><span class="sxs-lookup"><span data-stu-id="92b08-865">tax number</span></span>
  
<span data-ttu-id="92b08-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="92b08-866">taxid#</span></span>
  
<span data-ttu-id="92b08-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="92b08-867">taxno#</span></span>
  
<span data-ttu-id="92b08-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="92b08-868">cifid#</span></span>
  
<span data-ttu-id="92b08-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="92b08-869">spanishcifid#</span></span>
  
<span data-ttu-id="92b08-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="92b08-870">spanishcifno#</span></span>
  
<span data-ttu-id="92b08-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="92b08-871">número de contribuyente</span></span>
  
<span data-ttu-id="92b08-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="92b08-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="92b08-873">número de identificación 會計</span><span class="sxs-lookup"><span data-stu-id="92b08-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="92b08-874">cif número</span><span class="sxs-lookup"><span data-stu-id="92b08-874">cif número</span></span>
  
<span data-ttu-id="92b08-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="92b08-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="92b08-876">瑞典</span><span class="sxs-lookup"><span data-stu-id="92b08-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="92b08-877">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-877">Format</span></span>

<span data-ttu-id="92b08-878">十個數字和中指定的型態的符號</span><span class="sxs-lookup"><span data-stu-id="92b08-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-879">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-879">Pattern</span></span>

<span data-ttu-id="92b08-880">十個數字和符號：</span><span class="sxs-lookup"><span data-stu-id="92b08-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="92b08-881">會對應至 (YYMMDD) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="92b08-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="92b08-882">加號、 減號或反斜線</span><span class="sxs-lookup"><span data-stu-id="92b08-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="92b08-883">請識別的三位數數字唯一的位置：</span><span class="sxs-lookup"><span data-stu-id="92b08-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="92b08-884">發行之前 1990年數字，如第七個和第八個數字識別出生或 foreign-born 人員郡</span><span class="sxs-lookup"><span data-stu-id="92b08-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="92b08-885">在第九個位置的數字，表示女性 1 女 2 男或甚至是任一奇數性別</span><span class="sxs-lookup"><span data-stu-id="92b08-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="92b08-886">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="92b08-887">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-887">Checksum</span></span>

<span data-ttu-id="92b08-888">是</span><span class="sxs-lookup"><span data-stu-id="92b08-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-889">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-889">Definition</span></span>

<span data-ttu-id="92b08-890">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-891">函式`Func_sweden_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-892">從關鍵字`Keywords_sweden_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="92b08-893">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-894">函式`Func_sweden_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="92b08-895">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="92b08-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-897">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-897">tax id</span></span>
  
<span data-ttu-id="92b08-898">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="92b08-898">tax id no.</span></span>
  
<span data-ttu-id="92b08-899">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-899">tax id number</span></span>
  
<span data-ttu-id="92b08-900">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-900">tax identification</span></span>
  
<span data-ttu-id="92b08-901">稅務識別 #</span><span class="sxs-lookup"><span data-stu-id="92b08-901">tax identification#</span></span>
  
<span data-ttu-id="92b08-902">稅務否。</span><span class="sxs-lookup"><span data-stu-id="92b08-902">tax no.</span></span>
  
<span data-ttu-id="92b08-903">稅務 #</span><span class="sxs-lookup"><span data-stu-id="92b08-903">tax#</span></span>
  
<span data-ttu-id="92b08-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="92b08-904">taxid#</span></span>
  
<span data-ttu-id="92b08-905">稅務檔案</span><span class="sxs-lookup"><span data-stu-id="92b08-905">tax file</span></span>
  
<span data-ttu-id="92b08-906">不稅務檔案。</span><span class="sxs-lookup"><span data-stu-id="92b08-906">tax file no.</span></span>
  
<span data-ttu-id="92b08-907">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-907">personal id number</span></span>
  
<span data-ttu-id="92b08-908">skatt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="92b08-908">skatt id nummer</span></span>
  
<span data-ttu-id="92b08-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="92b08-909">skatt identifikation</span></span>
  
<span data-ttu-id="92b08-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="92b08-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="92b08-911">英國</span><span class="sxs-lookup"><span data-stu-id="92b08-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="92b08-912">格式</span><span class="sxs-lookup"><span data-stu-id="92b08-912">Format</span></span>

<span data-ttu-id="92b08-913">如果沒有空格和分隔符號的唯一 Taxpayer 參照 (UTR): 10 位數</span><span class="sxs-lookup"><span data-stu-id="92b08-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="92b08-914">國家保險號碼 (NINO): 如需詳細資訊，請參閱區段 」 英國</span><span class="sxs-lookup"><span data-stu-id="92b08-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="92b08-915">國家保險號碼 (NINO) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="92b08-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="92b08-916">模式</span><span class="sxs-lookup"><span data-stu-id="92b08-916">Pattern</span></span>

<span data-ttu-id="92b08-917">唯一 Taxpayer 參照 (UTR): 10 位數</span><span class="sxs-lookup"><span data-stu-id="92b08-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="92b08-918">國家保險號碼 (NINO): 如需詳細資訊，請參閱區段 」 英國</span><span class="sxs-lookup"><span data-stu-id="92b08-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="92b08-919">國家保險號碼 (NINO) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="92b08-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="92b08-920">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="92b08-920">Checksum</span></span>

<span data-ttu-id="92b08-921">是</span><span class="sxs-lookup"><span data-stu-id="92b08-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="92b08-922">定義</span><span class="sxs-lookup"><span data-stu-id="92b08-922">Definition</span></span>

<span data-ttu-id="92b08-923">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="92b08-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="92b08-924">函式`Func_uk_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="92b08-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="92b08-925">從關鍵字`Keywords_uk_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="92b08-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="92b08-926">關鍵字</span><span class="sxs-lookup"><span data-stu-id="92b08-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="92b08-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="92b08-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="92b08-928">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-928">tax id</span></span>
  
<span data-ttu-id="92b08-929">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="92b08-929">tax id no.</span></span>
  
<span data-ttu-id="92b08-930">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="92b08-930">tax id number</span></span>
  
<span data-ttu-id="92b08-931">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="92b08-931">tax identification</span></span>
  
<span data-ttu-id="92b08-932">稅務識別 #</span><span class="sxs-lookup"><span data-stu-id="92b08-932">tax identification#</span></span>
  
<span data-ttu-id="92b08-933">稅務否。</span><span class="sxs-lookup"><span data-stu-id="92b08-933">tax no.</span></span>
  
<span data-ttu-id="92b08-934">稅務 #</span><span class="sxs-lookup"><span data-stu-id="92b08-934">tax#</span></span>
  
<span data-ttu-id="92b08-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="92b08-935">taxid#</span></span>
  
<span data-ttu-id="92b08-936">稅務檔案</span><span class="sxs-lookup"><span data-stu-id="92b08-936">tax file</span></span>
  
<span data-ttu-id="92b08-937">不稅務檔案。</span><span class="sxs-lookup"><span data-stu-id="92b08-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="92b08-938">另請參閱</span><span class="sxs-lookup"><span data-stu-id="92b08-938">See also</span></span>

[<span data-ttu-id="92b08-939">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="92b08-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

