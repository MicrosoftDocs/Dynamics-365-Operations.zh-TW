---
title: 設定 TDS 參數
description: 本主題說明如何設定參數以啟用指定交易中的從源頭扣除稅款 (TDS) 功能。 這是使用從源頭扣除稅款 (TDS) 功能的必要步驟。
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
ms.openlocfilehash: ca98a74753ca0de3b376cb89ef47862bc1bfb30e
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451776"
---
# <a name="set-the-tds-parameters"></a>設定 TDS 參數

[!include [banner](../includes/banner.md)]

本主題說明如何設定參數以啟用指定交易中的從源頭扣除稅款 (TDS) 功能。 這是使用從源頭扣除稅款 (TDS) 功能的必要步驟。

1. 前往 **總帳\>分類帳設定\>總分類帳參數**。
2. 在 **直接稅** 索引標籤的 **從源頭扣除稅款** 區段，將 **啟用 TDS** 選項設定為 **是** 以啟用 TDS 功能，以及用於該功能的頁面和欄位。
3. 將 **發票** 選項設定為 **是**，以啟用用於在發票等級計算和扣除 TDS 的欄位。
4. 將 **付款** 選項設定為 **是**，以啟用用於在付款等級計算和扣除 TDS 的欄位。

    [![直接稅索引標籤。](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)

5. 在 **編號規則** 索引標籤，找到 **參考** 欄位設定為 **扣繳稅款付款** 的行。 在該行的 **編號規則代碼** 欄位中，選擇編號規則代碼。 編號規則代碼用於產生定期 TDS 結算流程的憑證編號。

    > [!NOTE]
    > 若要執行定期 TDS 結算流程，請前往 **稅務 \> 申報 \> 扣繳稅款 \> 扣繳稅款付款**。

    [![編號規則索引標籤。](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)

6. 關閉頁面。
