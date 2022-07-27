---
title: 透過將內容新增為原始 XML 來產生報表
description: 您可以設計產生 XML 格式的傳出文件的電子報表 (ER) 格式。
author: NickSelin
ms.date: 05/25/2018
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
ms.openlocfilehash: 160f27f4f44ab6982addb7294db889e2a8dbfcfbc03f7849548c44364b070aa9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460384"
---
# <a name="generate-reports-by-adding-content-as-raw-xml"></a>透過將內容新增為原始 XML 來產生報表

[!include[banner](../includes/banner.md)]

您可以使用新的 **RAW XML** 格式元素來設計產生 XML 格式的傳出文件的電子報表 (ER) 格式。 在某些情況下，出於以下一個或多個原因，您可能更願意將原始 XML 資料新增到這些報表中：

- 將原始 XML 用於報表的原始設計和持續維護會更方便，因為可以透過執行執行階段運算式自動產生 XML 結構。 因此，不必在設計階段為多個格式元素確定多個繫結。 當您使用的資料來源包含可用於在產生報表時製作 XML 元素的信息時，這是可能的。
- 沒有其他方法可用於使用先前接收並儲存在系統中的 XML 內容填入報表。 例如，產生的 XML 回應可能必須包含之前發送的 XML 請求的內容。
- 沒有其他方法可用於根據字元的數字代碼將字元插入到產生的文件中。 對於某些語言和字元，不存在這種類型的代碼。 範例包括希臘字母 rho (ρ) 和 HTML 實體代碼，例如 \&eacute; 表示帶有尖音符 (é) 的 *e*。

> [!NOTE]
> 請注意，架構不控制使用 **RAW XML** 格式元素放置到產生的文件中的 XML 內容是否正確。

若要了解此函數的更多信息，請播放 **ER 使用原始 XML 資料產生 XML 報表 (第 1 章節：設計資料模型)** 和 **ER 使用原始 XML 資料產生 XML 報表 (第 2 章節：設計和運行報表)** 工作指南，是 **7.5.4.3 獲取/開發 IT 服務/解決方案組件 (10677)** 商業流程的一部分，可從 [Microsoft 下載中心](https://go.microsoft.com/fwlink/?linkid=874684)下載。 這些工作指南向您解釋了設定 ER 格式以將原始 XML 資料插入產生的檔案的過程。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]