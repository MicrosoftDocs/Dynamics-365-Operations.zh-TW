---
title: 使用倉庫設定範本設定倉庫
description: 本主題說明如何使用倉庫設定範本設定倉庫。
author: yufeihuang
ms.date: 11/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportEnhanced, DMFDefinitionGroupTemplate, DMFEntityTemplateDefinitionLoadDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 6698d615826a1555426824bb76db654fde539360
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448374"
---
# <a name="set-up-a-warehouse-by-using-a-warehouse-configuration-template"></a>使用倉庫設定範本設定倉庫

[!include [banner](../includes/banner.md)]

本主題說明如何使用倉庫設定範本設定倉庫。 您可以使用多個預先定義的設定範本。 有關如何使用這些範本的資訊，請參閱[設定資料範本](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md)。

## <a name="scenarios-where-configuration-templates-can-be-helpful"></a>設定範本適用的案例

設定範本在許多案例中都很實用。 這裡有些範例：

- 您完成了一個設定設置並在測試環境中進行了測試，您現在想要將該設置複製到生產環境。
- 您希望將該倉庫設置推廣到多個法律實體，或在相同法律實體中建立新倉庫。
- 您想盡快為示範倉庫功能做好準備。
- 您希望現有品項和倉庫使用倉庫管理中的功能，而不是使用庫存管理中的功能。

本主題重點介紹以上案例中的第一個案例。 它示範如何使用設定範本將設定設置從測試環境複製到生產環境。

## <a name="copy-a-configuration-setup-from-a-test-environment-to-a-production-environment"></a>將設定設置從測試環境複製到生產環境

在此案例中，測試環境中已存在用於倉庫和一些交易流程的設定設置。 您現在想要將倉庫的設定設置從測試環境複製到生產環境。

> [!NOTE]
> 重要的是在複製設定設置時要包含其他相關設置資料。 例如，您想複製測試環境中的設置來設置產品。 但在建立產品之前，無法為該產品設置固定的揀料位置。 雖然個別設定範本不支援這種類型的相依性，但有支援它的預設資料範本。 您可以輕鬆地將這些預設資料範本包含在設定流程中。

### <a name="export-a-default-warehouse-template"></a>匯出預設倉庫範本 

1. 打開 **資料管理** 工作區。

    > [!NOTE]
    > 如果您是第一次使用此工作區，則必須先載入所有資料實體，然後才能繼續。

2. 選擇 **範本** 圖格，然後選擇 **載入預設範本** 以載入預設範本。

    > [!NOTE]
    > **載入預設範本** 僅在 **增強型** 檢視表中可用。 選擇 **框架參數**，然後在 **檢視預設值** 欄位，選擇 **增強型檢視表**。

3. 載入預設範本後，您可以變更它們以滿足您的業務需求。

    > [!NOTE]
    > 若要載入預設範本和匯入範本，您必須具有系統管理員存取權。 此要求有助於確保所有實體都正確載入到範本中。

4. 確保您所在的法律實體是您要從中匯出公司特定資料的法律實體。
5. 在工作區中，選擇 **匯出**。
6. 建立新的匯出專案。
7. 選擇 **+ 新增範本**，並尋找 **400 - WMS** 預設倉庫範本。 此範本新增了用於倉庫設定的資料實體。

    > [!NOTE]
    > 如果必須篩選要匯出的資料 (例如，您只想匯出與特定倉庫相關的資料)，則必須評估每個資料實體並透過查詢新增篩選。 或者，您可以匯出所有資料，然後刪除目的地檔案中不需要的記錄。

8. 選取 **匯出**。 匯出與品項中所有資料實體相關的資料。

您可以下載資料封裝的 ZIP 檔案。 此檔案包含所選格式 (例如 Excel 格式) 的所有資料。 如前所述，資料封裝檔案中的某些記錄可能必須先更新，然後才能將其匯入生產環境。 如果更新記錄，請確保不要變更檔案名稱。

### <a name="import-a-warehouse-configuration-setup"></a>匯入倉庫設定設置

1. 在目的地環境中，確保您所在的公司是要將倉庫資料匯入其中的公司。

    > [!NOTE]
    > 在匯入之前，應確定任何資料的相依性。 例如，**倉庫管理** 範本包含一個名為 **倉庫處置代碼** 的資料實體。 該實體包含與 **處置代碼** 設置頁面 (**倉庫管理** > **設置** > **行動裝置** > **處置代碼**) 相關的資料。 如果現有設置已處理銷售訂單的退貨流程，則 **退貨處置代碼** 欄位包含值。 此欄位中的處置代碼與 **處置代碼** 資料實體相關，其是 **銷售和行銷** 範本的一部分。 如果來自 **處置代碼** 資料實體的資料不在 **倉庫處置代碼** 欄位的資料之前匯入，匯入將失敗。

2. 在 **資料管理** 工作區，選擇 **匯入**。
3. 建立新的匯入專案。
4. 選擇 **+ 新增檔案**，並上傳資料封裝的 ZIP 檔案。
5. 選取 **匯入**。 在 **增強型** 檢視表中，可以使用 **篩選** 選項快速了解匯入過程中可能發生問題的概觀。

**檢視執行** 記錄提供有關匯入的各個資料實體的詳細資訊。 您可以使用暫存資料檢視表快速取得目標資料。 這樣，您可以在應用程式的相關頁面上看到匯入的資料會是什麼樣子。 使用預設資料範本時，每個資料實體的匯入順序採用預先定義的方式，以幫助確保先匯入所有相依性資料。 如果自訂資料實體是品項的一部分，您必須確保定義正確的序列。 有關詳細資訊，請參閱[設定資料範本](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md)。

若要了解有關如何使用倉庫範本將倉庫的設定從一個公司複製到同一實例中的新公司的更多資訊，請在 YouTube 上觀看此 3 分鐘影驗：[如何使用倉庫範本複製財務和營運的設定](https://www.youtube.com/watch?v=K2WIfFlqJYs)。

## <a name="related-topic"></a>相關主題

[設定資料範本](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]