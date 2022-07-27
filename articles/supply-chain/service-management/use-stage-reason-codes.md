---
title: 使用階段原因代碼
description: 使用原因代碼來表示取消服務等級協定 (SLA) 的原因，或服務訂單超過您在 SLA 中定義的時間限制的原因。
author: kamaybac
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac825fe96ee69491953bd50c758dde42744cea85
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448593"
---
# <a name="use-stage-reason-codes"></a>使用階段原因代碼 

[!include [banner](../includes/banner.md)]


使用原因代碼來表示取消服務等級協定 (SLA) 的原因，或服務訂單超過您在 SLA 中定義的時間限制的原因。

您還可以指定在取消 SLA 要求的原因代碼，或時間限制超過 SLA 中為服務訂單指定的時間時的原因代碼。

如果您已指定要求的原因代碼，則必須在以下情況下輸入原因代碼：

  - 當服務訂單移動到針對服務訂單 SLA 停止時間記錄的階段時。

  - 簽署服務訂單時。

  - 手動停止時間記錄時。

## <a name="set-up-reason-codes"></a>設定原因代碼

1.  點選 **服務管理** \> **設定** \> **服務訂單** \> **階段原因代碼**。

2.  在 **階段原因代碼** 表單中，點選 **新增** 以建立新的原因代碼。

3.  在 **階段原因代碼** 欄位，輸入唯一的階段原因代碼。

4.  在 **描述** 欄位中，輸入階段原因代碼的描述。

5.  關閉表單以儲存變更。

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a>取消服務等級協定時需要原因代碼

1.  點選 **服務管理** \> **設定** \> **服務管理參數**。

2.  在 **服務管理參數** 表單中，點選 **一般** 連結，然後選擇 **取消原因代碼** 核取方塊。

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a>當服務訂單超過服務等級協定設定的時間限制時需要原因代碼

1.  點選 **服務管理** \> **設定** \> **服務管理參數**。

2.  在 **服務管理參數** 表單中，點選 **一般** 連結，然後選擇 **超過時間的原因代碼** 核取方塊。

## <a name="see-also"></a>另請參閱

[服務訂單上的開始和停止時間記錄](start-and-stop-time-recording-on-a-service-order.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]