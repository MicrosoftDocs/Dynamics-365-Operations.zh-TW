---
title: 建立銷售訂單發票
description: 本主題介紹如何為銷售訂單開立發票，包括合併發票和批次處理。
author: ShivamPandey-msft
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b6712779ca64f5934edd37730597541679b86e43
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2021
ms.locfileid: "8450921"
---
# <a name="create-sales-order-invoices"></a>建立銷售訂單發票

[!include [banner](../../includes/banner.md)]

本主題介紹如何為銷售訂單開立發票，包括合併發票和批次處理。 此程序使用的是 USMF 示範公司。


## <a name="create-an-invoice-from-a-sales-order"></a>從銷售訂單建立發票
1. 前往 **瀏覽窗格 > 模組 > 應收帳款 > 訂單 > 已裝運但未開立發票的銷售訂單**。
2. 在清單中選擇一個銷售訂單。 
3. 在 **動作窗格** 上，點選 **發票 > 產生 > 發票**。 請注意，此銷售訂單有多個與其關聯的裝箱單。 它只會顯示 *多個* 字詞，而不會顯示裝箱單編號。  
4. 展開 **參數** 區段。
    - 過帳必須設定為 [是] 才能過帳發票。 您也可以關閉過帳並僅列印發票。 但是，您可以透過建立形式發票代替發票，其效果相同。  
    - 此選項用於批次作業。 執行批次作業時執行查詢。
5. 在 **列印** 欄位中，選取 [之後]。
6. 在 **列印發票** 選擇 **是**。 列印管理可以列印多份發票，也可以透過電子郵件將發票作為 PDF 文件發送。  
7. 在 **列印費用** 欄位中，選取 [彙總]。
8. 在 **檢查信用額度** 欄位，選擇 [餘額]。
9. 點選 **取消**。

## <a name="combine-orders-into-a-single-invoice"></a>將訂單合併為一張發票
1. 前往 **瀏覽窗格 > 模組 > 應收帳款 > 訂單 > 所有銷售訂單**。
2. 選擇有多個未結發票的客戶。
3. 選擇來自同一客戶的多個未結銷售訂單。
4. 在 **動作窗格** 上，點選 **發票 > 產生 > 發票**。
5. 展開 **參數** 區段。
6. 在 **數量** 欄位中，選取 [全部]。 請注意，概觀區段列出了兩張發票。 現在讓我們將它們合併到一張發票中。  
7. 在 **摘要更新** 欄位中，選取 [發票帳戶]。
8. 點選 **整理** 將銷售訂單合併為一張發票。 兩張銷售訂單現在合併為一張發票。   
9. 點選 **取消**。
10. 點選 **是**。

## <a name="post-invoices-in-a-batch"></a>以批次過帳發票
1. 前往 **瀏覽窗格 > 模組 > 應收帳款 > 發票 > 批次開立發票 > 發票**。
2. 點選 **選取**。
3. 點選 **確定**。
4. 點選 **批次**。
5. 請在 **批次處理** 中選取 **是**。
6. 點選 **重複執行**。
7. 選擇 **天數**。
8. 點選 **確定**。
9. 點選 **確定**。
10. 點選 **取消**。
11. 點選 **是**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
