---
title: 在倉庫內轉移實際庫存
description: 此程序將引導您完成建立和過帳庫存轉移日記帳的過程，以記錄項目從倉庫中的一個位置到另一個位置的移動。
author: yufeihuang
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf5a3711cfcd6e5a2ddce09af8569ea26c3502c8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449352"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>在倉庫內轉移實際庫存

[!include [banner](../../includes/banner.md)]

此程序將引導您完成建立和過帳庫存轉移日記帳的過程，以記錄項目從倉庫中的一個位置到另一個位置的移動。 在開始之前，您需要為庫存轉移設定庫存日記帳名稱。 您可以使用顯示的範例值在示範資料公司 USMF 中完成此程序，或者如果您設定了產品和位置，則可以使用您自己的資料。 這些工作通常由倉庫員工執行。


## <a name="create-an-inventory-transfer-journal"></a>建立庫存轉移日記帳
1. 在 **瀏覽窗格** 中，前往 **庫存管理 > 日記帳目錄 > 品項 > 轉移**。
2. 點選 **新增**。
3. 在 **名稱** 欄位中，輸入或選擇一個值。
4. 按一下 **確定**。 可以選擇為每個日記帳行指定「從」和「到」維度。 這些對於這種日記帳類型來說必不可少。 您可以使用不同的規則將品項轉移至各位置。 在此範例中，我們會在同一個倉庫中將物品從牌照控制的位置轉移到不受牌照控制的位置。   

## <a name="create-journal-lines"></a>建立日記帳明細
1. 在 **日記帳明細 fastTab** 中，點擊 **新增**。
2. 在 **項目號碼** 欄位中，輸入或選擇一個值。 如果您使用 USMF，則可以選取 'A0001'。  
3. 在 **出貨站點** 欄位中，輸入或選擇一個值。 如果您使用 USMF，則可以選取 '2'。  
4. 在 **出貨站點** 欄位中，輸入或選擇一個值。 如果您使用 USMF，則可以選取 '2'。  
5. 在 **出貨倉庫** 欄位中，輸入或選擇一個值。 如果您使用 USMF，則可以選取 '24'。  
6. 在 **收貨倉庫** 欄位中，輸入或選擇一個值。 如果您使用 USMF，則可以選取 '24'。  
7. 在 **出貨位置** 欄位中，輸入或選取一個值。 如果您使用 USMF，則可以選取 'FL-001'。  
8. 在 **收貨位置** 欄位中，輸入或選取一個值。 如果您使用 USMF，則可以選取 'BULK-001'。  
9. 在 **數量** 欄位中，輸入一個數字。
10. 在裡面 **行詳情** fastTab，點擊 **庫存維度** 索引標籤。
11. 在 **從庫存維度**，在 **牌照** 欄位中，輸入或選擇一個值。 如果您使用 USMF，則可以選取 '24'。  
12. 選取 **儲存**。

## <a name="post-the-inventory-transfer-journal"></a>張貼庫存轉移日記帳
1. 在 **動作窗格** 上，按一下 **過帳**。
2. 按一下 **確定**。

## <a name="view-inventory-transactions"></a>查看庫存交易
1. 按一下 **庫存**。
2. 按一下 **交易**。 在這裡，您可以查看日記帳過帳時建立的交易。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]