---
title: 部分位置週期盤點
description: 週期盤點規劃指導實際盤點操作。 您可以要求只計算特定產品和產品變體，而不是一個位置中的所有現有庫存。
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable, WHSRFMenuItemCycleCount, WHSCycleCountPlanListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f06b39f3c2d2f5a0bdfef1da9395c71686ed46968a1143305b5a10787f7e85f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447294"
---
# <a name="partial-location-cycle-counting"></a>部分位置週期盤點

[!include [banner](../includes/banner.md)]

週期盤點規劃指導實際盤點操作。 您可以要求只計算特定產品和產品變體，而不是一個位置中的所有現有庫存。

透過使用週期盤點計劃來建立盤點工作，您可以指導實際的盤點操作。 您可以要求只計算特定產品和產品變體，而不是一個位置中的所有現有庫存。 透過篩選特定產品，倉庫經理可以減少審查費用、避免合併錯誤並節省時間。

## <a name="how-to-configure-partial-location-cycle-counting"></a>如何設定部分位置週期盤點

當您使用倉庫工作流程進行盤點操作時，將為每個位置建立一個工作標題。 定義週期盤點計劃時，您可以使用 **選擇位置** 查詢以限制建立的週期盤點工作。 當您為週期盤點計劃選擇產品時，您可以同時選擇產品和產品變體查詢來進一步限定盤點的內容。

您可以將一個 **工作範本** 與週期盤點計劃產生關聯，來定義應如何建立週期盤點工作。 系統會直接從週期盤點計劃參照用於盤點操作的工作範本。

當定義工作範本詳細資料時，您可以使用 **工作換行符號** 選項以指定要依品項編號或產品變體編號將盤點工作行分組。 如果您只想為某個位置的特定產品盤點現有庫存，則需要此設定。 建立的週期盤點工作行將具有您在此處定義的資訊層級，且將根據此層級處理引導的盤點操作。

如果您使用 **工作斷行符號** 選項，將週期盤點計劃與工作範本產生關聯，則會為建立的週期盤點工作選擇 **部分週期盤點** 欄位，且將根據工作範本的定義建立多個週期盤點工作行。

在設定週期盤點的過程中，您必須先至少為行動裝置功能表項目選擇 **顯示品項編號**，才能處理部分週期盤點工作。 系統將要求倉庫操作員僅記錄與盤點行相關的盤點資訊 (品項編號和產品尺寸)。 此盤點流程將忽略所有其他的現有庫存。

對於部分週期盤點流程，即使盤點指定位置的所有現有品項，也不會更新該位置 **上次週期盤點** 日期/時間。 部分週期盤點不會考慮 **週期盤點計劃** 頁面上的 **週期盤點之間的天數** 參數。 部分週期盤點不支援同時盤點同一位置的多個品項。 當 **流程週期盤點計劃** 正在執行時，部分週期盤點功能可能會導致同一位置被盤點多次。 為避免這種情況發生，請在 **選擇位置** 欄位中指定篩選條件。

> [!NOTE]
> 當您使用部分週期盤點流程時，Warehouse Management 行動應用程式不會提供 **新增 LP 或品項** 按鈕。

## <a name="example"></a>範例

就此範例而言，只有品項編號 A0001 必須計入倉庫 61。

1. 系統會建立一個新的工作範本用於週期盤點。 **工作換行符號** 選項用於按品項編號將盤點工作分組。 因此，建立的週期盤點工作將具有每個品項編號的行項。 您還可以按產品變體編號對行項分組。
1. 系統會建立一個新的週期盤點計劃來參照新建立的工作範本。 週期盤點計劃包括倉庫 61 (**選擇位置** 查詢) 中所有保有品項編號 A0001 庫存的位置。 特定產品的選擇是在 **週期盤點產品選擇** 區段中定義的。
1. 您可以將 **空白位置** 欄位設定為 **排除空白**，為週期盤點計劃選擇產品。 處理週期盤點計劃時，會建立品項編號 A0001 的部分週期盤點工作。 實際的盤點流程可以透過將行動裝置功能表項目用於引導式週期盤點來執行。

## <a name="additional-resources"></a>其他資源

[週期盤點](cycle-counting.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]