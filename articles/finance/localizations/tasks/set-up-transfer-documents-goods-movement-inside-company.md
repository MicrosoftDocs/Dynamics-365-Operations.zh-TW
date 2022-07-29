---
title: 設定公司內部貨物移動的轉移文件
description: 此過程顯示如何為公司內部的貨物移動設定轉移文件。
author: v-oloski
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventTransferOrders, InventLocationIdLookup, TransportationDocument, HcmWorkerLookUp, SrsReportViewerForm, InventTransferParmShip
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 80805bf30b4be753d7543ed4c6de30401d36e981
ms.sourcegitcommit: 2fba4f2ef7e513357366fc640befe0d2f7bc31f5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/05/2021
ms.locfileid: "8451041"
---
# <a name="set-up-the-transfer-documents-for-goods-movement-inside-a-company"></a>設定公司內部貨物移動的轉移文件

[!include [banner](../../includes/banner.md)]

此過程顯示如何為公司內部的貨物建立轉移文件。 此程序僅適用於主要地址在立陶宛的法人實體。 該程序是使用示範資料公司 DEMF 所建立的，該公司的主要地址位於立陶宛。 在您可以完成此程序之前，您必須完成「設定公司內部貨物移動的轉移文件」程序。 此程序供庫存會計所用。 此程序是 Dynamics 365 for Operations 版本 1611 中增加的功能。


## <a name="create-a-transfer-order"></a>建立轉移訂單
1. 前往庫存管理 > 入庫訂單 > 轉移訂單。
2. 按一下「新增」。
3. 在出貨倉儲欄位中，輸入或選擇一個值。
4. 在收貨倉儲欄位中，輸入或選擇一個值。
5. 按一下「新增」。
6. 在清單中，標示選取的列。
7. 在商品號碼欄位中，輸入或選擇一個值。

## <a name="enter-transportation-details-for-the-transfer-order"></a>輸入轉移訂單的運輸詳細資訊
1. 按一下「儲存」。
2. 在「動作窗格」上按一下「出貨」。
3. 按一下運輸詳細資訊。
4. 在列印運輸詳細資訊欄位中選擇「是」。
5. 在貨物核發人欄位中，輸入或選擇一個值。
6. 在封裝欄位中，輸入一個值。
7. 在負載欄位的風險級別中，輸入一個值。
8. 在承運方欄位中，輸入或選擇一個值。
9. 在型號輸入中，輸入或選擇一個值。
10. 在註冊碼欄位中，輸入一個值。
11. 在拖車註冊碼欄位中，輸入一個值。
12. 在駕駛欄位輸入中，輸入或選擇一個值。
13. 在駕駛名稱欄位中，輸入一個值。
14. 按一下「儲存」。
15. 關閉頁面。

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a>檢視未過帳轉移訂單的裝箱單
1. 按一下裝箱單。
2. 按一下「確定」。
3. 關閉頁面。

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a>檢視已過帳轉移訂單的裝箱單
1. 在「動作窗格」上按一下「轉移訂單」。
2. 在「動作窗格」上按一下「出貨」。
3. 按一下「出貨」轉移訂單。
4. 按一下「一般」索引標籤。
5. 在「更新」欄位中，選擇一個選項。
6. 按一下「概觀」索引標籤。
7. 在裝箱單欄位中，輸入一個值。
8. 點選確定。
9. 在「動作窗格」上按一下「出貨」。
10. 按一下裝箱單。
11. 點選確定。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
