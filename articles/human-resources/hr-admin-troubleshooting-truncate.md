---
title: 避免位置階層結構上的文字遭到截斷並匯出到 Visio
description: 本主題說明在 Microsoft Dynamics 365 Human Resources 職位階層結構中，個人和職位名稱遭到截斷的問題。
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7b11bd0247634290c8dc43c2ae2291a485449627
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452442"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a>避免位置階層結構上的文字遭到截斷並匯出到 Visio


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**問題**

當客戶檢視 Microsoft Dynamics 365 Human Resources 中的職位階層結構時，個人和職位名稱遭到截斷。 因此很難截取螢幕畫面，或列印和分佈階層結構。

![職位階層結構。](media/position-h.png)

**肇因**

此行為經過設計。

**解決方案**

很遺憾，使用者不能輕易變更文字大小。 然而您可以將職位階層結構匯出人力資源，接著匯入到 Microsoft Visio。 雖然下面文章是為 2012 年的 Microsoft Dynamics AX 撰寫，但流程上仍然適用人力資源：[將職位階層結構匯出 Microsoft Visio](/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio)。

請按照下列步驟匯出到 Visio。

1. 請在人力資源打開 **職位** 清單頁面。

    若要在組織結構圖納入更多資訊，請將欄位新增到 **職位** 清單，方便您在這項程序使用 **組織結構圖精靈**。

2. 請在操作窗格上選取 **在 Microsoft Office 打開** 按鈕，接著在 **匯出到 Excel** 下方選取 **職位**。 或者按下 Ctrl+T。

    ![將職位清單頁面匯出到 Excel。](media/org-admin.png)

3. 儲存已匯出的 Excel 檔案。

    ![匯出到 Excel 對話方塊。](media/export-excel.png)

4. 請在 Visio 選取 **Visio - 新建** 和 **商業** 範本類別。

    ![新示意圖。](media/new.png)

5. 選取 **組織結構圖精靈**，接著選取 **建立**。

    ![組織結構圖精靈對話方塊。](media/orgchart-wizard.png)

6. 請選取 **已經儲存在檔案或資料庫的資訊**，接著選取 **下一步**。

    ![組織結構圖精靈 1。](media/orgchart-wizard7.png)

7. 請選擇 **文字 A，Org Plus (\*.txt) 或 Excel 檔案**，接著選取 **下一步**。

    ![組織結構圖精靈 2。](media/orgchart-wizard3.png)

8. 瀏覽以選取包含職位階層結構的已匯出 Excel 檔案，接著選取 **下一步**。

    ![組織結構圖精靈 3。](media/orgchart-wizard2.png)

9. 設定 **姓名** 欄位為 **職位**、設定 **回報對象** 欄位為 **回報職位**，接著選取 **下一步**。

    ![組織結構圖精靈 4。](media/orgchart-wizard1.png)

10. 請選取應在每個節點上顯示的欄位，接著選取 **下一步**。

    ![組織結構圖精靈 5。](media/orgchart-wizard5.png)

11. 新增 **職位** 欄位到 **形狀資料欄位** 清單，接著選取 **下一步**。

    ![組織結構圖精靈 6。](media/orgchart-wizard6.png)

12. 圖片目前未開放使用。 因此請在下一頁選取 **下一步**。
13. 選取 **我希望精靈自動跨頁分解我的組織結構圖**。

    ![組織結構圖精靈 7。](media/orgchart-wizard4.png)

14. 選取 **完成**。

    如果有任何職位不在結構圖內，系統會請您將它們納入示意圖。

Visio 產生的示意圖在分開的工作表上顯示每一位經理。

根據您選取納入示意圖的欄位，每個節點都會在產生 Visio 檔案時顯示適當資訊。

![階層結構圖。](media/hierarchy.png)

**附加選項**

您也可以在人力資源使用 **人員** 工作區檢視一些階層結構相關資訊。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
