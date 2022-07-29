---
title: 將 TDS 稅碼附加到 TDS 稅組並定義用於計算 TDS 的公式
description: 本主題說明如何設定從源頭扣除稅款 (TDS) 稅組，並將 TDS 稅碼附加到 TDS 稅組。 要計算 TDS 稅組的 TDS，必須定義附加到它的 TDS 稅碼的公式。
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
ms.openlocfilehash: ce4c2dcfb6ac6f95af3bc354412c36956ae63242
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451773"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a>將 TDS 稅碼附加到 TDS 稅組並定義用於計算 TDS 的公式

[!include [banner](../includes/banner.md)]

本主題說明如何設定從源頭扣除稅款 (TDS) 稅組，並將 TDS 稅碼附加到 TDS 稅組。 要計算 TDS 稅組的 TDS，必須定義附加到它的 TDS 稅碼的公式。

按照以下步驟設定 TDS 稅組，將 TDS 稅碼附加到它，並定義用於計算 TDS 的公式。

1. 前往 **稅務 \> 間接稅 \> 扣繳稅款 \> 扣繳稅款群組**。

    [![扣繳稅款群組頁面。](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)

2. 在動作窗格上，選擇 **新增** 為 TDS 建立扣繳稅款組，並輸入所需的詳細資料。
3. 在 **稅務類型** 欄位中，選取 **TDS**。
4. 在 **設定** FastTab，選擇 **新增** 來建立行。
5. 在 **扣繳稅款代碼** 欄位，選擇 TDS 稅組的 TDS 稅碼。 **扣繳稅款名稱** 欄位顯示 TDS 稅碼的名稱，**值** 欄位顯示值。
6. 要忽略為附加到 TDS 交易中 TDS 稅碼的 TDS 稅元件定義的閾值限制和異常閾值限制，請選擇 **忽略閾值** 核取方塊。
7. 要防止在交易中計算稅組，請選擇 **免稅** 核取方塊。
8. 在動作窗格上，選擇 **設計工具** 以打開公式設計工具，以便定義用於計算 TDS 稅組的 TDS 公式。 在 **設計工具** 頁面的 **稅收** 索引標籤顯示已為 TDS 稅組選擇的 TDS 稅碼。

    [![設計工具頁面。](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)

9. 在 **計算** 索引標籤上，選擇 **Alt+N** 建立行。 **識別碼** 欄位顯示 TDS 計算自動產生的優先順序識別碼。
10. 在 **稅碼** 欄位中，選擇要為其定義公式的 TDS 稅碼。 已為 TDS 稅組選擇的所有 TDS 稅碼都可在此欄位中選擇。
11. 在 **應稅基數** 欄位中，選擇用於計算 TDS 的基數：

    - **總額** – 使用為稅碼定義的計算運算式，根據總交易金額 (即發票金額) 計算 TDS。
    - **不含總金額** – 根據為稅碼定義的計算運算式計算 TDS。

    > [!NOTE]
    > 對於優先順序識別碼為 **1** 的 TDS 稅碼，**應稅基數** 欄位不能設定為 **不含總金額**。

12. TDS 計算根據在 **計算運算式** 欄位中為附加到 TDS 稅組的每個稅碼定義的公式。 選擇加號 (+)、減號 (-)、乘號 (\*) 或除號 (/) 按鈕，在 **計算運算式** 欄位中輸入所選 TDS 稅碼的計算運算式。

    > [!NOTE]
    > 針對優先順序識別碼為 **1** 的 TDS 稅碼，不定義任何計算運算式。

13. 若要在 **計算運算式** 欄位中定義 TDS 稅碼的計算運算式，請新增在 **稅務** 索引標籤上提供的 TDS 稅碼。若要在 **計算運算式** 欄位中新增 TDS 稅碼，您可以使用以下任一種方法：

    - 將所需的稅碼從 **稅務** 索引標籤拖曳到 **計算運算式** 欄位。
    - 點兩下 (或按兩下) **稅務** 索引標籤上的所需稅碼。
    - 選擇並按住 (或按滑鼠右鍵) **稅務** 索引標籤上的所需稅碼，然後選擇 **新增稅碼**。

    > [!NOTE]
    > 在每個 TDS 稅碼前插入計算運算式。 已新增到計算運算式中的 TDS 稅碼會顯示在中括弧 (\[...\]) 中。

14. 若要清除在 **計算運算式** 欄位中為稅碼定義的計算運算式，選擇 **C** 按鈕。
15. 若要刪除 **計算** 索引標籤上的記錄，請選擇 **刪除**。
16. 關閉頁面。
