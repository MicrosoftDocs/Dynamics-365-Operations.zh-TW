---
title: 為轉移訂單設定倉庫
description: 本主題介紹如何為轉移訂單設定倉庫。
author: Mirzaab
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation,CustVendTransportPoint2Point
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 6de9df2749836c68bc4e9f92a6934516ff9c1d469374f0d63173a209c841ba38
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447072"
---
# <a name="set-up-warehouses-for-transfer-orders"></a>為轉移訂單設定倉庫 

[!include [banner](../includes/banner.md)]

您可以使用倉庫級別建立支持倉庫之間轉移訂單的層次結構。 根據此設定，主計劃計算單一倉庫等級的物料需求，並從分配的源倉庫生成計劃的轉移訂單以履行它們。

1.  點擊 **庫存管理 > 設定 > 庫存明細 > 倉庫**。

2.  選取您要補貨的倉庫。

3.  在 **主要計劃** FastTa，選擇 **補貨** 核取方塊。

4.  在裡面 **主倉庫** 欄位中，選擇要分配為補貨倉庫的倉庫。 總排程會計算所選倉庫的轉移需求，並從分配的倉庫生成計劃轉移訂單 **主倉庫**。
   
    > [!NOTE]
    > <P>如果你清除<STRONG>補貨</STRONG>核取方塊，則所選倉庫會被分配到倉庫級別<STRONG>主倉庫</STRONG>，但是<STRONG>主倉庫</STRONG>不會設定為補貨倉庫。</P>

5.  關閉頁面以應用新設定。


> [!TIP]
> <P>如果要分配倉庫進行補貨，必須先將倉庫設定為倉庫維度<STRONG>儲存尺寸組</STRONG>頁面。 在此頁面上，選擇<STRONG>啟用</STRONG>欄位和<STRONG>依照尺寸劃分的覆蓋方案</STRONG>倉庫的欄位。</P>

## <a name="set-up-transport-lead-time"></a>設定運輸前置時間

您還必須設定倉庫之間的運輸前置時間 **運輸天數** 頁面。 
1. 前往 **庫存管理 > 設定 > 配送 > 運輸天數**。
2. 在 **接收點** 欄位中選擇 **倉庫**。
3. 選擇 **發貨倉庫**、**收貨倉庫** 和 **運輸天數**。 
4. (可選) 您也可以在 **每種運送方式的運輸天數** 索引標籤下，根據運送方式設定運輸時間。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]