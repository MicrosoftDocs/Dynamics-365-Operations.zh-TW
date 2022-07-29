---
title: 建立成本分攤原則並將其分配給成本控制單位
description: 使用此程序來建立成本分攤原則和相應的規則，並將其分配給成本控制單位。
author: ShylaThompson
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: de50191a7be30364236ee82b99d207e6f131cce26097a39728fea25e3ef7df9d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450141"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a>建立成本分攤原則並將其分配給成本控制單位

[!include [banner](../../includes/banner.md)]

使用此程序來建立成本分攤原則和相應的規則，並將其分配給成本控制單位。 此錄製內容使用 USP2 示範資料公司。


## <a name="create-a-policy"></a>建立原則
1. 前往 [成本會計] > [原則] > [成本分攤原則]。
2. 點選 [新增]。
3. 在 [原則名稱] 欄位中，輸入一個值。
4. 在 [成本物件維度階層] 欄位中，輸入或選取一個值。
    * 選取 [組織]。  
5. 在 [會計維度] 欄位中，輸入或選取一個值。
6. 點選 [儲存]。

## <a name="create-allocation-rules"></a>建立分攤規則
1. 點選 [新增]。
2. 在清單中，標示選取的列。
3. 在 [成本物件維度階層節點] 欄位中，輸入或選取一個值。
4. 在 [成本行為] 欄位中，選擇 [總計]。
5. 在 [分攤基礎] 欄位中，輸入或選取一個值。
6. 點選 [新增]。
7. 在清單中，標示選取的列。
8. 在 [成本物件維度階層節點] 欄位中，輸入或選取一個值。
9. 在 [成本行為] 欄位中，選擇 [總計]。
10. 在 [分攤基礎] 欄位中，輸入或選取一個值。
11. 點選 [新增]。
12. 在清單中，標示選取的列。
13. 在 [成本物件維度階層節點] 欄位中，輸入或選取一個值。
14. 在 [成本行為] 欄位中，選擇 [總計]。
15. 在 [分攤基礎] 欄位中，輸入或選取一個值。
    * 繼續操作，直到您建立了所有規則。  
16. 點選 [儲存]。

## <a name="assign-the-policy-to-a-cost-control-unit"></a>將原則指派到成本控制單位
1. 點選 [成本控制單位的原則指派]。
2. 點選 [新增]。
3. 在清單中，標示選取的列。
4. 在 [會計生效日期] 欄位中，輸入一個日期。
    * 規則具有時效性。 如果建立了更新的版本，使用者或系統可讓規則到期。  
5. 在 [成本控制單位] 欄位中，輸入或選取一個值。
6. 點選 [儲存]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]