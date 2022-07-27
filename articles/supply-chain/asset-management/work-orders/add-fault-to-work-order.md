---
title: 在工單新增異常
description: 本主題介紹在資產管理中如何在工單新增異常登記。
author: johanhoffmann
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1090d95d381a047e77bca3e18ef7b99151ea3d5f941f2d6c9e4877a339f1385e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447132"
---
# <a name="add-fault-to-work-order"></a>在工單新增異常

[!include [banner](../../includes/banner.md)]



對於在異常設計器設定的異常，您可以將其新增到工單。 一個或多個異常記錄必須連接到資產類型，該資產類型為工單中已選取的資產所使用的。 如需設定的詳細資訊，請參閱[異常管理](../setup-for-work-orders/fault-management.md)。

1. 選取 **資產管理** > **一般** > **工單** > **所有工單** 或 **進行中工單**。

2. 選取要進行異常登記的工單，然後在「動作窗格」中的 **工單** 索引標籤，在 **資產** 群組，選取 **資產異常**。

3. 在 **異常徵兆** 快速索引標籤，選取 **新增明細**。 一個序號型的異常編號會自動輸入到 **異常** 欄位。

4. 在 **異常徵兆** 欄位，選擇相關症狀。

5. 在 **異常區域** 和 **異常類型** 欄位，選取適當的值。

6. 在 **異常日期** 欄位，會自動插入當前日期。 請依據您的需求選取不同的日期。

7. 在 **選定異常徵兆的原由** 快速索引標籤，新增一明細來說明問題的原因。

8. 在 **選定異常徵兆的補救措施** 快速索引標籤，新增一明細來說明可能的解決方案。

9. 選取 **儲存**。

下圖為異常登記的範例。

![圖 1。](media/19-work-orders.png)


## <a name="view-asset-faults"></a>查看資產異常

**資產異常** 列表會摘要資產上註冊的所有異常。

**資產異常** 列表頁面會摘要所有已註冊在資產上的異常。 若要打開頁面，請選擇 **資產管理** > **查詢** > **資產異常** > **資產異常**。


## <a name="print-asset-fault-report"></a>列印資產異常報告

在 **所有資產** 列表頁面，您可以列印內含所有異常記錄和異常統計圖表摘要的資產異常報告。

1. 選擇 **資產管理** > **通用** > **資產** > **全部資產**。

2. 選取資產，以列印異常報告。

3. 在動作窗格上，**一般** 索引標籤，**報告** 群組中，選取 **資產異常**。

4. 輸入特定期間，或選取異常類型。

5. 選取 **確定**，列印報告。

>[!NOTE]
>若要列印多個資產或資產類型的異常報告，請選擇 **資產管理** > **報告** > **資產** > **資產異常**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]