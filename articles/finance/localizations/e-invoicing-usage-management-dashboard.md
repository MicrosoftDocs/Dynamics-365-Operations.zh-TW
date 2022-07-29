---
title: 使用方式管理儀表板
description: 本主題說明如何使用「使用方式管理儀表板」，來監控電子發票服務的使用情況並符合規定。
author: gionoder
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 35b50c8cb5c6ef72f466a4fb10c7af0e53afc3db5d1ef9e2b23d6049e24a70c3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450825"
---
# <a name="usage-management-dashboard"></a>使用方式管理儀表板

[!include [banner](../includes/banner.md)]

**使用方式管理** 儀表板可幫助您監控電子發票服務的使用情況，從而幫助您的組織在每月使用方面保持符合規定。 合規性是透過計算提交量並將其與獲取的提交量進行比較來確定的，以識別獲取量和使用量之間的任何偏差。

儀表板包括下列指標：

- 一種可用於監控消耗以實現許可合規性目的的成本指標：

    - 每月的使用情況 (匯出)

- 您可以使用三個作業指標來追蹤電子發票服務的使用情況以進行管理：

    - 依照功能分類的使用方式
    - 依照環境分類的使用方式
    - 每月的使用情況 (匯入)

## <a name="measurement-scope"></a>測量範圍

- 衡量單位： 

    **使用方式管理** 儀表板統計提交的業務文件和匯入的電子發票。

- 組織： 

    計數由組織的租用戶識別碼匯總，無論 Microsoft Dynamics 365 Finance 或 Dynamics 365 Supply Chain Management 的執行個體數量如何，或啟用電子發票服務的法人數量如何。


## <a name="indicator-usage-per-month-export"></a>指標：每月的使用情況 (匯出)

此指標提供您的組織在定義期間內開具的電子發票的相關詳細資訊。

### <a name="scope"></a>範圍
- 從 Finance 和 Supply Chain Management 提交到電子發票服務的業務文件的數量，無論這些業務文件包含多少行。
- 電子發票服務成功處理的已提交商務文件的數量。 當功能設置中定義的動作流程完成時，文件被視為已成功處理。

> [!NOTE]
> 將電子發票提交給外部 Web 服務時，計數與 Web 服務處理的結果 (接受、拒絕或模式驗證錯誤) 無關。 如果 Web 服務收到並回應來自電子發票服務的請求，則提交被視為有效計數。

- **例外：** 如果商務文件從 Finance 和 Supply Chain Management 重新提交到電子發票服務，則不計算在內，例如在需要重新提交相同商務文件以更改其狀態的情況下電子發票。 例如，巴西電子發票 (財務文件) 的開立被視為有效，但其取消請求不被計算在內。


### <a name="calculation"></a>運算

餘額的計算如下：

餘額 = 免費 + 已購買 - 已使用

其中：

- 免費：
  
    客戶可以每月提交的免費商務文件量。 其中包括一個包含 100 個商務文件的套件，可以提交給電子發票服務。 免費量不是累積的，任何剩餘餘額都不會轉入下一個期間。
  
- 已購買:
  
    一個包含 1,000 個商務文件的套件，可以提交給電子發票服務。 必須每月為您的組織購買此軟體套件。 購買量不是累積的，任何剩餘餘額都不會轉入下一個期間。
  
- 已使用： 

    根據定義的標準向電子發票服務提交的商務文件計數。
   
> [!IMPORTANT]
> 如果您的組織計劃超過每月 100 次免費提交的數量，請購買峰值數量，以確保您始終遵守 Microsoft 的電子發票服務許可政策。
>
> 目前，購買量必須手動輸入，根據購買日期，作為 1,000 份提交的多個套件。

## <a name="indicator-usage-by-feature"></a>指標：依照功能分類的使用方式

該指標顯示了在定義的時期內使用電子發票功能開具電子發票的情況。

- 運算：
  
    已使用 = 在向電子發票服務提交商務文件期間使用每個電子發票功能的次數。

## <a name="indicator-usage-by-environment"></a>指標：依照環境分類的使用方式

該指標顯示了指定期間內電子發票服務環境的使用情況。

- 運算：
    
    已使用 = 在向電子發票服務提交商務文件期間使用每個電子發票服務環境的次數。

## <a name="indicator-usage-per-month-import"></a>指標：每月的使用情況 (匯入)

該指標顯示在規定期間內通過電子開票服務將電子發票匯入 Finance 和 Supply Chain Management 的數量。

- 範圍：

    匯入 Finance 和 Supply Chain Management 的電子發票，無論這些電子發票包含多少行。

- 運算：

    已收到 = 匯入 Finance 和 Supply Chain Management 的電子發票計數。

## <a name="functions"></a>函式
### <a name="purchase"></a>購買

在 **每月使用方式 (匯出)** 索引標籤上，選擇 **購買** 以手動註冊獲得的提交量。

對於特定日期，選擇 **全新** 並輸入在該日期獲得的 **套件** 數量。

**數量** 計算如下：

數量 = 套件 * 1.000

計算出的 **數量** 反映在 **購買** 指標 **每月使用方式 (匯出)** 中。

### <a name="update"></a>更新

在動作窗格上，選擇 **更新** 以重新整理計算並更新頁面和圖表中顯示的數據。

### <a name="reset-history-data"></a>重置歷程資料

在動作窗格上，選擇 **重置歷程資料** 以重新整理計算指標的資料庫。




> [!NOTE]
> **使用方式管理** 儀表板不會顯示貨幣金額。 相反地，它只會顯示計數提交和匯入文件的數量。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
