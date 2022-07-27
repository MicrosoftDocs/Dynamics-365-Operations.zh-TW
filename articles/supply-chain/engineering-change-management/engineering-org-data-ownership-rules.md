---
title: 工程公司和資料所有權規則
description: 本主題說明如何使用一個或多個工程公司，來確保集中建立和維護產品的主資料。 工程公司代表擁有工程產品及其工程相關資料的公司。
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEngineeringOrganization
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1a05ad1a9d24239e2659c1ffecc21e5e186b1e96
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448569"
---
# <a name="engineering-companies-and-data-ownership-rules"></a>工程公司和資料所有權規則

[!include [banner](../includes/banner.md)]

## <a name="engineering-companies-and-operational-companies"></a>工程公司和營運公司

為了確保集中建立和維護產品主資料，您可以使用一個或多個 *工程公司*。 工程公司擁有自己工程產品及其工程相關資料。 始終和 (基於) 現有的 *法律實體* 保持連線，該法律實體也是一家公司。 透過連線，系統為工程公司中的工程產品，和所有工程相關的資料，建立了一個集中進入點。 在此集中進入點中，可以建立工程產品，並維護與工程相關的資料。 從這個地方，工程產品和工程相關的資料，會發布至 *營運公司*，該營運公司是其他法律實體。 (如需關於發布管理的資訊，請參閱[發布產品結構](release-product-structure.md)。) 這些營運公司會使用由工程公司所設計的工程資料。 任何後勤資料都由每個工程公司和運營公司於本機維護。

若要建立工程公司，前往 **工程變更管理\>設定\>工程組織**。 選擇 **新增**，輸入工程公司的名稱，然後選擇它所基於的現有公司 (法律實體)。

如果您要與外部產品生命週期管理 (PLM) 系統整合，則必須建立一個將成為外部公司的事業單位 (公司類型)。

## <a name="engineering-product-categories-and-engineering-companies"></a>工程產品類別和工程公司

*工程產品類別* 幫助確保工程產品，都是根據您公司業務規則和要求的行為所建立。 有關工程產品類別的詳細資訊，請參閱[工程版本和工程產品類別](engineering-versions-product-category.md)。

每個工程產品類別都屬於特定的工程公司，並且只能建立屬於該公司的產品。 同樣，維護工程產品的權利，也屬於與該產品的工程產品類別相關聯的公司。

## <a name="data-that-is-owned-by-the-engineering-company"></a>工程公司擁有的資料

由於工程公司擁有與工程相關的資料，因此控制以下流程：

- **工程產品的建立：** 每個工程公司只能以自己的工程產品類別為基礎，建立新的工程產品。 在某些情況下，營運公司維護與這些產品相關的本地資料。
- **建立工程版本：** 當公司建立新的工程產品時，系統會自動為其建立初始工程版本。 只有所屬工程公司，才能建立該產品的新版本。
- **建立和維護工程版本：** 當公司建立新的工程產品時，系統會自動為其新增工程屬性。 只有所屬工程公司，才能建立和維護這些屬性的值。 如需關於工程屬性的詳細資訊，請參閱[工程屬性與工程屬性搜尋](engineering-attributes-and-search.md)。
- **建立和維護與工程版本相關的材料清單 (BOM)：** 所屬工程公司可以直接將 BOM 連接到工程產品版本。 將 BOM 發布給其他法律實體時，變更 BOM 的工程資料受到以下方式限制：

    - 運營公司無法刪除已發布的 BOM 行。
    - 運營公司僅能讀取工程欄位上的 BOM 行。 所有其他欄位為物流操作欄位，可由運營公司進行編輯。
    - 運營公司可將 BOM 行新增至同一個 BOM。 如此，就可以新增額外的本地資訊，例如：包裝材料或潤滑液。
    - 運營公司可以新增全新、本地的 BOM。 如果發布期間，沒有提供 BOM 的情況下，可能會需要進行此變更。 運營公司可以擁有並維護本地 BOM。 如需關於版本管理的資訊，請參閱[產品版本結構](release-product-structure.md)。
    - 工程公司更新其 BOM 時，所有本地 BOM 和 BOM 行都會保留。

- **建立和維護與工程版本相關的路徑：** 所屬工程公司可以直接將路由連接至每個工程產品版本。 將路徑發布給其他法律實體時，變更路由資料受到以下方式限制：

    - 其他法律實體無法移除路徑上的工程資料。
    - 其他法律實體可以將作業新增至路徑。 如此一來，他們就可以新增本地路徑步驟。
    - 營運公司可以新增全新、本地的路徑。 如果發布期間，沒有包括路徑的情況下，可能會需要進行此變更。 營運公司可以擁有並維護本地路徑。 如需關於版本管理的資訊，請參閱[產品版本結構](release-product-structure.md)。
    - 當工程公司再次發布更新至路徑時，所有本地的變更都會保留。

- **建立和維護工程文件：** 工程公司可以將工程文件附加至每個工程版本。

    - 當文件發布給其他法律實體時，文件會受到保護，而不會被運營公司刪除。
    - 其他法律實體可以新增全新、本地的文件。 運營公司可以擁有並維護本地文件。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]