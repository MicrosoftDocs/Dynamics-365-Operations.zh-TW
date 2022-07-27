---
title: 為 RFQ 建立徵集類型和評分標準
description: 本指南說明如何建立徵集類型，並將之與評分方法建立關聯。
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d55b91def8b8edf8310cfa0bfe9d2bcc321ee6a6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448200"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a>為 RFQ 建立徵集類型和評分標準

[!include [banner](../../includes/banner.md)]

本指南說明如何建立徵集類型，並將之與評分方法建立關聯。 此外也會說明如何在詢價 (RFQ) 內使用徵集類型，並設定預設評分方法。 這些工作通常由採購經理執行。 您可用示範資料公司 USMF 或自己的資料來使用此程序。 開始前，您必須備妥評分方法。


## <a name="create-a-solicitation-type"></a>建立徵集類型
1. 移至採購和開源 > 設定 > 詢價 > 徵集類型。
2. 按一下新增。
3. 在名稱欄位中，輸入一個值。
4. 在 [描述] 欄位中輸入一個值。
5. 在評分方法欄位中，選擇此徵集類型要使用的評分方法。
6. 按一下儲存。
7. 關閉頁面。

## <a name="use-the-solicitation-type"></a>使用徵集類型
1. 移至採購和開源 > 詢價 > 所有詢價。
2. 按一下新增。
3. 在徵集類型欄位中，選擇您剛建立的徵集類型。 
    *   
4. 按一下確定。
5. 按一下評分標準。
    * 所顯示的評分標準係來自與該徵集類型相關聯的評分方法。 您可在此頁面中選擇新增或刪除標準。 您亦可從其他評分方法複製標準，藉此新增標準。  
6. 按一下複製標準。
7. 在評分方法欄位中，輸入或選擇一個值。
8. 按一下確定。
9. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]