---
title: 歐盟 GPS 座標
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/14/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: fdf2aebc-d5a4-4138-b10f-4a81dd70415a
description: Office 365 安全性的資料遺失防護 (DLP)&amp;規範中心包含許多可供您使用 DLP 原則中的敏感資訊類型。本主題說明歐盟 GPS 協調敏感資訊類型。
ms.openlocfilehash: 89fb8420e479b9f793fc2be9aa3a9a9fd5741691
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526671"
---
# <a name="eu-gps-coordinates"></a><span data-ttu-id="21539-104">歐盟 GPS 座標</span><span class="sxs-lookup"><span data-stu-id="21539-104">EU GPS Coordinates</span></span>

<span data-ttu-id="21539-p102">Office 365 安全性的資料遺失防護 (DLP)&amp;規範中心包含許多可供您使用 DLP 原則中的敏感資訊類型。本主題說明歐盟 GPS 協調敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="21539-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU GPS Coordinates sensitive information type.</span></span>
  
## <a name="austria"></a><span data-ttu-id="21539-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="21539-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="21539-108">格式</span><span class="sxs-lookup"><span data-stu-id="21539-108">Format</span></span>

<span data-ttu-id="21539-109">協調城市 （英文） 中奧地利的範圍內： 從 46.526 緯度 48.816 及 16.945 以從 9.6 經度。</span><span class="sxs-lookup"><span data-stu-id="21539-109">Coordinates for cities in Austria are in range: Latitude from 46.526 to 48.816 and longitude from 9.6 to 16.945.</span></span>
  
### <a name="pattern"></a><span data-ttu-id="21539-110">模式</span><span class="sxs-lookup"><span data-stu-id="21539-110">Pattern</span></span>

<span data-ttu-id="21539-111">每個座標、 最多 6 位數和小數點的組合。</span><span class="sxs-lookup"><span data-stu-id="21539-111">For each coordinate, combination of up to 6 digits and a decimal point.</span></span>
  
- <span data-ttu-id="21539-112">最多 6 位數</span><span class="sxs-lookup"><span data-stu-id="21539-112">Up to 6 digits</span></span>
    
- <span data-ttu-id="21539-113">在第一筆或第二個字之後的小數點。</span><span class="sxs-lookup"><span data-stu-id="21539-113">A decimal point after first or second digit.</span></span>
    
### <a name="checksum"></a><span data-ttu-id="21539-114">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-114">Checksum</span></span>

<span data-ttu-id="21539-115">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-116">定義</span><span class="sxs-lookup"><span data-stu-id="21539-116">Definition</span></span>

<span data-ttu-id="21539-117">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-118">規則運算式`Regex_austria_eu_gps_data_1`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-118">The regular expression  `Regex_austria_eu_gps_data_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="21539-119">從關鍵字`Keywords_austria_eu_gps_data`找到。</span><span class="sxs-lookup"><span data-stu-id="21539-119">A keyword from  `Keywords_austria_eu_gps_data` is found.</span></span> 
    
<span data-ttu-id="21539-120">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="21539-120">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-121">規則運算式`Regex_austria_eu_gps_data_1`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-121">The regular expression  `Regex_austria_eu_gps_data_1` finds content that matches the pattern.</span></span> 
    
<span data-ttu-id="21539-122">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-122">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-123">規則運算式`Regex_austria_eu_gps_data_2`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-123">The regular expression  `Regex_austria_eu_gps_data_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="21539-124">從關鍵字`Keywords_austria_eu_gps_data`找到。</span><span class="sxs-lookup"><span data-stu-id="21539-124">A keyword from  `Keywords_austria_eu_gps_data` is found.</span></span> 
    
<span data-ttu-id="21539-125">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 65%：</span><span class="sxs-lookup"><span data-stu-id="21539-125">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-126">規則運算式`Regex_austria_eu_gps_data_2`會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-126">The regular expression  `Regex_austria_eu_gps_data_2` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_gps_data_1" />
          <Match idRef="Keywords_austria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_austria_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_gps_data_2" />
          <Match idRef="Keywords_austria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_austria_eu_gps_data_2" />
        </Pattern>

```

### <a name="keywords"></a><span data-ttu-id="21539-127">關鍵字</span><span class="sxs-lookup"><span data-stu-id="21539-127">Keywords</span></span>

#### <a name="keywordsaustriaeugpsdata"></a><span data-ttu-id="21539-128">Keywords_austria_eu_gps_data</span><span class="sxs-lookup"><span data-stu-id="21539-128">Keywords_austria_eu_gps_data</span></span>

<span data-ttu-id="21539-129">gps tracker （英文)</span><span class="sxs-lookup"><span data-stu-id="21539-129">gps tracker</span></span>
  
<span data-ttu-id="21539-130">gps 座標</span><span class="sxs-lookup"><span data-stu-id="21539-130">gps coordinates</span></span>
  
<span data-ttu-id="21539-131">位置</span><span class="sxs-lookup"><span data-stu-id="21539-131">location</span></span>
  
<span data-ttu-id="21539-132">地圖</span><span class="sxs-lookup"><span data-stu-id="21539-132">map</span></span>
  
<span data-ttu-id="21539-133">緯度</span><span class="sxs-lookup"><span data-stu-id="21539-133">latitude</span></span>
  
<span data-ttu-id="21539-134">經度</span><span class="sxs-lookup"><span data-stu-id="21539-134">longitude</span></span>
  
<span data-ttu-id="21539-135">GPS tracker （英文)</span><span class="sxs-lookup"><span data-stu-id="21539-135">GPS-Tracker</span></span>
  
<span data-ttu-id="21539-136">GPS Koordinaten</span><span class="sxs-lookup"><span data-stu-id="21539-136">GPS-Koordinaten</span></span>
  
<span data-ttu-id="21539-137">Standort Karte</span><span class="sxs-lookup"><span data-stu-id="21539-137">Standort Karte</span></span>
  
<span data-ttu-id="21539-138">Breitengrad</span><span class="sxs-lookup"><span data-stu-id="21539-138">Breitengrad</span></span>
  
<span data-ttu-id="21539-139">Längengrad</span><span class="sxs-lookup"><span data-stu-id="21539-139">Längengrad</span></span>
  
## <a name="belgium"></a><span data-ttu-id="21539-140">比利時</span><span class="sxs-lookup"><span data-stu-id="21539-140">Belgium</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-141">模式</span><span class="sxs-lookup"><span data-stu-id="21539-141">Pattern</span></span>

-  <span data-ttu-id="21539-142">數字</span><span class="sxs-lookup"><span data-stu-id="21539-142">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-143">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-143">Checksum</span></span>

<span data-ttu-id="21539-144">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-145">定義</span><span class="sxs-lookup"><span data-stu-id="21539-145">Definition</span></span>

<span data-ttu-id="21539-146">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-147">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-147">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-148">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-148">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75>">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_gps_data_1" />
          <Match idRef="Keywords_belgium_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
          <Match idRef="Keywords_belgium_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="bulgaria"></a><span data-ttu-id="21539-149">保加利亞</span><span class="sxs-lookup"><span data-stu-id="21539-149">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-150">模式</span><span class="sxs-lookup"><span data-stu-id="21539-150">Pattern</span></span>

-  <span data-ttu-id="21539-151">數字</span><span class="sxs-lookup"><span data-stu-id="21539-151">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-152">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-152">Checksum</span></span>

<span data-ttu-id="21539-153">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-153">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-154">定義</span><span class="sxs-lookup"><span data-stu-id="21539-154">Definition</span></span>

<span data-ttu-id="21539-155">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-155">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-156">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-156">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-157">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-157">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75>
</Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_1" />
          <Match idRef="Keywords_bulgaria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_2" />
          <Match idRef="Keywords_bulgaria_eu_gps_data" />
        </Pattern>
</Entity>
```

## <a name="croatia"></a><span data-ttu-id="21539-158">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="21539-158">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-159">模式</span><span class="sxs-lookup"><span data-stu-id="21539-159">Pattern</span></span>

-  <span data-ttu-id="21539-160">數字</span><span class="sxs-lookup"><span data-stu-id="21539-160">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-161">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-161">Checksum</span></span>

<span data-ttu-id="21539-162">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-162">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-163">定義</span><span class="sxs-lookup"><span data-stu-id="21539-163">Definition</span></span>

<span data-ttu-id="21539-164">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-164">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-165">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-165">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-166">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-166">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_gps_data_1" />
          <Match idRef="Keywords_croatia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_croatia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_gps_data_2" />
          <Match idRef="Keywords_croatia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_croatia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="cyprus"></a><span data-ttu-id="21539-167">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="21539-167">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-168">模式</span><span class="sxs-lookup"><span data-stu-id="21539-168">Pattern</span></span>

-  <span data-ttu-id="21539-169">數字</span><span class="sxs-lookup"><span data-stu-id="21539-169">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-170">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-170">Checksum</span></span>

<span data-ttu-id="21539-171">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-171">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-172">定義</span><span class="sxs-lookup"><span data-stu-id="21539-172">Definition</span></span>

<span data-ttu-id="21539-173">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-173">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-174">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-174">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-175">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-175">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_1" />
          <Match idRef="Keywords_cyprus_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_2" />
          <Match idRef="Keywords_cyprus_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="czech-republic"></a><span data-ttu-id="21539-176">捷克</span><span class="sxs-lookup"><span data-stu-id="21539-176">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-177">模式</span><span class="sxs-lookup"><span data-stu-id="21539-177">Pattern</span></span>

-  <span data-ttu-id="21539-178">數字</span><span class="sxs-lookup"><span data-stu-id="21539-178">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-179">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-179">Checksum</span></span>

<span data-ttu-id="21539-180">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-180">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-181">定義</span><span class="sxs-lookup"><span data-stu-id="21539-181">Definition</span></span>

<span data-ttu-id="21539-182">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-182">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
<span data-ttu-id="21539-183">DLP 原則是 %有信心它已偵測到這種類型的機密資訊時，內鄰近的字元：</span><span class="sxs-lookup"><span data-stu-id="21539-183">A DLP policy is % confident that it's detected this type of sensitive information if, within a proximity of characters:</span></span>
  
- <span data-ttu-id="21539-184">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-184">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-185">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-185">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_1" />
          <Match idRef="Keywords_czech_republic_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_2" />
          <Match idRef="Keywords_czech_republic_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="denmark"></a><span data-ttu-id="21539-186">丹麥</span><span class="sxs-lookup"><span data-stu-id="21539-186">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-187">模式</span><span class="sxs-lookup"><span data-stu-id="21539-187">Pattern</span></span>

-  <span data-ttu-id="21539-188">數字</span><span class="sxs-lookup"><span data-stu-id="21539-188">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-189">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-189">Checksum</span></span>

<span data-ttu-id="21539-190">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-190">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-191">定義</span><span class="sxs-lookup"><span data-stu-id="21539-191">Definition</span></span>

<span data-ttu-id="21539-192">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-192">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-193">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-193">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-194">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-194">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_gps_data_1" />
          <Match idRef="Keywords_denmark_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_denmark_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_gps_data_2" />
          <Match idRef="Keywords_denmark_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_denmark_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="estonia"></a><span data-ttu-id="21539-195">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="21539-195">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-196">模式</span><span class="sxs-lookup"><span data-stu-id="21539-196">Pattern</span></span>

-  <span data-ttu-id="21539-197">數字</span><span class="sxs-lookup"><span data-stu-id="21539-197">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-198">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-198">Checksum</span></span>

<span data-ttu-id="21539-199">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-199">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-200">定義</span><span class="sxs-lookup"><span data-stu-id="21539-200">Definition</span></span>

<span data-ttu-id="21539-201">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-202">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-202">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-203">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-203">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_gps_data_1" />
          <Match idRef="Keywords_estonia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_estonia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_gps_data_2" />
          <Match idRef="Keywords_estonia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_estonia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="finland"></a><span data-ttu-id="21539-204">芬蘭</span><span class="sxs-lookup"><span data-stu-id="21539-204">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-205">模式</span><span class="sxs-lookup"><span data-stu-id="21539-205">Pattern</span></span>

-  <span data-ttu-id="21539-206">數字</span><span class="sxs-lookup"><span data-stu-id="21539-206">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-207">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-207">Checksum</span></span>

<span data-ttu-id="21539-208">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-208">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-209">定義</span><span class="sxs-lookup"><span data-stu-id="21539-209">Definition</span></span>

<span data-ttu-id="21539-210">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-210">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-211">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-211">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-212">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-212">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_gps_data_1" />
          <Match idRef="Keywords_finland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_finland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_gps_data_2" />
          <Match idRef="Keywords_finland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_finland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="france"></a><span data-ttu-id="21539-213">法國</span><span class="sxs-lookup"><span data-stu-id="21539-213">France</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-214">模式</span><span class="sxs-lookup"><span data-stu-id="21539-214">Pattern</span></span>

-  <span data-ttu-id="21539-215">數字</span><span class="sxs-lookup"><span data-stu-id="21539-215">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-216">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-216">Checksum</span></span>

<span data-ttu-id="21539-217">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-217">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-218">定義</span><span class="sxs-lookup"><span data-stu-id="21539-218">Definition</span></span>

<span data-ttu-id="21539-219">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-219">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-220">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-220">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-221">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-221">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_gps_data_1" />
          <Match idRef="Keywords_france_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_france_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_gps_data_2" />
          <Match idRef="Keywords_france_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_france_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="germany"></a><span data-ttu-id="21539-222">德國</span><span class="sxs-lookup"><span data-stu-id="21539-222">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-223">模式</span><span class="sxs-lookup"><span data-stu-id="21539-223">Pattern</span></span>

-  <span data-ttu-id="21539-224">數字</span><span class="sxs-lookup"><span data-stu-id="21539-224">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-225">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-225">Checksum</span></span>

<span data-ttu-id="21539-226">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-226">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-227">定義</span><span class="sxs-lookup"><span data-stu-id="21539-227">Definition</span></span>

<span data-ttu-id="21539-228">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-228">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-229">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-229">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-230">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-230">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_gps_data_1" />
          <Match idRef="Keywords_germany_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_germany_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_gps_data_2" />
          <Match idRef="Keywords_germany_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_germany_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="greece"></a><span data-ttu-id="21539-231">希臘</span><span class="sxs-lookup"><span data-stu-id="21539-231">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-232">模式</span><span class="sxs-lookup"><span data-stu-id="21539-232">Pattern</span></span>

-  <span data-ttu-id="21539-233">數字</span><span class="sxs-lookup"><span data-stu-id="21539-233">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-234">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-234">Checksum</span></span>

<span data-ttu-id="21539-235">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-235">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-236">定義</span><span class="sxs-lookup"><span data-stu-id="21539-236">Definition</span></span>

<span data-ttu-id="21539-237">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-237">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-238">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-238">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-239">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-239">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_gps_data_1" />
          <Match idRef="Keywords_greece_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_gps_data_2" />
          <Match idRef="Keywords_greece_eu_gps_data" />
        </Pattern>
</Entity>
```

## <a name="hungary"></a><span data-ttu-id="21539-240">匈牙利</span><span class="sxs-lookup"><span data-stu-id="21539-240">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-241">模式</span><span class="sxs-lookup"><span data-stu-id="21539-241">Pattern</span></span>

-  <span data-ttu-id="21539-242">數字</span><span class="sxs-lookup"><span data-stu-id="21539-242">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-243">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-243">Checksum</span></span>

<span data-ttu-id="21539-244">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-244">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-245">定義</span><span class="sxs-lookup"><span data-stu-id="21539-245">Definition</span></span>

<span data-ttu-id="21539-246">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-247">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-247">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-248">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-248">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_gps_data_1" />
          <Match idRef="Keywords_hungary_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_hungary_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_gps_data_2" />
          <Match idRef="Keywords_hungary_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_hungary_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="ireland"></a><span data-ttu-id="21539-249">Ireland</span><span class="sxs-lookup"><span data-stu-id="21539-249">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-250">模式</span><span class="sxs-lookup"><span data-stu-id="21539-250">Pattern</span></span>

-  <span data-ttu-id="21539-251">數字</span><span class="sxs-lookup"><span data-stu-id="21539-251">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-252">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-252">Checksum</span></span>

<span data-ttu-id="21539-253">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-253">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-254">定義</span><span class="sxs-lookup"><span data-stu-id="21539-254">Definition</span></span>

<span data-ttu-id="21539-255">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-255">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-256">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-256">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-257">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-257">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_gps_data_1" />
          <Match idRef="Keywords_ireland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_ireland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_gps_data_2" />
          <Match idRef="Keywords_ireland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_ireland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="italy"></a><span data-ttu-id="21539-258">義大利</span><span class="sxs-lookup"><span data-stu-id="21539-258">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-259">模式</span><span class="sxs-lookup"><span data-stu-id="21539-259">Pattern</span></span>

-  <span data-ttu-id="21539-260">數字</span><span class="sxs-lookup"><span data-stu-id="21539-260">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-261">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-261">Checksum</span></span>

<span data-ttu-id="21539-262">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-262">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-263">定義</span><span class="sxs-lookup"><span data-stu-id="21539-263">Definition</span></span>

<span data-ttu-id="21539-264">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-264">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-265">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-265">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-266">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-266">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_gps_data_1" />
          <Match idRef="Keywords_italy_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_italy_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_gps_data_2" />
          <Match idRef="Keywords_italy_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_italy_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="latvia"></a><span data-ttu-id="21539-267">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="21539-267">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-268">模式</span><span class="sxs-lookup"><span data-stu-id="21539-268">Pattern</span></span>

-  <span data-ttu-id="21539-269">數字</span><span class="sxs-lookup"><span data-stu-id="21539-269">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-270">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-270">Checksum</span></span>

<span data-ttu-id="21539-271">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-271">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-272">定義</span><span class="sxs-lookup"><span data-stu-id="21539-272">Definition</span></span>

<span data-ttu-id="21539-273">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-273">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-274">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-274">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-275">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-275">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_gps_data_1" />
          <Match idRef="Keywords_latvia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_latvia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_gps_data_2" />
          <Match idRef="Keywords_latvia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_latvia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="lithuania"></a><span data-ttu-id="21539-276">立陶宛</span><span class="sxs-lookup"><span data-stu-id="21539-276">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-277">模式</span><span class="sxs-lookup"><span data-stu-id="21539-277">Pattern</span></span>

-  <span data-ttu-id="21539-278">數字</span><span class="sxs-lookup"><span data-stu-id="21539-278">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-279">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-279">Checksum</span></span>

<span data-ttu-id="21539-280">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-280">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-281">定義</span><span class="sxs-lookup"><span data-stu-id="21539-281">Definition</span></span>

<span data-ttu-id="21539-282">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-283">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-283">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-284">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-284">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_1" />
          <Match idRef="Keywords_lithuania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_2" />
          <Match idRef="Keywords_lithuania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="luxemburg"></a><span data-ttu-id="21539-285">盧森堡</span><span class="sxs-lookup"><span data-stu-id="21539-285">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-286">模式</span><span class="sxs-lookup"><span data-stu-id="21539-286">Pattern</span></span>

-  <span data-ttu-id="21539-287">數字</span><span class="sxs-lookup"><span data-stu-id="21539-287">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-288">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-288">Checksum</span></span>

<span data-ttu-id="21539-289">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-289">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-290">定義</span><span class="sxs-lookup"><span data-stu-id="21539-290">Definition</span></span>

<span data-ttu-id="21539-291">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-291">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-292">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-292">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-293">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-293">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_1" />
          <Match idRef="Keywords_luxemburg_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_2" />
          <Match idRef="Keywords_luxemburg_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="malta"></a><span data-ttu-id="21539-294">馬爾他</span><span class="sxs-lookup"><span data-stu-id="21539-294">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-295">模式</span><span class="sxs-lookup"><span data-stu-id="21539-295">Pattern</span></span>

-  <span data-ttu-id="21539-296">數字</span><span class="sxs-lookup"><span data-stu-id="21539-296">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-297">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-297">Checksum</span></span>

<span data-ttu-id="21539-298">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-298">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-299">定義</span><span class="sxs-lookup"><span data-stu-id="21539-299">Definition</span></span>

<span data-ttu-id="21539-300">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-301">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-301">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-302">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-302">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_gps_data_1" />
          <Match idRef="Keywords_malta_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_gps_data_2" />
          <Match idRef="Keywords_malta_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="netherlands"></a><span data-ttu-id="21539-303">荷蘭</span><span class="sxs-lookup"><span data-stu-id="21539-303">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-304">模式</span><span class="sxs-lookup"><span data-stu-id="21539-304">Pattern</span></span>

-  <span data-ttu-id="21539-305">數字</span><span class="sxs-lookup"><span data-stu-id="21539-305">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-306">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-306">Checksum</span></span>

<span data-ttu-id="21539-307">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-307">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-308">定義</span><span class="sxs-lookup"><span data-stu-id="21539-308">Definition</span></span>

<span data-ttu-id="21539-309">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-309">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-310">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-310">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-311">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-311">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_1" />
          <Match idRef="Keywords_netherlands_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_2" />
          <Match idRef="Keywords_netherlands_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="poland"></a><span data-ttu-id="21539-312">波蘭</span><span class="sxs-lookup"><span data-stu-id="21539-312">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-313">模式</span><span class="sxs-lookup"><span data-stu-id="21539-313">Pattern</span></span>

-  <span data-ttu-id="21539-314">數字</span><span class="sxs-lookup"><span data-stu-id="21539-314">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-315">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-315">Checksum</span></span>

<span data-ttu-id="21539-316">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-316">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-317">定義</span><span class="sxs-lookup"><span data-stu-id="21539-317">Definition</span></span>

<span data-ttu-id="21539-318">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-318">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-319">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-319">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-320">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-320">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_gps_data_1" />
          <Match idRef="Keywords_poland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_poland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_gps_data_2" />
          <Match idRef="Keywords_poland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_poland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="portugal"></a><span data-ttu-id="21539-321">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="21539-321">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-322">模式</span><span class="sxs-lookup"><span data-stu-id="21539-322">Pattern</span></span>

-  <span data-ttu-id="21539-323">數字</span><span class="sxs-lookup"><span data-stu-id="21539-323">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-324">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-324">Checksum</span></span>

<span data-ttu-id="21539-325">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-325">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-326">定義</span><span class="sxs-lookup"><span data-stu-id="21539-326">Definition</span></span>

<span data-ttu-id="21539-327">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-327">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-328">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-328">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-329">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-329">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_gps_data_1" />
          <Match idRef="Keywords_portugal_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_portugal_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_gps_data_2" />
          <Match idRef="Keywords_portugal_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_portugal_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="romania"></a><span data-ttu-id="21539-330">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="21539-330">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-331">模式</span><span class="sxs-lookup"><span data-stu-id="21539-331">Pattern</span></span>

-  <span data-ttu-id="21539-332">數字</span><span class="sxs-lookup"><span data-stu-id="21539-332">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-333">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-333">Checksum</span></span>

<span data-ttu-id="21539-334">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-334">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-335">定義</span><span class="sxs-lookup"><span data-stu-id="21539-335">Definition</span></span>

<span data-ttu-id="21539-336">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-336">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-337">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-337">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-338">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-338">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_gps_data_1" />
          <Match idRef="Keywords_romania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_romania_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_gps_data_2" />
          <Match idRef="Keywords_romania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_romania_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="slovakia"></a><span data-ttu-id="21539-339">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="21539-339">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-340">模式</span><span class="sxs-lookup"><span data-stu-id="21539-340">Pattern</span></span>

-  <span data-ttu-id="21539-341">數字</span><span class="sxs-lookup"><span data-stu-id="21539-341">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-342">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-342">Checksum</span></span>

<span data-ttu-id="21539-343">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-343">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-344">定義</span><span class="sxs-lookup"><span data-stu-id="21539-344">Definition</span></span>

<span data-ttu-id="21539-345">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-345">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-346">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-346">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-347">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-347">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_1" />
          <Match idRef="Keywords_slovakia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_2" />
          <Match idRef="Keywords_slovakia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="slovenia"></a><span data-ttu-id="21539-348">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="21539-348">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-349">模式</span><span class="sxs-lookup"><span data-stu-id="21539-349">Pattern</span></span>

-  <span data-ttu-id="21539-350">數字</span><span class="sxs-lookup"><span data-stu-id="21539-350">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-351">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-351">Checksum</span></span>

<span data-ttu-id="21539-352">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-352">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-353">定義</span><span class="sxs-lookup"><span data-stu-id="21539-353">Definition</span></span>

<span data-ttu-id="21539-354">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-354">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-355">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-355">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-356">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-356">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_1" />
          <Match idRef="Keywords_slovenia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_2" />
          <Match idRef="Keywords_slovenia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="spain"></a><span data-ttu-id="21539-357">西班牙</span><span class="sxs-lookup"><span data-stu-id="21539-357">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-358">模式</span><span class="sxs-lookup"><span data-stu-id="21539-358">Pattern</span></span>

-  <span data-ttu-id="21539-359">數字</span><span class="sxs-lookup"><span data-stu-id="21539-359">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-360">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-360">Checksum</span></span>

<span data-ttu-id="21539-361">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-361">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-362">定義</span><span class="sxs-lookup"><span data-stu-id="21539-362">Definition</span></span>

<span data-ttu-id="21539-363">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-364">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-364">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-365">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-365">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_gps_data_1" />
          <Match idRef="Keywords_spain_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_spain_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_gps_data_2" />
          <Match idRef="Keywords_spain_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_spain_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="sweden"></a><span data-ttu-id="21539-366">瑞典</span><span class="sxs-lookup"><span data-stu-id="21539-366">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-367">模式</span><span class="sxs-lookup"><span data-stu-id="21539-367">Pattern</span></span>

-  <span data-ttu-id="21539-368">數字</span><span class="sxs-lookup"><span data-stu-id="21539-368">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-369">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-369">Checksum</span></span>

<span data-ttu-id="21539-370">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-370">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-371">定義</span><span class="sxs-lookup"><span data-stu-id="21539-371">Definition</span></span>

<span data-ttu-id="21539-372">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-372">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-373">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-373">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-374">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-374">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_gps_data_1" />
          <Match idRef="Keywords_sweden_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_sweden_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_gps_data_2" />
          <Match idRef="Keywords_sweden_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_sweden_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="uk"></a><span data-ttu-id="21539-375">英國</span><span class="sxs-lookup"><span data-stu-id="21539-375">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="21539-376">模式</span><span class="sxs-lookup"><span data-stu-id="21539-376">Pattern</span></span>

-  <span data-ttu-id="21539-377">數字</span><span class="sxs-lookup"><span data-stu-id="21539-377">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="21539-378">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="21539-378">Checksum</span></span>

<span data-ttu-id="21539-379">不適用</span><span class="sxs-lookup"><span data-stu-id="21539-379">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="21539-380">定義</span><span class="sxs-lookup"><span data-stu-id="21539-380">Definition</span></span>

<span data-ttu-id="21539-381">如果鄰近性是 300 個字元以內，則 DLP 原則偵測到此敏感資訊類型的信賴度是 75%：</span><span class="sxs-lookup"><span data-stu-id="21539-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="21539-382">規則運算式會找出符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="21539-382">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="21539-383">從關鍵字是找到。</span><span class="sxs-lookup"><span data-stu-id="21539-383">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_gps_data_1" />
          <Match idRef="Keywords_uk_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_uk_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_gps_data_2" />
          <Match idRef="Keywords_uk_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_uk_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="see-also"></a><span data-ttu-id="21539-384">另請參閱</span><span class="sxs-lookup"><span data-stu-id="21539-384">See also</span></span>

[<span data-ttu-id="21539-385">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="21539-385">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

