---
title: 從 Excel 發佈日記帳明細和文件
description: 本主題解釋如何從 Microsoft Excel 輸入和發佈總帳明細。 它包括有關您可以使用的各種範本資訊，具體取決於您正在輸入的交易類型。
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ad4d44030e49b9c07c0827e916d9b4f31fb54fce8b1121e9f69ea754e099591
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450255"
---
# <a name="publish-journal-lines-and-documents-from-excel"></a>從 Excel 發佈日記帳明細和文件

[!include [banner](../includes/banner.md)]

本主題解釋如何從 Microsoft Excel 輸入和發佈總帳明細。 它包括有關您可以使用的各種範本資訊，具體取決於您正在輸入的交易類型。

使用者可以從 Microsoft Excel 輸入和發佈財務日記帳明細。 使用者建立日記帳後，**在 Excel 打開明細** 按鈕會顯示開放使用的範本。 範本主要設計來支援特定設想情況，不過日記帳並非支援每種科目類型組合。 下表顯示目前開放使用的範本以及它們支援的科目類型。

| 範本             | 支援的科目類型 | 如何存取範本                                                          |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| 分類帳日記帳明細     | 科目：支援分類帳、客戶、廠商、銀行沖銷科目：分類帳、客戶、廠商、銀行公司間。       | 總帳                                                                         |
| 發票登記         | 科目：廠商抵銷科目：不支援公司間分類帳。                                                    | AP 發票登記                                                                     |
| 發票日記帳          | 科目：廠商抵銷科目：支援公司間分類帳。                                                      | AP 發票日記帳                                                                      |
| 廠商發票           |                                                                                                                         | 廠商發票                                                                          |
| 客戶發票日記帳 | 科目：客戶抵銷科目：支援公司間分類帳。                                                     | 總帳                                                                         |
| 普通發票        |                                                                                                                         | 在 **普通發票** 頁面上點選 **在 Excel 打開** (Microsoft Office 圖示)。 |
| 固定資產日記帳     | 資產到分類帳、銀行、客戶或廠商。 不支援公司間。                                               | 固定資產日記帳                                                                     |
| 廠商付款日記帳   | 科目：廠商抵銷科目：支援分類帳、銀行公司間。                                                 | 廠商付款日記帳                                                                  |
| 客戶付款日記帳 | 科目：客戶抵銷科目：支援銀行公司間分類帳。                                               | 客戶付款日記帳                                                                |
| 專案費用日記帳  | 支援科目：專案、分類帳、客戶、廠商沖銷科目：專案、分類帳、客戶、廠商公司間。 | 一般日記帳費用 (專案管理和會計項目下)                       |

發佈明細時會驗證確定它們是否遵守財務日記帳設定的規則。 明細發佈後，使用者可以從 Dynamics 365 Finance 編輯或發佈憑單。 

若要新增財務維度到範本，需要額外更改。 額外資訊，請參閱[新增維度到 Microsoft Excel 範本](../../fin-ops-core/dev-itpro/financial/add-dimensions-excel-templates.md)。 維度新增到實體後，它們在 Excel 設計器開放使用並且可以新增到範本。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]