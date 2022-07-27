---
title: 使用 Regression Suite Automation Tool 進行與資料無關的測試
description: 本主題討論使用 Regression Suite Automation Tool 進行與資料無關測試的建議。
author: kfend
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2019-09-11
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: d9a5bce1cc56dfdf66b2ce58c2e740b7c4b3bdfc7f4e75396fe5dc7cb931b6d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460518"
---
# <a name="data-agnostic-testing-using-the-regression-suite-automation-tool"></a>使用 Regression Suite Automation Tool 進行與資料無關的測試

[!include [banner](../includes/banner.md)]

雖然 ERP 應用程式的函數驗證不能完全與資料無關，但有多個測試階段和方法。 這些測試階段包括：  

- 系統測試架構
- ATL 架構
- Regression Suite Automation Tool (RSAT)

[![測試分類金字塔。](./media/rsat-data-agnostic-testing-01.PNG)](./media/rsat-data-agnostic-testing-01.PNG)

## <a name="overview"></a>概觀
-   **系統測試架構**– 系統測試架構對於編寫單元測試是可靠的。 因為單元測試通常是測試方法或函數，所以它們應該始終與資料無關，並且只依賴於作為測試一部分提供的輸入資料。
-   **ATL 架構**– Microsoft 有一個 ATL 架構，它是系統測試架構的抽象，使函數測試編寫更加簡單和可靠。 這個架構應該用於編寫組件測試或簡單的整合測試。
-   **RSAT**– RSAT 用於整合測試和商業週期測試。 商業週期測試，也稱為回歸驗證測試，依賴於現有資料。 但是，如果您考慮其他因素，這些測試可能會變得與資料無關。 

    - o 單元測試和組件測試是低級別的並且可以完全與資料無關 (不依賴於現有資料集)，商業週期或回歸驗證測試依賴於一些現有資料。 此資料包括設定、設定設定 (參數) 和主資料 (客戶、廠商、項目等)，但不包括交易資料。 確保在測試期間，如果其中任何一項被更改，它們將作為最終測試的一部分恢復。
    - 根據特定標準選取主資料，而不是選取特定記錄。 例如，如果您想根據其維度值和庫存可用性選取一個項目，請使用這些值篩選產品清單，選取第一個項目，然後復制要用於未來測試的編號。 如果它是一個簡單的主資料行，例如客戶、廠商或項目，則可以將其建立為自動化的一部分，並透過連結在未來的測試中使用。 
    - o 透過編號規則或使用 Microsoft Excel 函數，例如 = TEXT(NOW(),"yyyymmddhhmm")，輸入唯一識別碼，例如發票編號。 此函數將每分鐘提供一個唯一編號，以便您追蹤動作發生的時間。 這可用於產品收據編號和廠商發票編號等變數。 這些測試一次又一次地在同一個資料庫上工作，不需要任何恢復。
    - 始終將環境的 **編輯模式** 設定為 **讀取** 或 **編輯** 作為第一個測試案例，因為預設選項是 **自動**。**自動** 選項始終使用以前的設定，可能會導致不可靠的測試。 
 
    [![選項頁面，效能索引標籤。](./media/rsat-data-agnostic-testing-02.PNG)](./media/rsat-data-agnostic-testing-02.PNG)
 
    - 僅在篩選特定交易而不是通用驗證後進行驗證。 例如，對於記錄數，篩選交易編號或交易日期，以便驗證排除所有其他交易。 
    - 如果您正在檢查客戶餘額或預算檢查，請先儲存該值，然後新增您的交易值以驗證預期結果，而不是驗證固定的預期值。 
 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]