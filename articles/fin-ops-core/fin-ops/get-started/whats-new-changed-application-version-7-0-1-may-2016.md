---
title: Dynamics AX 應用程式版本 7.0.1 (2016 年 5 月) 的新增功能或變更
description: 本文介紹 Microsoft Dynamics AX 應用程式版本 7.0.1 中新增或更改的功能。 此版本於 2016 年 5 月發佈，其組建編號為 7.0.1265.23014。
author: sericks007
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 9a455ffbc4396ea4bf0e3df12e7acdcbfeaa5f5269dbe772848341ac0d22a5e1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460363"
---
# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a>Dynamics AX 應用程式版本 7.0.1 (2016 年 5 月) 的新增功能或變更

[!include [banner](../includes/banner.md)]

本文介紹 Microsoft Dynamics AX 應用程式版本 7.0.1 中新增或更改的功能。 此版本於 2016 年 5 月發佈，其組建編號為 7.0.1265.23014。

## <a name="electronic-reporting-er"></a>電子報表 (ER)

| 您能做什麼？ | 為什麼這很重要？ |
|------------------|------------------------|
| 設定用於設計電子報表 (ER) 報表的執行階段對話方塊，以便使用者可以選取所需的財務維度。 | 在執行階段，在執行 ER 報表的對話方塊中，使用者可以選取多個財務維度。 所選財務維度的詳情將顯示在產生的電子文件中。 |
| 在設計 ER 報表期間，透過到所需資料來源的單一對應設定對多個財務維度的存取。 | 相同的 ER 報表設定可用於產生顯示交易資料以及財務維度詳情的電子文件，而不管使用者選取的財務維度的數量或為目前法律實體或實體設定的財務維度的數量如何。 |
| 設定 ER 報表以在以 OPENXML 工作表格式建立的電子文件的動態產生欄中輸入資料。 | ER 報表可以透過水平複製資料欄在產生的 OPENXML 工作表中輸入資料。 因此，可以重複使用相同的 ER 報表設定來產生具有不同數量的動態產生欄的電子文件。 |
| 設定 ER 目標，以便將格式的輸出結果定向到特定目標：檔案、電子郵件或存檔 (Microsoft SharePoint 資料夾或 Microsoft Azure 儲存體)。 | 以前，當您執行 ER 設定時，會出現一個訊息方塊，需要使用者動作才能儲存或打開檔案。 您現在可以分別為每個格式設定和每個輸出組件 (資料夾或檔案) 預設定目的地。 具有適當存取權限的使用者還可以在執行階段修改目的地設定。 |

## <a name="pos--microsoft-dynamics-ax-retail"></a>POS – Microsoft Dynamics AX Retail

| 您能做什麼？ | 為什麼這很重要？ |
|------------------|------------------------|
| 使用 Google Chrome 瀏覽器。 | 零售商現在可以從 Chrome 瀏覽器啟動雲端 POS，並可以體驗 Microsoft Edge 和 Internet Explorer 版本的雲端 POS 中提供的所有函數。 |

## <a name="financial-reporting"></a>財務報表編製

| 您能做什麼？ | 為什麼這很重要？ |
|------------------|------------------------|
| 重建財務報表資料超市。 | 當您在環境之間行動 Dynamics AX 資料庫或對環境進行其他侵入性更改時，可能必須重建財務報表資料庫。 現在提供了一個 Windows PowerShell 指令碼來為您重建資料庫。 |
| 您不能再選取無效的 Report Designer 選項。 | 在市場版本的 Management Reporter 中使用的多個 Report Designer 選項不適用於此版本的 Dynamics AX。 這些選項與財務報表設計、輸出和連結有關。 這些選項已從財務 Report Designer 中刪除，以防止使用者出錯。 |

## <a name="financial-management"></a>財務管理

| 您能做什麼？ | 為什麼這很重要？ |
|------------------|------------------------|
| 為應付帳款產生付款確認檔案。 | 可以產生正支付檔案以幫助防止支票欺詐。 |

## <a name="warehouse-and-production"></a>倉庫和生產

<table>
<thead>
<tr>
<th>您能做什麼？</th>
<th>為什麼這很重要？</th>
</tr>
</thead>
<tbody>
<tr>
<td>定義控制在特定位置為一組產品建立工作的倉庫工作策略。</td>
<td>倉庫流程不一定套件括工作。 透過使用新的倉庫工作策略，您可以防止為特定位置的一組產品的原材料揀配和成品入庫建立工作。</td>
</tr>
<tr>
<td>指定生產輸出位置不受牌照控制。</td>
<td>您現在可以指定產品輸出位置不受牌照控制。 例如，當上游生產訂單將項目直接報表為已完成的位置時，此功能很有用，該位置可充當下游生產訂單的生產輸入位置。</td>
</tr>
<tr>
<td>支援套件含同一項目的不同產品尺寸的項目的 BOM。</td>
<td>在生產中使用一個或多個產品尺寸時，您可能會遇到想要根據同一項目的不同變體生產項目的情況。 如需相關資訊，請參閱<a href="/archive/blogs/axmfg/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item">此部落格</a>。</td>
</tr>
<tr>
<td>在其 BOM 的第一層有循環結構的生產訂單不套件括在物料資源計畫的 BOM 層計算中。</td>
<td>無法為導致 BOM 階層循環的生產訂單的產品變型指派正確的 BOM 級別。</td>
</tr>
<tr>
<td>為物料資源計劃和成本計算計算單獨的 BOM 級別：
<ul>
<li>對於物料資源計劃，在新的 <strong>ReqItemLevel</strong> 表中計算 BOM 級別。 計算中忽略已結束的生產訂單。</li>
<li>對於生產成本計算，BOM 級別會在 <strong>InventTable</strong> 中計算。 計算中套件含已結束的生產訂單。</li>
</ul>
</td>
<td>
<ul>
<li>在執行物料資源計劃時，例如主計劃計劃排程和展開，只需要重新計算用於物料資源計劃的 BOM 級別。 換言之，無需計算用於生產成本計算的 BOM 級別。</li>
<li>執行成本核算動作時，例如庫存結轉，只需要重新計算用於生產成本核算計算的 BOM 級別。</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>其他資源

[財務和營運應用程式首頁中的新增內容或更改內容](whats-new-changed.md)

[全新或更新的工作指南 (2016 年 5 月)](new-updated-task-guides-available-may-2016.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]