---
title: 調整倉庫中的庫存量 (基本倉儲)
description: 此流程將引導您完成建立和過帳庫存調整日記帳，以調整倉庫中產品的庫存量。
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 02458d588c9925a1f4cb9afeada793dfc55a2071
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448659"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a>調整倉庫中的庫存量 (基本倉儲)

[!include [banner](../../includes/banner.md)]

此流程將引導您完成建立和過帳庫存調整日記帳，以調整倉庫中產品的庫存量。 在開始之前，您需要為庫存調整設定庫存日記帳名稱。 您能以示範資料公司 USMF 或自己的資料走完這段程序。 這些工作通常由倉庫員工執行。


## <a name="create-an-inventory-adjustment-journal"></a>建立庫存調整日記帳
1. 前往庫存管理 > 日記帳項目 > 品項 > 庫存調整。
2. 按一下「新增」。
3. 在名稱欄位中，按一下下拉式按鈕開啟查詢。
4. 在列表中，對您要使用的庫存調整日記帳，按一下名稱。
    * 其他部分欄位將根據您選擇的庫存調整日記帳名稱的設定進行填充。  
5. 按一下「確定」。

## <a name="create-journal-lines"></a>建立日記帳明細
1. 按一下「新增」。
2. 在列表中，標記項目編號欄位。
3. 在項目編號欄位中，選取該品項。 如果您使用的是示範資料公司 USMF， 輸入「D0001」。
4. 在站點欄位中，按一下下拉式按鈕開啟查詢。
5. 在清單中，選取站點。
6. 在倉庫欄位中，按一下下拉式按鈕開啟查詢。
7. 在清單中，選取倉庫。
    * 如果位置是選取品項的必填維度，則必須在此處指定位置。  
8. 在數量欄位中，輸入一個數字。
    * 成本價欄位指定庫存收據的單位成本。 如果品項編號沒有指定成本，或者如果您想手動更改它，可以在此處執行。  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a>驗證並過帳庫存調整日記帳
1. 按一下「驗證」。
2. 按一下「確定」。
3. 按一下「過帳」。
    * 當您過帳此類日記帳時，庫存收據或發票會過帳，改變庫存量和價值，並生成分類帳交易。  
4. 按一下「確定」。
5. 關閉表單。
6. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]