---
title: 如何辨識內容以提供資料控管建議
ms.author: brendonb
author: stephow-MSFT
manager: laurawi
ms.date: 1/15/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Office 365 安全性與合規性中心會根據貴組織目前的環境設定來提供資料控管建議，您只要按幾下就可以完成各項設定。某些建議會先偵測貴組織中的特定內容，然後提供管理該內容的建議步驟。例如，建議可能會偵測包含營運關鍵內容的項目 (如律師-委託人權限或 NDA 資訊)，然後讓您在這些項目上自動套用保留標籤，確保這些項目按照需求予以分類和保留。此主題列出您可能會看到的資料控管建議，並說明提出之每個建議所偵測到的內容。
ms.openlocfilehash: 24e41501ed11d54e60f8b3d9f27a2e96f3cde112
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220433"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="21276-106">如何辨識內容以提供資料控管建議</span><span class="sxs-lookup"><span data-stu-id="21276-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="21276-p102">Office 365 安全性與合規性中心會根據貴組織目前的環境設定來提供資料控管建議，您只要按幾下就可以完成各項設定。某些建議會先偵測貴組織中的特定內容，然後提供管理該內容的建議步驟。例如，建議可能會偵測包含營運關鍵內容的項目 (如律師-委託人權限或 NDA 資訊)，然後讓您在這些項目上自動套用保留標籤，確保這些項目按照需求予以分類和保留。</span><span class="sxs-lookup"><span data-stu-id="21276-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="21276-110">此主題列出您可能會看到的資料控管建議，並說明提出之每個建議所偵測到的內容。</span><span class="sxs-lookup"><span data-stu-id="21276-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="21276-111">清理語音信箱</span><span class="sxs-lookup"><span data-stu-id="21276-111">Clean up voicemail</span></span>

<span data-ttu-id="21276-p103">在使用者的信箱中偵測到識別為「語音信箱」郵件類型的電子郵件訊息時，即會顯示此建議。深入了解 [Exchange 中的郵件內容](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange)。</span><span class="sxs-lookup"><span data-stu-id="21276-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="21276-114">設定律師-委託人權限內容的標籤</span><span class="sxs-lookup"><span data-stu-id="21276-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="21276-115">符合以下任一條件時，會顯示這個建議。</span><span class="sxs-lookup"><span data-stu-id="21276-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="21276-116">在電子郵件訊息內文中偵測到以下任何關鍵字組合：</span><span class="sxs-lookup"><span data-stu-id="21276-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="21276-117">ACP</span><span class="sxs-lookup"><span data-stu-id="21276-117">ACP</span></span>
    - <span data-ttu-id="21276-118">Attorney Client Privilege (律師-委託人權限)</span><span class="sxs-lookup"><span data-stu-id="21276-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="21276-119">Attorney-Client Privilege (律師-委託人權限)</span><span class="sxs-lookup"><span data-stu-id="21276-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="21276-120">Attorney-Client Privileged (律師-委託人權限)</span><span class="sxs-lookup"><span data-stu-id="21276-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="21276-121">在 SharePoint 或 OneDrive 檔案中偵測到以下任何關鍵字組合：</span><span class="sxs-lookup"><span data-stu-id="21276-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="21276-122">ACP</span><span class="sxs-lookup"><span data-stu-id="21276-122">ACP</span></span>
    - <span data-ttu-id="21276-123">Attorney-Client Privilege\* (律師-委託人權限)</span><span class="sxs-lookup"><span data-stu-id="21276-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="21276-124">AC Privilege (AC 權限)</span><span class="sxs-lookup"><span data-stu-id="21276-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="21276-125">保留音訊檔案</span><span class="sxs-lookup"><span data-stu-id="21276-125">Retain audio files</span></span>

<span data-ttu-id="21276-126">在 SharePoint 或 OneDrive 中偵測到以下檔案類型時，會顯示這個建議。</span><span class="sxs-lookup"><span data-stu-id="21276-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="21276-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="21276-127">.MP3</span></span>
- <span data-ttu-id="21276-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="21276-128">.WMA</span></span>
- <span data-ttu-id="21276-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="21276-129">.WAV</span></span>
- <span data-ttu-id="21276-130">.RA</span><span class="sxs-lookup"><span data-stu-id="21276-130">.RA</span></span>
- <span data-ttu-id="21276-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="21276-131">.RAM</span></span>
- <span data-ttu-id="21276-132">.RM</span><span class="sxs-lookup"><span data-stu-id="21276-132">.RM</span></span>
- <span data-ttu-id="21276-133">.MID</span><span class="sxs-lookup"><span data-stu-id="21276-133">.MID</span></span>
- <span data-ttu-id="21276-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="21276-134">.OGG</span></span>
- <span data-ttu-id="21276-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="21276-135">.AIFF</span></span>
- <span data-ttu-id="21276-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="21276-136">.PCM</span></span>
- <span data-ttu-id="21276-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="21276-137">.AAC</span></span>
- <span data-ttu-id="21276-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="21276-138">.FLAC</span></span>
- <span data-ttu-id="21276-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="21276-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="21276-140">保留 CAD 檔案</span><span class="sxs-lookup"><span data-stu-id="21276-140">Retain CAD files</span></span>

<span data-ttu-id="21276-141">在 SharePoint 或 OneDrive 中偵測到以下檔案類型時，會顯示這個建議。</span><span class="sxs-lookup"><span data-stu-id="21276-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="21276-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="21276-142">.3DXML</span></span>
- <span data-ttu-id="21276-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="21276-143">.ACIS</span></span>
- <span data-ttu-id="21276-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="21276-144">.ARC</span></span>
- <span data-ttu-id="21276-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="21276-145">.ASM</span></span>
- <span data-ttu-id="21276-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="21276-146">.CAT\*</span></span>
- <span data-ttu-id="21276-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="21276-147">.CGR</span></span>
- <span data-ttu-id="21276-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="21276-148">.DW\*</span></span>
- <span data-ttu-id="21276-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="21276-149">.DX\*</span></span>
- <span data-ttu-id="21276-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="21276-150">.EDRW</span></span>
- <span data-ttu-id="21276-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="21276-151">.IAM</span></span>
- <span data-ttu-id="21276-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="21276-152">.IGES</span></span>
- <span data-ttu-id="21276-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="21276-153">.IGS</span></span>
- <span data-ttu-id="21276-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="21276-154">.IPT</span></span>
- <span data-ttu-id="21276-155">.JT</span><span class="sxs-lookup"><span data-stu-id="21276-155">.JT</span></span>
- <span data-ttu-id="21276-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="21276-156">.MF1</span></span>
- <span data-ttu-id="21276-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="21276-157">.NEU</span></span>
- <span data-ttu-id="21276-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="21276-158">.PAR</span></span>
- <span data-ttu-id="21276-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="21276-159">.PKG</span></span>
- <span data-ttu-id="21276-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="21276-160">.PRC</span></span>
- <span data-ttu-id="21276-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="21276-161">.PRT</span></span>
- <span data-ttu-id="21276-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="21276-162">.PSM</span></span>
- <span data-ttu-id="21276-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="21276-163">.PWD</span></span>
- <span data-ttu-id="21276-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="21276-164">.SLD\*</span></span>
- <span data-ttu-id="21276-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="21276-165">.STEP</span></span>
- <span data-ttu-id="21276-166">.STL</span><span class="sxs-lookup"><span data-stu-id="21276-166">.STL</span></span>
- <span data-ttu-id="21276-167">.STP</span><span class="sxs-lookup"><span data-stu-id="21276-167">.STP</span></span>
- <span data-ttu-id="21276-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="21276-168">.U3D</span></span>
- <span data-ttu-id="21276-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="21276-169">.UNV</span></span>
- <span data-ttu-id="21276-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="21276-170">.VRML</span></span>
- <span data-ttu-id="21276-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="21276-171">.WRL</span></span>
- <span data-ttu-id="21276-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="21276-172">.X_\*</span></span>
- <span data-ttu-id="21276-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="21276-173">.XAS</span></span>
- <span data-ttu-id="21276-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="21276-174">.XMT\*</span></span>
- <span data-ttu-id="21276-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="21276-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="21276-176">保留影像檔</span><span class="sxs-lookup"><span data-stu-id="21276-176">Retain image files</span></span>

<span data-ttu-id="21276-177">在 SharePoint 或 OneDrive 中偵測到以下檔案類型時，會顯示這個建議。</span><span class="sxs-lookup"><span data-stu-id="21276-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="21276-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="21276-178">.JPEG</span></span>
- <span data-ttu-id="21276-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="21276-179">.GIF</span></span>
- <span data-ttu-id="21276-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="21276-180">.TIF\*</span></span>
- <span data-ttu-id="21276-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="21276-181">.BMP</span></span>
- <span data-ttu-id="21276-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="21276-182">.PNG</span></span>
- <span data-ttu-id="21276-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="21276-183">.RAW</span></span>
- <span data-ttu-id="21276-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="21276-184">.PSD</span></span>
- <span data-ttu-id="21276-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="21276-185">.PSP</span></span>
- <span data-ttu-id="21276-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="21276-186">.JPG</span></span>
- <span data-ttu-id="21276-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="21276-187">.EXIF</span></span>
- <span data-ttu-id="21276-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="21276-188">.PPM</span></span>
- <span data-ttu-id="21276-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="21276-189">.PGM</span></span>
- <span data-ttu-id="21276-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="21276-190">.PBM</span></span>
- <span data-ttu-id="21276-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="21276-191">.PNM</span></span>
- <span data-ttu-id="21276-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="21276-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="21276-193">保留 NDA 內容</span><span class="sxs-lookup"><span data-stu-id="21276-193">Retain NDA content</span></span> 

<span data-ttu-id="21276-194">符合以下任一條件時，會顯示這個建議。</span><span class="sxs-lookup"><span data-stu-id="21276-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="21276-195">在電子郵件訊息內文中偵測到以下任何關鍵字組合：</span><span class="sxs-lookup"><span data-stu-id="21276-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="21276-196">NDA</span><span class="sxs-lookup"><span data-stu-id="21276-196">NDA</span></span>
    - <span data-ttu-id="21276-197">“Non-Disclosure Agreement” (保密合約)</span><span class="sxs-lookup"><span data-stu-id="21276-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="21276-198">“Non Disclosure Agreement” (保密合約)</span><span class="sxs-lookup"><span data-stu-id="21276-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="21276-199">在 SharePoint 或 OneDrive 的 .PDF 或 .DOC 檔案中偵測到以下任何關鍵字組合：</span><span class="sxs-lookup"><span data-stu-id="21276-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="21276-200">NDA</span><span class="sxs-lookup"><span data-stu-id="21276-200">NDA</span></span>
    - <span data-ttu-id="21276-201">Non Disclosure Agreement (保密合約)</span><span class="sxs-lookup"><span data-stu-id="21276-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="21276-202">保留軟體開發檔案</span><span class="sxs-lookup"><span data-stu-id="21276-202">Retain software development files</span></span>

<span data-ttu-id="21276-203">在 SharePoint 或 OneDrive 中偵測到以下檔案類型時，會顯示這個建議。</span><span class="sxs-lookup"><span data-stu-id="21276-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="21276-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="21276-204">.ASAX</span></span>
- <span data-ttu-id="21276-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="21276-205">.ASM</span></span>
- <span data-ttu-id="21276-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="21276-206">.ASP\*</span></span>
- <span data-ttu-id="21276-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="21276-207">.BAT</span></span>
- <span data-ttu-id="21276-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="21276-208">.CONFIG</span></span>
- <span data-ttu-id="21276-209">.CS</span><span class="sxs-lookup"><span data-stu-id="21276-209">.CS</span></span>
- <span data-ttu-id="21276-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="21276-210">.CSS</span></span>
- <span data-ttu-id="21276-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="21276-211">.DISCO</span></span>
- <span data-ttu-id="21276-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="21276-212">.HTM\*</span></span>
- <span data-ttu-id="21276-213">.INC</span><span class="sxs-lookup"><span data-stu-id="21276-213">.INC</span></span>
- <span data-ttu-id="21276-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="21276-214">.JAD</span></span>
- <span data-ttu-id="21276-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="21276-215">.JAVA</span></span>
- <span data-ttu-id="21276-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="21276-216">.JS\*</span></span>
- <span data-ttu-id="21276-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="21276-217">.LIB</span></span>
- <span data-ttu-id="21276-218">.O</span><span class="sxs-lookup"><span data-stu-id="21276-218">.O</span></span>
- <span data-ttu-id="21276-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="21276-219">.PHP</span></span>
- <span data-ttu-id="21276-220">.RC</span><span class="sxs-lookup"><span data-stu-id="21276-220">.RC</span></span>
- <span data-ttu-id="21276-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="21276-221">.RESX</span></span>
- <span data-ttu-id="21276-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="21276-222">.RPT</span></span>
- <span data-ttu-id="21276-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="21276-223">.RSS</span></span>
- <span data-ttu-id="21276-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="21276-224">.SCPT</span></span>
- <span data-ttu-id="21276-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="21276-225">.SRC</span></span>
- <span data-ttu-id="21276-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="21276-226">.VB\*</span></span>
- <span data-ttu-id="21276-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="21276-227">.WSF</span></span>
- <span data-ttu-id="21276-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="21276-228">.XCODEPROJ</span></span>
- <span data-ttu-id="21276-229">.XML</span><span class="sxs-lookup"><span data-stu-id="21276-229">.XML</span></span>
- <span data-ttu-id="21276-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="21276-230">.XSD</span></span>
- <span data-ttu-id="21276-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="21276-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="21276-232">保留影片檔案</span><span class="sxs-lookup"><span data-stu-id="21276-232">Retain video files</span></span>

<span data-ttu-id="21276-233">在 SharePoint 或 OneDrive 中偵測到以下檔案類型時，會顯示這個建議。</span><span class="sxs-lookup"><span data-stu-id="21276-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="21276-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="21276-234">.AVCHD</span></span>
- <span data-ttu-id="21276-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="21276-235">.AVI</span></span>
- <span data-ttu-id="21276-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="21276-236">.FLV</span></span>
- <span data-ttu-id="21276-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="21276-237">.MOV</span></span>
- <span data-ttu-id="21276-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="21276-238">.MP2V</span></span>
- <span data-ttu-id="21276-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="21276-239">.MP4</span></span>
- <span data-ttu-id="21276-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="21276-240">.MP4V</span></span>
- <span data-ttu-id="21276-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="21276-241">.MPE</span></span>
- <span data-ttu-id="21276-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="21276-242">.MPEG</span></span>
- <span data-ttu-id="21276-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="21276-243">.MPEG1</span></span>
- <span data-ttu-id="21276-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="21276-244">.MPEG2</span></span>
- <span data-ttu-id="21276-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="21276-245">.MPEG4</span></span>
- <span data-ttu-id="21276-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="21276-246">.MPG</span></span>
- <span data-ttu-id="21276-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="21276-247">.MPG2</span></span>
- <span data-ttu-id="21276-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="21276-248">.MPG4</span></span>
- <span data-ttu-id="21276-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="21276-249">.WMV</span></span>
- <span data-ttu-id="21276-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="21276-250">.XMV</span></span>
