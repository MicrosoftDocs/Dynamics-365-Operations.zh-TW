---
title: 電子報表廠商支票樣本
description: 本主題提供有關如何使用電子申報樣本檢查格式的一般資訊。
author: sunfzam
ms.date: 06/14/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 2e1aa349b505713d0502aa90ddd5c3caff1f083c
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451020"
---
# <a name="electronic-reporting-sample-vendor-checks"></a>電子報表廠商支票樣本

[!include [banner](../includes/banner.md)]

您可以使用電子申報 (ER) 來格式化供應商支票。 市場上有許多銀行特定和支票提供商特定的支票格式。 範例支票格式已包含在 ER 工具庫的付款支票模型中。 這些樣本檢查標記為 **在中間檢查 (US)** 和 **檢查下方的頂部存根 (US)**。

## <a name="what-check-formats-are-currently-supported"></a>目前支持哪些支票格式？

您應始終存取 Microsoft Dynamics Lifecycle Services (LCS) 中的共用資產資料庫並查看資產類型為 **GER 設定** 的可用文件的當前清單。 下一部分「我必須設置什麼？」包含一個主題連結，該主題解釋如何建立 LCS 存放庫，以便您可以查看可用設定並匯入所選設定。

Microsoft Dynamics 365 Finance 包含一個範例格式，其中支票位於頂部，後跟兩個匯款部分。 它還包括一個樣本格式，其中支票位於中間，兩個匯款部分之間。 這些樣本格式對應於豪華商務支票格式。

## <a name="what-do-i-have-to-set-up"></a>我必須執行哪些設定？

- 在您可以使用 ER 列印支票之前，必須將至少一項活動支票設定匯入您的 ER 設定。 有關說明，請參閱[從 Lifecycle Services 下載電子報表編製配置](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)。
- 當您為銀行帳戶配置現金和銀行管理支票時，選中 **通用電子匯出格式** 核取方塊，然後選擇適當的支票格式作為匯出格式設定。
- 您還必須指定將在匯款上列印的滑動行數。 計算此數字時，請務必包括標題行。 對於兩種樣本檢查格式，推薦的滑動行數量為 17。 但是，此數字會有所不同，具體取決於您的支票庫存和列印機驅動程式。
- 我們建議您列印測試支票以驗證支票配置。 若要列印測試支票，請選擇 **列印測試** 選項。 在 Microsoft Excel 的高級列印機屬性中將 **邊際** 設定為 **None** 時，樣本檢查格式效果最佳。 生成測試檢查後，啟用 Excel 輸出的編輯，並配置頁面佈局，以便將所有邊距設定為 **0** (零)。 將支票的測試副本與您的支票庫存進行比較，並調整設置，直到您對對齊感到滿意。
- 當您在付款日誌中為配置的銀行帳戶生成付款時，支票將使用指定的格式打印。

如需詳細資訊，請參閱 [修改電子報告格式](../../fin-ops-core/dev-itpro/analytics/modify-electronic-reporting-format-reapply-excel-template.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
