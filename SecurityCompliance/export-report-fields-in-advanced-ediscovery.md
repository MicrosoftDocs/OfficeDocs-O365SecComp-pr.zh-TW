---
title: 在 Office 365 進階電子文件探索中匯出報告欄位
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 840a5aff-ecd0-4e56-ad22-fe99bc143687
description: 說明進階 ediscovery 匯出報告所包含的所有欄位。
ms.openlocfilehash: a578523098248bcfa16ea8ba97d756d97ba060fa
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526440"
---
# <a name="export-report-fields-in-office-365-advanced-ediscovery"></a>在 Office 365 進階電子文件探索中匯出報告欄位

> [!NOTE]
> 進階的 eDiscovery 需要您組織與進階規範附加元件或 E5 訂閱 Office 365 E3。如果您不具有該對應並想要嘗試進階的 eDiscovery，您還可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
本主題說明進階的 eDiscovery 匯出報表欄位標準與所有的範本。
  
## <a name="export-report-fields"></a>匯出報表欄位

下表列出每個匯出範本的欄位。
  
|**匯出欄位名稱**|**群組**|**說明**|**適用於標準的範本**|**適用於所有的範本**|
|:-----|:-----|:-----|:-----|:-----|
|即  <br/> |一般  <br/> |列號。  <br/> |是  <br/> |是  <br/> |
|File_ID  <br/> |一般  <br/> |檔案識別碼。  <br/> |是  <br/> |是  <br/> |
|File_class  <br/> |處理   <br/> |檔案類別。  <br/> |是  <br/> |是  <br/> |
|Family_ID  <br/> |處理   <br/> |用來群組檔案 （通常是電子郵件的執行個體和其附件） 的數值識別碼。  <br/> |是  <br/> |是  <br/> |
|For_review  <br/> |處理   <br/> |表示欄位要併入匯出供檢閱的旗標。  <br/> |是  <br/> |是  <br/> |
|Native_file_name  <br/> |處理   <br/> |原生檔案名稱，而不參照資料夾和分機號碼。  <br/> |是  <br/> |是  <br/> |
|Custodians  <br/> |一般  <br/> |Custodian 的檔案。  <br/> |是  <br/> |是  <br/> |
|Set_ID  <br/> |分析  <br/> |"ND 設定 」 或者 「 電子郵件設定 」 的識別碼。  <br/> |是  <br/> |是  <br/> |
|Inclusive_type  <br/> |電子郵件  <br/> |表示如果檔案 （含），根據下列值： 0-不 （含)、 1-（含)、 2-減去 3-（含） 的副本 （含)。  <br/> |是  <br/> |是  <br/> |
|Marked_as_pivot  <br/> |接近重複項目  <br/> |表示是否檔案是 [樞紐分析表。  <br/> |是  <br/> |是  <br/> |
|Similarity_percent  <br/> |接近重複項目  <br/> |相似性相對於 [樞紐分析表的百分比。  <br/> |是  <br/> |是  <br/> |
|Duplicate_subset  <br/> |接近重複項目  <br/> |重複的子集合的唯一識別碼。會指出檔案是否具有完全文字重複項目。  <br/> |是  <br/> |是  <br/> |
|日期  <br/> |一般  <br/> |檔案的日期 (取決於檔案類型-電子郵件： 傳送的日期、 文件： 修改日期)。  <br/> |是  <br/> |是  <br/> |
|Dominant_theme  <br/> |分析  <br/> |主要的佈景主題的檔案。  <br/> |是  <br/> |是  <br/> |
|Themes_list  <br/> |主題  <br/> |佈景主題名稱的清單。  <br/> |是  <br/> |是  <br/> |
|ND_set  <br/> |EquiSet  <br/> |Nearduplicate 集的唯一數字識別碼。  <br/> |是  <br/> |是  <br/> |
|Email_set  <br/> |電子郵件  <br/> |唯一的數字識別碼的電子郵件設定]。  <br/> |是  <br/> |是  <br/> |
|Email_thread  <br/> |電子郵件  <br/> |說明在電子郵件中的電子郵件的位置設定的所有節點識別碼 Consists 根目錄中目前的電子郵件、 以句號分隔。  <br/> |是  <br/> |是  <br/> |
|Email_subject  <br/> |電子郵件  <br/> |電子郵件的主旨。  <br/> |是  <br/> |是  <br/> |
|Email_date_sent  <br/> |電子郵件  <br/> |在其所傳送的電子郵件的日期。  <br/> |是  <br/> |是  <br/> |
|Email_participants  <br/> |電子郵件  <br/> |所有參與者的電子郵件執行緒，其中包含連結遺漏的電子郵件地址。  <br/> |是  <br/> |是  <br/> |
|Email_participant_domains  <br/> |電子郵件  <br/> |在電子郵件執行緒，包括遺失的連結中的所有參與者的網域。  <br/> |是  <br/> |是  <br/> |
|Email_sender  <br/> |電子郵件  <br/> |電子郵件寄件者名稱和/或地址。  <br/> |是  <br/> |是  <br/> |
|Email_sender_domain  <br/> |電子郵件  <br/> |電子郵件寄件者的網域。  <br/> |是  <br/> |是  <br/> |
|Email_to  <br/> |電子郵件  <br/> |收件者的電子郵件。  <br/> |是  <br/> |是  <br/> |
|Email_cc  <br/> |電子郵件  <br/> |[副本] 收件者的電子郵件。  <br/> |是  <br/> |是  <br/> |
|Email_bcc  <br/> |電子郵件  <br/> |[密件副本收件者的電子郵件。  <br/> |是  <br/> |是  <br/> |
|Email_recipient_domains  <br/> |電子郵件  <br/> |電子郵件收件者 (To、 [副本] 及 [密件副本]） 的網域。  <br/> |是  <br/> |是  <br/> |
|Email_date_received  <br/> |電子郵件  <br/> |在其收到電子郵件的日期。  <br/> |是  <br/> |是  <br/> |
|Email_action  <br/> |電子郵件  <br/> |值： 根據電子郵件主旨:"向前"(如"FW:")，"Reply"(的"RE:") 或"其他"（其他主體文字）。  <br/> |是  <br/> |是  <br/> |
|Meeting_Start_Date/時間  <br/> ||啟動日期和時間的會議項目。  <br/> |是  <br/> |是  <br/> |
|Meeting_End_Date/時間  <br/> ||日期及時間的結束會議項目。  <br/> |是  <br/> |是  <br/> |
|File_relevance_score  <br/> |相關性  <br/> |相關性分數 (0-100)。每個問題。  <br/> |是  <br/> |是  <br/> |
|Family_relevance_score  <br/> |相關性  <br/> |最大系列相關性分數 (0-100)。每個問題。  <br/> |是  <br/> |是  <br/> |
|Relevance_tag  <br/> |相關性  <br/> |若檔案已手動中已標記的相關性標記的檔案。每個問題。  <br/> |是  <br/> |是  <br/> |
|Relevance_load_group  <br/> |相關性  <br/> |相關性負載群組，指定的檔案，以個別問題] 欄位。  <br/> |是  <br/> |是  <br/> |
|Normalized_relevance_score  <br/> |相關性  <br/> |正規化的相關性分數 (0-100)，這是相較下的問題和載入之間。  <br/> |是  <br/> |是  <br/> |
|Marked_as_seed  <br/> |相關性  <br/> |如果它設為可為植入檔的相關性每個問題/類別中，標記的檔案。  <br/> |是  <br/> |是  <br/> |
|Marked_as_pre 標記  <br/> |相關性  <br/> |如果它是設定為預先標記相關性每個問題/類別中，標記的檔案。  <br/> |是  <br/> |是  <br/> |
|Relevance_status_description  <br/> |相關性  <br/> |相關性狀態的描述。  <br/> |是  <br/> |是  <br/> |
|註解  <br/> |一般  <br/> |使用者所輸入的註解。  <br/> |是  <br/> |是  <br/> |
|Export_input_path  <br/> |處理   <br/> |匯出輸入的路徑。  <br/> |是  <br/> |是  <br/> |
|Pivot_ID  <br/> |接近重複項目  <br/> |[樞紐分析表檔案的識別碼。  <br/> |是  <br/> |是  <br/> |
|Family_size  <br/> |處理   <br/> |在系列中的檔案數目。  <br/> |是  <br/> |是  <br/> |
|Native_type  <br/> |處理   <br/> |原生檔案類型。例如，試算表或簡報。  <br/> |是  <br/> |是  <br/> |
|Native_MD5  <br/> |處理   <br/> |原生檔案 MD5 雜湊值。  <br/> |是  <br/> |是  <br/> |
|Native_size  <br/> |處理   <br/> |原生檔案大小限制。  <br/> |是  <br/> |是  <br/> |
|Native_extension  <br/> |處理   <br/> |原生副檔名。  <br/> |是  <br/> |是  <br/> |
|Doc_date_modified  <br/> |文件屬性  <br/> |修改原生檔案，取自檔案的中繼資料的日期。  <br/> |是  <br/> |是  <br/> |
|Doc_date_created  <br/> |文件屬性  <br/> |日期原生檔案建立時，從檔案的中繼資料進行。  <br/> |是  <br/> |是  <br/> |
|Doc_modified_by  <br/> |文件屬性  <br/> |修改取自檔案的中繼資料的原生檔案的使用者。  <br/> |是  <br/> |是  <br/> |
|O365_date_modified  <br/> |文件屬性  <br/> |已修改日期原生檔案，請採取從 SharePoint 或 Exchange 的欄位。  <br/> |是  <br/> |是  <br/> |
|O365_date_created  <br/> |文件屬性  <br/> |建立日期原生檔案，取自 SharePoint] 或 [Exchange] 欄位。  <br/> |是  <br/> |是  <br/> |
|O365_modified_by  <br/> |文件屬性  <br/> |使用者上次修改原生檔案，取自 SharePoint] 或 [Exchange] 欄位。  <br/> |是  <br/> |是  <br/> |
|Compound_path  <br/> |處理   <br/> |包括其複合來源原生檔案路徑。  <br/> |是  <br/> |是  <br/> |
|Input_path  <br/> |處理   <br/> |輸入檔案的路徑。  <br/> |是  <br/> |是  <br/> |
|Input_date_modified  <br/> |處理   <br/> |上次修改日期的輸入檔。  <br/> |是  <br/> |是  <br/> |
|ND_ET_sort_excl_attach  <br/> |分析  <br/> |連鎖電子郵件設定和 ND 設定供檢閱。有 ' ND 集及 'E' 首碼新增至電子郵件 ssets 新增。  <br/> |是  <br/> |是  <br/> |
|ND_ET_sort_incl_attach  <br/> |分析  <br/> |連鎖電子郵件設定和設定供檢閱的 ND 嗎 ' 時新增至 ND 集與 'E' 首碼新增至電子郵件設定。每個電子郵件內 Email_set 此外，後面接著其適當的附件。  <br/> |是  <br/> |是  <br/> |
|Deduped_custodians  <br/> |一般  <br/> |取消上當檔案的 custodians  <br/> |是  <br/> |是  <br/> |
|Deduped_file_IDs  <br/> |一般  <br/> |取消上當檔案的識別碼  <br/> |是  <br/> |是  <br/> |
|Deduped_paths  <br/> |一般  <br/> |取消上當檔案的路徑  <br/> |是  <br/> |是  <br/> |
|File_key  <br/> |一般  <br/> |供日後使用的內部識別項。  <br/> |是  <br/> |是  <br/> |
|Export_native_path  <br/> |處理   <br/> |匯出套件中的原生檔案的路徑。  <br/> |是  <br/> |是  <br/> |
|Extracted_text_path  <br/> |處理   <br/> |解壓縮檔案的路徑。  <br/> |是  <br/> |是  <br/> |
|Process_batch  <br/> |處理   <br/> |批次匯入批次的識別碼。  <br/> |是  <br/> |是  <br/> |
|Process_status_ID  <br/> |處理   <br/> |表示程序階段狀態識別碼。  <br/> |是  <br/> |是  <br/> |
|Process_status_description  <br/> |處理   <br/> |程序階段狀態描述： 成功或錯誤的描述。  <br/> |是  <br/> |是  <br/> |
|Export_status_ID  <br/> |處理   <br/> |匯出狀態的識別碼。  <br/> |是  <br/> |是  <br/> |
|Export_status_description  <br/> |處理   <br/> |匯出狀態 ； 的描述成功或錯誤的描述。  <br/> |是  <br/> |是  <br/> |
|Read_percent  <br/> |相關性  <br/> |讀取 %(0-100)。每個問題。  <br/> |是  <br/> |是  <br/> |
|Doc_author  <br/> |文件屬性  <br/> |文件屬性： 作者。  <br/> |否  <br/> |是  <br/> |
|Doc_comments  <br/> |文件屬性  <br/> |文件屬性： 註解。  <br/> |否  <br/> |是  <br/> |
|Doc_keywords  <br/> |文件屬性  <br/> |文件屬性： 關鍵字。  <br/> |否  <br/> |是  <br/> |
|Doc_last_saved_by  <br/> |文件屬性  <br/> |文件屬性： 上次儲存。  <br/> |否  <br/> |是  <br/> |
|Doc_revision  <br/> |文件屬性  <br/> |文件屬性： 修訂版編號。  <br/> |否  <br/> |是  <br/> |
|Doc_subject  <br/> |文件屬性  <br/> |文件屬性： 主旨。  <br/> |否  <br/> |是  <br/> |
|Doc_template  <br/> |文件屬性  <br/> |文件屬性： 範本。  <br/> |否  <br/> |是  <br/> |
|Doc_title  <br/> |文件屬性  <br/> |文件屬性： 標題。  <br/> |否  <br/> |是  <br/> |
|Email_has_attachment  <br/> |電子郵件  <br/> |會指出電子郵件是否具有一或多個附件。  <br/> |否  <br/> |是  <br/> |
|Email_importance  <br/> |電子郵件  <br/> |電子郵件重要性屬性。  <br/> |否  <br/> |是  <br/> |
|Email_level  <br/> |電子郵件  <br/> |會指出在電子郵件執行緒內的電子郵件的層級。附件，附加的電子郵件的值。  <br/> |否  <br/> |是  <br/> |
|Email_recipients  <br/> |電子郵件  <br/> |名稱和/或 (To、 [副本] 及 [密件副本]） 的地址的電子郵件收件者。  <br/> |否  <br/> |是  <br/> |
|Email_security  <br/> |電子郵件  <br/> |電子郵件安全性屬性。  <br/> |否  <br/> |是  <br/> |
|Email_sensitivity  <br/> |電子郵件  <br/> |Sensitivity 屬性的電子郵件。  <br/> |否  <br/> |是  <br/> |
|Export_batch  <br/> |處理   <br/> |檔案的最後一個匯出批次名稱。  <br/> |否  <br/> |是  <br/> |
|Export_session  <br/> |處理   <br/> |檔案的最後一個匯出工作階段的識別碼包括日期。  <br/> |否  <br/> |是  <br/> |
|Extracted_text_length  <br/> |處理   <br/> |擷取文字檔的字元長度。  <br/> |否  <br/> |是  <br/> |
|Family_duplicate_set  <br/> |處理   <br/> |系列彼此的確切文字重複的數字識別碼 （分別-系列中的所有成員都是完全重複）。  <br/> |否  <br/> |是  <br/> |
|Has_Text  <br/> |處理   <br/> |會指出檔案中有沒有文字： 0-沒有;1-[是]。  <br/> |否  <br/> |是  <br/> |
|Input_file_ID  <br/> |處理   <br/> |從從中擷取檔案輸入檔案的識別碼。  <br/> |否  <br/> |是  <br/> |
|Native_SHA_256  <br/> |處理   <br/> |原生檔案 256 SHA-1 雜湊值。  <br/> |否  <br/> |是  <br/> |
|O365_authors  <br/> |文件屬性  <br/> |修改從 SharePoint 或 Exchange 欄位所採取的原生檔案的使用者。  <br/> |否  <br/> |是  <br/> |
|O365_created_by  <br/> |文件屬性  <br/> |建立從 SharePoint 或 Exchange 欄位所採取的原生檔案的使用者。  <br/> |否  <br/> |是  <br/> |
|Parent_node  <br/> |電子郵件  <br/> |是不是遺失的連結最接近父節點中的電子郵件執行緒的節點。  <br/> |否  <br/> |是  <br/> |
|Set_order_inclusives_first  <br/> |電子郵件  <br/> |電子郵件和附件： 計數器的時間先後順序 (Inclusives 第一個)。文件： 樞紐 first 和其餘由相似性分數、 遞減。  <br/> |否  <br/> |是  <br/> |
|Tagged_By  <br/> |相關性  <br/> |相關性中已標記該檔案的特定問題的使用者。  <br/> |否  <br/> |是  <br/> |
|Word_count  <br/> |分析  <br/> |文件中文字的數目。  <br/> |否  <br/> |是  <br/> |
|||||||||||
||||||
||||||
   
## <a name="related-topics"></a>相關主題

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[匯出與進階 eDiscovery 案件資料](export-case-data-in-advanced-ediscovery.md)
  
[匯出結果](export-results-in-advanced-ediscovery.md)
  
[檢視批次歷程記錄和匯出過去的結果](view-batch-history-and-export-past-results.md)
  

