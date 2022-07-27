---
title: 為到岸成本新增廠商設定
description: 本主題介紹啟用到岸成本模組時新增到現有廠商頁面的新欄位。 您可以使用這些欄位來設定將與到岸成本功能一起使用的廠商。
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: dc68cfd1afab808b1aa79fe4d0387cb6bb6c198f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448140"
---
# <a name="vendor-settings-added-for-landed-cost"></a>為到岸成本新增廠商設定

[!include [banner](../../includes/banner.md)]

啟用 **到岸成本** 模組時，幾個新欄位將新增到現有的 **廠商** 頁面。 您可以使用這些欄位來設定將與到岸成本功能一起使用的廠商。

若要設定相關欄位，請前往 **採購和資源開發 \> 廠商 \> 所有廠商**。 打開現有廠商或建立新廠商，然後選擇 **雜項詳細資料** FastTab。 所有 **到岸成本** 模組新增的新欄位都將出現在 **航程** 標題下。 下表說明這些欄位。

| 欄位 | 描述 |
|---|---|
| 裝運類型 | <p>選擇與到岸成本相關的廠商角色：</p><ul><li>**無** – 廠商沒有與到岸成本相關的特定角色。 此值是預設設定，因為大多數廠商可能沒有特定角色。</li><li>**裝運公司** – 廠商是裝運公司。 具有這種裝運類型的廠商可在 **航程** 頁面上的 **裝運公司** 欄位中選擇。</li><li>**報關行** – 廠商是報關行。 具有這種運輸類型的廠商可在 **對開** 頁面上的 **報關行** 欄位中選擇。</li><li>**代理人** – 廠商是代理人。 具有這種裝運類型的廠商可在 **廠商** 和 **訂購單** 頁面上的 **代理人** 欄位中選擇。</li></ul> |
| 成本類型群組 | 將廠商指派到成本類型群組，以選擇[自訂成本](auto-cost-setup.md)。 |
| 起點港口 | 選擇航程的始發港。 |
| 代理人 | 從廠商處進行採購時的預設代理人。 |
| 匯入成本計算廠商 | <p>指明廠商是否為到岸成本廠商。</p><p>**提示：** 您可以將此欄位與記錄級安全性結合使用，以限制建立航程時顯示的訂購單。</p> |
| 裝運公司 | 選擇為廠商建立訂購單時使用的預設裝運公司。 |
| 服務提供者 | 指明廠商是否為服務提供者。 |
| 超過/低於容差群組 | 為廠商選擇預設的超過/低於容差群組。 |
