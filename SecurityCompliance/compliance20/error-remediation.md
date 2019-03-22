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
ms.openlocfilehash: f6db3c178e584c45cf282158c58fb5125dc41f3f
ms.sourcegitcommit: cf9d9b545a7c153d314aa9c08c7fb16fcd785b3e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2019
ms.locfileid: "30737673"
---
# <a name="error-remediation-when-processing-data"></a>處理資料時發生補救錯誤

錯誤修復允許 eDiscovery 系統管理員修正正確處理內容時，防止進階電子文件 （預覽） 的資料問題的能力。 例如，因為檔案已鎖定或加密，無法處理受到密碼保護的檔案。 使用錯誤修復，eDiscovery 系統管理員可以下載這類錯誤的檔案、 移除密碼保護和修復的檔案上傳。

使用下列工作流程來修復在進階電子文件 （預覽） 的情況下發生錯誤的檔案。

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>建立要修復檔案與處理錯誤的錯誤修復工作階段

>[!NOTE]
>如果錯誤修復精靈已關閉隨時在下列程序期間，您可以傳回的錯誤修復工作階段 [**處理**] 索引標籤選取 [**檢視**] 下拉式功能表中的 [**錯誤補救措施**。

1. [**處理**] 索引標籤在進階電子文件 （預覽） 案例中，選取 [**檢視**] 下拉式功能表中的 [**錯誤**]。

2. 選取您要修復]，即可錯誤類型或檔案類型] 旁的 [選項] 按鈕的錯誤。  在下列範例中，我們正在修復密碼保護的檔案。

3. 按一下 [ **+ 新錯誤修復**]。

    ![錯誤修復](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    錯誤修復工作階段會開始，開始準備階段，而發生錯誤的檔案移至安全的 Azure 位置下載位置。

    ![準備錯誤修復](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. 準備工作完成後，按一下 [**下一步： 下載檔案**繼續進行下載。

    ![下載檔案](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. 若要下載檔案，指定 [**下載的目的路徑**;這是您應該已下載檔案的位置的本機電腦上的路徑。  預設路徑，%userprofile%\downloads\errors，指向登入使用者的下載項目資料夾;這可以視需要變更。

    >[!NOTE]
    >我們建議而不是遠端網路路徑使用本機檔案路徑，以獲得最佳效能。

    > [!NOTE]
    > 如果您未安裝 AzCopy，您可以從這裡安裝它：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

6. 按一下 [**複製到剪貼簿**複製預先定義的命令。 啟動 windows 命令提示字元中，貼上] 命令，並按**Enter**。  

    將下載的檔案。

    ![準備錯誤修復](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > 如果提供的 AzCopy 命令失敗，請參閱[疑難排解 AzCopy 在進階電子文件 （預覽）](troubleshooting-azcopy.md)

7. 下載檔案之後, 您可以使用適當工具修復它們。 密碼保護之檔案有許多密碼破解您可以使用的工具。 如果您知道之檔案的密碼，您可以將其開啟，並移除密碼保護。
    > [!NOTE]
    > IT 很重要，您會保留原封不動的修復檔案的目錄結構和檔案名稱。  所有命名慣例用於下載的檔案和資料夾會讓您能夠建立回原始的 remdiated 檔案的關聯。

8. 現在，返回進階電子文件 （預覽），然後按一下 [**下一步： 將檔案上傳**。  這將會移到下一步： 您現在可以上載檔案。

    ![上傳檔案](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. 請指定**的檔案位置路徑**] 文字方塊中，在修復檔案的位置然後按一下 [**複製到 clibpboard**。

10. 貼上命令到 Windows 命令提示字元，並按**Enter** ，以將檔案上傳。

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. 最後，回到 [進階電子文件 （預覽），然後按一下 [**下一步： 處理檔案**。

12. 當處理已完成。  您可以返回工作集，並查看修復的檔案。

## <a name="what-happens-when-files-are-remediated"></a>當檔案修復時，會發生什麼事

當修復的檔案上傳時，原始的中繼資料會保留除了下列欄位： 

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

如需進階電子文件 （預覽） 中的所有文件中繼資料欄位的定義，請參閱 <<c0>文件的中繼資料欄位。