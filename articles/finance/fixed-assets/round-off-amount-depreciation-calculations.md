---
title: 計算四捨五入的折舊金額
description: 本主題討論在 [帳冊設定] 頁面中的 [四捨五入折舊] 欄位。
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d3df48fc7bb092b0257c4652a8c67d1d740dbcfe
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451050"
---
# <a name="round-off-amount-for-depreciation-calculations"></a>計算四捨五入的折舊金額

[!include [banner](../includes/banner.md)]

本主題討論在 **帳冊設定** 頁面中的 **四捨五入折舊** 欄位。

為每個帳冊設定四捨五入的折舊金額。 四捨五入的折舊金額用於固定資產折舊概況表，其顯示固定資產的未來折舊和價值，也用於折舊方案。 輸入此帳冊允許的最低折舊金額。 

不管使用何種四捨五入設定，系統都不會四捨五入最近折舊期間的折舊金額。 在最近折舊期間結束時，如果使用殘值，則固定資產的值必須為 0 (零) 或殘值。

### <a name="example"></a>範例

未四捨五入的折舊計算為 2,444.44。 如下表中所示，根據設定的四捨五入方式，建議的金額會有所不同。

| 四捨五入方法 | 折舊金額 |
|-----------------|---------------------|
| 進位到 0.1    | 2,444.40            |
| 進位到 1.00   | 2,444.00            |
| 進位到 10.00  | 2,440.00            |
| 進位到 100.00 | 2,400.00            |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
