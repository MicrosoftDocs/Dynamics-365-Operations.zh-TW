---
title: 使用 ER 產生電子文件和更新申請資料
description: 您可以設計可在應用程式中用於產生傳出電子文件的電子報表 (ER) 格式。
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5f78f3b36a1aebfb263d64ccf2293097eb9af6e6de1ab49de39b18e1c318950
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460209"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a>使用 ER 產生電子文件和更新申請資料

[!include [banner](../includes/banner.md)]

您可以設計可在應用程式中用於產生傳出電子文件的電子報表 (ER) 格式。 您還可以設計 ER 格式來解析傳入的電子文件並使用這些文件中的內容來更新應用程式資料。

借助此函數，可以使用單一 ER 格式產生外發電子文件，然後更新應用程式資料。 此功能可用於以下場景：

- 為防止在後續流程中重複使用應用程式資料，您可以在應用程式資料用於產生電子文件後立即對其進行標記。 例如，您可以在付款交易包含在產生的付款訊息中後立即將其標記為已處理。
- 儲存使用 ER 邏輯產生之電子文件的處理細節。 例如，使用 ER 運算式產生的唯一付款訊息識別。 該運算式基於執行 ER 格式以產生文件時在 ER 對話方塊中輸入的資訊。

若要進一步了解此功能，請播放帶有應用程式資料更新工作指南的 ER 產生文件集 (7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677) 業務流程的一部分)，其中向您解釋了 Intrastat 報表的詳情和存檔。 完成這些工作指南中的某些步驟需要以下檔案。 下載這些檔案並將其儲存到本機。

- [ER 資料模型設定：Intrastat (模型)](https://download.microsoft.com/download/9/c/e/9ceeacbe-c13e-422e-96f2-594c4a6b45b7/Intrastatmodel.xml)
- [ER 模型對應設定：Intrastat (對應)](https://download.microsoft.com/download/2/1/d/21ddaaeb-64c5-4408-a35f-1ccb922d40a4/Intrastatmapping.xml)
- [ER 格式設定：Intrastat (格式)](https://download.microsoft.com/download/8/b/b/8bbb8891-e88d-4739-b92a-2d1d2fffcb79/Intrastatformat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
