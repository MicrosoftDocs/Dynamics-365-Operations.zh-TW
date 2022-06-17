---
title: 編輯零售交易的財務維度
description: 本主題說明如何在 Microsoft Dynamics 365 Commerce 中編輯零售交易的財務維度。
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: d5fee5f5dfee73ddb9fbcf8a33df66c29f9438b49136181633b989d1a02ef4f5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8452805"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a>編輯零售交易的財務維度

[!include [banner](../includes/banner.md)]

本主題說明如何在 Microsoft Dynamics 365 Commerce 中編輯零售交易的財務維度。

## <a name="edit-financial-dimensions"></a>編輯財務維度

若要在 Commerce 總部中編輯零售交易的財務維度，請執行下列步驟。

1. 開啟 **整合應用程式的財務維度設定** 頁面。
1. 選取使用中的 **預設維度整合** 記錄。
1. 在 **財務維度** FastTab 上，確保您要在 Excel 工作表中編輯的所有維度都存在於 **已選取** 清單中。 如需詳細資訊，請參閱[資料實體](../fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration.md#data-entities)。
1. 從 **對帳單** 頁面、**零售交易** 頁面，或 **商店財務** 工作區中的 **交易驗證失敗** 圖標下載並打開 Excel 檔案。
1. 若要變更交易財務維度，請選取 **設計**，然後選取 **交易 (可稽核)** 列旁的鉛筆符號。
1. 尋找並選取 **FinancialDimensionDisplayValue** 欄位，在 Excel 工作表的標題部分中選取一個儲存格，然後選取 **新增標籤**。
1. 依序選取您在上一個步驟中所選儲存格下方的儲存格、**新增值** 和 **重新整理**。 財務維度會新增至 Excel 工作表，然後即可對其進行編輯和發佈。
1. 若要變更交易明細上的維度，請選取 **銷售交易 (可稽核)** 列，選取鉛筆符號，然後重複步驟 6 和 7。
1. 若要變更付款明細上的維度，請選取 **付款交易 (可稽核)** 列，選取鉛筆符號，然後重複步驟 6 和 7。

## <a name="additional-resources"></a>其他資源

[編輯和稽核現金自運及現金管理交易](edit-cash-trans.md)

[編輯和稽核線上訂單以及非同步客戶訂單交易](edit-order-trans.md)

[建立 Excel 活頁簿以編輯零售交易](create-excel-edit.md)

[將欄位新增至 Excel 活頁簿以編輯零售交易](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]