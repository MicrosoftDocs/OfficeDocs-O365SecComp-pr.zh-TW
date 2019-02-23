---
title: DLP 功能所尋找的項目
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/18/2016
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 94349ed4-5351-4ee2-bbda-70813c9ed693
description: 敏感資訊類型尋找特定模式與證實來確保適當格式、 強制執行總和檢查碼，以及尋找相關的關鍵字或其他資訊。某些這項功能是由內部函數執行。本主題說明這些函數外觀，以協助您瞭解預先定義的敏感資訊類型的運作方式。
ms.openlocfilehash: 55c740e892e92902b368b2dcf7b0999cbc60f3ed
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219353"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="62d89-105">DLP 功能所尋找的項目</span><span class="sxs-lookup"><span data-stu-id="62d89-105">What the DLP functions look for</span></span>

<span data-ttu-id="62d89-p102">資料外洩防護 (DLP) 包含敏感資訊類型 (例如信用卡號與歐盟轉帳卡號)，您可以將這些類型用於 DLP 原則。這些敏感資訊類型是透過確保適當的格式、強制執行總和檢查碼，以及尋找相關關鍵字與其他資訊來尋找特定模式並加以證實。此部分功能是由內部函數執行。例如，信用卡卡號敏感資訊類型會使用函數尋找類似到期日的日期格式，以協助證實出現的數字的確是信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="62d89-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="62d89-p103">本主題會說明這些函數的功能，讓您能更了解預先定義的敏感資訊類型。如需詳細資訊，請參閱[What the sensitive information types look for](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="62d89-p103">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work. For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="funcusdate"></a><span data-ttu-id="62d89-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="62d89-112">Func_us_date</span></span>

<span data-ttu-id="62d89-p104">此函數會尋找在美國常使用的格式是日期這包括格式"month/日/年 」、 「 月-日-年 」 和 「 月日年 」。名稱或縮寫的月數不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="62d89-p104">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ". The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="62d89-115">範例：</span><span class="sxs-lookup"><span data-stu-id="62d89-115">Examples:</span></span>
  
- <span data-ttu-id="62d89-116">2016 年 12 月 2 日</span><span class="sxs-lookup"><span data-stu-id="62d89-116">December 2, 2016</span></span>
    
- <span data-ttu-id="62d89-117">2016、 Dec 2、</span><span class="sxs-lookup"><span data-stu-id="62d89-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="62d89-118">dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="62d89-118">dec 02 2016</span></span>
    
- <span data-ttu-id="62d89-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="62d89-119">12/2/2016</span></span>
    
- <span data-ttu-id="62d89-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="62d89-120">12/02/16</span></span>
    
- <span data-ttu-id="62d89-121">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="62d89-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="62d89-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="62d89-122">12-2-16</span></span>
    
<span data-ttu-id="62d89-123">接受的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="62d89-123">Accepted month names:</span></span>
  
- <span data-ttu-id="62d89-124">英文</span><span class="sxs-lookup"><span data-stu-id="62d89-124">English</span></span>
    
  - <span data-ttu-id="62d89-125">1 月、 年 2 月、 march、 April、 may、 年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月、 年 12 月</span><span class="sxs-lookup"><span data-stu-id="62d89-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="62d89-126">年 1 月 2005 年 2 月 Mar.2004 年 4 月可能 6 年 7 月 ie Sept.年 10 月 11 Dec。</span><span class="sxs-lookup"><span data-stu-id="62d89-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="funceudate"></a><span data-ttu-id="62d89-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="62d89-127">Func_eu_date</span></span>

<span data-ttu-id="62d89-p105">此函數尋找的是歐盟 (與美國之外大部分地區) 常用的日期格式。這包含了「日/月/年」、「日-月-年」和「日 月 年」的格式。月份的名稱或縮寫不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="62d89-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="62d89-132">範例：</span><span class="sxs-lookup"><span data-stu-id="62d89-132">Examples:</span></span>
  
- <span data-ttu-id="62d89-133">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="62d89-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="62d89-134">02 dec 2016</span><span class="sxs-lookup"><span data-stu-id="62d89-134">02 dec 2016</span></span>
    
- <span data-ttu-id="62d89-135">2 年 12 月 16</span><span class="sxs-lookup"><span data-stu-id="62d89-135">2 Dec 16</span></span>
    
- <span data-ttu-id="62d89-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="62d89-136">2/12/2016</span></span>
    
- <span data-ttu-id="62d89-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="62d89-137">02/12/16</span></span>
    
- <span data-ttu-id="62d89-138">2-Dec-2016</span><span class="sxs-lookup"><span data-stu-id="62d89-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="62d89-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="62d89-139">2-12-16</span></span>
    
<span data-ttu-id="62d89-140">接受的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="62d89-140">Accepted month names:</span></span>
  
- <span data-ttu-id="62d89-141">英文</span><span class="sxs-lookup"><span data-stu-id="62d89-141">English</span></span>
    
  - <span data-ttu-id="62d89-142">1 月、 年 2 月、 march、 April、 may、 年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月、 年 12 月</span><span class="sxs-lookup"><span data-stu-id="62d89-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="62d89-143">年 1 月 2005 年 2 月 Mar.2004 年 4 月可能 6 年 7 月 ie Sept.年 10 月 11 Dec。</span><span class="sxs-lookup"><span data-stu-id="62d89-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="62d89-144">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="62d89-144">Dutch</span></span>
    
  - <span data-ttu-id="62d89-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="62d89-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="62d89-146">jan 2 maart apr mei 6 月 7 月 8 月 sep sept oct okt 11 月 dec</span><span class="sxs-lookup"><span data-stu-id="62d89-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="62d89-147">法文</span><span class="sxs-lookup"><span data-stu-id="62d89-147">French</span></span>
    
  - <span data-ttu-id="62d89-148">janvier、 février、 mars、 avril、 郵件、 juin juillet、 août、 septembre、 octobre、 novembre、 décembre</span><span class="sxs-lookup"><span data-stu-id="62d89-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="62d89-p106">janv。févr。mars avril 郵件 juin juil。août sept。年 10 月 11 月。déc。</span><span class="sxs-lookup"><span data-stu-id="62d89-p106">janv. févr. mars avril mai juin juil. août sept. oct. nov. déc.</span></span>
    
- <span data-ttu-id="62d89-156">德文</span><span class="sxs-lookup"><span data-stu-id="62d89-156">German</span></span>
    
  - <span data-ttu-id="62d89-157">jänuar、 februar、 märz、 April、 郵件、 juni juli 年 8 月、 年 9 月、 oktober，11，dezember</span><span class="sxs-lookup"><span data-stu-id="62d89-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="62d89-p107">Jan。 / Jän。2005 年 2 月 März 2004 年 4 月郵件 Juni Juli ie Sept.Okt。11 Dez。</span><span class="sxs-lookup"><span data-stu-id="62d89-p107">Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span></span>
    
- <span data-ttu-id="62d89-161">義大利文</span><span class="sxs-lookup"><span data-stu-id="62d89-161">Italian</span></span>
    
  - <span data-ttu-id="62d89-162">gennaio、 febbraio、 marzo、 aprile、 maggio、 giugno、 luglio、 agosto、 settembre、 ottobre、 novembre、 dicembre</span><span class="sxs-lookup"><span data-stu-id="62d89-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="62d89-p108">genn。febbr。mar。apr。magg。giugno luglio ag。是家。ott。11 月。dic。</span><span class="sxs-lookup"><span data-stu-id="62d89-p108">genn. febbr. mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.</span></span>
    
- <span data-ttu-id="62d89-173">葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="62d89-173">Portuguese</span></span>
    
  - <span data-ttu-id="62d89-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="62d89-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="62d89-175">jan fev mar abr 郵件 6 月 7 月過去 11 月 dez 出設定</span><span class="sxs-lookup"><span data-stu-id="62d89-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="62d89-176">西班牙文</span><span class="sxs-lookup"><span data-stu-id="62d89-176">Spanish</span></span>
    
  - <span data-ttu-id="62d89-177">enero、 febrero、 marzo、 abril、 mayo、 junio、 羅、 agosto、 septiembre、 octubre、 noviembre、 diciembre</span><span class="sxs-lookup"><span data-stu-id="62d89-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="62d89-p109">enero 2。marzo abr.mayo jun.年 7 月。agosto sept./集。年 10 月 11 月。dic。</span><span class="sxs-lookup"><span data-stu-id="62d89-p109">enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.</span></span>
    
## <a name="funceudate1-deprecated"></a><span data-ttu-id="62d89-186">Func_eu_date1 (已過時)</span><span class="sxs-lookup"><span data-stu-id="62d89-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="62d89-187">因為它可支援僅葡萄牙文月份名稱，現在包含中已被取代此函數`Func_eu_date`上述的函數。</span><span class="sxs-lookup"><span data-stu-id="62d89-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="62d89-p110">此函數會尋找格式通常用於葡萄牙文的日期。此函數的格式是相同`Func_eu_date`、 受限於較只能在所用的語言。</span><span class="sxs-lookup"><span data-stu-id="62d89-p110">This function looks for a date in the format commonly used in Portuguese. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="62d89-190">範例：</span><span class="sxs-lookup"><span data-stu-id="62d89-190">Examples:</span></span>
  
- <span data-ttu-id="62d89-191">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="62d89-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="62d89-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="62d89-192">02 dez 2016</span></span>
    
- <span data-ttu-id="62d89-193">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="62d89-193">2 Dez 16</span></span>
    
- <span data-ttu-id="62d89-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="62d89-194">2/12/2016</span></span>
    
- <span data-ttu-id="62d89-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="62d89-195">02/12/16</span></span>
    
- <span data-ttu-id="62d89-196">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="62d89-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="62d89-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="62d89-197">2-12-16</span></span>
    
<span data-ttu-id="62d89-198">接受的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="62d89-198">Accepted month names:</span></span>
  
- <span data-ttu-id="62d89-199">葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="62d89-199">Portuguese</span></span>
    
  - <span data-ttu-id="62d89-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="62d89-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="62d89-201">jan fev mar abr 郵件 6 月 7 月過去 11 月 dez 出設定</span><span class="sxs-lookup"><span data-stu-id="62d89-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="funceudate2-deprecated"></a><span data-ttu-id="62d89-202">Func_eu_date2 (已過時)</span><span class="sxs-lookup"><span data-stu-id="62d89-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="62d89-203">因為它可支援僅荷蘭文月份名稱，現在包含中已被取代此函數`Func_eu_date`上述的函數。</span><span class="sxs-lookup"><span data-stu-id="62d89-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="62d89-p111">此函數會尋找格式通常用於荷蘭文的日期。此函數的格式是相同`Func_eu_date`、 受限於較只能在所用的語言。</span><span class="sxs-lookup"><span data-stu-id="62d89-p111">This function looks for a date in the format commonly used in Dutch. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="62d89-206">範例：</span><span class="sxs-lookup"><span data-stu-id="62d89-206">Examples:</span></span>
  
- <span data-ttu-id="62d89-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="62d89-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="62d89-208">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="62d89-208">02 mei 2016</span></span>
    
- <span data-ttu-id="62d89-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="62d89-209">2 Mei 16</span></span>
    
- <span data-ttu-id="62d89-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="62d89-210">2/12/2016</span></span>
    
- <span data-ttu-id="62d89-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="62d89-211">02/12/16</span></span>
    
- <span data-ttu-id="62d89-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="62d89-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="62d89-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="62d89-213">2-12-16</span></span>
    
<span data-ttu-id="62d89-214">接受的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="62d89-214">Accepted month names:</span></span>
  
- <span data-ttu-id="62d89-215">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="62d89-215">Dutch</span></span>
    
  - <span data-ttu-id="62d89-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="62d89-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="62d89-217">jan 2 maart apr mei 6 月 7 月 8 月 sep sept oct okt 11 月 dec</span><span class="sxs-lookup"><span data-stu-id="62d89-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="funcexpirationdate"></a><span data-ttu-id="62d89-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="62d89-218">Func_expiration_date</span></span>

<span data-ttu-id="62d89-p112">此函數會尋找格式通常由信用卡和金融卡、 排除偏好的月數天的日期。此函數會比對格式為 「 月/年 」、 「 月-年"、"[月份名稱] year"和"[月份縮寫] 年 」 日期。名稱或縮寫的月數不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="62d89-p112">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months. This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="62d89-222">範例</span><span class="sxs-lookup"><span data-stu-id="62d89-222">Examples:</span></span>
  
- <span data-ttu-id="62d89-223">MM/YY -- 例如，01/11 或 1/11</span><span class="sxs-lookup"><span data-stu-id="62d89-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="62d89-224">MM/YYYY -- 例如，01/2011 或 1/2011</span><span class="sxs-lookup"><span data-stu-id="62d89-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="62d89-225">MM-YY -- 例如，01-22 或 1-11</span><span class="sxs-lookup"><span data-stu-id="62d89-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="62d89-226">MM-YYYY -- 例如，01-2000 或 1-2000</span><span class="sxs-lookup"><span data-stu-id="62d89-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="62d89-227">下列格式支援 YY 或 YYYY：</span><span class="sxs-lookup"><span data-stu-id="62d89-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="62d89-228">Month-YYYY -- 例如，Jan-2010、january-2010、Jan-10 或 january-10</span><span class="sxs-lookup"><span data-stu-id="62d89-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="62d89-229">Month YYYY -- 例如，'january 2010'、'Jan 2010'、'january 10' 或 'Jan 10'</span><span class="sxs-lookup"><span data-stu-id="62d89-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="62d89-230">MonthYYYY -- 例如，'january2010'、'Jan2010'、'january10' 或 'Jan10'</span><span class="sxs-lookup"><span data-stu-id="62d89-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="62d89-231">Month/YYYY-例如，' 1 月/2010 '或' Jan/2010 '或' 年 1 月/10 '或' Jan/10 '</span><span class="sxs-lookup"><span data-stu-id="62d89-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="62d89-232">接受的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="62d89-232">Accepted month names:</span></span>
  
- <span data-ttu-id="62d89-233">英文</span><span class="sxs-lookup"><span data-stu-id="62d89-233">English</span></span>
    
  - <span data-ttu-id="62d89-234">1 月、 年 2 月、 march、 April、 may、 年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月、 年 12 月</span><span class="sxs-lookup"><span data-stu-id="62d89-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="62d89-235">Jan 2 Mar Apr 可能年 6 月 7 日 Sept Oct 11 月 Dec</span><span class="sxs-lookup"><span data-stu-id="62d89-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="funcusaddress"></a><span data-ttu-id="62d89-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="62d89-236">Func_us_address</span></span>

<span data-ttu-id="62d89-p113">此函數會尋找美國州名稱或是郵政縮寫，其後面接著有效的郵遞區號，就像郵遞地址所用的一樣。郵遞區號必須是與美國州名稱或縮寫關聯的其中一種正確郵遞區號。不能用標點符號或字母將美國州名稱和郵遞區號隔開。</span><span class="sxs-lookup"><span data-stu-id="62d89-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="62d89-240">範例：</span><span class="sxs-lookup"><span data-stu-id="62d89-240">Examples:</span></span>
  
- <span data-ttu-id="62d89-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="62d89-241">Washington 98052</span></span>
    
- <span data-ttu-id="62d89-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="62d89-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="62d89-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="62d89-243">WA 98052</span></span>
    
- <span data-ttu-id="62d89-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="62d89-244">WA 98052-9998</span></span>
    

