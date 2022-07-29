---
title: 衍生帳簿
description: 本文將概述衍生帳簿功能。
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 32abfce013d0daa208138cf698b2abd1f96462f6
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451062"
---
# <a name="derived-books"></a>衍生帳簿

[!include [banner](../includes/banner.md)]

本文將概述衍生帳簿功能。

衍生帳簿的目的是簡化定期計劃的固定資產帳簿交易的過帳。  選擇一個帳簿做為主帳簿。 這通常是用於會計折舊的帳簿。 然後，隨後附加到作為主帳簿以相同的間隔設定來過帳交易的其他帳簿。 稅收折舊帳簿通常設定為衍生帳簿。 

設定以過帳到衍生帳簿的最常見交易是購置、購置調整和處置。 

## <a name="example"></a>範例

帳簿 B 和帳簿 C 設定為帳簿 A 的購置交易類型的衍生帳簿。 在帳簿 A 中，為資產 123 的購置交易輸入 1,500.00。 

過帳交易時，將在資產 123 中為帳簿 B 產生並過帳購置交易，並且在資產 123 中為 1,500.00 的帳簿 C 產生並過帳購置交易記錄。 在您準備該主帳簿的交易以用於在固定資產日記帳中過帳時，還可以查看和修改衍生帳簿的交易。 如果您在其他日記帳中準備主帳簿交易，則不會顯示衍生值的交易。 但是，當您過帳主要帳簿交易時，它們會過帳到適當的科目和過帳層。

> [!NOTE]                                                                                                                               
> 設定為按主帳簿間隔以外的間隔過帳交易的帳簿必須作為單獨的帳簿而不是衍生帳簿附加到固定資產。  

更多資訊，請參閱[使用衍生帳簿過帳](post-derived-value-models.md)。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
