---
title: 設定費用類型
description: 本主題說明如何在「資產租賃」中設定費用類型。
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseExpenseTypeTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1e5af18921314061ba3256559d7fc7ceacef606a9b3d5cc3a8047c83494074fc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450156"
---
# <a name="set-up-expense-types"></a>設定費用類型

[!include [banner](../includes/banner.md)]

本主題說明如何在「資產租賃」中設定費用類型。 付款排程中未包含的費用稱為 *費用成本*。 這些費用的範例包括財產稅、公共區域維護成本和保險費用。

## <a name="add-an-administrative-expense-type"></a>新增管理費用類型

1. 前往 **資產租賃\>設定\>費用類型**。
2. 選擇 **新建**。
3. 在合適的欄位中，輸入新的費用類型和說明。

## <a name="assign-accounts-to-administrative-costs"></a>將科目指派給管理費用

接下來，您應該將科目與費用類型相關聯。 過帳費用排程項目時，將借記這些科目。 在每個租賃的 **執行費用付款排程** 明細中指定沖銷科目。

1. 前往 **資產租賃\>設定\>資產租賃參數**。
2. 在 **科目** 索引標籤中 **執行費用** FastTab 內的 **費用類型** 欄位，選擇費用類型。
3. 選擇 **新增**。
4. 在 **帳冊類型** 欄位中，選擇要連結到管理費用的帳冊類型。

    > [!NOTE]
    > 可以將多種帳冊類型連結到同一個費用科目。

5. 在 **科目代碼** 欄位中，指定帳冊應該套用在哪些租賃：

    - **全部**：將帳冊套用在所有租賃。
    - **群組**：將本帳冊套用在特定租賃群組。
    - **表**：將本帳冊套用在特定租賃。

6. 如果在 **科目代碼** 欄位中選擇 **群組** 或 **資料表**，則在 **科目/群組編號** 欄位中選擇科目編號或群組編號。
7. 在相應欄位中，選擇融資租賃主科目和營業租賃主科目。

完成這些步驟後，您可以經由所選租賃之 **租賃詳情** 頁面中的 **執行成本付款排程** 明細加入費用。 或者，您可以在建立新租賃時加入費用。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
