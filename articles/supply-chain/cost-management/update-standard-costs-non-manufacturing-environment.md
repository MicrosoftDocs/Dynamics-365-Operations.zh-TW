---
title: 更新非製造環境中的標準成本
description: 本文提供在非製造環境中更新標準成本的指南。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 139c72fc60330427336de872d7c9730fd12e291f8cad3f7327380b2003535d78
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447093"
---
# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a>更新非製造環境中的標準成本

[!include [banner](../includes/banner.md)]

本文提供在非製造環境中更新標準成本的指南。

以下指南假設您使用兩個版本的方法來更新標準成本。 在這種方法中，一個成本計算版本包含最初為凍結期定義的標準成本，第二個成本計算版本包含增量更新。 每次更新作為在第二個成本計算版本包括的成本記錄輸入，並最終啟用。 另一個版本的方法使用最初定義的標準成本集。 雙版本方法要求您定義第二個成本計算版本。 以下是定義此成本計算版本的指南：

-   指派 **標準成本** 的成本計算類型。
-   指派有意義的識別碼來指示成本計算版本的內容，例如 **2016-UPDATES**。
-   確保內容包括成本記錄。
-   允許輸入所有站點的成本記錄。 如果指定一個站點，則只能為該站點輸入成本記錄。
-   指示後饋原則為 **無**。 後饋原則僅適用於製造品項的成本計算。

若要更正、調整或更新新品項的標準成本，請執行以下步驟。

1.  使用 **成本計算版本設定** 頁面，以便將成本資料輸入到第二個成本計算版本中。 可以選擇阻止啟用待定成本，以便在準確定義待定成本後允許啟用。 您還可以選擇在 **開始日期** 欄位中輸入日期。 一般而言，請使用您打算啟用增量更新時的日期。 或者，將成本計算版本的 **開始日期** 欄位保留空白，然後在每個成本記錄的 **開始日期** 欄位中輸入日期。
2.  使用 **品項價格** 頁面以將更新輸入為包含在第二個成本計算版本中的品項成本記錄。
3.  使用 **品項價格** 報表以驗證包含在第二個成本計算版本中的品項成本記錄的完整性和準確性。
4.  使用 **成本計算版本維護** 頁面變更鎖定旗標，以允啟用第二個成本計算版本中的待定成本記錄。
5.  使用 **啟用價格** 頁面 (您從 **成本計算版本維護** 頁面打開的頁面) 啟用第二個成本計算版本中的所有待定品項成本記錄。 您還可以透過點選 **品項價格** 頁面上的 **啟用待定價格** 按鈕，啟用個別品項的待定成本記錄。
6.  若要防止進一步的資料維護，請使用 **成本計算版本設定** 頁面變更第二個成本計算版本中的鎖定旗標。 鎖定原則將阻止輸入新的待定成本和啟用待定成本。






[!INCLUDE[footer-include](../../includes/footer-banner.md)]