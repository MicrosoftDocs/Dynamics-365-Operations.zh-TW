---
title: 模型管理生命週期
description: 本主題說明維護貴組織的機器學習模型，以便最佳化它們產生預測的方法。
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 0b16cfdce801e8a63b47397526b47995018b99c9
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451002"
---
# <a name="model-management-lifecycle"></a>模型管理生命週期

[!include [banner](../includes/banner.md)]

本主題說明維護貴組織的機器學習模型，以便最佳化它們產生預測的方法。

我們建議您在沙箱環境訓練 AI 模型，然後使用託管解決方案部署到正式環境。 此辦法有助於確保已經準備好正確控制管理模型生命週期。

由於 AI 模型是以開發的發票和客戶資料為主，因此沙箱環境會有正式執行資料的最新副本，這很重要。 您可以開始在[使用客戶付款預測](use-customer-payment-predictions.md)中按照下列步驟訓練您的模型。 一旦重新訓練模型後，即可按照[評估初始客戶付款預測模型](evaluate-payment-prediction.md)所述評估結果。 使用[改善預測模型](improve-model.md)的資訊試驗有助於改善模型的功能和篩選條件組合。

當您對訓練結果感到滿意時，請按照[配置您的 AI 模型](/ai-builder/distribute-model)的步驟將模型轉換到您的正式環境。
