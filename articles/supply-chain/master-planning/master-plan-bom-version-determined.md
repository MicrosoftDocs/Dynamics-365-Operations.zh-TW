---
title: 確定 BOM 版本
description: 需求擴展期間，如果項目預設訂單類型為生產，則規劃引擎會根據位置尋找有效的 BOM 版本。
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 370091eed4ee050031d5d135aa7b1d8d0fe82491
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448362"
---
# <a name="determine-the-bom-version"></a>確定 BOM 版本

[!include [banner](../includes/banner.md)]

需求擴展期間，如果項目預設訂單類型為生產，則規劃引擎會根據位置尋找有效的 BOM 版本。 

位置維度是已知，並且於需求交易中說明。 下列程序用於確定要使用的 BOM 版本：

-   如果需求位置的項目已定義 BOM 版本，則會使用特定位置的 BOM。
-   如果需求位置的項目沒有定義特定位置的 BOM 版本，則會使用一般的 BOM。 一般的 BOM 不僅代表一個位置，而是對多個位置皆有效。 如果有一般 BOM，則會使用該 BOM。
-   如果沒有一般的 BOM 版本可使用，則需求擴展會在此時停止。

有效的 BOM 版本，無論是特定位置的還是一般的 BOM，都必須滿足日期和數量的條件。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]