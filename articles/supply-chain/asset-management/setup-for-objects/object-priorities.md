---
title: 資產服務層級
description: 本主題說明資產管理中的資產服務層級。
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e4f7daa10931ce406a5d2bdbbc1dced067e3de5065cdb61cce369d617709d67
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446724"
---
# <a name="asset-service-levels"></a>資產服務層級

[!include [banner](../../includes/banner.md)]

 

本主題說明資產管理中的資產服務層級。 資產服務層級與資產相關，已轉移到維護要求和工單。 它們用於在工單排程期間計算工單的優先順序。 如果需要變更，可以變更資產服務層級。

如需與工單排程評等分數相關的設定詳細資訊，請參閱[資產管理參數](../setup-for-objects/enterprise-asset-management-parameters.md)。 您必須為資產服務層級設定至少一個預設記錄。 如果在工單排程期間沒有找到其他符合項目，則使用此預設記錄。

**範例 1：** 如果沒有找到其他符合項目，則使用預設服務層級。 在此記錄中，您只選取一個服務層級。

**範例 2：** 用於排程 Volvo 卡車引擎作業的高服務層級。 在此記錄中，您選擇相關的資產類型 (例如 **卡車引擎**)、製造商 (**Volvo**) 和服務層級。

## <a name="set-up-asset-service-levels"></a>設定資產服務層級

1. 選取 **資產管理** \> **設定** \> **資產服務層級**。
2. 選取 **新增** 建立記錄。
3. 根據資產服務層級所需的詳細資料層級，在 **功能位置**、**資產類型**、**製造商**、**模型**、**資產**、**工單類型** 和 **服務層級** 欄位中進行相關選擇。

    > [!NOTE]
    > 當資產服務層級用於維護要求和工單時，資產管理會檢查所有資產服務層級記錄以檢查可能的符合項目。 一律先檢查最具體的組合。 換句話說，資產管理會先檢查 **工單類型** 欄位的符合項目。 如果沒有找到符合項目，它會檢查 **資產** 欄位的符合項目，依此類推。 正如您在 **資產服務層級** 頁面的配置中所見，此行為意味著為了找到最具體的組合，資產管理會從右到左檢查每條記錄以找出符合項目。 如果未找到符合項目，則會使用在這些欄位沒有選擇的預設記錄。

4. 在 **服務層級** 欄位中，選取一個表示服務層級 (優先順序) 的數字。


> [!NOTE]
> 如果您已先在工單上使用資產服務層級記錄，再變更 **資產服務層級** 頁面上的該記錄，則維護要求與工單上的服務層級不會相應更新。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]