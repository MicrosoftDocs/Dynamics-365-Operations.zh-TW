---
title: 定義資源能力
description: 資源能力描述了營運資源可以做什麼。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42451da0bd465ce3a18ecf18570f3331847474c1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449178"
---
# <a name="define-resource-capabilities"></a>定義資源能力

[!include [banner](../../includes/banner.md)]

資源能力描述了營運資源可以做什麼。 在調度期間，每個作業和操作的要求與可用資源的能力相符合。 本任務指南將協助您建立資源能力並將指派給資源。 用於創建此工作的示範資料公司是 USMF。


## <a name="create-a-resource-capability"></a>建立資源能力
1. 前往資源功能。
2. 按一下新增。
3. 在功能欄位能中，輸入資源功能的 ID。
    * 對於給定的操作，您可以使用功能 ID 指定資源必須具有此功能才能執行操作。  
4. 在描述欄位中輸入功能的描述。

## <a name="assign-capability-to-a-resource"></a>將功能指派給資源
1. 按一下新增。
2. 在資源字段中，輸入資源的 ID。
    * 資源功能可以指派給一個或多個資源。  
3. 在到期欄位中輸入日期。
    * 您可以使用此欄位指定資源僅在有限時間內具有功能。  
4. 在優先順序欄位中輸入一個數字。
    * 當您計劃作業和操作時，您可以指定是否按優先順序選擇資源。 如果您選擇執行此操作，並且多個資源可以在請求的日期之前執行作業或操作，則選擇相對於所需功能具有最低優先順序的資源。  
5. 在等級欄位中輸入一個數字。
    * 當您指定作業或操作需要特定功能時，您還可以指定所需的最低等級。 使用功能等級來區分可以執行相同作業，但速度、強度、大小等不同的資源。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]