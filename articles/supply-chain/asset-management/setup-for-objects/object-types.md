---
title: 資產類型
description: 本主題說明如何在資產管理中建立資產類型。 此外還描述與資產類型相關的元素。
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectJobType, EntAssetObjectType, EntAssetObjectTypeDefaultSparePart, EntAssetObjectTypeDefaultSparePartApprove, EntAssetObjectTypeDefaultCreateCombinations, EntAssetObjectTypeDefault, EntAssetObjectTypeDefaultCopy
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fc1a8d98e9a8853e2e72bfcc7415ddb9a0a3b7758504621d6fccff00a08a36be
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446784"
---
# <a name="asset-types"></a>資產類型

[!include [banner](../../includes/banner.md)]



本主題說明如何建立資產類型。 此外還描述與資產類型相關的元素。 資產類型用作資產的一般類別。 例如 CNC 機器、測量設備和卡車引擎。 資產類型用於管理可為資產選擇的維護作業類型 (維護工作)、資產生命週期狀態、計數器、資產屬性、條件評估範本和資產模型。 您在建立資產時，必須指定資產類型。

對於每種資產類型，可以建立資產類型設定的變體。 例如，如果您有一個名為 **卡車** 的資產類型，您可以為不同的資產製造商和資產模型建立該資產類型的變體。 對於每個資產類型設定，您可以新增所需的備用零件和維護計劃。

首先，您設定所需的資產類型。 接下來，您建立應該與資產類型相關的資產模型。 最後，在 **資產類型預設值** 頁面上，您可以建立設備所需資產類型的所有變體。

## <a name="create-an-asset-type"></a>建立資產類型

1. 選擇 **資產管理** > **設定** > **資產類型** > **資產類型**。
2. 選擇 **新增** 建立資產類型。
3. 在 **資產類型** 欄位中，輸入資產類型識別碼。
4. 在 **名稱** 欄位中，輸入名稱。
5. 在 **資產生命週期模型** 欄位中，選擇資產生命週期模型。 如需資產生命週期狀態和資產生命週期模型的詳細資訊，請參閱[資產生命週期狀態](object-stages.md)。
6. 如果應為具有此資產類型的資產計算彙總的關鍵績效指標 (KPI) 值，請將 **總計** 選項設定為 **是**。
7. 請選取 **儲存**。
8. 在 **維護作業類型** FastTab 上，選取應與資產類型相關的維護作業類型：

    - 若要選取維護作業類型，請在 **剩餘的維護作業類型** 欄位中選取該類型，然後選取向右箭號按鈕![向右箭號按鈕。](media/29-setup-for-objects.png) 將其移至 **選取的維護作業類型** 區段。
    - 若要選取所有可用的維護作業類型，請選取![所有箭號向前。](media/30-setup-for-objects.png) 按鈕。 所有維護作業類型都從 **剩餘的維護作業類型** 欄位轉移 **選取的維護作業類型** 欄位。
    - 若要取消選取維護作業類型，請在 **選取的維護作業類型** 欄位中選取該類型，然後選取向左箭號按鈕![向左箭號按鈕。](media/31-setup-for-objects.png) 將其移至 **剩餘的維護作業類型** 欄位。

9. 您也可以選取應該與資產類型相關的計數器。 在 **計數器** FastTab 上，使用步驟 8 中針對維護作業類型描述的方法進行選擇。 如需計數器設定的詳細資訊，請參閱[計數器](counters.md)。
10. 您也可以選取應該與資產類型相關的屬性類型。 在 **屬性類型** FastTab 上，使用步驟 8 中針對維護作業類型描述的方法進行選擇。 然後，若要建立偏好的屬性類型順序，請在 **選取的屬性類型** 欄位中選取一個屬性類型，然後使用向上箭號和向下箭號按鈕移動它。 屬性類型的順序將顯示在使用此資產類型的資產上。 如需資產屬性的詳細資訊，請參閱[維護屬性類型](../setup-for-functional-locations/specification-types.md)。

    > [!NOTE]
    > 當您在 **屬性類型** FastTab 上新增新屬性類型時，會自動以該資訊更新現有資產。

11. 您也可以選取應該與資產類型相關的條件評估範本。 在 **條件評估** FastTab 上，使用步驟 8 中針對維護作業類型描述的方法進行選擇。 如需條件評估範本和註冊的詳細資訊，請參閱[條件評估](../setup-for-objects/condition-assessment.md)。
12. **資產模型** FastTab 會顯示在所選資產類型上設定的資產製造商和模型的所有組合。 若要查看根據製造商劃分的組合，請選取 **資產模型**，然後開啟 **資產模型** 頁面。

    在 **資產模型** 頁面上，您可以新增資產模型-資產類型關係。 此外，在 **資產類型** 頁面，您可以將資產製造商-資產模型關係直接新增到資產類型。 最後，在 **資產模型** 頁面上 (**資產管理**\>**設定**\>**資產**\>**資產模型**)，您可以建立新的資產製造商-資產模型-資產類型關係。 因此，有三種方式可設定和編輯資產製造商-資產模型-資產類型關係。 系統會從不同的觀點顯示所有可用的組合，您可以在使用設定時選擇您偏好的進入點。

> [!NOTE]
> - 如果您在資產類型上選取計數器，則會在 **計數器** 頁面 (**資產管理** > **設定** > **資產** > **資產類型** > **計數器**) 上自動更新所做的選擇。
> - 在 **一般** FastTab 上 **詳細資料** 區段中的欄位會顯示在所選資產類型上設定的維護作業類型、計數器、屬性等數目。

通常，手動建立的工單會與修正性維護相關，而自動建立的工單會與預防性維護相關。 當您手動建立工單時，只會使用在 **資產類型** 頁面其 **維護作業類型** FastTab 上選取的維護作業類型。 但是，自動建立的工單可以使用您在 **維護作業類型** 頁面 (**資產管理**\>**設定**\>**作業**\>**維護作業類型**) 上建立的所有維護作業類型。

## <a name="create-asset-type-setup-lines"></a>建立資產類型設定明細

1. 選取 **資產管理**\>**設定**\>**資產**\>**資產類型**\>**資產類型設定**。 或者，選取 **資產管理**\>**設定**\>**資產**\>**資產類型**\>**資產類型**，選取資產類型，然後選取 **資產類型設定**。
2. 第一次使用 **資產類型設定** 頁面時，您可能會發現 **建立組合** 按鈕很有用。 您可以使用此按鈕在資產類型上快速建立資產模型的所有組合。 選取 **建立組合**，選取要建立其組合的資產類型，然後選取 **確定**。

    > [!NOTE]
    > 如果您不要使用所有自動建立的資產類型設定組合，可以將設定刪除，方法是選取該設定，然後選取 **刪除**。

3. 選取 **新增** 手動建立資產類型設定。
4. 根據資產類型設定的具體程度，在 **資產類型**、**製造商** 和 **模型** 欄位中進行選擇。
5. 如果保固協議與資產類型相關，請在 **供應商保個** 和 **客戶保固** 欄位中選取該協議。 
6. 在 **備用零件** FastTab 上，選取 **新增** 將備用零件新增至所選的資產類型設定。
7. 若要核准備用零件，請選取備用零件明細，然後選取 **核准**。 您可以選取多個明細進行核准。
8. 若要查看備用零件是否在資產管理中的其他地方使用 (例如，與資產和工單相關)，請選取備用零件，然後選取 **使用的項目** 以開啟 **使用的項目** 頁面。 若要查看清單中所有的使用中備用零件，請選取 **使用中** 核取方塊。 若僅查看核准的備用零件，請選取 **已核准** 核取方塊。
9. 在 **維護計劃** FastTab 上，選取 **新增** 將維護計劃新增至所選的資產類型設定。
10. 若要將資產類型設定複製到另一個設定，您可以使用複製功能。 選取要將設定複製到的資產類型設定，選取 **複製設定**，然後選取要複製其設定的資產類型設定。 各種選項的設定決定了所包含的資訊量。 完成後，選取 **確定** 複製設定。

> [!NOTE]
> 如果您有許多要重複使用的備用零件明細和維護計劃明細，則複製功能可讓您快速輕鬆地為許多資產類型設定組合設定資料。

## <a name="spare-parts-on-the-asset-type-setup"></a>資產類型設定上的備用零件

如「建立資產類型設定明細」一節所述，會在 **資產類型設定** 頁面的資產模型上設定備用零件。 因此，當您開啟 **資產類型設定** 頁面時，您只會看見與所選的資產類型、資產製造商和資產模型組合相關的備用零件。 若要查看所有的備用零件記錄清單，請開啟 **備用零件** 頁面 (**資產管理**\>**查詢**\>**備用零件**)。

在 **備用零件** 頁面上，您還可以為資產類型、資產製造商和資產模型的現有組合建立新的備用零件。 您可以決定您偏好在 **資產類型設定** 頁面還是在 **備用零件** 頁面上建立備用零件記錄。 **資產類型設定** 頁面提供所選的資產類型、資產製造商和資產模型組合的資料概觀，而 **備用零件** 頁面則提供所有資產類型設定明細的完整概觀。 如果 **備用零件** 頁面包含許多記錄，則 **資產類型設定** 頁面可提供更佳的概觀。

若要查看所選明細上的備用零件是否在資產管理中的其他地方使用 (例如，與資產和工單相關)，請選取 **使用的項目** 以開啟 **使用的項目** 頁面。 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]