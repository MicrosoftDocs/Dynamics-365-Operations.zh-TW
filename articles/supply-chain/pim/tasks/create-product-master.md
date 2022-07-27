---
title: 建立基準產品
description: 為預定義的變體建立基準產品。
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e76c367d4aa6c08332371374a26dd6fdbbdb4eb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449001"
---
# <a name="create-a-product-master"></a>建立基準產品

[!include [banner](../../includes/banner.md)]

為預定義的變體建立基準產品。 建立此程序的示範資料公司為 USMF。 此程序適用於產品設計師。


## <a name="create-a-new-product-master"></a>建立新的基準產品
1. 前往 **功能窗格 > 模組 > 產品資訊管理 > 產品 > 基準產品**。
2. 按一下 **新增**。
3. 在 **產品編號** 欄位中，輸入一個值。 編號必須是唯一的。 可以為 **產品編號** 欄位設定序列號。 在這種情況下，使用者就不必輸入值。
4. 在 **產品名稱** 欄位中，輸入一個值。 輸入描述性產品名稱。 該值預設為搜尋名稱，但使用者可以變更。
5. 在 **產品維度群組** 欄位中，按一下下拉式按鈕開啟查詢。 產品維度群組決定建立產品變體時，要用 4 個產品維度群組中的哪一個。 此範例使用顏色和大小群組。
6. 在清單中，尋找並選擇所需紀錄。
7. 在列表中，按一下所選行中的連結。 預設 **配置技術** 是「預定義變體」。 這將用於此範例。
8. 按一下 **確定**。

## <a name="select-product-dimension-groups"></a>選擇產品維度群組
1. 在 **顏色群組** 欄位中，按一下下拉式按鈕開啟查詢。
2. 在清單中，尋找並選擇所需紀錄。
3. 在列表中，按一下所選行中的連結。
4. 在 **大小群組** 欄位中，按一下下拉式按鈕開啟查詢。
5. 在清單中，尋找並選擇所需紀錄。
6. 在列表中，按一下所選行中的連結。

## <a name="add-dimension-groups"></a>新增維度群組
1. 在 **動作窗格** 上，按一下 **產品**。
2. 按一下 **維度群組**，打開下拉對話框。
3. 在 **儲存維度群組** 欄位中，按一下下拉式按鈕開啟查詢。 存儲維度可幫助您控制項目的儲存方式，和從庫存中取出的方式。 例如，儲存維度可以包括地點和倉庫。
4. 在清單中，尋找並選擇所需紀錄。
5. 在列表中，按一下所選行中的連結。
6. 在 **追蹤維度群組** 欄位中，按一下下拉式按鈕開啟查詢。 追蹤維度群組決定您可以新增到產品的追蹤維度。 例如，使用批次編號和序列號來追蹤庫存項目。
7. 在清單中，尋找並選擇所需紀錄。
8. 在列表中，按一下所選行中的連結。
9. 按一下 **確定**。
10. 按一下 **儲存**。
11. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]