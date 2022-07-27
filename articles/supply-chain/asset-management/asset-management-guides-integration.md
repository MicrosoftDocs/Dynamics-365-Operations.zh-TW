---
title: 整合 Dynamics 365 Supply Chain Management (資產管理) 與 Dynamics 365 Guides
description: 本主題介紹如何把 Microsoft Dynamics 365 Supply Chain Management 中的資產管理模組與 Dynamics 365 Guides 整合，在您的日常服務和維護工作流程中利用混合實境指南。
author: johanhoffmann
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 4132992eb5f4b42d43d9ff72cada616fe0573c2f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448095"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a>整合 Dynamics 365 Supply Chain Management (資產管理) 與 Dynamics 365 Guides

[!include [banner](../includes/banner.md)]

您可以把 Microsoft Dynamics 365 Supply Chain Management 中的 **資產管理模組** 與 Dynamics 365 Guides 整合，在日常服務和維護工作流程中利用混合實境指南。 如果指南與「資產管理」工單相關聯，則當工作人員在 Supply Chain Management (Dynamics 365) 行動裝置應用程式中打開工單的維護核取清單時，會看到指南可用。 然後，工作人員可以在 Dynamics 365 Guides HoloLens 應用程式中打開指南。

## <a name="prerequisites"></a>先決條件

您必須完成以下先決條件，才能將指南附加到資產管理工單：

- [設定 Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) 版本 10.0.9 或更高版本。
- [為 Supply Chain Management 應用程式打開雙重寫入](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md)。
- 對 **MRGuidesFeature** 功能，[開啟航班](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features)。 (對於生產環境，您必須先提交支援票證才能把租用戶新增到飛行組。)
- 在 **授權設定** 頁面，[打開以下設定索引鍵](/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference)：

    - 資產管理\>資產管理混合實境
    - 混合實境\>混合實境指南

- [設定 Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) 版本 200.0.0.96 或更高版本。

## <a name="use-dynamics-365-guides-with-asset-management"></a>使用 Dynamics 365 Guides 搭配資產管理

要關聯指南，您可以使用資產管理中的維護清單明細。 透過維護檢查清單範本、維護作業類型或工單來建立關聯，因為這三者都包含維護檢查清單明細。 您可以使用範本來節省時間，因為範本可以與使用它的所有維護作業類型相關聯。 例如，與維護作業類型相關聯的指南，自動與指定該作業類型的所有工單相關聯。 另一方面，與工單直接關聯的指南僅為該工單存在。

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a>將指南與維護檢查清單範本相關聯

若要將指南與維護檢查清單範本相關聯，請執行以下步驟。

1. 使用 Dynamics 365 Guides 電腦和 HoloLens 應用程式來建立指南。 有關如何建立指南的資訊，請參閱以下主題：

    - [使用 PC 應用程式建立指南](/dynamics365/mixed-reality/guides/pc-app-overview)
    - [使用 HoloLens 應用程式來放置全像投影](/dynamics365/mixed-reality/guides/hololens-app-overview)

1. 在 Supply Chain Management 中，[建立維護檢查清單範本](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template)。
1. 將您建立的指南與新維護檢查清單範本中的維護檢查清單明細相關聯：

    1. 在 **維護檢查清單明細** 快速索引標籤，選取要關聯到指南的明細。
    1. 在 **相關指南** 快速索引標籤，選取 **新增指南**。

        ![將指南與維護檢查清單明細相關聯。](media/am-guides-integration-add-guide.png "將指南與維護檢查清單明細相關聯")

    1. 請在 **名稱** 欄位選取指南，然後選取 **儲存**。

        ![在名稱欄位中進行選取。](media/am-guides-integration-select-guide.png "在名稱欄位中進行選取")

1. 將維護檢查清單範本與作業類型相關聯

    1. [建立維護作業類型](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type)，或選取現有的維護作業類型。
    1. 在「動作窗格」上，選取 **維護作業類型預設值**。

        ![維護作業類型預設值按鈕。](media/am-guides-integration-job-defaults.png "維護作業類型預設值按鈕")

    1. 建立明細，然後選取 **儲存**。

        ![建立明細。](media/am-guides-integration-add-line.png "建立明細")

    1. 在「動作窗格」上，請選取 **維護檢查清單**。

        ![維護檢查清單按鈕。](media/am-guides-integration-maintenance-checklist.png "維護檢查清單按鈕")

    1. 在 **維護檢查清單明細** 快速索引標籤，新增明細，然後把 **類型** 欄位的值更改為 **範本**。

        ![變更「類型」值。](media/am-guides-integration-checklist-lines.png "變更「類型」值")

    1. 在 **明細詳情** 快速索引標籤，到 **範本** 欄位，選取與指南關聯的範本，然後選取 **儲存**。

        ![選取範本。](media/am-guides-integration-checklist-line-details.png "選取範本")

1. [建立工單](work-orders/manually-created-workorders.md#create-work-order)，接著選取維護作業類型，並且此類型需使用到與指南關聯的維護檢查清單範本。 該指南會自動與工單關聯。

    ![選取維護作業類型。](media/am-guides-integration-create-work-order.png "選取維護作業類型")

1. 查看與工單和工作人員關聯的指南：

    1. 打開[資產管理行動裝置工作區](asset-management-mobile-workspace.md)，以存取工單。
    1. [打開維護檢查清單](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job)以找出工單。
    1. 選取檢查清單明細以查看相關指南。

        ![與檢查清單明細關聯的指南。](media/am-guides-integration-show-guide.png "與檢查清單明細關聯的指南")

    1. 打開 HoloLens 上的指南。

        ![打開 HoloLens 上的指南。](media/am-guides-integration-hololens-select.png "打開 HoloLens 上的指南")

> [!NOTE]
> 您還可以直接在工單或作業類型的維護檢查清單中關聯指南。

> [!IMPORTANT]
> 存在一個已知問題，當您將維護檢查清單範本與預設維護作業類型相關聯時，連接到該範本的指南不會出現在 **維護作業類型預設值** 頁面的 **相關指南** 快速索引標籤。 但是，在 **相關指南** 快速索引標籤將在該作業類型套用在工單後，指南會出現。

## <a name="see-also"></a>另請參閱

- [雙重寫入概述](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [資產管理概觀](index.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]