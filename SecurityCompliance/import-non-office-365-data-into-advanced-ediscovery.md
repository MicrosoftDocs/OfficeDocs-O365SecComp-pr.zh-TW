---
title: 針對進階電子文件探索分析匯入非 Office 365 內容
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 5/25/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: 如何匯入的內容，不會儲存在 O365 Azure 到步驟 blob 以便其可以使用 AeD 分析
ms.openlocfilehash: ab6c7ac76a159603a34719aa8edb51de3a4fabbb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527417"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a>針對進階電子文件探索分析匯入非 Office 365 內容

您可能需要使用 Office 365 進階 eDiscovery 分析的不是所有文件將會在 Office 365 live。非 Office 365 內容匯入進階 eDiscovery 可以上傳不到案例的連結、 Azure 儲存 blob live 在 （除了 PST 檔案） 的 Office 365 及分析它們與進階 eDiscovery 的文件中的功能。此程序將示範如何將非 Office 365 文件移入進階 eDiscovery 進行分析。
  
> [!NOTE]
> 進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
> [!NOTE]
> 您可以購買 Office 365 進階 eDiscovery 資料儲存區的附加元件訂閱的非 Office 365 內容。這是以獨佔方式適用於要分析與進階 eDiscovery 的內容。請遵循的步驟[購買或編輯與 Office 365 企業版的附加元件](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6)和購買 Office 365 進階 eDiscovery 儲存附加元件。 
  
## <a name="before-you-begin"></a>開始之前

使用此程序所述的上傳非 Office 365 功能需要您：
  
- 進階規範的附加元件或 E5 訂閱 Office 365 E3
    
- 將上傳其非 Office 365 內容的所有 custodians 必須有都已 E3 進階規範的附加元件或 E5 授權
    
- 現有的 eDiscovery 案例
    
- 所有上傳的檔案所收集到資料夾，其中有 okay 每一個資料夾以及的資料夾名稱是在此格式*alias@domainname* 。*Alias@domainname*必須是 Office 365 的使用者別名及網域。您可以將根資料夾收集所有*alias@domainname*資料夾。根資料夾只能含有*alias@domainname*資料夾、 根資料夾中必須有沒有寬鬆的檔案 
    
- EDiscovery 管理員或 eDiscovery 管理員帳戶
    
- 具有存取權的非 Office 365 內容的資料夾結構的電腦上安裝[Microsoft Azure 儲存工具](https://aka.ms/downloadazcopy)。 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>將非 Office 365 內容上載至進階的 eDiscovery

1. EDiscovery 管理員或 eDiscovery 管理員，以開啟**eDiscovery**，然後開啟將上傳至非 Office 365 資料的大小寫。如果您需要建立案例，請參閱[管理 Office 365 安全性的 eDiscovery 案例&amp;規範中心](manage-ediscovery-cases.md)
    
2. 按一下 [**進階 ediscovery 的切換參數**
    
3. 在**來源類型**] 下選取 [**非 Office 365 的資料**。
    
4. 按一下 [**新增] 容器**。命名容器並新增的描述。
    
5. 從 [容器] 清單中選取新增的容器及複製出現在 [容器] 詳細資料窗格中，然後關閉 [] 窗格中的 URL
    
6. 開啟命令提示字元中以系統管理員身分並將目錄變更為必須已安裝的 AzCopy 資料夾...
    
7. 建構 AzCopy 命令列上傳的檔案類似：
    
    AzCopy /Source:"*本機電腦上的根資料夾的完整路徑*"/Dest:"*容器 URL，但不是包括吗？* "/DestSAS:"*其餘部分從容器 url？結尾*"/ s。 
    
    例如，使用下列值： 
    
  - 根資料夾-C:\Collected 資料 
    
  - 容器 url- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp; sr = c&amp;si = NonOfficeData15 %7 C 0&amp;簽章 = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA %3d
    
    是 AzCopy 命令列語法：
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    如需有關 Azcopy 語法請參閱 ＜[將 windows AzCopy 與資料傳輸](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。 
    
    > [!IMPORTANT]
    > 必須有一個每位使用者的根資料夾和資料夾名稱必須是*alias@domainname*格式。 
  
8. 一旦完成資料夾上傳，切換至 [進階 eDiscovery。在您上傳的資料夾中的內容現在已可處理進階在 eDiscovery 中。選取的容器，並按一下 [程序] 按鈕。如需詳細資訊在進階 eDiscovery 處理查看，[執行程序模組和 Office 365 進階在 eDiscovery 中的將資料載入](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
    
    > [!IMPORTANT]
    > 一旦容器會成功處理進階在 eDiscovery 中，您將不再能夠 SAS 存放區 Azure 中新增新的內容。如果您收集其他的內容與您想要新增至進階的 eDiscovery 分析的案例，您必須建立新的**非 Office 365 資料**容器和重複此程序。 
  
    > [!NOTE]
    > 如果容器*不會處理成功由於資料夾命名問題*與您然後修正的問題，您仍必須以建立新的容器與重新連線及上傳一次使用本文中的程序。 
  

