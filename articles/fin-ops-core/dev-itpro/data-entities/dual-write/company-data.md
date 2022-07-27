---
title: Dataverse 中的公司概念
description: 本主題介紹 Finance and Operations 與 Dataverse 之間的公司資料整合。
author: RamaKrishnamoorthy
ms.date: 08/04/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 3657e41363ca6c1ce8eabfeaf3ba6da9b93f5e2a
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460368"
---
# <a name="company-concept-in-dataverse"></a>Dataverse 中的公司概念

[!include [banner](../../includes/banner.md)]




在 Finance and Operations 中，*公司* 的概念既是法律結構，也是商業結構。 它也是資料的安全性和可見性邊界。 使用者總是在單個公司的內容中工作，並且大區段資料都是按公司串接的。

Dataverse 沒有等效的概念。 最接近的概念是 *事業單位*，它主要是使用者資料的安全性和可見性邊界。 這個概念與公司概念沒有相同的法律或商業含義。

因為事業單位和公司不是等價的概念，所以為了 Dataverse 整合的目的，不可能在它們之間強制進行一對一 (1:1) 的對應。 但是，由於預設情況下使用者必須能夠在應用程式和 Dataverse 中看到相同的資料列，因此 Microsoft 在 Dataverse 中引入了一個名為 cdm\_Company 的新表。 此表等效於應用程式中的 Company 表。 若要幫助確保應用程式和 Dataverse 立即可用之間的資料列可見性相同，我們建議對 Dataverse 中的資料進行以下安裝：

+ 對於啟用雙重寫入的每個 Finance and Operations Company 資料列，都會建立一個相關的 cdm\_Company 資料列。
+ 當建立 cdm\_Company 資料列並啟用雙重寫入時，將建立具有相同名稱的預設事業單位。 儘管為該事業單位自動建立了預設團隊，但並未使用該事業單位。
+ 將建立一個具有相同名稱的單獨所有者團隊。 它還與事業單位相關。
+ 在預設情況下，建立並雙重寫入 Dataverse 的任何資料列的擁有者都設定為連結到相關事業單位的「DW 擁有者」團隊。

下圖顯示了 Dataverse 中此資料安裝的範例。

![Dataverse 中的資料安裝。](media/dual-write-company-1.png)

由於此設定，與 USMF 公司相關的任何行都將由與 Dataverse 中的 USMF 事業單位連結的團隊擁有。 因此，透過設定為事業單位級別可見性的安全角色有權存取該事業單位的任何使用者現在都可以看到這些資料列。 以下範例顯示了如何使用團隊來提供對這些行的正確存取權限。

+ 「銷售經理」角色指派給「USMF 銷售」團隊的成員。
+ 具有「銷售經理」角色的使用者可以存取屬於他們所屬的同一事業單位的任何帳戶資料列。
+ 「USMF 銷售」團隊與前面提到的 USMF 事業單位相關。
+ 因此，「USMF 銷售」團隊的成員可以看到「USMF DW」使用者擁有的任何帳戶，這些帳戶可能來自 Finance and Operations 中的 USMF Company 表。

![如何使用團隊。](media/dual-write-company-2.png)

如上圖所示，業務部門、公司和團隊之間的這種 1:1 對應只是一個起點。 在此範例中，在 Dataverse 中手動建立了一個新的「歐洲」事業單位作為 DEMF 和 ESMF 的父級。 這個新的根事業單位與雙重寫入無關。 但是，透過在相關的資訊安全角色中將資料可見性設定為 **父/子 BU**，它可用於讓「EUR 銷售」團隊的成員存取 DEMF 和 ESMF 中的帳戶資料。

最後要討論的主題是雙重寫入如何確定應該將行指派給哪個擁有者團隊。 此行為由 cdm\_Company 資料列上的 **預設負責團隊** 資料欄控制。 當為雙重寫入啟用 cdm\_Company 資料列時，外掛程式會自動建立相關的事業單位和擁有者團隊 (如果尚不存在)，並設定 **預設所有者團隊** 資料欄。 管理員可以將此資料欄更改為不同的值。 但是，只要表啟用了雙重寫入，管理員就無法清除該資料欄。

> [!div class="mx-imgBorder"]
![預設負責團隊資料欄。](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>公司串接和啟用載入

Dataverse 整合透過使用公司識別碼對資料進行串接來實現公司同位。 如下圖所示，所有特定於公司的表都已擴展，因此它們與 cdm\_Company 表具有多對一 (N:1) 關係。

> [!div class="mx-imgBorder"]
![公司特定表和 cdm_Company 表之間的 N:1 關係。](media/dual-write-bootstrapping.png)

+ 對於資料列，新增並儲存公司後，該值變為讀取專用。 因此，使用者應確保選取正確的公司。
+ 只有具有公司資料的資料列才有資格在應用程式和 Dataverse 之間進行雙重寫入。
+ 對於現有的 Dataverse 資料，很快就會提供管理員主導的啟用載入體驗。


## <a name="autopopulate-company-name-in-customer-engagement-apps"></a>在 Customer Engagement 應用程式中自動填入公司名稱

有幾種方法可以在 Customer Engagement 應用程式中自動填入公司名稱。

+ 如果您是系統管理員，您可以透過導覽到 **進階設定 > 系統 > 安全性 > 使用者** 來設定預設公司 開啟 **使用者** 表單，並在 **組織資訊** 區段，設定 **公司在表格上預設** 值。

    :::image type="content" source="media/autopopulate-company-name-1.png" alt-text="在組織資訊區段設定預設公司。":::

+ 如果您對 **事業單位** 級別的 **SystemUser** 表具有 **寫入** 權限，則可以透過從 **公司** 下拉式選單中選取公司來更改任何表單上的預設公司。

    :::image type="content" source="media/autopopulate-company-name-2.png" alt-text="在新帳戶上更改公司名稱。":::

+ 如果您對多個公司的資料具有 **寫入** 權限，則可以透過選取屬於不同公司的行來更改預設公司。

    :::image type="content" source="media/autopopulate-company-name-3.png" alt-text="選取資料列會更改預設公司。":::

+ 如果您是系統設定者或管理員，並且想要在自訂表單上自動填入公司資料，則可以使用[表單事件](/powerapps/developer/model-driven-apps/clientapi/events-forms-grids)。 新增對 **msdyn_/DefaultCompany.js** 的 JavaScript 參考並使用以下事件。 您可以使用任何立即可用的表單，例如 **帳戶** 表單。

    + 該表單的 **OnLoad** 事件：設定 **defaultCompany** 資料欄。
    + **Company** 資料欄的 **OnChange** 事件：設定 **updateDefaultCompany** 資料欄。

## <a name="apply-filtering-based-on-the-company-context"></a>根據公司內容套用過濾器

若要在自訂表單或新增到標準表單的自訂查詢列上應用基於公司內容的過濾，請打開表單並使用 **相關記錄過濾** 區段以套用公司過濾器。 您必須為需要根據給定資料欄上的基礎公司進行過濾的每個查詢列設定此項。 下圖中顯示了 **帳戶** 的設定。

:::image type="content" source="media/apply-company-context.png" alt-text="套用公司內容。":::



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]