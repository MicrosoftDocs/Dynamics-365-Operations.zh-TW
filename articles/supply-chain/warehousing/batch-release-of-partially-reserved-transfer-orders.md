---
title: 部分保留的轉移訂單批次發佈
description: 本主題說明如何從行動裝置設定並對部分保留轉移訂單套用批次發佈。
author: perlynne
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSFulfillmentPolicy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0fbe12b66da68bcd130fdb188eb0106b686200c3b59edc2af96b79f65022567a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447105"
---
# <a name="batch-release-of-partially-reserved-transfer-orders"></a>部分保留的轉移訂單批次發佈

[!include [banner](../includes/banner.md)]

部分保留轉移訂單的批次發佈功能讓您可以使用批次作業將轉移訂單部分發佈到倉庫。
因為您可以選擇發佈部分數量，所以您不必等待倉庫中的全部訂單數量備妥才發佈訂單。

將訂單發佈到倉庫是一個進階倉庫管理流程。 此過程涉及像是揀貨、包裝和運輸等活動，且倉庫工作人員可以使用行動裝置執行。

## <a name="where-it-applies"></a>適用處

有關此功能，使用批次作業將轉移訂單發佈到倉庫。 當您在倉庫中沒有足夠的庫存，但您仍希望將品項從一個倉庫轉移到另一個倉庫時，此功能很有用。

## <a name="how-it-is-set-up"></a>設定方式為何

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a>指定轉移訂單和銷售訂單的履行標準

在批次發佈部分訂單到倉庫之前，必須滿足履行標準。 這些履行標準由履行原則決定。

轉移訂單和銷售訂單的履行原則在公司層級指定。 將根據履行原則設定，接受或拒絕批次發佈訂單。 相應地處理訂單。

-   要為轉移訂單和銷售訂單建立履行原則，請按一下 **倉庫管理**\>**設定**\>**發佈到倉庫**\>**履行原則**，然後輸入名稱和說明來建立履行原則。

-   要指定履行率、值類型以及違反履行原則時顯示的訊息，請按一下 **倉庫管理**\>**設定**\>**發佈到倉庫**\>**履行原則**，然後設定 **履行率**、**值類型**，及 **履行違規訊息** 欄位。

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a>設定轉移訂單和銷售訂單的履行原則

-   若要設定轉移訂單的履行原則，請按一下 **庫存管理**\>**設定**\>**庫存和倉庫管理參數**\>**轉移訂單**\>**倉庫管理**，然後選取轉移訂單履行原則。

-   若要設定銷售訂單的履行原則，請按一下 **應收賬款**\>**設定**\>**應收賬款參數**\>**倉庫管理**，然後選擇銷售訂單履行原則

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-release-in-a-batch"></a>允許批次發佈並指定應批次發佈的數量

批次作業用於批次發佈訂單到倉庫。 對於應在批次作業中執行的訂單，在批次作業本身上設定區分這些訂單的參數。

**數量** 參數指定是否應在批次中發佈全部數量或實際保留數量。 **允許發佈部分發佈訂單** 參數確定，如果批次中的訂單之前被部分發佈，是否應被接受或拒絕。

-   若要對轉移訂單設定 **數量** 和 **允許發佈部分發佈的訂單** 參數，按一下 **倉庫管理**\>**發佈到倉庫**\>**自動發佈轉移訂單**。

-   若要對銷售訂單設定 **數量** 和 **允許發佈部分發佈的訂單** 參數，按一下 **倉庫管理**\>**發佈到倉庫**\>**自動發佈銷售訂單**。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]