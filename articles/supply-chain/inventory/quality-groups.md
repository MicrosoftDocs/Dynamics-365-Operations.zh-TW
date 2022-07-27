---
title: 品項品質群組
description: 本主題介紹如何使用和建立品項品質群組，以對產品進行邏輯分組，將其指派給品質關聯以自動產生品質檢驗訂單。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f7a4932c561c052bec1eb0094a390e315b9b1bb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449364"
---
# <a name="item-quality-groups"></a>品項品質群組

[!include [banner](../includes/banner.md)]

品質群組代表品項的常見測試要求。 本主題介紹如何使用和建立品項品質群組，以對產品進行邏輯分組，將其指派給品質關聯以自動產生品質檢驗訂單。

若要設定、編輯和查看指派給品質群組的品項，或指派給品項的品質群組，請移至 **庫存管理 \> 設定 \> 品質群組**。 您在 **測試群組** 頁面上定義測試要求後，就可以定義自動產生品質檢驗訂單的規則。 為了簡化流程，您無需為單一品項定義規則。 反之，您可以在 **品質關聯** 頁面上定義品質群組的規則。

## <a name="example-of-an-item-quality-group"></a>品項品質群組示例

一家製造公司採購多種原料，這些原料有相同的輸入檢查測試要求。 因此，公司定義了一個品質群組，然後將與原料相關的品項編號指派給該群組。 之後，公司採購了一種有相同檢測要求的新型原料。 公司沒有為新材料設定新的測試要求，而是將新材料的品項編號新增到現有的品質群組中。

此外，這家公司也生產有相同生產測試要求的品項，並裝運具有相同裝運前測試要求的品項。 因此，公司定義了兩個額外的品質群組，然後將相關的品項編號指派給每個群組。

## <a name="create-a-quality-group"></a>建立品質群組

若要建立品質群組，請遵循以下步驟。

1. 移至 **庫存管理 \> 設定 \> 品質控制 \> 品質群組**。
1. 在動作窗格上選取 **新增**，將資料列新增至格線。 接著，在新的一列上，設定以下欄位：

    - **品質群組**– 輸入品質群組的不重複識別碼或名稱。
    - **說明** – 輸入品質群組的詳細說明。

1. 關閉頁面。

## <a name="manually-add-items-to-a-quality-group"></a>手動將品項新增到品質群組

若要手動將品項新增到品質群組，請執行以下步驟。

1. 移至 **庫存管理 \> 設定 \> 品質控制 \> 品質群組**。
1. 選擇要新增品項的品質群組。
1. 在動作窗格上，選取 **品項**。
1. 在 **品質群組中的品項** 頁面，在動作窗格上，選擇 **新增**，在網格中新增一列。 然後，針對新列，將 **品項編號** 欄位設定為您要新增的品項編號。
1. 對必須新增的每個附加品項，重複上一步驟。
1. 關閉頁面。

## <a name="add-multiple-items-to-a-quality-group"></a>將多個品項新增到品質群組

若要將多個品項新增到品質群組，請執行以下步驟。

1. 移至 **庫存管理 \> 設定 \> 品質控制 \> 品質群組**。
1. 建立或選擇要新增品項的品質群組。
1. 在動作窗格上，選擇 **新增品項**。
1. 在 **詢問** 對話方塊中，輸入您要新增的品項的篩選準則。 例如，您可以篩選特定品項群組中的所有品項。
1. 選取 **確定**。
1. 在 **新增品項** 對話方塊中，網格會顯示與您的查詢相符的所有品項。 檢視結果。

    如需進行任何變更，請選擇 **選取** 回到 **查詢** 對話方塊，並調整您的查詢。

1. 如果結果包含您要新增的所有品項，請選取 **確定**。
1. 關閉頁面。

## <a name="manually-associate-an-item-with-a-quality-group"></a>手動將品項與品質群組建立關聯

若要手動將品項與品質群組建立關聯，請執行以下步驟。

1. 移至 **庫存管理 \> 設定 \> 品質控制 \> 品項品質群組**。
1. 在動作窗格上選取 **新增**，將資料列新增至格線。 接著，在新的一列上，設定以下欄位：

    - **品項編號** – 選擇要新增的品項編號。
    - **品質群組** – 選擇要指派給品項的品質群組。

1. 針對每個必須額外新增的品項和品質群組組合，重複上一步驟。
1. 關閉頁面。

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a>從已發佈產品頁面手動新增品質組合

若要手動從 **已發佈產品** 頁面手動新增品質群組，請執行以下步驟。

1. 請前往 **產品資訊管理 \> 產品 \> 已發佈的產品**。
1. 選擇要指派品質群組的產品。
1. 在動作窗格中的 **管理庫存** 索引標籤，在 **品質** 群組選擇 **品項品質群組**。
1. 在 **品質群組中的品項** 頁面，在動作窗格上，選擇 **新增**，在網格中新增一列。 然後，對於新列，將 **品質群組** 欄位設定成您要指派給產品的品質群組。
1. 對要指派給產品的每個額外品質群組，重複上一步驟。
1. 關閉頁面。

## <a name="additional-resources"></a>其他資源

- [品質管理測試群組儀器](quality-test-instruments.md)
- [品質管理測試](quality-tests.md)
- [品質管理測試群組](quality-test-groups.md)
- [品質管理測試群組變數](quality-test-variables.md)
- [品質關聯](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
