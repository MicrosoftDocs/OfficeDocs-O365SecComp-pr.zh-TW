---
title: 在 SharePoint Online 中的病毒偵測
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 01/14/2019
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Office 365 可協助防止惡意程式碼中的環境，藉由使用者上傳到 SharePoint Online 檔案中偵測有病毒。 掃描檔案有病毒後它們上傳。 如果找到受感染的檔案時，屬性是設定，讓使用者無法下載，或將檔案同步。
ms.openlocfilehash: 463c2d21c92e5b71602cfe5158dbf6c82e8e7385
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157785"
---
# <a name="virus-detection-in-sharepoint-online"></a>在 SharePoint Online 中的病毒偵測

Office 365 可協助防止惡意程式碼中的環境，藉由使用者上傳到 SharePoint Online 檔案中偵測有病毒。 掃描檔案有病毒後它們上傳。 如果找到受感染的檔案時，屬性是設定，讓使用者無法下載，或將檔案同步。
  
> [!IMPORTANT]
> SharePoint Online 中的這些防毒功能是含有病毒的方式。 它們不適合以防範惡意程式碼為您的環境的單一資料點。 我們鼓勵所有客戶評估和實作各種層級的反惡意程式碼保護，以及套用保護您的企業版基礎結構的最佳做法。 如需策略和最佳作法的詳細資訊，請參閱 < <b0>Office 365 的安全性最佳做法</b0>。 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>當受感染的檔案上傳至 SharePoint Online 時，會發生什麼事？

Office 365 使用常見的病毒偵測引擎。 引擎內 SharePoint Online 中，以非同步方式執行，並掃描檔案之後他們正在上傳。 找到檔案時含有病毒的郵件，就會標示，因此無法再次下載。 年 4 月 2018 年，我們移除了掃描檔案的 25 MB 限制。
  
以下是會發生什麼事：
  
1. 使用者上傳至 SharePoint Online 檔案。
    
2. 病毒偵測引擎掃描的檔案。
    
3. 如果找到病毒，則病毒引擎會指出受到感染的檔案上設定屬性。
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>當使用者嘗試使用瀏覽器來下載受到感染的檔案時，會發生什麼事？

如果檔案感染病毒，使用者使用瀏覽器，無法下載檔案從 SharePoint Online。
  
以下是會發生什麼事：
  
1. 使用者開啟網頁瀏覽器，並嘗試從 SharePoint Online 下載受到感染的檔案。
    
2. 使用者是指定已偵測到病毒警告。 使用者是指定選項，下載檔案，並嘗試清除其使用自己的防毒軟體。

> [!NOTE]
> 您可以使用**DisallowInfectedFileDownload**參數 Set-spotenant 指令程式不允許使用者下載偵測到的檔案，即使是在 [防毒] 警告視窗。 請參閱 [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>OneDrive 同步處理用戶端嘗試同步處理受感染的檔案時，會發生什麼事？

是否使用者同步處理檔案與新的 OneDrive 同步處理用戶端 (OneDrive.exe) 或前一個 OneDrive for Business 同步處理用戶端 (Groove.exe)，如果檔案包含病毒而，同步處理用戶端將不會下載它。 同步處理用戶端將會顯示無法同步處理檔案的通知。
  

