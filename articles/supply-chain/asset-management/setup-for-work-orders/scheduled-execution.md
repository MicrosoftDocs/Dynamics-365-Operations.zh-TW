---
title: 已排程執行
description: 本主題介紹資產管理中的已排程執行。
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4ace2da2c4bc3d5cc404301fc4ecef5ceeef240dae6569a4d28f621b02637930
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447312"
---
# <a name="scheduled-execution"></a>已排程執行

[!include [banner](../../includes/banner.md)]

 

可使用工單服務等級來設定已排程執行。 (有關工單服務等級的更多資訊，請參閱[服務等級和描述](service-level-and-description.md)。) 已排程執行為維護工人的工作計劃提供了靈活性，因為您可以為應在其中完成工單的時間間隔設定更詳細或大致的要求。 例如，能讓一個生產設施中完成作業速度比預計快的維護工人繼續處理附近另一個安排在本週，但不一定當天執行的作業。 這種方法可以最佳化工人規劃和工作完成。

與工單相關的已排程執行設定可以是通用，也可以是特定的。 可設定不限於特定工單類型、資產類型等的通用行。 或者，您可以建立適用於特定工作訂單類型、資產類型、維護作業類型等的已排程執行行。

1. 選擇 **資產管理** \> **設定** \> **工作訂單** \> **已排程執行**。
2. 選取 **新增** 以建立已排程執行行。
3. 在 **功能位置**、**工單類型**、**資產類型**、**製造商**、**型號**、**維護作業類型類別**、**維護工作類型**、**維護作業類型變體** 和 **交易** 欄位中，根據需要選擇值。
4. 在 **服務等級** 欄位選擇工單服務等級。 如果將此欄位保留空白，則會建立最通用的已排程執行行類型。 有關通用行的範例，請參見下圖中的第一個記錄。 該行啟用未為其安排特定日期和時間的工單服務等級的所有工單。
5. 在 **已排程執行** 欄位中，選擇時間間隔。
6. 選取 **儲存**。

![已排程執行。](media/20-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]