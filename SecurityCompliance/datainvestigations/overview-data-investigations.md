---
title: Microsoft 365 的資料調查 (預覽) 綜述
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
description: 本文說明 Microsoft 365 中的新資料調查 (預覽) 工具。
ms.openlocfilehash: 2b125d8f1dc24337804ea0461039aba824c42b8a
ms.sourcegitcommit: 6eb51931242d07abde2e37f1bd57d13bc724f0de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2019
ms.locfileid: "34547908"
---
# <a name="overview-of-data-investigations-preview-in-microsoft-365"></a>Microsoft 365 的資料調查 (預覽) 綜述

將包含機密、敏感或惡意內容的檔發行至不受信任的環境時, 會發生資料溢出。 偵測到資料溢出時, 請務必快速地包含環境、評估外泄的大小和位置、檢查其周圍的使用者活動, 然後從服務中刪除溢出的資料。 您可以使用新的資料調查 (預覽) 工具, 在 Office 365 中搜尋敏感、惡意或放錯位置的資料, 調查發生的情況, 並採取適當的動作來修復外泄。  

本文說明如何使用新的資料調查 (預覽) 工具中的功能來處理資料外泄案例。

## <a name="permissions"></a>權限

若要存取及進行資料調查, 您必須是「資料調查者」角色群組的成員。 如需詳細資訊, 請參閱[指派資料調查的許可權](permissions.md)。

## <a name="data-investigations-preview-workflow"></a>資料調查 (預覽) 工作流程 

下列各節說明內建工作流程中的每一個步驟, 在資料調查 (預覽) 中。 下列螢幕擷取畫面顯示名為高風險之調查的 [**首頁**] 索引標籤 *: [財務檔洩漏*]。 

![資料調查工具中的工作流程](../media/DataInvestigationsWorkflow.png)

## <a name="search-for-sensitive-malicious-or-misplaced-data"></a>搜尋敏感、惡意或放錯位置的資料

使用 [**搜尋**] 索引標籤來建立搜尋, 以尋找您要修正之資料的 Office 365。 您可以建立及執行查詢式搜尋, 以找出一組可能含有溢出資料的電子郵件訊息和檔, 然後將它們當做證據收集, 以供審閱和分析。 此外, 您也可以使用搜尋工具來預覽範例檔, 並查看可協助您精簡和改善搜尋結果的搜尋統計資料。 當您認為搜尋結果包含所有與調查相關的資料時, 您可以將搜尋結果新增至證據集, 以進一步審閱、影響評估, 並視需要採取補救動作。 如需詳細資訊, 請參閱[在調查中搜尋資料](search-for-data.md)。

## <a name="review-and-investigate-evidence"></a>檢查並調查證據

使用 [**證據**] 索引標籤來調查您從 live service 收集到的資料, 在此案例中為 Office 365。 證據集中的資料是您所收集的搜尋結果的快照。 當您將搜尋結果新增為證據時, 會觸發處理常式, 以提取檔案、中繼資料和文字。 此程式完成時, 資料調查工具會建立所有資料的新索引, 並將其新增至證據集。 針對任何時間敏感型調查, 這可讓您在調查隔離環境中所收集的證據時, 先刪除位於原始內容位置 (在 live service 中) 的資料, 以快速地包含環境。 收集證據之後, 您可以執行其他查詢, 依時間範圍、檔案類型、資料擁有者及其他類型的條件來縮小資料。 例如, 使用作者、寄件者和收件者條件, 您可以快速識別與資料溢出有關的人員, 以及是否有任何溢出的資料與組織外部的人員共用。

您也可以在所收集的證據上執行高級分析。 這可為您提供一般主題, 以及透過電子郵件執行緒、完全重複和接近重複專案來組織證據, 以協助您進行調查。 您可以使用解壓縮的文字視圖或原生檔案格式來查看檔, 並以調查結果標記它們。 如需詳細資訊，請參閱：

  - [檢閱辨識項中的資料](review-data-in-evidence.md)

  - [執行分析以更快速地調查](run-analytics-to-investigate-faster.md)


## <a name="managing-people-of-interest"></a>管理感興趣的人員

使用 [**感興趣的人員**] 索引標籤來新增和管理您在調查證據時已識別為感興趣的人員。 當您新增感興趣的人員時, 會識別並對應其資料來源 (例如其信箱和 OneDrive 帳戶)。 然後, 您可以僅搜尋這些人員的內容位置, 以限定其他搜尋的範圍。 依興趣的人員設定範圍時, 搜尋會更有效率且準確, 因為此工具會重新處理任何未編制索引的資料, 例如圖像或不支援的檔案類型。 在 [**感興趣的人員**] 索引標籤上, 您也可以查看和搜尋這些人員的 audit log 活動, 以進一步協助您進行調查。 您可以在整個調查中新增感興趣的人員。 如需詳細資訊, 請參閱[管理感興趣的調查人員](manage-people-of-interest.md)。

## <a name="indexing-the-data-of-people-of-interest"></a>編制感興趣之人員的資料索引

新增對調查感興趣的人員會從人員的資料來源重新索引任何已部分索引的專案。 此程式稱為「*高級索引*」。 高級索引重新處理資料 (如影像和不支援的檔案類型), 讓您在執行搜尋收集資料進行調查時, 可充分探索這些資料。 使用 [**處理**] 索引標籤來監視 [高級索引] 的狀態, 並修正使用稱為「*錯誤修復*」的程式可能發生的任何處理錯誤。 如需詳細資訊, 請參閱[處理調查資料時的錯誤修正](error-remediation.md)。

## <a name="exporting-data"></a>匯出資料

如果您想要匯出資料, 請使用 [**匯出**] 索引標籤來管理匯出工作, 並從證據集下載資料。 當您匯出證據時, 會將資料上傳至 Azure 儲存位置, 然後即可下載到本機電腦。 在 [**匯出**] 索引標籤上, 您可以取得 Azure 儲存位置 URL 和儲存評估金鑰, 這兩者都是下載匯出的資料所需的。 如需詳細資訊, 請參閱[從調查中匯出資料](export-data.md)。

## <a name="managing-jobs"></a>管理工作

使用 [**工作**] 索引標籤來監視長期執行的程式, 以取得與調查相關的工作。 這包括執行搜尋、將資料新增至證據集、重新編制索引資料, 以及匯出證據的工作。 例如, 您可能會在包含大量資料來源的 [**搜尋**] 索引標籤上建立新的搜尋。 此搜尋程式的狀態會顯示在 [**工作**] 索引標籤上。如需詳細資訊, 請參閱[在資料調查中管理工作](manage-jobs.md)。

## <a name="configuring-investigation-settings"></a>設定調查設定

使用 [**設定**] 索引標籤來設定調查範圍的設定。 這包括將成員新增至調查、關閉或刪除調查, 以及設定搜尋和分析行為。 如需詳細資訊, 請參閱[設定資料調查中的設定 (預覽)](configure-settings-datainvestigations.md)。
