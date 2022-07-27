---
title: 維護工作人員和工作人員群組
description: 本主題介紹資產管理中的維護工作人員和工作人員群組。
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetWorkerGroupCopyFromResourceGroup, EntAssetWorkerGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e976a28349a4bc7a371d23eb4df724e0ffd36a0553aec2deeb2ff07d0a63579
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446973"
---
# <a name="maintenance-workers-and-worker-groups"></a>維護工作人員和工作人員群組

[!include [banner](../../includes/banner.md)]

 

本主題介紹資產管理中的維護工作人員和工作人員群組。 在資產管理中，您可以將維護工作人員連接到功能位置。 (有關功能位置的更多資訊，請參閱[建立功能位置](../functional-locations/create-functional-locations.md)。) 例如，如果您要在位於功能位置 01 的機器上安排維護作業，並且您希望指派同一位置的維護工作人員來執行該作業，則此功能可能很有用。

您還可以建立維護工作人員群組並將維護工作人員與其關聯。 當您執行簡單的工單排程並希望在工單上排成一組維護工作人員時，此功能很有用。 您可以使用維護工作人員和維護工作人員群組來設定首選維護工作人員和負責的維護工作人員。 


## <a name="create-workers"></a>建立工作人員

1. 選擇 **資產管理** \> **設定** \> **工作人員** \> **工作人員**。
2. 選擇 **新增** 將工作人員新增到清單。
3. 在 **工作人員** 欄位，選擇工作人員。
4. 將 **使用中** 選項設為 **是**，以為工單安排工作人員。

    如果為工作人員選擇了資源，將自動填寫 **一般** FastTab 上的 **資源** 和 **描述** 欄位。 也將自動填寫 **行事曆** 欄位，前提是已將工作人員設為資源，並且已在 **資源** 頁面 (**組織管理** \> **資源** \> **資源**) 上為該資源指派了行事曆。

5. 在 **群組** FastTab 上，選擇 **新增**，然後為工作人員選擇維護工作人員群組。 一個工作人員可以隸屬多個群組。
6. 在標准設定中，工作人員與群組的從屬關係自您新增群組之日起生效，並且永不過期。 此日期會顯示在 **生效** 欄位。 若要查看 **生效** 欄位，請選擇 **檢視** \> **全部**。 如果工作人員與群組的從屬關係應限制在特定期間，請使用 **生效** 和 **到期** 欄位來定義期間。
7. 在 **功能位置** FastTab 上，選擇 **新增**，然後為維護工作人員選擇功能位置。 並指定哪個位置是工作人員的主功能位置。

    > [!NOTE]
    > 當您向工作人員新增功能位置時，將在各功能表項目 (如 **我的有效資產** 和 **我的有效功能位置**) 上顯示與這些功能位置有關的所有有效資產。 其還顯示在您新建立資產、維護要求或工單時顯示的資產查詢中。

    **詳細資料** FastTab 上的欄位顯示與所選維護工作人員相關的維護工作人員群組和功能位置的數量。

## <a name="create-worker-groups"></a>建立工作人員群組

1. 選取 **資產管理** \> **設定**\>**工作人員**\>**維護工作人員群組**。
2. 選擇 **新增** 將工作人員群組新增到清單。
3. 在 **維護工作人員群組** 欄位，輸入群組識別碼。
4. 在 **名稱** 欄位中，輸入名稱。
5. 在 **工作人員** FastTab 上，選擇 **新增**，然後為工作人員群組選擇維護工作人員。 有關 **生效** 和 **到期** 欄位的資訊，請參閱上一程序中的步驟 6。
6. 如果資源群組應與所選維護工作人員群組關聯，請選擇 **從資源群組複製**。 在 **群組** 欄位中，選擇要從中複製行事曆設定的資源群組。 然後，在 **工作人員群組** 欄位，選擇要將資源群組的行事曆設定複製到的工作人員群組。 僅當您希望維護工作人員在工單排程期間使用與資源 (工作中心) 相關的行事曆時，此步驟才相關。

    **詳細資料** FastTab 上的欄位顯示已為所選維護工作人員群組設定的維護工作人員數量。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]