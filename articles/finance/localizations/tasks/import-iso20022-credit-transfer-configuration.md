---
title: 匯入 ISO20022 貸記轉帳配置
description: 本項程序顯示如何匯入廠商付款電子報表配置。
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ffc86ba9dade0ae494ca4ace8d9f562da9c9527a4731493d892b60112293af3f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450885"
---
# <a name="import-iso20022-credit-transfer-configuration"></a>匯入 ISO20022 貸記轉帳配置

[!include [banner](../../includes/banner.md)]

本項程序顯示如何匯入廠商付款電子報表配置。 以德國 ISO 20022 信用轉移格式為例。 本項程序可用在其他開放使用的電子報表格式。 

本任務使用示範資料的公司 DEMF 建立，但您可以使用任何示範資料公司完成本任務。

這是五項任務當中的第一個，一同圖說使用電子報表配置的廠商付款流程。 此程序是 Dynamics 365 for Operations 版本 1611 中增加的功能。

1. 前往組織行政管理 > 工作區 > 電子報表。
2. 在開放的配置提供商清單選取 Microsoft。
3. 點選設定為有效。
4. 點選儲存庫。
5. 點選開啟。
6. 點選顯示篩選條件。
7. 套用下列篩選條件：使用 "開頭" 篩選運算子在 "配置名稱" 欄位輸入 "ISO20022 信用轉移 (DE)" 篩選條件值。
    * 您可以選擇性地在列表尋找配置並且選取後，移動到匯入任務。  
8. 點選匯入。
    * 如果匯入按鈕尚未開放使用，表示配置已經匯入。  
9. 點選是。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]