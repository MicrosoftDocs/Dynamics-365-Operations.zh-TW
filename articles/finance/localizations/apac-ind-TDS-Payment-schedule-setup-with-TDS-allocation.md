---
title: 設定包含 TDS 分配的付款排程
description: 本主題說明如何設定包含從源頭扣除稅款 (TDS) 分配的付款排程。
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
ms.openlocfilehash: 31ecf2e6fa4d3d37c3d5332dc1d5592bf1a99bad
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451818"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a>設定包含 TDS 分配的付款排程

[!include [banner](../includes/banner.md)]

本主題說明如何設定包含從源頭扣除稅款 (TDS) 分配的付款排程。

1. 前往 **應付帳款 \> 付款設定 \> 付款排程**。

    [![付款排程頁面。](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)

2. 在動作窗格上，選擇 **新增** 以建立付款排程，並輸入所需的詳細資料。
3. 在 **分配** 欄位中，選擇用於為付款排程分配付款的方法：

    - 總計
    - 固定金額
    - 固定數量
    - 指定

    **扣繳稅款分配** 欄位顯示付款計劃的 TDS 分配方法。 如果在 **分配** 欄位中選擇 **總計**，則 **扣繳稅款分配** 欄位將自動設為 **總計**。 如果在 **分配** 欄位中選擇 **固定金額**、**固定數量** 或 **指定**，則 **扣繳稅款分配** 欄位將自動設為 **按比例**。

    > [!NOTE]
    > 如果 **扣繳稅款分配** 欄位設為 **總計**，則將根據包括 TDS 金額的總額計算分期付款。 如果 **扣繳稅款分配** 欄位設為 **按比例**，則將根據扣除 TDS 金額的淨發票金額計算分期付款。

4. 輸入其他必要的詳細資料，然後關閉頁面。
