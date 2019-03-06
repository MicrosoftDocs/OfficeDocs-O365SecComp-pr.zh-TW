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
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410908"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="e0fc7-104">歐盟稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-104">EU Tax Identification Number</span></span>

<span data-ttu-id="e0fc7-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟稅務識別號碼 （錫） 敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="e0fc7-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="e0fc7-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="e0fc7-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-108">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-108">Format</span></span>

<span data-ttu-id="e0fc7-109">選擇性連字號和正斜線的九位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-110">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-110">Pattern</span></span>

<span data-ttu-id="e0fc7-111">選擇性連字號和正斜線的九位數：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="e0fc7-112">兩位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-112">Two digits</span></span> 
    
- <span data-ttu-id="e0fc7-113">連字號 （選用）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="e0fc7-114">三位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-114">Three digits</span></span>
    
- <span data-ttu-id="e0fc7-115">正斜線 （選用）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="e0fc7-116">四位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-117">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-117">Checksum</span></span>

<span data-ttu-id="e0fc7-118">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-119">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-119">Definition</span></span>

<span data-ttu-id="e0fc7-120">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-121">函式`Func_austria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-122">從關鍵字`Keywords_austria_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-123">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-124">函式`Func_austria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-125">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="e0fc7-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-127">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-127">tax number</span></span>
  
<span data-ttu-id="e0fc7-128">number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-128">number</span></span>
  
<span data-ttu-id="e0fc7-129">稅務登記號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-129">tax registration number</span></span>
  
<span data-ttu-id="e0fc7-130">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-130">tax id</span></span>
  
<span data-ttu-id="e0fc7-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-131">st.nr.</span></span>
  
<span data-ttu-id="e0fc7-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="e0fc7-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="e0fc7-133">比利時</span><span class="sxs-lookup"><span data-stu-id="e0fc7-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-134">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-134">Format</span></span>

<span data-ttu-id="e0fc7-135">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-136">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-136">Pattern</span></span>

<span data-ttu-id="e0fc7-137">11 位數：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-137">11 digits:</span></span>
  
- <span data-ttu-id="e0fc7-138">兩位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-138">Two digits</span></span>
    
- <span data-ttu-id="e0fc7-139">「 0 」 或者 「 1 」</span><span class="sxs-lookup"><span data-stu-id="e0fc7-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="e0fc7-140">一位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-140">One digit</span></span>
    
- <span data-ttu-id="e0fc7-141">"0"或"1"或"2"或者"3"</span><span class="sxs-lookup"><span data-stu-id="e0fc7-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="e0fc7-142">六位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-143">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-143">Checksum</span></span>

<span data-ttu-id="e0fc7-144">不適用</span><span class="sxs-lookup"><span data-stu-id="e0fc7-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-145">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-145">Definition</span></span>

<span data-ttu-id="e0fc7-146">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-147">規則運算式`Regex_belgium_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-148">從關鍵字`Keywords_belgium_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e0fc7-149">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="e0fc7-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-151">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-151">tax number</span></span>
  
<span data-ttu-id="e0fc7-152">國民登記號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-152">national registration number</span></span>
  
<span data-ttu-id="e0fc7-153">稅務登記號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-153">tax registration number</span></span>
  
<span data-ttu-id="e0fc7-154">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-154">tax id</span></span>
  
<span data-ttu-id="e0fc7-155">n 如果</span><span class="sxs-lookup"><span data-stu-id="e0fc7-155">nif</span></span>
  
<span data-ttu-id="e0fc7-156">n 如果 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-156">nif#</span></span>
  
<span data-ttu-id="e0fc7-157">numéro de registre 國際電話</span><span class="sxs-lookup"><span data-stu-id="e0fc7-157">numéro de registre national</span></span>
  
<span data-ttu-id="e0fc7-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="e0fc7-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="e0fc7-159">保加利亞</span><span class="sxs-lookup"><span data-stu-id="e0fc7-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-160">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-160">Format</span></span>

<span data-ttu-id="e0fc7-161">如果沒有空格和分隔符號十位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-162">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-162">Pattern</span></span>

<span data-ttu-id="e0fc7-163">10 位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e0fc7-164">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-164">Checksum</span></span>

<span data-ttu-id="e0fc7-165">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-166">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-166">Definition</span></span>

<span data-ttu-id="e0fc7-167">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-168">函式`Func_bulgaria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-169">從關鍵字`Keywords_bulgaria_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-170">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-171">函式`Func_bulgaria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-172">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="e0fc7-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-174">bucn</span><span class="sxs-lookup"><span data-stu-id="e0fc7-174">bucn</span></span>
  
<span data-ttu-id="e0fc7-175">統一民事數目</span><span class="sxs-lookup"><span data-stu-id="e0fc7-175">uniform civil number</span></span>
  
<span data-ttu-id="e0fc7-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-176">bucn#</span></span>
  
<span data-ttu-id="e0fc7-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="e0fc7-178">統一民事識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-178">uniform civil id</span></span>
  
<span data-ttu-id="e0fc7-179">統一民事否</span><span class="sxs-lookup"><span data-stu-id="e0fc7-179">uniform civil no</span></span>
  
<span data-ttu-id="e0fc7-180">egn</span><span class="sxs-lookup"><span data-stu-id="e0fc7-180">egn</span></span>
  
<span data-ttu-id="e0fc7-181">保加利亞文統一民事數目</span><span class="sxs-lookup"><span data-stu-id="e0fc7-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="e0fc7-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-182">uniformcivilno#</span></span>
  
<span data-ttu-id="e0fc7-183">egn #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-183">egn#</span></span>
  
<span data-ttu-id="e0fc7-184">УНИФОРМ ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="e0fc7-184">униформ граждански номер</span></span>
  
<span data-ttu-id="e0fc7-185">Униформ 識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-185">униформ id</span></span>
  
<span data-ttu-id="e0fc7-186">Униформ граждански 識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-186">униформ граждански id</span></span>
  
<span data-ttu-id="e0fc7-187">УНИФОРМ ГРАЖДАНСКИ НЕ</span><span class="sxs-lookup"><span data-stu-id="e0fc7-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="e0fc7-188">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="e0fc7-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-189">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-189">Format</span></span>

<span data-ttu-id="e0fc7-190">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-191">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-191">Pattern</span></span>

<span data-ttu-id="e0fc7-192">11 位數：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-192">11 digits:</span></span>
  
- <span data-ttu-id="e0fc7-193">十位數，隨機選擇</span><span class="sxs-lookup"><span data-stu-id="e0fc7-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="e0fc7-194">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-195">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-195">Checksum</span></span>

<span data-ttu-id="e0fc7-196">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-197">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-197">Definition</span></span>

<span data-ttu-id="e0fc7-198">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-199">函式`Func_croatia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-200">從關鍵字`Keywords_croatia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-201">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-202">函式`Func_croatia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-203">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="e0fc7-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-205">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-205">tax number</span></span>
  
<span data-ttu-id="e0fc7-206">稅務</span><span class="sxs-lookup"><span data-stu-id="e0fc7-206">tax</span></span>
  
<span data-ttu-id="e0fc7-207">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-207">tax id</span></span>
  
<span data-ttu-id="e0fc7-208">OID</span><span class="sxs-lookup"><span data-stu-id="e0fc7-208">oid</span></span>
  
<span data-ttu-id="e0fc7-209">oid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-209">oid#</span></span>
  
<span data-ttu-id="e0fc7-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="e0fc7-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="e0fc7-211">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="e0fc7-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-212">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-212">Format</span></span>

<span data-ttu-id="e0fc7-213">八位數與所指定的型態的其中一個字母</span><span class="sxs-lookup"><span data-stu-id="e0fc7-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-214">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-214">Pattern</span></span>

<span data-ttu-id="e0fc7-215">八位數和一個字母：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="e0fc7-216">「 0 」</span><span class="sxs-lookup"><span data-stu-id="e0fc7-216">A "0"</span></span> 
    
- <span data-ttu-id="e0fc7-217">七位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-217">Seven digits</span></span>
    
- <span data-ttu-id="e0fc7-218">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-219">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-219">Checksum</span></span>

<span data-ttu-id="e0fc7-220">不適用</span><span class="sxs-lookup"><span data-stu-id="e0fc7-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-221">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-221">Definition</span></span>

<span data-ttu-id="e0fc7-222">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-223">函式`Func_cyprus_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-224">從關鍵字`Keywords_cyprus_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-225">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-226">函式`Func_cyprus_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="e0fc7-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-229">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-229">tax number</span></span>
  
<span data-ttu-id="e0fc7-230">稅務</span><span class="sxs-lookup"><span data-stu-id="e0fc7-230">tax</span></span>
  
<span data-ttu-id="e0fc7-231">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-231">tax id</span></span>
  
<span data-ttu-id="e0fc7-232">稅務識別程式碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-232">tax identification code</span></span>
  
<span data-ttu-id="e0fc7-233">tic</span><span class="sxs-lookup"><span data-stu-id="e0fc7-233">tic</span></span>
  
<span data-ttu-id="e0fc7-234">tic #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-234">tic#</span></span>
  
<span data-ttu-id="e0fc7-235">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="e0fc7-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="e0fc7-236">ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ</span><span class="sxs-lookup"><span data-stu-id="e0fc7-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="e0fc7-237">ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="e0fc7-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="e0fc7-238">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="e0fc7-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-239">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-239">Format</span></span>

<span data-ttu-id="e0fc7-240">具有選用反斜線的九個或十位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-241">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-241">Pattern</span></span>

<span data-ttu-id="e0fc7-242">具有選用 backslashl 九個或十位數：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="e0fc7-243">六位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-243">Six digits</span></span> 
    
- <span data-ttu-id="e0fc7-244">反斜線 （選用）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="e0fc7-245">三或四位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-246">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-246">Checksum</span></span>

<span data-ttu-id="e0fc7-247">不適用</span><span class="sxs-lookup"><span data-stu-id="e0fc7-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-248">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-248">Definition</span></span>

<span data-ttu-id="e0fc7-249">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-250">規則運算式`Regex_czech_republic_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-251">從關鍵字`Keywords_czech_republic_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e0fc7-252">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="e0fc7-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-254">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-254">tax number</span></span>
  
<span data-ttu-id="e0fc7-255">稅務</span><span class="sxs-lookup"><span data-stu-id="e0fc7-255">tax</span></span>
  
<span data-ttu-id="e0fc7-256">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-256">tax id</span></span>
  
<span data-ttu-id="e0fc7-257">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-257">personal number</span></span>
  
<span data-ttu-id="e0fc7-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="e0fc7-258">daňové číslo</span></span>
  
<span data-ttu-id="e0fc7-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="e0fc7-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="e0fc7-260">丹麥</span><span class="sxs-lookup"><span data-stu-id="e0fc7-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-261">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-261">Format</span></span>

<span data-ttu-id="e0fc7-262">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-263">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-263">Pattern</span></span>

<span data-ttu-id="e0fc7-264">10 位數包含 hyphenl:</span><span class="sxs-lookup"><span data-stu-id="e0fc7-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="e0fc7-265">會對應至 (DDMMYY) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="e0fc7-266">連字號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-266">A hyphen</span></span>
    
- <span data-ttu-id="e0fc7-267">會對應至其中的第一個數字會對應至的出生世紀序號的四位數，最後一個數字會對應至個別的性別 （如 1 女 2 男以及即使女性奇數）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-268">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-268">Checksum</span></span>

<span data-ttu-id="e0fc7-269">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-270">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-270">Definition</span></span>

<span data-ttu-id="e0fc7-271">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-272">函式`Func_denmark_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-273">從關鍵字`Keywords_denmark_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-274">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-275">函式`Func_denmark_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-276">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="e0fc7-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-278">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-278">tax number</span></span>
  
<span data-ttu-id="e0fc7-279">稅務</span><span class="sxs-lookup"><span data-stu-id="e0fc7-279">tax</span></span>
  
<span data-ttu-id="e0fc7-280">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-280">tax id</span></span>
  
<span data-ttu-id="e0fc7-281">cpr 數目</span><span class="sxs-lookup"><span data-stu-id="e0fc7-281">cpr number</span></span>
  
<span data-ttu-id="e0fc7-282">cpr #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-282">cpr#</span></span>
  
<span data-ttu-id="e0fc7-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="e0fc7-283">skat nummer</span></span>
  
<span data-ttu-id="e0fc7-284">skat 識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="e0fc7-285">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="e0fc7-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-286">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-286">Format</span></span>

<span data-ttu-id="e0fc7-287">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-288">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-288">Pattern</span></span>

<span data-ttu-id="e0fc7-289">11 位數：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-289">11 digits:</span></span>
  
-  <span data-ttu-id="e0fc7-290">會對應至性別和世紀的出生其中奇數的數字表示 1 女 2 男並偶數指出女性，如下所示的一個數字： 1，2 代表 19 世紀;3、 4 20 的 century;5，6 第 21 世紀</span><span class="sxs-lookup"><span data-stu-id="e0fc7-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="e0fc7-291">會對應至 (YYMMDD) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="e0fc7-292">會對應至分隔出生日期相同的人員序號的三位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="e0fc7-293">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-294">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-294">Checksum</span></span>

<span data-ttu-id="e0fc7-295">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-296">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-296">Definition</span></span>

<span data-ttu-id="e0fc7-297">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-298">函式`Func_estonia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-299">從關鍵字`Keywords_estonia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-300">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-301">函式`Func_estonia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-302">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="e0fc7-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-304">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-304">tax number</span></span>
  
<span data-ttu-id="e0fc7-305">稅務</span><span class="sxs-lookup"><span data-stu-id="e0fc7-305">tax</span></span>
  
<span data-ttu-id="e0fc7-306">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-306">tax id</span></span>
  
<span data-ttu-id="e0fc7-307">個人的程式碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-307">personal code</span></span>
  
<span data-ttu-id="e0fc7-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="e0fc7-308">maksunumber</span></span>
  
<span data-ttu-id="e0fc7-309">maksu 識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-309">maksu id</span></span>
  
<span data-ttu-id="e0fc7-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="e0fc7-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="e0fc7-311">芬蘭</span><span class="sxs-lookup"><span data-stu-id="e0fc7-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-312">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-312">Format</span></span>

<span data-ttu-id="e0fc7-313">字母的數字，11 個字元組合，以及加號與減號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-314">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-314">Pattern</span></span>

<span data-ttu-id="e0fc7-315">字母的數字，11 個字元組合，以及加號與減號：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="e0fc7-316">六位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-316">Six digits</span></span>
    
- <span data-ttu-id="e0fc7-317">下列其中之一： 加上加號、 減號或其中加號表示字母"A"（不區分大小寫） 之間 1800年 1899 年出生減號登入表示出生之間 1999 1900 年和"A"表示出生 2000年和之後</span><span class="sxs-lookup"><span data-stu-id="e0fc7-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="e0fc7-318">三位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-318">Three digits</span></span>
    
- <span data-ttu-id="e0fc7-319">一個字母或一個數字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-320">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-320">Checksum</span></span>

<span data-ttu-id="e0fc7-321">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-322">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-322">Definition</span></span>

<span data-ttu-id="e0fc7-323">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-324">函式`Func_finland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-325">從關鍵字`Keywords_finland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-326">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-327">函式`Func_finland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-328">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="e0fc7-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-330">識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-330">identification number</span></span>
  
<span data-ttu-id="e0fc7-331">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-331">personal id</span></span>
  
<span data-ttu-id="e0fc7-332">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-332">identity number</span></span>
  
<span data-ttu-id="e0fc7-333">芬蘭國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-333">finnish national id number</span></span>
  
<span data-ttu-id="e0fc7-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-334">personalidnumber#</span></span>
  
<span data-ttu-id="e0fc7-335">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-335">national identification number</span></span>
  
<span data-ttu-id="e0fc7-336">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-336">id number</span></span>
  
<span data-ttu-id="e0fc7-337">國民身分證沒有。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-337">national id no.</span></span>
  
<span data-ttu-id="e0fc7-338">國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-338">national id number</span></span>
  
<span data-ttu-id="e0fc7-339">識別碼不</span><span class="sxs-lookup"><span data-stu-id="e0fc7-339">id no</span></span>
  
<span data-ttu-id="e0fc7-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="e0fc7-340">tunnistenumero</span></span>
  
<span data-ttu-id="e0fc7-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="e0fc7-341">henkilötunnus</span></span>
  
<span data-ttu-id="e0fc7-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="e0fc7-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="e0fc7-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="e0fc7-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="e0fc7-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="e0fc7-344">identiteetti numero</span></span>
  
<span data-ttu-id="e0fc7-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="e0fc7-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="e0fc7-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="e0fc7-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="e0fc7-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="e0fc7-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="e0fc7-348">tunnusnumero</span></span>
  
<span data-ttu-id="e0fc7-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="e0fc7-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="e0fc7-350">法國</span><span class="sxs-lookup"><span data-stu-id="e0fc7-350">France</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-351">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-351">Format</span></span>

<span data-ttu-id="e0fc7-352">13 位數個人與實體的九位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-353">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-353">Pattern</span></span>

<span data-ttu-id="e0fc7-354">針對個人的 13 位數：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="e0fc7-355">必須是 0、 1、 2 或 3 的一個數字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="e0fc7-356">12 位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-356">12 digits</span></span>
    
<span data-ttu-id="e0fc7-357">實體的九位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e0fc7-358">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-358">Checksum</span></span>

<span data-ttu-id="e0fc7-359">不適用</span><span class="sxs-lookup"><span data-stu-id="e0fc7-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-360">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-360">Definition</span></span>

<span data-ttu-id="e0fc7-361">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-362">函式`Func_france_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-363">從關鍵字`Keywords_france_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-364">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-365">函式`Func_france_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-366">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="e0fc7-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-368">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-368">tax identification number</span></span>
  
<span data-ttu-id="e0fc7-369">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-369">tax number</span></span>
  
<span data-ttu-id="e0fc7-370">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-370">tax id</span></span>
  
<span data-ttu-id="e0fc7-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="e0fc7-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="e0fc7-372">德國</span><span class="sxs-lookup"><span data-stu-id="e0fc7-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-373">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-373">Format</span></span>

<span data-ttu-id="e0fc7-374">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-375">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-375">Pattern</span></span>

<span data-ttu-id="e0fc7-376">11 位數：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-376">11 digits :</span></span>
  
-  <span data-ttu-id="e0fc7-377">十位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-377">Ten digits</span></span> 
    
- <span data-ttu-id="e0fc7-378">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-379">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-379">Checksum</span></span>

<span data-ttu-id="e0fc7-380">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-381">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-381">Definition</span></span>

<span data-ttu-id="e0fc7-382">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-383">函式`Func_germany_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-384">從關鍵字`Keywords_germany_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-385">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-386">函式`Func_germany_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-387">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="e0fc7-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-389">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-389">tax number</span></span>
  
<span data-ttu-id="e0fc7-390">稅務否。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-390">tax no.</span></span>
  
<span data-ttu-id="e0fc7-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-391">taxno#</span></span>
  
<span data-ttu-id="e0fc7-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-392">taxnumber#</span></span>
  
<span data-ttu-id="e0fc7-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e0fc7-393">taxnumber</span></span>
  
<span data-ttu-id="e0fc7-394">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-394">tax id</span></span>
  
<span data-ttu-id="e0fc7-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-395">taxid#</span></span>
  
<span data-ttu-id="e0fc7-396">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-396">tax identification number</span></span>
  
<span data-ttu-id="e0fc7-397">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-397">tax identification no.</span></span>
  
<span data-ttu-id="e0fc7-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="e0fc7-398">steuernummer</span></span>
  
<span data-ttu-id="e0fc7-399">steuer 識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-399">steuer id</span></span>
  
<span data-ttu-id="e0fc7-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="e0fc7-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="e0fc7-401">希臘</span><span class="sxs-lookup"><span data-stu-id="e0fc7-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-402">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-402">Format</span></span>

<span data-ttu-id="e0fc7-403">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-404">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-404">Pattern</span></span>

<span data-ttu-id="e0fc7-405">九位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e0fc7-406">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-406">Checksum</span></span>

<span data-ttu-id="e0fc7-407">不適用</span><span class="sxs-lookup"><span data-stu-id="e0fc7-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-408">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-408">Definition</span></span>

<span data-ttu-id="e0fc7-409">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-410">規則運算式`Regex_greece_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-411">從關鍵字`Keywords_greece_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e0fc7-412">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="e0fc7-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-414">afm</span><span class="sxs-lookup"><span data-stu-id="e0fc7-414">afm</span></span>
  
<span data-ttu-id="e0fc7-415">錫</span><span class="sxs-lookup"><span data-stu-id="e0fc7-415">tin</span></span>
  
<span data-ttu-id="e0fc7-416">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-416">tax id no.</span></span>
  
<span data-ttu-id="e0fc7-417">不稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-417">tax id no</span></span>
  
<span data-ttu-id="e0fc7-418">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-418">tax identification number</span></span>
  
<span data-ttu-id="e0fc7-419">稅務登錄編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-419">tax registry number</span></span>
  
<span data-ttu-id="e0fc7-420">不稅務登錄。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-420">tax registry no.</span></span>
  
<span data-ttu-id="e0fc7-421">afm #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-421">afm#</span></span>
  
<span data-ttu-id="e0fc7-422">錫 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-422">tin#</span></span>
  
<span data-ttu-id="e0fc7-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-423">taxidno#</span></span>
  
<span data-ttu-id="e0fc7-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-424">taxregistryno#</span></span>
  
<span data-ttu-id="e0fc7-425">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="e0fc7-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="e0fc7-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="e0fc7-426">aφμ</span></span>
  
<span data-ttu-id="e0fc7-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="e0fc7-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="e0fc7-428">ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="e0fc7-429">ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="e0fc7-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="e0fc7-430">匈牙利</span><span class="sxs-lookup"><span data-stu-id="e0fc7-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-431">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-431">Format</span></span>

<span data-ttu-id="e0fc7-432">不含空格或分隔符號十位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-433">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-433">Pattern</span></span>

<span data-ttu-id="e0fc7-434">十位數：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-434">Ten digits:</span></span>
  
-  <span data-ttu-id="e0fc7-435">必須是"8"的一個數字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="e0fc7-436">會對應至日期之間的天數的五位數 01/01/1867年和個別的出生日期</span><span class="sxs-lookup"><span data-stu-id="e0fc7-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="e0fc7-437">會對應至數來區分個人在同一天出生巧產生的三位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="e0fc7-438">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-439">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-439">Checksum</span></span>

<span data-ttu-id="e0fc7-440">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-441">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-441">Definition</span></span>

<span data-ttu-id="e0fc7-442">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-443">函式`Func_hungary_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-444">從關鍵字`Keywords_hungary_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-445">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-446">函式`Func_hungary_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-447">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="e0fc7-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-449">匈牙利文的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="e0fc7-450">匈牙利文錫</span><span class="sxs-lookup"><span data-stu-id="e0fc7-450">hungarian tin</span></span>
  
<span data-ttu-id="e0fc7-451">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-451">tax id number</span></span>
  
<span data-ttu-id="e0fc7-452">vat 編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-452">vat number</span></span>
  
<span data-ttu-id="e0fc7-453">不稅務授權單位</span><span class="sxs-lookup"><span data-stu-id="e0fc7-453">tax authority no</span></span>
  
<span data-ttu-id="e0fc7-454">稅務識別碼稅務身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-454">tax id tax identity number</span></span>
  
<span data-ttu-id="e0fc7-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-455">taxidnumber#</span></span>
  
<span data-ttu-id="e0fc7-456">錫 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-456">tin#</span></span>
  
<span data-ttu-id="e0fc7-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-457">hungatiantin#</span></span>
  
<span data-ttu-id="e0fc7-458">不稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-458">tax identification no</span></span>
  
<span data-ttu-id="e0fc7-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-459">taxidno#</span></span>
  
<span data-ttu-id="e0fc7-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="e0fc7-460">adóazonosító szám</span></span>
  
<span data-ttu-id="e0fc7-461">adószám</span><span class="sxs-lookup"><span data-stu-id="e0fc7-461">adószám</span></span>
  
<span data-ttu-id="e0fc7-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="e0fc7-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="e0fc7-463">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="e0fc7-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-464">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-464">Format</span></span>

<span data-ttu-id="e0fc7-465">七位數後尾隨不含空格或分隔符號的字母</span><span class="sxs-lookup"><span data-stu-id="e0fc7-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-466">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-466">Pattern</span></span>

<span data-ttu-id="e0fc7-467">七位數後尾隨字母：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="e0fc7-468">七位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-468">Seven digits</span></span> 
    
- <span data-ttu-id="e0fc7-469">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-470">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-470">Checksum</span></span>

<span data-ttu-id="e0fc7-471">不適用</span><span class="sxs-lookup"><span data-stu-id="e0fc7-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-472">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-472">Definition</span></span>

<span data-ttu-id="e0fc7-473">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-474">函式`Func_ireland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-475">從關鍵字`Keywords_ireland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-476">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-477">函式`Func_ireland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="e0fc7-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-480">公用服務沒有</span><span class="sxs-lookup"><span data-stu-id="e0fc7-480">public service no</span></span>
  
<span data-ttu-id="e0fc7-481">個人公用服務沒有</span><span class="sxs-lookup"><span data-stu-id="e0fc7-481">personal public service no</span></span>
  
<span data-ttu-id="e0fc7-482">pps 沒有</span><span class="sxs-lookup"><span data-stu-id="e0fc7-482">pps no</span></span>
  
<span data-ttu-id="e0fc7-483">個人服務否</span><span class="sxs-lookup"><span data-stu-id="e0fc7-483">personal service no</span></span>
  
<span data-ttu-id="e0fc7-484">pps service 否</span><span class="sxs-lookup"><span data-stu-id="e0fc7-484">pps service no</span></span>
  
<span data-ttu-id="e0fc7-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-485">ppsno#</span></span>
  
<span data-ttu-id="e0fc7-486">愛爾蘭 pps 沒有</span><span class="sxs-lookup"><span data-stu-id="e0fc7-486">irish pps no</span></span>
  
<span data-ttu-id="e0fc7-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-487">publicserviceno#</span></span>
  
<span data-ttu-id="e0fc7-488">個人公用服務號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-488">personal public service number</span></span>
  
<span data-ttu-id="e0fc7-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="e0fc7-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="e0fc7-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="e0fc7-490">pps uimh</span></span>
  
<span data-ttu-id="e0fc7-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="e0fc7-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="e0fc7-492">義大利</span><span class="sxs-lookup"><span data-stu-id="e0fc7-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-493">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-493">Format</span></span>

<span data-ttu-id="e0fc7-494">16 個字母和數字中指定的型態</span><span class="sxs-lookup"><span data-stu-id="e0fc7-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-495">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-495">Pattern</span></span>

<span data-ttu-id="e0fc7-496">16 個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="e0fc7-497">會對應到前三個母音系列名稱中的三個字母</span><span class="sxs-lookup"><span data-stu-id="e0fc7-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="e0fc7-498">會對應至第一、 第三個和第四個的三個字母母音在名字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="e0fc7-499">會對應至最後一位數的出生年份的兩位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="e0fc7-500">會對應至出生的月份的一個數字 — 字母可用依字母順序，但只字母 A 到 E、 H、 L、 M、 P、 R 以 T 可用 （因此，一月是的而且年 10 月 R）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="e0fc7-501">會對應至出生其中 40 加入的來區分從男生女生出生日期的月份日期的兩位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="e0fc7-502">會對應至特定出生人員 municipality 區域代碼的四位數 — 全國家/地區的代碼可用外部國家/地區</span><span class="sxs-lookup"><span data-stu-id="e0fc7-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="e0fc7-503">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-504">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-504">Checksum</span></span>

<span data-ttu-id="e0fc7-505">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-506">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-506">Definition</span></span>

<span data-ttu-id="e0fc7-507">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-508">函式`Func_italy_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-509">從關鍵字`Keywords_italy_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-510">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-511">函式`Func_italy_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-512">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="e0fc7-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-514">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-514">tax number</span></span>
  
<span data-ttu-id="e0fc7-515">稅務否。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-515">tax no.</span></span>
  
<span data-ttu-id="e0fc7-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-516">taxno#</span></span>
  
<span data-ttu-id="e0fc7-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-517">taxnumber#</span></span>
  
<span data-ttu-id="e0fc7-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e0fc7-518">taxnumber</span></span>
  
<span data-ttu-id="e0fc7-519">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-519">tax id</span></span>
  
<span data-ttu-id="e0fc7-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-520">taxid#</span></span>
  
<span data-ttu-id="e0fc7-521">會計年度的程式碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-521">fiscal code</span></span>
  
<span data-ttu-id="e0fc7-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="e0fc7-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="e0fc7-523">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="e0fc7-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-524">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-524">Format</span></span>

<span data-ttu-id="e0fc7-525">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-526">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-526">Pattern</span></span>

<span data-ttu-id="e0fc7-527">11 位數，代表所指定模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="e0fc7-528">會對應至 (DDMMYY) 出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="e0fc7-529">會對應至的出生其中"0"會對應至 19 世紀"1"會對應至 20 世紀，，"2"會對應至第 21 世紀世紀的一個數字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="e0fc7-530">四位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-531">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-531">Checksum</span></span>

<span data-ttu-id="e0fc7-532">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-533">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-533">Definition</span></span>

<span data-ttu-id="e0fc7-534">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-535">函式`Func_latvia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-536">從關鍵字`Keywords_latvia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-537">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-538">函式`Func_latvia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-539">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="e0fc7-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-541">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-541">tax number</span></span>
  
<span data-ttu-id="e0fc7-542">稅務否。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-542">tax no.</span></span>
  
<span data-ttu-id="e0fc7-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-543">taxno#</span></span>
  
<span data-ttu-id="e0fc7-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-544">taxnumber#</span></span>
  
<span data-ttu-id="e0fc7-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e0fc7-545">taxnumber</span></span>
  
<span data-ttu-id="e0fc7-546">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-546">tax id</span></span>
  
<span data-ttu-id="e0fc7-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-547">taxid#</span></span>
  
<span data-ttu-id="e0fc7-548">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-548">tax identification number</span></span>
  
<span data-ttu-id="e0fc7-549">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-549">tax identification no.</span></span>
  
<span data-ttu-id="e0fc7-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="e0fc7-550">nodokļa numurs</span></span>
  
<span data-ttu-id="e0fc7-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="e0fc7-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="e0fc7-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="e0fc7-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="e0fc7-553">立陶宛</span><span class="sxs-lookup"><span data-stu-id="e0fc7-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-554">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-554">Format</span></span>

<span data-ttu-id="e0fc7-555">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-556">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-556">Pattern</span></span>

<span data-ttu-id="e0fc7-557">11 位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e0fc7-558">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-558">Checksum</span></span>

<span data-ttu-id="e0fc7-559">不適用</span><span class="sxs-lookup"><span data-stu-id="e0fc7-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-560">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-560">Definition</span></span>

<span data-ttu-id="e0fc7-561">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-562">函式`Func_lithuania_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-563">從關鍵字`Keywords_lithuania_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-564">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-565">函式`Func_lithuania_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-566">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="e0fc7-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-568">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-568">tax number</span></span>
  
<span data-ttu-id="e0fc7-569">稅務否。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-569">tax no.</span></span>
  
<span data-ttu-id="e0fc7-570">稅務否 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-570">tax no#</span></span>
  
<span data-ttu-id="e0fc7-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-571">taxnumber#</span></span>
  
<span data-ttu-id="e0fc7-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e0fc7-572">taxnumber</span></span>
  
<span data-ttu-id="e0fc7-573">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-573">tax id</span></span>
  
<span data-ttu-id="e0fc7-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-574">taxid#</span></span>
  
<span data-ttu-id="e0fc7-575">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-575">tax identification number</span></span>
  
<span data-ttu-id="e0fc7-576">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-576">tax identification no.</span></span>
  
<span data-ttu-id="e0fc7-577">mokesčių 識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-577">mokesčių id</span></span>
  
<span data-ttu-id="e0fc7-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="e0fc7-578">mokesčių numeris</span></span>
  
<span data-ttu-id="e0fc7-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="e0fc7-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="e0fc7-580">盧森堡</span><span class="sxs-lookup"><span data-stu-id="e0fc7-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-581">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-581">Format</span></span>

<span data-ttu-id="e0fc7-582">不含空格或分隔符號的 13 位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-583">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-583">Pattern</span></span>

<span data-ttu-id="e0fc7-584">13 位數：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-584">13 digits:</span></span>
  
-  <span data-ttu-id="e0fc7-585">11 位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-585">11 digits</span></span> 
    
- <span data-ttu-id="e0fc7-586">二位數檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-587">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-587">Checksum</span></span>

<span data-ttu-id="e0fc7-588">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-589">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-589">Definition</span></span>

<span data-ttu-id="e0fc7-590">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-591">函式`Func_luxemburg_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-592">從關鍵字`Keywords_luxemburg_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-593">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-594">函式`Func_luxemburg_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-595">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="e0fc7-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-597">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-597">tax number</span></span>
  
<span data-ttu-id="e0fc7-598">稅務否。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-598">tax no.</span></span>
  
<span data-ttu-id="e0fc7-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-599">taxno#</span></span>
  
<span data-ttu-id="e0fc7-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-600">taxnumber#</span></span>
  
<span data-ttu-id="e0fc7-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e0fc7-601">taxnumber</span></span>
  
<span data-ttu-id="e0fc7-602">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-602">tax id</span></span>
  
<span data-ttu-id="e0fc7-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-603">taxid#</span></span>
  
<span data-ttu-id="e0fc7-604">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-604">tax identification number</span></span>
  
<span data-ttu-id="e0fc7-605">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-605">tax identification no.</span></span>
  
<span data-ttu-id="e0fc7-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="e0fc7-606">steuernummer</span></span>
  
<span data-ttu-id="e0fc7-607">steuer 識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-607">steuer id</span></span>
  
<span data-ttu-id="e0fc7-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="e0fc7-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="e0fc7-609">馬爾他</span><span class="sxs-lookup"><span data-stu-id="e0fc7-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-610">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-610">Format</span></span>

<span data-ttu-id="e0fc7-611">針對馬爾他 nationals: 7 位數與所指定的型態的其中一個字母</span><span class="sxs-lookup"><span data-stu-id="e0fc7-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="e0fc7-612">非馬爾他文 nationals 和馬爾他實體： 9 位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-613">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-613">Pattern</span></span>

<span data-ttu-id="e0fc7-614">馬爾他 nationals: 7 位數和一個字母</span><span class="sxs-lookup"><span data-stu-id="e0fc7-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="e0fc7-615">七位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-615">Seven digits</span></span> 
    
- <span data-ttu-id="e0fc7-616">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="e0fc7-617">非馬爾他文 nationals 和馬爾他實體： 9 位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="e0fc7-618">九位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-619">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-619">Checksum</span></span>

<span data-ttu-id="e0fc7-620">不適用</span><span class="sxs-lookup"><span data-stu-id="e0fc7-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-621">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-621">Definition</span></span>

<span data-ttu-id="e0fc7-622">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-623">函式`Func_malta_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-624">從關鍵字`Keywords_malta_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-625">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-626">函式`Func_malta_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-627">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="e0fc7-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-629">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-629">tax number</span></span>
  
<span data-ttu-id="e0fc7-630">稅務否。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-630">tax no.</span></span>
  
<span data-ttu-id="e0fc7-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-631">taxno#</span></span>
  
<span data-ttu-id="e0fc7-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-632">taxnumber#</span></span>
  
<span data-ttu-id="e0fc7-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e0fc7-633">taxnumber</span></span>
  
<span data-ttu-id="e0fc7-634">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-634">tax id</span></span>
  
<span data-ttu-id="e0fc7-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-635">taxid#</span></span>
  
<span data-ttu-id="e0fc7-636">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-636">tax identification number</span></span>
  
<span data-ttu-id="e0fc7-637">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-637">tax identification no.</span></span>
  
<span data-ttu-id="e0fc7-638">numru 且 taxxa</span><span class="sxs-lookup"><span data-stu-id="e0fc7-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="e0fc7-639">識別碼且 taxxa</span><span class="sxs-lookup"><span data-stu-id="e0fc7-639">id tat-taxxa</span></span>
  
<span data-ttu-id="e0fc7-640">numru 東西 ' identifikazzjoni 且 taxxa</span><span class="sxs-lookup"><span data-stu-id="e0fc7-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="e0fc7-641">荷蘭</span><span class="sxs-lookup"><span data-stu-id="e0fc7-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-642">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-642">Format</span></span>

<span data-ttu-id="e0fc7-643">不含空格或分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-644">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-644">Pattern</span></span>

<span data-ttu-id="e0fc7-645">九位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e0fc7-646">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-646">Checksum</span></span>

<span data-ttu-id="e0fc7-647">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-648">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-648">Definition</span></span>

<span data-ttu-id="e0fc7-649">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-650">函式`Func_netherlands_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-651">從關鍵字`Keywords_netherlands_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-652">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-653">函式`Func_netherlands_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-654">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="e0fc7-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-656">荷蘭稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="e0fc7-657">荷蘭稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-657">netherlands tax identification</span></span>
  
<span data-ttu-id="e0fc7-658">荷屬安的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="e0fc7-659">荷屬安的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-659">netherland's tax identification</span></span>
  
<span data-ttu-id="e0fc7-660">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-660">tax identification number</span></span>
  
<span data-ttu-id="e0fc7-661">荷蘭文的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-661">dutch tax id</span></span>
  
<span data-ttu-id="e0fc7-662">荷蘭文的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-662">dutch tax identification number</span></span>
  
<span data-ttu-id="e0fc7-663">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-663">tax id</span></span>
  
<span data-ttu-id="e0fc7-664">稅務識別碼 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-664">tax id#</span></span>
  
<span data-ttu-id="e0fc7-665">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-665">tax number</span></span>
  
<span data-ttu-id="e0fc7-666">稅務否 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-666">tax no#</span></span>
  
<span data-ttu-id="e0fc7-667">稅務 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-667">tax#</span></span>
  
<span data-ttu-id="e0fc7-668">錫</span><span class="sxs-lookup"><span data-stu-id="e0fc7-668">tin</span></span>
  
<span data-ttu-id="e0fc7-669">錫 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-669">tin#</span></span>
  
<span data-ttu-id="e0fc7-670">荷蘭錫</span><span class="sxs-lookup"><span data-stu-id="e0fc7-670">netherlands tin</span></span>
  
<span data-ttu-id="e0fc7-671">荷屬安的錫</span><span class="sxs-lookup"><span data-stu-id="e0fc7-671">netherland's tin</span></span>
  
<span data-ttu-id="e0fc7-672">荷蘭 belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="e0fc7-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="e0fc7-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="e0fc7-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="e0fc7-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="e0fc7-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="e0fc7-675">荷蘭 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="e0fc7-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="e0fc7-676">荷蘭 belasting 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="e0fc7-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="e0fc7-677">荷蘭 belastingnummer</span><span class="sxs-lookup"><span data-stu-id="e0fc7-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="e0fc7-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="e0fc7-678">btw nummer</span></span>
  
<span data-ttu-id="e0fc7-679">文拚字檢查 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="e0fc7-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="e0fc7-680">波蘭</span><span class="sxs-lookup"><span data-stu-id="e0fc7-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-681">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-681">Format</span></span>

<span data-ttu-id="e0fc7-682">不含空格或分隔符號十一份數字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-683">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-683">Pattern</span></span>

<span data-ttu-id="e0fc7-684">十一份數字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e0fc7-685">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-685">Checksum</span></span>

<span data-ttu-id="e0fc7-686">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-687">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-687">Definition</span></span>

<span data-ttu-id="e0fc7-688">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-689">函式`Func_poland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-690">從關鍵字`Keywords_poland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-691">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-692">函式`Func_poland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-693">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="e0fc7-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-695">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-695">tax number</span></span>
  
<span data-ttu-id="e0fc7-696">稅務否。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-696">tax no.</span></span>
  
<span data-ttu-id="e0fc7-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-697">taxno#</span></span>
  
<span data-ttu-id="e0fc7-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-698">taxnumber#</span></span>
  
<span data-ttu-id="e0fc7-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e0fc7-699">taxnumber</span></span>
  
<span data-ttu-id="e0fc7-700">nip</span><span class="sxs-lookup"><span data-stu-id="e0fc7-700">nip</span></span>
  
<span data-ttu-id="e0fc7-701">nip #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-701">nip#</span></span>
  
<span data-ttu-id="e0fc7-702">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-702">tax id</span></span>
  
<span data-ttu-id="e0fc7-703">稅務識別碼 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-703">tax id#</span></span>
  
<span data-ttu-id="e0fc7-704">nip 識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-704">nip id</span></span>
  
<span data-ttu-id="e0fc7-705">nip 識別碼 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-705">nip id#</span></span>
  
<span data-ttu-id="e0fc7-706">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-706">tax identification number</span></span>
  
<span data-ttu-id="e0fc7-707">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-707">tax identification no.</span></span>
  
<span data-ttu-id="e0fc7-708">vat 編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-708">vat number</span></span>
  
<span data-ttu-id="e0fc7-709">vat 否。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-709">vat no.</span></span>
  
<span data-ttu-id="e0fc7-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-710">vatno#</span></span>
  
<span data-ttu-id="e0fc7-711">vat 識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-711">vat id</span></span>
  
<span data-ttu-id="e0fc7-712">vat id #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-712">vat id#</span></span>
  
<span data-ttu-id="e0fc7-713">數目 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="e0fc7-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="e0fc7-714">polski 數目 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="e0fc7-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="e0fc7-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="e0fc7-716">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="e0fc7-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-717">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-717">Format</span></span>

<span data-ttu-id="e0fc7-718">不含空格或分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-719">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-719">Pattern</span></span>

<span data-ttu-id="e0fc7-720">九位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e0fc7-721">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-721">Checksum</span></span>

<span data-ttu-id="e0fc7-722">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-723">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-723">Definition</span></span>

<span data-ttu-id="e0fc7-724">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-725">函式`Func_portugal_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-726">從關鍵字`Keywords_portugal_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-727">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-728">函式`Func_portugal_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-729">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="e0fc7-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-731">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-731">tax number</span></span>
  
<span data-ttu-id="e0fc7-732">稅務否。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-732">tax no.</span></span>
  
<span data-ttu-id="e0fc7-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-733">taxno#</span></span>
  
<span data-ttu-id="e0fc7-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-734">taxnumber#</span></span>
  
<span data-ttu-id="e0fc7-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="e0fc7-735">taxnumber</span></span>
  
<span data-ttu-id="e0fc7-736">n 如果</span><span class="sxs-lookup"><span data-stu-id="e0fc7-736">nif</span></span>
  
<span data-ttu-id="e0fc7-737">n 如果 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-737">nif#</span></span>
  
<span data-ttu-id="e0fc7-738">numero 會計</span><span class="sxs-lookup"><span data-stu-id="e0fc7-738">numero fiscal</span></span>
  
<span data-ttu-id="e0fc7-739">número de identificação 會計</span><span class="sxs-lookup"><span data-stu-id="e0fc7-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="e0fc7-740">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="e0fc7-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-741">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-741">Format</span></span>

<span data-ttu-id="e0fc7-742">不含空格或分隔符號的 13 位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-743">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-743">Pattern</span></span>

<span data-ttu-id="e0fc7-744">13 位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e0fc7-745">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-745">Checksum</span></span>

<span data-ttu-id="e0fc7-746">不適用</span><span class="sxs-lookup"><span data-stu-id="e0fc7-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-747">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-747">Definition</span></span>

<span data-ttu-id="e0fc7-748">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-749">規則運算式`Regex_romania_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-750">從關鍵字`Keywords_romania_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e0fc7-751">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="e0fc7-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-753">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-753">tax id</span></span>
  
<span data-ttu-id="e0fc7-754">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-754">tax id number</span></span>
  
<span data-ttu-id="e0fc7-755">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="e0fc7-755">tax file no</span></span>
  
<span data-ttu-id="e0fc7-756">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-756">tax file number</span></span>
  
<span data-ttu-id="e0fc7-757">稅務否</span><span class="sxs-lookup"><span data-stu-id="e0fc7-757">tax no</span></span>
  
<span data-ttu-id="e0fc7-758">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-758">tax number</span></span>
  
<span data-ttu-id="e0fc7-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-759">taxid#</span></span>
  
<span data-ttu-id="e0fc7-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-760">taxno#</span></span>
  
<span data-ttu-id="e0fc7-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="e0fc7-761">id-ul taxei</span></span>
  
<span data-ttu-id="e0fc7-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="e0fc7-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="e0fc7-763">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="e0fc7-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-764">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-764">Format</span></span>

<span data-ttu-id="e0fc7-765">不含空格或分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-766">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-766">Pattern</span></span>

<span data-ttu-id="e0fc7-767">10 位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e0fc7-768">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-768">Checksum</span></span>

<span data-ttu-id="e0fc7-769">不適用</span><span class="sxs-lookup"><span data-stu-id="e0fc7-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-770">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-770">Definition</span></span>

<span data-ttu-id="e0fc7-771">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-772">規則運算式`Regex_slovakia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-773">從關鍵字`Keywords_slovakia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e0fc7-774">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="e0fc7-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-776">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-776">tax id</span></span>
  
<span data-ttu-id="e0fc7-777">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-777">tax id number</span></span>
  
<span data-ttu-id="e0fc7-778">鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-778">tin id</span></span>
  
<span data-ttu-id="e0fc7-779">鐵皮否</span><span class="sxs-lookup"><span data-stu-id="e0fc7-779">tin no</span></span>
  
<span data-ttu-id="e0fc7-780">斯洛伐克鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-780">slovakian tin id</span></span>
  
<span data-ttu-id="e0fc7-781">錫</span><span class="sxs-lookup"><span data-stu-id="e0fc7-781">tin</span></span>
  
<span data-ttu-id="e0fc7-782">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="e0fc7-782">tax file no</span></span>
  
<span data-ttu-id="e0fc7-783">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-783">tax file number</span></span>
  
<span data-ttu-id="e0fc7-784">稅務否</span><span class="sxs-lookup"><span data-stu-id="e0fc7-784">tax no</span></span>
  
<span data-ttu-id="e0fc7-785">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-785">tax number</span></span>
  
<span data-ttu-id="e0fc7-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-786">taxid#</span></span>
  
<span data-ttu-id="e0fc7-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-787">taxno#</span></span>
  
<span data-ttu-id="e0fc7-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="e0fc7-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="e0fc7-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="e0fc7-789">daňové číslo</span></span>
  
<span data-ttu-id="e0fc7-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="e0fc7-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="e0fc7-791">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="e0fc7-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-792">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-792">Format</span></span>

<span data-ttu-id="e0fc7-793">不含空格或分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-794">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-794">Pattern</span></span>

<span data-ttu-id="e0fc7-795">八位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e0fc7-796">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-796">Checksum</span></span>

<span data-ttu-id="e0fc7-797">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-798">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-798">Definition</span></span>

<span data-ttu-id="e0fc7-799">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-800">函式`Func_slovenia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-801">從關鍵字`Keywords_slovenia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-802">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-803">函式`Func_slovenia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-804">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="e0fc7-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-806">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-806">tax id</span></span>
  
<span data-ttu-id="e0fc7-807">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-807">tax id number</span></span>
  
<span data-ttu-id="e0fc7-808">鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-808">tin id</span></span>
  
<span data-ttu-id="e0fc7-809">鐵皮否</span><span class="sxs-lookup"><span data-stu-id="e0fc7-809">tin no</span></span>
  
<span data-ttu-id="e0fc7-810">斯洛維尼亞文鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-810">slovenian tin id</span></span>
  
<span data-ttu-id="e0fc7-811">錫</span><span class="sxs-lookup"><span data-stu-id="e0fc7-811">tin</span></span>
  
<span data-ttu-id="e0fc7-812">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="e0fc7-812">tax file no</span></span>
  
<span data-ttu-id="e0fc7-813">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-813">tax file number</span></span>
  
<span data-ttu-id="e0fc7-814">稅務否</span><span class="sxs-lookup"><span data-stu-id="e0fc7-814">tax no</span></span>
  
<span data-ttu-id="e0fc7-815">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-815">tax number</span></span>
  
<span data-ttu-id="e0fc7-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-816">taxid#</span></span>
  
<span data-ttu-id="e0fc7-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-817">taxno#</span></span>
  
<span data-ttu-id="e0fc7-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="e0fc7-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="e0fc7-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="e0fc7-819">davčna številka</span></span>
  
<span data-ttu-id="e0fc7-820">Številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="e0fc7-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="e0fc7-821">西班牙</span><span class="sxs-lookup"><span data-stu-id="e0fc7-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-822">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-822">Format</span></span>

<span data-ttu-id="e0fc7-823">7 或 8 位數與所指定的型態的一或兩個字母</span><span class="sxs-lookup"><span data-stu-id="e0fc7-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-824">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-824">Pattern</span></span>

<span data-ttu-id="e0fc7-825">西班牙文自然人西班牙國民身分證與：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="e0fc7-826">八位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-826">Eight digits</span></span> 
    
- <span data-ttu-id="e0fc7-827">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="e0fc7-828">非駐留西班牙人沒有西班牙國民身分證</span><span class="sxs-lookup"><span data-stu-id="e0fc7-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="e0fc7-829">一個大寫字母"L"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="e0fc7-830">七位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-830">Seven digits</span></span>
    
- <span data-ttu-id="e0fc7-831">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="e0fc7-832">[] 下的保留天數 14 年沒有西班牙國民身分證駐留西班牙人：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="e0fc7-833">一個大寫字母"K"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="e0fc7-834">七位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-834">Seven digits</span></span> 
    
- <span data-ttu-id="e0fc7-835">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="e0fc7-836">外國人與因此識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="e0fc7-837">一個大寫也就是字母 「 X 」、 「 Y"或"Z"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="e0fc7-838">七位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-838">Seven digits</span></span>
    
- <span data-ttu-id="e0fc7-839">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="e0fc7-840">外國人沒有因此識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="e0fc7-841">一個大寫字母，為 「 M 」 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="e0fc7-842">七位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-842">Seven digits</span></span>
    
- <span data-ttu-id="e0fc7-843">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e0fc7-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-844">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-844">Checksum</span></span>

<span data-ttu-id="e0fc7-845">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-846">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-846">Definition</span></span>

<span data-ttu-id="e0fc7-847">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-848">函式`Func_spain_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-849">從關鍵字`Keywords_spain_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-850">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-851">函式`Func_spain_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-852">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="e0fc7-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-854">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-854">tax id</span></span>
  
<span data-ttu-id="e0fc7-855">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-855">tax id number</span></span>
  
<span data-ttu-id="e0fc7-856">cif 識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-856">cif id</span></span>
  
<span data-ttu-id="e0fc7-857">cif 沒有</span><span class="sxs-lookup"><span data-stu-id="e0fc7-857">cif no</span></span>
  
<span data-ttu-id="e0fc7-858">西班牙文的 cif 識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-858">spanish cif id</span></span>
  
<span data-ttu-id="e0fc7-859">cif</span><span class="sxs-lookup"><span data-stu-id="e0fc7-859">cif</span></span>
  
<span data-ttu-id="e0fc7-860">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="e0fc7-860">tax file no</span></span>
  
<span data-ttu-id="e0fc7-861">西班牙文的 cif 數目</span><span class="sxs-lookup"><span data-stu-id="e0fc7-861">spanish cif number</span></span>
  
<span data-ttu-id="e0fc7-862">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-862">tax file number</span></span>
  
<span data-ttu-id="e0fc7-863">西班牙文的 cif 沒有</span><span class="sxs-lookup"><span data-stu-id="e0fc7-863">spanish cif no</span></span>
  
<span data-ttu-id="e0fc7-864">稅務否</span><span class="sxs-lookup"><span data-stu-id="e0fc7-864">tax no</span></span>
  
<span data-ttu-id="e0fc7-865">稅務編號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-865">tax number</span></span>
  
<span data-ttu-id="e0fc7-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-866">taxid#</span></span>
  
<span data-ttu-id="e0fc7-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-867">taxno#</span></span>
  
<span data-ttu-id="e0fc7-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-868">cifid#</span></span>
  
<span data-ttu-id="e0fc7-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-869">spanishcifid#</span></span>
  
<span data-ttu-id="e0fc7-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-870">spanishcifno#</span></span>
  
<span data-ttu-id="e0fc7-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="e0fc7-871">número de contribuyente</span></span>
  
<span data-ttu-id="e0fc7-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="e0fc7-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="e0fc7-873">número de identificación 會計</span><span class="sxs-lookup"><span data-stu-id="e0fc7-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="e0fc7-874">cif número</span><span class="sxs-lookup"><span data-stu-id="e0fc7-874">cif número</span></span>
  
<span data-ttu-id="e0fc7-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="e0fc7-876">瑞典</span><span class="sxs-lookup"><span data-stu-id="e0fc7-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-877">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-877">Format</span></span>

<span data-ttu-id="e0fc7-878">十個數字和中指定的型態的符號</span><span class="sxs-lookup"><span data-stu-id="e0fc7-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-879">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-879">Pattern</span></span>

<span data-ttu-id="e0fc7-880">十個數字和符號：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="e0fc7-881">會對應至 (YYMMDD) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="e0fc7-882">加號、 減號或反斜線</span><span class="sxs-lookup"><span data-stu-id="e0fc7-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="e0fc7-883">請識別的三位數數字唯一的位置：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="e0fc7-884">發行之前 1990年數字，如第七個和第八個數字識別出生或 foreign-born 人員郡</span><span class="sxs-lookup"><span data-stu-id="e0fc7-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="e0fc7-885">在第九個位置的數字，表示女性 1 女 2 男或甚至是任一奇數性別</span><span class="sxs-lookup"><span data-stu-id="e0fc7-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="e0fc7-886">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e0fc7-887">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-887">Checksum</span></span>

<span data-ttu-id="e0fc7-888">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-889">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-889">Definition</span></span>

<span data-ttu-id="e0fc7-890">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-891">函式`Func_sweden_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-892">從關鍵字`Keywords_sweden_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e0fc7-893">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-894">函式`Func_sweden_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e0fc7-895">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="e0fc7-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-897">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-897">tax id</span></span>
  
<span data-ttu-id="e0fc7-898">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-898">tax id no.</span></span>
  
<span data-ttu-id="e0fc7-899">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-899">tax id number</span></span>
  
<span data-ttu-id="e0fc7-900">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-900">tax identification</span></span>
  
<span data-ttu-id="e0fc7-901">稅務識別 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-901">tax identification#</span></span>
  
<span data-ttu-id="e0fc7-902">稅務否。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-902">tax no.</span></span>
  
<span data-ttu-id="e0fc7-903">稅務 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-903">tax#</span></span>
  
<span data-ttu-id="e0fc7-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-904">taxid#</span></span>
  
<span data-ttu-id="e0fc7-905">稅務檔案</span><span class="sxs-lookup"><span data-stu-id="e0fc7-905">tax file</span></span>
  
<span data-ttu-id="e0fc7-906">不稅務檔案。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-906">tax file no.</span></span>
  
<span data-ttu-id="e0fc7-907">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-907">personal id number</span></span>
  
<span data-ttu-id="e0fc7-908">skatt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="e0fc7-908">skatt id nummer</span></span>
  
<span data-ttu-id="e0fc7-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="e0fc7-909">skatt identifikation</span></span>
  
<span data-ttu-id="e0fc7-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="e0fc7-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="e0fc7-911">英國</span><span class="sxs-lookup"><span data-stu-id="e0fc7-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="e0fc7-912">Format</span><span class="sxs-lookup"><span data-stu-id="e0fc7-912">Format</span></span>

<span data-ttu-id="e0fc7-913">如果沒有空格和分隔符號的唯一 Taxpayer 參照 (UTR): 10 位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="e0fc7-914">國家保險號碼 (NINO): 如需詳細資訊，請參閱區段 」 英國</span><span class="sxs-lookup"><span data-stu-id="e0fc7-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="e0fc7-915">國家保險號碼 (NINO) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e0fc7-916">模式</span><span class="sxs-lookup"><span data-stu-id="e0fc7-916">Pattern</span></span>

<span data-ttu-id="e0fc7-917">唯一 Taxpayer 參照 (UTR): 10 位數</span><span class="sxs-lookup"><span data-stu-id="e0fc7-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="e0fc7-918">國家保險號碼 (NINO): 如需詳細資訊，請參閱區段 」 英國</span><span class="sxs-lookup"><span data-stu-id="e0fc7-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="e0fc7-919">國家保險號碼 (NINO) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e0fc7-920">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-920">Checksum</span></span>

<span data-ttu-id="e0fc7-921">是</span><span class="sxs-lookup"><span data-stu-id="e0fc7-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e0fc7-922">定義</span><span class="sxs-lookup"><span data-stu-id="e0fc7-922">Definition</span></span>

<span data-ttu-id="e0fc7-923">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e0fc7-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e0fc7-924">函式`Func_uk_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e0fc7-925">從關鍵字`Keywords_uk_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e0fc7-926">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e0fc7-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="e0fc7-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e0fc7-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="e0fc7-928">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-928">tax id</span></span>
  
<span data-ttu-id="e0fc7-929">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-929">tax id no.</span></span>
  
<span data-ttu-id="e0fc7-930">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-930">tax id number</span></span>
  
<span data-ttu-id="e0fc7-931">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-931">tax identification</span></span>
  
<span data-ttu-id="e0fc7-932">稅務識別 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-932">tax identification#</span></span>
  
<span data-ttu-id="e0fc7-933">稅務否。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-933">tax no.</span></span>
  
<span data-ttu-id="e0fc7-934">稅務 #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-934">tax#</span></span>
  
<span data-ttu-id="e0fc7-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="e0fc7-935">taxid#</span></span>
  
<span data-ttu-id="e0fc7-936">稅務檔案</span><span class="sxs-lookup"><span data-stu-id="e0fc7-936">tax file</span></span>
  
<span data-ttu-id="e0fc7-937">不稅務檔案。</span><span class="sxs-lookup"><span data-stu-id="e0fc7-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e0fc7-938">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e0fc7-938">See also</span></span>

[<span data-ttu-id="e0fc7-939">機密資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="e0fc7-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

