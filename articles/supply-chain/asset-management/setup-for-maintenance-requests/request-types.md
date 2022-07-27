---
title: 維護要求類型
description: 本主題說明如何在「資產管理」中設定維護要求類型。
author: johanhoffmann
ms.date: 07/26/2019
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
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f51c90f72120d236ae9acf3fbcb8ac98fdc8cdf3d3bd032b3a3a3d317483b070
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446697"
---
# <a name="maintenance-request-types"></a>維護要求類型

[!include [banner](../../includes/banner.md)]

 

維護請求類型用於分類維護要求。 例如，您可能有與預防性維護和矯正性維護相關的維護要求類型。 或者，您可能有用於管理資產維修 (倉庫維修) 的特殊維護要求類型。

維護要求類型定義與維護要求生命週期狀態群組 (維護生命週期模型) 之間的關係。 維護要求生命週期模型定義可為維護要求設定的生命週期狀態。 (維護要求生命週期狀態的範例包括 **已建立**、**使用中** 和 **已結束**。)

1. 選取 **資產管理** \> **設定**\> **維護要求** \> **維護要求類型**。
2. 選取 **新增** 建立維護要求類型。
3. 在 **維護要求類型** 欄位中，輸入維護要求類型的識別碼。
4. 在 **名稱** 欄位中，輸入名稱。
5. 在 **一般** FastTab 上的 **維護要求生命週期模型** 欄位中，選擇維護要求生命週期模型。
6. 在 **工單類型** 欄位中，選取工單類型。 當維護要求轉換為工單後，工單會自動取得與維護要求類型相關的工作訂單類型。

下圖顯示 **維護要求類型** 頁面。

![維護要求類型頁面。](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]