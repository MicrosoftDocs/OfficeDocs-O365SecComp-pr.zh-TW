---
title: 在 SharePoint Online 中的病毒偵測
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
description: Office 365 可協助您的環境免受病毒偵測使用者上傳至 SharePoint Online 的檔案中的惡意程式碼。掃描檔案有病毒之後其上傳。若檔案已發現受到感染、 屬性設定，讓使用者無法下載或同步處理檔案。
ms.openlocfilehash: 22e983d35283ff96e1469fdf913e25b8d1d1c485
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527009"
---
# <a name="virus-detection-in-sharepoint-online"></a>在 SharePoint Online 中的病毒偵測

Office 365 可協助您的環境免受病毒偵測使用者上傳至 SharePoint Online 的檔案中的惡意程式碼。掃描檔案有病毒之後其上傳。若檔案已發現受到感染、 屬性設定，讓使用者無法下載或同步處理檔案。
  
> [!IMPORTANT]
> SharePoint Online 這些防毒功能是包含病毒的方式。它們不適用對象為惡意程式碼為您的環境的防禦措施的單一資料點。我們建議所有客戶評估及實作不同的層級的反惡意程式碼保護並套用保護您的企業基礎結構的最佳作法。如需策略和最佳作法的詳細資訊，請參閱 ＜ [Security for Office 365 的最佳作法](security-best-practices.md)。 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>受到感染的檔案上傳至 SharePoint Online 發生什麼情況？

Office 365 使用一般的病毒偵測引擎。引擎會以非同步方式執行內 SharePoint Online 和掃描之後他們正在上傳的檔案。當包含病毒而找到的檔案時、 標記使它無法再下載。4 月 2018年中我們移除了掃描的檔案有 25 MB 限制。
  
以下是會發生什麼事：
  
1. 使用者上傳至 SharePoint Online 的檔案。
    
2. 病毒偵測引擎會掃描檔案。
    
3. 如果有找到病毒、 病毒引擎會指出受到感染的檔案上設定的屬性。
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>當使用者嘗試使用瀏覽器下載受到感染的檔案有什麼？

如果檔案感染病毒，使用者無法使用瀏覽器從 SharePoint Online 下載檔案。
  
以下是會發生什麼事：
  
1. 使用者開啟網頁瀏覽器，並嘗試從 SharePoint Online 下載受到感染的檔案。
    
2. 使用者是指定警告病毒已偵測到，並授與下載檔案的選項和嘗試清除其使用自己的防毒軟體。
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>當 OneDrive sync 用戶端嘗試以同步處理受到感染的檔案會發生什麼事？

如果檔案包含病毒而使用者同步的檔案與新的 OneDrive sync 用戶端 (OneDrive.exe) 或上一個 OneDrive for Business sync 用戶端 (Groove.exe)、 是否 sync 用戶端將不會下載它。Sync 用戶端將會顯示無法同步處理之檔案的通知。
  

