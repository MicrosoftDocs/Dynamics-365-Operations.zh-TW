---
title: 通過檢查接受退回的品項
description: 通過檢查接受退回的品項。
author: kamaybac
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c800c18bbef17baa4b114c960da5ee0faec8a359
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449280"
---
# <a name="take-returned-items-through-inspection"></a>通過檢查接受退回的品項 

[!include [banner](../includes/banner.md)]


1.  點擊 **庫存管理** \> **定期** \> **品質管理** \> **檢疫訂單**。

2.  找到與您正在檢查的退回品項對應的訂單行。

    > [!NOTE]
    > <P>檢疫訂單只能與單一品項編號相關聯。 如果在單一運送中退回 10 件具有不同品項編號的品項並將其發送至檢疫，則會建立 10 個獨立的檢疫訂單。</P>

3.  檢查品項後，在 **處置代碼** 欄位選擇應如何處理該品項，以及如何處理相關的財務交易。 範例包括將品項退回庫存並向客戶退款、報廢品項並向客戶發送替代品，或在沒有信用額度的情況下將品項退回給客戶。
    
    > [!NOTE]
    > <P>如果單一品項編號批次中的多個退貨項目無法分配相同的處置代碼，則必須拆分檢疫訂單 (<STRONG>職能</STRONG> &gt; <STRONG>分裂</STRONG>) 為每個子批次分配不同的處置代碼。</P>


4.  完成檢查後，點擊 **報告完成** 釋出退回品項，並建立品項品項到貨日記帳目錄。 接收品項的人員或部門，然後要處理欲退回庫存品項的日記帳。
    
    -或-
    
    結束檢疫訂單，並使用其中一種 **庫存** 功能，直接將物品移回庫存。

5.  關閉表單以儲存變更。

## <a name="see-also"></a>另請參閱

[指定如何處置退回的品項](specify-how-to-dispose-of-returned-items.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]