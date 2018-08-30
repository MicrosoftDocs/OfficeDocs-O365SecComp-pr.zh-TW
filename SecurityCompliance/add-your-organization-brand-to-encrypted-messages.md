---
title: 將您的組織的商標新增至加密的郵件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/2/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
description: 'Exchange 系統管理員身分您可以套用您的組織品牌識別您的組織已加密的電子郵件和加密入口網站的內容。 '
ms.openlocfilehash: 2f34b5cea3155f587fd7787f1f69270d1373400b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526771"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a><span data-ttu-id="9617e-103">將貴組織的品牌新增至您的加密郵件</span><span class="sxs-lookup"><span data-stu-id="9617e-103">Add your organization's brand to your encrypted messages</span></span>

<span data-ttu-id="9617e-p101">身為 Exchange Online 或 Exchange Online Protection 的管理員，您可以套用公司品牌來自訂貴組織的 Office 365 郵件加密的電子郵件的外觀和加密入口網站的內容。使用 Get-omeconfiguration 與 Set-omeconfiguration Windows PowerShell cmdlet，您可以自訂下列部分的加密的電子郵件的收件者的檢視經驗：</span><span class="sxs-lookup"><span data-stu-id="9617e-p101">As an Exchange Online or Exchange Online Protection administrator, you can apply your company branding to customize the look of your organization's Office 365 Message Encryption email messages and the contents of the encryption portal. Using the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets, you can customize the following aspects of the viewing experience for recipients of encrypted email messages:</span></span>
  
- <span data-ttu-id="9617e-106">包含加密訊息的電子郵件簡介文字</span><span class="sxs-lookup"><span data-stu-id="9617e-106">Introductory text of the email that contains the encrypted message</span></span>
    
- <span data-ttu-id="9617e-107">包含加密訊息的電子郵件免責聲明文字</span><span class="sxs-lookup"><span data-stu-id="9617e-107">Disclaimer text of the email that contains the encrypted message</span></span>
    
- <span data-ttu-id="9617e-108">會出現在 OME 入口網站中的文字</span><span class="sxs-lookup"><span data-stu-id="9617e-108">Text that appears in the OME portal</span></span>
    
- <span data-ttu-id="9617e-109">會出現在電子郵件和 OME 入口網站的標誌</span><span class="sxs-lookup"><span data-stu-id="9617e-109">Logo that appears in the email message and OME portal</span></span>
    
- <span data-ttu-id="9617e-110">在電子郵件和 OME 入口網站的背景色彩</span><span class="sxs-lookup"><span data-stu-id="9617e-110">Background color in the email message and OME portal</span></span>
    
<span data-ttu-id="9617e-111">您也可以隨時回復為預設的外觀與風格。</span><span class="sxs-lookup"><span data-stu-id="9617e-111">You can also revert back to the default look and feel at any time.</span></span>
  
||
|:-----|
|<span data-ttu-id="9617e-p102">本文屬於較大的一系列有關 Office 365 郵件加密的文章。本文適用於系統管理員和 ITPros 的。如果您只尋找的資訊在傳送或接收加密的郵件，請參閱[Office 365 郵件加密 (OME)](ome.md)中的文章的清單並找出最適合您需求的文章。</span><span class="sxs-lookup"><span data-stu-id="9617e-p102">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||
   
<span data-ttu-id="9617e-115">**若要自訂使用您的組織的商標加密由 OME OME 入口網站和電子郵件訊息的外觀**</span><span class="sxs-lookup"><span data-stu-id="9617e-115">**To customize the look of the OME portal and email messages encrypted by OME with your organization's brand**</span></span>
  
1. <span data-ttu-id="9617e-116">連線至 Exchange Online 使用遠端 PowerShell[連線至 Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="9617e-116">Connect to Exchange Online using Remote PowerShell, as described in [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="9617e-117">使用 Set-omeconfiguration 指令程式[Set-omeconfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)中所述或使用下表取得指引。</span><span class="sxs-lookup"><span data-stu-id="9617e-117">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b) or use the following table for guidance.</span></span> 
    
<span data-ttu-id="9617e-118">**加密自訂選項**</span><span class="sxs-lookup"><span data-stu-id="9617e-118">**Encryption customization options**</span></span>

|<span data-ttu-id="9617e-119">**若要自訂此加密經驗功能**</span><span class="sxs-lookup"><span data-stu-id="9617e-119">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="9617e-120">**使用這些命令**</span><span class="sxs-lookup"><span data-stu-id="9617e-120">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9617e-p103">加密的電子郵件隨附的預設文字。預設文字看起來檢視加密的郵件的指示上方。</span><span class="sxs-lookup"><span data-stu-id="9617e-p103">Default text that accompanies encrypted email messages. The default text appears above the instructions for viewing encrypted messages</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="9617e-123">**範例：**</span><span class="sxs-lookup"><span data-stu-id="9617e-123">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="9617e-124">包含加密訊息之電子郵件中的免責聲明</span><span class="sxs-lookup"><span data-stu-id="9617e-124">Disclaimer statement in the email that contains the encrypted message</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="9617e-125">**範例：**</span><span class="sxs-lookup"><span data-stu-id="9617e-125">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only."` <br/> |
|<span data-ttu-id="9617e-126">出現在加密郵件檢視入口網站上方的文字</span><span class="sxs-lookup"><span data-stu-id="9617e-126">Text that appears at the top of the encrypted mail viewing portal</span></span><br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="9617e-127">**範例：**</span><span class="sxs-lookup"><span data-stu-id="9617e-127">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."` <br/> |
|<span data-ttu-id="9617e-128">標誌</span><span class="sxs-lookup"><span data-stu-id="9617e-128">Logo</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> <span data-ttu-id="9617e-129">**範例：**</span><span class="sxs-lookup"><span data-stu-id="9617e-129">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="9617e-130">支援的檔案格式：.png、.jpg、.bmp 或 .tiff</span><span class="sxs-lookup"><span data-stu-id="9617e-130">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="9617e-131">標誌檔案的最佳大小：小於 40 KB</span><span class="sxs-lookup"><span data-stu-id="9617e-131">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="9617e-132">標誌影像的最佳大小：170x70 像素</span><span class="sxs-lookup"><span data-stu-id="9617e-132">Optimal size of logo image: 170x70 pixels</span></span>  <br/> |
|<span data-ttu-id="9617e-133">背景色彩</span><span class="sxs-lookup"><span data-stu-id="9617e-133">Background color</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> <span data-ttu-id="9617e-134">**範例：**</span><span class="sxs-lookup"><span data-stu-id="9617e-134">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -BackgroundColor "#ffffff"` <br/> |
   
<span data-ttu-id="9617e-135">**若要移除依 OME 加密 OME 入口網站和電子郵件訊息的商標自訂項目**</span><span class="sxs-lookup"><span data-stu-id="9617e-135">**To remove brand customizations from the OME portal and email messages encrypted by OME**</span></span>
  
1. <span data-ttu-id="9617e-136">連線至 Exchange Online 使用遠端 PowerShell[連線至 Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="9617e-136">Connect to Exchange Online using Remote PowerShell, as described in [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="9617e-p104">使用 Set-omeconfiguration 指令程式[Set-omeconfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)中所述。若要移除您組織的加商標的自訂項目從 DisclaimerText、 EmailText、 和 PortalText 值將值設定為空字串， `""`。如所有圖像值，例如標誌，將值設定為`"$null"`。</span><span class="sxs-lookup"><span data-stu-id="9617e-p104">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b). To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string,  `""`. For all image values, such as Logo, set the value to  `"$null"`.</span></span>
    
<span data-ttu-id="9617e-140">**加密自訂選項**</span><span class="sxs-lookup"><span data-stu-id="9617e-140">**Encryption customization options**</span></span>

<span data-ttu-id="9617e-141">**將加密體驗的這項功能回復為預設文字和影像**</span><span class="sxs-lookup"><span data-stu-id="9617e-141">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="9617e-142">**使用這些命令**</span><span class="sxs-lookup"><span data-stu-id="9617e-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9617e-143">加密電子郵件隨附的預設文字</span><span class="sxs-lookup"><span data-stu-id="9617e-143">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="9617e-144">預設文字會出現在檢視加密郵件的指示上方。</span><span class="sxs-lookup"><span data-stu-id="9617e-144">The default text appears above the instructions for viewing encrypted messages</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> <span data-ttu-id="9617e-145">**範例：**</span><span class="sxs-lookup"><span data-stu-id="9617e-145">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|<span data-ttu-id="9617e-146">包含加密訊息之電子郵件中的免責聲明</span><span class="sxs-lookup"><span data-stu-id="9617e-146">Disclaimer statement in the email that contains the encrypted message</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> <span data-ttu-id="9617e-147">**範例：**</span><span class="sxs-lookup"><span data-stu-id="9617e-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|<span data-ttu-id="9617e-148">出現在加密郵件檢視入口網站上方的文字</span><span class="sxs-lookup"><span data-stu-id="9617e-148">Text that appears at the top of the encrypted mail viewing portal</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> <span data-ttu-id="9617e-149">**範例回還原預設值：**</span><span class="sxs-lookup"><span data-stu-id="9617e-149">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|<span data-ttu-id="9617e-150">標誌</span><span class="sxs-lookup"><span data-stu-id="9617e-150">Logo</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> <span data-ttu-id="9617e-151">**範例回還原預設值：**</span><span class="sxs-lookup"><span data-stu-id="9617e-151">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
|<span data-ttu-id="9617e-152">背景色彩</span><span class="sxs-lookup"><span data-stu-id="9617e-152">Background color</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> <span data-ttu-id="9617e-153">**範例回還原預設值：**</span><span class="sxs-lookup"><span data-stu-id="9617e-153">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null` <br/> |
   

