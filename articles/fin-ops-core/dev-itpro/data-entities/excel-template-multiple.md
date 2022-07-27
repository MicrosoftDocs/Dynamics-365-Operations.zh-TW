---
title: 具有多個工作表的資料範本
description: 本主題介紹如何使用 Excel 資料實體範本將資料匯入財務和營運。
author: peakerbl
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: cf3c423bdf06685a3c4025551927123773ae818a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460446"
---
# <a name="data-templates-with-multiple-worksheets"></a>具有多個工作表的資料範本

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

應用程式中的資料管理支援基於 Microsoft Excel 的資料實體範本。 這些範本可以包含一個或多個工作表。 當方便管理單個檔案中的資料並將其匯入多個資料實體時，通常會使用具有多個工作表的範本。 一個範例是站點和倉庫。

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a>一次上傳檔案並將其對應到所有實體
讓我們舉一個範例，其中有一個 Excel 檔案，其中的工作表名為 **站點** 和 **倉庫**。 若要設定資料匯入專案，您將新增第一個資料實體，**站點**，然後上傳檔案。 您將能夠選取 **站點** 作為要用於該實體的工作表。

如果您在不離開 **新增檔案** 表單的情況下新增第二個實體 **倉庫**，則工作表查詢將允許您選取 **倉庫** 工作表，而無需再次上傳檔案。 上傳新檔案的唯一原因是 **倉庫** 資料位於不同的檔案中。

![多個工作表。](./media/AddFileMultipleWorkSheets.png)

## <a name="fix-worksheet-to-entity-mapping"></a>修復工作表到實體對應

工作表到匯入作業中資料實體的對應可以從格線中修復。 **工作表** 格線中的列顯示對應檔案中的工作表。 您可以從下拉式選單中選取不同的工作表。 如果所選工作表已對應到資料專案中的實體，系統會要求您確認更改。 我們建議您修復格線中的所有對應。

![更新工作表對應。](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a>重新對應到新檔案

如果必須為資料項目中的現有實體上傳同一檔案的新版本或全新檔案，則必須使用 **新增檔案** 經驗，然後像第一次新增實體一樣再次新增實體。 在繼續之前，系統將確認您要覆寫資料項目中的現有實體。 未再次新增 (或覆寫) 的實體將繼續保留前一個檔案中的前一個對應。

## <a name="upload-a-file-using-run-project"></a>使用執行專案上傳檔案

您可以在使用 **執行專案** 選項執行匯入專案時上傳 Excel 檔案。 您必須小心僅上傳與資料專案中資料實體上的現有對應具有相同工作表的檔案。 如果在新上傳的檔案中沒有找到工作表，系統將顯示錯誤並停止匯入。 如果必須更改實體到工作表的對應，則必須先從資料專案中更新資料專案中的對應，然後才能使用 **執行專案** 經驗。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
