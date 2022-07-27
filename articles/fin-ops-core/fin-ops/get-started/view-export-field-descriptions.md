---
title: 檢視和匯出欄位說明
description: 本文介紹如何查看欄位描述以及如何使用「欄位描述」頁面匯出描述。
author: rschloma
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ea52c39ef1c7d7b62f20da9fe4d94103119ccc23
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460298"
---
# <a name="view-and-export-field-descriptions"></a>檢視和匯出欄位說明

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本文介紹如何查看欄位描述以及如何使用「欄位描述」頁面匯出描述。

有些更複雜的欄位具有欄位描述。 當您將游標停在某個欄位上時，就會出現這些描述。 您還可以在 **欄位描述** 頁面上查看和匯出描述。

並非所有頁面都有欄位描述。 我們只想為更複雜的欄位提供描述，而不是在欄位使用明顯的地方提供描述。 因此，有些頁面沒有任何欄位描述，有些頁面有一些描述，而一些更複雜的頁面，例如很多參數頁面，有很多描述。

如果您有權存取開發環境，則可以新增新欄位描述並自訂現有描述。 例如，您可以將公司特定資訊新增到欄位描述中。 如需相關資訊，請參閱[自訂欄位描述](../../dev-itpro/user-interface/customize-field-help.md)。

## <a name="see-field-descriptions-in-the-user-interface"></a>查看使用者介面中的欄位說明

您可以透過將游標停在欄位上來查看欄位描述。 如果沒有可用的描述，當您將游標停在該欄位上時，您會看到該欄位名稱。

> [!NOTE]
> 在 Dynamics AX 7.0 (2016 年 2 月) 中，只能在 **欄位描述** 頁面上查看欄位描述。

下圖顯示了當您將游標停在 **計數期間鎖定項目** 欄位上時出現的欄位描述。

[![欄位描述範例。](./media/field-description.png)](./media/field-description.png)

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a>使用欄位描述頁面查看和導出欄位幫助

**欄位描述** 頁面允許您查看和導出欄位描述。 您可以一次查看一頁可用的說明。

### <a name="view-the-descriptions-for-a-page"></a>查看頁面的描述

若要查看頁面的描述，請執行此步驟。

- 在 **選取一個頁面** 欄位中，輸入頁面的名稱。 或者，點選箭頭打開所有頁面的清單，然後瀏覽或篩選清單。

您可以使用使用者介面 (UI) 中顯示的頁面名稱 (例如，**客戶**) 或按右鍵點選頁面時可用的代碼名稱 (AOT 名稱) (例如，**CustTable**)。

如需篩選頁面清單的各種方法相關資訊，請參閱本文後面的「搜尋頁面」章節。

如果您將 **包括沒有描述的欄位** 選項設定為 **是**，頁面上的所有欄位都會顯示，即使它們沒有欄位說明。

### <a name="export-the-descriptions-for-a-page"></a>匯出頁面的描述

若要匯出頁面的描述，請執行這些步驟。

1. 在 **選取一個頁面** 欄位中，選取一個頁面。
2. 點選 **在 Microsoft Office 中開啟** 按鈕，然後點選 **FieldDescriptionTmp**。

### <a name="searching-for-a-page"></a>搜尋頁面

有多種方法可以在 **選取頁面** 欄位中搜尋頁面。 在許多情況下，您必須點選 **選取一個頁面** 欄位以打開下拉式清單，然後從篩選的頁面清單中進行選取。

- 輸入部分名稱，然後打開下拉式清單以從篩選的頁面清單中進行選取。
- 打開下拉式清單，然後點選清單頂部的 **頁面名稱** 標題或 **頁面 AOT 名稱** 標題。 將出現一個對話方塊，您可以在其中使用進階篩選選項，例如 **頁面名稱開頭**。
- 輸入頁面的全名。 使用此選項時，最好打開下拉式清單並查看清單中的其他內容，即使顯示了欄位說明。

    - 如果名稱完全相符，則會顯示該頁面的欄位描述。
    - 如果有多個完全相符，則不顯示任何描述。 您必須打開下拉式清單並選取所需的頁面。
    - 如果您輸入的名稱是另一個頁面名稱的一部分，您會看到您的頁面的描述。 但是，如果您打開下拉式清單，您會看到包含該名稱的其他頁面。

例如，當您在 **選取頁面** 欄位中輸入 **計數** 時，不會顯示任何描述。 打開下拉式清單，您會看到有兩個頁面的名稱為 **計數**，還有幾個頁面的名稱中包含「計數」一詞。 如果您選取具有 AOT 名稱 **InventJournalCount** 的頁面，則會顯示該頁面的欄位描述。 但是，如果您再次打開下拉式清單，您將看到該清單現在包含所有將「InventJournalCount」作為其 AOT 名稱一部分的頁面。

## <a name="troubleshooting"></a>疑難排解

本節提供的資訊可幫助您解決在使用欄位描述時可能遇到的問題。

### <a name="i-cant-find-a-field-description"></a>我找不到欄位說明

我們正在為更複雜的欄位新增描述。 如果您需要特定領域的幫助，請透過為此主題新增評論來告知我們。

### <a name="the-field-description-isnt-helpful"></a>欄位描述沒有幫助

透過為此主題新增評論讓我們知道。 如果可以，請描述您需要的其他資訊。

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a>我在欄位描述頁面上找不到欄位

若要顯示頁面上的所有欄位，請將 **包含沒有描述的欄位** 選項設定為 **是**。 點選 **選取一個頁面** 欄位以驗證您是否選取了正確的頁面。 如果您鍵入的名稱是另一個欄位名稱的一部分，則您可能選取了名稱較長的頁面。

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a>我在欄位描述頁面上找不到頁面

如需查詢頁面的各種方法相關資訊，請參閱本文前面的「搜尋頁面」部分。 如果您輸入了頁面的確切名稱，如果多個頁面具有相同的名稱，則可能不會顯示欄位說明。 點選 **選取頁面** 欄位中的箭頭以打開可用頁面的篩選清單。

## <a name="additional-resources"></a>其他資源

[自訂欄位描述](../../dev-itpro/user-interface/customize-field-help.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]