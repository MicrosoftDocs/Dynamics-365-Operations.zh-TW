---
title: 在機能位置安裝資產
description: 本主題說明如何在資產管理中的機能位置安裝資產。
author: johanhoffmann
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationObjectChange, EntAssetFunctionalLocationObjectInstall, EntAssetFunctionalLocationObject
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc278564b02335b44a0b35d6a3a981125e6f456b08893be2b5886f0a55396d52
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447264"
---
# <a name="install-assets-on-functional-locations"></a>在機能位置安裝資產

[!include [banner](../../includes/banner.md)]

 

建立機能位置結構後，下一步便是在相關機能位置安裝資產。 本主題說明如何在資產管理中的那些機能位置安裝資產。 如需有關如何建立資產的資訊，請參閱[資產介紹](../objects/introduction-to-objects.md)。

如果您已建立資產結構，則必須將整個資產結構安裝在機能位置。 因此，在機能位置上只能選擇父系資產 (沒有父系資產的最高層資產)。 所有相關的子系資產 (子資產) 也將安裝在機能位置。 在機能位置安裝資產時，機能位置的財務維度可能會自動傳輸過去，取決於機能位置選擇的機能位置類型設定。 如需如何設定機能位置類型的詳細資訊，請參閱[機能位置類型](../setup-for-functional-locations/functional-location-types.md)。

> [!NOTE]
> 您可以在用於機能位置的機能位置類型上設定資產類型。 在這種情況下，當您在機能位置安裝資產時，只有具相同資產類型的父系資產，才會顯示在可安裝於機能位置的資產清單中。

在機能位置安裝資產後，您可以視需要替換父系資產或資產結構。 與安裝資產時一樣，您會選擇要替換的父系資產。 所有相關的子系資產也將被替換。 


## <a name="install-an-asset-structure-on-a-functional-location"></a>在機能位置安裝資產結構

1. 選擇 **資產管理** \> **通用** \> **機能位置** \> **所有機能位置** 或 **使用中機能位置**。
2. 選擇要安裝資產的機能位置。
3. 選擇 **安裝資產**。

    **屬性** 部分顯示了為機能位置選擇的機能位置類型上設定的資產屬性要求清單。 該屬性僅供參考。 系統不會根據您正在安裝的資產上設定的資產屬性來驗證這些屬性。 您必須在 **資產** 欄位選擇資產後才進行該驗證。

4. 在 **資產** 欄位中，選擇要安裝的父系資產。 所有相關的子系資產都會自動包含在安裝中。

    資產清單右側的 **資產屬性** 部分，會顯示與所選資產相關的資產屬性。

5. 在 **生效** 欄位中，選擇資產安裝的有效日期和時間。 在該日期和時間之後，資產和相關子資產的成本將與機能位置相關。

    > [!NOTE]
    > 在資產上設定的資產屬性將新增到 **屬性** 部分。 例如，**重量** 屬性要求已被新增為對資產和機能位置的要求。 如果資產具有與機能位置相同類型的屬性要求，則該資產的屬性要求值會被輸入到 **值** 欄位中。 因此，您可以根據機能位置上設定的屬性要求驗證資產值。 在機能位置上設定的屬性要求會標有核取符號。

6. 選擇 **確定**。

    > [!NOTE]
    > 若要透過將資產安裝在新的機能位置來變更資產的安裝，請執行此程序的步驟 1 到 6。 當您在新的機能位置安裝資產時，該資產會自動從以前的機能位置解族安裝。 在您將資產安裝到新機能位置之前，在資產上建立的任何使用中維護要求或工單都 **不會** 自動轉移到新的機能位置。 如果資產仍需要這些維護請求和工單，則您必須在將資產安裝到新位置後手動重新進行建立。

7. 如要檢視安裝在機能位置的所有資產 (包括子資產) 的清單，請在 **所有機能位置** 頁選擇機能位置，然後選擇 **資產**。
8. 如要檢視與安裝在機能位置的資產相關的使用中維護要求、有效工單或故障登記的清單，請選擇 **所有機能位置** 頁面上的機能位置，然後選擇 **請求**、**工單**，或 **錯誤**。

> [!NOTE]
> 當資產相關資料變更時，它會在安裝資產的機能位置上自動更新。 此自動更新對維護請求、工單、資產異常登記、維護停機時間登記，和資產測量登記的變更有關。

## <a name="automatically-create-one-asset-on-a-functional-location"></a>在機能位置自動建立一項資產

您可以設定機能位置階段和機能位置類型來處理機能位置上的 *一個* 資產的自動建立。 該資產取得與機能位置相同的識別碼和名稱。 當您處理大型靜態資產 (例如建築物) 的維護時，此機能可能很實用。

在您可以在機能位置上自動建立資產之前，以下設定資料必須為可用：

- 建立機能位置類型以處理資產的自動建立。 在 **資產類型** 欄位中，選擇資產類型。 如需詳細資訊，請參閱[機能位置類型](../setup-for-functional-locations/functional-location-types.md)。
- 建立機能位置生命週期狀態以處理資產的自動建立。 將 **建立資產** 選項設為 **是**。 如需詳細資訊，請參閱[機能位置生命週期狀態](../setup-for-functional-locations/functional-location-stages.md)。

設定資料可用後，您就可以建立資產了。

1. 在 **所有機能位置** 頁面，請確認您希望自動建立資產的機能位置使用您為此目的建立的機能位置類型。
2. 選擇清單中的機能位置。
3. 選擇 **更新機能位置狀態**，然後選擇您為此目的建立的生命週期狀態。 現在，一項資產會自動安裝在機能位置上。 此資產擁有與機能位置相同的名稱。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]