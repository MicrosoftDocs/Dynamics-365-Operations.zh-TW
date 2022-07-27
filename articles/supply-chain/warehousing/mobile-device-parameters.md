---
title: 全球行動裝置參數
description: 本主題說明如何在倉庫管理參數頁面上設定行動裝置的設定。
author: HuberIvan
ms.date: 08/13/2021
ms.topic: article
ms.search.form: WHS
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-huberivan
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 03c10232d55c99c73e625170797f89f6c77e812b
ms.sourcegitcommit: 99bde425ade701ef244c6bca6d411aef94a59b3c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2021
ms.locfileid: "8447711"
---
# <a name="global-mobile-device-parameters"></a>全球行動裝置參數

[!include [banner](../includes/banner.md)]

本主題說明如何設定影響系統與行動裝置互動方式的全球倉庫管理參數。

如需如何設定倉庫工作人員的詳細資訊，請參閱[管理倉庫工作人員](manage-warehouse-workers.md)。 如需行動裝置上處理牌照的詳細資訊，請參閱[透過 Warehouse Management 行動應用程式接收牌照](warehousing-mobile-device-app-license-plate-receiving.md)。 如需週期盤點程序的詳細資訊，請參閱[週期盤點](cycle-counting.md)和[週期盤點範例案例](cycle-counting-scenarios.md)。

## <a name="open-the-warehouse-management-parameters-page"></a>開啟倉庫管理參數頁面

若要開啟 **倉庫管理參數** 頁面，請前往 **倉庫管理 \> 設定 \> 倉庫管理參數**。 然後，您可以設定與行動裝置工作相關的欄位，如本主題下一節所述。

## <a name="mobile-device-fasttab-on-the-general-tab"></a>一般索引標籤上的行動裝置 FastTab

全球行動裝置設定位於 **倉庫管理參數** 頁面 **一般** 索引標籤上的 **行動裝置** FastTab。 可以使用以下欄位。

| 欄位 | 描述 |
|---|---|
| 行動裝置備註類型 | 選取在銷售訂單揀貨期間向工作人員顯示的資訊類型。 |
| 掃描數量限制 | 輸入工作人員在每個工作階段期間可以使用具有 **工作建立程序** 值進行的 *調整*。 此欄位不影響使用其他任何類型功能表項目完成的掃描。 |
| 使用行動裝置工作階段記錄 | 將此選項設定為 *是*，以保留工作人員的登入記錄。 若要檢視記錄，請前往 **工作使用者工作階段 \> 查詢和報告 \> 行動裝置記錄 \> 工作使用者工作階段**。 |
| 儲存的錯誤數 | 輸入系統應儲存的最大錯誤記錄數。 若要檢視錯誤記錄，請前往 **工作使用者工作階段 \> 查詢和報告 \> 行動裝置記錄 \> 工作使用者工作階段**。 |
| 預設倉儲轉移日記帳 | 選擇當工作人員使用行動裝置將產品從一個倉庫移動到另一個倉庫時使用的日記帳。 |
| 當外部審閱時，允許訂購單行註冊 | 如果工作人員可以使用行動裝置，為 *在外部審查中* 值為 **核准狀態** 的值註冊訂單行，則將此選項設定為 *是*。 若要防止工作人員為外部核准的訂購單註冊行，請將此選項設定為 *否*。 |
| 啟用 RSAT 支援 | 該欄為啟用 Warehouse Management 行動裝置應用程式工作驗證器，他會記錄並驗證應用程式執行的每個步驟。 由於此程序會顯著降低系統效能，因此，您應該僅於測試期間啟用驗證器。 您永遠不應於實際執行環境中啟用。 |
