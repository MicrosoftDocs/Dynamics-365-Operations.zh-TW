---
title: 狀態評量
description: 本主題說明在資產管理中如何建立狀態評量範本並登記。
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectCondition, EntAssetConditionTemplate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cced322dd2f213d8e6025d853edc8472618989b61de7139b28ba1c6bffd3ad2a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446844"
---
# <a name="condition-assessment"></a>狀態評量

[!include [banner](../../includes/banner.md)]

 

本主題說明在資產管理中如何建立狀態評量範本並登記。 定期進行狀態評量，主要目標是建立和維護資產狀態資料。 從預防性維護的角度來說，監控當前狀態和剩餘壽命等關鍵資訊非常重要。 此外，如果您定期進行狀態評量，您將能夠監控工廠中的機器並比較狀態。

狀態評量可用於測量和監控設備上的許多狀態。 例如：您可以測量機器的振動。 在資產管理中為各種類型的設備登記振動測量後，您可以搜尋最近登記的評估並查看其振動測量。

狀態評量是建立在資產上的。 在執行狀態評量程序之前，您可以在資產類型上設定狀態評量範本。 使用範本進行狀態評量的原因是為了避免類似資產的狀態資料出現差異。 在資產管理中設定和使用狀態評量的順序是：首先設定必要的條件狀態範本。 接著，將範本與 **資產類型** 表單中的資產類型相關聯。 最後，您可以在 **資產** 表單內的資產上建立資產評量登記。

## <a name="create-a-condition-assessment-template"></a>狀態評量範本識別碼

1. 選取 **資產管理** > **設定** > **資產類型** > **狀態評量**。
2. 選取 **新增** 以建立新範本。
3. 在 **範本** 欄位插入範本識別碼。
4. 在 **名稱** 欄位中插入範本名稱。
5. 在 **狀態評量明細** FastFab，新增狀態評量必要的明細，包括選擇適當的狀態類型和測量單位。
6. 在 **資產類型** FastTab，新增應使用狀態評量的資產類型。
7. 在螢幕上方的 **詳細資料** 群組中，在 **明細** 和 **資產類型** 欄位，您將看到與選定狀態評量範本相關的評量明細數量和資產類型。


## <a name="create-condition-assessment-registration-on-an-asset"></a>在資產上建立狀態評量明細登記

1. 選取 **資產管理** > **一般** > **資產** > **全部資產**。
2. 在清單中，選取您要為其建立狀態評量登記的資產。
3. 在 **一般** 索引標籤上，按一下 **狀態評量**。
4. 按一下 **新增** 進行新的登記。
5. 在 **日期** 欄位中，選取狀態評量的日期。
6. 在 **工作人員** 欄位，選取進行評量登記的工作人員名稱。
7. 在 **明細** 欄位，您會看到在狀態評量上設定的評量明細數量。
8. 在 **範本** 欄位中，選取狀態評量的範本。 範本名稱會自動插入 **名稱** 欄位，並且相關的登記明細會被插入到 **狀態評量明細** FastTab。
9. 您可以在 **附註** FastTab 中，插入與選定狀態評量相關的附註。
10. 對於每個狀態評量明細，將測量資料插入 **值** 欄位。
11. 您可以在 **狀態評量明細** FastTab >**註解** 欄位中，插入與選定登記明細相關的註解。 如果您在一個明細上新增註解，則 **註解** 核取方塊會自動選取。

對資產完成狀態評量登記後，您可以列印狀態評量報告。

>[!NOTE]
>您還可以在工單上登記狀態評量 (**資產管理** > **一般** > **工單** > **所有工單** > **狀態評量** 按鈕。)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]