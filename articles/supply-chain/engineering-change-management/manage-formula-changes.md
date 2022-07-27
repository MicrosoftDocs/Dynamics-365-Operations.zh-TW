---
title: 管理配方及其成分的變更
description: 本主題介紹如何進行配方管理，與管理對流程製造主資料的變更。
author: t-benebo
ms.date: 05/19/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 31953fd29c471e52bd63dbb02c20f5f224c3cae2
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449943"
---
# <a name="manage-changes-in-formulas-and-their-ingredients"></a>管理配方及其成分的變更

[!include [banner](../includes/banner.md)]

如果您正在使用 Microsoft Dynamics 365 Supply Chain Management 的流程製造功能，您還可以使用相關的配方管理功能來管理以下變更：

- **配方及規劃項目：** 管理配方及其聯產品 (co-products) 與副產品 (by-products) 中成分的變化。
- **聯產品與副產品：** 編輯配方中聯產品和副產品的數量及其他資訊。
- **實秤重量品項：** 管理對實秤重量品項的變更。

## <a name="turn-this-feature-on-or-off"></a>開啟或關閉這項功能

本主題中說明的功能，必須在系統中打開功能 *工程變更管理* 和 *管理配方與成分的變更*。 更多關於如何打開或關閉這些功能的詳細資訊，請參閱[工程變更管理概述](product-engineering-overview.md)。

## <a name="feature-naming-conventions"></a>特徵命名規範

在 Supply Chain Management 使用者介面 (UI) 和文件中，變更管理功能通常稱為 *工程變更管理*，而可管理的產品通常被稱為 *工程產品*。 儘管此術語通常與流程製造的配方管理無關，但您應該將工程變更管理視為簡單變更管理，而將工程產品視為版本化產品。

## <a name="work-with-formula-change-management-features"></a>使用配方變更管理功能

以下清單總結了工程變更管理功能如何應用於配方管理。 它也提供更多的資訊連結。 由於配方變更管理利用了工程變更管理功能，因此您應該瞭解工程變更管理的一般工作原理，以便您使用它來管理您的配方及其成分。

- **集中式產品資料管理** – 建立一個組織，透過受管理發佈流程確保整個企業的使用者都可以使用準確且相關的產品資料。 如需詳細資訊，請參閱[工程公司和資料所有權規則](engineering-org-data-ownership-rules.md)。
- **產品版本控制** – 透過產品版本追蹤產品變更，並在供應鏈的各個階段控制產品。 如此一來，您便可以追蹤配方的變化。 如需詳細資訊，請參閱[工程版本與工程產品類別](engineering-versions-product-category.md)。
- **產品生命週期管理** – 管理整個組織中產品資料的能見度，並控制供應鏈每個階段的產品版本可用性。 您可以詳細控制何時可在特定業務流程中使用產品版本，並且可以建立自己的生命週期狀態，以滿足您的業務需求。 有關詳細資訊，請參閱[產品生命週期狀態和交易](product-lifecycle-state-transactions.md)。
- **配方變更管理** – 您整個組織中的使用者都可以要求變更配方。 使用變更單來評估並記錄提議變更造成的影響。 新增工作流程以管理變更過程，以及新版本產品及其配方的發佈。 如需詳細資訊，請參閱[管理工程產品變更](engineering-change-management.md)。
- **整備控制** – 使用系統檢查和使用者指南 (問卷和檢查清單) 以確保在產品發佈之前完整輸入所有必要的產品資料。 如需詳細資訊，請參閱[產品整備度](product-readiness.md)。
- **增強型產品發佈功能** – 從組織 (法律實體) 向其他法律實體發佈產品及其配方的完整定義版本。 您甚至可以決定是否必須在發佈前檢閱或編輯產品資訊。 如需更多資訊，請參閱[發布產品結構](release-product-structure.md)。

請注意，上一個清單中連結到的大多數主題，都提供了以物料清單 (BOM) 為依據的範例。 但是，配方的運作方式類似。 在您使用變更管理 (或僅配方變更管理) 來管理配方和 BOM 時，以下是一些實用的附加概念：

- 對於每個[產品工程類別](engineering-versions-product-category.md)，您可以指定生產類型 (BOM、配方或規劃品項)。 您還可以指定使用該類別的產品是否需要實秤重量支援。
- 聯產品和副產品不是工程產品。 因此，它們不是版本化的。 如果您必須變更它們，建立一個新產品即可。 這種方法使維護更為容易。
- 您可以管理作為 BOM 且具有子配方品項的成品。 該功能適用於包含配方和/或包含 BOM 配方的任何 BOM 組合。
