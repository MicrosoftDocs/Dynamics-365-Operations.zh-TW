---
title: 攤銷製造品項的恆定成本
description: 製造品項的固定成本反映了作業設定時間以及具有固定數量或固定報廢量的組件。
author: AndersGirke
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: d9c539d525639ace6a139716e0644214364a060a2957ac97586cfad617e56ec0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446748"
---
# <a name="amortize-constant-costs-for-a-manufactured-item"></a>攤銷製造品項的恆定成本

[!include [banner](../includes/banner.md)]

製造品項的固定成本反映了作業設定時間以及具有固定數量或固定報廢量的組件。 

批量成本核算的概念用於在製造品項的計算成本中攤銷這些恆定成本。 這個概念有幾個同義詞，其中之一是批量會計。 攤銷恆定成本的概念也有幾個同義詞，其中之一是恆定比例成本。

將製造品項的批量成本核算中的數量使用到物料清單 (BOM) 計算。 數量取決於您如何啟動和執行 BOM 計算，如下所示：

-   品項 BOM 計算中的預設計算數量 − 品項的庫存標準訂單數量充當成本核算批量大小，但預設值可能是更大的數量以反映品項訂單數量的倍數。 品項的標準訂單數量和倍數可以在其預設訂單設定或站點專屬的訂單設定中定義。
-   品項 BOM 計算中的指定計算數量 - 指定的計算數量充當品項的成本核算批量大小。 計算數量最初使用品項的標準訂單數量，但可以手動覆寫預設值。 指定的計算數量表示指定品項的批量成本核算，以及具有生產 BOM 明細類型的製造組件其批量成本核算。 因為這假設組件將按精確數量生產。 具有品項 BOM 明細類型的其他製造組件，其批量成本核算將反映其標準訂單數量。
-   指定在品項 BOM 計算中的按訂單計算數量 - 當 BOM 計算使用按訂單展開模式時，指定的計算數量充當品項及其製造組件的批量成本核算。 這假設製造組件將按精確數量生產，就像具有生產 BOM 明細類型的製造組件一樣。
-   指定的計算數量為特定訂單的 BOM 計算 - 可以對銷售訂單、銷售報價單或服務訂單上的明細品項執行特定訂單的 BOM 計算。 指定的計算數量使用原始明細品項上的數量，但可以覆寫預設數量。 您可以選擇特定訂單的 BOM 計算是使用按訂單生產還是多層展開模式。

製造品項的攤銷恆定成本的計算金額稱為費用。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]