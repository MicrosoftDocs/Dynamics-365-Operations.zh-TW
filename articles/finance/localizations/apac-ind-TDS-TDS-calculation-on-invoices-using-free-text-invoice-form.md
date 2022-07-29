---
title: 普通發票頁面中發票的 TDS 計算
description: 本主題說明如何使用普通發票頁面計算發票的從源頭扣除稅款 (TDS)。
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
ms.openlocfilehash: 4b4466bb9d7a420b3fe8a1804437ae4229c63267
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451842"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a>普通發票頁面中發票的 TDS 計算

[!include [banner](../includes/banner.md)]

本主題說明如何使用 **普通發票** 頁面計算發票的從源頭扣除稅款 (TDS)。

1. 前往 **應收帳款 \> 發票 \> 所有普通發票**。

    [![普通發票頁面。](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)

2. 選擇 **新增** 以建立普通發票，然後輸入所需的詳細資料。
3. 選擇 **發票** 索引標籤。在 **扣繳稅款群組** 區段中，**評估對象的性質** 欄位會顯示客戶的評估對象類別的性質。
4. 在 **TDS 群組** 欄位中，查看或變更為廠商或客戶定義的預設 TDS 群組。

    > [!NOTE]
    > 在 **TDS 群組** 欄位中選擇值時，**TCS 群組** 欄位會變得無法使用。 僅在 **所有客戶** 頁面上為客戶將 **計算扣繳稅款** 選項設為 **是** 時，才計算 TDS。

5. 在 **稅務資訊** 索引標籤的 **公司資訊** 區段中，在 **名稱** 欄位中，為已為公司設定的備用地址選擇公司名稱。

    在 **扣繳稅款** 區段中，**稅務帳號 (TAN)** 欄位顯示所選公司的稅務帳號 (TAN)。

6. 在 **發票行** 索引標籤上建立發票行，然後輸入所需的詳細資料。

    在 **扣繳稅款群組** 區段中，**稅務帳號 (TAN)** 欄位會顯示 TAN，**TDS 群組** 欄位顯示 TDS 群組。

7. 選擇 **扣繳稅款** 以打開 **臨時扣繳稅款交易** 頁面。 此頁面的上部具有以下欄位：

    - **扣繳稅款的總金額** - 已為 TDS 群組的交易計算的總 TDS。
    - **值** - 已用於計算交易 TDS 的總百分比。 總百分比以為 TDS 稅碼定義和附加到 TDS 群組的公式為基礎。
    - **調整後扣繳稅款總額** - TDS 群組中所有稅碼的調整後 TDS 總金額。
    - **TDS** – 選取核取方塊表示 TDS 群組已附加到交易。

    **概觀**、**一般** 和 **調整** 索引標籤上的欄位，為附加到 TDS 群組的每個 TDS 稅碼顯示計算 TDS 金額和調整後 TDS 金額詳細資料。

8. 選擇 **閾值** 以打開 **閾值** 頁面，您可以在其中查看為附加到特定 TDS 稅碼的 TDS 稅務組成部分定義的閾值限制。
9. 選擇 **公式設計工具** 以打開 **公式設計工具** 頁面，您可以在其中查看為特定 TDS 稅碼定義的公式。
10. 過帳普通發票。 為普通發票計算的 TDS 金額將過帳到為 TDS 群組中的每個 TDS 稅碼定義的應收帳款。 TDS 稅碼的應收帳款在 **扣繳稅款代碼** 頁面上定義。
11. 選擇 **過帳扣繳稅款** 以打開 **扣繳稅款交易** 頁面。 **值** - 欄位顯示已用於計算交易 TDS 的總百分比。

    **概觀**、**一般** 和 **金額** 索引標籤上的欄位顯示針對發票行計算的 TDS 金額。

12. 查看附加到 TDS 群組的每個 TDS 稅碼的 TDS 計算資訊。
