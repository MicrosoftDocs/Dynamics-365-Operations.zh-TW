---
title: 固定資產管理工作區
description: 本主題提供有關固定資產管理工作區的資訊。 此工作區顯示輸入系統的固定資產相關資訊。 它包括摘要視圖和分析視圖。
author: saraschi2
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetWorkspace
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 597a9a32995d44282c89725e053f6da4643dbb691b1b36ae7c237acbfa2afb70
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450201"
---
# <a name="fixed-asset-management-workspace"></a>固定資產管理工作區

[!include [banner](../includes/banner.md)]

**固定資產管理** 工作區顯示輸入系統的固定資產相關資訊。 此工作區包括摘要視圖和分析視圖。 **我的工作** 索引標籤顯示摘要圖塊、固定資產詳細資料和當前公司固定資產的相關資訊。 您也可以直接將分析新增到工作區裡的 Power BI 分析專區。 **分析 - 所有公司** 索引標籤使用 Microsoft Power BI 功能顯示與所有公司固定資產相關的視覺效果。

## <a name="my-work"></a>我的工作

### <a name="summary"></a>摘要

**摘錄** 專區裡的圖塊概述您的固定資產。 資訊包括尚未採購的資產、本年度已採購的資產以及本年度已處置的資產計量。 **摘錄** 專區也可以快速導航到 **固定資產** 清單頁、批次折舊建議和固定資產日記帳。

### <a name="find-fixed-assets"></a>尋找固定資產

**尋找固定資產** 專區讓您藉由提供固定資產編號、群組、名稱、位置或負責人來快速搜尋資產。 所有符合搜尋條件的資產都將顯示在清單。

您可以從清單檢視下列頁面：

 - 固定資產 **細節** 頁
 - 與固定資產有關聯的所有帳冊的 **帳冊** 頁
 - **固定資產估價** 頁

### <a name="valuations"></a>估價

**固定資產估價** 頁讓您在同一頁查看有關固定資產的最重要資訊，以及與固定資產有關聯的所有帳冊細節。 頁面左上角的 **餘額** 選項顯示與固定資產有關聯的各帳冊當前估價情況。 您可以從各數值切回查看組成彙總值的詳細交易記錄。 頁面左上角的 **設定檔** 選項顯示與固定資產有關聯的各帳冊折舊時間表。

您可以從 **固定資產管理** 工作區或 **固定資產** 清單頁存取 **固定資產估價** 頁。

### <a name="related-information"></a>相關資訊

您可以直接導航到 **帳冊設定** 頁、**固定資產交易查詢** 頁，以及使用工作區 **相關資訊** 專區連結的幾份報表。

### <a name="analytics--all-companies"></a>分析 - 所有公司

**分析** 頁提供有關系統中所有法人實體固定資產的重要計量。 對此索引標籤的存取是由檢視所有公司安全權限的固定資產分析控制。

下表顯示了每個報告頁面上可用的視覺效果。

| 報表頁            | 視覺化        |
|------------------------|----------------------|
| 固定資產估價 | 帳面淨值總額 |
| 固定資產估價 | 固定資產群組的帳面淨值 |
| 固定資產估價 | 採購值 |
| 固定資產估價 | 處置值 |
| 固定資產估價 | 固定資產明細 |
| 估價地圖        | 帳面淨值總額 |
| 估價地圖        | 固定資產位置 |
| 估價地圖        | 固定資產明細 |

若要檢視資料分析情況，您必須先重新整理 **實體商店** 頁的 AssetTransactionMeasure 加總測量值。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]