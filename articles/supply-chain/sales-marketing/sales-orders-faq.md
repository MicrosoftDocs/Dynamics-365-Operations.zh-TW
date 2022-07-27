---
title: 銷售訂單常見問題集
description: 此頁面說明在 Dynamics 365 Supply Chain Management 中處理銷售訂單時遇到的常見問題。
author: Henrikan
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 3cee75b1d740e7cb414c674157dde0146e8faa50
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448437"
---
# <a name="sales-order-faqs"></a>銷售訂單常見問題集

此頁面說明在 Dynamics 365 Supply Chain Management 中處理銷售訂單時遇到的常見問題。

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>我可以將訂購單連結到銷售訂單來滿足需求嗎？

您可以從銷售訂單建立訂購單。 有關詳細資訊，請參閱[從銷售訂單建立訂購單](/dynamics365/supply-chain/sales-marketing/tasks/create-purchase-order-sales-order)。

## <a name="can-i-cancel-or-delete-a-sales-order-or-return-order"></a>我可以取消或刪除銷售訂單或退貨單嗎？

您只能取消處於 *已建立* 狀態的銷售訂單和退貨單。 有關詳細資訊，請參閱[取消退貨單](/dynamics365/supply-chain/service-management/cancel-return-order)。

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>我可以還原刪除的已開立發票的銷售訂單嗎？

如果誤刪了已開立發票的銷售訂單，您可以還原它或查看其詳細資料。

移至 **客戶帳戶 \> 交易 \> 原始文件 \> 查看詳細資料**。 找到您要尋找的發票，並選取它以查看其詳細資料。 這些詳細資料包括銷售訂單參考。 您還應該能從該頁面存取銷售訂單詳細資料。

## <a name="how-do-i-delete-orphaned-sales-order-records"></a>如何刪除孤立的銷售訂單記錄？

若要清理孤立的銷售訂單記錄，請移至以下任一位置執行 *銷售訂單刪除* 定期作業：

- 銷售和行銷 \> 定期工作 \> 清理 \> 刪除銷售訂單
- 零售和商業 \> 零售和商業 IT \> 清理 \> 刪除銷售訂單

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>是否有辦法計算已經過帳的發票上的佣金？

Supply Chain Management 目前不支援計算已過帳發票上的佣金。
