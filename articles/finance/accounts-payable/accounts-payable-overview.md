---
title: 設定應付帳款概觀
description: 本主題介紹用於設定應付帳款的基本功能和可選功能頁面。 還介紹在開始設定應付帳款之前必須完成的設定步驟。
author: abruer
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable, DeliveryReason, DeliveryTerms, DestinationCode
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "24671"
- intro-internal
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4ed5664b5be11f013900d6411d4307692d5e8334
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2022
ms.locfileid: "8451635"
---
# <a name="configure-accounts-payable-overview"></a>設定應付帳款概觀

[!include [banner](../includes/banner.md)]

本文介紹用於設定應付帳款的基本功能和可選功能頁面。 還介紹在開始設定應付帳款之前必須完成的設定步驟。

## <a name="prerequisites-for-accounts-payable-setup"></a>應付帳款設定的先決條件

在您設定應付帳款之前，您必須完成下列步驟：

-   總帳中：
    -   如果您計劃使用付款日記帳，請設定付款日記帳。
    -   如果您計劃執行匯率調整，請在 **貨幣** 頁面設定貨幣代碼，在 **匯率類型** 頁面設定匯率類型，並在 **貨幣匯率** 頁面設定貨幣匯率。
-   在現金和銀行管理中，設定銀行帳戶以使用付款方式。

## <a name="setup-pages-for-accounts-payable"></a>應付帳款的設定頁面

使用以下頁面為每個法律實體設定應付帳款的基本功能。 這些頁面會按推薦的設定順序列出。 為了使設定過程更簡單，您可以從建立的第一批記錄建立範本。 在範本中，通常在許多欄位中輸入值，以反映組織希望為特定類型的廠商實施的功能。
1.  在 **付款條件** 頁面，定義您指派給銷售訂單、訂購單、客戶和廠商的付款條件並確定發票到期日。 如需相關資訊，請參閱[定義廠商付款費用](tasks/define-vendor-payment-fees.md)。
2.  在 **付款方式 - 廠商** 頁面，建立和維護有關組織如何向其廠商付款的資訊。
3.  在 **廠商群組** 頁面，建立和維護共用用於過帳、結算和付款、報告和預測之重要參數的廠商群組。
4.  在 **廠商過帳設定檔** 頁面，定義如何將廠商交易過帳到總帳。
5.  在 **應付帳款參數** 頁面，設定在未指定更具體設定時套用的預設設定、各種功能的參數以及應付帳款的各種編號規則。
6.  在 **表單設定** 頁面，定義與廠商相關的各種單據的格式，以及組織用來追蹤來自廠商的收據並輸入向廠商付款的原因。
7.  在 **廠商** 頁面，建立和維護廠商帳戶，以及組織向其申報銷售稅的稅務機關。

## <a name="optional-setup-pages-for-accounts-payable"></a>應付帳款的選擇性設定頁面
除了基本功能外，應付帳款還具有可設定的其他功能。

附加設定頁面按功能組織。

**原則**
-   在 **廠商發票原則** 頁面，設定廠商發票原則。

**發票比對**

-   在 **發票總計允差** 頁面，設定發票總計的允差。
-   在 **比對原則** 頁面，設定雙向和三向比對原則。
-   在 **價格允差** 頁面，設定單價的允差。
-   在 **品項價格允差群組** 頁面，設定品項價格的允差群組。
-   在 **廠商價格允差群組** 頁面，設定廠商價格的允差群組。
-   在 **費用允差** 頁面，設定費用的允差。

**工作流程**

-   在 **應付帳款工作流程** 頁面，設定日記帳核准和採購申請的工作流程設定。

**原因**

-   在 **廠商原因** 頁面，設定原因代碼。

**費用**

-   在 **費用代碼** 頁面，為訂購單中使用的費用設定代碼。
-   在 **廠商費用群組** 頁面，為廠商建立和維護費用群組。
-   在 **品項費用群組** 頁面，為品項建立和維護費用群組。
-   在 **自動費用** 頁面，定義自動分配給訂單的費用。

**補充品項**

-   在 **補充品項群組 - 廠商** 頁面，為廠商建立和維護補充品項群組。
-   在 **補充品項群組 - 庫存** 頁面，為品項建立和維護補充品項群組。

**分配**

-   在 **交貨條款** 頁面，建立和維護品項從賣方轉移到買方的條件。
-   在 **交貨方式** 頁面，建立和維護訂單從賣方交付給買方時使用的運輸方式。
-   在 **目的地代碼** 頁面，建立和維護交貨目的地的識別碼和描述。

**表單**

-   在 **表格附註** 頁面，建立出現在各個頁面上的標准文字。
-   在 **表單排序參數** 頁面，設定請購單、收貨清單、裝箱單和發票的排序順序。
-   在 **列印管理設定** 頁面，設定原件和複本的列印管理資訊。

**付款**

-   在 **現金折扣** 頁面，設定和管理取得現金折扣的條款。 現金折扣代碼鏈接到廠商並套用至訂購單。
-   在 **付款排程** 頁面，設定用於管理向廠商分期付款的付款計劃。
-   在 **付款天數** 頁面，定義用於計算到期日的付款天數，並指定一週或一個月中特定日期的付款天數。
-   在 **支付費用** 頁面，建立和維護與廠商相關的付款費用。
-   在 **付款說明** 頁面，建立和維護付款說明。

**統計資料**

-   在 **帳齡期間定義** 頁面，設定使用者定義的間隔，用於分析廠商帳戶的到期分配。
-   在 **企業營運** 頁面，建立分配給廠商的企業營運 (LOB) 代碼。

**1099 稅**

-   在 **1099 欄位** 頁面，根據最新的 IRS 要求，驗證並更新必須向美國國稅局 (IRS) 申報的最低金額。

## <a name="optional-setup-for-other-modules"></a>**其他模組的選擇性設定**
**組織管理**

-   在 **編號規則** 頁面，為發票編號設定編號規則群組。
-   在以下頁面上，設定地址資訊：
    -   **地址設定**
    -   **NAF 代碼**
    -   **匯入郵遞區號**

**總帳**

-   在 **財務維度** 頁面，設定財務維度。
-   在以下頁面上，設定稅務資訊：
    -   **銷售稅代碼**
    -   **銷售稅群組**
    -   **品項銷售稅群組**
    -   **帳戶群組**
    -   **銷售稅免稅代碼**
    -   **銷售稅區域**
    -   **銷售稅主管機構**
    -   **銷售稅結算期間**

**現金和銀行管理**

-   在 **付款目的代碼** 頁面，設定 **中央銀行目的代碼**。



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
