---
title: 建立耗用報告
description: 本主題說明如何在資產管理中建立耗用報告。
author: johanhoffmann
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e54511932ee9487cccae12a479dd210b5978c593dd7000ec2dfe09c3c4014670
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446619"
---
# <a name="create-consumption-reports"></a>建立耗用報告

[!include [banner](../../includes/banner.md)]

 

在資產管理中的工單建立並過帳耗用登記後，有兩個報告能顯示耗用詳細資料。


## <a name="asset-consumption-report"></a>資產耗用報告

在工單上過帳耗用後，您可列印資產耗用報告。 此報告會顯示資產上過帳的時數、時數成本、項目成本和費用。

1. 按一下 **資產管理** > **報告** > **資產** > **資產耗用**。

2. 在 **資產耗用** 對話方塊中，在相關切換按鈕選擇 **是**，並於 **顯示** 區段插入功能位置層級，藉此選擇參數與詳細程度。
    - 您可運用 **程度** 欄位，指定資產明細功能位置的詳細程度。 
    
        例如，如果在欄位中輸入數字「1」，並且您有一個多層功能位置結構，則一個功能位置的所有資產將顯示於最上層，讓您從較低層級的功能位置新增明細。 
        
        若在 **程度** 欄位輸入數字「0」，將呈現詳細的結果，顯示所有功能位置層級上相關的所有資產。 
        
    - 在 **所有子資產總和** 切換按鈕選擇 **是**，即可檢視報告內每項子資產的總和。

3. 在 **日期** 區段選擇日期間隔。

4. 在 **目的地** FastTab 上，選擇是否要在畫面上顯示報告、列印報告或將其儲存為檔案或電子郵件。

5. 如果需要，您可選擇在報告中顯示特定資產。 在 **要包括的記錄** FastTab 中，按一下 **篩選**，並新增要在報告中納入的資產。

6. 按一下 **確定** 以產生報告。


## <a name="work-order-consumption-report"></a>工單耗用報告

在工單上過帳耗用後，您可列印工單耗用報告。 此報告會顯示工單上過帳的時數、時數成本、項目成本和費用。

1. 按一下 **資產管理** > **報告** > **工單** > **工單耗用**。

2. 在 **工單耗用** 對話方塊中，在 **顯示** 區段的相關切換按鈕選擇 **是**，藉此選擇欲納入報告的參數。

3. 在 **日期** 區段選擇日期間隔。

4. 在 **目的地** FastTab 上，選擇是否要在畫面上顯示報告、列印報告或將其儲存為檔案或電子郵件。

5. 如果需要，您可選擇在報告中顯示特定工單。 在 **要包括的記錄** FastTab 中，按一下 **篩選**，並新增要在報告中納入的工單。

6. 按一下 **確定** 以產生報告。


>[!NOTE]
>您也可產生[工單報告](../work-orders/work-order-report.md)，其中包含更多工單詳細資料。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]