---
title: 印表機 ER 目的地類型
description: 本主題說明如何為電子報告 (ER) 格式的每個 FOLDER 或 FILE 組件設定印表機目的地。
author: NickSelin
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2513fc4f86519c71602089cd46e9757813b1a708
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2022
ms.locfileid: "8460501"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>印表機目的地

[!include [banner](../includes/banner.md)]

您可以將產生的文件直接發送到網路印表機進行直接列印。

## <a name="prerequisites"></a>先決條件

在開始之前，您必須安裝和設定文件路由傳送代理程式，然後註冊網路印表機。 如需相關資訊，請參閱[安裝文件路由傳送代理程式以啟用網路列印](./install-document-routing-agent.md)。

## <a name="make-the-printer-destination-available"></a>使印表機目的地可用

若要使 **印表機** 目的地在 Microsoft Dynamics 365 Finance 的現行實體中可用，請進入 **函數管理** 工作區，然後按以下順序打開以下函數：

1. 將電子報告輸出文件從 Microsoft Office 格式轉換為 PDF
2. 文件路由傳送代理程式作為輸出文件的電子報告目的地

[![在函數管理中打開 ER 印表機目的地函數。](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>適用性

#### <a name="pdf-printing"></a>PDF 列印

在 10.0.18 版之前的 Finance 版本中，**印表機** 目的地只能為用於產生可列印 PDF 格式 (**PDF 合併** 或 **PDF 檔案** 格式元素) 或 Microsoft Office Excel 和 Word 格式 (**Excel 檔案** 格式) 輸出的檔案組件設定印表機目的地。 當以 PDF 格式產生輸出時，它會被發送到印表機。 當使用 **Excel 檔案** 格式元素以 Office 格式產生輸出時，它會自動轉換為 PDF 格式，然後發送到印表機。

但是，從 10.0.18 版開始，您可以為 **常用檔案** 格式元素設定 **印表機** 目的地。 此格式元素主要用於產生 TXT 或 XML 格式的輸出。 您可以設定包含 **常用檔案** 格式元素作為根格式元素和 **二進位內容** 格式元素作為其下唯一巢狀元素的 ER 格式。 在這種情況下，**常用檔案** 格式元素將以您為 **二進位內容** 格式元素設定的繫結指定的格式產生輸出。 例如，您可以設定此繫結以使用 PDF 或 Office (Excel 或 Word) 格式的[文件管理](../../fin-ops/organization-administration/configure-document-management.md)附件的內容[填入](tasks/er-document-management-files-5.md#modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format)此元素。 您可以使用設定的 **印表機** 目的地列印輸出。 

> [!NOTE]
> 當您選取 **Common\\File** 格式元素來設定 **印表機** 目的地時，無法在設計階段保證所選元素將產生 PDF 格式的輸出或可以轉換為 PDF 格式的輸出。 因此，您會收到以下警告訊息：「請確保所選格式組件產生的輸出可以轉換為 PDF。 否則，請取消選中『轉換為 PDF』選項。」 當在執行階段提供非 PDF 或非 PDF 可轉換輸出以供列印時，您必須採取措施幫助防止執行階段問題。 如果您希望接收 Office（Excel 或 Word）格式的輸出，則必須選取 **轉換為 PDF** 選項。
>
> 在 10.0.26 版及更高版本中，若要使用 **轉換為 PDF** 選項，您必須為設定的 **印表機** 目的地的 **文件路由傳送類型** 參數選取 **PDF**。

#### <a name="zpl-printing"></a>ZPL 列印

在 10.0.26 版及更高版本中，您可以透過為 **文件路由傳送類型** 參數選取 **ZPL** 來為 **Common\\File** 格式元素設定 **印表機** 目的地。 在這種情況下，執行階段會忽略 **轉換為 PDF** 選項，並使用[文件路由傳送代理程式 (DRA)](install-document-routing-agent.md) 的 Zebra 程式設計語言 (ZPL) 合同將 TXT 或 XML 輸出直接發送到選定的印表機。 將此函數用於表示 ZPL II 標籤配置的 ER 格式以列印各種標籤。

[![在目的地設定對話方塊中設定文件路由傳送類型參數。](./media/ER_Destinations-SetDocumentRoutingType.png)](./media/ER_Destinations-SetDocumentRoutingType.png)

如需此函數的相關資訊，請參閱[設計一種新的 ER 解決方案來列印 ZPL 標籤](er-design-zpl-labels.md)。

### <a name="limitations"></a>限制

**印表機** 目的地僅針對雲端部署實施。

### <a name="use-the-printer-destination"></a>使用印表機目的地

1. 將 **已啟用** 選項設定為 **是** 以將產生的文件發送到印表機。
2. 在 **印表機** 名稱欄位中，選取所需的網路印表機。
3. 將 **儲存在列印歸檔中？** 選項設定為 **是** 以將產生的輸出儲存在列印存檔中，以便進一步列印。 若要稍後存取存檔的輸出，請進入 **組織管理**\>**查詢和報告**\>**報告歸檔**。

[![使用印表機目的地。](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> 設定 **印表機** 目的地時，不必打開 **轉換為 PDF** 選項。 即使關閉該選項，也會進行用於列印的 PDF 轉換。

若要在列印 Excel 格式的輸出文件時使用特定的 [頁面方向](electronic-reporting-destinations.md#SelectPdfPageOrientation)，您必須打開 **轉換為 PDF** 選項。 當您將 **轉換為 PDF** 選項設定為 **是** 時，**頁面方向** 欄位變為可用。 在 **頁面方向** 欄位中，您可以選取頁面方向。

## <a name="additional-resources"></a>其他資源

- [電子報表 (ER) 概觀](general-electronic-reporting.md)
- [電子報表 (ER) 目的地](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
