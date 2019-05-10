---
title: 將非 Office 365 的資料載入檢閱集
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
ms.openlocfilehash: 60775002d5ebec83aacbec350a044b9d6ffeb461
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834955"
---
# <a name="load-non-office-365-data-into-a-review-set"></a>將非 Office 365 的資料載入檢閱集

並非所有文件，您可能需要與 Office 365 進階電子文件探索分析會存在於 Office 365 中。 使用非 Office 365 內容匯入您可以上傳到設定分析進階電子文件與因此檢閱不 live Office 365 中的文件的進階電子文件中的功能。 此程序將示範如何將非 Office 365 文件移入進階電子文件探索進行分析。

>[!Note]
>進階電子文件為您的組織需要與進階合規性附加元件或 E5 訂閱 Office 365 E3。 如果您不具有該計劃，並想要再試進階電子文件，您可以註冊 Office 365 企業版 E5 的試用版。

## <a name="before-you-begin"></a>開始之前

使用上傳非 Office 365 功能，如本文所述，需要您有下列：

- Office 365 或 Microsoft 365 E5 訂閱或與進階合規性的附加元件訂閱版 E3 訂閱。

- 將上傳其非 Office 365 內容的所有 custodians 必須有版 E3 授權來搭配進階合規性的附加元件授權或具有 E5 授權。

- 現有的進階電子文件探索案例。

- Custodians 必須新增至這種情況，您將有相關聯的非 Office 365 資料上傳至它們之前。

- 將上傳的所有檔案必須都位於的資料夾，其中每個資料夾是與特定 custodian 相關聯。 這些資料夾的名稱必須使用下列的命名格式： *alias@domainname*。 *Alias@domainname*必須是使用者的 Office 365 別名和網域。 您可以收集所有*alias@domainname*資料夾到根資料夾。 根資料夾僅能包含*alias@domainname*資料夾;寬鬆的檔案不允許的根資料夾中。

   比方說，您要上傳的非 Office 365 資料的資料夾結構可能與下列相似：

   - c:\nonO365\ abraham.mcmahon@contoso.com
   - c:\nonO365\ jewell.gordon@contoso.com
   - c:\nonO365\ staci.gonzalez@contoso.com

   其中 abraham.mcmahon@contoso.com、 jewell.gordon@contoso.com 及 staci.gonzalez@contoso.com 均的情況下 custodians 的 SMTP 地址。

   ![非 Office 365 的資料上傳資料夾結構](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- EDiscovery 管理員 」 或 「 eDiscovery 系統管理員帳戶

- 具有非 Office 365 內容的資料夾結構的存取權的電腦上安裝 Microsoft Azure 儲存體工具。

- 安裝 AzCopy，您可以從這裡：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>非 Office 365 內容上傳至進階電子文件

1. EDiscovery 管理員或 eDiscovery 系統管理員，以開啟 [進階電子文件，然後將上傳到非 Office 365 資料的案例]。  **檢閱 [設定**] 索引標籤，然後選取您想要將非 Office 365 資料載入檢閱設定。  如果您未建立檢閱設定，您可以立即執行。  最後，按一下 [**管理檢閱設定**，然後按一下 [**檢視上傳**中 * * 非 Office 365 [資料] 磚。

2. 按一下 [**上傳檔案**] 按鈕來啟動非 Office 365 資料匯入精靈]。

   ![上傳檔案](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. 在精靈中的第一個步驟只會準備要上傳檔案的安全 Azure blob。  準備完成之後，按一下 [**下一步： 將檔案上傳**] 按鈕。

   ![非 Office 365 匯入-準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. 在 [**上傳檔案**] 步驟中，指定**的檔案位置路徑**] 中，這是您計劃匯入非 Office 365 資料所在的位置。  設定正確的位置可確保正確更新命令 AzCopy。

   > [!NOTE]
   > 如果您未安裝 AzCopy，您可以從這裡：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. 按一下 [**複製到剪貼簿**] 連結，將複製的預先定義的命令。 啟動 windows 命令提示字元中，貼上命令並按 enter 鍵。  檔案就會上傳到安全的 Azure blob 儲存的下一個步驟。

   ![非-Office 365 匯入-上傳檔案](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   ![非 Office 365 匯入-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > 如果提供的 AzCopy 命令失敗，請參閱[疑難排解 AzCopy 進階電子文件中](troubleshooting-azcopy.md)

6. 最後，傳回回到安全性 & 合規性，並按一下 [**下一步： 處理檔案**] 按鈕。  這將會引發處理、 文字擷取和編製索引的上傳的檔案。  您可以追蹤處理以下或在 [**工作**] 索引標籤中的進度。 完成之後，新的檔案則可在檢閱設定。  處理完成後，您可以關閉精靈。

   ![非-Office 365 匯入的程序檔案](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

