---
title: 設定搜尋和分析設定
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 253650bb9916da8260491870d1a0bc899d6245c8
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217103"
---
# <a name="configure-search-and-analytics-settings"></a>設定搜尋和分析設定


## <a name="near-duplicates-and-email-threading"></a>接近重複項目及電子郵件超執行緒

此區段中，您可以設定的參數重複資料偵測、 接近重複資料偵測、 和電子郵件執行緒。

- 啟用/停用： 包括重複資料偵測、 接近重複資料偵測、 和電子郵件執行緒分析流程啟用時的一部分。因為它們建置彼此，您必須啟用所有的或停用所有。

- 臨界值： 如果兩個文件的相似性層級超出臨界值，這些皆會置中接近重複的設定相同。

- 根據預設隱藏重複項目： 在此設定時，會在設定預設的工作中套用隱藏重複文件的篩選器。可以在必要時設定工作中手動移除篩選。

- 字數目最小值/上限： 接近重複項目和電子郵件超執行緒會執行僅在字數目最小值和最單字的最大數目至少要有的文件。如需詳細資訊，請參閱[接近重複資料偵測](near-duplicates.md)和[電子郵件執行緒](email-threading.md)。

## <a name="themes"></a>主題

此區段中，您可以設定為佈景主題的參數。

- 啟用/停用： 包括叢集分析流程啟用時的一部分的佈景主題。
- 動態動態調整的佈景主題數目上限： 在某些情況下，沒有足夠的文件產生所需的佈景主題數目。如果開啟此設定，然後而不是嘗試強制所需的數目上限佈景主題，系統會調整佈景主題數目上限動態。
- 佈景主題數目上限： 想要的佈景主題數目
- 包含佈景主題中的數字： 啟用時，它會加上號碼中的產生佈景主題時。  

## <a name="optical-character-recognition-ocr"></a>光學字元辨識 (OCR)

當開啟此設定時，會執行 OCR 上以便他們可以搜尋 ingested 分割工作的圖像。

## <a name="ignore-text"></a>搜尋時忽略的文字

有其中某些敘述性文字會降低分析，例如冗長的免責聲明取得新增至特定電子郵件的電子郵件的內容不論品質的執行個體。如果您已清楚這種情況下，您可以藉由指定的文字 （支援 RegEx） 和其從分析排除此文字的文字排除的模組。