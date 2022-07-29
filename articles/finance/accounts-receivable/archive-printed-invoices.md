---
title: 使用雜湊編號封存列印的客戶發票
description: 本主題說明如何啟用封存以儲存具有雜湊編號的列印客戶發票。
author: ilkond
ms.date: 09/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 093b1b8c516c0c659e7970d17d3f84b2ed0ccf8f
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2021
ms.locfileid: "8450987"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a>使用雜湊編號封存列印的客戶發票

[!include [banner](../includes/banner.md)]

在某些國家/地區，法律要求將計算出的雜湊編號與某些文件的列印輸出一起儲存在系統中。 雜湊編號可用於向主管機關報告和在稽核期間報告。

本主題說明如何設定封存以儲存具有雜湊編號的列印客戶發票。

## <a name="prerequisites"></a>先決條件

- 在 **功能管理** 工作區，打開 **封存具有雜湊編號的列印客戶發票** 功能。 更多資訊，請參閱[功能管理概觀](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)。
- 在 **列印管理** 中設定所需文件的可列印格式。

此功能適用於以下文件。

**應收帳款**
- 客戶發票
- 客戶貸項通知單
- 普通發票
- 普通發票貸方通知單

**專案管理和會計**
- 專案發票
- 專案貸項通知單

## <a name="configure-customer-master-data"></a>設定客戶主資料
完成以下步驟以設定客戶資料，並啟用將列印發票自動另存為附件的功能。

1. 前往 **應收帳款** > **所有客戶**。 
2. 選擇客戶，然後在 **發票和交貨** FastTab 的 **電子發票** 區段，在 **電子發票附件** 欄位，選擇 **是**。

## <a name="print-invoices"></a>列印發票
您可以為上一個程序中設定的客戶過帳和列印任意文字、客戶和專案發票或貸方通知單。

打開列印發票的 **附件** 頁面。 在 **附件** FastTab 上，在 **其他詳細資料** 欄位群組的 **文件雜湊編號** 欄位中，尋找為列印發票計算的已儲存雜湊編號。

![附件雜湊編號。](media/attach-hash-num.jpg)

