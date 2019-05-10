---
title: 在進階電子文件中支援的檔案類型
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
ms.openlocfilehash: 378bd9ae88269d6a6d15a672473550e50179f772
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834932"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>在進階電子文件中支援的檔案類型

進階電子文件支援許多檔案類型，以及支援它們，如下表所述的不同層級。 這份清單不尚未完成，我們將新增新的檔案類型，當我們繼續我們驗證測試。 表也表示是否可以在進階電子文件中可用的檢視器中檢視的檔案類型。

| Mime 類型 | 描述 | 原生檢視器 | 文字檢視器 | 加上註解檢視器 | 容器擷取 | Extensions |
| :- | :- | :- | :- | :- | :- | :- |
| 應用程式/mbox | 封存 / 容器 |  |  |  | 是 | .mbox |
| 應用程式/msword | 生產力 | 是 | 是 | 是 |  | .doc;.dat |
| 應用程式/pdf | 生產力 | 是 | 是 | 是 |  | .pdf |
| 應用程式/rtf | Document | 是 | 是 | 是 |  | .rtf;。doc |
| 應用程式/vnd.ms-excel | 生產力 | 是 | 是 | 是 |  | .xls;.dat |
| application/vnd.ms-excel.sheet.binary.macroenabled.12 | 生產力 | 是 | 是 | 否 |  | .xlsb |
| application/vnd.ms-excel.sheet.macroenabled.12 | 生產力 | 是 | 是 | 是 |  | .xlsm |
| application/vnd.ms-excel.template.macroenabled.12 | 生產力 | 否 | 是 | 否 |  | .xltm |
| 應用程式/vnd.ms-outlook | 共同作業 | 是 | 是 | 是 |  | .msg |
| 應用程式/vnd.ms-outlook 的 pst | 封存 / 容器 |  |  |  | 是 | .pst |
| 應用程式/vnd.ms-powerpoint | 生產力 | 是 | 是 | 是 |  | .ppt，.pps;。pot |
| application/vnd.ms-word.document.macroenabled.12 | 生產力 | 是 | 是 | 是 |  | .docm |
| application/vnd.ms-word.template.macroenabled.12 | 生產力 | 是 | 是 | 是 |  | .dotm |
| application/vnd.oasis.opendocument.text | 生產力 | 是 | 是 | 是 |  | .odt;  |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | 生產力 | 是 | 是 | 是 |  | .pptx |
| application/vnd.openxmlformats-officedocument.presentationml.slideshow | 生產力 | 是 | 是 | 是 |  | .ppsx |
| application/vnd.openxmlformats-officedocument.presentationml.template | 生產力 | 是 | 是 | 是 |  | .potx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | 生產力 | 是 | 是 | 是 |  | .xlsx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.template | 生產力 | 是 | 是 | 是 |  | .xltx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | 生產力 | 是 | 是 | 是 |  | .docx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.template | 生產力 | 是 | 是 | 是 |  | .dotx |
| application/vnd.visio | 生產力 | 是 | 是 | 是 |  | .vsd |
| 應用程式/x-7z-壓縮 | 封存 / 容器 |  |  |  | 是 | .7z |
| 應用程式/xhtml + xml | Document | 是 | 是 | 是 |  | .xhtml |
| 應用程式/xml | Document | 是 | 是 | 是 |  | .xml |
| 應用程式/x-msaccess | 生產力 | 是 | 是 | 是 |  | .mdb |
| 應用程式/x-mspublisher | 生產力 | 是 | 是 | 是 |  | .pub |
| 應用程式/x-rar-壓縮 | 封存 / 容器 |  |  |  | 是 | .rar |
| 應用程式/x-tar | 封存 / 容器 |  |  |  | 是 | .tar |
| 應用程式/zip | 封存 / 容器 |  |  |  | 是 | .zip |
| image/bmp | 影像 | 是 | 是 | 是 |  | .bmp |
| image/emf | 影像 | 是 | 是 | 是 |  | .emf |
| image/gif | 影像 | 是 | 是 | 是 |  | .gif |
| image/jpeg | 影像 | 是 | 是 | 是 |  | .jpg、.jpeg、.dat;。jpgt |
| image/png | 影像 | 是 | 是 | 是 |  | .png |
| image/tiff | 影像 | 是 | 是 | 是 |  | .tif |
| image/vnd.dwg | 繪圖 | 是 | 是 | 是 |  | .dwg;。dxf; |
| image/wmf | Document | 是 | 是 | 是 |  | .wmf |
| message/rfc822 | 共同作業 | 是 | 是 | 是 |  | .eml |
| 文字/csv | Document | 是 | 是 | 是 |  | .csv |
| 文字/html | Document | 是 | 是 | 是 |  | .html;。shtml;.htm |
| 文字/一般 | Document | 是 | 是 | 是 |  | .txt;.css;。詐騙、.pl、.csv、.dat |
| 文字/vcard-連絡人 | 共同作業 | 是 | 是 | 是 |  | .vcf |
||||||||
