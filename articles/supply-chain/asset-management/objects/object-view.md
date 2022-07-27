---
title: 資產檢視
description: 本主題說明資產管理中的資產檢視。
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTree, EntAssetFunctionalLocationTree
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4265928fc5cb899a77eee6e5b9ff0a928efbe99c99ec7fe31eecffcb0f98f752
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447150"
---
# <a name="asset-view"></a>資產檢視

[!include [banner](../../includes/banner.md)]

 

本主題說明資產管理中的資產檢視。 **資產檢視** 頁面會以樹狀結構檢視顯示使用中的資產和功能位置。 因此，您可以輕鬆瞭解資產與功能位置的關係。 此外，您還可以檢視與功能位置、資產和相關物料清單 (BOM) 相關的詳細資訊。 您還可以快速瞭解與資產相關的使用中維護要求和工單。

1. 選取 **資產管理** \> **一般** \> **資產** \> **資產檢視**。
2. 若要變更頁面上顯示的檢視，請在 **檢視** 欄位中選取新的值。

    > [!NOTE]
    > 當您開啟 **資產檢視** 頁面時顯示的預設檢視取決於在 **資產管理參數** 頁面 (**資產管理** \> **設定** \> **資產管理參數**) 的 **資產** 索引標籤上 **檢視** 欄位中選取的值。

在頁面右側，FastTabs 會顯示所選檢視的詳細資料。

在樹狀結構檢視上方出現的階層連結導覽會以樹狀結構檢視顯示目前的選擇。 此階層連結導覽使用以下格式：

功能位置識別碼/功能位置識別碼 (如果有多個功能位置)\>資產識別碼/資產識別碼 (如果有多個資產) - 項目編號。

如果您在樹狀結構檢視中選取一個資產，則可以選取 **使用中要求** 或 **使用中工單** 以檢視與資產相關的維護要求或工單。 您也可以選取 **開啟** \> **功能位置**、**資產** 或 **資產 BOM** 以開啟相關檢視。

您在 **檢視** 欄位中可以選取的 **資產功能位置** 選項，在您可以選取資產的任何資產查詢中也可使用。 樹狀結構檢視會顯示在 **資產檢視** 索引標籤上，舉例來說，您在此處可[建立資產](../objects/create-an-object.md)、建立維護要求或建立工單。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]