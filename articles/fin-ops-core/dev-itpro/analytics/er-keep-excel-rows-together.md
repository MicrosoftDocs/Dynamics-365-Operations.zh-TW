---
title: 設計 ER 格式以將資料列保持在同一個 Excel 頁面上
description: 本主題說明如何設計一種電子報表 (ER) 格式，以使同一 Microsoft Excel 頁面上的資料列保持相連。
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-03-01
ms.dyn365.ops.version: Version 10.0.26
ms.openlocfilehash: 711681ab38fb24b57a83f008f86a8261176aa5a5
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2022
ms.locfileid: "8460595"
---
# <a name="design-an-er-format-to-keep-rows-together-on-the-same-excel-page"></a>設計 ER 格式以將資料列保持在同一個 Excel 頁面上

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

本主題說明系統管理員或電子報表職能顧問角色的使用者如何設定[電子報表 (ER)](general-electronic-reporting.md) [格式](er-overview-components.md#format-component)，以在 Microsoft Excel 中產生輸出文件並管理文件分頁，以便將建立的資料列保留在同一頁面上。

在此範例中，您將修改 Microsoft 提供的用於在 Excel 中列印普通發票的 ER 格式。 您的修改將允許您管理產生的普通發票報表的分頁，以便盡可能將單個發票行的所有資料列保持在同一頁面上。

本主題中的程序可以在 **USMF** 公司完成。 無需編碼。

在此範例中，您將建立 **Litware, Inc.** 樣本公司的所需的 ER[設定](general-electronic-reporting.md#Configuration)。 確保 **Litware, Inc.** (`http://www.litware.com`) 樣本公司的設定提供者列在 ER 架構，並且被標記為 **有效**。 如果此設定提供者未列出，或者未標記為 **有效**，按照[建立設定提供者並將其標記為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)中的步驟。

## <a name="enter-a-new-free-text-invoice"></a>輸入新的普通發票

1. 按照[建立普通發票](../../../finance/accounts-receivable/create-free-text-invoice-new.md#create-a-free-text-invoice-1)中的步驟新增普通發票。

    1. 在發票中新增單一明細。
    2. 為發票明細新增五個註釋。

    ![查看附件頁面上的發票明細註釋。](./media/er-keep-excel-rows-together-notes.png)

2. 按照[複製明細](../../../finance/accounts-receivable/create-free-text-invoice-new.md#copy-lines)中的步驟建立五個附加發票明細，它們複製您在上一步中新增的發票明細。

    ![查看普通發票頁面上的普通發票明細。](./media/er-keep-excel-rows-together-invoice.png)

## <a name="configure-the-er-framework"></a>設定 ER 架構

按照[設定 ER 架構](er-quick-start2-customize-report.md#ConfigureFramework)中的步驟設定最小的 ER 參數集。 在開始使用 ER 架構設計標準 ER 格式的自訂版本之前，您必須完成此安裝。

## <a name="import-the-standard-er-format-configuration"></a>匯入標準 ER 格式設定

按照[匯入標準 ER 格式設定](er-quick-start2-customize-report.md#ImportERSolution1)中的步驟將標準 ER 設定新增到您現行的 Dynamics 365 Finance 實體。 例如，匯入 **普通發票 (Excel)** 格式設定的 **252.116** 版。 基本 **發票模型** 設定的基本版本 **252** 與所需的 **發票模型對應** 設定一起自動從存放庫中匯入。

## <a name="set-up-print-management-to-use-the-standard-er-format"></a>設定列印管理以使用標準 ER 格式

按照 [安裝列印管理](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement1)中的步驟為 **應收帳款** 模組設定列印管理，以便使用標準 ER 格式列印普通發票。

## <a name="configure-a-format-destination-for-the-standard-er-format"></a>為標準 ER 格式設定格式目標

按照[設定螢幕預覽的格式目標](er-quick-start1-new-solution.md#ConfigureDestination)中的步驟設定標準 ER 格式的[螢幕](er-destination-type-screen.md) ER 目標，以便將產生的報表轉換為 PDF 格式並在新的瀏覽器索引標籤上預覽。

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a>使用標準 ER 格式列印普通發票

1. 按照[列印普通發票](er-embed-images-header-footer-excel-reports.md#ProcessInvoice1)中的步驟使用標準 ER 格式為新增的發票產生 Excel 格式的普通發票報表。
2. 下載產生的 Excel 活頁簿，並在 Excel 桌面應用程式中查看它。

    請注意，發票的第六行從報表的第一頁開始並在第二頁繼續。 最後一個註釋出現在第二頁，不明顯它屬於第六個發票行。 因此，發票行內容中間的分頁符使該文件更難閱讀。

    ![在 Excel 桌面應用程式中查看產生的普通發票的分頁。](./media/er-keep-excel-rows-together-invoice1.gif)

本主題中的其餘過程展示了如何調整標準 ER 格式，以透過將單個發票明細的所有內容保留在同一頁面上來改進發票報表的外觀和可讀性。

## <a name="create-a-custom-format"></a>建立自訂格式

按照 [建立自訂格式](er-embed-images-header-footer-excel-reports.md#DeriveProvidedFormat)中的步驟從匯入的 ER 格式衍生格式，並建立可用於編輯和修改的 **普通發票 (Excel) 自訂** ER 設定。

## <a name="edit-the-custom-format"></a>編輯自訂格式

1. 按照[建立自訂格式](er-embed-images-header-footer-excel-reports.md#ConfigureDerivedFormat)中的步驟在 ER 格式設計工具中打開衍生的 ER 格式進行編輯。
2. 在 **格式設計工具** 頁面，在左窗格的格式組件樹狀結構中，展開 **Free text invoice\>Sheet\>InvoiceLines**，並選取 **InvoiceLines_Values** 組件。
3. 在 **格式** 索引標籤上，將 **將資料列保持相連** 選項設定為 **是**。

    ![在格式設計工具頁面上為可編輯的 ER 格式設定將資料列保持相連選項。](./media/er-keep-excel-rows-together-format.png)

4. 選取 **儲存**，然後關閉此頁。

## <a name="mark-the-custom-format-as-runnable"></a>將自訂格式標記為可執行

按照[將自訂格式標記為可執行](er-embed-images-header-footer-excel-reports.md#MarkFormatRunnable)中的步驟使自訂 ER 格式的修改版本可執行。

## <a name="set-up-print-management-to-use-the-custom-er-format"></a>設定列印管理以使用自訂 ER 格式

按照 [安裝列印管理](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement2)中的步驟為 **應收帳款** 模組設定列印管理，以便使用自訂 ER 格式列印普通發票。

## <a name="configure-a-format-destination-for-the-custom-er-format"></a>為自訂 ER 格式設定格式目標

按照 [設定螢幕預覽的格式目標](er-quick-start1-new-solution.md#ConfigureDestination)中的步驟設定自訂 ER 格式的 **螢幕** ER 目標，以便將產生的報表轉換為 PDF 格式並在新的瀏覽器索引標籤上預覽。

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a>使用自訂 ER 格式列印普通發票

1. 按照[列印普通發票](er-embed-images-header-footer-excel-reports.md#ProcessInvoice2)中的步驟使用自訂 ER 格式為新增的發票產生 Excel 格式的普通發票報表。
2. 下載產生的 Excel 活頁簿，並在 Excel 桌面應用程式中查看它。

    請注意，發票的第六行從第二頁開始，代表該發票明細的所有 Excel 行一起出現在該頁面上。

    ![在 Excel 桌面應用程式中查看產生的普通發票的更新分頁。](./media/er-keep-excel-rows-together-invoice2.gif)

## <a name="additional-resources"></a>其他資源

[設計用於產生 Excel 格式文件的設定](er-fillable-excel.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
