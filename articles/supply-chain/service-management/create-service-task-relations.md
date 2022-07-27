---
title: 建立服務工作關係
description: 您可將服務工作與服務合約或服務訂單建立關聯，藉此描述該合約或訂單應完成的服務工作。
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b13309816af6984e77f828e827ecffe6266b3ede
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448917"
---
# <a name="create-service-task-relations"></a>建立服務工作關係    

[!include [banner](../includes/banner.md)]

您可將服務工作與服務合約或服務訂單建立關聯，藉此描述該合約或訂單應完成的服務工作。 此資訊可供服務技術人員和客戶使用。

## <a name="create-a-relation-with-a-service-agreement"></a>與服務合約建立關係

1.  前往 **服務管理** \> **一般** \> **服務合約** \> **服務合約**。

2.  選擇現有服務合約或建立新的服務合約。

3.  在動作窗格中，選擇 **服務工作** 按鈕。

4.  在 **服務工作** 表單中，選擇 **新增** 來建立新的明細，然後從 **服務工作** 清單中選擇服務工作，將之附加到服務合約。

5.  在 **描述** 索引標籤中，於任意文字欄位輸入任何內部或外部附註描述。

6.  關閉表單以儲存記錄。

重複此程序，直到您為該服務合約建立所有必要的服務工作關係。 您現可在所有附加的合約明細指定這些服務工作。

服務合約附加的所有服務訂單皆可使用該服務合約上建立的服務工作關係。

## <a name="create-a-relation-with-a-service-order"></a>與服務訂單建立關係

1.  前往 **服務管理** \> **一般** \> **服務訂單** \> **服務訂單**。

2.  選擇現有服務訂單或建立新的服務訂單。

3.  在動作窗格中，選擇 **服務工作** 按鈕。

4.  在 **服務工作** 表單中，選擇 **新增** 來建立新的明細，然後從 **服務工作** 清單中選擇服務工作，將之附加到服務訂單。

5.  在 **描述** 索引標籤中，於任意文字欄位輸入任何內部或外部附註描述。

6.  關閉表單以儲存記錄。

重複此程序，直到您為該服務訂單建立所有必要的服務工作關係。 您現可選擇建立服務訂單明細時已建立關係的這些服務工作。

服務訂單上建立的服務工作關係僅供該特定服務訂單使用。

## <a name="see-also"></a>另請參閱

[服務工作概觀](service-tasks.md)


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]