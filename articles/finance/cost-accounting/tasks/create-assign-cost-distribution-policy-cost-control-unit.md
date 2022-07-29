---
title: 建立成本分攤原則並將其指配給成本控制單位
description: 成本分攤規則用於指派在財務上已在集體成本中心計算的成本。
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostDistributionRule
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9230410d7b8cd4c94fdab5465e542e16fd286c530a8189d5cd1eca825bb1faf4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450792"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a>建立成本分攤原則並將其指配給成本控制單位

[!include [banner](../../includes/banner.md)]

成本分攤規則用於指派在財務上已在集體成本中心計算的成本。 成本會計師確保根據選定的指派基礎將成本分配到成本中心。 將原則和相應的規則指派給成本控制單位。 本工作指南使用範例說明如何建立成本分攤原則和相應的規則。


## <a name="create-a-policy"></a>建立原則
1. 前往 [成本會計] > [原則] > [成本分配原則]。
2. 點選 [新增]。
3. 在 [原則名稱] 欄位中，輸入一個值。
4. 在 [描述] 欄位中，輸入一個值。
5. 在 [成本物件維度階層] 欄位中，輸入或選取一個值。
    * 選取 [組織]。  
6. 在 [成本元素維度階層] 欄位中，輸入或選取一個值。
    * 選取 [CDS P/L]。  
7. 在 [會計維度] 欄位中，輸入或選取一個值。
    * 選取 [統計元素]。  
8. 點選 [儲存]。

## <a name="create-rules-for-the-policy"></a>建立原則的規則
1. 點選 [新增]。
2. 在清單中，標示選取的列。
3. 在 [成本物件維度階層節點] 欄位中，輸入或選取一個值。
    * 展開階層以選擇 094。  
4. 在 [成本元素維度階層節點] 欄位中，輸入或選取一個值。
    * 選擇 [其他營運費用]，然後選擇 [605110 清潔]。  
5. 在 [成本行為] 欄位中，選取選項。
    * 選取 [固定成本]。  
6. 在 [分攤基礎] 欄位中，輸入或選取一個值。
7. 點選 [新增]。
8. 在清單中，標示選取的列。
9. 在 [成本物件維度階層節點] 欄位中，輸入或選取一個值。
    * 展開階層以選擇 094。  
10. 在 [成本元素維度階層節點] 欄位中，輸入或選取一個值。
    * 選擇 [其他營運費用]，然後選擇 [605150 租金]。  
11. 在 [成本行為] 欄位中，選取選項。
    * 選取 [固定成本]。  
12. 在 [分攤基礎] 欄位中，輸入或選取一個值。
13. 點選 [儲存]。

## <a name="assign-rules-to-a-cost-control-unit"></a>將規則指派給成本控制單位
1. 點選 [成本控制單位的原則指派]。
2. 點選 [新增]。
3. 在清單中，標示選取的列。
4. 在 [會計生效日期] 欄位中，輸入一個日期。
    * 在 [有效會計年度] 中選擇 [9 月 1 日]。  
5. 在 [成本控制單位] 欄位中，輸入或選取一個值。
6. 點選 [儲存]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]