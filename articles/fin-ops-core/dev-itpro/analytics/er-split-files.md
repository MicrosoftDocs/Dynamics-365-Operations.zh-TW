---
title: 根據檔案大小和內容數量拆分產生的 XML 檔案
description: 本主題提供有關如何根據檔案大小和內容項數量拆分產生之檔案的資訊。
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 3735bcb06eff966fc364a891b38d44e34e845e35f59314822d13eba40d51d5f4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460224"
---
# <a name="split-generated-xml-files-based-on-file-size-and-content-quantity"></a>根據檔案大小和內容數量拆分產生的 XML 檔案

[!include[banner](../includes/banner.md)]

您可以設計電子報表 (ER) 格式以產生 XML 格式的傳出文件。 有時，這些文件只有在滿足特定標準時才能被接受，例如最大檔案大小或某些 XML 節點的最大數量。 您可以設計 ER 格式來產生滿足這些文件的收件人指定的要求的電子文件。

- 對於 FILE 格式元素，您可以將檔案大小限制定義為 ER 運算式。 如果在產生 ER 報表時超出了定義的限制，則 ER 會完成目前檔案的建立，然後繼續建立下一個檔案。
- 對於任何 XML ELEMENT 格式，您可以將元素數量限制定義為 ER 運算式。 如果在執行 ER 報表時已產生檔案中的 XML 節點數超過了定義的限制，則 ER 將完成目前檔案的建立，然後繼續建立下一個檔案。
- 對於任何 XML SEQUENCE 格式元素，您可以將子項目數量限制定義為 ER 運算式。 如果執行 ER 報表時已產生檔案中格式元素的巢狀 XML 節點數超過定義的限制，則 ER 完成目前檔案的建立，然後繼續建立下一個檔案。
- 您可以將任何 XML ELEMENT 格式元素標記為不可破壞。 這樣，您可以將在格式元素下已產生 XML 節點的巢狀項儲存在單個產生的檔案中。

除了使用 XML ELEMENT 和 XML SEQUENCE 格式元素將 XML 節點新增到產生的檔案之外，您還可以使用 RAW XML 格式元素。 但是，在計算節點數以評估元素數限制時，不會考慮使用 RAW XML 格式元素新增的節點。

如果您為已設定為在超出特定限制時拆分產生的輸出的 FILE 格式元素設定檔案目的地，則產生的每條輸出都將作為單獨的檔案發送到設定的檔案目的地。 若要唯一命名透過拆分輸出建立的檔案，您必須為 FILE 格式元素設定 ER 運算式。 如果您包含 NUMBER SEQUENCE 類型的 ER 資料來源，則數字序列將針對分割輸出的每一部分遞增。

若要進一步了解此功能，請播放 **ER 根據檔案大小或內容項數量拆分 XML 檔案** 工作指南，它是 **7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677)** 業務流程的一部分，並且可以從[Microsoft 下載中心](https://go.microsoft.com/fwlink/?linkid=874684)下載。 本工作指南將引導您完成設定 ER 格式以根據檔案大小和內容項數量的限制拆分產生的檔案的過程。 若要完成工作指南，您必須下載以下檔案：

- [ER 模型設定 - XmlFilesSplittingModel.xml](https://download.microsoft.com/download/e/a/f/eaffe96a-22ec-4a32-898a-f4328c91c387/XmlFilesSplittingModel.xml)
- [ER 格式設定 - XmlFilesSplittingFormat.xml](https://download.microsoft.com/download/e/9/c/e9c5849b-8254-4cdf-bb00-4c2ebc72ddec/XmlFilesSplittingFormat.xml)

## <a name="additional-resources"></a>其他資源
[電子報表 (ER) 目的地](electronic-reporting-destinations.md)

[電子報表 (ER) 中的公式設計工具](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
