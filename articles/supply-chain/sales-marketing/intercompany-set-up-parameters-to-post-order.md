---
title: 設定發佈公司間訂單的參數
description: 本主題說明如何設定發佈公司間訂單的參數
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c728f2f491948ae1c8550396ba4d72f76f46fe85
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447738"
---
# <a name="set-up-parameters-to-post-an-intercompany-order"></a>設定發佈公司間訂單的參數

[!include [banner](../../includes/banner.md)]

當發佈公司間客戶發票時，您可以設定自動發佈公司間訂購訂單和原始客戶發票。

> [!NOTE]
> 執行此流程之前，請在組織中設定列印管理，以指向正確的發票印表機。 這有助於確保原始銷售訂單的發票，會由正確的印表機列印。

您必須設定下列參數：

1. 前往 **銷售和行銷\>銷售訂單\>所有銷售訂單**。 選擇您要使用的銷售訂單。
1. 在銷售訂單的動作窗格上，選擇 **標題檢視** 然後選擇並開啟 **公司間設定** FastTab。
1. 前往動作窗格，在 **銷售訂單** 索引標籤上，選擇 **編輯**。
1. 返回 **公司間設定** FastTab，並選擇 **直接交貨**，以在整個公司間鏈結 (所有訂單) 中啟用直接交貨。
1. 選擇 **儲存**，以儲存銷售訂單的新設定。 然後選擇 **關閉**，以關閉銷售訂單。
1. 前往 **採購和委外 \> 廠商 \> 所有廠商**。 在 **一般** 索引標籤上，選擇 **公司間**。
1. 在 **公司間** 頁面上，選擇 **訂購單原則** 連結。 在 **公司間訂購單 (直接交貨)** 欄位群組，選擇 **自動發佈發票**，並移除 **自動列印發票** 欄位的選取標記。
1. 在 **原始銷售訂單 (直接交貨)** 欄位群組，選擇 **自動發佈發票**，並選擇 **自動列印發票** 欄位。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
