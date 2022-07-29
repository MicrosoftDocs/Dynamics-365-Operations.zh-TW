---
title: 建立維護要求
description: 本主題說明如何在資產管理中建立維護要求。
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4b48a0504b79d2edf7815296312c7839052092e7d6773b7ebd5d38cbb59c9428
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446646"
---
# <a name="create-maintenance-requests"></a>建立維護要求

[!include [banner](../../includes/banner.md)]

 

如果維護工人或生產工人發現設備需要維護，但維護工作不能立即完成，則可以使用維護要求。

**範例：** 在維護工人進行修復時，他們發現必須維修同一地點的另一項資產。 但是，維護人員沒有時間或所需的預備零件來完成維護工作。 因此，他們會針對資產建立維護要求並輸入問題的簡短說明。

在 **所有資產** 或 **使用中資產** 頁面 (**資產管理** \> **通用** \> **資產** \> **所有資產** 或 **使用中資產**) 右側的 **相關資訊** 窗格的 **使用中維護要求** 區段，會顯示連接到選定資產的使用中維護要求。

1. 選擇 **資產管理** \> **通用** \> **維護要求** \> **所有維護要求** 或 **使用中維護要求**。
2. 選擇 **新增**。
3. 在 **建立要求** 對話方塊的 **維護要求類型** 欄位中，選擇維護要求的類型。 建議使用預設類型。
4. 在 **描述** 欄位中，輸入簡要描述該維護要求的名稱或標題。
5. 在 **功能位置** 和 **資產** 欄位中，依據需要選擇功能位置或資產，或功能位置與資產的組合。 您可以在不選擇資產的情況下建立維護要求，並可在稍後將資產新增到維護要求中。 如果登入的維護工人與資產相關的資源相關，則 **資產** 欄位是自動設定的。

    如果維護請求已連接到所選資產，則訊息列將出現在 **建立要求** 對話方塊上方，以通知您現有維護要求的 ID。 如果資產包含在保固協議中，訊息欄也會通知您。

6. 在 **服務等級** 欄位中，選擇指示要求緊急程度的服務等級。
7. 如果您在步驟 5 中選擇了資產，則可以使用 **異常徵兆**、**異常區域** 和 **異常類型** 欄位來建立異常登記。
8. 如果維護要求導致維護停機，請輸入停機的開始日期和時間。

    **開始於** 欄位會自動設您的名稱。

10. **實際開始** 欄位自動設為目前日期和時間。 但是，您可以根據需要變更該值。
11. 在 **附註** 欄位，輸入任何所需的附加註解。
12. 選擇 **確定**。

![建立維護要求。](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a>維護要求的後續處理

建立維護要求後，但在將其轉換為工單之前，應更新其中的各項資訊。 通常，規劃者或其他管理人員會完成此工作。

- 在 **所有維護要求** 或 **使用中維護要求** 頁面，選擇要處理的請求，然後選擇 **編輯**。

在詳細資訊檢視中，您可以更新各種資訊。 這裡有些範例：

- 選擇並驗證資產。 如果您之後必須選擇不同資產，您可以將 **資產驗證** 選項設為 **否**。
- 選擇負責的維護工作者群組和/或負責的維護工作者。 如需有關所需設定的詳細資訊，請參閱[負責的維修工作者](../setup-for-maintenance-requests/responsible-workers.md)。
- 選擇維護工作類型，如果此資訊有相關性，則選擇相關的維護工作變體和工作交易。
- 在 **緯度** 與 **經度** 欄位，輸入地理座標。 新增到維護要求的任何座標都會自動傳輸到相關的工單中。 

![更新維護要求。](media/04-manage-maintenance-requests.png)

> [!NOTE]
> 如果您在建立維護要求時選擇了一項資產，則可以向該資產新增一項異常。 建立維護要求後，您可以視需要新增更多異常。 如要新增異常，請在 **所有維護要求** 頁面上選擇 **資產異常**。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]