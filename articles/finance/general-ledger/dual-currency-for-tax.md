---
title: 稅金的雙貨幣支援
description: 本主題介紹如何在稅金領域擴展雙貨幣會計功能以及對稅金計算和過帳的影響
author: EricWang
ms.date: 12/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 449ebe55b8be7ee7ea22b4be7c44162d83fc3c2affbd4d20f4cad235ddb0f772
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450432"
---
# <a name="dual-currency-support-for-sales-tax"></a>銷售稅的雙貨幣支援
[!include [banner](../includes/banner.md)]

本主題介紹如何擴展銷售稅的雙貨幣會計功能以及對稅金計算、過帳與結算的影響

8.1 版 (2018 年 10 月) 中引入了適用於 Dynamics 365 Finance 的雙貨幣功能。 其改變了以報表貨幣計算會計分錄的方式。

在早期版本中，交易按以下順序轉換為報表貨幣： 

- 交易總額以交易貨幣計算 > 交易金額轉換為會計貨幣 > 會計貨幣金額轉換為報表貨幣

啟用雙貨幣功能後，交易按以下順序轉換為報表貨幣：

- 交易貨幣金額 > 報表貨幣金額

有關雙貨幣的更多資訊，請參閱[雙貨幣](dual-currency.md)。

由於支援雙貨幣，功能管理中增加了兩個新功能： 

- 營業稅轉換 (10.0.13 版本中的新功能)
- 在已實現的貨幣調整損益帳戶中輸入財務維度以進行銷售稅結算 (版本 10.0.17 中的新功能)

對銷售稅的雙貨幣支援可確保以稅金貨幣準確計算稅款，並以會計貨幣和報表貨幣準確計算銷售稅結算餘額。

## <a name="sales-tax-conversion"></a>銷售稅轉換

**銷售稅轉換** 參數提供了兩個選項來將稅額從交易貨幣轉換為稅金貨幣。 

- 記帳貨幣：路徑為 [交易貨幣金額 > 會計貨幣金額 > 稅金貨幣金額]。 會計貨幣匯率類型 (在分類帳中設定) 將用於貨幣轉換。
- 報表貨幣：路徑為 [交易貨幣金額 > 報表貨幣金額 > 稅金貨幣金額]。 報表貨幣匯率類型 (在分類帳中設定) 將用於貨幣轉換。

### <a name="example"></a>範例

以下是介紹此功能的簡單示範：

分類帳和稅金的貨幣設定

| 交易貨幣 | 會計貨幣 | 報表貨幣 | 稅金貨幣 |
| -------------------- | ------------------- | ------------------ | ------------ |
| 歐元                  | 美元                 | 英鎊                | 英鎊          |

匯率

| 原始貨幣 | 目標貨幣 | 係數 | 匯率 |
| ------------- | ----------- | ------ | ------------- |
| 歐元           | 美元         | 1      | 1.11          |
| 歐元           | 英鎊         | 1      | 0.83          |
| 美元           | 英鎊         | 1      | 0.75          |

不同參數選項中的稅額計算

稅額 = 100 歐元

| 銷售稅轉換參數 | 交易貨幣 (歐元) | 會計貨幣 (美元) | 報表貨幣 (英鎊) | 稅金貨幣 (英鎊) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| 會計貨幣             | 100                        | 111                       | 83                       | **83.25**          |
| 報表貨幣              | 100                        | 111                       | 83                       | **83**             |

該參數可以根據稅金機關的合規需求進行設定。


### <a name="upgrade-consideration"></a>升級注意事項

此功能僅適用於新交易。 對於已儲存在 TAXTRANS 表中但尚未結算的稅金交易，系統不會重新計算稅幣稅額，因為過帳稅時的匯率已經缺失。

為防止出現上述情況，建議在不包含任何未結算稅金交易的新 (乾淨) 稅金結算期間變更此參數值。 要在納稅期中間變更此值，請在變更此參數值之前執行目前納稅期的 [結算和過帳銷售稅] 程序。

此功能將新增會計分錄，以闡明貨幣兌換的收益和損失。 在銷售稅結算期間進行重估時，將在已實現的貨幣調整損益帳戶中建立分錄。 有關詳細資訊，請參閱本主題後文的[稅金結算自動平衡採用報表貨幣](#tax-settlement-auto-balance-in-reporting-currency)一節。

> [!NOTE]
> 在結算期間，財務維度的資訊取自增值稅科目 (即資產負債表科目)，並輸入貨幣調整損益科目 (即損益表科目)。 由於資產負債表科目和損益表科目對財務維度值的限制不同，因此在結算和銷售稅後處理過程中可能會出現錯誤。 為避免必須修改科目結構，您可以打開 [將財務維度填充到已實現的貨幣調整損益科目以進行增值稅結算] 功能。 此功能將強制將財務維度衍生到貨幣調整損益帳戶。 

## <a name="track-reporting-currency-tax-amount"></a>追蹤報表貨幣稅額

三個新欄位被新增到與稅金相關的表格中，以追蹤報表貨幣的金額。 這些欄位位於 TAXUNCOMMITTED 和 TAXTRANS 表中：

- TaxAmountRep：以報表貨幣計的稅額
- TaxBaseAmountRep：以報表貨幣計的基準額
- TaxInCostPriceRep：以報表貨幣計的不可扣除額

對於僅儲存在 TAXUNCOMMITTED 表中但尚未過帳的稅款，系統將在過帳時重新計算以報表貨幣計的稅額並儲存在 TAXTRANS 表中。

此版本不包括以報表貨幣顯示稅額的報告和表格的變更。 報告和表格的變更將在未來版本中提供。



## <a name="tax-settlement-auto-balance-in-reporting-currency"></a>報表貨幣的稅金結算自動平衡

若因營業稅折算路徑為 [會計貨幣] 等原因導致報稅結算不平衡，或單個報稅期間匯率發生變化，系統將自動產生會計分錄調整稅額差異並將其與在分類帳設定中設定的已實現匯兌損益帳戶相抵消。

使用前面的例子來演示這個特性，假設過帳時 TAXTRANS 表中的資料如下。

| 銷售稅轉換參數 | 交易貨幣 (歐元) | 會計貨幣 (美元) | 報表貨幣 (英鎊) | 稅務貨幣 (英鎊) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| 會計貨幣             | 100                        | 111                       | 83                       | **83.25**          |
| 報表貨幣              | 100                        | 111                       | 83                       | **83**             |

月末執行銷售稅結算程序時，會計分錄將如下所示。
#### <a name="scenario-sales-tax-conversion--accounting-currency"></a>案例：營業稅轉換 = [會計貨幣]

| 主科目           | 交易貨幣 (英鎊) | 會計貨幣 (美元) | 報表貨幣 (英鎊) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| 應付/應收稅金 | -83.25                     | -111                      | -83.25                   |
| 稅金結算         | 83.25                      | 111                       | 83.25                    |
| 已實現收益/損失     | 0                          | 0                         | -0.25                    |
| 應付/應收稅金 | 0                          | 0                         | 0.25                     |

#### <a name="scenario-sales-tax-conversion--reporting-currency"></a>案例：營業稅轉換 = [報表貨幣]


| 主科目           | 交易貨幣 (英鎊) | 會計貨幣 (美元) | 報表貨幣 (英鎊) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| 應付/應收稅金 | -83                        | -110.67                   | -83                      |
| 稅金結算         | 83                         | 110.67                    | 83                       |
| 已實現收益/損失     | 0                          | 0.33                      | 0                        |
| 應付/應收稅金 | 0                          | -0.33                     | 0                        |



有關詳細資訊，請參閱下列主題：

- [雙貨幣](dual-currency.md)
- [銷售稅概觀](indirect-taxes-overview.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
