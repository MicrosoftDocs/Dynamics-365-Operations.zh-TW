---
title: 設計生產現場執行介面
description: 本主題說明如何為每個設定設計使用者介面的內容。
author: johanhoffmann
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration, JmgProductionFloorExecutionConfigurationTab
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: ee206ced76dbdd356c77d34a4b8f197879e9a3f0
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2022
ms.locfileid: "8450099"
---
# <a name="design-the-production-floor-execution-interface"></a>設計生產現場執行介面

[!include [banner](../includes/banner.md)]

您可以為生產現場執行介面使用的每項設定設計使用者介面的內容。  例如，一個工作單元中的工作人員可能需要能在生產現場開啟工作說明，但另一個工作單元中的工作人員不需要說明。 在這種情況下，應建立兩種設定，一種設有開啟文件附件的按鈕，另一種沒有此按鈕。

## <a name="design-a-tab"></a>設計索引標籤

在 **設定現場執行** 頁面，選取操作窗格上的 **設計索引標籤** 即可建立和設定索引標籤。

每個索引標籤分成四個部分，如下圖所示。

![索引標籤配置。](media/pfe-tab-layout.png "索引標籤配置")

插圖中顯示下列元素：

1. 主工具列
1. 次要工具列
1. 主要檢視
1. 詳細資料檢視

若要建立和設計新索引標籤，請執行以下步驟：

1. 前往 **產品控制 \> 設定 \> 製造執行 \>  設定生產現場執行**。

1. 選取在動作窗格上的 **設計索引標籤** 以開啟 **設計索引標籤** 頁面。

    ![設計索引標籤頁面。](media/pfe-design-tabs.png "設計標籤配置頁面")

1. 在動作窗格上，選擇 **新增**。

1. 在頁面標題中進行以下設定：

    - **索引標籤名稱** – 指定索引標籤的名稱。
    - **主要檢視** – 在預先定義的作業清單中選擇 (*使用中作業*、*所有作業*、*我的作業*，和 *我的機器*)。
    - **詳細資料檢視** – 選取空白值或 **作業詳細資料**。 如果選擇空白值，索引標籤中將沒有詳細資料檢視。如果您選擇 **工作詳細資料**，詳細檢視會包含在主檢視作業清單中選擇的作業的詳細說明。

1. 在 **主要工具列** 部分，選擇主工具列中應該可用的按鈕。 **可用動作** 欄列出可以新增的所有按鈕。 **與所選的動作** 欄列出目前定中包含的所有按鈕。 您可以視需要使用欄之間的按鈕，在欄之間移動所選項目。 使用 **所選的動作** 欄旁邊的向上和向下按鈕，來控制按鈕在使用者介面中的顯示順序。

1. 在 **次要工具列** 部分，選擇要在次要工具列中提供的按鈕。 **可用動作** 欄列出可以新增的所有按鈕。 **與所選的動作** 欄列出目前定中包含的所有按鈕。 您可以視需要使用欄之間的按鈕，在欄之間移動所選項目。 使用 **所選的動作** 欄旁邊的向上和向下按鈕，來控制按鈕在使用者介面中的顯示順序。

## <a name="associate-a-tab-with-a-configuration"></a>將索引標籤與設定建立關聯

設計完所有需要的索引標籤後，您可以將索引標籤與設定建立關聯。

1. 前往 **產品控制 \> 設定 \> 製造執行 \>  設定生產現場執行**。

    ![設定生產現場執行。](media/pfe-config-prod-floor-execution.png "設定生產現場執行介面")

1. 選取 **索引標籤選擇** FastTab 上的 **新增**。

1. 系統會新增一個列到網格中。 針對這個新列，選擇要新增到設定中的索引標籤名稱。

1. 視需要繼續新增其他索引標籤。

1. 根據需求使用工具欄上的 **上移** 和 **下移** 按鈕來排列索引標籤。 索引標籤會按照上面螢幕擷取畫面中顯示的順序從左到右顯示 (頂部的索引標籤顯示在左側)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
