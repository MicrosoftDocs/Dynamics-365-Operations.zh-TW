---
title: 壓縮在電子報表中產生的大型文件
description: 本主題說明如何壓縮由電子報告 (ER) 格式產生的大型文件。
author: NickSelin
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERFormatDestinationTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 7ef8f730f2e207a8fd28c2bf5167d14f57d6c607314bfc48d4358a59d3ef5c43
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460247"
---
# <a name="compress-large-documents-that-are-generated-in-electronic-reporting"></a>壓縮在電子報表中產生的大型文件 

[!include [banner](../includes/banner.md)]

您可以使用[電子報告 (ER) 架構](general-electronic-reporting.md)來設定一個解決方案，該解決方案獲取交易資料以產生輸出文件。 這個產生的文件可能非常大。 產生此類型的文件時，使用[應用程式物件伺服器 (AOS)](../dev-tools/access-instances.md#location-of-packages-source-code-and-other-aos-configurations) 記憶體來持有它。 在某個時候，必須從 Microsoft Dynamics 365 Finance 應用程式中下載該文件。 目前，在 ER 中產生的單個文件的最大容量限制為 2 GB。 此外，Finance 現行將下載檔案的大小[限制](https://fix.lcs.dynamics.com/Issue/Details?kb=4569432&bugId=453907&dbType=3)為1 GB。 因此，您必須設定一個ER解決方案，以減少超過這些限制的可能性，並且您將收到 **串流太長** 或 **算術作業中的溢位或下溢** 異常。

設定解決方案時，您可以透過新增 **資料夾** 類型的根元素來壓縮其任何巢狀元素產生的內容來調整 Operations 設計工具中的 ER 格式。 壓縮「及時」工作，因此可以減少峰值記憶體使用和將要下載的檔案的大小。

> [!NOTE]
> 檔案壓縮佔用額外百分比的 CPU 使用率。

如需此方法的相關資訊，請完成本主題中的範例。

## <a name="example-compress-an-outbound-document"></a>範例：壓縮輸出文件

此範例顯示了指派給 **系統管理員** 或 **電子報告函數顧問** 角色的使用者如何設定 ER 格式以壓縮產生的文件。

### <a name="prerequisites"></a>先決條件

在完成此主題中的程序之前，必須完成以下步驟。

1. [啟用設定提供者](er-defer-xml-element.md#activate-a-configuration-provider)。
2. [匯入樣本 ER 設定](er-defer-xml-element.md#import-the-sample-er-configurations)。
3. [查閱已匯入的格式](er-defer-xml-element.md#review-the-imported-format)。

> [!NOTE]
> 現行，格式結構從 **檔案** 類型的 **報告** 元素開始，並包含 XML 元素。 因此，將以 XML 格式產生輸出文件，並且不會使用壓縮。

### <a name="generate-an-er-format-to-get-an-uncompressed-document"></a>產生 ER 格式以取得未壓縮的文件

1. [執行已匯入的格式](er-defer-xml-element.md#run-the-imported-format)。
2. 請注意，產生的 XML 格式文件的大小為 3 KB。

    ![預覽未壓縮的輸出文件。](./media/er-compress-outbound-files1.png)

### <a name="modify-the-format-to-compress-the-generated-output"></a>修改格式以壓縮產生的輸出

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，展開 **學習已遞延元素的模型**。
3. 選取 **格式學習遞延 XML 元素** 設定。
4. 選取 **設計工具** 以修改格式結構。
5. 在 **格式設計工具** 頁面上，在 **格式** 索引標籤上，選取 **新增根** 以新增根格式元素。
6. 在 **新增** 對話方塊中，選取 **Common\\Folder**。
7. 選取 **確定** 以確認新增新的根元素。
8. 選取 **儲存**。

> [!NOTE]
> 格式結構從 **資料夾** 類型的元素開始。 此元素將產生輸出為壓縮 (zip) 檔案。 當 **報告** 元素產生的文件放在輸出 ZIP 檔案中時，將壓縮其內容以減少輸出檔案的大小。

### <a name="generate-an-er-format-to-get-a-compressed-document"></a>產生 ER 格式以取得壓縮的文件

1. 在 **格式設計工具** 頁面上，選取 **執行**。
2. 下載網頁瀏覽器提供的 ZIP 檔案，然後打開它以供查看。
3. 請注意，以 ZIP 格式產生的文件的大小為 1 KB。

    > [!NOTE] 
    > 此 ZIP 檔案儲存的 XML 檔案的壓縮率為 87%。 壓縮率取決於正在壓縮的資料。

    ![預覽壓縮的輸出文件。](./media/er-compress-outbound-files2.png)

> [!NOTE]
> 如果為產生輸出的格式元素設定了 ER [目的地](electronic-reporting-destinations.md) (本範例中的 **報告** 元素)，則輸出的壓縮將被略過。

## <a name="additional-resources"></a>其他資源

[電子報表 (ER) 概觀](general-electronic-reporting.md)

[電子報表 (ER) 目的地](electronic-reporting-destinations.md)

[遞延執行 ER 格式的 XML 元素](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]