---
title: 完成已發布基準產品的基本設定
description: 本主題說明在 BOM 版本中使用基準產品之前，如何完成必要的基礎設定。
author: t-benebo
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a1ec567892c09968fe80c3a075d656185aceb4e5
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448119"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a>完成已發布基準產品的基本設定

[!include [banner](../../includes/banner.md)]

本主題說明在 BOM 版本中使用基準產品之前，如何完成必要的基礎設定。

這是說明如何建立維度式設定組合的第三個程序 (共八個程序)。 建立此程序的示範資料公司為 USMF。

1. 移至 **瀏覽窗格 > 模組 > 產品資訊管理 > 產品 > 已發佈產品**。
2. 在清單中，尋找並選擇所需紀錄。 選取您在第二個程序中發布的基準產品。 該基準產品是使用維度式設定技術建立的。  
3. 在動作窗格上，選擇 **產品**。
4. 選擇 **維度群組** 打開下拉對話框。
5. 在 **儲存維度群組** 欄位中，選擇下拉式按鈕開啟查詢。
6. 在清單中，尋找並選擇所需紀錄。 儲存維度群組確定哪些儲存維度用於產品交易。 對於這個程序，選取 **地點**。  
7. 在 **追蹤維度群組** 欄位中，選擇下拉式按鈕開啟查詢。
8. 在清單中，尋找並選擇所需紀錄。 追蹤維度群組確定哪些追蹤維度用於產品交易。 為這個程序，選取 **無**。  
9. 按一下 **確定**。
10. 按一下 **編輯**。
11. 在 **項目型號群組** 欄位中，選擇下拉式按鈕開啟查詢。
12. 在清單中，尋找並選擇所需紀錄。 品項模型群組包含設定，該設定在品項接收和發出上，決定控制和處理的方式。 並確定如何計算品項消耗。 為這個程序，選取 **FIFO**。  
13. 展開 **管理成本** 區段。
14. 在 **項目群組** 欄位中，選擇下拉式按鈕開啟查詢。
15. 在清單中，尋找並選擇所需紀錄。 品項群組用以將庫存品項分組，以管理庫存。 為這個程序，選取 **CarAudio**。  
16. 在動作窗格上，選取 **計劃**。
17. 選取 **預設訂單設定值**。
18. 在 **預設訂單類型** 欄位中，選取一個選項。 選取 **生產** 指定此基準產品的預設供應選項是生產它。  
19. 選擇 **儲存**。
20. 關閉頁面。
21. 關上 **已發布產品詳細資料** 表單。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]