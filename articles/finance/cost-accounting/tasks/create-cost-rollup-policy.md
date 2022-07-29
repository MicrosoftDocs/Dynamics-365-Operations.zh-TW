---
title: 建立成本彙總原則
description: 此程序說明如何建立成本彙總原則，並為該原則建立規則。
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd7a390ced7b7b4997d9c86b9218f1fa83ee14729e450e1ae1cb53dbbd605edb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450582"
---
# <a name="create-a-cost-rollup-policy"></a>建立成本彙總原則

[!include [banner](../../includes/banner.md)]

此程序說明如何建立成本彙總原則，並為該原則建立規則。 建立此流程的示範資料公司為 USP2。


## <a name="create-a-policy"></a>建立原則
1. 前往 [成本會計] > [原則] > [成本彙總原則]。
2. 點選 [新增]。
3. 在 [原則名稱] 欄位中，輸入一個值。
4. 在 [描述] 欄位中，輸入一個值。
5. 在 [成本物件維度階層] 欄位中，輸入或選取一個值。
    * 選擇 [成本彙總 CC]。  
6. 在 [成本元素維度階層] 欄位中，輸入或選取一個值。
    * 選擇 [成本彙總 CC]。  
7. 點選 [儲存]。

## <a name="create-rules-for-the-cost-rollup-policy"></a>為成本彙總原則建立規則
1. 點選 [新增]。
2. 在清單中，標示選取的列。
3. 在 [成本物件維度階層節點] 欄位中，輸入或選取一個值。
    * 選取 007。  
4. 在 [成本元素維度階層節點] 欄位中，輸入或選取一個值。
    * 選擇 [成本彙總 CE]。  
5. 在 [次要成本元素] 欄位中，輸入或選取一個值。
    * 對於此範例，將次要成本元素 CC-007 對應到成本中心。  
6. 點選 [新增]。
7. 在清單中，標示選取的列。
8. 在 [成本物件維度階層節點] 欄位中，輸入或選取一個值。
    * 選取 008。  
9. 在 [成本元素維度階層節點] 欄位中，輸入或選取一個值。
    * 選擇 [成本彙總 CE]。  
10. 在 [次要成本元素] 欄位中，輸入或選取一個值。
    * 對於此範例，將次要成本元素 CC-008 對應到成本中心。  
11. 點選 [新增]。
12. 在清單中，標示選取的列。
13. 在 [成本物件維度階層節點] 欄位中，輸入或選取一個值。
    * 選取 009。  
14. 在 [成本元素維度階層節點] 欄位中，輸入或選取一個值。
    * 選擇 [成本彙總 CE]。  
15. 在 [次要成本元素] 欄位中，輸入或選取一個值。
    * 對於此範例，將次要成本元素 CC-009 對應到成本中心。  
    * 繼續操作，直到所有成本中心都已對應到其相應的次級成本元素。  
16. 點選 [儲存]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]