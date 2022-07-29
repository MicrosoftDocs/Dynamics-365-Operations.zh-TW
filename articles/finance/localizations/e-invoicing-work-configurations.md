---
title: 使用設定
description: 本主題概述了使用全球化功能工作區中電子申報 (ER) 設定的主要方案。
author: dkalyuzh
ms.date: 01/26/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4318399ee58ed54b29f8d360345b8930238ea9f2
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451725"
---
# <a name="work-with-configurations"></a>使用設定

[!include [banner](../includes/banner.md)]

電子報告 (ER) 設定是電子發票功能的主要組件之一。 ER 設定包含文件結構的設定和一組用於以兩種方式轉換資料的轉換規則：

- **匯出 ER 格式設定** - 此設定將資料從統一的內部結構 (ER 模型) 轉換為電子檔案格式。
- **匯入 ER 格式設定** - 此設定將資料從電子檔案格式轉換為統一的內部結構 (ER 模型)。

除了以預定義格式生成出站電子文件外，ER 設定也廣泛用於解析來自外部 Web 服務的傳入訊息作為回應。 此功能有助於建立可設定邏輯以獲取與外部通道通信的結果，將這些結果 (代碼、訊息和日誌) 轉換為使用者可讀的結構，然後將該資訊傳遞給客戶端應用程式。

若要開始在您的電子發票功能中使用 ER 設定，您必須將它們連結到該功能並使其在當前功能版本的 **設定** 索引標籤上可用。 您可以透過選擇 **新增**、**刪除**、**編輯** 或 **檢視** 來使用連結的 ER 設定。

在您可以新增指向 ER 設定的連結之前，該設定必須存在於您的 Regulatory Configuration Service (RCS) 存放庫中。 若要查看 RCS 存放庫中可用的 ER 設定，請執行以下步驟。

1. 登入您的 RCS 帳戶。
2. 在 **電子報告** 工作區的 **設定** 部分中，選擇 **報告設定** 區塊。

關於如何建立新 ER 設定或從全域存放庫匯入現有 ER 設定的資訊，請參閱[電子報告](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md)。

若要調整連結的 ER 設定，請在 **設定** 索引標籤上為當前電子發票功能選擇 **編輯**。 系統會自動建立 ER 設定的版本。 如果目前版本不是由活動設定提供者建立，系統會建立一個使用您的設定提供者的衍生版本。 如果目前版本是由活動設定提供者建立的，則系統會建立一個新版本。 在這兩種情況下，您都可以修改建立的版本，然後自動執行所有必需的更新。
