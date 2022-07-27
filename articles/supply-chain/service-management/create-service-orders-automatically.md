---
title: 自動建立服務訂單
description: 您可為一個服務合約或多個服務合約建立服務訂單。
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
ms.openlocfilehash: 8fc63a720dd06c85be17ca61de1fe7c25f1cf3f7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448425"
---
# <a name="create-service-orders-automatically"></a>自動建立服務訂單    

[!include [banner](../includes/banner.md)]


您可為一個服務合約或多個服務合約建立服務訂單。 建立後，即可在 **服務訂單** 表單內檢視服務訂單。

所建立的服務訂單僅適用於服務合約的有效期限內。 **建立服務訂單** 表單內指定的時間區間若落在服務合約開始日期之前或結束日期之後，則所建立的服務訂單僅適用於服務合約日期範圍內的區間。

從服務合約明細手動或自動建立服務訂單時，該服務訂單的時間區間必須落在該明細訂定之開始與結束日期之間，除非該明細並未指定結束日期。

## <a name="create-service-orders-automatically-for-a-service-agreement"></a>在服務合約自動建立服務訂單

1.  按一下 **服務管理** \> **常用** \> **服務合約** \> **服務合約**。

2.  選擇服務合約。

3.  按一下 **交貨** 索引標籤，再按一下 **已規劃服務訂單**。

4.  於 **開始日期** 和 **結束日期** 欄位中指定日期，確定服務期間。

5.  選擇 **顯示資訊記錄** 核取方塊，顯示所建立的服務訂單清單。

6.  於 **包含的交易類型** 欄位群組中選擇交易類型。 交易類型可代表服務合約內建立的明細，而您所選擇的每個交易類型都會依據服務合約明細指定的服務期間，產生數個服務訂單。

7.  若要建立連續服務訂單內缺少的服務訂單，選擇 **連續** 核取方塊。

8.  按一下 **確定**。

## <a name="create-service-orders-automatically-for-several-service-agreements"></a>在數個服務合約自動建立服務訂單

1.  按一下 **服務管理** \> **定期** \> **服務訂單** \> **建立服務訂單**。

2.  按一下 **選擇**，即可選擇新增或移除建立服務訂單要使用的標準。

3.  按一下 **確定**。

## <a name="see-also"></a>另請參閱

[服務訂單](service-orders.md)

[自動建立服務訂單](auto-create-service-orders.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]