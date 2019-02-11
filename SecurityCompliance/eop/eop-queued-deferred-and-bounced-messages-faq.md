---
title: EOP 排入佇列、延後和退回的訊息常見問題集
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: 本主題提供有關已排入佇列、延遲，或在 Microsoft Exchange Online Protection (EOP) 篩選程序中退回之郵件的常見問題解答。
ms.openlocfilehash: 4b2c902adacd6e72e587aadaceecd22dd0084d85
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29686423"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP 排入佇列、延後和退回的訊息常見問題集

本主題提供有關已排入佇列、延遲，或在 Microsoft Exchange Online Protection (EOP) 篩選程序中退回之郵件的常見問題解答。
  
 **問：為何將郵件排入佇列？**
  
答：如果服務無法連線到傳遞的收件者伺服器，郵件會排入佇列或延遲。如果從收件者的網路傳回 500 系列錯誤，它不會延遲郵件。
  
 **問：如何延遲郵件？**
  
答：當收件者伺服器的連線無法建立，而且收件者的伺服器傳回連接逾時、連線被拒絕或 400 系列錯誤等「暫存失敗」時，就會保留郵件。如果發生永久性失敗 (例如 500 系列錯誤)，郵件就會傳回給寄件者。
  
 **問：郵件維持延遲的時間有多長，而重試間隔時間有多長？**
  
A.郵件延期中仍然我們佇列中的 2 天。郵件重試次數根據我們得到收件者的郵件系統中的錯誤。第幾個 deferrals 為 15 分鐘或小於與後續的重試次數 （透過下的半數十或賣） 增加透過多個最大值為 60 分鐘重試的間隔。時間間隔期間擴充是動態，考慮到多個佇列大小和內部郵件優先順序的變數。在基本、 它是 15 分鐘 （小於或等於） 若要啟動，然後展開從該處透過後續的幾個小時為最大 60 分鐘。
  
 **問：還原您的電子郵件伺服器後，已排入佇列的郵件如何散佈？**
  
答：您的電子郵件伺服器還原後，所有排入佇列的郵件會在伺服器無法使用時，自動根據他們被接收與排入佇列的順序自動進行處理。 
  

