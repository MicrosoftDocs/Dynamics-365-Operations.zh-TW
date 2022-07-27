---
title: 從收貨倉庫到商店的直接轉運產品
description: 本程序介紹建立和處理直接轉運以將產品從訂購單接收地點配送到一個或多個商店的步驟。
author: Mirzaab
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailBuyersPushPerPackage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e65535a1879eab229f185e0e97d81a304fd292d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448575"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a>從收貨倉庫到商店的直接轉運產品

[!include [banner](../../includes/banner.md)]

本程序介紹建立和處理直接轉運以將產品從訂購單接收地點配送到一個或多個商店的步驟。 使用者可以定義多個設定並讓系統建議如何配送產品，或者手動輸入產品配送地點，以及配送到每個商店的數量。 程序不包括可在直接轉運中使用的資料設定，例如補貨規則、組織階層結構和商店權重。 程序使用的是 USRT 示範公司。

1. 前往所有訂購單。
2. 在清單中選擇一個訂購單，然後按一下連結開啟該訂單。
3. 在動作窗格上，按一下「零售和商務」。
4. 按一下直接轉運。
5. 按一下編輯。
    * 類別可用於篩選行區段中的項目。  
6. 在清單中，尋找並選擇所需紀錄。
7. 在直接轉運數量欄位中，輸入值以指定應配送多少所購買的所選產品。
8. 在其他直接轉運數量欄位中，輸入值以指定購買中可用產品的配送數量
9. 在配送欄位中，輸入「位置權重」。
    * 您可以選擇其他類型以使用不同的配送規則。  
10. 在補貨階層欄位中選擇值。
11. 在遵守分類欄位中選擇是。
12. 按一下計算數量。
13. 按一下建立訂單。
14. 按一下是。
15. 在清單中，找到並選擇接收產品的倉庫
16. 按一下訂單查看為所選倉庫建立的訂單



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]