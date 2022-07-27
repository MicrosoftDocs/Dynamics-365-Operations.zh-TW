---
title: 自訂生產現場執行介面
description: 本主題說明如何為生產現場執行介面擴展當前表單或建立新表單和按鈕。
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-11-08
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 67fb381cbef6f1673afcaa834666b4a859bdf4e6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449868"
---
# <a name="customize-the-production-floor-execution-interface"></a>自訂生產現場執行介面

[!include [banner](../includes/banner.md)]

開發人員可以為生產現場執行介面擴展當前表單或建立他們自己的表單和按鈕。 為這些新元素新增代碼後，管理員或工廠經理可以使用標準設定控件輕鬆地將它們新增到介面。

例如，如果在主要表單中需要新欄，以下是一些可能的解決方案：

- 擴展 `JmgProductionFloorExecutionMainGrid` 表單，然後新增所需的欄位。
- 建立一個新表單，並將其新增為新的主檢視表（索引標籤）。

## <a name="add-a-new-button-action"></a>新增新按鈕（動作）

要新增新按鈕（動作），請按照以下步驟建立一個實現您的自訂動作的類別。

1. 建立一個新類別，名為 `<ExtensionPrefix>_JmgProductionFloorExecution<ActionName>Action`，在那裡：

    - `<ExtensionPrefix>` 唯一識別您的解決方案，通常使用您的公司名稱。
    - `<ActionName>` 是該類別的唯一名稱。 它通常識別動作的類型。

1. 新類別必須擴展 `JmgProductionFloorExecutionAction` 類別。
1. 覆寫所有必要的方法。

例如，查看以下類別的代碼：

- `JmgProductionFloorExecutionBreakAction` –不需要任何記錄的簡單動作的類別。
- `JmgProductionFloorExecutionReportFeedbackAction` –提供更複雜功能的類別。

當您完成後，新按鈕（動作）將自動列在 Microsoft Dynamics 365 Supply Chain Management 的 **設計索引標籤** 頁面上。 在那裡，您（或管理員或工廠經理）可以輕鬆地將其新增到主要或次要工具列，就像您可以新增標準按鈕一樣。 如需說明，請參閱 [設計生產現場執行介面 ](production-floor-execution-tabs.md)。

## <a name="add-a-new-main-view"></a>新增新的主檢視表

1. 建立一個具有所需元素和功能的新表單。 請注意，此表單是一個新表單，而不是擴充。 為該表單命名為 `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`，在那裡：

    - `<ExtensionPrefix>` 唯一識別您的解決方案，通常使用您的公司名稱。
    - `<FormName>` 是該表單的唯一名稱。

1. 建立一個功能表項目，該項目名為 `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`。
1. 建立一個名為 `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension` 的擴充，其中`getMainMenuItemsList` 方法會透過將新功能表項目新增到清單中來擴展。 以下代碼顯示一個範例。

    ```xpp
    [ExtensionOf(classStr(JmgProductionFloorExecutionForm))]
    public final class <ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>_Extension{
        static public List getMainMenuItemsList()
        {
            List menuItemList = next getMainMenuItemsList();
            menuItemList.addEnd(menuItemDisplayStr(<ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>));
            return menuItemList;
        }
    ```

當您完成後，新的主檢視表將自動列在 Supply Chain Management 中的 **設計索引標籤** 頁面上的 **主檢視表** 下拉式方塊內。 在那裡，您（或管理員或工廠經理）可以輕鬆地將其新增到新的或現有的索引標籤，就像您可以新增標準主檢視表一樣。 如需說明，請參閱 [設計生產現場執行介面 ](production-floor-execution-tabs.md)。

## <a name="add-a-details-view"></a>新增詳細資料檢視表

1. 建立一個具有所需元素和功能的新表單。 請注意，此表單是新的，而不是擴充。 為該表單命名為 `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`，在那裡： 

    - `<ExtensionPrefix>` 唯一識別您的解決方案，通常使用您的公司名稱。
    - `<FormName>` 是該表單的唯一名稱。

1. 建立一個功能表項目，該項目名為 `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`。
1. 建立一個名為 `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension` 的擴充，其中`getDetailsMenuItemList` 方法會透過將新功能表項目新增到清單中來擴展。

當您完成後，新的詳細資料檢視表將自動列在 Supply Chain Management 中的 **設計索引標籤** 頁面上的 **詳細資料檢視表** 下拉式方塊內。 在那裡，您（或管理員或工廠經理）可以輕鬆地將其新增到新的或現有的索引標籤，就像您可以新增標準詳細資料檢視表一樣。 如需說明，請參閱 [設計生產現場執行介面 ](production-floor-execution-tabs.md)。

## <a name="add-a-numeric-keypad-to-a-form-or-dialog"></a>將數字鍵盤新增到表單或對話方塊

以下範例顯示如何將數字鍵盤新增到表單。

1. 每個表單包含的數字鍵盤控制器的數量必須等於該表單中的數字鍵盤的數量。

    ```xpp
    private JmgProductionFloorExecutionNumpadController   numpadController1;
    private JmgProductionFloorExecutionNumpadController   numpadController2;
    private JmgProductionFloorExecutionNumpadController   numpadController3;
    ```

1. 設定每個數字鍵盤控制器的行為，並將每個數字鍵盤控制器連接到一個數字鍵盤組件。

    ```xpp
    /// <summary>
    /// Initializes all numpad controllers, defines their behavior and connects them with numpad form parts.
    /// </summary>
    public void initializeNumpadController()
    {
        numpadController1 = new JmgProductionFloorExecutionNumpadController();
        numpadController1.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_1);
        QuantityNumpad1.getPartFormRun().setNumpadController(numpadController1);
    
        numpadController2 = new JmgProductionFloorExecutionNumpadController();
        numpadController2.parmNumpadEnabled(false);
        numpadController2.parmNumpadValue(333.56);
        numpadController2.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_2);
        QuantityNumpad2.getPartFormRun().setNumpadController(numpadController2);
    }
    ```

## <a name="use-a-numeric-keypad-as-a-pop-up-dialog"></a>使用數字鍵盤作為快顯對話方塊

以下範例顯示為快顯對話方塊設定數字鍵盤控制器的一種方法。

```xpp
private void setupNumpadController()
{
    numpadController = new JmgProductionFloorExecutionNumpadController();
    numpadController.parmShouldNumpadShowOkCancelButtons(true);
    numpadController.setNumpadValueToParentFormDelegate += eventhandler(this.setQtyValueFromNumpad);
}
```

以下範例顯示呼叫該數字鍵盤快顯對話方塊的一種方法。

```xpp
Args args = new Args();
args.name(formstr(JmgProductionFloorExecutionNumpad));
args.menuItemName(menuItemDisplayStr(JmgProductionFloorExecutionNumpad));
args.caller(element);
Object formRun = classfactory.formRunClass(args);
formRun.init();
formRun.setNumpadController(numpadController);
numpadController.setValueToNumpad(333.56);
formRun.run();
```

## <a name="additional-resources"></a>其他資源

- [設計生產現場執行介面](production-floor-execution-styles.md)
- [設計生產現場執行介面](production-floor-execution-tabs.md)
