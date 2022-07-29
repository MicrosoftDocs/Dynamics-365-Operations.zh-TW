---
title: 可用的預算資金
description: 本主題介紹可用的預算資金功能並提供資訊以幫助您設定預算控制以最佳化組織財務資源的管理。
author: rcarlson
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "60493"
- intro-internal
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2021-11-28
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: a8279ae9b08c7537548c1c8b71e6e978fee2b8a1
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451278"
---
# <a name="budget-funds-available"></a>可用的預算資金

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

本主題介紹可用的預算資金功能並提供資訊以幫助您設定預算控制以最佳化組織財務資源的管理。

## <a name="enhanced-calculation-feature-for-budget-funds-available"></a>增強的可用預算資金計算功能

**僅追蹤可用預算資金計算中的金額** 功能可讓您根據 **定義預算控制參數** 頁面上的設定追蹤基礎預算控制表的文件類型和狀態。

某些預算控制設定選項必須具有特定設定才能使該功能正常運作。 在 **定義預算控制參數** 頁面的 **可用預算資金** 索引標籤上選擇或清除這些選項。 下表顯示了可用預算資金功能所需的設定。

| 如果選擇此選項 | 也必須選擇此選項 |
| ------------------------- | -------------------------------- |
| 預留保留數的預算預留 | 保留款 *和* 實際支出的預算預留 |
| 保留款的預算預留 | 實際支出 |
| 具有採購申請類型文件的保留款的預算預留 | 預留保留數的預算預留 |

此功能僅影響新文件。 現有文件的金額將繼續追蹤並顯示在預算控制統計資訊查詢中，直到可用預算資金設定變更並啟用新的預算控制設定。 屆時，將從可用預算資金計算中刪除的文件的預算追蹤資料將被刪除。

建議您保持清除 **未過帳的實際支出** 選項。 如果選擇它，則會對未過帳的文件 (例如待處理的廠商發票) 進行耗時的預算控制計算。
