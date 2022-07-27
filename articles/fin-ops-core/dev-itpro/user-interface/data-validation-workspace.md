---
title: 資料驗證檢查清單工作區
description: 資料驗證檢查清單工作區允許您跨公司、區域和人員跟踪資料驗證過程。
author: bking
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DataValidationWorkspace
audience: Application User
ms.reviewer: tfehr
ms.assetid: ''
ms.search.region: Global
ms.author: bking
ms.openlocfilehash: fef3130f06cbb1d8afdbae93bdc55b47be3480b3
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460534"
---
# <a name="data-validation-checklist-workspace"></a>資料驗證檢查清單工作區

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本主題概述了 **資料驗證檢查清單工作區** 和相關設定。

**資料驗證檢查清單** 工作區允許您跨公司、區域和人員跟踪資料驗證過程。 該檢查清單可在新實施期間、升級後或移轉後使用。 根據您對 **資料驗證檢查清單** 工作區的視圖，您將看到資料驗證專案的所有工作和狀態，或者僅看到指派給您的工作。

您必須先在工作區頂部選取一個資料驗證專案。 然後，工作區中顯示的所有資料都由所選資料驗證專案過濾。

## <a name="summary-tiles"></a>摘要圖格

**摘要** 圖格提供流程概覽，指標可幫助您保持資料驗證流程的正常進行。您可以查看該流程的所有剩餘工作、已完成工作、正在進行的工作和未開始的工作。 此信息適用於所選資料驗證專案中包含的所有公司。

## <a name="tasks-and-status-section"></a>工作和狀態區段

在 **工作和狀態** 區段，整體資料驗證項目的狀態以多種方式顯示：按法人、按區域和按工作清單的狀態。 您可以選取過濾器來查看特定公司的狀態。 每個狀態索引標籤都按已完成百分比和剩餘工作數提供細分。

最後一個索引標籤用於詳細的工作清單。 此清單顯示完整的工作清單。 您可以透過多種方式過濾工作清單。 點選 **編輯工作** 更改工作的狀態或指派工作。 點選 **附件** 查看工作的附件。

工作名稱是指向使用者完成工作必須去的頁面的超連結。 當您從 **設定資料驗證專案** 表單編輯或建立工作時，您可以使用 **選單項目名稱** 欄位設定此超連結。

您可以使用 **附件** 動作將檔案、註釋、影像和 URL 附加到工作。 例如，您可以附加為工作列印的報表檔案。 如果存在 **附件**，則工作的附件欄中會出現一個圖示。

工作完成後，**完成者** 選項將自動填入完成該工作之員工的名字。 當工作標記為已完成時，**已完成日期** 欄位會自動更新為現行日期和時間。

## <a name="configure-data-validation-project-page"></a>設定資料驗證專案頁面

在您可以使用 **資料驗證檢查清單** 工作區之前，您必須使用 **設定資料驗證專案** 頁面來設定流程。 (點選 **工作區**\>**資料驗證檢查清單**\>**設定資料驗證專案**。)

## <a name="task-areas"></a>工作區域

您使用工作區域將資料驗證工作分組到組織內的邏輯所有權區域。 例如，應付帳款、應收帳款或總帳可用作工作範圍。

**選單項目名稱** 與工作工作量相關，可用於從工作區中的工作連結直接轉到相關頁面。 例如，為應付帳款執行 **應付帳款帳齡** 報表的資料驗證工作可以連結到 **應付帳款帳齡報表** 頁面。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]