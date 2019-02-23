---
title: 針對進階電子文件探索分析匯入非 Office 365 內容
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 5/25/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: 如何匯入的內容，不會儲存在 O365 Azure 到步驟 blob 以便其可以使用 AeD 分析
ms.openlocfilehash: 1019fa2e2429aeff8bd20bc3dfb266ab5fb25eaf
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217063"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a><span data-ttu-id="d809e-103">針對進階電子文件探索分析匯入非 Office 365 內容</span><span class="sxs-lookup"><span data-stu-id="d809e-103">Import non-Office 365 content for Advanced eDiscovery analysis</span></span>

<span data-ttu-id="d809e-p101">您可能需要使用 Office 365 進階 eDiscovery 分析的不是所有文件將會在 Office 365 live。非 Office 365 內容匯入進階 eDiscovery 可以上傳不到案例的連結、 Azure 儲存 blob live 在 （除了 PST 檔案） 的 Office 365 及分析它們與進階 eDiscovery 的文件中的功能。此程序將示範如何將非 Office 365 文件移入進階 eDiscovery 進行分析。</span><span class="sxs-lookup"><span data-stu-id="d809e-p101">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365. With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery. This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d809e-p102">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="d809e-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d809e-p103">您可以購買 Office 365 進階 eDiscovery 資料儲存區的附加元件訂閱的非 Office 365 內容。這是以獨佔方式適用於要分析與進階 eDiscovery 的內容。請遵循的步驟[購買或編輯與 Office 365 企業版的附加元件](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6)和購買 Office 365 進階 eDiscovery 儲存附加元件。</span><span class="sxs-lookup"><span data-stu-id="d809e-p103">You can purchase an Office 365 Advanced eDiscovery data storage add-on subscription for your non-Office 365 content. This is exclusively available for content that is to be analyzed with Advanced eDiscovery. Follow the steps in [Buy or edit and add-on for Office 365 for business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) and purchase the Office 365 Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="d809e-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="d809e-112">Before you begin</span></span>

<span data-ttu-id="d809e-113">使用此程序所述的上傳非 Office 365 功能需要您：</span><span class="sxs-lookup"><span data-stu-id="d809e-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="d809e-114">進階規範的附加元件或 E5 訂閱 Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="d809e-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
    
- <span data-ttu-id="d809e-115">將上傳其非 Office 365 內容的所有 custodians 必須有都已 E3 進階規範的附加元件或 E5 授權</span><span class="sxs-lookup"><span data-stu-id="d809e-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
    
- <span data-ttu-id="d809e-116">現有的 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="d809e-116">An existing eDiscovery case</span></span>
    
- <span data-ttu-id="d809e-p104">所有上傳的檔案所收集到資料夾，其中有 okay 每一個資料夾以及的資料夾名稱是在此格式*alias@domainname* 。*Alias@domainname*必須是 Office 365 的使用者別名及網域。您可以將根資料夾收集所有*alias@domainname*資料夾。根資料夾只能含有*alias@domainname*資料夾、 根資料夾中必須有沒有寬鬆的檔案</span><span class="sxs-lookup"><span data-stu-id="d809e-p104">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  . The  *alias@domainname*  must be users Office 365 alias and domain. You can collect all the  *alias@domainname*  folders into a root folder. The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder</span></span> 
    
- <span data-ttu-id="d809e-121">EDiscovery 管理員或 eDiscovery 管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="d809e-121">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>
    
- <span data-ttu-id="d809e-122">具有存取權的非 Office 365 內容的資料夾結構的電腦上安裝[Microsoft Azure 儲存工具](https://aka.ms/downloadazcopy)。</span><span class="sxs-lookup"><span data-stu-id="d809e-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="d809e-123">將非 Office 365 內容上載至進階的 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d809e-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="d809e-p105">EDiscovery 管理員或 eDiscovery 管理員，以開啟**eDiscovery**，然後開啟將上傳至非 Office 365 資料的大小寫。如果您需要建立案例，請參閱[管理 Office 365 安全性的 eDiscovery 案例&amp;規範中心](manage-ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="d809e-p105">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to. If you need to create a case, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md)</span></span>
    
2. <span data-ttu-id="d809e-126">按一下 [**進階 ediscovery 的切換參數**</span><span class="sxs-lookup"><span data-stu-id="d809e-126">Click **Switch to Advanced eDiscovery**</span></span>
    
3. <span data-ttu-id="d809e-127">在**來源類型**] 下選取 [**非 Office 365 的資料**。</span><span class="sxs-lookup"><span data-stu-id="d809e-127">Under **Source type** select **Non-Office 365 data**.</span></span>
    
4. <span data-ttu-id="d809e-p106">按一下 [**新增] 容器**。命名容器並新增的描述。</span><span class="sxs-lookup"><span data-stu-id="d809e-p106">Click **Add container**. Name the container and add a description.</span></span>
    
5. <span data-ttu-id="d809e-130">從 [容器] 清單中選取新增的容器及複製出現在 [容器] 詳細資料窗格中，然後關閉 [] 窗格中的 URL</span><span class="sxs-lookup"><span data-stu-id="d809e-130">Select the newly added container from the container list and copy the URL that appears in the container details pane and then close the pane</span></span>
    
6. <span data-ttu-id="d809e-131">開啟命令提示字元中以系統管理員身分並將目錄變更為必須已安裝的 AzCopy 資料夾...</span><span class="sxs-lookup"><span data-stu-id="d809e-131">Open a command prompt as an administrator and change directory to folder where you have AzCopy installed..</span></span>
    
7. <span data-ttu-id="d809e-132">建構 AzCopy 命令列上傳的檔案類似：</span><span class="sxs-lookup"><span data-stu-id="d809e-132">Construct the AzCopy command line to upload the files like this:</span></span>
    
    <span data-ttu-id="d809e-p107">AzCopy /Source:"*本機電腦上的根資料夾的完整路徑*"/Dest:"*容器 URL，但不是包括吗？* "/DestSAS:"*其餘部分從容器 url？結尾*"/ s。</span><span class="sxs-lookup"><span data-stu-id="d809e-p107">AzCopy /Source:" *full path to root folder on local machine*  " /Dest:"  *container URL up to but not including the ?*  " /DestSAS:"  *remainder of the container url from the ? to the end*  " /S.</span></span> 
    
    <span data-ttu-id="d809e-135">例如，使用下列值：</span><span class="sxs-lookup"><span data-stu-id="d809e-135">For example, using these values:</span></span> 
    
  - <span data-ttu-id="d809e-136">根資料夾-C:\Collected 資料</span><span class="sxs-lookup"><span data-stu-id="d809e-136">root folder - C:\Collected Data</span></span> 
    
  - <span data-ttu-id="d809e-137">容器 url- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp; sr = c&amp;si = NonOfficeData15 %7 C 0&amp;簽章 = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA %3d</span><span class="sxs-lookup"><span data-stu-id="d809e-137">container url - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D</span></span>
    
    <span data-ttu-id="d809e-138">是 AzCopy 命令列語法：</span><span class="sxs-lookup"><span data-stu-id="d809e-138">the AzCopy command line syntax would be:</span></span>
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    <span data-ttu-id="d809e-139">如需有關 Azcopy 語法請參閱 ＜[將 windows AzCopy 與資料傳輸](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="d809e-139">For more information on Azcopy syntax see, [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="d809e-140">必須有一個每位使用者的根資料夾和資料夾名稱必須是*alias@domainname*格式。</span><span class="sxs-lookup"><span data-stu-id="d809e-140">There must be one root folder per user and the folder name must be in the  *alias@domainname*  format.</span></span> 
  
8. <span data-ttu-id="d809e-p108">一旦完成資料夾上傳，切換至 [進階 eDiscovery。在您上傳的資料夾中的內容現在已可處理進階在 eDiscovery 中。選取的容器，並按一下 [程序] 按鈕。如需詳細資訊在進階 eDiscovery 處理查看，[執行程序模組和 Office 365 進階在 eDiscovery 中的將資料載入](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="d809e-p108">Once the folders have finished uploading, switch back to Advanced eDiscovery. The content in the folders you uploaded is now ready to be processed in Advanced eDiscovery. Select the container and click the Process button. For more details on Advanced eDiscovery Processing see, [Run the Process module and load data in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d809e-p109">一旦容器會成功處理進階在 eDiscovery 中，您將不再能夠 SAS 存放區 Azure 中新增新的內容。如果您收集其他的內容與您想要新增至進階的 eDiscovery 分析的案例，您必須建立新的**非 Office 365 資料**容器和重複此程序。</span><span class="sxs-lookup"><span data-stu-id="d809e-p109">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure. If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="d809e-147">如果容器*不會處理成功由於資料夾命名問題*與您然後修正的問題，您仍必須以建立新的容器與重新連線及上傳一次使用本文中的程序。</span><span class="sxs-lookup"><span data-stu-id="d809e-147">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span> 
  

