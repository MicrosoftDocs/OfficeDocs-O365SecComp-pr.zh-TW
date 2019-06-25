---
title: Office 365 ATP 安全附件的運作方式
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: '[安全附件] 功能可提供電子郵件附件的按一下時間驗證。 使用安全附件來保護您的組織, 防止他人以電子郵件傳送或接收的惡意檔案。'
ms.openlocfilehash: 99d31e327343971f6a7630e2a43ffd3044fbf976
ms.sourcegitcommit: 424a614141c1f19a1c84a67ec2d71dd3d7ef6694
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/30/2019
ms.locfileid: "34592251"
---
# <a name="how-ffice-365-atp-safe-attachments-works"></a>Office 365 ATP 安全附件的運作方式

## <a name="how-it-works"></a>運作方式

ATP 安全附件功能會檢查您組織中人員的電子郵件附件。 當 ATP 安全附件原則到位, 且該原則所涵蓋的人員會在 Office 365 中查看其電子郵件時, 會檢查其電子郵件附件, 並根據您的 ATP 安全附件原則採取適當的動作。 根據您的原則定義方式, 使用者可以繼續運作, 而不需要知道他們是否已傳送惡意檔案。
  
以下是工作中 ATP 安全附件的兩個範例。
  
- **範例 1: 電子郵件附件**假設您會收到具有附件的電子郵件。 如果附件是安全的, 或實際包含的惡意程式碼是用來竊取使用者認證的, 並不是顯而易見的。 在「管理員」的組織中, 安全性管理員在幾天前定義 ATP 安全附件原則。 使用 ATP 安全附件功能時, 電子郵件附件會在虛擬環境中開啟和測試, 然後才會收到。 如果附件被判定為惡意, 就會自動將其移除。 如果附件是安全的, 當您按一下時, 它會如預期的方式開啟。

- **範例 2: SharePoint Online 中的**檔案假設 Jean-francois 收到檔案, 並將其上傳至 SharePoint Online 中的文件庫。 Jean-francois 會與小組的其餘部分共用檔案的連結, 而不知道該檔案實際上是惡意的。 幸運的是, [SharePoint、OneDrive 及 Microsoft 團隊的 ATP](atp-for-spo-odb-and-teams.md)會偵測惡意檔案並加以封鎖。 幾天之後, Chris 會開啟檔。 雖然 Chris 可以看到該檔案, 但是 Chris 無法開啟或共用, 這會保護 Chris 的電腦與其他惡意檔案。

ATP 安全附件原則可以套用至組織中的特定人員或群組, 或套用至整個網域。 此外, ATP 安全附件原則可以設定為在掃描實際附件時使用預留位置附件。 若要深入瞭解, 請參閱**[在 Office 365 中設定 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)**。

> [!NOTE]
> ATP 安全附件掃描會在您的 Office 365 資料所在的同一個區域中進行。 如需資料中心地理位置的詳細資訊, 請參閱[您的資料位於何處？](https://products.office.com/where-is-your-data-located?geo=All) 

