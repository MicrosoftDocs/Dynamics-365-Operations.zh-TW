---
title: 廠商加值稅登記日期
description: 本主題提供有關啟用供應商增值稅登記日期的功能的
author: anasyash
ms.date: 01/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: global
ms.author: anasyash
ms.search.validFrom: 2022-01-15
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: 882d5a8718d819cff80bfa5b86e054a39e9db159
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451401"
---
# <a name="date-of-vendor-vat-register"></a>廠商加值稅登記日期

在 Microsoft Dynamics 365 Finance 版本 10.0.24 中，新的 **供應商增值稅登記日期** 欄位可用於供應商發票。 此欄位指定採購的應稅供應日期。

若要啟用新欄位，請前往 **功能管理** 工作區，找到並選擇在供應商發票上 **啟用供應商增值稅登記日期** 功能，然後選擇 **立即啟用**。

供應商的進貨發票可以有兩個日期：供應商開具發票的日期和應稅供應的日期 (即供應商收取應交增值稅 [VAT] 的日期)。 在某些情況下，這兩個日期可能不同。

您可以扣除採購發票的進項增值稅金額，並稍後將該發票包含在增值稅報告中，日期與前面提到的兩個日期都不同。 此日期受當地法律規定關於在某些情況下推遲抵扣增值稅的規定。 這會因國家/地區而異。

一些增值稅報告，例如捷克共和國的 [VAT 控制聲明報告](emea-cze-vat-declaration-tax-declaration-model.md#vat-control-statement)，要求應稅供應的日期報告購買文件。 必須報告此日期，以便稅務機關可以協調交易對手之間的增值稅報告。

在 Finance 中，您可以在以下字段中定義日期：

- **發票日期** – 供應商開具發票的日期。
- **增值稅登記日期** – 採購發票增值稅金額扣除的日期。
- **供應商增值稅登記日期** – 供應商應稅供應的日期。
- **接收文件日期** – 您收到發票的日期。

這些欄位包含在以下頁面中：

- 廠商發票
- 廠商發票登記
- 供應商發票核准
- 供應商發票日記帳

過帳供應商發票後，您可以查看 **發票日記帳** 和 **供應商交易** 頁面上的日期。
