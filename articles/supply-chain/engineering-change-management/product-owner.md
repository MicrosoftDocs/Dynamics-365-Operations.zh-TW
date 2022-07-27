---
title: 產品擁有者
description: 本主題提供有關產品擁有者的資訊。 產品擁有者是負責特定產品的一組使用者。 只有該組的成員才能發佈那些產品。 產品擁有者也可用於核准工作流程。
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a29ab169e9b24826fbe69fbc316040d4618750ee
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448020"
---
# <a name="product-owners"></a>產品擁有者

[!include [banner](../includes/banner.md)]

該產品擁有者是負責特定產品的一組使用者。 將產品擁有者群組指派給產品後，只有該組的成員才能發佈產品。 該產品擁有者也可在工程變更管理中用於核准工作流程。

產品擁有者是全域設定。 因此，它們可供所有法律實體使用。

## <a name="create-a-product-owner-group"></a>建立產品擁有者群組

要建立產品擁有者群組並向其新增成員，請按照以下步驟操作。

1. 前往 **工程變更管理 \> 設定 \> 產品擁有者**。
2. 在動作窗格上，選擇 **新增**。
3. 在 **產品擁有者** 欄位內輸入該群組的名稱。
4. 在 **名稱** 欄位中輸入該群組的描述。
5. 在 **成員** FastTab 上，新增應該是該群組成員的工作人員。

## <a name="assign-a-product-owner-to-a-product"></a>將產品擁有者指派給產品

要將產品擁有者指派給產品，請依以下步驟操作。

1. 打開相關產品或基準產品的 **產品詳細資料** 頁面。
1. 在 **一般** FastTab 上，將 **產品擁有者** 欄位設到相關產品擁有者群組的名稱。

將產品擁有者指派給產品時，只有該產品擁有者群組的成員可以編輯 **產品擁有者** 設定。

產品擁有者也會顯示在 **已發佈產品** 頁面上。

## <a name="product-owners-and-product-releases"></a>產品擁有者和產品發佈

只有產品的產品擁有者群組中的使用者才能發佈該產品。 但是，當產品是子項目，且其父系項目由父系項目的擁有者發佈時，會有一個例外。 換句話說，如果該產品是另一個產品的 BOM 的一部分，則系統不會檢查 BOM 中每個項目的產品擁有者。 它僅檢查父系項目的產品擁有者。

例如，產品 X 指派給 *設計櫃* 產品擁有者群組。 產品 X 也是產品 Y 的 BOM 的一部分，該 BOM 指派給 *設計揚聲器* 產品擁有者群組。 如果來自 *設計揚聲器* 產品擁有者群組的使用者發佈產品 Y 及其 BOM，則產品 X 將與產品 Y 一起發佈。

## <a name="product-owners-and-approvals"></a>產品擁有者和核准

因為產品擁有者知道特定的工程變更是否會使他們的產品受益，所以將它們作為工程變更管理核准過程的一部分通常是有意義的。 您可以透過將產品擁有者設定為用於工程變更管理的工作流程中的參與者提供者來實施此方法。 然後根據工程變更要求和工程變更單中的產品，系統將會在工作流程中指派核准任務。 如需詳細資訊，請參閱[管理工程產品變更](engineering-change-management.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]