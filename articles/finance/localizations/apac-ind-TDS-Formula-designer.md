---
title: TDS 計算的公式設計工具
description: 本主題提供了一個範例，說明如何根據為附加到交易記錄的 TDS 群組中的每個 TDS 稅碼定義的公式計算從源頭扣除稅款 (TDS)。
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 3d8e098243688ebf6977db97130592443e269973
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451824"
---
# <a name="formula-designer-for-tds-calculations"></a>TDS 計算的公式設計工具

[!include [banner](../includes/banner.md)]

本主題提供了一個範例，說明如何根據為每個 TDS 稅碼定義的公式計算從源頭扣除稅款 (TDS)。 TDS 稅碼在附加到交易記錄的 TDS 群組中定義。 在設計 TDS 公式之前，請完成 TDS 所需的基本設定，如以下步驟所示。 

- 使用 **扣繳稅款構件群組** 頁面設定 TDS 構件群組。 
- 使用 **扣繳稅款構件** 頁面設定 TDS 構件群組，並將 TDS 構件群組附加到 TDS 構件群組。 
- 使用 **扣繳稅款代碼** 頁面設定 TDS 稅碼，並將 TDS 構件附加到 TDS 稅碼。 
- 使用 **扣繳稅款群組** 頁面設定 TDS 稅組。 然後使用 **公式設計工具** 頁面將 TDS 稅碼附加到稅組，並定義公式。 

**範例公式**

在此範例中，TDS 群組「租金」將附加到為廠商 A 建立的採購發票。發票金額為 $100,000。 請參閱下表以查看發票的 TDS 計算。

| TDS 群組                                                   | 已附加到 TDS 群組的 TDS 稅碼 | 值              | 應稅基數 (公式設計工具) | 計算運算式 (公式設計工具) | 基準金額 | 計算的 TDS 金額 |
| ------------------------------------------------------------ | --------------------------------------- | ------------------ | --------------------------------- | :----------------------------------------: | ----------- | --------------------- |
| 租金                                                         | TDS (TDS 構件-TDS)                | 10%                | 總金額                      |                                            | 100,000      | 10,000                 |
| 附加費 (TDS 構件-附加費)                         | 10%                                     | 不含總金額 | +TDS                              |                   10000                    | 1,000        |                       |
| PE-Cess (TDS 構件-PE-Cess)                            | 2%                                      | 不含總金額 | +TDS+ 附加費                    |                   11000                    | 220         |                       |
| SHE Cess (TDS 構件-SHE Cess)                          | 1%                                      | 不含總金額 | +TDS+ 附加費                    |                   11000                    | 110         |                       |
| **針對****發票****計算****的****總** **TDS** | **11,330**                               |                    |                                   |                                            |             |                       |

建立憑證項目，如下所示。

| 客戶           | 借方  | 貸方 |
| ----------------- | ------ | ------ |
| 租金              | 100,000 |        |
| 廠商 A          |        | 100,000 |
| 廠商 A          | 11,330  |        |
| 應付 TDS       |        | 10,000  |
| 應付附加費 |        | 1,000   |
| 應付 PE-Cess   |        | 220    |
| 應付 SHE Cess  |        | 110    |
