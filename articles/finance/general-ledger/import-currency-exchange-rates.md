---
title: 匯入貨幣匯率
description: 本主題提供有關匯入由匯率提供商公開的外匯參考匯率要求資訊。
author: EvgenyPopovMBS
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: f96622132be3c8a404f3f4e9c34f3ac5085a4fdc007ecb627d06a95d7c80932b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450261"
---
# <a name="import-currency-exchange-rates"></a>匯入貨幣匯率

[!include [banner](../includes/banner.md)]

如果法人實體已經收到外幣發票，必須將外幣換算成當地貨幣。 這意味著需要不同貨幣的最新匯率。 本主題提供匯入由匯率提供商 (例如歐洲中央銀行和俄羅斯中央銀行) 公開的外匯參考匯率所需設定和處理概觀。

下列章節說明用來設定和處理外匯匯率匯入的資訊流。

## <a name="configure-an-exchange-rate-provider"></a>配置匯率提供商
在您可以匯入匯率之前，您必須先設定提供匯率的提供商所需資訊。 請使用 **配置匯率提供商** 頁面選取匯率提供商。 某些匯率提供商會納入 Dynamics 365 Finance 的示範資料。 下表提供本頁面的控制項說明。

| 欄位 | 描述                   |
|-----------|-----------------------------------|
| **姓名**  | 匯率提供商名稱。                                                                                                                                                                                     |
| **機碼**   | 提供商要求每則配置資訊唯一的識別碼。 本項資訊會自動新增您新增的每個匯率提供商。 |
| **值** | 每個金鑰資訊。 本項資訊會新增您新增的每個匯率提供商。                                                                                         |

## <a name="import-currency-exchange-rates"></a>匯入貨幣匯率
您可以從匯率提供商來源匯入匯率並新增到 **貨幣匯率** 頁。 請使用 **匯入貨幣匯率** 頁面匯入匯率。 下表提供成功完成匯入流程所需的欄位說明。

| 欄位 | 描述                   |
|-----------|-----------------------------------|
| **匯率類型**                 | 匯率類型。                                                                                                                                                                                                                                                                                                                                                      |
| **匯率提供商**             | 匯率提供商。                                                                                                                                                                                                                                                                                                                                                  |
| **匯入日期**                       | 本參數管理是從當天日期起匯入或是特定日期範圍匯入。 如果您希望使用日期範圍，請輸入或選取開始日期和結束日期。                                                                                                                                                                                                                |
| **建立必要的貨幣對**    | 如果匯入的貨幣對不存在，此勾選方塊會管理貨幣對的自動建立。 本選項可能不適用一些提供商。                                                                                                                                                                                               |
| **覆寫既有的匯率**   | 當特定日期的匯率已經存在時，此勾選方塊管理貨幣對在既有匯率的更新。 如果您未選取此勾選方塊，如果已存在另一個匯率，不會匯入特定日期的匯率。                                                                                       |
| **防止國定假日匯入** | 此勾選方塊管理國定假日當天日期的匯率匯入。 例如，如果您選取此勾選方塊並使用歐洲中央銀行作為匯率提供商，系統將不會在目前法人實體相關的國定假日當天更新匯率。 本選項可能不適用一些提供商。 |
| **前一天匯率** | 如果您啟用 **功能管理** 頁面上的 **當日或前日歐洲央行匯入** 功能，此勾選方塊即會開放使用。 此勾選方塊只開放提供商，*歐洲央行* 使用。 選取此勾選方塊匯入歐洲央行於前一個工作日大約 16:00 CET 公開的貨幣匯率。 預設選取此勾選方塊。 清除此勾選方塊匯入同一個工作日公開的貨幣匯率。  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]