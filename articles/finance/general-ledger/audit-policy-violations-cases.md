---
title: 稽核原則違規記錄和案例
description: 本文說明如何從稽核原則規則違規產生稽核案例。 它還包括有關稽核原則使用文件選擇日期範圍的各種方式的資訊。
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 057cb8afe0da5e0810a2d1c87f7cdbe73bc88b9819ca81631d889bfa1cc55e6c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450609"
---
# <a name="audit-policy-violations-and-cases"></a>稽核原則違規記錄和案例

[!include [banner](../includes/banner.md)]

本文說明如何從稽核原則規則違規產生稽核案例。 它還包括有關稽核原則使用文件選擇日期範圍的各種方式的資訊。

## <a name="how-audit-cases-are-generated"></a>稽核案例是如何產生的

稽核原則用於識別不符合您定義和設定為稽核原則規則的業務規則的費用報表、採購訂單和廠商發票。 

稽核原則以批次模式執行。 執行稽核原則時，屬於該原則的所有原則規則都會同時執行。

每個原則規則評估一組文件。 原則規則會選擇文件選擇日期範圍內且符合指定條件的文件。 例如，一項原則規則可能會選擇餐費超過 50.00 的費用報表。 其他原則規則可能會選擇應付給特定廠商的廠商發票。 系統會針對在一組文件中選擇的各個文檔產生違規記錄。 該違規行為是特定文件 (例如發票 12345) 不符合原則規則的記錄。 

多個稽核違規記錄組合在一起並與稽核案例相關聯。 根據預設，每個稽核原則的案例都按稽核原則規則分組。 如果需要，可以使用 **案例分組條件** 頁面選擇其他分組條件。。 例如，您可以按項目識別碼對費用標題進行分組，並按廠商帳戶對廠商發票進行分組。 在這種情況下，具有相同項目識別碼的所有費用標題違規將分組在同一個案例中，具有相同廠商帳戶的所有廠商發票將分組在同一案例中。 

> [!NOTE]
> 對於根據 **重複** 查詢類型的稽核原則規則，違規記錄不由原則規則或在 **案例分組條件** 頁面指定的條件分組。 相反，它們按稽核原則規則中內建的條件進行分組。 例如，如果原則規則評估相同金額、商戶識別碼和日期的重複費用的費用報表，則在這些欄位中具有相同值的所有費用都將是一種案例。 任何具有不同價值的費用將是單獨的案例。

稽核案例產生後，會使用案例管理的典型流程進行處理。

## <a name="document-selection-date-ranges"></a>文件選取日期範圍
執行稽核原則時，每個原則規則都會選擇日期在文件選擇日期範圍內的指定類型的文件。 在 **其他選項** 頁面指定文件選擇日期範圍。 許多文件有多個與其相關的日期。 在 **原則規則類型** 頁上指定稽核原則規則使用的日期欄位。

以下是稽核原則使用文件選擇日期範圍的其他方式：

-   該原則使用在文件選擇日期範圍的最後一天有效的每個原則規則的版本。 您可以在 **稽核原則** 清單頁面查看每個原則規則的生效日期。
-   該原則使用在文件選擇日期範圍的最後一天與該原則關聯的組織節點。 只有目前與原則關聯的組織節點顯示在 **稽核原則** 清單頁面。
-   對於根據 **清單搜尋** 查詢類型的原則規則，原則會評估在文件選擇日期範圍的最後一天有效的受監視實體的文件。


有關詳細資訊，請參閱[稽核原則規則](audit-policy-rules.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]