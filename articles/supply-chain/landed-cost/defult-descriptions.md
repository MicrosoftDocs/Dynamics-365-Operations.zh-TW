---
title: 總帳的預設描述
description: 預設描述可用於將憑證過帳中的說明欄位更新到總帳。
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 52e048e5a9271dfcd1d7b303d8ae8eae331296a3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449028"
---
# <a name="default-descriptions-for-the-general-ledger"></a>總帳的預設描述

[!include [banner](../../includes/banner.md)]

預設描述可用於將憑證過帳中的 **說明** 欄位更新到總帳。 此功能已得到增強，可與到岸成本一起使用。

若要設定分類帳過帳的預設描述，請前往 **組織管理 \> 設定 \> 預設描述**。

下表列出了已加入 **描述** 欄位 (位於 **預設描述** 頁面)，以支援到岸成本的新值。

| 描述類型 | 附註 |
|---|---|
| 進口成本核算 – 成本應計 | 過帳採購訂單發票時，會為估計航程成本處理應計成本。 可以指定預設描述，將航次編號添加到描述中。 採用 *%4* 為裝運編號。 |
| 進口成本核算 – 貨物在途訂單 | 如果您使用在途處理，則會過帳採購訂單發票，並將貨物過帳到在途貨物科目。 可以指定預設描述，將在途訂單號添加到描述中。 採用 *%4* 為在途訂單號。 |
| 庫存 – 關閉 – 調整 | 處理航次成本的應付帳款 (AP) 發票時，會處理庫存調整以估計航次成本。 可以指定預設描述，將航次編號添加到描述中。 採用 *%4* 為裝運編號。 |

如需關於如何使用 **預設描述** 頁面的詳細資訊，請參閱[設定自動發布的預設描述](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md)。
