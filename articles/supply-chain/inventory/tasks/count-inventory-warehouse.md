---
title: 在倉庫中計算庫存
description: 本主題說明建立和過帳庫存計數日記帳，以計算倉庫中某個位置的特定項目過程。
author: yufeihuang
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b7dd3788d3cbf80bfba373f5b6ce9d2e0ca0c07
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449109"
---
# <a name="count-inventory-in-a-warehouse"></a>在倉庫中計算庫存

[!include [banner](../../includes/banner.md)]

本主題說明建立和過帳庫存計數日記帳，以計算倉庫中某個位置的特定項目過程。 該過程適用於庫存管理模組中可使用的「基本倉儲」功能，而不適用於倉庫管理模組中可用的倉儲功能。 您能以示範資料公司 USMF 或自己的資料走完這段程序。 如果您在使用自己的資料，請確認您已設定產品和位置，並已建立庫存日記帳名稱，以用於清點日記帳。 庫存清點通常由倉庫員工進行。


## <a name="create-an-inventory-counting-journal"></a>建立庫存清點日記帳
1. 前往 **導覽窗格 > 模組 > 庫存管理 > 日記帳項目 > 項目清點 > 盤點**。
2. 選擇 **新建**。
3. 在 **名稱** 欄位中，從下拉式清單中選擇要使用的庫存清點日記帳名稱。 其他部分欄位將根據您選擇的庫存清點日記帳名稱的設定進行填充。  
4. 在 **背景工作角色** 欄位中，選擇下拉式按鈕開啟查詢。
5. 在清單中，**選擇** 您想使用的背景工作角色。
6. 選取 **確定**。

## <a name="create-journal-lines"></a>建立日記帳明細
1. 選擇 **新建**。
2. 在 **品項編號** 欄位中，在下拉式清單中選擇所需的記錄。 如果您使用的是示範資料公司 USMF，請選擇 **A0001**。  
3. 在 **站點** 欄位中，在下拉式清單中選擇所需的記錄。 如果您使用的是示範資料公司 USMF，請選擇站點 **2**。
4. 在 **倉庫** 欄位中，在下拉式清單中選擇所需的記錄。 如果您使用的是示範資料公司 USMF，請選擇倉庫 **24**。  
5. 在 **位置** 欄位中，在下拉式清單中選擇所需的記錄。 如果您使用的是示範資料公司 USMF，請選擇位置 **BULK-001**。  
6. 在已清點欄位中輸入一個數字。 如果您輸入的清點數字與 **現有** 欄位中顯示的數字不同，**數量** 欄位將更新以顯示差異。  
7. 選取 **儲存**。

## <a name="post-the-inventory-counting-journal"></a>張貼庫存清點日記帳
1. 選擇 **張貼**。 當您張貼庫存清點日記帳時，如果清點金額與在 **現有** 欄位中報告的金額不同，則會張貼庫存收貨或發貨，庫存等級和值會變更，並且會產生分類帳交易記錄。
2. 選取 **確定**。

## <a name="view-inventory-transactions"></a>查看庫存交易
1. 選擇 **庫存**。
2. 選擇 **交易**。 在這裡，您可以看到張貼庫存清點日記帳時將建立的任何相關交易。   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]