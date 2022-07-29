---
title: 將付款期程套用到發票日記帳
description: 本主題說明如何新增付款到廠商發票日記帳。
author: sunfzam
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: f6481c3fc033acf4bb563bf1716789216646b60b
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2022
ms.locfileid: "8451650"
---
# <a name="apply-a-payment-schedule-to-the-invoice-journal"></a>將付款期程套用到發票日記帳

[!include [banner](../includes/preview-banner.md)]

在 Microsoft Dynamics 365 Finance 發行版本 10.0.25 中，**廠商發票日記帳** 上現在已支援付款期程。

若要使用此功能，您必須啟用功能管理中的 **將付款期程套用到發票日記帳** 功能。

啟用此功能後，新 **付款期程** 欄位會新增到 **發票日記帳** 頁面。 建立發票日記帳明細時，如果付款條件按廠商維護，並且在付款期程選取付款條件，則 **付款期程** 欄位會在 **發票日記帳** 頁面上更新。

您可以根據您的業務需求更改使用的付款期程。 廠商發票日記帳過帳期間，廠商未結交易將根據付款期程建立。

 - 若要審核付款期程產生的多筆廠商未結交易，請前往 **應付帳款\>發票\>打開廠商發票**，然後輸入發票號碼或廠商帳號。
 - 若要審核或配置付款期程，請前往 **應付帳款\>付款設定\>付款期程**。
 - 若要配置付款條件和指派付款期程，請前往 **應付帳款\>付款設定\>付款條件**。
 - 若要維護廠商的付款條件，請前往 **應付帳款\>所有廠商**，選取廠商帳號，然後在 **付款** 索引標籤上設定 **付款條件** 欄位。

付款期程功能也會在 **廠商發票登記** 流程開放使用。 如果在發票登記日記帳上選取付款期程，過帳發票登記簿時 **將不會** 產生多條廠商付款明細。 廠商付款明細將在核准發票時產生。

## <a name="limitation"></a>上限

以待核定廠商發票為例，如果付款期程以發票抬頭出具，會有進階頁讓使用者編輯付款明細資料。 (例如，使用者可以編輯每條付款明細的到期日和值。) 從發票日記帳產生的付款明細值將以付款期程為主。

此功能將在未來發行版本中，開放 **廠商發票日記帳** 和 **待核定發票** 使用。
