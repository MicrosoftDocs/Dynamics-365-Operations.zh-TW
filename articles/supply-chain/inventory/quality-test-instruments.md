---
title: 品質管理測試群組儀器
description: 本主題介紹如何建立測試儀器，以便在 Microsoft Dynamics 365 Supply Chain Management 中在品質檢驗訂單上進行測試。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d80a4f784a43e0d83d1f5b42f6740ef6da3add1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447867"
---
# <a name="quality-management-test-instruments"></a>品質管理測試群組儀器

[!include [banner](../includes/banner.md)]

本主題介紹如何建立測試儀器，以便在 Microsoft Dynamics 365 Supply Chain Management 中在品質檢驗訂單上進行測試。

您使用 **測試儀器** 頁面來定義和查看有關用於對品質檢驗訂單執行測試的裝置詳細資料。 測試儀器是選用項目。 但是，它們可以幫助品質工作人員瞭解應該使用哪種裝置或工具來執行特定測試。

## <a name="test-instrument-example"></a>測試儀器示例

您正在對電子元件進行各種測試。 有些測試是針對元件的電壓輸出，一項測試針對元件溫度，另一項測試是針對其重量。 各項測試會使用不同的工具、裝置或設備。 例如，電壓表用於測量電壓，溫度計用於測量溫度，磅秤則用於測量重量。 您可以將這些設備中的每一個配置為測試儀器，並指示應記錄測試結果的測量單位。 例如，電壓表的結果以伏特記錄，溫度計的結果以華氏度或攝氏度記錄，磅秤的結果以磅或公斤記錄。

## <a name="create-a-test-instrument"></a>建立測試儀器

1. 移至 **庫存管理 \> 設定 \> 品質控制 \> 測試儀器**。
1. 在動作窗格上選取 **新增**，將資料列新增至格線。 接著，在新的一列上，設定以下欄位：

    - **測試儀器**– 輸入測試儀器的不重複識別碼或名稱。
    - **說明** – 輸入測試儀器的詳細說明。
    - **單位** – 選擇儀器測量結果的單位。 **精確度** 欄位會根據您選擇的單位自動設定。

1. 關閉頁面。

## <a name="additional-resources"></a>其他資源

- [品質管理測試](quality-tests.md)
- [品質管理測試群組](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
