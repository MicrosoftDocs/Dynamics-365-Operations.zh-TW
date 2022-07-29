---
title: 建立成本物件
description: 此程序顯示如何透過資料連接器將成本中心財務維度匯入成本會計來建立成本物件。
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0215e815e3e44568fb81ab7fad9b44c219e961cb6ef68996bf43218ef817e8d9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450675"
---
# <a name="create-cost-objects"></a>建立成本物件 

[!include [banner](../../includes/banner.md)]

此程序顯示如何透過資料連接器將成本中心財務維度匯入成本會計來建立成本物件。 建立此程序時使用 USMF 示範公司。 


## <a name="create-new-cost-objects"></a>建立新成本物件
1. 前往 [成本會計] > [維度] > [成本物件維度]。
2. 點選 [新增]。
3. 在名稱欄位中，輸入一個值。
4. 在 [維度成員的資料連接器] 欄位，輸入或選取一值。
5. 在 [描述] 欄位中，輸入一個值。
6. 點選 [儲存]。

## <a name="configure-the-data-connector"></a>設定資料連接器
1. 點選 [設定維度成員提供者]。
    * 選擇 CostCenter 以將 CostCenter 維度匯入成本會計。  
2. 在 [維度名稱] 欄位中，輸入 [成本中心]。
3. 點選 [確定]。

## <a name="import-cost-centers"></a>匯入成本中心
1. 點選 [匯入維度成員]。
2. 點選 [確定]。

## <a name="view-the-imported-cost-centers"></a>查看匯入的成本中心
1. 點選 [檢視維度成員]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]