---
title: 建立和管理客戶入口網站使用者 (包含影片)
description: 本主題說明如何建立客戶入口網站使用者帳戶並為其設定權限。
author: Henrikan
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 4615182e6c3341a376e8e55a1417480e3e3f5ea7
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449841"
---
# <a name="create-and-manage-customer-portal-users"></a>建立和管理客戶入口網站使用者

[!include [banner](../includes/banner.md)]


在立即可用的實作中，使用者無法自行註冊使用客戶入口網站建立的網站。 如欲登入和使用網站，使用者必須由管理員邀請。Microsoft 刻意阻止使用者自行註冊。

在使用者可以使用網站之前，必須為該使用者建立聯絡人記錄。 此記錄表示使用者屬於哪個客戶帳戶和法律實體。 此資訊對於確保使用者可以建立和檢視銷售訂單至關重要。

使用者自行註冊時，會自動為他們建立聯絡人記錄。 因此，您無法確保使用者選擇正確的客戶帳戶和法律實體。 另一方面，邀請流程允許管理員在發送邀請之前，將正確的客戶帳戶和法律實體指派至聯絡人記錄。 如果您正在考慮自訂解決方案以便使用者可以自行註冊，請務必考慮可能的後果。

## <a name="video"></a>影片
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ADkI]

[邀請客戶註冊及使用您的客戶入口網站](https://youtu.be/drGUYHX9QIQ)影片 (如上所示) 包含在[財務和營運播放清單](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW)之中，可在 YouTube 觀看。

## <a name="prerequisite-setup"></a>先決條件設定

Power Apps 入口網站聯絡人作為記錄儲存在 Microsoft Dataverse 的 **聯絡人** 資料表中。 然後雙重寫入會依據需求將這些記錄同步到 Microsoft Dynamics 365 Supply Chain Management。

![客戶入口網站聯絡人系統圖示。](media/customer-portal-contacts.png "客戶入口網站聯絡人系統圖示")

在開始邀請新客戶之前，請確保您已啟用雙重寫入之中的 **聯絡人** 資料表對應。

## <a name="the-invitation-process"></a>邀請流程

如欲邀請現有聯絡人到客戶入口網站，請按照 Power Apps 入口網站文件的[邀請聯絡人造訪入口網站](/powerapps/maker/portals/configure/invite-contacts)步驟辦理。

在您邀請客戶加入客戶入口網站之前，請確保客戶的[聯絡人記錄](/powerapps/maker/portals/configure/configure-contacts)可用並按以下方式設定：

1. 設定 **公司** 欄位至您希望客戶在 Supply Chain Management 中所屬的法律實體。
2. 設定 **帳戶號碼** 欄位至您希望使用者在 Supply Chain Management 中擁有的客戶帳戶號碼。

建立聯絡人後，您應該能夠在 Supply Chain Management 中看到它。

詳細資訊請參閱 Power Apps 入口網站文件的[設定聯絡人以在入口網站上使用](/powerapps/maker/portals/configure/configure-contacts)。

## <a name="out-of-box-web-roles-and-table-permissions"></a>立即可用的 Web 角色和資料表權限

Power Apps 入口網站的使用者角色是由 [Web 角色](/powerapps/maker/portals/configure/create-web-roles)和[資料表權限](/powerapps/maker/portals/configure/assign-entity-permissions)定義。 客戶入口網站定義了一些立即可用的角色。 您可以建立新角色，也可以修改或移除現有角色。

### <a name="out-of-box-web-roles"></a>立即可用的 Web 角色

本節介紹隨客戶入口網站提供的 Web 角色。

有關如何修改立即可用使用者角色的詳細資訊，請參閱 Power Apps 入口網站文件的[為入口網站建立 Web 角色](/powerapps/maker/portals/configure/create-web-roles)和[使用入口網站的資料表權限新增基於記錄的安全性](/powerapps/maker/portals/configure/assign-entity-permissions)。

#### <a name="administrator"></a>管理員

管理員監督和維護網站。 此人將佈建和設定客戶入口網站。 管理員維護入口網站的 IT 和安全層面，並確保一切順利運行。 管理員還可以透過新增新功能、建立新角色和其他方式以自訂和/或更改入口網站。

#### <a name="customer-representative"></a>客戶代表

客戶代表為客戶公司工作，負責管理公司下單的訂單。 客戶代表可以查看為公司下單的所有訂單以及下單的使用者。 此外，客戶代表可以查看有關整個帳戶的資訊，以及哪些聯絡人可以代表該帳戶下訂單。

#### <a name="authorized-users"></a>授權使用者

授權使用者可以下訂單並查看已下單訂單的狀態。 但是，他們無法查看公司中其他使用者所下單的訂單狀態。

#### <a name="unauthorized-users"></a>未授權使用者

未授權使用者無法查看任何資料。 他們只能查看公開資訊，例如條款及條件，以及有關執行客戶入口網站的公司詳細資訊。

#### <a name="example"></a>範例

下表顯示了每個 Web 角色中的使用者可以在系統中看到的銷售訂單。

| 銷售訂單 | 管理員 | 客戶&nbsp;X 的客戶代表 | 授權使用者：Jane | 授權使用者：Sam | 未授權使用者：May |
|---|---|---|---|---|---|
| 客戶&nbsp;X 訂購者：&nbsp;Jane | 是 | 是 | 是 | 否 | 否 |
| 客戶&nbsp;X 訂購者：&nbsp;Sam | 是 | 是 | 否 | 是 | 否 |
| 客戶&nbsp;Y 訂購者：&nbsp;May | 是 | 否 | 否 | 否 | 否 |

> [!NOTE]
> 儘管 Sam 和 Jane 都是為客戶 X 工作的聯絡人，但他們只能看到自己下的訂單，而看不到其他任何東西。 儘管 May 在系統中有訂單，但她無法在客戶入口網站中看到該訂單，因為她是未授權使用者。 (此外，她一定是透過客戶入口網站以外的某個通路下訂單的。)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]