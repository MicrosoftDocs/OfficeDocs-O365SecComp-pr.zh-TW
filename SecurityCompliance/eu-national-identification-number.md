---
title: 歐盟國家識別碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟國民身分識別號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: 205019d040648f0600f3dbf4403063edf9f31c41
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154455"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="0ddbc-104">歐盟國家識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-104">EU National Identification Number</span></span>

<span data-ttu-id="0ddbc-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟國民身分識別號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type.</span></span> <span data-ttu-id="0ddbc-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="0ddbc-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="0ddbc-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-108">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-108">Format</span></span>

<span data-ttu-id="0ddbc-109">24 個字元組合的字母、 數字和特殊字元</span><span class="sxs-lookup"><span data-stu-id="0ddbc-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-110">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-110">Pattern</span></span>

<span data-ttu-id="0ddbc-111">24 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-111">24 characters:</span></span>
  
-  <span data-ttu-id="0ddbc-112">22 字母 （不區分大小寫）、 數字、 反斜線、 正斜線或加號</span><span class="sxs-lookup"><span data-stu-id="0ddbc-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="0ddbc-113">兩個字母 （不區分大小寫）、 數字、 反斜線、 正斜線、 加號或等號</span><span class="sxs-lookup"><span data-stu-id="0ddbc-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ddbc-114">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-114">Checksum</span></span>

<span data-ttu-id="0ddbc-115">不適用</span><span class="sxs-lookup"><span data-stu-id="0ddbc-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-116">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-116">Definition</span></span>

<span data-ttu-id="0ddbc-117">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-118">規則運算式`Regex_austria_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-119">從關鍵字`Keywords_austria_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ddbc-120">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-120">Keywords</span></span>

#### <a name="keywordsaustriaeunationalidcard"></a><span data-ttu-id="0ddbc-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-122">奧地利身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-122">austrian identity number</span></span>
  
<span data-ttu-id="0ddbc-123">國民身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-123">national identity number</span></span>
  
<span data-ttu-id="0ddbc-124">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-124">identity number</span></span>
  
<span data-ttu-id="0ddbc-125">國民身分證</span><span class="sxs-lookup"><span data-stu-id="0ddbc-125">national id</span></span>
  
<span data-ttu-id="0ddbc-126">personalausweis republik österreich</span><span class="sxs-lookup"><span data-stu-id="0ddbc-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="0ddbc-127">比利時</span><span class="sxs-lookup"><span data-stu-id="0ddbc-127">Belgium</span></span>

<span data-ttu-id="0ddbc-128">如需詳細資訊，請參閱 「 比利時國民編碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="0ddbc-129">保加利亞</span><span class="sxs-lookup"><span data-stu-id="0ddbc-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-130">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-130">Format</span></span>

<span data-ttu-id="0ddbc-131">如果沒有空格和分隔符號十位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-132">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-132">Pattern</span></span>

<span data-ttu-id="0ddbc-133">如果沒有空格和分隔符號十位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="0ddbc-134">會對應至 (YYMMDD) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="0ddbc-135">對應至出生順序的兩位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="0ddbc-136">會對應至性別的一個數字： 1 女 2 男和女性奇數數字偶數數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="0ddbc-137">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ddbc-138">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-138">Checksum</span></span>

<span data-ttu-id="0ddbc-139">是</span><span class="sxs-lookup"><span data-stu-id="0ddbc-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-140">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-140">Definition</span></span>

<span data-ttu-id="0ddbc-141">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-142">函式`Func_bulgaria_national_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-143">從關鍵字`Keywords_bulgaria_national_number`找到。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="0ddbc-144">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-145">函式`Func_bulgaria_national_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="0ddbc-146">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-146">Keywords</span></span>

#### <a name="keywordsbulgarianationalnumber"></a><span data-ttu-id="0ddbc-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="0ddbc-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="0ddbc-148">egn</span><span class="sxs-lookup"><span data-stu-id="0ddbc-148">egn</span></span>
  
<span data-ttu-id="0ddbc-149">egn #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-149">egn#</span></span>
  
<span data-ttu-id="0ddbc-150">保加利亞文的國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-150">bulgarian national number</span></span>
  
<span data-ttu-id="0ddbc-151">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-151">national number</span></span>
  
<span data-ttu-id="0ddbc-152">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-152">social security number</span></span>
  
<span data-ttu-id="0ddbc-153">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-153">nationalnumber#</span></span>
  
<span data-ttu-id="0ddbc-154">ssn #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-154">ssn#</span></span>
  
<span data-ttu-id="0ddbc-155">ssn</span><span class="sxs-lookup"><span data-stu-id="0ddbc-155">ssn</span></span>
  
<span data-ttu-id="0ddbc-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="0ddbc-156">nationalnumber</span></span>
  
<span data-ttu-id="0ddbc-157">bnn #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-157">bnn#</span></span>
  
<span data-ttu-id="0ddbc-158">bnn</span><span class="sxs-lookup"><span data-stu-id="0ddbc-158">bnn</span></span>
  
<span data-ttu-id="0ddbc-159">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-159">personal id number</span></span>
  
<span data-ttu-id="0ddbc-160">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-160">personalidnumber#</span></span>
  
<span data-ttu-id="0ddbc-161">ЕДИНЕН ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="0ddbc-161">единен граждански номер</span></span>
  
<span data-ttu-id="0ddbc-162">edinen grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="0ddbc-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="0ddbc-163">ЕГН</span><span class="sxs-lookup"><span data-stu-id="0ddbc-163">егн</span></span>
  
<span data-ttu-id="0ddbc-164">ЕГН #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="0ddbc-165">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="0ddbc-165">Croatia</span></span>

<span data-ttu-id="0ddbc-166">如需詳細資訊，請參閱 「 克羅埃西亞身分識別號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="0ddbc-167">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="0ddbc-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-168">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-168">Format</span></span>

<span data-ttu-id="0ddbc-169">如果沒有空格和分隔符號十位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-170">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-170">Pattern</span></span>

 <span data-ttu-id="0ddbc-171">十位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="0ddbc-172">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-172">Checksum</span></span>

<span data-ttu-id="0ddbc-173">不適用</span><span class="sxs-lookup"><span data-stu-id="0ddbc-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-174">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-174">Definition</span></span>

<span data-ttu-id="0ddbc-175">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-176">規則運算式`Regex_cyprus_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-177">從關鍵字`Keywords_cyprus_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ddbc-178">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-178">Keywords</span></span>

#### <a name="keywordscypruseunationalidcard"></a><span data-ttu-id="0ddbc-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-180">證號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-180">id card number</span></span>
  
<span data-ttu-id="0ddbc-181">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-181">national identification number</span></span>
  
<span data-ttu-id="0ddbc-182">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-182">personal id number</span></span>
  
<span data-ttu-id="0ddbc-183">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-183">identity card number</span></span>
  
<span data-ttu-id="0ddbc-184">ΤΑΥΤΟΤΗΤΑΣ</span><span class="sxs-lookup"><span data-stu-id="0ddbc-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="0ddbc-185">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="0ddbc-185">Czech Republic</span></span>

<span data-ttu-id="0ddbc-186">如需詳細資訊，請參閱 「 捷克國民身分識別號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="0ddbc-187">丹麥</span><span class="sxs-lookup"><span data-stu-id="0ddbc-187">Denmark</span></span>

<span data-ttu-id="0ddbc-188">如需詳細資訊，請參閱 「 丹麥個人識別碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="0ddbc-189">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="0ddbc-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-190">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-190">Format</span></span>

<span data-ttu-id="0ddbc-191">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="0ddbc-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-192">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-192">Pattern</span></span>

<span data-ttu-id="0ddbc-193">11 位數：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-193">11 digits:</span></span>
  
- <span data-ttu-id="0ddbc-194">會對應至性別和世紀的出生的一個數字 (奇數數字 1 女 2 男、 偶數 [女; 1-2: 19 世紀; 3-4: 20 世紀; 5-6： 第 21 世紀)</span><span class="sxs-lookup"><span data-stu-id="0ddbc-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="0ddbc-195">會對應至 (YYMMDD) 出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="0ddbc-196">會對應至分隔出生日期相同的人員序號的三位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="0ddbc-197">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ddbc-198">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-198">Checksum</span></span>

<span data-ttu-id="0ddbc-199">是</span><span class="sxs-lookup"><span data-stu-id="0ddbc-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-200">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-200">Definition</span></span>

<span data-ttu-id="0ddbc-201">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-202">函式`Func_estonia_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-203">從關鍵字`Keywords_estonia_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="0ddbc-204">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-205">函式`Func_estonia_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="0ddbc-206">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-206">Keywords</span></span>

#### <a name="keywordsestoniaeunationalidcard"></a><span data-ttu-id="0ddbc-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-208">個人識別碼的程式碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-208">personal identification code</span></span>
  
<span data-ttu-id="0ddbc-209">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-209">personal identification number</span></span>
  
<span data-ttu-id="0ddbc-210">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-210">national identification number</span></span>
  
<span data-ttu-id="0ddbc-211">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-211">national number</span></span>
  
<span data-ttu-id="0ddbc-212">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-212">personal id number</span></span>
  
<span data-ttu-id="0ddbc-213">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-213">personalidnumber#</span></span>
  
<span data-ttu-id="0ddbc-214">ik</span><span class="sxs-lookup"><span data-stu-id="0ddbc-214">ik</span></span>
  
<span data-ttu-id="0ddbc-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="0ddbc-215">isikukood</span></span>
  
<span data-ttu-id="0ddbc-216">識別碼 kaart</span><span class="sxs-lookup"><span data-stu-id="0ddbc-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="0ddbc-217">芬蘭</span><span class="sxs-lookup"><span data-stu-id="0ddbc-217">Finland</span></span>

<span data-ttu-id="0ddbc-218">如需詳細資訊，請參閱 「 芬蘭國民身分證 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="0ddbc-219">法國</span><span class="sxs-lookup"><span data-stu-id="0ddbc-219">France</span></span>

<span data-ttu-id="0ddbc-220">如需詳細資訊，請參閱 「 法國國民身分證 (CNI) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="0ddbc-221">德國</span><span class="sxs-lookup"><span data-stu-id="0ddbc-221">Germany</span></span>

<span data-ttu-id="0ddbc-222">如需詳細資訊，請參閱 「 德國身分證號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="0ddbc-223">希臘</span><span class="sxs-lookup"><span data-stu-id="0ddbc-223">Greece</span></span>

<span data-ttu-id="0ddbc-224">如需詳細資訊，請參閱 「 希臘國民身分證 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="0ddbc-225">匈牙利</span><span class="sxs-lookup"><span data-stu-id="0ddbc-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-226">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-226">Format</span></span>

<span data-ttu-id="0ddbc-227">11 位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-228">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-228">Pattern</span></span>

<span data-ttu-id="0ddbc-229">11 位數：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-229">11 digits:</span></span>
  
-  <span data-ttu-id="0ddbc-230">會對應至性別 （1-1 女 2 男 2 女性、 其他的數字是也可能公民出生 1900年之前或具有雙公民公民） 的一個數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="0ddbc-231">會對應至 (YYMMDD) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="0ddbc-232">會對應至序號的三位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="0ddbc-233">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ddbc-234">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-234">Checksum</span></span>

<span data-ttu-id="0ddbc-235">是</span><span class="sxs-lookup"><span data-stu-id="0ddbc-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-236">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-236">Definition</span></span>

<span data-ttu-id="0ddbc-237">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-238">函式`Func_hungary_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-239">從關鍵字`Keywords_hungary_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="0ddbc-240">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-241">函式`Func_hungary_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="0ddbc-242">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-242">Keywords</span></span>

#### <a name="keywordshungaryeunationalidcard"></a><span data-ttu-id="0ddbc-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-244">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-244">personal identification number</span></span>
  
<span data-ttu-id="0ddbc-245">識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-245">identification number</span></span>
  
<span data-ttu-id="0ddbc-246">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-246">personal id number</span></span>
  
<span data-ttu-id="0ddbc-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="0ddbc-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="0ddbc-248">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="0ddbc-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-249">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-249">Format</span></span>

<span data-ttu-id="0ddbc-250">九個字元字母、 數字，與組合中所指定的型態的空間</span><span class="sxs-lookup"><span data-stu-id="0ddbc-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-251">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-251">Pattern</span></span>

<span data-ttu-id="0ddbc-252">九個字元字母、 數字，與組合中所指定的型態的空間</span><span class="sxs-lookup"><span data-stu-id="0ddbc-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="0ddbc-253">從 01 到現在的年 1 月 2013:</span><span class="sxs-lookup"><span data-stu-id="0ddbc-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="0ddbc-254">七位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-254">Seven digits</span></span> 
    
- <span data-ttu-id="0ddbc-255">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-255">One check digit</span></span>
    
- <span data-ttu-id="0ddbc-256">一個空格或大寫字母"W"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="0ddbc-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="0ddbc-257">之前 01 年 1 月 2013:</span><span class="sxs-lookup"><span data-stu-id="0ddbc-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="0ddbc-258">七位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-258">Seven digits</span></span> 
    
- <span data-ttu-id="0ddbc-259">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-259">One check digit</span></span>
    
- <span data-ttu-id="0ddbc-260">一個空格或大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="0ddbc-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ddbc-261">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-261">Checksum</span></span>

<span data-ttu-id="0ddbc-262">是</span><span class="sxs-lookup"><span data-stu-id="0ddbc-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-263">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-263">Definition</span></span>

<span data-ttu-id="0ddbc-264">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-265">函數找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="0ddbc-266">找到來自於關鍵字。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-266">A keyword from is found.</span></span>
    
<span data-ttu-id="0ddbc-267">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-268">函數找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-268">The function finds content that matches the pattern.</span></span>
    
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

### <a name="keywords"></a><span data-ttu-id="0ddbc-269">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-269">Keywords</span></span>

#### <a name="keywordsirelandeunationalidcard"></a><span data-ttu-id="0ddbc-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-271">個人公用服務號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-271">personal public service number</span></span>
  
<span data-ttu-id="0ddbc-272">pps 沒有</span><span class="sxs-lookup"><span data-stu-id="0ddbc-272">pps no</span></span>
  
<span data-ttu-id="0ddbc-273">收益及社會保險號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="0ddbc-274">rsi 不</span><span class="sxs-lookup"><span data-stu-id="0ddbc-274">rsi no</span></span>
  
<span data-ttu-id="0ddbc-275">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-275">personal identification number</span></span>
  
<span data-ttu-id="0ddbc-276">識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-276">identification number</span></span>
  
<span data-ttu-id="0ddbc-277">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-277">personal id number</span></span>
  
<span data-ttu-id="0ddbc-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="0ddbc-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="0ddbc-279">uimh。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-279">uimh.</span></span> <span data-ttu-id="0ddbc-280">psp</span><span class="sxs-lookup"><span data-stu-id="0ddbc-280">psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="0ddbc-281">義大利</span><span class="sxs-lookup"><span data-stu-id="0ddbc-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-282">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-282">Format</span></span>

<span data-ttu-id="0ddbc-283">字母和數字中指定的型態的 16 個字元組合</span><span class="sxs-lookup"><span data-stu-id="0ddbc-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-284">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-284">Pattern</span></span>

<span data-ttu-id="0ddbc-285">字母和數字 16 個字元組合：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="0ddbc-286">會對應到前三個母音系列名稱中的三個字母</span><span class="sxs-lookup"><span data-stu-id="0ddbc-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="0ddbc-287">會對應至第一、 第三個和第四個的三個字母母音在名字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="0ddbc-288">會對應至最後一位數的出生年份的兩位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="0ddbc-289">對應於信件的出生的月份的一個字母 — 字母可用依字母順序，但只字母 A 到 E、 H、 L、 M、 P、 R 以 T 可用 （因此，一月是的而且年 10 月 R）</span><span class="sxs-lookup"><span data-stu-id="0ddbc-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="0ddbc-290">會對應至出生的月份日期的兩位數 — 為了區別 genders，40 會新增至的女性的出生日期</span><span class="sxs-lookup"><span data-stu-id="0ddbc-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="0ddbc-291">會對應至 municipality 出生之人員的特定區域的程式碼的四個位數 （國家/地區全代碼用於外部國家/地區提供）</span><span class="sxs-lookup"><span data-stu-id="0ddbc-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="0ddbc-292">一個同位檢查數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ddbc-293">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-293">Checksum</span></span>

<span data-ttu-id="0ddbc-294">是</span><span class="sxs-lookup"><span data-stu-id="0ddbc-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-295">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-295">Definition</span></span>

<span data-ttu-id="0ddbc-296">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-297">函式`Func_italy_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-298">從關鍵字`Keywords_italy_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="0ddbc-299">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-300">函式`Func_italy_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="0ddbc-301">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-301">Keywords</span></span>

#### <a name="keywordsitalyeunationalidcard"></a><span data-ttu-id="0ddbc-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-303">個人的程式碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-303">personal code</span></span>
  
<span data-ttu-id="0ddbc-304">個人代碼數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-304">personal code number</span></span>
  
<span data-ttu-id="0ddbc-305">個人的憑證數目</span><span class="sxs-lookup"><span data-stu-id="0ddbc-305">personal certificate number</span></span>
  
<span data-ttu-id="0ddbc-306">會計年度的程式碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-306">fiscal code</span></span>
  
<span data-ttu-id="0ddbc-307">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-307">personalcodeno#</span></span>
  
<span data-ttu-id="0ddbc-308">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-308">personal id number</span></span>
  
<span data-ttu-id="0ddbc-309">個人識別碼的程式碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-309">personal id code</span></span>
  
<span data-ttu-id="0ddbc-310">codice personale</span><span class="sxs-lookup"><span data-stu-id="0ddbc-310">codice personale</span></span>
  
<span data-ttu-id="0ddbc-311">numero certificato personale</span><span class="sxs-lookup"><span data-stu-id="0ddbc-311">numero certificato personale</span></span>
  
<span data-ttu-id="0ddbc-312">numero personale</span><span class="sxs-lookup"><span data-stu-id="0ddbc-312">numero personale</span></span>
  
<span data-ttu-id="0ddbc-313">numero 識別碼 personale</span><span class="sxs-lookup"><span data-stu-id="0ddbc-313">numero id personale</span></span>
  
<span data-ttu-id="0ddbc-314">codice 識別碼 personale</span><span class="sxs-lookup"><span data-stu-id="0ddbc-314">codice id personale</span></span>
  
<span data-ttu-id="0ddbc-315">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="0ddbc-315">codice fiscale</span></span>
  
## <a name="italy"></a><span data-ttu-id="0ddbc-316">義大利</span><span class="sxs-lookup"><span data-stu-id="0ddbc-316">Italy</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-317">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-317">Format</span></span>

<span data-ttu-id="0ddbc-318">11 個數字和以指定的格式為連字號</span><span class="sxs-lookup"><span data-stu-id="0ddbc-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-319">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-319">Pattern</span></span>

<span data-ttu-id="0ddbc-320">11 位數，並連字號：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="0ddbc-321">會對應至 (DDMMYY) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="0ddbc-322">連字號</span><span class="sxs-lookup"><span data-stu-id="0ddbc-322">A hyphen</span></span>
    
- <span data-ttu-id="0ddbc-323">會對應至的出生 （"0"19 世紀的、 20 世紀的"1"和"2"的第 21 世紀） 世紀的一個數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="0ddbc-324">四位數，隨機產生</span><span class="sxs-lookup"><span data-stu-id="0ddbc-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ddbc-325">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-325">Checksum</span></span>

<span data-ttu-id="0ddbc-326">是</span><span class="sxs-lookup"><span data-stu-id="0ddbc-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-327">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-327">Definition</span></span>

<span data-ttu-id="0ddbc-328">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-329">函式`Func_latvia_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-330">從關鍵字`Keywords_latvia_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="0ddbc-331">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-332">函式`Func_latvia_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="0ddbc-333">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-333">Keywords</span></span>

#### <a name="keywordslatviaeunationalidcard"></a><span data-ttu-id="0ddbc-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-335">個人的程式碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-335">personal code</span></span>
  
<span data-ttu-id="0ddbc-336">個人代碼數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-336">personal code number</span></span>
  
<span data-ttu-id="0ddbc-337">個人的憑證數目</span><span class="sxs-lookup"><span data-stu-id="0ddbc-337">personal certificate number</span></span>
  
<span data-ttu-id="0ddbc-338">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-338">personalcodeno#</span></span>
  
<span data-ttu-id="0ddbc-339">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-339">personal id number</span></span>
  
<span data-ttu-id="0ddbc-340">個人識別碼的程式碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-340">personal id code</span></span>
  
<span data-ttu-id="0ddbc-341">人物代表 kods</span><span class="sxs-lookup"><span data-stu-id="0ddbc-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="0ddbc-342">立陶宛</span><span class="sxs-lookup"><span data-stu-id="0ddbc-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-343">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-343">Format</span></span>

<span data-ttu-id="0ddbc-344">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="0ddbc-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-345">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-345">Pattern</span></span>

<span data-ttu-id="0ddbc-346">如果沒有空格和分隔符號的 11 位數：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="0ddbc-347">會對應至該人員的性別和世紀的出生的一個數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="0ddbc-348">會對應至 (YYMMDD) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="0ddbc-349">會對應至出生日期序號的三位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="0ddbc-350">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ddbc-351">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-351">Checksum</span></span>

<span data-ttu-id="0ddbc-352">是</span><span class="sxs-lookup"><span data-stu-id="0ddbc-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-353">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-353">Definition</span></span>

<span data-ttu-id="0ddbc-354">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-355">函式`Func_lithuania_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-356">從關鍵字`Keywords_lithuania_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="0ddbc-357">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-358">函式`Func_lithuania_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="0ddbc-359">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-359">Keywords</span></span>

#### <a name="keywordslithuaniaeunationalidcard"></a><span data-ttu-id="0ddbc-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-361">個人數字碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-361">personal numeric code</span></span>
  
<span data-ttu-id="0ddbc-362">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-362">unique identification number</span></span>
  
<span data-ttu-id="0ddbc-363">公民健保號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-363">citizen service number</span></span>
  
<span data-ttu-id="0ddbc-364">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-364">unique identity number</span></span>
  
<span data-ttu-id="0ddbc-365">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="0ddbc-366">個人的程式碼。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-366">personal code.</span></span>
  
<span data-ttu-id="0ddbc-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="0ddbc-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="0ddbc-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="0ddbc-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="0ddbc-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="0ddbc-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="0ddbc-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="0ddbc-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="0ddbc-371">asmens kodas。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="0ddbc-372">盧森堡</span><span class="sxs-lookup"><span data-stu-id="0ddbc-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-373">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-373">Format</span></span>

<span data-ttu-id="0ddbc-374">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="0ddbc-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-375">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-375">Pattern</span></span>

<span data-ttu-id="0ddbc-376">11 位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-376">11 digits</span></span>
  
- <span data-ttu-id="0ddbc-377">會對應至該人員的性別和世紀的出生的一個數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="0ddbc-378">會對應至 (YYMMDD) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="0ddbc-379">會對應至出生日期序號的三位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="0ddbc-380">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ddbc-381">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-381">Checksum</span></span>

<span data-ttu-id="0ddbc-382">不適用</span><span class="sxs-lookup"><span data-stu-id="0ddbc-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-383">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-383">Definition</span></span>

<span data-ttu-id="0ddbc-384">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-385">規則運算式`Regex_luxemburg_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-386">從關鍵字`Keywords_luxemburg_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ddbc-387">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-387">Keywords</span></span>

#### <a name="keywordsluxemburgeunationalidcard"></a><span data-ttu-id="0ddbc-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-389">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-389">personal id</span></span>
  
<span data-ttu-id="0ddbc-390">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-390">personal id number</span></span>
  
<span data-ttu-id="0ddbc-391">personalidno #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-391">personalidno#</span></span>
  
<span data-ttu-id="0ddbc-392">唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-392">unique id number</span></span>
  
<span data-ttu-id="0ddbc-393">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-393">personalidnumber#</span></span>
  
<span data-ttu-id="0ddbc-394">唯一識別碼機碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-394">unique id key</span></span>
  
<span data-ttu-id="0ddbc-395">個人識別碼的程式碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-395">personal id code</span></span>
  
<span data-ttu-id="0ddbc-396">uniqueidkey #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-396">uniqueidkey#</span></span>
  
<span data-ttu-id="0ddbc-397">個別的程式碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-397">individual code</span></span>
  
<span data-ttu-id="0ddbc-398">個別的識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-398">individual id</span></span>
  
<span data-ttu-id="0ddbc-399">eindeutige 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="0ddbc-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="0ddbc-400">eindeutige 識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-400">eindeutige id</span></span>
  
<span data-ttu-id="0ddbc-401">識別碼 personnelle</span><span class="sxs-lookup"><span data-stu-id="0ddbc-401">id personnelle</span></span>
  
<span data-ttu-id="0ddbc-402">numéro d'identification 人員</span><span class="sxs-lookup"><span data-stu-id="0ddbc-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="0ddbc-403">idpersonnelle #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-403">idpersonnelle#</span></span>
  
<span data-ttu-id="0ddbc-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="0ddbc-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="0ddbc-405">eindeutigeid #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="0ddbc-406">馬爾他</span><span class="sxs-lookup"><span data-stu-id="0ddbc-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-407">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-407">Format</span></span>

<span data-ttu-id="0ddbc-408">一個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-409">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-409">Pattern</span></span>

<span data-ttu-id="0ddbc-410">一個字母後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="0ddbc-411">七位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-411">Seven digits</span></span> 
    
- <span data-ttu-id="0ddbc-412">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="0ddbc-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ddbc-413">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-413">Checksum</span></span>

<span data-ttu-id="0ddbc-414">不適用</span><span class="sxs-lookup"><span data-stu-id="0ddbc-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-415">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-415">Definition</span></span>

<span data-ttu-id="0ddbc-416">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-417">規則運算式`Regex_malta_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-418">從關鍵字`Keywords_malta_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="0ddbc-419">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-420">規則運算式`Regex_malta_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="0ddbc-421">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-421">Keywords</span></span>

#### <a name="keywordsmaltaeunationalidcard"></a><span data-ttu-id="0ddbc-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-423">個人數字碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-423">personal numeric code</span></span>
  
<span data-ttu-id="0ddbc-424">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-424">unique identification number</span></span>
  
<span data-ttu-id="0ddbc-425">公民健保號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-425">citizen service number</span></span>
  
<span data-ttu-id="0ddbc-426">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-426">unique identity number</span></span>
  
<span data-ttu-id="0ddbc-427">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="0ddbc-428">kodiċi numerali personali</span><span class="sxs-lookup"><span data-stu-id="0ddbc-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="0ddbc-429">numru 東西 ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="0ddbc-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="0ddbc-430">numru 塔司 servizz taċ ċittadin</span><span class="sxs-lookup"><span data-stu-id="0ddbc-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="0ddbc-431">numru 東西 ' identità uniku</span><span class="sxs-lookup"><span data-stu-id="0ddbc-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="0ddbc-432">荷蘭</span><span class="sxs-lookup"><span data-stu-id="0ddbc-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-433">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-433">Format</span></span>

<span data-ttu-id="0ddbc-434">不含空格或分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-435">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-435">Pattern</span></span>

<span data-ttu-id="0ddbc-436">九位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0ddbc-437">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-437">Checksum</span></span>

<span data-ttu-id="0ddbc-438">是</span><span class="sxs-lookup"><span data-stu-id="0ddbc-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-439">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-439">Definition</span></span>

<span data-ttu-id="0ddbc-440">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-441">函式`Func_netherlands_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-442">找到來自於關鍵字。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-442">A keyword from is found.</span></span>
    
<span data-ttu-id="0ddbc-443">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-444">函式`Func_netherlands_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="0ddbc-445">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-445">Keywords</span></span>

#### <a name="keywordsnetherlandseunationalidcard"></a><span data-ttu-id="0ddbc-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-447">個人數字碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-447">personal numeric code</span></span>
  
<span data-ttu-id="0ddbc-448">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-448">unique identification number</span></span>
  
<span data-ttu-id="0ddbc-449">公民健保號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-449">citizen service number</span></span>
  
<span data-ttu-id="0ddbc-450">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-450">unique identity number</span></span>
  
<span data-ttu-id="0ddbc-451">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="0ddbc-452">bsn</span><span class="sxs-lookup"><span data-stu-id="0ddbc-452">bsn</span></span>
  
<span data-ttu-id="0ddbc-453">bsn #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-453">bsn#</span></span>
  
<span data-ttu-id="0ddbc-454">persoonlijke numerieke 程式碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="0ddbc-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="0ddbc-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="0ddbc-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="0ddbc-456">burgerservicenummer</span></span>
  
<span data-ttu-id="0ddbc-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="0ddbc-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="0ddbc-458">波蘭</span><span class="sxs-lookup"><span data-stu-id="0ddbc-458">Poland</span></span>

<span data-ttu-id="0ddbc-459">如需詳細資訊，請參閱 「 波蘭國家識別碼 (PESEL) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="0ddbc-460">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="0ddbc-460">Portugal</span></span>

<span data-ttu-id="0ddbc-461">如需詳細資訊，請參閱 「 葡萄牙公民證號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="0ddbc-462">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="0ddbc-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-463">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-463">Format</span></span>

<span data-ttu-id="0ddbc-464">如果沒有空格和分隔符號的 13 位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-465">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-465">Pattern</span></span>

<span data-ttu-id="0ddbc-466">13 位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0ddbc-467">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-467">Checksum</span></span>

<span data-ttu-id="0ddbc-468">是</span><span class="sxs-lookup"><span data-stu-id="0ddbc-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-469">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-469">Definition</span></span>

<span data-ttu-id="0ddbc-470">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-471">函式`Func_romania_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-472">從關鍵字`Keywords_romania_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="0ddbc-473">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-474">函式`Func_romania_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="0ddbc-475">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-475">Keywords</span></span>

#### <a name="keywordsromaniaeunationalidcard"></a><span data-ttu-id="0ddbc-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-477">個人數字碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-477">personal numeric code</span></span>
  
<span data-ttu-id="0ddbc-478">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-478">unique identification number</span></span>
  
<span data-ttu-id="0ddbc-479">cnp</span><span class="sxs-lookup"><span data-stu-id="0ddbc-479">cnp</span></span>
  
<span data-ttu-id="0ddbc-480">cnp #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-480">cnp#</span></span>
  
<span data-ttu-id="0ddbc-481">pin 碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-481">pin</span></span>
  
<span data-ttu-id="0ddbc-482">pin 碼 #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-482">pin#</span></span>
  
<span data-ttu-id="0ddbc-483">保險號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-483">insurance number</span></span>
  
<span data-ttu-id="0ddbc-484">insurancenumber #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-484">insurancenumber#</span></span>
  
<span data-ttu-id="0ddbc-485">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-485">unique identity number</span></span>
  
<span data-ttu-id="0ddbc-486">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="0ddbc-487">cod 數值個人</span><span class="sxs-lookup"><span data-stu-id="0ddbc-487">cod numeric personal</span></span>
  
<span data-ttu-id="0ddbc-488">cod identificare 個人</span><span class="sxs-lookup"><span data-stu-id="0ddbc-488">cod identificare personal</span></span>
  
<span data-ttu-id="0ddbc-489">cod unic identificare</span><span class="sxs-lookup"><span data-stu-id="0ddbc-489">cod unic identificare</span></span>
  
<span data-ttu-id="0ddbc-490">număr 個人 unic</span><span class="sxs-lookup"><span data-stu-id="0ddbc-490">număr personal unic</span></span>
  
<span data-ttu-id="0ddbc-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="0ddbc-491">număr identitate</span></span>
  
<span data-ttu-id="0ddbc-492">număr identificare 個人</span><span class="sxs-lookup"><span data-stu-id="0ddbc-492">număr identificare personal</span></span>
  
<span data-ttu-id="0ddbc-493">număridentitate #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-493">număridentitate#</span></span>
  
<span data-ttu-id="0ddbc-494">codnumericpersonal #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="0ddbc-495">numărpersonalunic #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="0ddbc-496">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="0ddbc-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-497">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-497">Format</span></span>

<span data-ttu-id="0ddbc-498">10 位數包含一個反斜線</span><span class="sxs-lookup"><span data-stu-id="0ddbc-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-499">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-499">Pattern</span></span>

<span data-ttu-id="0ddbc-500">10 位數包含一個反斜線：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0ddbc-501">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-501">Checksum</span></span>

<span data-ttu-id="0ddbc-502">是</span><span class="sxs-lookup"><span data-stu-id="0ddbc-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-503">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-503">Definition</span></span>

<span data-ttu-id="0ddbc-504">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-505">函式`Func_slovakia_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-506">從關鍵字`Keywords_slovakia_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="0ddbc-507">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-508">函式`Func_slovakia_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="0ddbc-509">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-509">Keywords</span></span>

#### <a name="keywordsslovakiaeunationalidcard"></a><span data-ttu-id="0ddbc-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-511">出生數目</span><span class="sxs-lookup"><span data-stu-id="0ddbc-511">birth number</span></span>
  
<span data-ttu-id="0ddbc-512">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-512">national identification number</span></span>
  
<span data-ttu-id="0ddbc-513">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-513">personal identification number</span></span>
  
<span data-ttu-id="0ddbc-514">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-514">social security number</span></span>
  
<span data-ttu-id="0ddbc-515">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-515">nationalnumber#</span></span>
  
<span data-ttu-id="0ddbc-516">ssn #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-516">ssn#</span></span>
  
<span data-ttu-id="0ddbc-517">ssn</span><span class="sxs-lookup"><span data-stu-id="0ddbc-517">ssn</span></span>
  
<span data-ttu-id="0ddbc-518">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-518">national number</span></span>
  
<span data-ttu-id="0ddbc-519">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-519">personal id number</span></span>
  
<span data-ttu-id="0ddbc-520">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-520">personalidnumber#</span></span>
  
<span data-ttu-id="0ddbc-521">rč</span><span class="sxs-lookup"><span data-stu-id="0ddbc-521">rč</span></span>
  
<span data-ttu-id="0ddbc-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="0ddbc-522">rodné číslo</span></span>
  
<span data-ttu-id="0ddbc-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="0ddbc-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="0ddbc-524">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="0ddbc-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-525">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-525">Format</span></span>

<span data-ttu-id="0ddbc-526">不含空格或分隔符號的 13 位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-527">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-527">Pattern</span></span>

<span data-ttu-id="0ddbc-528">13 位數，代表所指定的型態：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="0ddbc-529">會對應至出生日期 (DDMMLLL) 」 LLL 」 對應至最後一個三位數的出生年份的七位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="0ddbc-530">會對應至出生的區域中的兩位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="0ddbc-531">在同一天 (000-如 1 女 2 男的 499) 和 500-999 名為女性出生的人會對應至性別及序號的組合的三位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="0ddbc-532">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ddbc-533">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-533">Checksum</span></span>

<span data-ttu-id="0ddbc-534">是</span><span class="sxs-lookup"><span data-stu-id="0ddbc-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-535">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-535">Definition</span></span>

<span data-ttu-id="0ddbc-536">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-537">函式`Func_slovenia_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-538">從關鍵字`Keywords_slovenia_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="0ddbc-539">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-540">函式`Func_slovenia_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="0ddbc-541">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-541">Keywords</span></span>

#### <a name="keywordssloveniaeunationalidcard"></a><span data-ttu-id="0ddbc-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-543">個人數字碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-543">personal numeric code</span></span>
  
<span data-ttu-id="0ddbc-544">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-544">unique identification number</span></span>
  
<span data-ttu-id="0ddbc-545">唯一登記號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-545">unique registration number</span></span>
  
<span data-ttu-id="0ddbc-546">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-546">unique identity number</span></span>
  
<span data-ttu-id="0ddbc-547">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="0ddbc-548">唯一的主版公民數目</span><span class="sxs-lookup"><span data-stu-id="0ddbc-548">unique master citizen number</span></span>
  
<span data-ttu-id="0ddbc-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="0ddbc-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="0ddbc-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="0ddbc-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="0ddbc-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="0ddbc-552">emšo</span><span class="sxs-lookup"><span data-stu-id="0ddbc-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="0ddbc-553">西班牙</span><span class="sxs-lookup"><span data-stu-id="0ddbc-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="0ddbc-554">格式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-554">Format</span></span>

<span data-ttu-id="0ddbc-555">七位數後尾隨一個字元</span><span class="sxs-lookup"><span data-stu-id="0ddbc-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ddbc-556">模式</span><span class="sxs-lookup"><span data-stu-id="0ddbc-556">Pattern</span></span>

<span data-ttu-id="0ddbc-557">七位數後尾隨一個字元</span><span class="sxs-lookup"><span data-stu-id="0ddbc-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="0ddbc-558">七位數</span><span class="sxs-lookup"><span data-stu-id="0ddbc-558">Seven digits</span></span>
    
- <span data-ttu-id="0ddbc-559">一個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="0ddbc-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ddbc-560">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-560">Checksum</span></span>

<span data-ttu-id="0ddbc-561">不適用</span><span class="sxs-lookup"><span data-stu-id="0ddbc-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ddbc-562">定義</span><span class="sxs-lookup"><span data-stu-id="0ddbc-562">Definition</span></span>

<span data-ttu-id="0ddbc-563">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="0ddbc-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ddbc-564">規則運算式`Regex_spain_eu_national_id_card`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ddbc-565">從關鍵字`Keywords_spain_eu_national_id_card"`找到。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ddbc-566">關鍵字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-566">Keywords</span></span>

#### <a name="keywordsspaineunationalidcard"></a><span data-ttu-id="0ddbc-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="0ddbc-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="0ddbc-568">dni</span><span class="sxs-lookup"><span data-stu-id="0ddbc-568">dni</span></span>
  
<span data-ttu-id="0ddbc-569">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-569">national identification number</span></span>
  
<span data-ttu-id="0ddbc-570">國民身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-570">national identity number</span></span>
  
<span data-ttu-id="0ddbc-571">保險號碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-571">insurance number</span></span>
  
<span data-ttu-id="0ddbc-572">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-572">personal identification number</span></span>
  
<span data-ttu-id="0ddbc-573">國民身分識別</span><span class="sxs-lookup"><span data-stu-id="0ddbc-573">national identity</span></span>
  
<span data-ttu-id="0ddbc-574">個人身分識別沒有</span><span class="sxs-lookup"><span data-stu-id="0ddbc-574">personal identity no</span></span>
  
<span data-ttu-id="0ddbc-575">唯一識別數字</span><span class="sxs-lookup"><span data-stu-id="0ddbc-575">unique identity number</span></span>
  
<span data-ttu-id="0ddbc-576">nationalidno #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-576">nationalidno#</span></span>
  
<span data-ttu-id="0ddbc-577">uniqueid #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-577">uniqueid#</span></span>
  
<span data-ttu-id="0ddbc-578">dni #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-578">dni#</span></span>
  
<span data-ttu-id="0ddbc-579">nationalid #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-579">nationalid#</span></span>
  
<span data-ttu-id="0ddbc-580">nie #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-580">nie#</span></span>
  
<span data-ttu-id="0ddbc-581">nie</span><span class="sxs-lookup"><span data-stu-id="0ddbc-581">nie</span></span>
  
<span data-ttu-id="0ddbc-582">nienúmero #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-582">nienúmero#</span></span>
  
<span data-ttu-id="0ddbc-583">nie número</span><span class="sxs-lookup"><span data-stu-id="0ddbc-583">nie número</span></span>
  
<span data-ttu-id="0ddbc-584">documento nacional de identidad</span><span class="sxs-lookup"><span data-stu-id="0ddbc-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="0ddbc-585">identidad único</span><span class="sxs-lookup"><span data-stu-id="0ddbc-585">identidad único</span></span>
  
<span data-ttu-id="0ddbc-586">número nacional identidad</span><span class="sxs-lookup"><span data-stu-id="0ddbc-586">número nacional identidad</span></span>
  
<span data-ttu-id="0ddbc-587">dni número</span><span class="sxs-lookup"><span data-stu-id="0ddbc-587">dni número</span></span>
  
<span data-ttu-id="0ddbc-588">dninúmero #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-588">dninúmero#</span></span>
  
<span data-ttu-id="0ddbc-589">identidadúnico #</span><span class="sxs-lookup"><span data-stu-id="0ddbc-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="0ddbc-590">瑞典</span><span class="sxs-lookup"><span data-stu-id="0ddbc-590">Sweden</span></span>

<span data-ttu-id="0ddbc-591">如需詳細資訊，請參閱 「 瑞典國民身分證 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0ddbc-592">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0ddbc-592">See also</span></span>

[<span data-ttu-id="0ddbc-593">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="0ddbc-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

