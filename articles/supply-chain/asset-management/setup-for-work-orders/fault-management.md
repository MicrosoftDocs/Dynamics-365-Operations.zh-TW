---
title: 故障管理
description: 本主題說明「資產管理」中的故障管理。
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetFaultArea, EntAssetFaultDesigner, EntAssetFaultCopyFromObjectType, EntAssetFaultRemedy, EntAssetObjectFaultRelationRequestInfoPart, EntAssetObjectFaultRelationWorkOrderInfoPart, EntAssetFaultCreateCombinations, EntAssetObjectFaultSymptom, EntAssetObjectFaultSymptomListPage, EntAssetFaultType, EntAssetFaultSymptom, EntAssetFaultCause
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 149d4fc8026a2a1878155d2b708cf3a79dd0e5af966db4e7f9339d8ca582da70
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446616"
---
# <a name="fault-management"></a>故障管理

[!include [banner](../../includes/banner.md)]

 

在「資產管理」中，您可以使用故障設計工具設定資產類型的故障徵兆、故障區域和故障類型。 這種方式讓您可以管理偵測到的資產故障。 此外，系統還會將故障原因和故障修復建議登錄在工單上。

故障登錄及管理程序包含下步驟。

1. 針對資產類型建立可能發生的故障徵兆、故障區域和故障類型清單。
2. 在故障設計工具中設定徵兆、故障區域和故障類型。

以下範例可協助您瞭解故障徵兆、故障區域和故障類型之間的區別。

**故障徵兆：**

- 電壓不平衡
- 短路
- 噪音
- 洩漏
- 振動

**故障區域：**

- 電路系統
- 機械結構
- 液壓系統
- 氣動系統

**錯誤類型：**

- 主要定子繞組故障
- 二極體故障
- 繞組髒污
- 發電機瑕疵
- 感應器瑕疵

## <a name="create-fault-symptoms"></a>建立故障徵兆

請按照以下步驟建立可用於故障設計工具的徵兆清單。

1. 選擇 **資產管理**\>**設定**\>**故障**\>**故障徵兆**。
2. 選取 **新增** 建立記錄。
3. 在 **故障徵兆** 欄位中，輸入故障徵兆的名稱。
4. 在 **描述** 欄位中，輸入描述。
5. 選擇 **儲存**。

## <a name="create-fault-areas"></a>建立故障區域

請按照以下步驟建立可用於故障設計工具的區域或位置清單。

1. 選擇 **資產管理**\>**設定**\>**故障**\>**故障區域**。
2. 選取 **新增** 建立記錄。
3. 在 **故障區域** 欄位中，輸入故障區域的名稱。
4. 在 **描述** 欄位中，輸入描述。
5. 選擇 **儲存**。

## <a name="create-fault-types"></a>建立故障類型

請按照以下步驟建立可用於故障設計工具的故障類型清單。

1. 選擇 **資產管理**\>**設定**\>**故障**\>**故障類型**。
2. 選取 **新增** 建立記錄。
3. 在 **故障類型** 欄位中，輸入故障類型的名稱。
4. 在 **描述** 欄位中，輸入描述。
5. 選擇 **儲存**。

## <a name="set-up-the-fault-designer"></a>設定故障設計工具

在故障設計工具中，您可以設定資產類型的故障資料。

1. 選擇 **資產管理**\>**設定**\>**故障**\>**故障設計工具**。
2. 在左側窗格中，選取要設定故障記錄的資產類型。
3. 在 **故障徵兆** FastTab 上選擇 **新增明細**，然後在 **故障徵兆** 欄位中選擇故障徵兆。
4. 在 **故障區域** FastTab 上選擇 **新增明細**，然後在 **故障區域** 欄位中選擇故障區域。
5. 在 **故障類型** FastTab 上選擇 **新增明細**，然後在 **故障類型** 欄位中選擇故障類型。
6. 若要為所選資產類型快速建立所有現有故障徵兆、區域和類型的組合，請選擇 **建立故障組合**。 如果您新增了許多故障徵兆、區域和類型，此功能很實用。 刪除與資產類型無關的組合明細，比手動建立新明細更容易。

    > [!NOTE]
    > 若要將某個資產類型的故障徵兆、區域和類型設定複製到所選資產類型，請選擇 **從資產類型複製**。

7. 選擇 **儲存** 以儲存您的變更。

![錯誤設計工具頁面。](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a>建立故障原因

請按照以下步驟，建立可加入工單或維修要求的已知故障原因清單。

1. 選擇 **資產管理**\>**設定**\>**故障**\>**故障原因**。
2. 選取 **新增** 建立記錄。
3. 在 **故障原因** 欄位中，輸入故障原因的名稱。
4. 在 **描述** 欄位中，輸入描述。
5. 選擇 **儲存**。

## <a name="create-fault-remedies"></a>設定故障補救措施

請按照以下步驟，建立可加入工單或維修要求的補救措施和修復建議清單。

1. 選擇 **資產管理**\>**設定**\>**故障**\>**故障補救措施**。
2. 選取 **新增** 建立記錄。
3. 在 **故障徵兆** 欄位中，輸入故障補救措施的名稱。
4. 在 **描述** 欄位中，輸入描述。
5. 選擇 **儲存**。

> [!NOTE]
> 您可以視需要變更故障徵兆、區域、類型、原因和補救措施的名稱。 名稱變更會自動反映在相關的故障登錄項目中。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]