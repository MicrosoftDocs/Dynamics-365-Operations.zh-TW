---
title: 手動建立服務訂單
description: 您可使用服務合約或使用 **服務訂單** 表單，手動建立服務訂單。
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1fad4abcf39021f94db50c07a39803af31f85c2
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449151"
---
# <a name="create-service-orders-manually"></a>手動建立服務訂單    

[!include [banner](../includes/banner.md)]


您可使用服務合約或使用 **服務訂單** 表單，手動建立服務訂單。 您亦可從專案建立服務訂單。

> [!TIP]
> <P>您可使用自動化流程來建立服務訂單。 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a>在服務合約手動建立服務訂單

1.  選擇 **服務管理** \> **一般** \> **服務合約** \> **服務合約**。

2.  選擇服務合約或建立新的服務合約。

3.  選擇 **交貨** 索引標籤，並於 **建立** 群組中選擇 **已規劃服務訂單**，即可開啟 **建立服務訂單** 表單。

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a>在服務訂單表單中手動建立服務訂單

1.  選擇 **服務管理** \> **一般** \> **服務訂單** \> **服務訂單**。

2.  選擇 **新增** 建立新的服務訂單。

3.  在服務訂單建立服務訂單明細。

> [!NOTE]
> <P>若您選擇<STRONG>服務管理參數</STRONG>表單內的<STRONG>允許無服務合約</STRONG>核取方塊，則可在服務訂單明細張貼交易，不需要將服務訂單附加到服務合約。 若清除該核取方塊，則您必須將該手動建立的服務訂單附加到專案，之後才能張貼服務訂單明細。</P>

## <a name="create-a-service-order-from-a-project"></a>從專案建立服務訂單

1.  移至 **專案管理和會計** \> **一般** \> **專案** \> **所有專案**。

2.  在 **專案** 表單內的 **動作窗格** 上，選擇 **管理** 索引標籤 \> 選擇 **服務** \> **服務訂單**。

3.  遵循之前的程序，在 **服務訂單** 表單中手動建立服務訂單。 **專案識別碼** 欄位會顯示專案參考。

> [!NOTE]
> <P>若您選擇<STRONG>服務管理參數</STRONG>表單內的<STRONG>允許無服務合約</STRONG>核取方塊，則可在服務訂單明細張貼交易，不需要將服務訂單附加到服務合約。 若清除該核取方塊，則您必須將該手動建立的服務訂單附加到專案，之後才能張貼服務訂單明細。</P>

## <a name="create-a-service-order-from-the-sales-order-form"></a>從銷售訂單表單建立服務訂單

您可在 **銷售訂單** 表單建立服務訂單，方法是使用 **根據銷售訂單建立新的服務訂單** 精靈。

1.  移至 **銷售和行銷** \> **一般** \> **銷售訂單** \> **所有銷售訂單**。

2.  開啟相關的銷售訂單。

3.  在 **銷售訂單** 索引標籤中，選擇 **服務訂單**，即可啟動 **根據銷售訂單建立新的服務訂單** 精靈。

4.  選擇 **下一步\>**，然後於 **選擇服務訂單合約** 頁面中完成下列步驟：
    
      - 使用 **服務合約** 欄位來選擇新的服務訂單相關聯的服務合約。
    
      - 選用：使用 **專案識別碼** 欄位，將此服務訂單與特定專案建立關聯。

5.  選擇 **下一步\>**，然後於 **建立服務訂單** 頁面中完成下列步驟：
    
      - 在 **偏好服務時間** 欄位中，輸入服務呼叫開始的日期與時間。
    
      - 選用：修改 **描述** 欄位內的文字。 此欄位預設有您於上個頁面選擇的服務合約的描述。
    
      - 在 **負責** 欄位中，選擇負責該合約的員工識別碼，若您知道客戶服務呼叫偏好的技術人員，您也可輸入其識別碼。
    
      - 在 **連絡人識別碼** 欄位中，選擇此服務訂單在客戶公司內應連絡的人員。

6.  選擇 **下一步\>**，然後選擇 **結束**。


## <a name="see-also"></a>另請參閱

[服務訂單](service-orders.md)

[自動建立服務訂單](create-service-orders-automatically.md)

[建立服務訂單 (類別表單)](https://technet.microsoft.com/library/aa553901\(v=ax.60\)) 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]