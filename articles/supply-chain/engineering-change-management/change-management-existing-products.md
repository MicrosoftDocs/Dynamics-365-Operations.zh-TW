---
title: 對現有產品啟用變更管理
description: 本主題說明如何為現有產品啟用變更管理。 它還說明了在哪些情況下，會限制啟用變更管理。
author: t-benebo
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-02
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: e356ef8339f8f71965bf9313e14fed3d0810152d
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450015"
---
# <a name="enable-change-management-on-existing-products"></a>對現有產品啟用變更管理

[!include [banner](../../includes/banner.md)]

本主題說明如何為現有產品啟用變更管理。 它還說明了在哪些情況下，會限制啟用變更管理。

當您為現有產品啟用變更管理時，您可以建立該產品的版本並追蹤在其整個生命週期中對其做的更改。 因此，您可以使用變更單來追蹤這些變更。 若要啟用變更管理，您必須將相關產品轉換為 *工程品項* (也稱為工程產品)。 工程產品是以變更管理進行版本化及管理的產品。 並提供了一個精靈來帶領您完成轉換過程。

## <a name="turn-this-feature-on-or-off"></a>開啟或關閉這項功能

本主題中說明的功能，必須在系統中打開功能 *工程變更管理* 和 *對現有產品啟用變更管理*。 更多關於如何打開或關閉這些功能的詳細資訊，請參閱[工程變更管理概述](product-engineering-overview.md)。

## <a name="restrictions-and-limitations"></a>限制

並非所有產品類型都可以轉換為所有其他類型。 具有以下限制：

- 當您將產品轉換為工程產品時，它仍然是 *產品*。 它不會成為一個 *基準產品*。
- 當您轉換具有一組特定維度的基準產品時，這些維度會在變更後保留。 例如，如果您轉換具有尺寸維度的基準產品，它將保留尺寸維度。

因此，如果您有一個獨特產品，更改為工程產品後，將不追蹤交易中的產品維度 (即不使用版本維度)。 更多有關這些問題的資訊，請參閱本主題的其餘區段。

## <a name="prepare-for-conversion-by-creating-all-required-engineering-product-categories"></a>請建立所有必須的工程產品類別，準備進行轉換

*工程產品類別* 必須指派給每個工程產品。 在執行 **轉換為工程產品** 精靈時，您將進行指派。 對於所有相關標準產品，都必須 *先* 存在工程產品類別，您才可以轉換這些產品。

工程產品類別為建立工程產品提供了基礎，它建立了一組預設值和原則。 工程屬性及其預設值 (為工程類別定義)也套用在其工程產品上。 您可以根據需要對受影響產品編輯屬性值和/或新增更多工程屬性。

工程產品類別必須與您指派給它的產品相相符。 例如，產品類型和維度群組必須與產品及其工程產品類別相符合。 如需詳細資訊，請參閱[工程版本與工程產品類別](engineering-versions-product-category.md)。

> [!IMPORTANT]
> **轉換為工程產品** 精靈將產品轉換為工程產品後，該工程產品在交易中沒有進行版本追踪。 因此，為轉換現有產品而建立的工程產品類別，其中的 **追蹤交易中的版本** 選項必須設定為 *否*。

有關如何建立工程產品類別的資訊，請參閱[工程版本和工程產品類別](engineering-versions-product-category.md).

## <a name="run-the-convert-to-engineering-product-wizard"></a>執行轉換為工程產品精靈

**轉換為工程產品** 精靈可以協助將一種或多種現有產品轉換為工程產品。 它將產品轉換為工程產品(版本化產品)，並且該工程產品在交易中不追蹤版本 (即不使用版本維度)。 轉換完成後，您可以使用工程變更管理來管理產品。

轉換是永久性的。 因此，您以後將無法註銷轉換。 

每個轉換後的工程產品將在發佈原始產品的同一公司中維持發佈狀態。 但是，工程物料清單 (BOM) 和途程不會自動發佈給這些公司。

按照以下步驟執行 **轉換為工程產品** 精靈，將產品轉換為工程產品。

1. 請前往 **產品資訊管理 \> 產品 \> 已發佈的產品**。
1. 在網格中，為您要轉換的每個產品選取核取方塊。
1. 在動作窗格上，在 **工程師** 索引標籤，到 **工程變更管理** 群組，請選取 **轉換為工程產品**，打開精靈。
1. 精靈的第一頁是 **歡迎** 頁面。 如果您還不熟悉轉換過程，請仔細閱讀此頁面上的資訊。 當您準備好繼續時，選取 **下一頁**。
1. **為要轉換的產品選取詳細資料** 頁面顯示您在打開精靈之前選定的每個產品。 檢查列表。 依據您的需求，使用工具列上的 **新增** 和 **刪除** 按鈕，新增或移除產品。
1. 到網格頂部，使用以下欄位為列出的每個產品指派預設值。 (在轉換完成後，能夠對單個產品更改這些值。) 預設值不會指派給相關值已指派的產品。

    - **預設工程類別**– 選取一個初始工程產品類別以指派給每個列出的產品。 您選取的類別將僅套用在與其相容的產品。
    - **預設版本**–輸入初始產品版本，指派給每個列出的產品。 每個工程產品至少有一個工程版本。
    - **預設生命週期狀態**–選取初始產品生命週期狀態，指派給每個列出的產品。
    - **當前 BOM 將成為工程產品的一部分**–如果每個列出的產品其當前 BOM 都應該用作工程產品的 BOM，請選取此核取方塊。

    有關產品設定的詳細資訊，請參閱下一步驟。

1. 檢閱網格中列出的每個產品，並評估已指派的預設值對其適用的程度。 對於每一列，檢閱以下資訊並設定所有相關欄位：

    - **產品編號** – 產品編號。
    - **產品名稱** – 產品名稱。
    - **工程類別**–選取產品轉換後所屬的工程產品類別。 每個產品都必須存在適當的類別，如本主題的前一部分所述。 必須為每個產品指派一個類別。
    - **版本**–輸入產品版本，指派給完成轉換後的產品。 例如，您可以選取一個與類別使用的數字序列相容的數字。 每個工程版本都儲存該版本的專屬工程相關資料。 如需詳細資訊，請參閱[工程版本與工程產品類別](engineering-versions-product-category.md)。
    - **產品生命週期狀態**–選取產品在轉換後應處於的產品生命週期狀態。 產品生命週期狀態讓您能控制在指定工程版本中哪些交易是允許的。 有關詳細資訊，請參閱[產品生命週期狀態和交易](product-lifecycle-state-transactions.md)。
    - **有 BOM**–核取方塊選定表示產品具有 BOM。 此核取方塊的設定可以幫助您決定如何設定 **當前 BOM 將成為工程產品的一部分** 核取方塊。
    - **當前 BOM 將成為工程產品的一部分**–如果產品的當前 BOM 應該用作工程產品的 BOM，請選取此核取方塊。 然後，該 BOM 將由工程變更管理進行管理。 如果產品沒有 BOM，或者您希望稍後為轉換後的產品手動建立 BOM，請清除此核取方塊。
    - **有錯誤**– 核取方塊選定表示產品設定有一個或多個錯誤。 例如，產品類型或維度組在類別中可能不相符。 有錯誤的產品將被跳過並且不會被轉換。

1. 完成後，選取 **驗證** 以驗證產品設定。 對於每一列，將更新 **有錯誤** 核取方塊以指示產品的狀態。 調整這些值，直到每個產品的設定都沒有錯誤。
1. 正確設定所有產品後，選擇 **下一頁** 繼續。
1. **確認選擇** 頁面顯示設定中沒有錯誤並且可以轉換的產品數量。 它還顯示了因錯誤而被跳過的產品數量。 若要將轉換以批處理作業執行，請將 **批量執行** 選項設定為 *是的*。
1. 選取 **結束** 套用您的設定並開始將產品轉換為工程產品。

> [!NOTE]
> 如果您的系統設定必須在產品發布之前手動接受產品，則您必須使用在相應公司的 **未結產品發佈** 頁面，接受每個轉換後的產品。 更多詳細資料，請參閱[在區域公司發佈產品之前，請審閱並接受產品](engineering-scenarios.md#accept)。
