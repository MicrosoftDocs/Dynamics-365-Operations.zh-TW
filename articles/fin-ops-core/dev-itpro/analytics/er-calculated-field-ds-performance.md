---
title: 透過新增參數化的導出欄位資料來源來提高 ER 解決方案的效能
description: 本主題說明如何透過新增參數化的導出欄位資料來源來幫助提高電子報表 (ER) 解決方案的效能。
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5fada2fc0b35e22da18f5d6a0505df077d5ada4e0221031d63c316d8c705bc79
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460248"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a>透過新增參數化的導出欄位資料來源來提高 ER 解決方案的效能

[!include [banner](../includes/banner.md)]

本主題解釋了如何對執行的 [電子報表 (ER)](general-electronic-reporting.md) 格式進行 [效能追蹤](trace-execution-er-troubleshoot-perf.md)，然後利用這些跟蹤的資訊，透過設定參數化的 **導出欄位** 資料來源來幫助提高效能。

作為設計 ER 設定以產生商業文件的過程的一部分，您定義用於從應用程式取出資料並將其輸入到產生的輸出中的方法。 透過設計參數化的 ER 資料來源 **導出欄位** 類型，您可以減少資料庫調用的次數，並顯著減少收集 ER 格式執行細節所涉及的時間和成本。

## <a name="prerequisites"></a>先決條件

- 若要完成本主題中的範例，您必須有權存取以下[角色](../sysadmin/tasks/assign-users-security-roles.md)之一：

    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

- 該公司必須設定為 **DEMF**。
- 按照本主題[附錄 1](#appendix1) 的步驟，下載完成本主題中的範例所需的 Microsoft ER 解決方案的組件。
- 按照本主題[附錄 2](#appendix2) 的步驟，設定使用 ER 架構所需的最小 ER 參數集，以幫助提高 Microsoft ER 解決方案樣本的效能。

## <a name="import-the-sample-er-solution"></a>匯入範例 ER 解決方案

想像一下，您必須設計 ER 解決方案來產生顯示廠商交易的新報告。 現行，您可以在 **廠商交易** 頁面上找到所選廠商的交易 (進入 **應付帳款**\>**廠商**\>**所有廠商**，選取廠商，然後，在動作窗格上，在 **廠商** 索引標籤上，在 **交易** 組中，選取 **交易**)。 但是，您希望將所有廠商交易集中在一個 XML 格式的電子文件中。 該解決方案將包含多個 ER 設定，其中包含所需的資料模型、模型對應和格式組件。

第一步是匯入範例 ER 解決方案以產生廠商交易報告。

1. 登入到為您公司提供的 Microsoft Dynamics 365 Finance 的執行個體。
2. 在此主題中，您將建立和修改 **Litware, Inc.** 樣本公司的所需的 ER設定。 確保此設定提供者已新增到您的 Finance 執行個體並標記為有效。 更多資訊，請參閱[建立組態提供者並標示為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)。
3. 在 **電子報表** 工作區中，選取 **報告設定** 圖格。
4. 在 **設定** 頁面，將您作為前提條件下載的 ER 設定匯入 Finance，順序如下：資料模型、模型對應、格式。 對於每個設定，請執行以下步驟：

    1. 在動作窗格上，選取 **交換**\>**從 XML 檔案載入**。
    2. 選取 **瀏覽**，並為 XML 格式的 ER 設定選取適當的文件。
    3. 選取 **確定**。

![在設定頁面上匯入設定。](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a>審查樣本 ER 解決方案

### <a name="review-the-model-mapping"></a>查看模型對應

1. 在 **設定** 頁面，在設定樹狀結構中，展開 **效能改進模型**，並選取 **效能改善對應**。
2. 在動作窗格上，選取 **設計工具**。
3. 在 **對資料來源對應建模** 頁面上，在動作窗格上，選取 **設計工具**。

    此 ER 模型對應旨在執行以下操作：

    - 擷取儲存在 VendTrans 表中的廠商交易清單 (**Trans** 資料來源)。
    - 對於每筆交易，從 VendTable 表中擷取已過帳交易的廠商的記錄 (**\#Vend** 資料來源)。

    > [!NOTE]
    > **\#Vend** 資料來源被設定為透過使用現有的多對一關係 **\@\>Relations'.VendTable\_AccountNum** 來擷取相應的廠商記錄。

    此設定中的模型對應為為此模型建立並在 Finance 中執行的任何 ER 格式實施基本資料模型。 因此，**Trans** 資料來源的內容針對抽像 **模型** 資料來源等 ER 格式公開。

    ![模型對應設計工具頁面上的 Trans 資料來源。](media/er-calculated-field-ds-performance-mapping-1.png)

4. 關上 **模型對應設計工具** 頁面。
5. 關閉 **資料來源對應的模型** 頁面。

### <a name="review-format"></a>審查格式

1. 在 **設定** 頁面，在設定樹狀結構中，展開 **效能改進模型**，並選取 **效能改善格式**。
2. 在動作窗格上，選取 **設計工具**。
3. 在 **格式設計工具** 頁面上，在 **對應** 索引標籤上，選取 **展開/折疊**。
4. 展開 **模型**、**資料，** 和 **交易** 項目。

    此 ER 格式旨在產生 XML 格式的廠商交易報告。

    ![格式設計工具頁面上的格式資料來源和設定的格式元素的繫結。](media/er-calculated-field-ds-performance-format.png)

5. 關上 **格式設計工具** 頁面。

## <a name="run-the-sample-er-solution-to-trace-execution"></a>執行樣本 ER 解決方案以追蹤執行

想像一下，您已經完成了 ER 解決方案的第一個版本的設計。 您現在想要在 Finance 執行個體中測試解決方案並分析執行效能。

### <a name="turn-on-the-er-performance-trace"></a>打開 ER 效能追蹤

1. 選取 **DEMF** 公司。
2. 按照[打開 ER 效能追蹤](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace)中的步驟在執行 ER 格式時產生效能追蹤。

    ![使用者參數對話方塊。](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a>執行 ER 格式

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面，在設定樹狀結構中，選取 **效能改善格式**。
3. 在動作窗格中，選取 **執行**。

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a>使用效能追蹤分析模型對應效能

1. 在 **設定** 頁面，在設定樹狀結構中，選取 **效能改善對應**。
2. 在動作窗格上，選取 **設計工具**。
3. 在 **模型對應** 頁面上，在動作窗格上，選取 **設計工具**。
4. 在 **模型對應設計工具** 頁面上，在動作窗格上，選取 **效能追蹤**。
5. 選取最近產生的追蹤，然後選取 **確定**。

新資訊現在可用於現行模型對應的某些資料來源項目：

- 使用資料來源取得資料所花費的實際時間
- 相同的時間表示為執行整個模型對應所花費的總時間的百分比

![模型對應設計工具頁面上的執行時間詳情。](./media/er-calculated-field-ds-performance-mapping-2.png)

這 **效能統計** 格線顯示，**Trans** 資料來源調用 VendTrans 表一次。 **Trans** 資料來源的值 **\[265\]\[Q:265\]** 表示已經從申請表中擷取了 265 個廠商交易並返回到資料模型。

這 **效能統計** 格線還顯示現行模型對應重複了資料庫要求，同時執行 **\#Vend** 資料來源。 出現這種重複的原因如下：

- 對於 265 次迭代的廠商交易，每次調用廠商表兩次，總共 530 次調用：

    - 撥打一通電話以輸入廠商帳號。
    - 撥打一通電話以輸入廠商名稱。

- 即使只為五個廠商過帳擷取的交易，也會為每個迭代的廠商交易調用廠商表。 在 530 個調用中，有 525 個是重複的。 下圖顯示了您收到的有關重複調用 (資料庫要求) 的訊息。

![模型對應設計工具頁面上有關重複資料庫要求的訊息。](./media/er-calculated-field-ds-performance-mapping-2a.png)

在模型對應的總執行時間 (大約 8 秒) 中，請注意超過 80% (大約 6 秒) 用於從 VendTable 應用程式表中提取值。 與 VendTrans 應用程式表中的資訊量相比，該百分比對於五個廠商的兩個屬性來說太大了。

為了減少為獲取每個交易的廠商詳情而進行的調用次數，並提高模型對應的效能，您可以將快取用於 **\#Vend** 資料來源。

> [!NOTE]
> **Trans\\\#Vend** 資料來源將在執行階段快取在 **Trans** 資料來源的現行交易範圍內。

透過快取 **\#Vend** 資料來源，可以將重複調用的數量從 525 減少到 260，但並不能完全消除重複。 為了完全消除重複，您可以設定新的參數化資料來源 **導出欄位** 類型。

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>根據來自執行追蹤的資訊改善模型對應

### <a name="change-the-logic-of-the-model-mapping"></a>更改模型對應的邏輯

按照這些步驟來使用快取和 **導出欄位** 類型的資料來源，以幫助防止重複調用資料庫。

1. 在 **設定** 頁面，在設定樹狀結構中，選取 **效能改善對應**。
2. 在動作窗格上，選取 **設計工具**。
3. 在 **模型對應** 頁面上，在動作窗格上，選取 **設計工具**。
4. 在 **模型對應設計工具** 頁面，按照以下步驟新增資料來源 **資料表記錄** 類型以存取 VendTable 應用程式表中的記錄：

    1. 在 **資料來源類型** 窗格中，展開 **Dynamics 365 for Operations**，並選取 **資料表記錄**。
    2. 選取 **新增根**。
    3. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **Vend**。
    4. 在 **資料表** 欄位中，輸入 **VendTable**。
    5. 選取 **確定**。

5. 只有當 **導出欄位** 類型的資料來源駐留在容器中時，您才能對這些資料來源進行參數化調用。 因此，請按照以下步驟新增 **空白容器** 類型的資料來源，以容納 **導出欄位** 類型的新參數化資料來源。

    1. 在 **資料來源類型** 窗格中，展開 **一般**，並選取 **空白容器**。
    2. 選取 **新增根**。
    3. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **Box**。
    3. 選取 **確定**。

    ![模型對應設計工具頁面上的 Box 資料來源。](./media/er-calculated-field-ds-performance-mapping-3.png)

6. 按照這些步驟，新增 **導出欄位** 類型的參數化資料來源：

    1. 在 **資料來源** 窗格中，選取 **Box**。
    2. 在 **資料來源類型** 窗格中，展開 **函數**，並選取 **導出欄位**。
    3. 選取 **新增**。
    4. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **Vend**。
    5. 選取 **編輯公式**。
    6. 在 **公式設計工具** 頁面上，選取 **參數** 指定調用此資料來源時必須提供的參數。
    7. 在 **參數** 對話方塊中，選取 **新建**。
    8. 在 **名稱** 欄位中，輸入 **parmVendAccNumber**。
    9. 在 **類型** 欄位中，選取 **字串**。
    10. 選取 **確定**。
    11. 在 **公式** 欄位中，輸入 **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**。
    12. 選取 **儲存**，關閉 **公式設計工具** 頁面。
    13. 選取 **確定** 以新增新資料來源。

7. 按照以下步驟在執行期間將新增的資料來源標記為快取：

    1. 在 **資料來源** 窗格中，選取 **Box\\Vend**。
    2. 選取 **快取**。

    > [!NOTE]
    > **Box\\Vend** 資料來源在執行階段將被快取在 **Trans** 資料來源的所有廠商交易範圍內。

8. 按照以下步驟更新巢狀 **Trans\\\#Vend** 資料來源，以便它使用 **Box\\Vend** 資料來源：

    1. 在 **資料來源** 窗格中，展開 **Trans**。
    2. 選取 **Trans\\\#Vend** 資料來源，然後選取 **編輯**\>**編輯公式**。
    3. 在 **公式設計工具** 頁面上，在 **公式** 欄位中，輸入 **Box.Vend(\@.AccountNum)**。
    4. 選取 **儲存**，然後關閉 **公式設計工具** 頁面。
    5. 選取 **確定** 完成對所選資料來源的更改。

9. 選取 **儲存**。

    ![模型對應設計工具頁面上的 Vend 資料來源。](./media/er-calculated-field-ds-performance-mapping-4.png)

10. 關上 **模型對應設計工具** 頁面。
11. 關上 **模型對應** 頁面。

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>完成 ER 模型對應設定的修改版本

1. 在 **設定** 頁上，在 **版本** FastTab 上，選取 **效能改善對應設定** 的 **1.2** 版。
2. 選取 **更改狀態**\>**完成**，然後選取 **確定**。

## <a name="run-the-modified-er-solution-to-trace-execution"></a>執行修改好的 ER 解決方案以追蹤執行

重複本主題前面[執行 ER 格式](#run-format)區段中的步驟以產生新的效能追蹤。

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a>使用效能追蹤來分析對模型對應的調整 

1. 在 **設定** 頁面，在設定樹狀結構中，選取 **效能改善對應**。
2. 在動作窗格上，選取 **設計工具**。
3. 在 **模型對應** 頁面上，在動作窗格上，選取 **設計工具**。
4. 在 **模型對應設計工具** 頁面上，在動作窗格上，選取 **效能追蹤**。
5. 選取最近產生的追蹤，然後選取 **確定**。

請注意，您對模型對應所做的調整已經消除了對資料庫的重複查找。 此模型對應對資料庫表和資料來源的調用次數也減少了。

![模型對應設計工具第 1 頁上的追蹤資訊。](./media/er-calculated-field-ds-performance-mapping-5.png)

總執行時間減少了大約 20 倍 (從大約 8 秒到大約 400 毫秒)。 因此，整個 ER 解決方案的效能得到了提高。

![模型對應設計工具第 2 頁上的追蹤資訊。](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a>附錄 1：下載樣本 Microsoft ER 解決方案的組件

您必須下載以下文件並將其儲存在本地。

| 檔案                                        | 內容 |
|---------------------------------------------|---------|
| 效能改善 model.version.1     | [樣本 ER 資料模型設定](https://download.microsoft.com/download/4/6/f/46f0f3fa-782b-414a-8f7b-b6c64a388661/Performance_improvement_model.version.1.xml) |
| 效能改善 mapping.version.1.1 | [樣本 ER 模型對應設定](https://download.microsoft.com/download/8/9/1/8913a763-afb8-4bf4-aaf1-95ad793ffc5a/Performance_improvement_mapping.version.1.1.xml) |
| 效能改善 format.version.1.1  | [樣本 ER 格式設定](https://download.microsoft.com/download/9/0/c/90c75963-bc78-4edc-9096-556bbe281f10/Performance_improvement_format.version.1.1.xml) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a>附錄 2：設定 ER 架構

在開始使用 ER 架構來提高樣本 Microsoft ER 解決方案的效能之前，您必須設定最小的 ER 參數集。

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>設定 ER 參數

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **電子報表參數**。
3. 在 **電子報表參數** 頁的 **一般** 索引標籤上，將 **啟用設計模式** 選項設定為 **是**。
4. 在 **附件** 索引標籤上設定下列參數：

    - 在 **設定** 欄位中，選取 **文件** 類型為 **DEMF** 公司。
    - 在 **作業封存**、**臨時**、**基準** 和 **其他** 欄位中，選取 **檔案** 類型。

如需 ER 參數的相關資訊，請參閱[設定 ER 架構](electronic-reporting-er-configure-parameters.md)。

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>啟用 ER 設定提供者

新增的每個 ER 設定都被標記為歸 ER 設定提供者所有。 在 **電子報表** 工作區中啟用的 ER 設定提供者用於此目的。 因此，您必須先在 **電子報表** 工作區中啟用 ER 設定提供者，然後才能開始新增或編輯 ER 設定。

> [!NOTE]
> 只有 ER 設定的擁有者可以編輯該設定。 因此，在可以編輯 ER 設定之前，必須在 **電子報表** 工作區中啟動相應的 ER 設定提供者。

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>查看 ER 設定提供者清單

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **設定提供者**。
3. 在 **設定提供者資料表** 頁面，每個設定提供者記錄都有一個唯一的名稱和 URL。 查看此頁面的內容。 如果 **Litware, Inc.** 的記錄已經存在，跳過下一個過程，[新增新的 ER 設定提供者](#ActivateProvider)。

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>新增新的 ER 設定提供者

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **設定提供者**。
3. 在 **設定提供者** 頁面上，選取 **新建**。
4. 在 **名稱** 欄位中，輸入 **Litware, Inc.**
5. 在 **網址** 欄位，輸入 `https://www.litware.com`。
6. 選取 **儲存**。

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>啟用 ER 設定提供者

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **設定提供者** 部分中，選取 **Litware, Inc.** 圖格，然後選取 **設定為有效狀態**。

如需 ER 設定提供者的相關資訊，請參閱[建立設定提供者並將其標記為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)。

## <a name="additional-resources"></a>其他資源

- [電子報表概述](general-electronic-reporting.md)
- [追蹤 ER 格式的執行以解決效能問題](trace-execution-er-troubleshoot-perf.md)
- [支援導出欄位類型的 ER 資料來源的參數化調用](er-calculated-field-type.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
