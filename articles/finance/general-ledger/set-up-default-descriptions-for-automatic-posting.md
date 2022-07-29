---
title: 設定自動過帳的預設說明
description: 本主題介紹如何設定用於說明自動過帳到總帳的會計分錄之預設文字。 您可以透過使用任意形式的文字或選擇固定變量來設定預設說明文字。
author: aprilolson
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 89ea19753abdc4e5d4219a123a832bb3606515a43b439d5f94a9619857b6c7d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450210"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a>設定自動過帳的預設說明

[!include [banner](../includes/banner.md)]

本主題介紹如何設定用於說明自動過帳到總帳的會計分錄之預設文字。 您可以透過使用任意形式的文字或選擇固定變量來設定預設說明文字。

> [!NOTE]
> 對於某些國家或地區的某些交易類型，您還可以在 Microsoft Dynamics AX 資料庫中加入與這些交易類型相關的欄位文字。 有關交易類型以及國家和地區的清單，請參閱本主題後段的[選擇性：在預設說明加入其他文字](#optional-add-other-text-to-default-descriptions)部分。

## <a name="set-up-default-descriptions"></a>設定預設說明

1. 前往 **組織管理** \> **設定** \> **預設說明**。
2. 在動作窗格上，選擇 **新建**。
3. 在 **說明** 欄位中，選擇要為其建立預設說明的交易類型。
4. 在 **語言** 欄位中，選擇套用至說明的語言。
5. 在 **文字** 欄位中，輸入預設說明。 您可以在欄位中輸入文字，也可以使用以下一個或多個任意文字變量：

    - **%1** – 加入交易日期。
    - **%2** – 加入對應於正在過帳到總帳的單據類型識別碼。 例如，對於與發票相關的交易類型，**%2** 變量加入發票編號。
    - **%3** – 加入與正在過帳到總帳的單據類型相關的識別碼。 例如，對於與發票相關的交易類型，**%3** 變量加入客戶帳號。

## <a name="optional-add-other-text-to-default-descriptions"></a>選擇性：在預設說明加入其他文字

對於某些國家或地區的某些交易類型，預設說明可以在您的資料中加入來自與這些交易類型相關的欄位文字。 以下清單顯示可以使用此選項的交易類型以及國家和地區。

**交易類型**

您可以將其他文字加到與以下單據類型相關的交易預設說明中：

- 客戶發票
- 客戶貸方票據
- 客戶現金支付
- 廠商付款
- 銷售訂單
- 訂購單
- 庫存日記帳
- 主計劃 (MRP)
- 固定資產

**國家和地區**

此選項適用於以下國家和地區：

- 巴西
- 中國
- 捷克共和國
- 東歐
- 匈牙利
- 印度
- 日本
- 立陶宛
- 拉脫維亞
- 波蘭
- 俄羅斯

### <a name="add-text-to-default-descriptions"></a>在預設說明加入文字

完成本主題前部的[設定預設說明](#set-up-default-descriptions)部分的步驟後，請執行以下步驟，在預設說明中加入其他文字。

1. 在 **參數** FastTab，選擇 **新增**。
2. 在 **參考資料表** 欄位中，選擇要從哪個資料庫資料表將參數資料加到說明中。
3. 在 **參考欄位** 欄位中，選擇要從哪個欄位將參數資料加到說明中。
4. 重複步驟 1 到 3，以加入更多參數。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]