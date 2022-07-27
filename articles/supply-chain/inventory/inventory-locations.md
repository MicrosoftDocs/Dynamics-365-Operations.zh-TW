---
title: 庫存位置
description: 庫存位置會與基本倉儲 (WMS I) 一起使用，以判斷在 WMS I 倉庫中項目的儲存位置以及揀貨位置。
author: yufeihuang
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSLocation, WMSBlockingCause, WHSLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c202a679e992c562772cbf6da6e17c4b8149760f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448674"
---
# <a name="inventory-locations"></a>庫存位置

[!include [banner](../includes/banner.md)]

庫存位置會與基本倉儲 (WMS I) 一起使用，以判斷在 WMS I 倉庫中項目的儲存位置以及揀貨位置。

本主題適用於庫存管理模組中的功能。 它不適用於倉庫管理模組中的功能。

位置一詞，是指品項進行儲存和提取的地方。

針對每個位置，我們也可以指定插入品項的地方。 預設情況下，它們都是相同的。 品項通常會從位置的同一側插入和提取，但有時候也不一定。 例如，儲存在即時儲存貨架中的品項，會從一個走道插入，並從另一個走道提取。 主要輸入由位置名稱提供，通常由其座標所決定：倉庫、走道、貨架、層架和間隔。 此名稱或識別碼可以手動輸入或從位置座標產生 - 例如，01-02-03-4 表示庫存位置頁面中的走道 1、貨架 2、層架 3、間隔 4。
位置屬性

位置具有以下特徵：
-   尺寸 (高度、寬度、深度以及體積)
-   倉庫、走道、貨架、層架和間隔位置
-   位置類型 (散裝位置、揀貨位置、入庫月台、出庫月台、生產輸入位置、檢驗位置或看板超市)

檢查文字可用於線上系統，以驗證操作員是否為特定品項選擇了正確的位置。 此檢查文字可以手動或依預設來建立。

## <a name="sort-codes"></a>排序代碼
使用排序代碼最佳化揀貨明細的處理，這些明細描述了從庫存中揀貨所需的資訊，包括揀貨訂單。 排序代碼可以由走道和其他座標指定，也可以依位置手動指派。

## <a name="blocked-locations"></a>已封鎖地點
有時候，您可能希望指示某個位置被封鎖一段時間，例如要進行維修的時候。 在其他時候，建議您指示僅封鎖輸入或僅封鎖輸出。

## <a name="tree-structure"></a>樹狀結構

在庫存位置頁面中，您可以根據庫存位置的座標，使用定義的顯示格式以樹狀結構查看倉庫配置。

## <a name="maintain-inventory-locations-via-the-warehouse-form"></a>透過倉庫表單維護庫存位置

位置可以從一個倉庫複製到另一個倉庫，並透過精靈建立位置。 在執行精靈之前，您應該確認您已在倉庫頁面上指定了預設位置名稱。



## <a name="additional-resources"></a>其他資源

[建立新的倉庫配置](tasks/create-new-warehouse-layout.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]