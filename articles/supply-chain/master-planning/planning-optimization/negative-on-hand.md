---
title: 現有數量為負的規劃
description: 本主題說明在使用規劃最佳化時如何處理負數現有數量。
author: ChristianRytt
ms.date: 07/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 97688e09aae9706dd85e7965aa08c7ea873a44d81391c39406e2e6367660e0d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447099"
---
# <a name="planning-with-negative-on-hand-quantities"></a>現有數量為負的規劃

[!include [banner](../../includes/banner.md)]

如果系統顯示負數的彙總現有數量，則規劃引擎會將此數量視為 0 (零)，以幫助避免供應過剩。 以下是此功能的運作原理：

1. 規劃最佳化功能會在涵蓋維度的最低層級彙總現有數量。 (例如，如果 *位置* 不是涵蓋維度，則規劃最佳化會在 *倉庫* 層級彙總現有數量。)
1. 如果在涵蓋維度最低層級的彙總現有數量為負數，則系統會假定現有數量確實為 0 (零)。

> [!IMPORTANT]
> 規劃系統只能與輸入資料一樣精確。 如果輸入資料不精確，則負數現有數量記錄將指出 Microsoft Dynamics 365 Supply Chain Management 中的庫存資訊與實際資訊不同步。 因此，規劃結果將是有瑕疵的。 若要取得精確的規劃結果，您應該盡量減少會顯示負數現有數量的記錄數。

## <a name="example-1"></a>範例 1 

倉庫 13 的設定如下所示：

- **涵蓋代碼：** 下限/上限。
- **下限：** 15 件
- **上限：** 25 件

涵蓋維度的最低層級是 *倉庫*，且會在 *位置* 層級記錄下列現有數量：

- **站點 1，倉庫 13，位置 1：** 20 件
- **站點 1，倉庫 13，位置 2：** &minus;8 件。

因此，倉庫 13 的彙總現有數量為 12 件。 (= 20 件 &minus; 8 件)。

在這種情況下，倉庫 13 的規劃引擎會使用 12 件的彙總現有數量 。

結果是 13 件的已規劃訂單 (= 25 件 &minus;12 件)，以將倉庫 13 從 12 件重新填裝為 25 件。

## <a name="example-2"></a>範例 2 

倉庫 13 的設定如下所示：

- **涵蓋代碼：** 下限/上限。
- **下限：** 15 件。
- **上限：** 25 件

涵蓋維度的最低層級是 *倉庫*，且會在 *位置* 層級記錄下列現有數量：

- **站點 1，倉庫 13，位置 1：** 4 件
- **站點 1，倉庫 13，位置 2：** &minus;8 件。

因此，倉庫 13 的彙總現有數量為 &minus;4 件。 (= 4 件 &minus; 8 件)。 換句話說，它小於 0 (零)。

在這種情況下，規劃引擎會假定倉庫 13 的現有數量為 0 件， 而非 &minus;4 件。

結果是 25 件的已規劃訂單 (= 25 件 &minus;0 件)，以將倉庫 13 從 0 件重新填裝為 25 件。

## <a name="planning-when-there-is-a-reservation-against-negative-on-hand-inventory"></a>當保留負數現有庫存時進行規劃

如果您在實際保留存在的情況下調整庫存，您會造成實際保留負數庫存訂單的狀況。 在這種情況下，由於實際保留存在，因此規劃最佳化會假定現有庫存支援它，即使現有庫存的收貨尚未在系統中登記。 因此它假定不需要補貨，而且不會建立已規劃訂單來補充訂單的數量。

以下範例說明這種情況。

### <a name="example"></a>範例 

系統設定如下：

- 產品 *FG* 存在並且有 *10* 件 的現有庫存。
- 產品設定允許實際負數庫存。
- 數量為 *10* 件且 產品為 *FG* 的銷售訂單存在。
- 銷售訂單數量是針對現有的現有庫存實際保留的。

接著您會調整產品 *FG* 的數量，使現有庫存變為 0 (零)。 由於現有產品庫存為零，因此現在會為負數庫存保留銷售訂單數量。 但是，如果您現在執行總規劃，則不會建立已規劃訂單以供應銷售訂單，因為規劃最佳化將假定所需的現有庫存已存在，以供應實際保留。

## <a name="related-resources"></a>相關資源

- [規劃最佳化概觀](planning-optimization-overview.md)
- [開始使用規劃最佳化](get-started.md)
- [規劃最佳化適合度分析](planning-optimization-fit-analysis.md)
- [檢視計劃歷程與規劃日誌](plan-history-logs.md)
- [取消規劃作業](cancel-planning-job.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
