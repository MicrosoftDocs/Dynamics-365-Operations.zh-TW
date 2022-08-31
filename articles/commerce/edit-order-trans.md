---
title: 編輯和稽核線上訂單以及非同步客戶訂單交易
description: 本文章描述如何在 Microsoft Dynamics 365 Commerce 中編輯和稽核線上訂單和非同步客戶訂單交易。
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.industry: Retail
ms.openlocfilehash: dac7ffe6d62aaea11f2f5af0476db446b091938b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287669"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a>編輯和稽核線上訂單以及非同步客戶訂單交易

[!include [banner](../includes/banner.md)]

本文章描述如何在 Microsoft Dynamics 365 Commerce 中編輯和稽核線上訂單和非同步客戶訂單交易。

## <a name="overview"></a>概觀

在 Commerce 10.0.5 與 10.0.6 版之間，新增了編輯現金自運交易 (例如銷售和退貨) 和現金管理交易 (例如浮動輸入和取消招標) 的支援。 在 Commerce 10.0.7 版中，新增了編輯線上訂單交易和非同步客戶訂單交易的支援。

## <a name="edit-and-audit-order-transactions"></a>編輯和稽核訂單交易

若要在 Commerce 總部中編輯和稽核訂單交易，請執行下列步驟。

1. 安裝 [Microsoft Dynamics Office 增益集](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview)。
1. 在 **Retail** 參數頁面 **客戶訂單** 索引標籤的 **訂單** FastTab 上，為 **訂單同步錯誤的保留代碼** 指定一個保留代碼。
1. 開啟 **存放區財務** 工作區。 **線上訂單同步錯誤** 和 **客戶訂單同步錯誤** 圖標提供預先篩選的零售交易頁面檢視。 每個圖標都會顯示對應訂單類型同步失敗的交易記錄。
1. 開啟 **線上訂單同步錯誤** 頁面或 **客戶訂單同步錯誤** 頁面。 選取記錄以檢視同步錯誤詳細資料。 **同步狀態** FastTab 提供下列錯誤詳細資料：

    - 擱置中的訂單狀態
    - 訂單錯誤詳細資料
    - 修改日期和時間
    - 重試計數

1. 如果錯誤詳細資料指出必須修正記錄，請選取 **Office 增益集**，然後選 **取編輯選取的交易**。 這會開啟一個 Excel 檔案，其中顯示所選交易的詳細資料。

    - 如果所編輯的交易是線上訂單交易，則 Excel 檔案包含下列工作表：

        - **交易** - 此工作表包含交易的標題詳細資料。
        - **銷售交易** - 此工作表包含交易的明細詳細資料。
        - **付款交易** - 此工作表包含交易的付款明細詳細資料。
        - **折扣交易** - 此工作表包含交易的折扣相關詳細資料。
        - **稅務交易** - 此工作表包含交易的稅務相關詳細資料。
        - **費用交易** - 此工作表包含交易的費用相關資料。

    - 如果所編輯的交易是非同步客戶訂單交易，則 Excel 檔案包含下列工作表：

        - **明細** - 此工作表包含交易的標題和明細詳細資料。
        - **付款** - 此工作表包含交易的付款明細詳細資料。
        - **折扣** - 此工作表包含交易的折扣相關詳細資料。
        - **稅務** - 此工作表包含交易的稅務相關詳細資料。
        - **費用** - 此工作表包含交易的費用相關資料。

1. 在 Excel 檔案的 **擱置中的訂單狀態** 欄位中，輸入 **編輯中**，然後發佈變更。 如此一來，即可防止在批次模式中執行的 **同步訂單** 作業在處理期間略過此記錄。
1. 在 Excel 檔案中，修改適當的欄位，然後使用 Dynamics Excel 增益集的發佈功能將資料上傳回 Commerce 總部。 發佈資料之後，這些變更就會反映在系統中。 在發佈期間，不會對使用者所做的變更進行驗證。
1. 您可以針對標題層級變更選取 **零售交易** 標頭中的 **檢視稽核線索** 來檢視變更的完整稽核線索，也可以在適當交易頁面上的相關區段和記錄中進行檢視。 例如，所有與銷售明細相關的變更會顯示在 **銷售交易** 頁面上，而所有與付款相關的變更則會顯示在 **付款交易** 頁面上。 系統會維護變更的下列稽核詳細資料：

    - 修改日期和時間
    - 欄位
    - 舊值
    - 新值
    - 修改者

1. 當您完成並發佈變更之後，請選取 **同步訂單** 以立即開始同步程序。 或者，您可以等候在批次模式中執行的同步程序處理交易。

根據預設，在成功同步訂單之後，這些訂單會根據 Commerce 參數中定義的保留代碼處於保留狀態。 您必須先移除對訂單的保留，才能進一步處理訂單以履行或執行其他作業。

## <a name="additional-resources"></a>其他資源

[編輯和稽核現金自運及現金管理交易](edit-cash-trans.md)

[編輯零售交易的財務維度](edit-financial-dim.md)

[建立 Excel 活頁簿以編輯零售交易](create-excel-edit.md)

[將欄位新增至 Excel 活頁簿以編輯零售交易](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
