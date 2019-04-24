---
title: 建立搜尋以收集資料
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
ms.openlocfilehash: 14f90b29cbff9c1a588b816563178039c7af7da6
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243411"
---
# <a name="create-a-search-to-collect-data"></a>建立搜尋以收集資料

在您的情況下的 [**搜尋**] 索引標籤上您可以按一下 [**新增搜尋**，並遵循精靈建立新的搜尋。

## <a name="name-your-search-and-give-description"></a>命名您的搜尋，並提供說明

每個搜尋與案例應該有唯一的名稱。 （選用） 您可以提供的描述您的搜尋。 

## <a name="define-your-conditions"></a>定義您的條件

您可以定義用於搜尋使用預先內建的條件卡或使用關鍵字查詢語言 (KQL) 條件。 如需詳細資訊，請參閱 <<c0>建立搜尋查詢。

## <a name="choose-the-custodians-to-search-from"></a>選擇 [從搜尋 custodians

一旦您已經定義您的條件，您必須選擇您想要搜尋的位置。 若要這樣做的其中一個方法是藉由指定您想要搜尋您已經新增至案例哪些 custodians。 藉由選取 custodian，您將針對所有的資料來源對應至 custodian 執行搜尋。 如需如何將 custodians 新增至您的案例及管理其資料來源詳細資訊，請參閱[Work with custodians](managing-custodians.md) 。

## <a name="choose-non-custodial-locations"></a>選擇 [非 custodial 位置

在某些情況下，您可能想要搜尋不會對應到 custodian 的資料來源。 在此情況下，您可以指定您想要搜尋，或選擇搜尋特定的 Office 365 服務 （例如搜尋所有 Exchange 信箱或所有 SharePoint 和 OneDrive for Business 網站） 的所有內容位置的位置。