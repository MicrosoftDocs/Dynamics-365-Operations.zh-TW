---
title: 合併服務訂單
description: 您可以合併服務訂單。
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
ms.openlocfilehash: 5df9571cb1330489651a28462b747cacd7ac7e46
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449310"
---
# <a name="combine-service-orders"></a>合併服務訂單   

[!include [banner](../includes/banner.md)]


當您在 **服務合約** 表單中自動建立服務訂單明細，您可以選擇以下任一選項來指定分組方式：

  - **按服務合約**

  - **按服務工作**

  - **按員工**

  - **按服務對象**

## <a name="example"></a>範例

請建立一份開始日期為 2007-31-03 的服務合約。 在 **合併服務訂單** 欄位，請指定 **按服務對象**。 接著建立以下服務合約明細：

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>合約明細編號</p></th>
<th><p>交易類型</p></th>
<th><p>描述</p></th>
<th><p>間隔</p></th>
<th><p>服務對象</p></th>
<th><p>開始日期</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p><strong>小時</strong></p></td>
<td><p>SAL1</p></td>
<td><p>每週</p></td>
<td><p>X-1</p></td>
<td><p>2007-04-01</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p><strong>小時</strong></p></td>
<td><p>SAL2</p></td>
<td><p>每雙週</p></td>
<td><p>X-2</p></td>
<td><p>2007-04-01</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p><strong>小時</strong></p></td>
<td><p>SAL3</p></td>
<td><p>每週</p></td>
<td><p>X-2</p></td>
<td><p>2007-04-01</p></td>
</tr>
</tbody>
</table>


您沒有為任何服務合約明細指定時間窗口。 因此，服務訂單明細不會從它們所在的計算日期移動。

接下來，您從 **建立服務訂單** 表單生成從 2007-04-01 到 2007-04-30 的服務訂單明細。

總共建立 10 份服務訂單。 因為您選取的合併設定是 **按服務對象**，建立的所有服務訂單其服務訂單明細都只有一個特定服務對象。 從此服務合約生成且具有相同服務日期和對象的服務訂單明細會合併到同一個服務訂單中。


> [!NOTE]
> <P>在此範例中，在<STRONG>服務管理參數</STRONG>表單中指定的日曆沒有休息天數。</P>



根據您在服務合約明細上指定的任何時間窗口，將服務訂單明細另外分組到服務訂單中。

## <a name="see-also"></a>另請參閱

[自動建立服務訂單](create-service-orders-automatically.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]