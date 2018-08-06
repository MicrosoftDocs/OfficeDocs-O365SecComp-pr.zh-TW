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
ms.openlocfilehash: 17e5955195c4e38299712fb9161822984b2a643a
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026220"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP 排入佇列、延後和退回的訊息常見問題集

本主題提供有關已排入佇列、延遲，或在 Microsoft Exchange Online Protection (EOP) 篩選程序中退回之郵件的常見問題解答。
  
 **問：為何將郵件排入佇列？**
  
答：如果服務無法連線到傳遞的收件者伺服器，郵件會排入佇列或延遲。如果從收件者的網路傳回 500 系列錯誤，它不會延遲郵件。
  
 **問：如何延遲郵件？**
  
答：當收件者伺服器的連線無法建立，而且收件者的伺服器傳回連接逾時、連線被拒絕或 400 系列錯誤等「暫存失敗」時，就會保留郵件。如果發生永久性失敗 (例如 500 系列錯誤)，郵件就會傳回給寄件者。
  
 **問：郵件維持延遲的時間有多長，而重試間隔時間有多長？**
  
答：延遲中的郵件會保留在我們的佇列中 2 天。郵件重試次數是以從收件者的郵件系統傳回的錯誤為基礎。一般而言，郵件會每隔 5 分鐘重試一次。
  
 **問：還原您的電子郵件伺服器後，已排入佇列的郵件如何散佈？**
  
答：您的電子郵件伺服器還原後，所有排入佇列的郵件會在伺服器無法使用時，自動根據他們被接收與排入佇列的順序自動進行處理。 
  

