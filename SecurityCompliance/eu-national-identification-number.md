---
title: 歐盟國家識別碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 2ea971bf-9434-4b61-b825-2bbd28ae6064
description: 本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟國家識別碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。
ms.openlocfilehash: 29d2126b937ff46039284a74eb2a84f2ebbacb41
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526694"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="1e7df-104">歐盟國家識別碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-104">EU National Identification Number</span></span>

<span data-ttu-id="1e7df-p102">本主題說明什麼資料外洩防護 (DLP) 原則會尋找時被歐盟國家識別碼敏感資訊類型。此敏感資訊類型定義不同的模式、 關鍵字及每個國家/地區的其他證據。</span><span class="sxs-lookup"><span data-stu-id="1e7df-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="1e7df-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="1e7df-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-108">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-108">Format</span></span>

<span data-ttu-id="1e7df-109">24 個字元之字母、 數字和組合特殊字元</span><span class="sxs-lookup"><span data-stu-id="1e7df-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-110">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-110">Pattern</span></span>

<span data-ttu-id="1e7df-111">24 個字元：</span><span class="sxs-lookup"><span data-stu-id="1e7df-111">24 characters:</span></span>
  
-  <span data-ttu-id="1e7df-112">22 字母 （不區分大小寫）、 數字、 反斜線、 正斜線或加號</span><span class="sxs-lookup"><span data-stu-id="1e7df-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="1e7df-113">兩個字母 （不區分大小寫）、 數字、 反斜線、 正斜線、 加號或等號</span><span class="sxs-lookup"><span data-stu-id="1e7df-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1e7df-114">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-114">Checksum</span></span>

<span data-ttu-id="1e7df-115">不適用</span><span class="sxs-lookup"><span data-stu-id="1e7df-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-116">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-116">Definition</span></span>

<span data-ttu-id="1e7df-117">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-118">規則運算式`Regex_austria_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-119">從關鍵字`Keywords_austria_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-120">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-120">Keywords</span></span>

#### <a name="keywordsaustriaeunationalidcard"></a><span data-ttu-id="1e7df-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-122">奧地利身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-122">austrian identity number</span></span>
  
<span data-ttu-id="1e7df-123">國民身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-123">national identity number</span></span>
  
<span data-ttu-id="1e7df-124">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-124">identity number</span></span>
  
<span data-ttu-id="1e7df-125">
national id</span><span class="sxs-lookup"><span data-stu-id="1e7df-125">national id</span></span>
  
<span data-ttu-id="1e7df-126">personalausweis republik österreich</span><span class="sxs-lookup"><span data-stu-id="1e7df-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="1e7df-127">比利時</span><span class="sxs-lookup"><span data-stu-id="1e7df-127">Belgium</span></span>

<span data-ttu-id="1e7df-128">如需詳細資訊，請參閱節"比利時國民 Number"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7df-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="1e7df-129">保加利亞</span><span class="sxs-lookup"><span data-stu-id="1e7df-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-130">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-130">Format</span></span>

<span data-ttu-id="1e7df-131">十位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="1e7df-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-132">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-132">Pattern</span></span>

<span data-ttu-id="1e7df-133">十位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="1e7df-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="1e7df-134">會對應至出生日期 (YYMMDD) 的六個數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="1e7df-135">會對應至出生順序的最上層的兩位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="1e7df-136">會對應至性別的一個數字： 偶數數字 2 男和女性奇數數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="1e7df-137">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1e7df-138">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-138">Checksum</span></span>

<span data-ttu-id="1e7df-139">是</span><span class="sxs-lookup"><span data-stu-id="1e7df-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-140">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-140">Definition</span></span>

<span data-ttu-id="1e7df-141">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-142">此函數`Func_bulgaria_national_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-143">從關鍵字`Keywords_bulgaria_national_number`找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="1e7df-144">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-145">此函數`Func_bulgaria_national_number`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-146">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-146">Keywords</span></span>

#### <a name="keywordsbulgarianationalnumber"></a><span data-ttu-id="1e7df-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="1e7df-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="1e7df-148">egn</span><span class="sxs-lookup"><span data-stu-id="1e7df-148">egn</span></span>
  
<span data-ttu-id="1e7df-149">egn #</span><span class="sxs-lookup"><span data-stu-id="1e7df-149">egn#</span></span>
  
<span data-ttu-id="1e7df-150">保加利亞國際號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-150">bulgarian national number</span></span>
  
<span data-ttu-id="1e7df-151">國際號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-151">national number</span></span>
  
<span data-ttu-id="1e7df-152">social security number
</span><span class="sxs-lookup"><span data-stu-id="1e7df-152">social security number</span></span>
  
<span data-ttu-id="1e7df-153">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="1e7df-153">nationalnumber#</span></span>
  
<span data-ttu-id="1e7df-154">ssn #</span><span class="sxs-lookup"><span data-stu-id="1e7df-154">ssn#</span></span>
  
<span data-ttu-id="1e7df-155">ssn</span><span class="sxs-lookup"><span data-stu-id="1e7df-155">ssn</span></span>
  
<span data-ttu-id="1e7df-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="1e7df-156">nationalnumber</span></span>
  
<span data-ttu-id="1e7df-157">bnn #</span><span class="sxs-lookup"><span data-stu-id="1e7df-157">bnn#</span></span>
  
<span data-ttu-id="1e7df-158">bnn</span><span class="sxs-lookup"><span data-stu-id="1e7df-158">bnn</span></span>
  
<span data-ttu-id="1e7df-159">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-159">personal id number</span></span>
  
<span data-ttu-id="1e7df-160">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="1e7df-160">personalidnumber#</span></span>
  
<span data-ttu-id="1e7df-161">ЕДИНЕН ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="1e7df-161">единен граждански номер</span></span>
  
<span data-ttu-id="1e7df-162">edinen grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="1e7df-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="1e7df-163">ЕГН</span><span class="sxs-lookup"><span data-stu-id="1e7df-163">егн</span></span>
  
<span data-ttu-id="1e7df-164">ЕГН #</span><span class="sxs-lookup"><span data-stu-id="1e7df-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="1e7df-165">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="1e7df-165">Croatia</span></span>

<span data-ttu-id="1e7df-166">如需詳細資訊，請參閱節"克羅埃西亞 Identity Number"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7df-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="1e7df-167">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="1e7df-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-168">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-168">Format</span></span>

<span data-ttu-id="1e7df-169">十位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="1e7df-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-170">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-170">Pattern</span></span>

 <span data-ttu-id="1e7df-171">十位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1e7df-172">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-172">Checksum</span></span>

<span data-ttu-id="1e7df-173">不適用</span><span class="sxs-lookup"><span data-stu-id="1e7df-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-174">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-174">Definition</span></span>

<span data-ttu-id="1e7df-175">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-176">規則運算式`Regex_cyprus_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-177">從關鍵字`Keywords_cyprus_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-178">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-178">Keywords</span></span>

#### <a name="keywordscypruseunationalidcard"></a><span data-ttu-id="1e7df-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-180">識別碼卡卡號</span><span class="sxs-lookup"><span data-stu-id="1e7df-180">id card number</span></span>
  
<span data-ttu-id="1e7df-181">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-181">national identification number</span></span>
  
<span data-ttu-id="1e7df-182">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-182">personal id number</span></span>
  
<span data-ttu-id="1e7df-183">身分識別卡卡號</span><span class="sxs-lookup"><span data-stu-id="1e7df-183">identity card number</span></span>
  
<span data-ttu-id="1e7df-184">ΤΑΥΤΟΤΗΤΑΣ</span><span class="sxs-lookup"><span data-stu-id="1e7df-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="1e7df-185">捷克</span><span class="sxs-lookup"><span data-stu-id="1e7df-185">Czech Republic</span></span>

<span data-ttu-id="1e7df-186">如需詳細資訊，請參閱節"捷克文國民身分識別 Number"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7df-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="1e7df-187">丹麥</span><span class="sxs-lookup"><span data-stu-id="1e7df-187">Denmark</span></span>

<span data-ttu-id="1e7df-188">如需詳細資訊，請參閱節"丹麥個人識別碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7df-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="1e7df-189">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="1e7df-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-190">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-190">Format</span></span>

<span data-ttu-id="1e7df-191">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="1e7df-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-192">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-192">Pattern</span></span>

<span data-ttu-id="1e7df-193">11 位數：</span><span class="sxs-lookup"><span data-stu-id="1e7df-193">11 digits:</span></span>
  
- <span data-ttu-id="1e7df-194">會對應至性別和出生的 century 的一個數字 (奇數的數字 2 男，偶數女性、 1-2: 19 century ； 3-4： 20 century; 5-6： 第 21 世紀)</span><span class="sxs-lookup"><span data-stu-id="1e7df-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="1e7df-195">會對應至出生 (YYMMDD) 的日期的六個數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="1e7df-196">會對應至分隔出生日期相同的人員序號的三個位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="1e7df-197">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1e7df-198">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-198">Checksum</span></span>

<span data-ttu-id="1e7df-199">是</span><span class="sxs-lookup"><span data-stu-id="1e7df-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-200">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-200">Definition</span></span>

<span data-ttu-id="1e7df-201">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-202">此函數`Func_estonia_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-203">從關鍵字`Keywords_estonia_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="1e7df-204">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-205">此函數`Func_estonia_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-206">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-206">Keywords</span></span>

#### <a name="keywordsestoniaeunationalidcard"></a><span data-ttu-id="1e7df-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-208">個人識別碼的程式碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-208">personal identification code</span></span>
  
<span data-ttu-id="1e7df-209">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-209">personal identification number</span></span>
  
<span data-ttu-id="1e7df-210">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-210">national identification number</span></span>
  
<span data-ttu-id="1e7df-211">國際號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-211">national number</span></span>
  
<span data-ttu-id="1e7df-212">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-212">personal id number</span></span>
  
<span data-ttu-id="1e7df-213">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="1e7df-213">personalidnumber#</span></span>
  
<span data-ttu-id="1e7df-214">ik</span><span class="sxs-lookup"><span data-stu-id="1e7df-214">ik</span></span>
  
<span data-ttu-id="1e7df-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="1e7df-215">isikukood</span></span>
  
<span data-ttu-id="1e7df-216">識別碼 kaart</span><span class="sxs-lookup"><span data-stu-id="1e7df-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="1e7df-217">芬蘭</span><span class="sxs-lookup"><span data-stu-id="1e7df-217">Finland</span></span>

<span data-ttu-id="1e7df-218">如需詳細資訊，請參閱節"芬蘭國家識別碼 」 中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7df-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="1e7df-219">法國</span><span class="sxs-lookup"><span data-stu-id="1e7df-219">France</span></span>

<span data-ttu-id="1e7df-220">如需詳細資訊，請參閱節"法國國民識別碼卡片 (CNI)"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7df-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="1e7df-221">德國</span><span class="sxs-lookup"><span data-stu-id="1e7df-221">Germany</span></span>

<span data-ttu-id="1e7df-222">如需詳細資訊，請參閱節"德國識別卡 Number"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7df-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="1e7df-223">希臘</span><span class="sxs-lookup"><span data-stu-id="1e7df-223">Greece</span></span>

<span data-ttu-id="1e7df-224">如需詳細資訊，請參閱節"希臘國家識別碼卡片"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7df-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="1e7df-225">匈牙利</span><span class="sxs-lookup"><span data-stu-id="1e7df-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-226">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-226">Format</span></span>

<span data-ttu-id="1e7df-227">11 位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-228">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-228">Pattern</span></span>

<span data-ttu-id="1e7df-229">11 位數：</span><span class="sxs-lookup"><span data-stu-id="1e7df-229">11 digits:</span></span>
  
-  <span data-ttu-id="1e7df-230">會對應至性別 （1-2 男 2 女性、 其他號碼是也可能的市民出生 1900年之前或具有雙公民公民） 的一個數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="1e7df-231">會對應至出生日期 (YYMMDD) 的六個數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="1e7df-232">會對應到序號的三個位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="1e7df-233">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1e7df-234">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-234">Checksum</span></span>

<span data-ttu-id="1e7df-235">是</span><span class="sxs-lookup"><span data-stu-id="1e7df-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-236">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-236">Definition</span></span>

<span data-ttu-id="1e7df-237">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-238">此函數`Func_hungary_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-239">從關鍵字`Keywords_hungary_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="1e7df-240">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-241">此函數`Func_hungary_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-242">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-242">Keywords</span></span>

#### <a name="keywordshungaryeunationalidcard"></a><span data-ttu-id="1e7df-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-244">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-244">personal identification number</span></span>
  
<span data-ttu-id="1e7df-245">identification number
</span><span class="sxs-lookup"><span data-stu-id="1e7df-245">identification number</span></span>
  
<span data-ttu-id="1e7df-246">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-246">personal id number</span></span>
  
<span data-ttu-id="1e7df-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="1e7df-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="1e7df-248">Ireland</span><span class="sxs-lookup"><span data-stu-id="1e7df-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-249">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-249">Format</span></span>

<span data-ttu-id="1e7df-250">九個字元之字母、 數字和組合中所指定的型態的空間</span><span class="sxs-lookup"><span data-stu-id="1e7df-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-251">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-251">Pattern</span></span>

<span data-ttu-id="1e7df-252">九個字元之字母、 數字和組合中所指定的型態的空間</span><span class="sxs-lookup"><span data-stu-id="1e7df-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="1e7df-253">從到現在的年 1 月 2013 01 日</span><span class="sxs-lookup"><span data-stu-id="1e7df-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="1e7df-254">七位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-254">Seven digits</span></span> 
    
- <span data-ttu-id="1e7df-255">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-255">One check digit</span></span>
    
- <span data-ttu-id="1e7df-256">一個空格或大寫字母"W"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="1e7df-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="1e7df-257">01 年 1 月 2013年前的：</span><span class="sxs-lookup"><span data-stu-id="1e7df-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="1e7df-258">七位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-258">Seven digits</span></span> 
    
- <span data-ttu-id="1e7df-259">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-259">One check digit</span></span>
    
- <span data-ttu-id="1e7df-260">一個空格或大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="1e7df-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1e7df-261">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-261">Checksum</span></span>

<span data-ttu-id="1e7df-262">是</span><span class="sxs-lookup"><span data-stu-id="1e7df-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-263">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-263">Definition</span></span>

<span data-ttu-id="1e7df-264">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-265">此函數會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="1e7df-266">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-266">A keyword from is found.</span></span>
    
<span data-ttu-id="1e7df-267">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-268">此函數會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-268">The function finds content that matches the pattern.</span></span>
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-269">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-269">Keywords</span></span>

#### <a name="keywordsirelandeunationalidcard"></a><span data-ttu-id="1e7df-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-271">個人公用健保號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-271">personal public service number</span></span>
  
<span data-ttu-id="1e7df-272">pps 無</span><span class="sxs-lookup"><span data-stu-id="1e7df-272">pps no</span></span>
  
<span data-ttu-id="1e7df-273">收益及社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="1e7df-274">rsi 無</span><span class="sxs-lookup"><span data-stu-id="1e7df-274">rsi no</span></span>
  
<span data-ttu-id="1e7df-275">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-275">personal identification number</span></span>
  
<span data-ttu-id="1e7df-276">identification number
</span><span class="sxs-lookup"><span data-stu-id="1e7df-276">identification number</span></span>
  
<span data-ttu-id="1e7df-277">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-277">personal id number</span></span>
  
<span data-ttu-id="1e7df-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="1e7df-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="1e7df-p103">uimh。psp</span><span class="sxs-lookup"><span data-stu-id="1e7df-p103">uimh. psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="1e7df-281">義大利</span><span class="sxs-lookup"><span data-stu-id="1e7df-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-282">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-282">Format</span></span>

<span data-ttu-id="1e7df-283">16 個字元之字母和組合中所指定的型態的數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-284">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-284">Pattern</span></span>

<span data-ttu-id="1e7df-285">16 個字元字母和數字的組合：</span><span class="sxs-lookup"><span data-stu-id="1e7df-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="1e7df-286">會對應至系列名稱中前三個母音的三個字母</span><span class="sxs-lookup"><span data-stu-id="1e7df-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="1e7df-287">會對應至第一個、 第三和第四的三個字母母音中第一個名稱</span><span class="sxs-lookup"><span data-stu-id="1e7df-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="1e7df-288">會對應至最後一出生年的數字的兩位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="1e7df-289">對應於信件的月出生的一個字母 — 字母依字母順序使用，但僅限字母 A 到 E、 H、 L、 M、 P、 R 以 T 可用 （即得出年 1 月是 A 及年 10 月為 R）</span><span class="sxs-lookup"><span data-stu-id="1e7df-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="1e7df-290">會對應至出生的月的一天的兩個位數 — 以區分 genders、 40 新增的女性出生的天</span><span class="sxs-lookup"><span data-stu-id="1e7df-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="1e7df-291">會對應至區碼出生人員 municipality 特有的四個位數 （國家全代碼可用外部的國家/地區）</span><span class="sxs-lookup"><span data-stu-id="1e7df-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="1e7df-292">一個同位數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1e7df-293">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-293">Checksum</span></span>

<span data-ttu-id="1e7df-294">是</span><span class="sxs-lookup"><span data-stu-id="1e7df-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-295">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-295">Definition</span></span>

<span data-ttu-id="1e7df-296">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-297">此函數`Func_italy_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-298">從關鍵字`Keywords_italy_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="1e7df-299">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-300">此函數`Func_italy_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-301">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-301">Keywords</span></span>

#### <a name="keywordsitalyeunationalidcard"></a><span data-ttu-id="1e7df-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-303">個人的程式碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-303">personal code</span></span>
  
<span data-ttu-id="1e7df-304">個人的程式碼數目</span><span class="sxs-lookup"><span data-stu-id="1e7df-304">personal code number</span></span>
  
<span data-ttu-id="1e7df-305">個人憑證數目</span><span class="sxs-lookup"><span data-stu-id="1e7df-305">personal certificate number</span></span>
  
<span data-ttu-id="1e7df-306">會計程式碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-306">fiscal code</span></span>
  
<span data-ttu-id="1e7df-307">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="1e7df-307">personalcodeno#</span></span>
  
<span data-ttu-id="1e7df-308">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-308">personal id number</span></span>
  
<span data-ttu-id="1e7df-309">個人識別碼的程式碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-309">personal id code</span></span>
  
<span data-ttu-id="1e7df-310">codice personale</span><span class="sxs-lookup"><span data-stu-id="1e7df-310">codice personale</span></span>
  
<span data-ttu-id="1e7df-311">numero certificato personale</span><span class="sxs-lookup"><span data-stu-id="1e7df-311">numero certificato personale</span></span>
  
<span data-ttu-id="1e7df-312">numero personale</span><span class="sxs-lookup"><span data-stu-id="1e7df-312">numero personale</span></span>
  
<span data-ttu-id="1e7df-313">numero 識別碼 personale</span><span class="sxs-lookup"><span data-stu-id="1e7df-313">numero id personale</span></span>
  
<span data-ttu-id="1e7df-314">codice 識別碼 personale</span><span class="sxs-lookup"><span data-stu-id="1e7df-314">codice id personale</span></span>
  
<span data-ttu-id="1e7df-315">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="1e7df-315">codice fiscale</span></span>
  
## <a name="italy"></a><span data-ttu-id="1e7df-316">義大利</span><span class="sxs-lookup"><span data-stu-id="1e7df-316">Italy</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-317">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-317">Format</span></span>

<span data-ttu-id="1e7df-318">11 位數與指定之格式的連字號</span><span class="sxs-lookup"><span data-stu-id="1e7df-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-319">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-319">Pattern</span></span>

<span data-ttu-id="1e7df-320">11 位數和連字號：</span><span class="sxs-lookup"><span data-stu-id="1e7df-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="1e7df-321">會對應至出生日期 (DDMMYY) 的六個數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="1e7df-322">一個連字號</span><span class="sxs-lookup"><span data-stu-id="1e7df-322">A hyphen</span></span>
    
- <span data-ttu-id="1e7df-323">會對應至出生 （"0"的 19 century、 20 century 為"1"和"2"第 21 世紀） 的 century 的一個數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="1e7df-324">隨機產生的四位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1e7df-325">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-325">Checksum</span></span>

<span data-ttu-id="1e7df-326">是</span><span class="sxs-lookup"><span data-stu-id="1e7df-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-327">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-327">Definition</span></span>

<span data-ttu-id="1e7df-328">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-329">此函數`Func_latvia_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-330">從關鍵字`Keywords_latvia_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="1e7df-331">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-332">此函數`Func_latvia_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-333">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-333">Keywords</span></span>

#### <a name="keywordslatviaeunationalidcard"></a><span data-ttu-id="1e7df-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-335">個人的程式碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-335">personal code</span></span>
  
<span data-ttu-id="1e7df-336">個人的程式碼數目</span><span class="sxs-lookup"><span data-stu-id="1e7df-336">personal code number</span></span>
  
<span data-ttu-id="1e7df-337">個人憑證數目</span><span class="sxs-lookup"><span data-stu-id="1e7df-337">personal certificate number</span></span>
  
<span data-ttu-id="1e7df-338">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="1e7df-338">personalcodeno#</span></span>
  
<span data-ttu-id="1e7df-339">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-339">personal id number</span></span>
  
<span data-ttu-id="1e7df-340">個人識別碼的程式碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-340">personal id code</span></span>
  
<span data-ttu-id="1e7df-341">人物代表 kods</span><span class="sxs-lookup"><span data-stu-id="1e7df-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="1e7df-342">立陶宛</span><span class="sxs-lookup"><span data-stu-id="1e7df-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-343">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-343">Format</span></span>

<span data-ttu-id="1e7df-344">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="1e7df-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-345">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-345">Pattern</span></span>

<span data-ttu-id="1e7df-346">不含空格和分隔符號的 11 位數：</span><span class="sxs-lookup"><span data-stu-id="1e7df-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="1e7df-347">會對應至這個人性別和出生的 century 的一個數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="1e7df-348">會對應至出生日期 (YYMMDD) 的六個數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="1e7df-349">會對應至出生的日期序號的三個位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="1e7df-350">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1e7df-351">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-351">Checksum</span></span>

<span data-ttu-id="1e7df-352">是</span><span class="sxs-lookup"><span data-stu-id="1e7df-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-353">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-353">Definition</span></span>

<span data-ttu-id="1e7df-354">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-355">此函數`Func_lithuania_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-356">從關鍵字`Keywords_lithuania_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="1e7df-357">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-358">此函數`Func_lithuania_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-359">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-359">Keywords</span></span>

#### <a name="keywordslithuaniaeunationalidcard"></a><span data-ttu-id="1e7df-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-361">個人數字碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-361">personal numeric code</span></span>
  
<span data-ttu-id="1e7df-362">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-362">unique identification number</span></span>
  
<span data-ttu-id="1e7df-363">市民健保號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-363">citizen service number</span></span>
  
<span data-ttu-id="1e7df-364">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-364">unique identity number</span></span>
  
<span data-ttu-id="1e7df-365">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="1e7df-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="1e7df-366">個人的程式碼。</span><span class="sxs-lookup"><span data-stu-id="1e7df-366">personal code.</span></span>
  
<span data-ttu-id="1e7df-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="1e7df-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="1e7df-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="1e7df-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="1e7df-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="1e7df-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="1e7df-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="1e7df-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="1e7df-371">asmens kodas。</span><span class="sxs-lookup"><span data-stu-id="1e7df-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="1e7df-372">盧森堡</span><span class="sxs-lookup"><span data-stu-id="1e7df-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-373">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-373">Format</span></span>

<span data-ttu-id="1e7df-374">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="1e7df-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-375">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-375">Pattern</span></span>

<span data-ttu-id="1e7df-376">11 位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-376">11 digits</span></span>
  
- <span data-ttu-id="1e7df-377">會對應至這個人性別和出生的 century 的一個數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="1e7df-378">會對應至出生日期 (YYMMDD) 的六個數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="1e7df-379">會對應至出生的日期序號的三個位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="1e7df-380">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1e7df-381">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-381">Checksum</span></span>

<span data-ttu-id="1e7df-382">不適用</span><span class="sxs-lookup"><span data-stu-id="1e7df-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-383">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-383">Definition</span></span>

<span data-ttu-id="1e7df-384">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-385">規則運算式`Regex_luxemburg_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-386">從關鍵字`Keywords_luxemburg_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-387">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-387">Keywords</span></span>

#### <a name="keywordsluxemburgeunationalidcard"></a><span data-ttu-id="1e7df-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-389">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-389">personal id</span></span>
  
<span data-ttu-id="1e7df-390">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-390">personal id number</span></span>
  
<span data-ttu-id="1e7df-391">personalidno #</span><span class="sxs-lookup"><span data-stu-id="1e7df-391">personalidno#</span></span>
  
<span data-ttu-id="1e7df-392">唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-392">unique id number</span></span>
  
<span data-ttu-id="1e7df-393">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="1e7df-393">personalidnumber#</span></span>
  
<span data-ttu-id="1e7df-394">唯一識別碼機碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-394">unique id key</span></span>
  
<span data-ttu-id="1e7df-395">個人識別碼的程式碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-395">personal id code</span></span>
  
<span data-ttu-id="1e7df-396">uniqueidkey #</span><span class="sxs-lookup"><span data-stu-id="1e7df-396">uniqueidkey#</span></span>
  
<span data-ttu-id="1e7df-397">個別的程式碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-397">individual code</span></span>
  
<span data-ttu-id="1e7df-398">個別的識別碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-398">individual id</span></span>
  
<span data-ttu-id="1e7df-399">eindeutige 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="1e7df-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="1e7df-400">eindeutige 識別碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-400">eindeutige id</span></span>
  
<span data-ttu-id="1e7df-401">識別碼 personnelle</span><span class="sxs-lookup"><span data-stu-id="1e7df-401">id personnelle</span></span>
  
<span data-ttu-id="1e7df-402">numéro d'identification 人員</span><span class="sxs-lookup"><span data-stu-id="1e7df-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="1e7df-403">idpersonnelle #</span><span class="sxs-lookup"><span data-stu-id="1e7df-403">idpersonnelle#</span></span>
  
<span data-ttu-id="1e7df-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="1e7df-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="1e7df-405">eindeutigeid #</span><span class="sxs-lookup"><span data-stu-id="1e7df-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="1e7df-406">馬爾他</span><span class="sxs-lookup"><span data-stu-id="1e7df-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-407">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-407">Format</span></span>

<span data-ttu-id="1e7df-408">後面接著一個字母的七位數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-409">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-409">Pattern</span></span>

<span data-ttu-id="1e7df-410">後面接著一個字母的七位數字：</span><span class="sxs-lookup"><span data-stu-id="1e7df-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="1e7df-411">七位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-411">Seven digits</span></span> 
    
- <span data-ttu-id="1e7df-412">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="1e7df-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1e7df-413">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-413">Checksum</span></span>

<span data-ttu-id="1e7df-414">不適用</span><span class="sxs-lookup"><span data-stu-id="1e7df-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-415">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-415">Definition</span></span>

<span data-ttu-id="1e7df-416">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-417">規則運算式`Regex_malta_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-418">從關鍵字`Keywords_malta_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="1e7df-419">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-420">規則運算式`Regex_malta_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-421">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-421">Keywords</span></span>

#### <a name="keywordsmaltaeunationalidcard"></a><span data-ttu-id="1e7df-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-423">個人數字碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-423">personal numeric code</span></span>
  
<span data-ttu-id="1e7df-424">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-424">unique identification number</span></span>
  
<span data-ttu-id="1e7df-425">市民健保號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-425">citizen service number</span></span>
  
<span data-ttu-id="1e7df-426">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-426">unique identity number</span></span>
  
<span data-ttu-id="1e7df-427">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="1e7df-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="1e7df-428">kodiċi numerali personali</span><span class="sxs-lookup"><span data-stu-id="1e7df-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="1e7df-429">numru 東西 ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="1e7df-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="1e7df-430">numru tas servizz taċ ċittadin</span><span class="sxs-lookup"><span data-stu-id="1e7df-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="1e7df-431">numru 東西 ' identità uniku</span><span class="sxs-lookup"><span data-stu-id="1e7df-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="1e7df-432">荷蘭</span><span class="sxs-lookup"><span data-stu-id="1e7df-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-433">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-433">Format</span></span>

<span data-ttu-id="1e7df-434">不含空格或分隔符號的九個位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-435">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-435">Pattern</span></span>

<span data-ttu-id="1e7df-436">九位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1e7df-437">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-437">Checksum</span></span>

<span data-ttu-id="1e7df-438">是</span><span class="sxs-lookup"><span data-stu-id="1e7df-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-439">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-439">Definition</span></span>

<span data-ttu-id="1e7df-440">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-441">此函數`Func_netherlands_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-442">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-442">A keyword from is found.</span></span>
    
<span data-ttu-id="1e7df-443">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-444">此函數`Func_netherlands_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-445">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-445">Keywords</span></span>

#### <a name="keywordsnetherlandseunationalidcard"></a><span data-ttu-id="1e7df-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-447">個人數字碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-447">personal numeric code</span></span>
  
<span data-ttu-id="1e7df-448">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-448">unique identification number</span></span>
  
<span data-ttu-id="1e7df-449">市民健保號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-449">citizen service number</span></span>
  
<span data-ttu-id="1e7df-450">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-450">unique identity number</span></span>
  
<span data-ttu-id="1e7df-451">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="1e7df-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="1e7df-452">bsn</span><span class="sxs-lookup"><span data-stu-id="1e7df-452">bsn</span></span>
  
<span data-ttu-id="1e7df-453">bsn #</span><span class="sxs-lookup"><span data-stu-id="1e7df-453">bsn#</span></span>
  
<span data-ttu-id="1e7df-454">persoonlijke numerieke 程式碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="1e7df-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="1e7df-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="1e7df-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="1e7df-456">burgerservicenummer</span></span>
  
<span data-ttu-id="1e7df-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="1e7df-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="1e7df-458">波蘭</span><span class="sxs-lookup"><span data-stu-id="1e7df-458">Poland</span></span>

<span data-ttu-id="1e7df-459">如需詳細資訊，請參閱節"波蘭國家識別碼 (PESEL)"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7df-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="1e7df-460">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="1e7df-460">Portugal</span></span>

<span data-ttu-id="1e7df-461">如需詳細資訊，請參閱節"葡萄牙市民卡卡號"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7df-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="1e7df-462">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="1e7df-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-463">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-463">Format</span></span>

<span data-ttu-id="1e7df-464">不含空格和分隔字元 13 數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-465">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-465">Pattern</span></span>

<span data-ttu-id="1e7df-466">13 位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1e7df-467">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-467">Checksum</span></span>

<span data-ttu-id="1e7df-468">是</span><span class="sxs-lookup"><span data-stu-id="1e7df-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-469">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-469">Definition</span></span>

<span data-ttu-id="1e7df-470">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-471">此函數`Func_romania_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-472">從關鍵字`Keywords_romania_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="1e7df-473">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-474">此函數`Func_romania_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-475">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-475">Keywords</span></span>

#### <a name="keywordsromaniaeunationalidcard"></a><span data-ttu-id="1e7df-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-477">個人數字碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-477">personal numeric code</span></span>
  
<span data-ttu-id="1e7df-478">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-478">unique identification number</span></span>
  
<span data-ttu-id="1e7df-479">cnp</span><span class="sxs-lookup"><span data-stu-id="1e7df-479">cnp</span></span>
  
<span data-ttu-id="1e7df-480">cnp #</span><span class="sxs-lookup"><span data-stu-id="1e7df-480">cnp#</span></span>
  
<span data-ttu-id="1e7df-481">釘選</span><span class="sxs-lookup"><span data-stu-id="1e7df-481">pin</span></span>
  
<span data-ttu-id="1e7df-482">pin #</span><span class="sxs-lookup"><span data-stu-id="1e7df-482">pin#</span></span>
  
<span data-ttu-id="1e7df-483">保險數目</span><span class="sxs-lookup"><span data-stu-id="1e7df-483">insurance number</span></span>
  
<span data-ttu-id="1e7df-484">insurancenumber #</span><span class="sxs-lookup"><span data-stu-id="1e7df-484">insurancenumber#</span></span>
  
<span data-ttu-id="1e7df-485">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-485">unique identity number</span></span>
  
<span data-ttu-id="1e7df-486">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="1e7df-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="1e7df-487">cod 數值個人</span><span class="sxs-lookup"><span data-stu-id="1e7df-487">cod numeric personal</span></span>
  
<span data-ttu-id="1e7df-488">cod identificare 個人</span><span class="sxs-lookup"><span data-stu-id="1e7df-488">cod identificare personal</span></span>
  
<span data-ttu-id="1e7df-489">cod unic identificare</span><span class="sxs-lookup"><span data-stu-id="1e7df-489">cod unic identificare</span></span>
  
<span data-ttu-id="1e7df-490">număr 個人 unic</span><span class="sxs-lookup"><span data-stu-id="1e7df-490">număr personal unic</span></span>
  
<span data-ttu-id="1e7df-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="1e7df-491">număr identitate</span></span>
  
<span data-ttu-id="1e7df-492">număr identificare 個人</span><span class="sxs-lookup"><span data-stu-id="1e7df-492">număr identificare personal</span></span>
  
<span data-ttu-id="1e7df-493">număridentitate #</span><span class="sxs-lookup"><span data-stu-id="1e7df-493">număridentitate#</span></span>
  
<span data-ttu-id="1e7df-494">codnumericpersonal #</span><span class="sxs-lookup"><span data-stu-id="1e7df-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="1e7df-495">numărpersonalunic #</span><span class="sxs-lookup"><span data-stu-id="1e7df-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="1e7df-496">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="1e7df-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-497">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-497">Format</span></span>

<span data-ttu-id="1e7df-498">包含一個反斜線的十位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-499">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-499">Pattern</span></span>

<span data-ttu-id="1e7df-500">包含一個反斜線十位數：</span><span class="sxs-lookup"><span data-stu-id="1e7df-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1e7df-501">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-501">Checksum</span></span>

<span data-ttu-id="1e7df-502">是</span><span class="sxs-lookup"><span data-stu-id="1e7df-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-503">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-503">Definition</span></span>

<span data-ttu-id="1e7df-504">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-505">此函數`Func_slovakia_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-506">從關鍵字`Keywords_slovakia_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="1e7df-507">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-508">此函數`Func_slovakia_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-509">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-509">Keywords</span></span>

#### <a name="keywordsslovakiaeunationalidcard"></a><span data-ttu-id="1e7df-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-511">出生數目</span><span class="sxs-lookup"><span data-stu-id="1e7df-511">birth number</span></span>
  
<span data-ttu-id="1e7df-512">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-512">national identification number</span></span>
  
<span data-ttu-id="1e7df-513">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-513">personal identification number</span></span>
  
<span data-ttu-id="1e7df-514">social security number
</span><span class="sxs-lookup"><span data-stu-id="1e7df-514">social security number</span></span>
  
<span data-ttu-id="1e7df-515">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="1e7df-515">nationalnumber#</span></span>
  
<span data-ttu-id="1e7df-516">ssn #</span><span class="sxs-lookup"><span data-stu-id="1e7df-516">ssn#</span></span>
  
<span data-ttu-id="1e7df-517">ssn</span><span class="sxs-lookup"><span data-stu-id="1e7df-517">ssn</span></span>
  
<span data-ttu-id="1e7df-518">國際號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-518">national number</span></span>
  
<span data-ttu-id="1e7df-519">個人識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-519">personal id number</span></span>
  
<span data-ttu-id="1e7df-520">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="1e7df-520">personalidnumber#</span></span>
  
<span data-ttu-id="1e7df-521">rč</span><span class="sxs-lookup"><span data-stu-id="1e7df-521">rč</span></span>
  
<span data-ttu-id="1e7df-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="1e7df-522">rodné číslo</span></span>
  
<span data-ttu-id="1e7df-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="1e7df-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="1e7df-524">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="1e7df-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-525">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-525">Format</span></span>

<span data-ttu-id="1e7df-526">不含空格或分隔字元 13 數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-527">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-527">Pattern</span></span>

<span data-ttu-id="1e7df-528">在指定的型態的數字 13:</span><span class="sxs-lookup"><span data-stu-id="1e7df-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="1e7df-529">會對應至出生日期 (DDMMLLL)"LLL"對應至最後一出生年的三個字的七位數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="1e7df-530">會對應至出生的區域的兩位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="1e7df-531">針對的人員在同一天 (000-為 2 男的 499) 和 500 位 999 的女性出生對應的性別與序號組合的三個位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="1e7df-532">一次檢查數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1e7df-533">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-533">Checksum</span></span>

<span data-ttu-id="1e7df-534">是</span><span class="sxs-lookup"><span data-stu-id="1e7df-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-535">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-535">Definition</span></span>

<span data-ttu-id="1e7df-536">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 85%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-537">此函數`Func_slovenia_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-538">從關鍵字`Keywords_slovenia_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="1e7df-539">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-540">此函數`Func_slovenia_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-541">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-541">Keywords</span></span>

#### <a name="keywordssloveniaeunationalidcard"></a><span data-ttu-id="1e7df-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-543">個人數字碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-543">personal numeric code</span></span>
  
<span data-ttu-id="1e7df-544">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-544">unique identification number</span></span>
  
<span data-ttu-id="1e7df-545">註冊的唯一號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-545">unique registration number</span></span>
  
<span data-ttu-id="1e7df-546">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-546">unique identity number</span></span>
  
<span data-ttu-id="1e7df-547">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="1e7df-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="1e7df-548">唯一的主要市民數</span><span class="sxs-lookup"><span data-stu-id="1e7df-548">unique master citizen number</span></span>
  
<span data-ttu-id="1e7df-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="1e7df-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="1e7df-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="1e7df-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="1e7df-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="1e7df-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="1e7df-552">emšo</span><span class="sxs-lookup"><span data-stu-id="1e7df-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="1e7df-553">西班牙</span><span class="sxs-lookup"><span data-stu-id="1e7df-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="1e7df-554">格式</span><span class="sxs-lookup"><span data-stu-id="1e7df-554">Format</span></span>

<span data-ttu-id="1e7df-555">後面接著一個字元的七位數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1e7df-556">模式</span><span class="sxs-lookup"><span data-stu-id="1e7df-556">Pattern</span></span>

<span data-ttu-id="1e7df-557">後面接著一個字元的七位數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="1e7df-558">七位數</span><span class="sxs-lookup"><span data-stu-id="1e7df-558">Seven digits</span></span>
    
- <span data-ttu-id="1e7df-559">一個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="1e7df-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1e7df-560">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-560">Checksum</span></span>

<span data-ttu-id="1e7df-561">不適用</span><span class="sxs-lookup"><span data-stu-id="1e7df-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1e7df-562">定義</span><span class="sxs-lookup"><span data-stu-id="1e7df-562">Definition</span></span>

<span data-ttu-id="1e7df-563">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="1e7df-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1e7df-564">規則運算式`Regex_spain_eu_national_id_card`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7df-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1e7df-565">從關鍵字`Keywords_spain_eu_national_id_card"`找到。</span><span class="sxs-lookup"><span data-stu-id="1e7df-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1e7df-566">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1e7df-566">Keywords</span></span>

#### <a name="keywordsspaineunationalidcard"></a><span data-ttu-id="1e7df-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="1e7df-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="1e7df-568">dni</span><span class="sxs-lookup"><span data-stu-id="1e7df-568">dni</span></span>
  
<span data-ttu-id="1e7df-569">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-569">national identification number</span></span>
  
<span data-ttu-id="1e7df-570">國民身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-570">national identity number</span></span>
  
<span data-ttu-id="1e7df-571">保險數目</span><span class="sxs-lookup"><span data-stu-id="1e7df-571">insurance number</span></span>
  
<span data-ttu-id="1e7df-572">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1e7df-572">personal identification number</span></span>
  
<span data-ttu-id="1e7df-573">國民身分識別</span><span class="sxs-lookup"><span data-stu-id="1e7df-573">national identity</span></span>
  
<span data-ttu-id="1e7df-574">個人身分識別沒有</span><span class="sxs-lookup"><span data-stu-id="1e7df-574">personal identity no</span></span>
  
<span data-ttu-id="1e7df-575">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="1e7df-575">unique identity number</span></span>
  
<span data-ttu-id="1e7df-576">nationalidno #</span><span class="sxs-lookup"><span data-stu-id="1e7df-576">nationalidno#</span></span>
  
<span data-ttu-id="1e7df-577">uniqueid #</span><span class="sxs-lookup"><span data-stu-id="1e7df-577">uniqueid#</span></span>
  
<span data-ttu-id="1e7df-578">dni #</span><span class="sxs-lookup"><span data-stu-id="1e7df-578">dni#</span></span>
  
<span data-ttu-id="1e7df-579">nationalid #</span><span class="sxs-lookup"><span data-stu-id="1e7df-579">nationalid#</span></span>
  
<span data-ttu-id="1e7df-580">nie #</span><span class="sxs-lookup"><span data-stu-id="1e7df-580">nie#</span></span>
  
<span data-ttu-id="1e7df-581">nie</span><span class="sxs-lookup"><span data-stu-id="1e7df-581">nie</span></span>
  
<span data-ttu-id="1e7df-582">nienúmero #</span><span class="sxs-lookup"><span data-stu-id="1e7df-582">nienúmero#</span></span>
  
<span data-ttu-id="1e7df-583">nie número</span><span class="sxs-lookup"><span data-stu-id="1e7df-583">nie número</span></span>
  
<span data-ttu-id="1e7df-584">documento nacional de identidad</span><span class="sxs-lookup"><span data-stu-id="1e7df-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="1e7df-585">identidad único</span><span class="sxs-lookup"><span data-stu-id="1e7df-585">identidad único</span></span>
  
<span data-ttu-id="1e7df-586">número nacional identidad</span><span class="sxs-lookup"><span data-stu-id="1e7df-586">número nacional identidad</span></span>
  
<span data-ttu-id="1e7df-587">dni número</span><span class="sxs-lookup"><span data-stu-id="1e7df-587">dni número</span></span>
  
<span data-ttu-id="1e7df-588">dninúmero #</span><span class="sxs-lookup"><span data-stu-id="1e7df-588">dninúmero#</span></span>
  
<span data-ttu-id="1e7df-589">identidadúnico #</span><span class="sxs-lookup"><span data-stu-id="1e7df-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="1e7df-590">瑞典</span><span class="sxs-lookup"><span data-stu-id="1e7df-590">Sweden</span></span>

<span data-ttu-id="1e7df-591">如需詳細資訊，請參閱節"瑞典國民身分證號"中[尋找敏感資訊類型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7df-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1e7df-592">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1e7df-592">See also</span></span>

[<span data-ttu-id="1e7df-593">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="1e7df-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

