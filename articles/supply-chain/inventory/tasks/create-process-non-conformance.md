---
title: 創建和處理不符合項
description: 本主題說明，如何根據現有品質檢驗訂單，進行不符合項管理。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 032f5b712c2be5312524129cd25e655e778f5f44
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449358"
---
# <a name="create-and-process-nonconformances"></a>創建和處理不符合項

[!include [banner](../../includes/banner.md)]

本主題說明，如何根據現有品質檢驗訂單，進行不符合項管理。 通常，不符合項管理是由品管職員完成。 做為先決條件，您必須有可用的品質檢驗訂單。 (有關如何創建品質檢驗訂單的資訊，請參閱[檢查商品質量](inspect-quality-goods.md)。)

在使用者處理不符合項的批准之前，必須在 **使用者** 頁面上的 **人員** 欄位指派工作人員。 此外，在使用者可以使用文檔註釋之前，在他們使用者選項中的 **啟用文檔處理** 選項，必須設定為 *是*。

## <a name="create-a-nonconformance"></a>創建不符合項

若要建立不符合項，請遵循以下步驟。

1. 前往 **庫存管理 \> 定期任務 \> 品質管理 \> 不符合項**。
1. 在動作窗格上，選擇 **新建**。
1. 在 **創建不符合項** 對話框中，在 **問題類型** 欄位，選擇檢查過程中發現的問題類型。
1. 選擇 **確定**。

## <a name="approve-or-reject-a-nonconformance"></a>批准或拒絕不符合項

若要批准或拒絕不符合項，請遵循以下步驟。

1. 前往 **庫存管理 \> 定期任務 \> 品質管理 \> 不符合項**。
1. 在清單中，找到並選擇您要更新的不符合項。

    > [!NOTE]
    > 您只能對已批准的不合格項新增訂正。

1. 在操作窗格上，選擇 **功能 \> 批准不符合項**，以批准不符合項，或是 **功能 \> 拒絕不符合項** 以拒絕。 您可以將已批准的不符合項與[相關操作](../quality-operations.md)建立關聯。 這樣，您可以記錄已經更正和處理，完成部分不符合項的處理工作。
1. 系統會提示您確認選擇。 選擇 **是** 繼續。

## <a name="add-operations-and-other-details-to-nonconformances"></a>將操作和其他詳細資訊，新增到不符合項

創建不合格項後，您可以開始新增相關操作，並指定有關這些操作的其他資訊。 您只能對已批准的不符合項新增相關操作。

除了基本資訊之外，您還可以向操作新增以下詳細信息：

- **項目** – 您可以創建用於執行更正的項目列表。 例如，這些項目可能是維修設備所需的產品，或返工成品所需的成分。
- **品質費用** – 您可以創建一個由外部來源產生或計費的費用清單。
- **時間表** – 您可以創建每個工人在操作上花費的時間的日誌。

其餘設定都是可用選項。 每個項目的成本、品質費用和時間表都會匯總並顯示在操作中。 不能直接編輯 **成本** 欄位上的操作。

### <a name="create-an-operation-for-a-nonconformance"></a>為不符合項創建操作

若要建立不符合項的操作，請遵循以下步驟。

1. 前往 **庫存管理 \> 定期任務 \> 品質管理 \> 不符合項**。
1. 在清單中，找到並選擇您要更新的不符合項。

    > [!NOTE]
    > 您只能對已批准的不符合項新增或更新操作。

1. 在動作窗格上，選擇 **相關操作**。
1. 在 **相關操作** 頁面，在動作窗格上，選擇 **新增**，在網格中新增一列。 接著，在新的一列上，設定以下欄位：

    - **操作** – 選擇將對不符合項執行的操作代碼。
    - **原因** – 輸入詳細說明，解釋為什麼需要該操作。
    - **銷售訂單** – 如果所選操作代碼與銷售訂單類型相關，請選擇您要連結操作的銷售訂單。
    - **訂購單** – 如果所選操作代碼與訂購單類型相關，請選擇您要連結操作的訂購單。

1. 關閉頁面。

### <a name="add-items-to-an-operation"></a>將項目新增到操作

若要將項目新增到操作，請遵循以下步驟。

1. 前往 **庫存管理 \> 定期任務 \> 品質管理 \> 不符合項**。
1. 在清單中，找到並選擇您要更新的不符合項。

    > [!NOTE]
    > 您只能對已批准的不符合項新增或更新操作。

1. 在動作窗格上，選擇 **相關操作**。
1. 在 **相關操作** 頁面，選擇要新增項目的操作。
1. 在動作窗格上，選取 **品項**。
1. 在 **相關操作** 頁面，在動作窗格上，選擇 **新增**，在網格中新增一列。 接著，在新的一列上，設定以下欄位：

    - **項目編號** – 選擇將作為所選操作的一部分使用的產品。
    - **數量** – 輸入將要使用的物品數量。

    > [!NOTE]
    > 您可以在 **成本** 欄位的 **一般** 標籤上檢視成本。那裡顯示的成本來自於 **發布產品** 頁面的設定。 成本無法在 **相關操作項目** 頁面上直接更新。 所有新增到 **相關操作項目** 頁面上的項目，會自動新增到 **相關操作** 頁面上的 **成本欄位**。

1. 對必須新增的每個附加項目，重複上一步驟。
1. 關閉頁面。

### <a name="add-quality-charges-to-an-operation"></a>將品質費用新增到操作中

若要將品質費用新增到操作，請遵循以下步驟。

1. 前往 **庫存管理 \> 定期任務 \> 品質管理 \> 不符合項**。
1. 在清單中，找到並選擇您要更新的不符合項。

    > [!NOTE]
    > 您只能對已批准的不符合項新增或更新操作。

1. 在動作窗格上，選擇 **相關操作**。
1. 在 **相關操作** 頁面，選擇要新增品質費用的操作。
1. 在動作窗格上，選擇 **品質費用**。
1. 在 **相關操作收費** 頁面，在動作窗格上，選擇 **新增**，在網格中新增一列。 接著，在新的一列上，設定以下欄位：

    - **收費代碼** – 選擇您要新增的品質費用。
    - **說明** – 輸入費用的詳細說明。
    - **收費值** – 輸入費用金額。

1. 對必須新增的每個其他費用，重複上一步驟。
1. 關閉頁面。

> [!NOTE]
> **收費值** 欄位中的金額，會自動匯總所有品質費用，並新增到 **相關操作** 頁面的 **成本欄位**。

### <a name="create-a-timesheet-on-an-operation"></a>在操作上創建時間表

若要將時間表新增到操作，請遵循以下步驟。

1. 前往 **庫存管理 \> 定期任務 \> 品質管理 \> 不符合項**。
1. 在清單中，找到並選擇您要更新的不符合項。

    > [!NOTE]
    > 您只能對已批准的不符合項新增或更新操作。

1. 在動作窗格上，選擇 **相關操作**。
1. 在 **相關操作** 頁面，選擇要新增時間表的操作。
1. 在動作窗格上，選擇 **時間表**。
1. 在 **相關操作時間表** 頁面，在動作窗格上，選擇 **新增**，在網格中新增一列。 接著，在新的一列上，設定以下欄位：

    - **日期** – 指定工作完成的日期。 預設情況下，此欄位設置為當前日期。
    - **工人** – 選擇完成工作的工人。 預設情況下，此欄位設置為分配給當前使用者的工作人員。
    - **作業時數** – 輸入所選操作的工作小時數。
    - **已開發票** – 如果時間已在發票上計入客戶或供應商，請選中此復選框。

    > [!NOTE]
    > 您可以在 **成本** 欄位 **一般** 標籤上檢視成本。成本是使用您在 **庫存管理參數** 頁面上所定義的費率。

1. 對必須新增的每個其他時間表行，重複上一步驟。
1. 關閉頁面。

> [!NOTE]
> **成本** 欄位中的金額，會自動匯總所有質量費用，並新增到 **相關操作** 頁面的 **成本欄位**。

## <a name="add-a-correction-to-a-nonconformance"></a>新增不符合項的訂正

若要將訂正新增到操作，請遵循以下步驟。

1. 前往 **庫存管理 \> 定期任務 \> 品質管理 \> 不符合項**。
1. 在清單中，找到並選擇您要更新的不符合項。

    > [!NOTE]
    > 您只能對已批准的不合格項新增訂正。

1. 在動作窗格上，選擇 **訂正**。
1. 在 **訂正** 頁面，在動作窗格上，選擇 **新增**，在網格中新增一列。 接著，在新的一列上，設定以下欄位：

    - **診斷** – 選擇識別您正在創建的更正類型的診斷類型。
    - **工人** – 選擇負責訂正的人員。
    - **訂正優先級** – 選擇一個選項以指示應如何確定訂正的優先級 (*低*、*一般* 或 *高*)。
    - **申請日期** – 輸入要求採取訂正動作的日期。
    - **計劃日期** – 輸入預計完成更正的日期。
    - **短期解決方案** – 如果糾正措施僅在短時間內糾正不符合項，請選擇此核取方塊。

1. 關閉頁面。

## <a name="mark-a-correction-as-completed"></a>將訂正標記為已完成

若要將不符合項訂正標記為已完成，請遵循以下步驟。

1. 前往 **庫存管理 \> 定期任務 \> 品質管理 \> 不符合項**。
1. 在清單中，找到並選擇您要更新的不符合項。

    > [!NOTE]
    > 您只能對已批准的不合格項新增訂正。

1. 在動作窗格上，選擇 **訂正**。
1. 在 **訂正** 頁面，在網格中，選擇要標記為已完成的訂正。
1. 在動作窗格上，選擇 **標記為完成**。
1. 系統會提示您確認選擇。 選擇 **確定**，繼續。 這 **完成日期和時間** 欄位設置為當前日期和時間，並且選擇 **已完成** 核取方塊。
1. 關閉頁面。

## <a name="reopen-a-completed-correction"></a>重新打開已完成的訂正

若要重新打開已完成的訂正，請遵循以下步驟。

1. 前往 **庫存管理 \> 定期任務 \> 品質管理 \> 不符合項**。
1. 在清單中，找到並選擇您要更新的不符合項。
1. 在動作窗格上，選擇 **訂正**。
1. 在 **訂正** 頁面，在網格中，選擇要重新打開的訂正。
1. 在動作窗格上，選擇 **重新打開**。
1. 系統會提示您確認選擇。 選擇 **確定**，繼續。 該值會從 **完成日期和時間** 欄位清除，以及取消選擇 **已完成** 核取方塊。
1. 關閉頁面。

您現在可以對訂正進行其他編輯或更新。 完成後，您可以再次將訂正標記為已完成。

## <a name="close-a-nonconformance"></a>關閉不符合項

若要關閉不符合項，請遵循以下步驟。

1. 前往 **庫存管理 \> 定期工作 \> 品質管理 \> 品質檢驗訂單**。
1. 在網格中選擇一個品質檢驗訂單。
1. 在動作窗格上，選擇 **查詢 \> 不符合項**。
1. 在 **不符合項** 頁面，在網格中選擇目標不合格項。
1. 在動作窗格上，選擇 **功能 \> 關閉不符合項**。
1. 系統會提示您確認選擇。 選擇 **是** 繼續。
1. 關閉頁面。

## <a name="additional-resources"></a>其他資源

- [品質管理概觀](../quality-management-processes.md)
- [啟用品質和不符合項管理](../enable-quality-management.md)
- [負責批准不符合項的工人](../quality-responsible-workers.md)
- [不符合項隔離區](../quality-quarantine-zones.md)
- [不符合項的診斷類型](../quality-diagnostic-types.md)
- [不符合項的品質收費](../quality-charges.md)
- [不符合項操作](../quality-operations.md)
- [倉庫流程的品質管理](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
