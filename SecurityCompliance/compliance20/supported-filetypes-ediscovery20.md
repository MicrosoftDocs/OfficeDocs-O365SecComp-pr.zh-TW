---
title: 在進階電子文件中支援的檔案類型
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 3dbebb20d179f78e97a8ae18fb810a8cb53c45ed
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151425"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>在進階電子文件中支援的檔案類型

進階電子文件支援許多不同的層級，如下表所述的許多檔案類型。 這份清單未完成，並為我們繼續我們驗證測試，我們會將新增新的檔案類型。 表格會指出文字擷取 (OCR 影像)，是否支援的檔案類型中的原生檢視器和也支援進階電子文件中的附註檢視器中檢視。

## <a name="archive--container"></a>封存 / 容器

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 容器擷取 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |
| 應用程式/x-7z-壓縮 | 是 | 是 | 是 | .7z |
| 應用程式/x-rar-壓縮 | 是 | 是 | 是 | .rar |
| 應用程式/x-tar | 是 | 是 | 是 | .tar |
| 應用程式/zip | 是 | 是 | 是 | .zip |
||||||||

## <a name="database"></a>Database

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| 應用程式/x-msaccess | 是 | 是 | 是 | 否 | 否 | .mdb |
||||||||

## <a name="email"></a>電子郵件

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| 應用程式/vnd.ms-outlook | 是 | 是 | 是 | 是 | 是 | .msg |
| message/rfc822 | 是 | 是 | 是 | 是 | 是 | .eml |
| 文字/vcard-連絡人 | 是 | 是 | 是 | 是 | 是 | .vcf |
||||||||

## <a name="email-container"></a>電子郵件容器

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 容器擷取 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |
| 應用程式/mbox | 是 | 是 | 是 | .mbox |
| 應用程式/vnd.ms-outlook 的 pst | 是 | 是 | 是 | .pst |
||||||||

## <a name="html"></a>HTML

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| 應用程式/xhtml + xml | 是 | 是 | 是 | 是 | 是 | .xhtml |
| 應用程式/xml | 是 | 是 | 是 | 是 | 是 | .xml |
| 文字/html | 是 | 是 | 是 | 是 | 是 | .htm;.html;.shtml |
||||||||

## <a name="image"></a>影像

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | OCR 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| image/bmp | 是 | 是 | 是 | 是 | 是 | .bmp |
| image/emf | 是 | 是 | 是 | 是 | 是 | .emf |
| image/gif | 是 | 是 | 是 | 是 | 是 | .gif |
| image/jpeg | 是 | 是 | 是 | 是 | 是 | .jpeg;.jpg |
| image/png | 是 | 是 | 是 | 是 | 是 | .png |
| svg 影像 / + xml | 是 | 是 | 是 | 是 | 否 | .svg |
| image/tiff | 是 | 是 | 是 | 是 | 是 | .tif |
| image/vnd.dwg | 是 | 是 | 是 | 是 | 是 | .dwg;.dxf |
| image/wmf | 是 | 是 | 是 | 是 | 是 | .wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| 應用程式/vnd.ms-excel | 是 | 是 | 是 | 是 | 是 | .dat;.xls |
| application/vnd.ms-excel.sheet.binary.macroenabled.12 | 是 | 是 | 是 | 是 | 否 | .xlsb |
| application/vnd.ms-excel.sheet.macroenabled.12 | 是 | 是 | 是 | 是 | 是 | .xlsm |
| application/vnd.ms-excel.template.macroenabled.12 | 是 | 是 | 是 | 否 | 否 | .xltm |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | 是 | 是 | 是 | 是 | 是 | .xlsx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.template | 是 | 是 | 是 | 是 | 是 | .xltx |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft Powerpoint

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| 應用程式/vnd.ms-powerpoint | 是 | 是 | 是 | 是 | 是 | .pot;.pps;.ppt |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | 是 | 是 | 是 | 是 | 是 | .pptx |
| application/vnd.openxmlformats-officedocument.presentationml.slideshow | 是 | 是 | 是 | 是 | 是 | .ppsx |
| application/vnd.openxmlformats-officedocument.presentationml.template | 是 | 是 | 是 | 是 | 是 | .potx |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| 應用程式/x-mspublisher | 是 | 是 | 是 | 是 | 是 | .pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd.ms-visio.drawing | 是 | 是 | 是 | 是 | 否 |  |
| application/vnd.visio | 是 | 是 | 是 | 是 | 是 | .vsd |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| 應用程式/msword | 是 | 是 | 是 | 是 | 是 | .dat;.doc |
| 應用程式/rtf | 是 | 是 | 是 | 是 | 是 | .doc;.rtf |
| application/vnd.ms-word.document.macroenabled.12 | 是 | 是 | 是 | 是 | 是 | .docm |
| application/vnd.ms-word.template.macroenabled.12 | 是 | 是 | 是 | 是 | 是 | .dotm |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | 是 | 是 | 是 | 是 | 是 | .docx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.template | 是 | 是 | 是 | 是 | 是 | .dotx |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| 應用程式/vnd.ms-works-ss | 是 | 是 | 否 | 否 | 否 | .wps |
| 應用程式/vnd.ms-works-wp | 是 | 是 | 否 | 否 | 否 | .wps |
||||||||

## <a name="open-document-format"></a>開啟的文件格式

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd.oasis.opendocument.text | 是 | 是 | 是 | 是 | 是 | .odt |
||||||||

## <a name="other"></a>其他

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| 應用程式/json | 是 | 是 | 是 | 是 | 是 | n/a |
| 應用程式/vnd.ms-圖 | 是 | 是 | 否 | 否 | 否 |  |
| 應用程式/winhlp | 是 | 是 | 否 | 否 | 否 | .hlp |
| 應用程式/x-tnef | 是 | 是 | 否 | 否 | 否 |  |
||||||||

## <a name="plain-text"></a>純文字

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| 文字/csv | 是 | 是 | 是 | 是 | 是 | .csv |
| 文字/一般 | 是 | 是 | 是 | 是 | 是 | .con;.css;.csv;.dat;.pl;.txt |
||||||||

## <a name="portable-document-format"></a>可攜式文件格式

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| 應用程式/pdf | 是 | 是 | 是 | 是 | 是 | .pdf |
||||||||

## <a name="word-perfect"></a>Word 完美

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd.wordperfect;版本 = 5.0 | 是 | 是 | 是 | 否 | 否 | .wpd |
| application/vnd.wordperfect;版本 = 5.1 | 是 | 是 | 是 | 否 | 否 | .wpd |
| application/vnd.wordperfect;版本 = 6.x | 是 | 是 | 是 | 否 | 否 | .wpd |
||||||||

## <a name="word-pro"></a>Word 專業人員

| Mime 類型 | 檔案識別碼 | 中繼資料擷取 | 文字擷取 | 原生檢視器 | 加上註解檢視器 | 可能的擴充功能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| 應用程式/vnd.lotus-wordpro | 是 | 是 | 否 | 否 | 否 | .lwp |
||||||||
