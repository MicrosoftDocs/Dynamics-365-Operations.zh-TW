---
title: 安裝、設定和更新客戶入口網站
description: 本主題提供客戶入口網站的授權詳細資料和設定說明。
author: Henrikan
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 187efe1372bf2400241f3d65751189247c001447
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449799"
---
# <a name="install-set-up-and-update-the-customer-portal"></a>安裝、設定和更新客戶入口網站

[!include [banner](../includes/banner.md)]


## <a name="licensing-requirements"></a>授權要求

如欲實作客戶入口網站，您必須擁有以下授權：

- **Power Apps 入口網站** – 為客戶入口網站提供主機服務需要此授權。 入口網站根據使用方式獲得授權。 詳細資訊請參閱 [Power Apps 入口網站授權](/power-platform/admin/powerapps-flow-licensing-faq#portals)。
- **雙重寫入** – 您必須擁有必要授權才能為 Supply Chain Management 資料表啟用雙重寫入。 詳細資訊請參閱[雙重寫入系統要求](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md)。

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a>雙重寫入及 Power Apps 入口網站的相依性

客戶入口網站仰賴 Power Apps 入口網站和雙重寫入，如下圖所示。

![客戶入口網站相依性。](media/customer-portal-elements.png "客戶入口網站相依性")

與 Supply Chain Management 的其他功能不同，客戶入口網站範本位於 Power Apps 入口網站。 因此，客戶入口網站僅限於 Power Apps 入口網站和雙重寫入資料表提供的功能。

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a>啟用客戶入口網站所需的設定

確保您擁有所需的授權後，您可以設定雙重寫入，如[雙重寫入初始同步說明](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-entity-map.md)所述。

請務必在雙重寫入中啟用以下資料表對應：

- 銷售訂單標題
- 銷售訂單詳細資料
- 帳戶
- 連絡人
- 產品

完成此設定後，您可以佈建客戶入口網站範本。

## <a name="provision-the-customer-portal"></a>佈建客戶入口網站

在開始之前，請確保您已經完成了[所需設定](#required-setup)。 然後按照以下步驟佈建客戶入口網站。

1. 前往 [make.powerapps.com](https://make.powerapps.com/)。
2. 確保您使用啟用了雙重寫入的環境。
3. 在 **建立** 索引標籤，向下捲動到 **從範本開始** 區段，然後選擇名為 **客戶入口網站** 的範本。
4. 按照螢幕上的說明進行操作。

佈建完成後，您就可以在 **首頁** 頁面的 **您的應用程式** 區段存取客戶入口網站。

> [!NOTE]
> 如果您正在使用的環境中未安裝雙重寫入解決方案，您將收到一條錯誤訊息，並且不會佈建客戶入口網站。

## <a name="update-the-customer-portal"></a>更新客戶入口網站

以後可能會向客戶入口網站新增更多功能。 Microsoft 對基礎解決方案元件所做的任何更改都將自動出現在您的環境中。 但是，在您的環境中佈建的網站不會自動反映對設定資料所做的變更。 您必須從新範本獲取程式碼並將其與佈建的網站合併，以手動套用這些變更。

## <a name="additional-resources"></a>其他資源

如欲瞭解如何設定和自訂客戶入口網站，您應該首先查看以下基礎技術文件：

- [Power Apps 入口網站文件](/powerapps/maker/portals/overview)
- [雙重寫入文件](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

要有效管理入口網站，您必須瞭解 Power Apps 入口網站和 Microsoft Dataverse 生命週期。 詳細資訊請參閱下列資源：

- [關於入口網站生命週期](/powerapps/maker/portals/admin/portal-lifecycle)
- [升級入口網站](/powerapps/maker/portals/admin/upgrade-portal)
- [遷移入口網站設定](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [解決方案生命週期管理：Dynamics 365 for Customer Engagement 應用程式](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]