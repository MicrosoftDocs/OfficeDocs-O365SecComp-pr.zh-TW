---
title: 處理資料時發生補救錯誤
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
ms.openlocfilehash: bf48e605dc321da4b7a9d5343d18f90fbb179073
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296726"
---
# <a name="error-remediation-when-processing-data"></a>處理資料時發生補救錯誤

錯誤修復允許 eDiscovery 系統管理員能夠修正防止進階的 eDiscovery （預覽） 適當地處理內容的資料問題。例如，由於檔案鎖定或加密無法處理受到密碼保護的檔案。使用錯誤補救、 eDiscovery 管理員可以下載含有這類錯誤的檔案、 移除密碼保護及上傳的已修復的檔案。

使用下列工作流程來修復檔案與進階的 eDiscovery （預覽） 案例中的錯誤。

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>建立要修復檔案處理錯誤的錯誤補救工作階段

>[!NOTE]
>如果錯誤補救精靈已關閉下列程序期間的任何時候，您可以傳回給錯誤補救工作階段的 [**處理**] 索引標籤來**檢視**下拉式功能表中選取**錯誤補救措施**。

1. [**處理**] 索引標籤進階的 eDiscovery （預覽） 案例中選取 [**檢視**下拉式清單功能表中的 [**錯誤**]。

2. 選取您要修復按一下旁邊的錯誤類型或檔案類型] 選項按鈕的錯誤。 在下列範例中，我們要補救相關密碼保護的檔案。

3. 按一下 [ **+ 新錯誤補救方法**。

    ![錯誤修復](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    錯誤修復工作階段會開始，開頭準備階段而發生此錯誤的檔案移至安全的 Azure 位置下載位置。

    ![準備錯誤補救方法](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. 準備完成後，按一下 [**下一步： 下載檔案**繼續進行下載。

    ![下載檔案](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. 若要下載檔案，指定**供下載的目的路徑**；這是您應該已下載檔案的位置的本機電腦上的路徑。 預設路徑，%userprofile%\downloads\errors、 指向已登入使用者的下載項目資料夾;這可以視需要變更。

    >[!NOTE]
    >我們建議您使用本機檔案路徑，而不是遠端網路路徑以達最佳效能。

    > [!NOTE]
    > 若您尚未安裝 AzCopy，您可以從這裡來進行安裝：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

6. 依序按一下 [**複製到剪貼簿**中複製的預先定義的命令。啟動 windows 命令提示字元下、 貼上命令並按**Enter**。  

    將下載的檔案。

    ![準備錯誤補救方法](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > 如果您有執行此命令的問題，請參閱https://go.microsoft.com/fwlink/?linkid=2038117疑難排解秘訣。

7. 下載檔案之後, 可以修復它們與適當的工具。受密碼保護之檔案有許多密碼破解您可以使用的工具。如果您知道檔案密碼，您可以開啟其並移除密碼保護。
    > [!NOTE]
    > IT 重要您保留可識別的已修復檔案的目錄結構和檔案名稱。 所有的命名慣例用於下載的檔案及資料夾進行可能產生關聯回原始的 remdiated 檔案。

8. 現在，傳回進階 ediscovery （預覽） 並按一下 [**下一步： 上傳檔案**。 這會將移至下一個步驟可以立即上載的檔案。

    ![上傳檔案](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. 不必**的檔案位置路徑**] 文字方塊中的已修復檔案的位置然後按一下 [**複製到 clibpboard**。

10. 貼到 Windows 命令提示字元上命令並按**Enter**以上傳檔案。

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. 最後，傳回進階 ediscovery （預覽） 並按一下 [**下一步： 處理檔案**。

12. 當處理已完成。 您可以返回工作集並查看已修復的檔案。

## <a name="what-happens-when-files-are-remediated"></a>檔案會在於時會發生什麼情況

當已修復的檔案上傳時、 原始的中繼資料會保留除了下列欄位： 

- DocumentExtractedUrl
- ExtractedTextSize
- HasText
- IsErrorRemediate
- IsParentExtractedUrl
- ItemExtractedUrl
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- 文字
- WordCount
- WorkingsetId

進階 eDiscovery (Preview) 中的所有文件中繼資料欄位的定義，請參閱[文件中繼資料欄位](document-metadata-fields.md)。