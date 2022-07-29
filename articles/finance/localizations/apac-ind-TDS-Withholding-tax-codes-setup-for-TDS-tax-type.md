---
title: 設定 TDS 稅務類型的扣繳稅款代碼
description: 本主題說明如何設定從源頭扣除稅款 (TDS) 的稅碼。
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
ms.openlocfilehash: 03d8b7d4992fbb49a873f14e1ce1f0c816cef202
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451770"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a>設定 TDS 稅務類型的扣繳稅款代碼

[!include [banner](../includes/banner.md)]

本主題說明如何設定從源頭扣除稅款 (TDS) 的稅碼。

1. 前往 **稅務 \> 間接稅 \> 扣繳稅款 \> 扣繳稅款代碼**。

    [![扣繳稅款代碼頁面。](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)

2. 在動作窗格上，選擇 **新增** 為 TDS 建立扣繳稅款代碼，並輸入所需的詳細資料。
3. 在 **一般** FastTab 的 **稅務類型** 欄位，選擇 **TDS** 以將稅碼歸類為 TDS 稅碼。
4. 在 **結算期間** 欄位，選擇 TDS 稅碼的 TDS 結算期間。
5. 在 **主科目** 欄位，選擇應將 TDS 金額過帳到的分類帳科目。
6. 在 **應收帳款** 欄位，選擇應將銷售交易中扣除的 TDS 金額過帳到的應收帳款。

    **來源** 欄位將自動設為 **總額百分比**，此值無法改變。

    > [!NOTE]
    > 對於 TDS 稅務類型的稅碼，不能將來源設為 **淨額百分比**。

7. 在 **扣繳稅款組成部分** 欄位，選擇 TDS 稅碼的 TDS 稅務組成部分。
8. 在動作窗格上，選擇 **值** 以開啟 **扣繳稅款值** 頁面。
9. 在 **開始日期** 欄位，輸入 TDS 值的開始日期。 在 **結束日期** 欄位中輸入結束日期。

    > [!NOTE]
    > **下限**、**上限** 和 **排除 ％** 欄位不適用於 TDS 稅務類型的稅碼。

10. 在 **值** 欄位，輸入 TDS 稅碼的 TDS 百分比。
11. 關閉 **扣繳稅款值** 頁面將返回 **扣繳稅款代碼** 頁面。

    > [!NOTE]
    > **扣繳稅款代碼** 頁面上的 **限制** 按鈕不適用於 TDS 稅務類型的稅碼。

12. 關閉頁面。
