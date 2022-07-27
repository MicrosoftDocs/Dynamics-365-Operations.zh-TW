---
title: 多層級資產
description: 本主題介紹如何建立和刪除多層級資產。
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f43c7c97f8b05a1bf76b2f2c869e6868689f388d06337064f04af839f2403357
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447213"
---
# <a name="multi-level-assets"></a>多層級資產

[!include [banner](../../includes/banner.md)]

 

本主題介紹如何建立和刪除多層級資產。 您可以在階層樹狀結構中建立資產和相關子資產。 透過這種方式，您可以顯示資產之間的關係和相依性。 維護作業可以與樹狀結構的所有層級相關。 此外也可以為個別層級建立統計資料，或建立統計資料成為所有子資產層級的總和。

在 **所有資產** 清單頁面上 (**資產管理** \> **一般** \> **資產** \> **所有資產**)，**資產** 欄依階層順序列出資產。 **父系** 欄顯示相關的父系。 此外，如果已建立資產和子資產，則 **相關資訊** 窗格中的 **資產樹狀結構** 區段會依樹狀結構顯示資產。

有關如何建立資產的資訊，請參閱[建立資產 ](../objects/create-an-object.md)。 若要建立子資產，請在 **一般** FastTab 的 **父系** 欄位中選取父系資產。

## <a name="copy-an-asset-or-asset-structure"></a>複製資產或資產結構

如果您的公司有多個類似的資產結構，您可以使用資產管理中的複製功能快速建立資產結構。

1. 選取 **資產管理** \> **一般** \> **資產** \> **全部資產**。
2. 在 **所有資產** 清單頁面中，選取要複製的資產。 例如，如果您要複製整個資產結構，包括子資產，請選取父系資產。
3. 選取 **複製資產**。 在 **複製自** 區段中，**資產** 欄位會設定為您在清單頁面上選取的資產。
4. 在 **複製至** 區段的 **資產** 欄位中，輸入新資產的名稱。
5. 如果您正在建立的資產應該是現有資產結構的一部分，則在 **父系資產** 區段的 **資產** 欄位中，選取父系識別碼。
6. 選取 **確定**。 新的資產結構會顯示在 **所有資產** 清單頁面上。 與您所複製資產相關的所有資產屬性、維護計劃和維護回合都將轉移到新資產或資產結構中。

複製資產結構時，新結構中的子資產會與您複製的子資產同名。 複製過程完成後，您便可以輕鬆變更資產的名稱和其他設定。 在 **所有資產** 清單頁面上選取該資產，然後選取 **編輯** 按鈕。

> [!NOTE]
> 當您複製資產或資產結構時，新資產的生命週期狀態將重設為您定義為資產初始生命週期狀態的任何狀態。 功能位置會重設為預設的功能位置。

## <a name="delete-an-asset-or-asset-structure"></a>刪除資產或資產結構

如果資產具有相關子資產，則只有在任何資產上未登記維護要求、工單作業、故障登記或狀況評估時，您才能將該資產刪除。

1. 在 **所有資產** 清單頁面中，選取要刪除的資產。
2. 選取 **刪除**。

> [!NOTE]
> 如果您無法使用此程序刪除資產，則處理刪除的另一種方法就是針對此目的設定資產生命週期狀態。 例如，您可以在 **資產生命週期狀態** 頁面上設定 **已報廢** 或 **已刪除** 生命週期狀態。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]