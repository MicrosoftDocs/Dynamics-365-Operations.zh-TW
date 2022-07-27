---
title: 將 BOM 和配方明細發佈到倉庫
description: 本主題介紹將 BOM 和配方明細的原物料發佈到倉庫的流程。
author: johanhoffmann
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm, ProdParmReleaseToWarehouse, WHSReleaseToWarehouseProdBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: c9956290ce8f90f04bc144d710ad35b5a0243e3898a8f3e75692b1a9da506149
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446793"
---
# <a name="release-bom-and-formula-lines-to-the-warehouse"></a>將 BOM 和配方明細發佈到倉庫

[!include [banner](../includes/banner.md)]

本主題介紹將物料清單 (BOM) 明細和配方明細的原物料發佈到倉庫的流程。 在您將 BOM 或配方明細發佈到倉庫時，系統首先會確定將用於生產流程的物料之所在工廠生產輸入位置上是否已經提供該物料。

- 如果生產輸入位置提供該物料，則在發出將該物料發佈到倉庫的信號後立即從該位置領取該物料。
- 如果在生產輸入位置不提供該物料，則物料發佈指示必須將該物料從倉庫中的位置移動到生產輸入位置。 透過倉庫工作移動物料以進行原物料揀選。 因此，必須設定原物料揀選的倉庫流程。 如需詳細資訊，請參閱[補貨概覽](../warehousing/replenishment.md)和[使用工作範本和位置指令控制倉庫工作](../warehousing/control-warehouse-location-directives.md)。

## <a name="methods-for-releasing-bom-and-formula-lines"></a>發佈 BOM 和配方明細的方法

您可以設定 BOM 和配方明細的發佈，以便在發佈生產訂單或批次訂單時發生。 或者，可以透過批次工作控制發佈或手動調整完成發佈。

用於發佈 BOM 和配方明細的方法由 **生產明細發佈** 參數控制。 您可以在 **生產控制** \> **設定** \> **生產參數** 找到此參數。

- **作為生產或批次訂單發佈的一部分發佈 BOM 和配方明細** – 在該方法中，用於生產或批次訂單的 BOM 和配方明細作為發佈訂單流程的一部分進行發佈。 通常在發佈生產或批次訂單期間，生產作業發佈給工廠工作人員，並列印生產文件。 在這個流程中，訂單的狀態也更改為 **已發佈**。
- **透過批次工作或手動調整發佈 BOM 和配方明細** – 在這種方法中，BOM 和配方明細只能透過 **自動發佈 BOM 和配方明細** 批次工作或手動調整。 若要手動發佈 BOM 和配方明細，在生產訂單清單頁面或生產訂單詳細資料頁面的動作窗格中，選擇 **發佈到倉庫**。

有關如何使用批次工作將 BOM 和配方明細發佈到生產的快速示範，請觀看以下 YouTube 短片：[批量發佈生產揀貨到倉庫](https://www.youtube.com/watch?v=8urAJn50dQ8)。

## <a name="releasing-the-bom-and-formula-lines-by-using-a-batch-job"></a>使用批次工作發佈 BOM 和配方明細

**自動發佈 BOM 和配方明細** 批次工作檢查包含要發佈剩餘數量的選定 BOM 和配方明細。 該工作僅考慮狀態為 **已發佈**、**已開始** 或 **已報告為完成** 的訂單。 如果 BOM 和配方明細包含要發佈的剩餘數量，該工作最多發佈已經實際預留的數量和實際可用的數量能夠涵蓋的數量。

### <a name="example-of-a-batch-job-release"></a>批次作業發佈範例

| 案例 | 要發佈的剩餘數量 | 實際預留的數量 | 實際可用數量 | 批次作業發佈的數量 |
|----------|-------------------------------|------------------------------|-------------------------------|------------------------------------|
| 1        | 100                           | 20                           | 90                            | 100                                |
| 2        | 100                           | 20                           | 70                            | 90                                 |
| 3        | 100                           | 0                            | 90                            | 90                                 |
| 4        | 100                           | 0                            | 110                           | 100                                |
| 5        | 100                           | 20                           | 0                             | 20                                 |

### <a name="batch-job-setup"></a>批次工作設定

在 **自動發佈 BOM 和配方明細** 批次工作的查詢中，可以設定篩選條件以指定工作應提前多少天查找具有未發佈數量的明細。 在工作查詢的 **原物料日期** 欄位，使用 **(LessThanDate())** 函數作為篩選條件。

下圖顯示包含兩個工作 (10 和 20) 的生產訂單，這兩個工作負責生產訂單的組裝和包裝。 設定每個工作以消耗一定數量的物料。 在此圖中，時間軸下方的綠色箭頭指示的發佈時界等於在 **(LessThanDate())** 條件中指定的天數。 例如，**(LessThanDate(2))** 表示工作應僅查找兩天時界內的未發佈數量。

![具有兩個批次工作的生產訂單範例。](media/bach-job-setup.PNG)

## <a name="releasing-material-per-operation-number-or-in-proportion-to-the-amount-of-finished-goods"></a>按照作業編號或按照成品數量的比例發佈物料

如果使用 **生產訂單發佈時** 參數設定發佈物料，進行手動發佈時，有兩個選項可用於控制物料發佈：

- 按照作業編號發佈物料。
- 按成品數量的比例發佈物料。

### <a name="release-material-per-operation-number"></a>按照作業編號發佈物料

若要控制應發佈物料的作業，則使用 **發佈到倉庫** 頁面。

- 選擇 **生產控制** \> **生產訂單** \> **所有生產訂單**，選擇一個生產訂單，然後在 **倉庫** 索引標籤選擇 **發佈到倉庫**。 然後使用 **起始作業編號** 和 **截止作業編號** 欄位以指定作業編號的範圍。

下圖顯示含有兩個作業 (10 和 20) 的生產訂單。 在本範例中，您可以限制發佈到作業 10，僅發佈物料 M9203。

![每個作業編號的物料發佈範例。](media/two-operations.PNG)

有關如何按照成品數量的比例發佈物料之快速示範，請觀看以下 YouTube 短片：關於[生產訂單發佈流程的改進](https://www.youtube.com/watch?v=Rm3ojAz6Zu0)。

### <a name="release-material-in-proportion-to-the-amount-of-finished-goods"></a>按成品數量的比例發佈物料

您可以為部分成品數量或以特定的單位發佈原物料。

- 若要為部分成品數量發佈原物料，則選擇 **生產控制** \> **生產訂單** \> **所有生產訂單**，選擇一個生產訂單，然後在 **倉庫** 索引標籤選擇 **發佈到倉庫**。 然後在 **數量** 欄位中輸入數量。

    例如，為 1,000 件 (pcs.) 物料建立和安排生產訂單。 工廠主管計劃下一個班次生產 100 件， 並且希望僅發佈該班次的物料。 在這種情況下，主管可以使用 **數量** 欄位為下一個班次 計劃 100 件發佈物料。

- 若要以特定單位發佈原物料，則選擇 **生產控制** \> **生產訂單** \> **所有生產訂單**，選擇一個生產訂單，然後在 **倉庫** 索引標籤選擇 **發佈到倉庫**。 然後使用 **單位** 欄位選擇發佈物料的成品單位。

    可用單位在成品的單位序列群組識別碼中定義。

    例如，成品在單位磅 (lbs.) 和棧板 (PL) 之間進行以下轉換：1 PL = 100 lbs。 若要為 10,000 lbs 成品建立一個生產訂單， 可以為計劃要生產的棧板數量發佈原物料。 選擇 **PL** 為單位，然後在 **數量** 欄位選擇一個相應的數字。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]