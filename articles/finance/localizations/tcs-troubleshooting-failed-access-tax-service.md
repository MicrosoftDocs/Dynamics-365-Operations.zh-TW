---
title: 無法存取稅務服務
description: 本主題說明如何解決無法存取稅務計算服務的問題。
author: hangwan
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 02/16/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 48a75cd0c1d91c3b3d9c3fb2e6cab93a76756532
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2022
ms.locfileid: "8451734"
---
# <a name="failed-to-access-tax-service"></a>無法存取稅務服務

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

本主題介紹如何修復稅務計算服務的“無法存取稅務服務”錯誤。

## <a name="symptoms"></a>問題

在 Microsoft Dynamics 365 Finance，前往 **稅務** \> **設定** \> **稅務設定** \> **稅務服務參數**。 在 **一般** 索引標籤，您啟用 **啟用稅務計算** 選項。 若您接著嘗試在 **功能設定名稱** 欄位選擇值，則發生錯誤。 錯誤訊息顯示“無法存取稅務服務”。

## <a name="cause"></a>原因

出現此錯誤的原因是 Finance 無法存取稅務計算服務。

## <a name="resolution"></a>解決方法 

1. 登錄 Microsoft Dynamics Lifecycle Services (LCS)。
2. 在 **環境** 頁面的 **環境增益集** 索引標籤，找到 **稅務計算** 項目，檢視其狀態。 該狀態應該是 **正在安裝** 或 **已安裝**。 如果未安裝稅務計算服務增益集，您將收到錯誤訊息。

## <a name="mitigation"></a>風險降低

1. 在 LCS 中，在 **財務** 頁面，在 **Power platform 整合** 部分，選擇 **安裝新的增益集**。
2. 滾動到頁面底部，然後選擇 **稅務計算** 增益集來安裝它。
3. 返回您的財務環境，並嘗試存取稅務計算服務。

> [!NOTE]
> 在安裝稅務計算服務之前，請查看[稅務計算服務先決條件 ](global-get-started-with-tax-calculation-service.md#prerequisites)。
> 
> 如果您因為 **Power platform 整合** 部分不可用而無法安裝增益集，請參閱[增益集概覽 ](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md)。 如果您在安裝增益集後仍遇到錯誤，請聯繫您的系統管理員。
