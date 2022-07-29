---
title: 為 TDS 稅務類型設定稅務構件
description: 本主題說明如何為從源頭扣除稅款 (TDS) 稅務類型設定扣繳稅款組成部分。 本主題還說明如何定義用於計算每個 TDS 組成部分的 TDS 閾值限制。
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
ms.openlocfilehash: 34ef487da382e50efb2f9637d537669524c25d8f
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451815"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a>為 TDS 稅務類型設定稅務構件

[!include [banner](../includes/banner.md)]

本主題說明如何為從源頭扣除稅款 (TDS) 稅務類型設定扣繳稅款組成部分。 TDS 組成部分是 TDS、附加費、PE-Cess 和 SHE Cess。 本主題還說明如何定義用於計算每個 TDS 組成部分的 TDS 閾值。 此外，您可以定義異常閾值，用於計算每個 TDS 組成部分的 TDS。

請按照以下步驟設定 TDS 組成部分。

1. 前往 **稅務 \> 設定 \> 扣繳稅款 \> 扣繳稅款組成部分**。

    [![扣繳稅款組成部分頁面。](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)

2. 在 **稅務類型** 欄位，選擇 **TDS** 以為 TDS 稅務類型設定扣繳稅款組成部分。
3. 在動作窗格上，選擇 **新增** 建立行。
4. 在 **扣繳稅款組成部分** 欄位，輸入 TDS 組成部分的名稱。
5. 在 **扣繳稅款組成部分群組** 欄位，選擇 TDS 組成部分要附加到的 TDS 扣繳稅款組成部分群組。
6. 在 **一般** 的 FastTab 上，在 **描述** 欄位中，輸入 TDS 組成部分的描述。
7. 在動作窗格上，選擇 **閾值** 以打開 **閾值** 頁面，以便您可以定義用於計算 TDS 組成部分的 TDS 的閾值。
8. 使用 **開始日期** 和 **結束日期** 欄位定義閾值適用的期間。
9. 在 **一般** FastTab 的 **閾值** 欄位中，輸入用於計算 TDS 組成部分的 TDS 的閾值金額。 只有當累計發票金額超過閾值時，才會從源頭扣除稅款。

    例如，如果閾值金額為 10,000，則在累計發票金額超過 10,000 (即為 10,001 或更多時) 後計算 TDS。

10. 在 **異常閥值** 欄位中，輸入用於計算 TDS 組成部分的 TDS 的異常閾值金額。 只有當累計發票金額超過異常閾值時，才會從源頭扣除發票行上的稅款。

    例如，如果異常閾值金額為 5,000，則在發票行金額超過 5,000 (換言之，如果金額為 5,001 或更多) 時，將在特定發票行上計算 TDS。

    [![閾值頁面。](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)

    > [!NOTE]
    > 異常閾值金額必須小於或等於閾值金額。
    >
    > 如果交易金額超過異常閾值，即使累計發票金額未超過在 **閾值** 欄位中指定的閾值，也扣除交易的稅款。

11. 關閉 **閾值** 頁面以返回 **扣繳稅款組成部分** 頁面。
12. 在動作窗格上，選擇 **複製** 以打開 **複製扣繳稅款組成部分** 對話方塊，以便您可以將為一個 TDS 組成部分群組設定的 TDS 組成部分複製到另一個 TDS 組成部分群組。
13. 在 **開始** 欄位中，選擇要從中複製 TDS 組成部分的 TDS 組成部分群組。 在 **結束** 欄位中，選擇要將 TDS 組成部分複製到的扣繳稅款組成部分群組。

    > [!NOTE]
    > 不會複製附加到這兩個 TDS 組成部分群組的常見 TDS 組成部分。

14. 選擇 **確定** 以在 **扣繳稅款組成部分** 頁面上為其他 TDS 組成部分群組複製和建立 TDS 組成部分。

    [![複製扣繳稅款組成部分對話方塊。](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)

15. 關閉頁面。
