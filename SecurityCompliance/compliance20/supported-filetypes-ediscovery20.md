---
title: 進階 eDiscovery (Preview) 中支援的檔案類型
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8b5651e7e1f1e15aae34a3100b25564f0b84abb7
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296156"
---
# <a name="supported-file-types-in-advanced-ediscovery-preview"></a>進階 eDiscovery (Preview) 中支援的檔案類型


| Mime 類型 | 檔案類別 （例如圖像、 封存、 電子郵件、 Office Doc、 等） | 原生檢視器 | 文字 | 加上註解檢視器 | 容器擷取 | 可能的延伸模組 |
| :- | :- | :- | :- | :- | :- | :- |
| 應用程式/msword | 文件 | 是 | 是  | 有 | 否 | .doc、.dat |
| application/pdf | 文件 | 是 | 是  | 有 | 否 | .pdf |
| 應用程式/rtf | 文件 | 是 | 是  | 有 | 否 | .rtf;。文件 |
| 為 application/vnd.ms-excel | 文件 | 是 | 是  | 有 | 否 | .xls ；.dat |
| application/vnd.ms-excel.sheet.binary.macroenabled.12 | 產能 / 開啟文件格式 | 是 | 有 | 否 | 否 | .xlsb |
| application/vnd.ms-excel.sheet.macroenabled.12 | 文件 | 是 | 是  | 有 | 否 | .xlsm |
| application/vnd.ms-excel.template.macroenabled.12 | 產能 / 開啟文件格式 | 否 | 是 | 否 | 否 | .xltm |
| 應用程式/vnd.ms-outlook | 生產力 | 否 | 否 | 否 | 否 | .msg |
| 應用程式/vnd.ms-outlook-pst | 產能 / 共同作業 | 否 | 否 | 否 | 是 | .pst |
| 為 application/vnd.ms-powerpoint | 文件 | 是 | 是  | 有 | 否 | .ppt、.pps ；。pot |
| application/vnd.ms-word.document.macroenabled.12 | 文件 | 是 | 是  | 有 | 否 | .docm |
| application/vnd.ms-word.template.macroenabled.12 | 文件 | 是 | 是  | 有 | 否 | .dotm |
| application/vnd.oasis.opendocument.text | 文件 | 是 | 是  | 有 | 否 | .odt;  |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | 文件 | 是 | 是  | 有 | 否 | .pptx |
| application/vnd.openxmlformats-officedocument.presentationml.slideshow | 產能 / 開啟文件格式 | 是 | 是  | 有 | 否 | .ppsx |
| application/vnd.openxmlformats-officedocument.presentationml.template | 文件 | 是 | 是  | 有 | 否 | .potx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | 文件 | 是 | 是  | 有 | 否 | .xlsx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.template | 文件 | 是 | 是  | 有 | 否 | .xltx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | 文件 | 是 | 是  | 有 | 否 | .docx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.template | 文件 | 是 | 是  | 有 | 否 | .dotx |
| application/vnd.visio | 文件 | 是 | 是  | 有 | 否 | .vsd |
| 應用程式/x-7z-壓縮 | 封存 / 容器 | 否 | 否 | 否 | 是 | .7z |
| 應用程式/xhtml + xml | 文件 | 是 | 是  | 有 | 否 | .xhtml |
| 應用程式/xml | 文件 | 是 | 是  | 有 | 否 | .xml |
| 應用程式/x-msaccess | 文件 | 是 | 是  | 有 | 否 | .mdb |
| 應用程式/x-mspublisher | 文件 | 是 | 是  | 有 | 否 | .pub |
| 應用程式/x-rar-壓縮 | 封存 / 容器 | 否 | 否 | 否 | 是 | .rar |
| 應用程式/zip | 封存 / 容器 | 否 | 否 | 否 | 是 | .zip |
| bmp 圖像 / | 影像 | 是 | 是  | 有 | 否 | .bmp |
| 圖像/emf | 影像 | 是 | 是  | 有 | 否 | .emf |
| gif 圖像 / | 文件 | 是 | 是  | 有 | 否 | .gif |
| image/jpeg | 影像 | 是 | 是  | 有 | 否 | .jpg、.jpeg、.dat;。jpgt |
| png 影像 / | 影像 | 是 | 是  | 有 | 否 | .png |
| 圖像/tiff | 影像 | 是 | 是  | 有 | 否 | .tif |
| image/vnd.dwg | 文件 | 是 | 是  | 有 | 否 | .dwg;。dxf; |
| 圖像/wmf | 文件 | 是 | 是  | 有 | 否 | .wmf |
| 郵件 /rfc822 | 產能 / 共同作業 | 否 | 否 | 否 | 否 | .eml |
| 文字/csv | 文件 | 是 | 是  | 有 | 否 | .csv |
| text/html | 文件 | 是 | 是  | 有 | 否 | .html;。shtml ；.htm |
| text/plain | 文件 | 是 | 是  | 有 | 否 | .txt、.css;。詐騙、.pl、.csv、.dat |
| 文字/vcard 位連絡人 | 文件 | 是 | 是  | 有 | 否 | .vcf |