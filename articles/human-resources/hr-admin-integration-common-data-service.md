---
title: 配置 Dataverse 整合
description: 本主題說明 Microsoft Dataverse和 Dynamics 365 Human Resources 之間的整合。
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c4e68142045b72b139bdda8be707a73e21e568fd
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452133"
---
# <a name="configure-dataverse-integration"></a>配置 Dataverse 整合


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

您可以打開或關閉 Microsoft Dataverse 和 Dynamics 365 Human Resources 之間的整合功能。 您也可以檢視同步化細節、清理追蹤資料和重新同步化資料表，以便有助於排除兩個環境之間的資料問題障礙。

> [!NOTE]
> 更多有關 Dataverse (前身為 Common Data Service) 和術語更新的資訊，請參閱[何謂 Microsoft Dataverse？](/powerapps/maker/data-platform/data-platform-intro)

當您關閉整合功能時，用戶可以在 Human Resources 或 Dataverse 變更，但這些更改不會在兩個環境之間同步。

預設情況下會關閉人力資源和 Dataverse 之間的整合功能。

此時您可能希望關閉整合功能：

- 您正在透過 Data Management Framework 填寫資料，並且必須多次匯入資料才能達到正確狀態。

- 人力資源或 Dataverse 中的資料有問題。 如果您關閉整合功能，您可以在不必刪除另一個的情況下刪除一個環境的記錄。 當您回頭重新打開整合功能時，環境裡未刪除的記錄會同步到它被刪除的環境。 下次當 **Dataverse 整合錯過同步要求** 批次處理工作執行時會開始同步。

> [!WARNING]
> 當您關閉資料整合功能時，請確定您沒有在兩個環境編輯相同記錄。 當您回頭重新打開整合功能時，您上次編輯的記錄將會進行同步。 因此，如果您沒有在兩個環境對記錄進行相同變更，會發生資料遺失情況。

## <a name="access-the-dataverse-integration-page"></a>存取 Dataverse 整合頁

1. 在您希望檢視或配置與 Dataverse 的整合設定時，請選取 **系統管理** 圖格。

    [![系統管理圖格。](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. 請選取 **連結** 索引標籤。

    [![連結索引標籤。](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. 請在 **整合** 下方選取 **Dataverse 組態**。

    [![Dataverse 組態連結。](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a>打開或關閉人力資源和 Dataverse 之間的資料整合功能

- 若要打開整合功能，請在 **Microsoft Dataverse 整合** 頁上設定 **啟用 Dataverse 整合** 選項到 **是**。

    > [!NOTE]
    > 當您打開整合功能時，資料將在下次 **Dataverse 整合錯過同步要求** 批次處理工作執行時同步。 所有資料應該在完成批次處理工作後皆可使用。

- 若要關閉整合功能，請將選項設定為 **否**。

[![打開或關閉 Dataverse 整合功能。](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)

> [!WARNING]
> 我們強烈建議在執行資料移轉任務時關閉 Dataverse 整合功能。 大量資料上傳會大幅影響效能。 例如，啟用整合功能時上傳 2000 位工作人員會耗費數小時，而停用時則耗費不到一小時。 本範例提供的數字僅供示範目的。 匯入記錄所需的確切時間會因許多因素而有很大差異。

## <a name="view-data-integration-details"></a>檢視資料整合細節

您會在 **Microsoft Dataverse 整合** 頁的 **管理** FastTab 上看到人力資源和 Dataverse 之間的行項如何連結在一起。

- 若要檢視資料表的行項資料，請在 **Dataverse 資料表** 欄位選取資料表。 網格顯示連結到選取資料表的所有行項。

> [!NOTE]
> 目前尚未列出全部的 Dataverse 資料表。 只有支援使用自訂欄位的資料表才會出現在網格。 新資料表可透過持續的 Human Resources 版本使用。

網格包括的欄位如下：

- **Dataverse 資料表** – Dataverse 資料表名稱。
- **Dataverse 資料表參考** – Dataverse 用來辨別記錄的識別碼。 此數值相當於人力資源 **Recld** 值。 您可以在打開 Microsoft Excel 中的 Dataverse 資料表時找到識別碼。
- **人力資源實體名稱** – 上次同步資料到 Dataverse 的人力資源實體。 此實體會有 Dataverse 前綴詞或其他前綴詞。
- **人力資源參考** - 與人力資源記錄相關聯的 **Recld** 值。
- **從 Dataverse 刪除** – 指出是否已從 Dataverse 刪除的值。

> [!NOTE]
> 人力資源的記錄對應到 Dataverse 的行項。

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a>從 Dataverse 行移除與人力資源記錄的關

如果您在同步人力資源和 Dataverse 之間的資料期間經歷問題，您可以藉由清除追蹤並讓追蹤資料表重新同步的方式解決這些問題。 如果刪除關聯，接著變更或刪除 Dataverse 中的行項，變更不會同步到人力資源。 如果您在 Human Resources 變更，會建立新追蹤記錄，而行項會在 Dataverse 更新。

- 若要移除人力資源記錄和 Dataverse 行項的關聯，請選取 **Dataverse 資料表** 欄位裡的資料表，然後選取 **清除追蹤資訊**。

[![清除追蹤資訊。](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)

若要在清除追蹤後進行資料表完整同步動作，請參閱下一道程序。

## <a name="sync-a-table-between-human-resources-and-dataverse"></a>同步 Human Resources 和 Dataverse 之間的資料表

下列情況請使用這道程序：

- Dataverse 的變更出現在人力資源的時間太長。

- 您必須在清除追蹤後重新整理追蹤資料表。

若要在 Human Resources 和 Dataverse 之間的表資料上執行完整同步：

1. 請選取 **Dataverse 資料表** 欄位的資料表。

2. 請選取 **立即同步**。

[![執行完整同步。](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)

## <a name="see-also"></a>也請參閱

[Dataverse資料表](hr-developer-entities.md)<br>
[配置 Dataverse 虛擬資料表](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[人力資源虛擬資料表常見問答集](hr-admin-virtual-entity-faq.md)<br>
[何謂 Microsoft Dataverse？](/powerapps/maker/data-platform/data-platform-intro)<br>
[術語更新](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
