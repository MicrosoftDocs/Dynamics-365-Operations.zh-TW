---
title: 電子開票概觀
description: 本主題概述了 Microsoft Dynamics 365 Finance 和 Dynamics 365 Supply Chain Management 中的電子開票功能。
author: gionoder
ms.date: 01/21/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 23a98706bc2ab0abc2c72e9f20d8e8fbff56b2b9
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451704"
---
# <a name="electronic-invoicing-overview"></a>電子開票概觀

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Finance 和 Dynamics 365 Supply Chain Management 的電子開票是一種超可擴充的多租用戶服務，可對電子發票進行可設定處理和可設定電子文件交換。 處理和整合規則完全可設定，邏輯在 Finance 和 Supply Chain Management外部執行。 該服務主要針對企業對政府情況下的電子發票文件處理。 但是，它可以針對其他目的進行自訂定，例如在企業對企業情況中使用不同類型的文件。

電子開票能幫助您實現以下目標：

- 快速輕鬆地採用國家/地區的特定要求
- 標準化實作電子開票解決方案
- 增強文件歷史記錄的可追溯性
- 實施週期更短
- 降低擁有權總成本 (TCO)
- 無需變更代碼即可輕鬆調整設定
- 簡化設定封裝
- 內建匯出、匯入和整合，並可在處理電子發票文件時輕鬆擴充
- 跨公司輕鬆重複使用相同的匯出、匯入和整合設定

## <a name="service-availability"></a>服務可用性

目前，Finance 和 Supply Chain Management 客戶可以使用電子開票功能。 有關更多資訊，請查看您的應用程式的授權條款及條件。

由於滿足國家/地區特定要求的功能可能會在發佈的不同階段受到限制，因此您應該查看最新的文件，這些文件重點介紹受支援的國家/地區特定解決方案的覆蓋範圍。

電子開票部署的 Azure 地理位置如下：

- 美國
- 歐洲
- 亞洲

> [!NOTE]
> 電子開票不支援內部部署。

## <a name="feature-highlights"></a>功能亮點

- 與 Finance 和 Supply Chain Management 的現成整合
- 為所有國家和地區的電子開票流程的設定和監控提供一致的使用者體驗
- 在新的國家或地區更快、更輕鬆、更便宜地採用電子開票解決方案
- 透過設定 Regulatory Configuration Service (RCS) 和全球化功能來設定服務
- 使用 RCS 中定義的設定將業務資料轉換為多種電子發票格式 (XML、JavaScript 物件標記法 \[JSON\]、TXT 和逗號分隔值 \[CSV\])：

    - 電子報表 (ER) 格式可用於無法使用電子發票轉換設定的國家和地區

- 可設定地向外部 Web 服務提交電子開票，包括透過數位簽章處理認證：

    - 內建、易於擴充且可設定的整合包含適用於多個國家和地區的其他內容

- 處理來自 Web 服務的回應，包括可設定的例外狀況訊息處理
- 支援電子簽章 (例如，使用 XMLDSig 簽署算法的電子簽章)
- 能夠將文件發送到電子郵件並將其存儲在 SharePoint 中
- 批次處理電子發票訊息
- 對傳入文件進行可設定的轉換，以及在 Finance 和 Supply Chain Management 中處理這些文件
- 能夠從電子郵件和 SharePoint 等通道接收傳入文件

## <a name="privacy-notice"></a>隱私權注意事項

啟用和使用電子開票可能需要僅發送有限的資料。 此資料包括組織的稅務登記識別碼。 該資料被傳輸到稅務機關授權的第三方機構，以便使用與政府的 Web 服務整合所需的預先定義格式發送電子發票。 從這些外部系統匯入此 Dynamics 365 線上服務的資料受[隱私權聲明](https://go.microsoft.com/fwlink/?LinkId=512132)約束。 有關詳細資訊，請參閱特定國家/地區的功能文件中的「隱私權聲明」區段。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
