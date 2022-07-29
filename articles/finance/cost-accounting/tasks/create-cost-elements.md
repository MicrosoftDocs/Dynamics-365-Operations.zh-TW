---
title: 建立成本元素
description: 有幾種方法可以在成本會計中建立成本元素。
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba36e8d2c5b1fc1df6e63e5eef20c465cbd0b693086eece4079ae2216d2c156e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450657"
---
# <a name="create-cost-elements"></a>建立成本元素 

[!include [banner](../../includes/banner.md)]

有幾種方法可以在成本會計中建立成本元素。 此程序顯示如何透過資料連接器匯入主科目來建立成本元素。 建立此程序時使用 USMF 示範公司。 本程序是針對在 Dynamics 365 for Operations 版本 1611 新增的成本會計功能。


## <a name="create-new-cost-elements"></a>建立新成本元素
1. 前往成本會計 > 維度 > 成本元素維度。
2. 點選 [新增]。
3. 在名稱欄位中，輸入一個值。
4. 在 [維度成員的資料連接器] 欄位，輸入或選取一值。
5. 在 [描述] 欄位中，輸入一個值。
6. 點選 [儲存]。

## <a name="configure-the-data-connector"></a>設定資料連接器
1. 點選 [設定維度成員提供者]。
2. 在 [會計科目表] 欄位中，輸入或選取一個值。
    * 選取 [共用] 以使用共用的會計科目表。  
3. 點選 [新增]。
4. 在清單中，標示選取的列。
    * 您可以將篩選套用至科目以滿足您的條件。  
5. 在 [來原主科目] 欄位中，輸入或選取一個值。
6. 在 [目標主科目] 欄位中，輸入或選取一個值。
7. 點選 [確定]。

## <a name="import-main-accounts"></a>匯入主科目
1. 點選 [匯入維度成員]。
    * 主科目將匯入成本會計並做為成本元素。  
2. 點選 [確定]。

## <a name="view-the-imported-accounts-as-cost-elements"></a>將匯入的科目視為成本元素
1. 點選 [檢視維度成員]。
    * 將匯入的分類帳科目視為可流入業務中成本的成本元素。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]