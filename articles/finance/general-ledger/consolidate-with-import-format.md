---
title: 合併的匯入格式
description: 本主題提供有關合併多個法律實體的財務資料時使用的匯入格式的詳細資料。
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 6d25ebfedfe748dfa262c1d4b0671539e6150a0f9f05dfca42e87f23486fbb19
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450495"
---
# <a name="import-format-for-consolidation"></a>合併的匯入格式

[!include [banner](../includes/banner.md)]

本主題提供有關合併多個法律實體的財務資料時使用的匯入格式的詳細資料。 匯入格式必須儲存為文字檔 (.txt)。

## <a name="import-format"></a>匯入格式

下表列出了在匯入期間進行合併時應使用的匯入格式。

| 記錄表 | 格式 | 附註 |
|--------------|---------|-------|
| 1            | 170150, Goodwill, 4 | <ul><li>記錄表</li><li>來源主科目識別碼</li><li>主科目行</li><li>主科目類型</li></ul> |
| 2            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>主科目識別碼</li><li>交易日期</li><li>會計期間類型 (**0** = 期初，**1** = 營運，**2** = 期末)</li><li>交易貨幣</li><li>借方或貸方 (**0** = 借方，**1** = 貸方)</li><li>過帳層</li><li>交易金額</li><li>數量</li><li>本地 RecID (交易的模糊、唯一 int64 值)</li></ul> |
| 3            | USMF0000009, 2017/01/01, FY2017, 1, 2017,01,01, 602200, USD, 6053.6.0 | <ul><li>分錄編號 (預算標題交易編號)</li><li>預算標題的預設日期</li><li>預算模型識別碼</li><li>預算類型 (**1** - 原始預算，**2** - 轉移，**3** - 修訂，**4** - 保留款，**5** - 預留款，**6** - 結轉預算，**7** - 專案，**8** - 固定資產，**9** - 需求預測，**10** - 供應預測，**11** - 分攤，**12** - 初步預算。)</li><li>行的日期</li><li>行的主科目識別碼</li><li>行的貨幣代碼</li><li>行的金額，以交易貨幣為單位</li><li>行的預算類型 (費用或收入) 的列舉整數值</li></ul> |
| 4            | DEMF | RecordCompany 是來源法律實體。 |
| 5            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>主科目識別碼</li><li>交易日期</li><li>會計期間類型 (0 期初，1 營運，2 期末)</li><li>交易貨幣</li><li>借方或貸方 (0 代表借方，1 代表貸方)</li><li>過帳層</li><li>交易金額</li><li>數量</li><li>本地 RecID (交易的模糊、唯一 int64 值)</li></ul>  |
| 6            | BusinessUnit，1 個部門，2 | 在區段訂單中定義的財務維度屬性。<p>您可以使用 **匯出** 頁面以驗證屬性是如何定義的。</p> |
| 7            | 002,1,658 | <ul><li>財務維度值</li><li>財務維度，作為 RecordDimensions 中提供的索引</li><li>與 RecordTrans 或 RecordTrans2 中的唯一記錄識別碼關聯的模糊的唯一記錄識別碼</li></ul> |
| 8            | 002,1,1 | <ul><li>與 RecordBudget 中的交易關聯的維度值</li><li>財務維度，作為 RecordDimensions 中提供的索引</li><li>與檔案中交易行的順序一致的模糊行記錄識別碼</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
