---
title: 服務狀態和進度欄位互動
description: 在 [服務訂單] 表單中，標題上的 [進度] 欄位反映了整個服務訂單的狀態，而 [狀態] 報告各個服務訂單行的狀態。
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0758c370fd1548770d596115b18f133071f3bbc0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447882"
---
# <a name="service-status-and-progress-field-interaction"></a>服務狀態和進度欄位互動

[!include [banner](../includes/banner.md)]

在 **服務訂單** 表單中，服務訂單標題上的 **進度** 欄位反映了整個服務訂單的狀態，而 **狀態** 報告各個服務訂單行的狀態。

<table>
<colgroup>
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>進度</p></th>
<th><p>第 1 行狀態</p></th>
<th><p>第 2 行狀態</p></th>
<th><p>第 3 行狀態</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>處理中</strong></p></td>
<td><p><strong>已建立</strong></p></td>
<td><p><strong>已建立</strong></p></td>
<td><p><strong>已建立</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>處理中</strong></p></td>
<td><p><strong>已取消</strong></p></td>
<td><p><strong>已建立</strong></p></td>
<td><p><strong>已建立</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>處理中</strong></p></td>
<td><p><strong>已建立</strong></p></td>
<td><p><strong>已取消</strong></p></td>
<td><p><strong>已張貼</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>已取消</strong></p></td>
<td><p><strong>已取消</strong></p></td>
<td><p><strong>已取消</strong></p></td>
<td><p><strong>已取消</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>已張貼</strong></p></td>
<td><p><strong>已張貼</strong></p></td>
<td><p><strong>已張貼</strong></p></td>
<td><p><strong>已張貼</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>已張貼</strong></p></td>
<td><p><strong>已張貼</strong></p></td>
<td><p><strong>已取消</strong></p></td>
<td><p><strong>已取消</strong></p></td>
</tr>
</tbody>
</table>

如果所有行的狀態都為 **已建立**，則服務訂單的進度為處理中，如果某些行的狀態為 **已取消** 或 **已過帳**，則服務訂單的進度仍為處理中。

如果服務訂單中的所有行都標記為 **已過帳**，則訂單的進度狀態為 **已過帳**。 如果某些行的狀態為 **已過帳**，有些是 **已取消**，則進度仍為 **已過帳**。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
