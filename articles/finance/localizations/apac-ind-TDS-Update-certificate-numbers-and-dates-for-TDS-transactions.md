---
title: 更新 TDS 交易的憑證編號和日期
description: 本主題說明如何更新從源頭扣除稅款 (TDS) 的為廠商、客戶和分類帳科目記錄的可退稅憑證編號和日期。
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
ms.openlocfilehash: b23f01f110009ba2f0cfe71c7bb995a4dc21ca3b
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451836"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a>更新 TDS 交易的憑證編號和日期

[!include [banner](../includes/banner.md)]

本主題說明如何更新從源頭扣除稅款 (TDS) 的為廠商、客戶和分類帳科目記錄的可退稅憑證編號和日期。 您可以在 **可退稅的憑證** 頁面上查看 TDS 交易的憑證。 可以使用 **更新憑證** 頁面更新憑證。

按照以下步驟更新 TDS 交易的憑證編號和日期。

1. 前往 **稅務 \> 申報 \> 扣繳稅款 \> 更新憑證**。

    [![更新憑證頁面。](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)

2. 在 **更新憑證** 頁面的 **選擇** 區段，在 **稅務類型** 欄位，選擇 **TDS**。
3. 在 **憑證編號** 欄位，選擇客戶或廠商的 TDS 憑證編號。

    > [!NOTE]
    > **憑證編號** 欄位僅列出 **可退稅的憑證** 頁面上清除了 **已關閉** 核取方塊的 TDS 憑證編號

    **憑證日期** 欄位顯示憑證日期。 **帳戶類型** 欄位顯示接收 TDS 憑證編號的帳戶類型，**名稱** 欄位顯示帳戶的名稱。

5. 在 **起始日期** 和 **結束日期** 欄位中，選擇要顯示 TDS 交易之期間的開始和結束日期。
6. 選擇 **顯示資料** 查看在選定期間過帳的 TDS 交易。

    在 **概觀** 索引標籤中，上方窗格中的格線顯示有關在選定期間為廠商或客戶過帳的每個 TDS 交易的以下資訊：

    - **憑證** - TDS 交易的憑證編號。
    - **日期** - TDS 交易的日期。
    - **金額** - 計算 TDS 的發票金額。
    - **稅額** - 為交易計算的 TDS 稅額。

7. 若要將特定 TDS 交易從上部格線移動到下部格線，請選擇交易，然後選擇 **包括**。 或者，選擇 **全部包括** 將所有 TDS 交易從上部格線移動到下部格線。

    若要將特定 TDS 交易或所有 TDS 交易從下部格線移動到上部格線，請使用 **排除** 或 **全部排除** 按鈕。

8. 選擇 **更新** 以更新下部格線中 TDS 交易的 **憑證編號** 和 **憑證日期** 欄位。
10. 前往 **稅務 \> 間接稅 \> 扣繳稅款 \> 可退稅憑證**，並選擇 **查詢**，以查看在 **憑證交易** 頁面上具有新憑證編號的已更新交易行。

    [![憑證交易頁面。](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)
