---
title: 資訊屏障原則的屬性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 請使用本文做為資訊屏障原則中可使用的各種屬性參考。
ms.openlocfilehash: 896b87a3ccc696d3a8193e37237fe555d326ca52
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394308"
---
# <a name="attributes-for-information-barrier-policies-preview"></a>資訊障礙原則的屬性 (預覽)

Azure Active Directory 中的某些屬性可以用來分割使用者。 一旦定義區段後, 這些區段就可以做為資訊屏障原則的篩選器。 例如, 您可能會使用**部門**, 依組織中的部門定義使用者區段 (假設沒有單一員工同時對兩個部門運作)。 

本文說明如何將屬性與資訊障礙搭配使用, 並提供可使用的屬性清單。 若要深入瞭解資訊障礙, 請參閱下列資源:
- [資訊障礙 (預覽)](information-barriers.md)
- [定義 Microsoft 團隊中資訊障礙的原則 (預覽)](information-barriers-policies.md)
- [編輯 (或移除) 資訊屏障原則 (預覽)](information-barriers-edit-segments-policies.md.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>如何使用資訊屏障原則中的屬性

本文所列的屬性可用於定義或編輯使用者的區段。 在[資訊屏障原則](information-barriers-policies.md)中, 您定義的區段會做為參數 (稱為*UserGroupFilter*值)。

1. 決定要用來定義區段的屬性。 (請參閱本文中的[參考](#reference)一節)。

2. 請確定使用者帳戶的值已填入您在步驟1中選取的屬性。 查看使用者帳戶詳細資料, 如有必要, 編輯使用者帳戶以包含屬性值。 

    若要使用 PowerShell 來執行這項操作, 請參閱使用[Office 365 PowerShell 設定使用者帳戶屬性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)。

    若要在 Azure Active Directory 中執行此作業, 請參閱[使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。

3. [使用 PowerShell 定義區段](information-barriers-policies.md#define-segments-using-powershell), 類似下列範例:

    |範例  |Cmdlet  |
    |---------|---------|
    |使用部門屬性定義稱為 Segment1 的區段     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |使用 MemberOf 屬性定義稱為 SegmentA 的區段 (假設此屬性包含組名, 例如 "BlueGroup")     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |使用 ExtensionAttribute1 定義稱為 DayTraders 的區段 (假設此屬性包含職稱, 例如 "DayTrader")|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > 當您定義線段時, 請對您的所有區段使用相同的屬性。 例如, 如果您使用*部門*來定義某些區段, 請使用*部門*定義所有的區段。 請勿使用*部門*和其他使用*MemberOf*的其他區段來定義。 請確定您的區段沒有重迭;每個使用者都應該指派給一個區段。 

## <a name="reference"></a>參考

下表列出您可以與資訊障礙搭配使用的屬性。

|Azure Active Directory 屬性名稱 (LDAP 顯示名稱)  |Exchange 屬性名稱  |
|---------|---------|
|合作者       | 合作者        |
|Company     |Company         |
|部門     |部門         |
|ExtensionAttribute1 |CustomAttribute1  |
|ExtensionAttribute2 |CustomAttribute2  |
|ExtensionAttribute3 |CustomAttribute3  |
|ExtensionAttribute4 |CustomAttribute4  |
|ExtensionAttribute5 |CustomAttribute5  |
|ExtensionAttribute6 |CustomAttribute6  |
|ExtensionAttribute7 |CustomAttribute7  |
|ExtensionAttribute8 |CustomAttribute8  |
|ExtensionAttribute9 |CustomAttribute9  |
|ExtensionAttribute10 |CustomAttribute10  |
|ExtensionAttribute11 |CustomAttribute11  |
|ExtensionAttribute12 |CustomAttribute12  |
|ExtensionAttribute13 |CustomAttribute13  |
|ExtensionAttribute14 |CustomAttribute14  |
|ExtensionAttribute15 |CustomAttribute15  |
|MSExchExtensionCustomAttribute1 |ExtensionCustomAttribute1 |
|MSExchExtensionCustomAttribute2 |ExtensionCustomAttribute2 |
|MSExchExtensionCustomAttribute3 |ExtensionCustomAttribute3 |
|MSExchExtensionCustomAttribute4 |ExtensionCustomAttribute4 |
|MSExchExtensionCustomAttribute5 |ExtensionCustomAttribute5 |
|MailNickname |別名 |
|PhysicalDeliveryOfficeName |Office |
|PostalCode |PostalCode |
|ProxyAddresses |EmailAddresses |
|StreetAddress |StreetAddress |
|TargetAddress |ExternalEmailAddress |
|UsageLocation |UsageLocation |
|UserPrincipalName  |UserPrincipalName  |
|郵件   |WindowsEmailAddress    |
|描述    |描述    |
|屬於   |MemberOfGroup  |

## <a name="related-topics"></a>相關主題

[定義 Microsoft 團隊中資訊障礙的原則 (預覽)](information-barriers-policies.md)

[疑難排解資訊障礙 (預覽)](information-barriers-troubleshooting.md)

[資訊障礙 (預覽)](information-barriers.md)



