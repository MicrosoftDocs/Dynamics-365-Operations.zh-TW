---
title: 記錄 TDS 可退稅憑證編號
description: 本主題說明如何使用可退稅憑證頁面，記錄特定廠商、客戶或分類帳收到的從源扣繳稅款 (TDS) 憑證的憑證編號和日期。
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
ms.openlocfilehash: 8fa4d1200818b4657b044a376ebb292426250ae1
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451800"
---
# <a name="record-tds-recoverable-certificate-numbers"></a>記錄 TDS 可退稅憑證編號

[!include [banner](../includes/banner.md)]

本主題說明如何使用 **可退稅憑證** 頁面，記錄特定廠商、客戶或分類帳收到的從源扣繳稅款 (TDS) 憑證的憑證編號和日期。 要更新此頁面上為 TDS 交易的 TDS 憑證編號和日期，請使用 **更新憑證** 頁面 (**總帳 \> 定期 \> 扣繳稅款 \> 更新憑證**)。 更新完 TDS 憑證編號後，關閉它們。

按照以下步驟記錄 TDS 憑證編號和日期。

1. 前往 **稅務 \> 間接稅 \> 扣繳稅款 \> 可退稅憑證**。

    [![可退稅憑證頁面。](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png) 

2. 在 **可退稅憑證** 頁面的 **稅務類型** 欄位，選擇 **TDS**。
3. 選取 **新增** 建立記錄。
4. 在 **憑證編號** 欄位中，輸入 TDS 憑證編號。
5. 在 **帳戶類型** 欄位中，選擇接收 TDS 憑證的帳戶類型：**廠商**、**客戶** 或 **分類帳**。
6. 在 **帳戶** 欄位中，選擇廠商、客戶或分類帳科目編號，具體取決於您選擇的科目類型。 **名稱** 欄位顯示廠商、客戶或分類帳科目的名稱。
7. 在 **憑證金額** 欄位中，輸入 TDS 憑證的金額。
8. 在 **日期** 欄位中，輸入憑證編號的憑證日期。
9. 選擇 **查詢** 以打開 **憑證交易** 頁面，您可以在其中查看更新了 TDS 憑證編號和日期的 TDS 交易。 可在 **更新憑證** 頁面上更新此資訊 (**稅務 \> 申報 \> 扣繳稅款 \> 更新憑證**)。

    **更新憑證** 頁面顯示每個 TDS 交易的以下資訊：

    - **日期** - TDS 交易的過帳日期。
    - **憑證** - TDS 交易的憑證編號。
    - **來源** – 用於建立 TDS 交易的模組。
    - **帳戶** – 為其建立 TDS 交易的廠商、客戶或分類帳科目編號。
    - **名稱** – 為其建立 TDS 交易的廠商、客戶或分類帳科目的名稱。
    - **金額** - 計算 TDS 的發票金額。
    - **稅額** - 為交易計算的 TDS 稅額。
    - **憑證日期** – 為 TDS 交易更新的 TDS 憑證日期。
    - **憑證編號** – 為 TDS 交易更新的 TDS 憑證編號。

10. 在 **可退稅憑證** 頁面上，選擇 **已關閉** 核取方塊，以在 **更新憑證** 頁面上為 TDS 交易完成更新後，關閉 TDS 憑證編號。

    若要對頁面上所有記錄選取 **已關閉** 核取方塊，請選擇 **全部標記**。

    > [!NOTE]
    > 為其選取 **已關閉** 核取方塊的 TDS 憑證編號都無法在 **更新憑證** 頁面上使用。
