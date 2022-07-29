---
title: TaxTrans 中的不正確欄位值
description: 本主題提供對 TaxTrans 中的不正確欄位值進行疑難排解的相關資料。
author: EricWangChen
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 00424d98d5ff99123edf42ee19919d149e7a6abc
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2021
ms.locfileid: "8450984"
---
# <a name="incorrect-field-value-in-taxtrans"></a>TaxTrans 中的不正確欄位值

[!include [banner](../includes/banner.md)]

如果 **TaxTrans** 中的欄位值不正確，請使用本主題中的資料來解決此問題。

## <a name="overview-of-values"></a>值概覽
以下清單顯示為何 **TaxTrans**、**TaxUncommitted** 和 **TmpTaxWorkTrans** 是相似的資料集，而如何以不同的方式工作。

  - **TaxTrans** 是保留在資料庫中的最終已過帳稅款交易結果。
  - **TaxUncommitted** 是保留在資料庫中的中間計算稅款結果 (如果適用)，其稍後將在過帳時使用。
  - **TmpTaxWorkTrans** 是記憶體內部表中的臨時計算稅款結果 (表類型 = InMemory)。

如果您發現 **TaxTrans** 列不正確的根本原因，那麼您同時也找到 **TaxUncommitted** 或 **TmpTaxWorkTrans** 列不正確的根本原因。 這是因為這三列是相互複製的。

通常，在計算稅款時，將產生 **TmpTaxWorkTrans**，然後產生 **TaxUncommitted** (如果適用)。 在稅款過帳期間，產生 **TaxTrans**。


## <a name="add-breakpoints"></a>加入中斷點
若要加入中斷點，請完成以下步驟： 

1. 在擴充名中的 *insert()* 和 *update()* 中加入擴充名和中斷點，如下所示。

     - **TaxTrans**

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TaxUncommitted**

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TmpTaxWorkTrans**

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. 或者，您可以在未包括 **TaxUncommitted** 時直接加入中斷點。

     - *TaxTrans.insert()*、*TaxTrans.update()*
     - *TmpTaxWorkTrans.insert()*、*TmpTaxWorkTrans.update()*

## <a name="reproduce-and-debug"></a>重現和偵錯

設立中斷點後，在偵錯期間可以看到每個資料持久性變化。 找出 **TaxTrans**、**TaxUncommitted** 或 **TmpTaxWorkTrans** 列不正確的根本原因，查看並注意以下各項：

- 列正確的最後一個中斷點。
- 列不正確的第一個中斷點。
- 在這兩個點之間發生什麼。

## <a name="determine-whether-customization-exists"></a>確認是否存在自訂
如果您已完成前幾部分中的步驟，但仍無法解決問題，請確定是否存在自訂。 如果不存在自訂，請連絡 Microsoft 支援服務尋求協助。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

