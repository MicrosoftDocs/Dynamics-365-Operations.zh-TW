---
title: 透過重新應用 Excel 範本修改電子報表格式
description: 本主題介紹如何透過重新套用修改後的 Excel 範本來修改用於產生商業文件的電子報表 (ER) 格式。
author: NickSelin
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 57f0db12657878fa34c86c55925d62100c26cad8799e5e6ace7e7dd81d91cd9f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460453"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a>透過重新應用 Excel 範本修改電子報表格式

[!include [banner](../includes/banner.md)]

電子報表 (ER) 工具用於產生電子格式的商業文件。 若要產生商業文件，您必須建立 ER 格式，然後使用 ER 設計工具定義商業文件的配置並指定應包含在其中的資料。 然後，您可以運行 ER 格式來產生商業文件。

ER 工具可用於產生商業文件，如 Microsoft Excel 檔案。 您可以使用 Excel 文件作為這些文件的範本。 若要在 ER 設計工具中定義文件配置，您可以將要用作範本的 Excel 文件的內容匯入到定義的 ER 格式中。 如需更多詳情並練習此案例，請播放工作指南 **ER 設計用於產生 OPENXML 格式報表的設定**(7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677) 業務流程的一部分)。

如果您編輯用作商業文件範本的 Excel 文件，新的 ER 函數允許您將更新的範本重新套用到 ER 格式。 然後更新 ER 格式，使其符合更新後的範本。 如需此函數的更多詳情，請播放工作指南 **ER 透過重新套用 Excel 範本修改格式**(7.5.5.3 獲得/開發 IT 服務/解決方案組件 (10683) 業務流程的一部分)。 在匯入更新範本的工作指南步驟中，使用付款報表 Excel 檔案 SampleVendPaymWsReport2 的修改範本作為範本。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]