---
title: 建立具有範圍的利息代碼
description: 可以設定利息代碼，根據值範圍以計算不同的利息金額。
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d77fc88f606f4e690583fbcda79f628a35f14f6a
ms.sourcegitcommit: 6a269db08e8bb3bb3405c9f4a512091d13c80faa
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2022
ms.locfileid: "8451575"
---
# <a name="create-an-interest-code-with-a-range"></a>建立具有範圍的利息代碼

[!include [banner](../../includes/banner.md)]
可以設定利息代碼，根據值範圍以計算不同的利息金額。 此程序將說明如何新增利息代碼並為其新增範圍。

1. 前往 **信用和收帳 > 利息 > 設定利息代碼**。
2. 點選 **新增**。
3. 請在 **利息代碼** 欄位中，輸入利息代碼名稱。
4. 在 **描述** 欄位中，輸入利息代碼的描述。
5. 選取 **月份**。
6. 展開 **收益** 區段。
7. 展開 **原幣收益** 區段。
8. 在 **分類帳過帳科目** 欄位中，指定所需值。
9. 在 **範圍利息** 欄位，選擇 [月份]。
10. 選點 **新增**。
11. 在 **描述** 欄位中，輸入貨幣和範圍的描述。
12. 點選 **儲存**。
13. 點選 **範圍**。
14. 點選 **新增**。
15. 在 **起始值** 輸入 0，然後輸入將用於計算利息的每月利息百分比。 在此範例中是 1.5。
16. 點選 **新增**。
17. 在 [下一個起始值] 輸入 4，這是您將計算新利息金額的第一個月。
18. 輸入將用於計算月份 4 後的月利息百分比。 在此範例中是 2.0。
19. 點選 **新增**。
20. 在 [下一個起始值] 輸入 7，這是您將計算新利息金額的下一個月。
21. 輸入將用於計算月份 7 後的月利息百分比。 在此範例中是 2.5。
22. 點選 **關閉** 以完成設定。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
