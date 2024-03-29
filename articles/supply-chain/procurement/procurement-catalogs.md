---
title: 採購目錄概觀
description: 本文描述採購專業人員如何設定和維護採購目錄的概況。 採購目錄定義公司員工可以訂購供內部使用的品項和服務。
author: Henrikan
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, CatDisplayProductRelationAdd
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2214"
- intro-internal
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: efe0541859822b4c6404f2833ae38e07b79dd634
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449721"
---
# <a name="procurement-catalogs-overview"></a>採購目錄概觀

[!include [banner](../includes/banner.md)]

本文描述採購專業人員如何設定和維護採購目錄的概況。 採購目錄定義公司員工可以訂購供內部使用的品項和服務。

採購專業人員可以建立和維護可採購供組織內部使用的品項與服務目錄。 設定目錄後，公司員工可以建立採購申請，以從該申請中訂購。 目錄可用於強制執行採購原則，讓員工只能訂購允許為其購買法律實體購買的品項和服務。 當您建立採購目錄時，您應考慮以下工作：

-   在建立目錄之前，請先設定您的採購類別階層。
-   決定您希望員工能夠訂購哪些產品。 您可以顯示或隱藏目錄節點中的特定產品，也可以顯示或隱藏節點中的所有產品。
-   決定您需要多少採購目錄。 對採購目錄的存取權由您為將員工指配到的法律實體和營運單位設定的目錄原則規則決定。

有幾個因素決定了員工可以訂購的產品，以及他們在建立採購申請時可以使用的採購類別：

-   採購原則中的類別存取原則規則決定採購申請中可用的採購類別。 如果未定義規則，則所有採購類別均可用。
-   只有產品位於您組織的使用中採購目錄中，並且位於已啟用節點中且未隱藏時，員工才能訂購該產品。 該產品也必須屬於特定員工根據類別存取原則規則可以存取的類別。
-   目錄策略規則指定使用的目錄。 如果未定義目錄原則規則，則類別存取規則會單獨決定員工可以在申請中訂購的產品。

## <a name="prerequisites"></a>先決條件
下表描述採購專業人員在建立採購目錄之前必須完成的工作。

| 工作                                                | 角色               | 描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 設定採購類別階層。            | 採購經理 | 採購類別階層會將品項或交易分類，以進行報告和分析。 透過使用採購類別階層，公司可以策略性地從一個中心位置管理類別、產品、廠商和其他採購因素。 系統會為整個組織定義一個採購類別階層。 目錄是以採購類別階層為基礎：階層中的類別會變成目錄中的節點。 廠商和產品包含在您的目錄中。 |
| 將廠商和產品新增到採購類別。 | 採購經理 | 為您的組織建立採購類別階層時，每個採購類別都可以與特定廠商、產品等相關聯。 這些關聯會自動複製到目錄中。                                                                                                                                                                                                                                                                                           |

## <a name="setting-up-a-catalog"></a>設定目錄
滿足先決條件後，您可以設定目錄。 您可以建立一個目錄供整個組織使用，或建立多個目錄供組織各個部門使用。 如果您為整個組織建立一個目錄，則對目錄的存取權由您的採購原則規則控制。  

目錄定義了在建立採購申請時哪些產品可用，但您可以使用類別存取原則規則以套用其他的限制。 因為目錄中的節點是採購類別，所以它們會被類別存取原則規則抑制。 在這種情況下，該類別中的產品無法供員工在申請時使用。 您可以在 **採購原則** 頁面上定義類別存取原則規則。 下表描述要設定目錄前必須先完成的工作。

| 工作                                                   | 角色             | 描述                                                                                                                                                                                                                                                                                                                  |
|--------------------------------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 建立新目錄                                  | 採購代理人員 | 建立目錄時，您會指定目錄的名稱和描述。 您還可以定義目錄是手動更新還是自動更新，並指定目錄擁有者。                                                                                                                                      |
| 控制產品在目錄中是否可用。 | 採購代理人員 | 因為產品繼承自採購類別，所以它們全部皆出現在適當的目錄節點中。 您可以控制當在採購申請中使用目錄時，要隱藏還是顯示節點中的所有產品。 您還可以控制要隱藏或顯示節點中的各個產品。 |
| 發佈目錄。                                   | 採購代理人員 | 在目錄可供員工在申請中使用之前，您必須先為目錄定義目錄原則規則，將目錄的狀態設置為 **使用中**，並發佈該目錄。 您可以停用您不再想要使用者使用的目錄。                                              |

更新可自動或手動發佈，取決於您在 **目錄** 頁面上的 **預設更新類型** 欄位中為目錄選擇的選項。 以下預設更新類型可用於目錄：

-   **動態** – 目錄只要有變更就會自動更新。
-   **靜態** – 必須手動更新目錄。
-   **兩者** – 如果目錄包含預設更新類型為 **靜態** 的產品類別，則當這些類別更新時，必須手動更新該目錄。 如果目錄包含預設更新類型為 **動態** 的產品類別，則目錄只要有變更就會自動更新。


## <a name="additional-resources"></a>其他資源

[設定採購類別階層](tasks/set-up-procurement-category-hierarchy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]