---
title: 服務物件關係
description: 您可以在服務物件和服務合約或服務訂單之間建立服務物件關係。
author: kamaybac
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7eb5b185ca2ef5903eb1739edfdd7b60749babd4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448899"
---
# <a name="service-object-relations"></a>服務物件關係 

[!include [banner](../includes/banner.md)]

您可以在服務物件和服務合約或服務訂單之間建立服務物件關係。 建立關係時，將服務物件附加到服務合約或服務訂單。

建立關係後，可將服務物件附加到服務合約或服務訂單上的任何行。

## <a name="template-boms"></a>範本 BOM

您還可以為物件關係指定範本 BOM。 範本 BOM 是您對其執行服務之物件的物料清單。 如果您在登門服務期間更換服務物件的組成部分，您可以使用 [服務物件] 表單在服務 BOM 中登記此變更。

## <a name="example"></a>範例

您為客戶站點兩部電梯提供的服務建立了一份服務合約。
服務合約具有識別碼 SAL-001。

電梯在 [服務物件] 表單中設定為 EL-S/1000 物件和 EL-L/1000 物件。

將服務物件 EL-S/1000 和 EL-L/1000 附加到服務合約中。

您想要在 BOM 中登記服務物件的變更，因為您更換了該物件的組件零件; 因此，您將服務 BOM 附加到該服務對象關係，如下表中所述。

| 服務物件 | 關係 - 服務合約 | 服務 BOM   |
|----------------|------------------------------|---------------|
| EL-S/1000      | ID SAL-001                   | BOM-EL-S/1000 |
| EL-L/1000      | ID SAL-001                   | BOM-EL-L/1000 |

由於合約存在服務物件關係，所以您現在可以建立服務合約行，行中具有下表中顯示的這些物件。

| 交易類型 | 類別           | 服務物件 |
|------------------|--------------------|----------------|
| 小時             | 檢查         | EL-S/1000      |
| 小時             | 齒輪箱清洗  | EL-S/1000      |
| 項目             | 清潔材料 | EL-S/1000      |
| 小時             | 檢查         | EL-L/1000      |
| 小時             | 變速箱清洗   | EL-L/1000      |
| 項目             | 清潔材料 | EL-L/1000      |

在登門服務中，您必須更換電梯 EL-S/1000 的變速箱。 若要更換物件的零件，您可以使用為目前服務合約設定的服務物件關係存取 BOM 設計工具。

使用服務物件關係存取 BOM 設計工具

1. 服務合約
2. 按兩下服務合約，或點選服務合約以建立服務合約。
3. 點選 [設定] 索引標籤。
4. 點選服務物件以將範本 BOM 附加到服務合約。
5. 在服務物件表單中，點選設計工具以打開設計工具表單以修改範本 BOM。

## <a name="automatically-created-service-orders"></a>自動建立服務訂單

如果您自動建立服務合約的服務訂單，則合約中的服務物件關係也會在服務訂單中建立。



[!INCLUDE[footer-include](../../includes/footer-banner.md)]