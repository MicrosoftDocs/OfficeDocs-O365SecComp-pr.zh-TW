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
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>將貴組織的品牌新增至您的加密郵件

身為 Exchange Online 或 Exchange Online Protection 的管理員，您可以套用公司品牌來自訂貴組織的 Office 365 郵件加密的電子郵件的外觀和加密入口網站的內容。使用 Get-omeconfiguration 與 Set-omeconfiguration Windows PowerShell cmdlet，您可以自訂下列部分的加密的電子郵件的收件者的檢視經驗：
  
- 包含加密訊息的電子郵件簡介文字
    
- 包含加密訊息的電子郵件免責聲明文字
    
- 會出現在 OME 入口網站中的文字
    
- 會出現在電子郵件和 OME 入口網站的標誌
    
- 在電子郵件和 OME 入口網站的背景色彩
    
您也可以隨時回復為預設的外觀與風格。
  
||
|:-----|
|本文屬於較大的一系列有關 Office 365 郵件加密的文章。本文適用於系統管理員和 ITPros 的。如果您只尋找的資訊在傳送或接收加密的郵件，請參閱[Office 365 郵件加密 (OME)](ome.md)中的文章的清單並找出最適合您需求的文章。 |
||
   
**若要自訂使用您的組織的商標加密由 OME OME 入口網站和電子郵件訊息的外觀**
  
1. 連線至 Exchange Online 使用遠端 PowerShell[連線至 Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)中所述。
    
2. 使用 Set-omeconfiguration 指令程式[Set-omeconfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)中所述或使用下表取得指引。 
    
**加密自訂選項**

|**若要自訂此加密經驗功能**|**使用這些命令**|
|:-----|:-----|
|加密的電子郵件隨附的預設文字。預設文字看起來檢視加密的郵件的指示上方。  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|包含加密訊息之電子郵件中的免責聲明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only."` <br/> |
|出現在加密郵件檢視入口網站上方的文字<br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."` <br/> |
|標誌  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支援的檔案格式：.png、.jpg、.bmp 或 .tiff  <br/> 標誌檔案的最佳大小：小於 40 KB  <br/> 標誌影像的最佳大小：170x70 像素  <br/> |
|背景色彩  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -BackgroundColor "#ffffff"` <br/> |
   
**若要移除依 OME 加密 OME 入口網站和電子郵件訊息的商標自訂項目**
  
1. 連線至 Exchange Online 使用遠端 PowerShell[連線至 Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)中所述。
    
2. 使用 Set-omeconfiguration 指令程式[Set-omeconfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)中所述。若要移除您組織的加商標的自訂項目從 DisclaimerText、 EmailText、 和 PortalText 值將值設定為空字串， `""`。如所有圖像值，例如標誌，將值設定為`"$null"`。
    
**加密自訂選項**

**將加密體驗的這項功能回復為預設文字和影像**|**使用這些命令**|
|:-----|:-----|
|加密電子郵件隨附的預設文字  <br/> 預設文字會出現在檢視加密郵件的指示上方。  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|包含加密訊息之電子郵件中的免責聲明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|出現在加密郵件檢視入口網站上方的文字  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **範例回還原預設值：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|標誌  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **範例回還原預設值：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
|背景色彩  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **範例回還原預設值：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null` <br/> |
   

