---
title: 服務物件概觀
description: 本主題概述了如何使用服務物件。
author: kamaybac
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad758d32c6e9de0758c6fddb57a7dea886ab73d4
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449781"
---
# <a name="service-objects-overview"></a>服務物件概觀

[!include [banner](../includes/banner.md)]

服務物件就是您可為其提供服務的客戶資產與產品。 根據您提供的服務類型，物件可以是有形物件或無形物件：

-  有形物件是您可以對其執行實際服務工作的事物，例如機器或建築物。

    有形服務物件還可以是您在 [已發佈產品詳細資料] 表單中建立的庫存品項。 根據您附加到品項的庫存維度群組，您可以建立服務物件以包含品項序號的詳細資料等級。 當您必須追蹤服務物件所代表的確切品項時，這會很實用。

    有形服務物件還可以是與公司的直接生產或供應鏈不直接相關的品項。 例如，服務訂單中用於維修的工具包可以是不包括在庫存中的服務物件。 在這種情況下，您不會將其登記為庫存品項。

-  無形物件是對其執行服務工作的抽象事務，例如一組帳戶或法律文件。

## <a name="example-of-an-intangible-service-object"></a>無形服務物件的範例

A 公司負責維護多家小公司的財務記錄。 A 公司的客戶之一是當地的足球隊，A 公司為其每週記帳並每年稽核俱樂部的帳戶。 俱樂部的帳戶在服務物件表單中設定，並在服務合約中指定為物件。 該物件有兩個服務合約行。 第 1 行是具有指派給到行之每週間隔的每週記帳，第 2 行是具有指派到行之年度間隔的年度稽核。

## <a name="related-topics"></a>相關主題

[建立服務物件](create-service-objects.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]