---
title: 根據登記支付薪資
description: 本主題說明如何根據員工登記計算工資。
author: johanhoffmann
ms.date: 03/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgCalcApproveWeekView, JmgProdStatusListPagePayrollCostDetails, JmgPayCountTable, JmgPayStatConfig, JmgOvertimeSlize, JmgPayAgreementOverride, JmgPayCountSum, JmgPayAdjustSetup, JmgPayAdjustCostType, JmgPayEmployee, JmgMESBreak, JmgPayAddTable, JmgPayAddTransSelectTransId, JmgPayrollCostDetailsPart, jmgProdStatusListPagePayrollCosts, JmgPayrollCostPart, JmgPayEvents, JmgTermRegPayStatSetup, JmgPayStatGroup, JmgPayAddTrans, JmgPayStatTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-03-20
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 58ff2629c2894e85ca5529df5f995ffa5273de67e1c22564f5f9911ea86fbd95
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446652"
---
# <a name="pay-based-on-registrations"></a>根據登記支付薪資

[!include [banner](../includes/banner.md)]

本主題詳細說明如何根據員工登記計算工資。 其中的範例顯示可用於計算的各種設定選項組合如何影響結果。 以下是一些涉及的範圍：

- 彈性時間
- 加班時間
- 休息時間
- 切換代碼
- 薪資項目
- 薪資合約
- 時間及出勤計算參數
- 缺勤

## <a name="the-use-of-flex-time"></a>彈性時間的使用

彈性時間時段是在時間及考勤中使用的時間設定檔中設定的。 有兩種彈性設定檔類型：**彈性+** 和 **彈性-**。 當員工在 [彈性+] 期間登記間時，員工的彈性餘額會隨工作時數增加。 員工在 [彈性+] 期間工作的時數不會得到任何薪資。 但是，員可以在 [彈性-] 期間請假，並從彈性餘額中的時數獲得薪資。 因此，系統會將彈性時段的休假視為缺勤。

## <a name="scenarios-based-on-flex-periods"></a>以彈性時段為基礎的案例

以下的兩個案例以代表工作日的彈性設定檔為基礎。 對於這兩種案例，薪資都是根據員工打卡上班和打卡下班的彈性時段計算的。

### <a name="flex-profile-for-one-workday"></a>一個工作日的彈性設定檔

| 設定檔類型  | 開始    | 結束      | 天     |
|---------------|----------|----------|---------|
| 加班時間     | 00:00 AM | 06:00 AM | 星期一  |
| 彈性+         | 06:00 AM | 07:00 AM | 星期一  |
| 打卡上班      | 07:00 AM | 07:00 AM | 星期一  |
| 標準時間 | 07:00 AM | 02:30 PM | 星期一  |
| 彈性-         | 02:30 PM | 03:30 PM | 星期一  |
| 打卡下班     | 03:30 PM | 03:30 PM | 星期一  |
| 加班時間     | 03:30 PM | 06:00 AM | 星期二 |

### <a name="scenario-1-a-worker-registers-clock-in-during-a-flex-period-and-clock-out-during-a-flex--period"></a>案例 1：員工在 [彈性+] 時段登記打卡下班，在 [彈性-] 時段登記打卡下班

員工在當天的登記如下所示。

| 日記帳登記類型 | 開始    | 結束      |
|---------------------------|----------|----------|
| 打卡上班                  | 06:30 AM | 06:30 AM |
| 生產作業            | 06:30 AM | 02:45 PM |
| 打卡下班                 | 02:45 PM | 02:45 PM |

系統會計算並轉移員工當天的登記，以供在 **核准** 頁面 (**時間及出勤**&gt;**審查與核准**&gt;**核准**) 上支付。 將登記資料計算完成後，便可以在 **時間** 索引標籤上檢視計算結果。 

若要瞭解此案例，請查看以下欄位。

| 彈性+ | 彈性- | 時間 | 薪資時間 |
|--------|--------|------|----------|
| 0.50   | 0.75   | 8.25 | 8.50     |

#### <a name="calculation-of-flex"></a>彈性+ 的計算

根據彈性設定檔，06:00 AM 和 07:00 AM 之間的時間是 [彈性+] 時段。 因此，如果員工在 06:30 AM 打卡上班，他們將獲得 0.5 小時。 這段時間量會新增到員工的彈性帳戶中。

#### <a name="calculation-of-flex-"></a>彈性- 的計算

根據彈性設定檔，[彈性-] 時段從 02:30 PM 開始，到 03:30 PM 結束。 因此，如果員工在 02:45 PM 打卡下班，則 [彈性-] 時段中剩餘的 45 分鐘 (0.75 小時) 將登記為薪資時間，並且會從員工的彈性帳戶中扣除相同的時間量。 這 45 分鐘會包含在薪資時間內，因為員工將獲得 [彈性-] 時段中剩餘 45 分鐘的薪資。 如果員工在 [彈性-] 時段期間缺勤，這 45 分鐘將從他的彈性帳戶中扣除。

#### <a name="calculation-of-time"></a>時間的計算

[時間] 是計算打卡上班和打卡下班之間而得的時間，即 06:30 AM 到 14:45 PM，等於 8.25 小時。

#### <a name="calculation-of-pay-time"></a>薪資時間的計算

[薪資時間] 是指員工獲得薪酬的期間。 在此案例中，員工工作 8.25 小時 (**時間**)。 然而，系統計算出的 **薪資時間** 為 8.50 小時，因為員工在打卡下班後於 [彈性-] 時段期間獲得薪酬。薪資時間等於規劃的工作時數，因為 [彈性+] 時間會新增到員工的彈性帳戶，而不是薪資時間。 [彈性-] 時段期間的缺勤時間會由薪資時間補償，並從員工的彈性帳戶中扣除。

| 時間              | 登記類型 | 薪資時間 (時數)      |
|-------------------|-------------------|-----------------------|
| 6:30 AM - 7:00 AM | 彈性+             | 0                     |
| 7:00 AM – 2:45 PM | 標準時間     | 7.75                  |
| 2:45 PM – 3:30 PM | 彈性-             | 0.75 (缺勤時段) |
|                   | 總計             | 8.50                  |

### <a name="scenario-2-a-worker-works-during-the-whole-flex--period-and-also-works-overtime"></a>案例 2：員工在整個 [彈性+] 時段期間工作，同時也加班

員工在當天的登記如下所示。

| 日記帳登記類型 | 開始    | 結束      |
|---------------------------|----------|----------|
| 打卡上班                  | 06:30 AM | 06:30 AM |
| 生產作業            | 06:30 AM | 05:00 PM |
| 打卡下班                 | 05:00 PM | 05:00 PM |

在 **核准** 頁面上計算日記帳登記後，可以在 **時間** 索引標籤檢視計算結果。若要瞭解此案例，請查看以下欄位。

| 彈性+ | 彈性- | 時間  | 薪資時間 | 加班薪資時間 |
|--------|--------|-------|----------|--------------|
| 0.50   | 0.00   | 10.50 | 10.00    | 1.50         |

#### <a name="calculation-of-flex"></a>彈性+ 的計算

根據彈性設定檔，06:00 AM 和 07:00 AM 之間的時間是 [彈性+] 時段。 因此，如果員工在 06:30 AM 打卡上班，他們的彈性餘額將獲得 0.5 小時的 [彈性+] 時間。

#### <a name="calculation-of-flex-"></a>彈性- 的計算

因為員工在 [彈性-] 時段期間工作，所以不會計算 [彈性-]。 如果員工在 [彈性-] 時段期間缺勤，則只會計算 [彈性-]。 從薪資的角度來看，如果員工在 [彈性-] 時段期間工作，則他們將獲得針對標準時間定義的薪資率。 如果員工在 [彈性-] 時段期間缺勤，這 45 分鐘會從其彈性帳戶中扣除。

#### <a name="calculation-of-time"></a>時間的計算

[時間] 是計算打卡上班時間 06:30 AM 到打卡下班時間 05:00 PM 之間而得的時間，亦即 10.50 小時。

#### <a name="calculation-of-pay-time"></a>薪資時間的計算

在此案例中，員工工作 10.50 小時 (**時間**)。 然而，**薪資時間** 計算為 10.00 小時，因為員工在 [彈性+] 期間沒有獲得薪資。

#### <a name="calculation-of-pay-overtime"></a>加班薪資時間的計算

| 時間               | 登記類型 | 薪資時間 (時數) |
|--------------------|-------------------|------------------|
| 6:30 AM - 7:00 AM  | 彈性+             | 0                |
| 7:00 AM – 2:30 PM  | 標準時間     | 7.50             |
| 2:30 PM – 3:30 PM  | 彈性-             | 1.00             |
| 3:30 PM – 05:00 PM | 加班時間          | 1.50             |
|                    | 總計             | 10.00            |

### <a name="generation-of-pay-items"></a>產生薪資項目

會從 **核准** 頁面轉移員工在當天的登記。 在轉移過程中，會產生薪資項目與轉移的登記。 薪資項目代表將薪資時間細分為標準時間、加班時間、有薪酬休息時間等。

若要開啟薪資項目清單，請選取 **時間及出勤**&gt;**審查與核准**&gt;**核准**。 然後選取 **詢問**&gt;**轉移的登記**。

薪資項目是員工薪資的基礎。 您可以產生一個包含薪資項目資訊的檔案，並將該檔案轉移到薪資系統。

在轉移的過程中，來自生產和專案活動的時間和成本會轉移到生產和專案日記帳，以說明所花費的時間和成本。 轉移的登記是生產訂單和專案每小時的時間和成本價格的基礎。 您可以使用 **核准** 頁面上的 **查詢** 功能表開啟轉移的登記。

例如，對於案例 2，會產生以下的薪資項目。

| 工資類型     | 薪資類型 | 薪資單位 | 費率  | 總成本 |
|---------------|----------|-----------|-------|------------|
| 標準時間 | 1201     | 10.0      | 10    | 100        |
| 加班時間      | 1301     | 1.50      | 5     | 7.50       |
|               |          |           | 總計 | 107.50     |

標準時間薪資項目的薪資單位為 10 小時，包括標準時間、[彈性-] 時間和加班時間。 標準時間、[彈性-] 時間和加班時間合併為一個薪資項目，因為所有類型均根據 **計算參數** 頁面 (**時間及出勤**&gt;**設定**&gt;**計算參數**) 的預設參數設定計算成為標準時間。 加班時間是使用附加費率 5 以標準時間為基礎計算而得的。

如果您想要明確區分標準時間和加班時間，使薪資類型的薪資單位僅涵蓋花費在標準時間和加班時間上的實際時間，則標準時間的薪資單位必須計算為 8.50，加班時間的薪資單位必須計算為 1.50。

若要設定系統以明確區分標準時間和加班時間，您必須將加班時間從標準時間中排除。 您還必須變更加班時間的薪資類型設定，以便加班時間薪資率涵蓋加班時間時數的所有薪資。

### <a name="exclude-overtime-from-the-standard-time"></a>從標準時間中排除加班時間

在 **計算參數** 頁面上，選取 **加班時間** 作為設定檔規格類型，並將 **薪資時間** 選項設定為 **否**，如此處所示。

| 登記規格 | 設定檔規格類型 | 計算   | 設定 | 已付款         | 設定 |
|--------------------|----------------------------|---------------|-----|--------------|-----|
| 工作時間       | 加班時間                   | 標準時間 | 是 | 薪資時間     | 否  |
|                    |                            | 薪資時間      | 是 | 加班薪資時間 | 是 |

調整計算參數後，會產生以下薪資項目。

| 工資類型     | 薪資類型 | 薪資單位 | 費率  | 總成本 |
|---------------|----------|-----------|-------|------------|
| 標準時間 | 1201     | 8.50      | 10    | 85.0       |
| 加班時間      | 1301     | 1.50      | 15    | 22.50      |
|               |          |           | 總計 | 107.50     |

> [!NOTE]
> 計算參數具有推薦的標準設定。 一般而言，變更這些參數時應該小心。 若要還原推薦的標準設定，請在 **計算參數** 頁面上選取 **還原值**。

### <a name="allow-a-deviation-from-the-standard-pay-profiles"></a>允許偏離標準薪資設定檔

在 **設定檔** 頁面 (**時間及出勤**&gt;**設定**&gt;**時間設定檔**&gt;**設定檔**)，您可以設定包含切換代碼和休息的設定檔類型。

### <a name="switch-codes"></a>切換代碼

您可以使用切換代碼來允許員工透過變更不同的設定檔類型來偏離其設定檔類型。 例如，您可以允許員工從 [彈性+] 時間變更為加班時間。 員工在登記期間可以新增切換代碼，您也可以將新增切換代碼的工作指派給登記的核准者。

您必須先將切換代碼定義為一種間接活動，才能使用切換代碼。 然後，您必須將切換代碼新增到您希望允許變更設定檔類型的時段其時間設定檔。 例如，按照以下步驟建立一個切換代碼，允許將 [彈性+] 時段從 06:00 AM 到 07:00 AM 變更為加班時間。

1. 建立一個名為 **OTBCI (在打卡上班前將彈性時間轉換為加班時間)** 的切換代碼。 選取 **時間及出勤**&gt;**管理間接活動**&gt;**間接活動**。
2. 在 **切換代碼** 欄中，將 OTBCI 新增到時間設定檔中的 [彈性+] 明細。
3. 在 **次要** 欄中，新增 **加班時間** 設定檔類型。

考慮以下代表工作日的彈性設定檔。

| 設定檔類型  | 開始    | 結束      | 天     |
|---------------|----------|----------|---------|
| 加班時間     | 00:00 AM | 06:00 AM | 星期一  |
| 彈性+         | 06:00 AM | 07:00 AM | 星期一  |
| 打卡上班      | 07:00 AM | 07:00 AM | 星期一  |
| 標準時間 | 07:00 AM | 02:30 PM | 星期一  |
| 彈性-         | 02:30 PM | 03:30 PM | 星期一  |
| 打卡下班     | 03:30 PM | 03:30 PM | 星期一  |
| 加班時間     | 03:30 PM | 06:00 AM | 星期二 |

以下是員工在當天的登記。

| 日記帳登記類型 | 開始    | 結束      |
|---------------------------|----------|----------|
| 打卡上班                  | 06:30 AM | 06:30 AM |
| 生產作業            | 06:30 AM | 02:45 PM |
| 打卡下班                 | 05:00 PM | 05:00 PM |

轉移後會產生以下薪資項目。

| 工資類型     | 薪資類型 | 薪資單位 | 費率  | 總成本 |
|---------------|----------|-----------|-------|------------|
| 標準時間 | 1201     | 8.50      | 10    | 85.0       |
| 加班時間      | 1305     | 1.50      | 15    | 22.50      |
|               |          |           | 總計 | 107.50     |

在 **核准** 頁面上復原轉移，然後使用 **切換代碼** 功能表套用 **OTBCI** 切換代碼。 當您第二次轉移登記時，會產生以下薪資項目。

| 工資類型     | 薪資類型 | 薪資單位 | 費率  | 總成本 |
|---------------|----------|-----------|-------|------------|
| 標準時間 | 1201     | 8.50      | 10    | 80.0       |
| 加班時間      | 1305     | 2.00      | 15    | 30.0       |
|               |          |           | 總計 | 107.50     |

> [!NOTE]
> 套用切換代碼後，加班時間會增加 0.5 小時，從 1.50 增加到 2.00。 0.5 小時是將所登記的 [彈性+] 時間從 6:30 AM 到 07:00 AM 轉換成加班時間。

### <a name="breaks"></a>休息時間

休息時間會影響員工薪資的計算。 休息時間定義為一種間接活動。 休息時間可定義為 **有薪酬**，以允許將休息時間新增至員工的薪資，也可以定義 **無薪酬**，以防止將休息時間新增至員工的薪資。 休息時間也可以定義成 **已規劃** 或 **已登記**。

#### <a name="planned-breaks"></a>已規劃休息時間

如果公司有固定的休息時間，例如固定的午餐休息時間，則可以在時間設定檔中預先定義休息時間。 在這種情況下，員工不必在作業卡頁面上登記休息時間。 相反的，在 **核准** 頁面上計算員工的登記時，會自動計算休息時間。

#### <a name="registered-breaks"></a>已登記休息時間

如果公司不使用已規劃休息時間，則員工可以在工作日期間登記休息時間。 例如，如果員工正在使用沒有定義打卡上班和打卡下班時間的彈性時間設定檔工作，則可以使用已登記休息時間。 已登記休息時間是一種間接活動。 員工在 **作業卡** 終端頁面或 **作業卡** 裝置頁面上登記休息時間。 在這兩個頁面上，使用者都可以在預先定義的休息時間活動清單中選擇休息時間類型。

#### <a name="paid-and-unpaid-breaks"></a>有薪酬和無薪酬休息

休息時間活動可以設定為 **有薪酬** 或 **無薪酬**。 有薪酬休息時間包括在薪資時間的計算中，系統將薪資合約中定義的薪資類型用於 **休息時間** 登記類型。

### <a name="example-of-a-planned-break"></a>已規劃休息時間範例

思考一下以下的時間設定檔，此設定檔包含無薪酬的午餐休息時間。

| 設定檔類型  | 開始    | 結束      | 天     |
|---------------|----------|----------|---------|
| 加班時間     | 00:00 AM | 06:00 AM | 星期一  |
| 彈性+         | 06:00 AM | 07:00 AM | 星期一  |
| 打卡上班      | 07:00 AM | 07:00 AM | 星期一  |
| 標準時間 | 07:00 AM | 12:00 PM | 星期一  |
| 中斷         | 12:00 PM | 12:30 PM | 星期一  |
| 標準時間 | 12:30 PM | 02:30 PM | 星期一  |
| 彈性-         | 02:30 PM | 03:30 PM | 星期一  |
| 打卡下班     | 03:30 PM | 03:30 PM | 星期一  |
| 加班時間     | 03:30 PM | 06:00 AM | 星期二 |

以下是員工在當天的登記。

| 日記帳登記類型 | 開始    | 結束      |
|---------------------------|----------|----------|
| 打卡上班                  | 06:30 AM | 06:30 AM |
| 生產作業            | 06:30 AM | 02:45 PM |
| 打卡下班                 | 05:00 PM | 05:00 PM |

在 **核准** 頁面上計算日記帳登記後，可以在 **時間** 索引標籤檢視計算結果。若要瞭解此案例，請查看以下欄位。

| 彈性+ | 彈性- | 時間  | 薪資時間 | 無薪酬休息時間 | 加班薪資時間 |
|--------|--------|-------|----------|---------------------|--------------|
| 0.50   | 0.00   | 10.50 | 9.50     | 0.5                 | 1.50         |

> [!NOTE] 
> 系統計算出 0.5 小時的無薪酬休息時間，且該時間不屬於薪資時間。

### <a name="example-of-a-registered-break"></a>已登記休息時間範例

思考一下以下的時間設定檔，此設定檔不包含已規劃休息時間。

| 設定檔類型  | 開始    | 結束      | 天     |
|---------------|----------|----------|---------|
| 加班時間     | 00:00 AM | 06:00 AM | 星期一  |
| 彈性+         | 06:00 AM | 07:00 AM | 星期一  |
| 打卡上班      | 07:00 AM | 07:00 AM | 星期一  |
| 標準時間 | 07:00 AM | 02:30 PM | 星期一  |
| 彈性-         | 02:30 PM | 03:30 PM | 星期一  |
| 打卡下班     | 03:30 PM | 03:30 PM | 星期一  |
| 加班時間     | 03:30 PM | 06:00 AM | 星期二 |

以下是員工在當天的登記。

| 日記帳登記類型 | 開始    | 結束      |
|---------------------------|----------|----------|
| 打卡上班                  | 06:30 AM | 06:30 AM |
| 生產作業            | 06:30 AM | 05:00 PM |
| 中斷                     | 12:03 PM | 12:32 PM |
| 打卡下班                 | 05:00 PM | 05:00 PM |

當計算登記時，會計算活動的時間。

| 日記帳登記類型 | 開始    | 結束      | 時間  |
|---------------------------|----------|----------|-------|
| 打卡上班                  | 06:30 AM | 06:30 AM |       |
| 生產作業            | 06:30 AM | 05:00 PM | 10.00 |
| 中斷                     | 12:03 PM | 12:32 PM | 0.50  |
| 打卡下班                 | 05:00 PM | 05:00 PM |       |

> [!NOTE]
> 休息時間與活動時間 (在本範例中為生產作業) 並行執行。 此行為一律用於休息活動。 計算登記時，會從活動時間中減去休息時間。 在這種狀況中，生產作業的持續時間為 10.50 小時，但計算出的時間為 10，因為從活動時間中減去了 0.5 小時的休息時間。

在 **核准** 頁面上計算日記帳登記後，可以在 **時間** 索引標籤檢視計算結果。若要瞭解此案例，請查看以下欄位。

| 彈性+ | 彈性- | 時間  | 薪資時間 | 無薪酬休息時間 | 加班薪資時間 |
|--------|--------|-------|----------|---------------------|--------------|
| 0.50   | 0.00   | 10.50 | 9.50     | 0.5                 | 1.50         |

如果已規劃休息時間為有薪酬，而不是無薪酬，則計算結果如下所示。

| 彈性+ | 彈性- | 時間  | 薪資時間 | 有薪酬休息時間 | 加班薪資時間 |
|--------|--------|-------|----------|-----------------|--------------|
| 0.50   | 0.00   | 10.50 | 10.00    | 0.5             | 1.50         |

### <a name="pay-items-and-paid-breaks"></a>薪資項目與有薪酬休息時間

當您在 **核准** 頁面中轉移登記時，會產生薪資項目。 系統會為有薪酬休息時間產生單獨的薪資項目。

有薪酬休息時間的薪資率是由休息時間薪資合約中設定的薪資類型決定的。 您可以在定義的日期間隔內設定休息時間的每小時成本價，而不是使用薪資類型。

思考一下以下時間設定檔。

| 設定檔類型  | 開始    | 結束      | 天     |
|---------------|----------|----------|---------|
| 加班時間     | 00:00 AM | 06:00 AM | 星期一  |
| 彈性+         | 06:00 AM | 07:00 AM | 星期一  |
| 打卡上班      | 07:00 AM | 07:00 AM | 星期一  |
| 標準時間 | 07:00 AM | 02:30 PM | 星期一  |
| 彈性-         | 02:30 PM | 03:30 PM | 星期一  |
| 打卡下班     | 03:30 PM | 03:30 PM | 星期一  |
| 加班時間     | 03:30 PM | 06:00 AM | 星期二 |

以下是員工在當天的登記。

| 日記帳登記類型 | 開始    | 結束      | 時間 |
|---------------------------|----------|----------|------|
| 打卡上班                  | 07:00 AM | 07:00 AM |      |
| 生產作業            | 07:00 AM | 03:00 PM | 7.5  |
| 休息時間 (有薪酬)              | 12:00 PM | 12:30 PM | 0.5  |
| 打卡下班                 | 03:00 PM | 03:00 PM |      |

在此範例中，標準時間的薪資類型設定為 **1201**，薪資率 **10** 是在薪資合約中設定的。 有薪酬休息時間的薪資類型為 **1301**，薪資率為 **8**。 當您轉移登記時，會產生以下薪資項目。

| 工資類型     | 薪資類型 | 薪資單位 | 費率 |
|---------------|----------|-----------|------|
| 標準時間 | 1201     | 7.50      | 10   |
| 彈性-         | 1201     | 0.50      | 10   |
| 休息時間 (有薪酬)  | 1301     | 0.50      | 8    |

## <a name="how-the-cost-of-paid-breaks-is-allocated-to-projects-and-production-orders"></a>如何將有薪酬休息時間的成本分配給專案和生產訂單

可以設定專案活動和生產作業的每小時成本，以便由 [時間及出勤] 中計算的薪資率或由為活動定義的成本類別來決定每小時成本。

若要設定成本類別，請選取 **生產控制**&gt;**設定**&gt;**製造執行**&gt;**生產訂單預設值**，並將 **成本類別** 欄位設定為 **是** 或 **否**。

- **否** – 根據為 [時間及出勤] 登記類型定義的薪資率計算成本。
- **是** – 根據生產和專案活動的成本類別計算成本。

### <a name="cost-calculation-based-on-pay-rates-that-are-calculated-in-time-and-attendance"></a>根據 [時間及出勤] 中計算的薪資率計算成本

以下範例顯示在設定成本時如何計算每小時成本，以根據薪資率進行計算。

用於生產訂單和專案的每小時成本費率是在轉移過程中計算的。 若要檢視各活動每小時費率，請開啟 [時間及出勤] 頁面中的 **核准** 頁面，然後選取 **詢問**&gt;**已轉移登記**。 您可以在 **成本價格** 索引標籤上找到各登記的每小時成本費率。

請思考以下登記，這些登記使用與上一個範例相同的時間設定檔。

| 日記帳登記類型 | 開始    | 結束      | 時間 |
|---------------------------|----------|----------|------|
| 打卡上班                  | 07:00 AM | 07:00 AM |      |
| 流程 (訂單：4711)     | 07:00 AM | 11:00 AM | 4    |
| 流程 (訂單：4712)     | 11:00 AM | 03:00 PM | 3.50 |
| 休息時間 (有薪酬)              | 12:00 PM | 12:30 PM | 0.50 |
| 打卡下班                 | 03:00 PM | 03:00 PM |      |

在轉移登記後，會產生以下的已轉移登記。

| 登記類型     | 時間 | 每小時成本價 |
|-----------------------|------|---------------------|
| 打卡上班              | 0.00 | 0.00                |
| 流程 (訂單：4711) | 4.00 | 10.00               |
| 流程 (訂單：4712) | 3.50 | 11.14               |
| 休息時間 (有薪酬)          | 0.50 | 0.00                |
| 打卡下班             | 0.00 | 0.00                |

帶薪酬休息時間其每小時成本價格的計算取決於直接薪資表成本的設定。 選取 **時間及出勤**&gt;**設定**&gt;**時間及出勤參數**。 在 **成本價格** 索引標籤上，在 **直接薪資表成本** 下的 **標準時間** 欄位中，您可以選取 **是**、**否** 或 **配置**。

- **是** – 該值用於前面的範例。 成本會配置到與有薪酬休息活動並行執行的生產或專案活動。 在範例中，此活動是訂單 4712 的生產作業。 如您所見，帶薪酬休息時間的每小時成本價格為 0 (零)，並且會配置給與休息時間並行執行的作業。

    有薪酬休息時間為 0.5 小時，薪資率為 8。 因此，有薪酬休息時間的總成本為 4。 然後將總成本配置給 3.5 小時的流程作業。 因此，有薪酬休息時間每小時會產生 1.14 的成本 (4 ÷ 3.5 = 1.14)。

- **配置** – 有薪酬休假時間平均分配給當天登記的作業。 如果此值用於前面的範例，則會產生以下的已轉移登記。

    | 登記類型     | 時間 | 每小時成本價 |
    |-----------------------|------|---------------------|
    | 打卡上班              | 0.00 | 0.00                |
    | 流程 (訂單：4711) | 4.00 | 10.53               |
    | 流程 (訂單：4712) | 3.50 | 10.53               |
    | 休息時間 (有薪酬)          | 0.50 | 0.00                |
    | 打卡下班             | 0.00 | 0.00                |

    兩個生產作業的總處理時間為 7.5 小時，有薪酬休息時間的總成本為 4。 因此，休息時間的成本計算結果為 0.53 (= 4 ÷ 7.5)。

- **否** – 有薪酬休息時間的成本不會增加流程活動的每小時成本。

    | 登記類型     | 時間 | 每小時成本價 |
    |-----------------------|------|---------------------|
    | 打卡上班              | 0.00 | 0.00                |
    | 流程 (訂單：4711) | 4.00 | 10.00               |
    | 流程 (訂單：4712) | 3.50 | 10.00               |
    | 休息時間 (有薪酬)          | 0.50 | 0.00                |
    | 打卡下班             | 0.00 | 0.00                |

## <a name="absence"></a>缺勤

缺勤代碼用於登記員工缺勤的時段。 與休息時間和切換代碼一樣，缺勤代碼是一種間接活動。 缺勤時間可以是已規劃或已登記，缺勤可以是正當或不正當的。 正當缺勤的例子包括醫師約診、研討會或履行陪審團義務。 不正當缺勤是指無正當理由的缺勤，例如員工上班遲到。 通常，正當缺勤不會導致扣除員工薪資，而不正當缺勤會導致扣除薪資。

### <a name="planned-absence"></a>已規劃缺勤

您可以在 **建立已規劃缺勤** 頁面 (**時間及出勤**&gt;**建立已規劃缺勤**) 上為員工建立已規劃缺勤。 在該頁面上，會將已規劃缺勤登記成指定日期和時間間隔的缺勤作業。

該作業以查詢為基礎。 因此，您可以為多個員工建立已規劃缺勤，例如屬於同一個計算群組的員工。 如果已規劃缺勤是針對單一員工，則可以從 **出勤** 頁面或 **時間登記員工** 頁面輸入登記。

- 若要從 **出勤** 頁面輸入缺勤登記，請選取 **時間及出勤**&gt;**查詢與報告**&gt;**出勤**&gt;**出勤**，然後選取 **缺勤登記**。
- 若要從 *<strong><em>時間登記員工</em></strong>* 頁面輸入缺勤登記，請選取<strong>時間及出勤</strong>&gt;<strong>設定</strong>&gt;<strong>時間登記員工</strong>，然後在<strong>時間</strong>索引標籤的<strong>時間指派</strong>下方，選取<strong>缺勤登記</strong>。

您可以使用 **已規劃缺勤** 報告查看員工的已規劃缺勤概觀。 若要開啟此報告，請選取 **時間及出勤**&gt;**查詢與報告**&gt;**缺勤報告**&gt;**已規劃缺勤**。

### <a name="registered-absence"></a>已登記缺勤

一般而言，如果員工在已規劃打卡上班時間和已規劃打卡下班時間之間的任何時段內沒有工作，則視為缺勤。 如果員工打卡上班時間晚於規劃的時間，或者打卡下班時間早於規劃的時間，系統會提示他們選擇缺勤代碼以指出缺勤原因。 可以設定缺勤代碼，使其適用於登記。 只有適用的代碼可供在清單中選擇。

## <a name="scenarios-based-on-various-combinations-of-work-hour-registrations"></a>以各種工時登記組合為基礎的方案

以下案例顯示根據員工的登記為員工產生的薪資項目和待核准項目。 所有案例均以下列時間設定檔為基礎。

| 設定檔類型  | 開始    | 結束      | 天     |
|---------------|----------|----------|---------|
| 加班時間     | 00:00 AM | 06:00 AM | 星期一  |
| 彈性+         | 06:00 AM | 07:00 AM | 星期一  |
| 打卡上班      | 07:00 AM | 07:00 AM | 星期一  |
| 標準時間 | 07:00 AM | 02:30 PM | 星期一  |
| 彈性-         | 02:30 PM | 03:30 PM | 星期一  |
| 打卡下班     | 03:30 PM | 03:30 PM | 星期一  |
| 加班時間     | 03:30 PM | 06:00 AM | 星期二 |

### <a name="scenario-1-the-worker-clocks-in-later-than-planned"></a>案例 1：員工的打卡上班時間晚於規劃的時間

員工在 08:30 AM 打卡上班。 因為他的已規劃打卡上班時間是 7:00 AM，所以他遲到了 1.50 小時。 由於這 1.50 小時視為缺勤時間，因此會提示員工選擇缺勤代碼。 員工在 03:30 PM 下班，這是已規劃的打卡下班時間。 當計算與核准員工的登記後，會為 07:00 AM 至 08:30 AM 之間的時段顯示此缺勤登記及員工在打卡上班時選擇的缺勤代碼。

在時間設定檔中，您可以設定 **打卡上班** 登記類型，以允許有員工上班遲到的寬限期。 例如，如果您將寬限期設定為 5，則只有在員工於 07:05 AM 之後打卡上班時，才會提示他們輸入缺勤代碼。

在這種情況下，由於員工沒有正當的上班遲到理由，因此他們選擇一個為不正當缺勤定義的缺勤代碼。 如果已為缺勤代碼所屬的缺勤群組啟用加班時間扣除設定，則會將缺勤代碼視為適用於不正當缺勤。 若要進行設定，請選取 **時間及出勤**&gt;**設定**&gt;**群組**&gt;**缺勤群組**，然後選取 **扣除加班時間** 核取方塊。

以下是在計算之後，員工在當天的登記顯示於 **核准** 頁面上。

| 日記帳登記類型         | 開始    | 結束      | 時間 |
|-----------------------------------|----------|----------|------|
| 缺勤 (不正當 - 上班遲到) | 07:00 AM | 08:30 AM | 1.5  |
| 打卡上班                          | 08:30 AM | 08:30 AM |      |
| 生產作業                    | 07:30 AM | 03:30 PM | 7.0  |
| 打卡下班                         | 03:30 PM | 03:30 PM |      |

這是登記轉移後產生的薪資項目。

| 工資類型     | 薪資類型 | 薪資單位 | 費率 |
|---------------|----------|-----------|------|
| 標準時間 | 1201     | 7.00      | 10   |

### <a name="scenario-2-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-standard-time-period"></a>案例 2：員工在標準時間時段內於規劃的打卡下班時間之前下班

員工在 07:00 AM 打卡上班，並提早在 01:00 PM 打卡下班。 由於 01:00 PM 早於 03:30 PM 的已規劃打卡下班時間，且 01:00 AM 處於標準時間時段中，因此會提示員工選擇缺勤代碼。 員工選擇代表醫師約診的缺勤代碼，此代碼被定義為正當缺勤。 正當缺勤的薪資率是在薪資合約中針對 **缺席** 登記類型 (**時間及出勤**&gt;**設定**&gt;**薪資表**&gt;**薪資合約**) 定義的。

以下是在計算之後，員工在當天的登記顯示於 **核准** 頁面上。

| 日記帳登記類型              | 開始    | 結束      | 時間 |
|----------------------------------------|----------|----------|------|
| 打卡上班                               | 07:00 AM | 07:00 AM |      |
| 生產作業                         | 07:00 AM | 01:00 PM | 4.0  |
| 打卡下班                              | 01:00 PM | 01:00 PM |      |
| 缺勤 (正當 - 醫師約診) | 01:00 PM | 03:30 PM | 3.5  |

這是登記轉移後產生的薪資項目。

| 工資類型     | 薪資類型 | 薪資單位 | 費率 |
|---------------|----------|-----------|------|
| 標準時間 | 1201     | 7.50      | 10   |

### <a name="scenario-3-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-flex--period"></a>案例 3：員工在 [彈性+] 時間時段內於規劃的打卡下班時間之前下班

員工在 07:00 AM 打卡上班，在 02:15 PM 打卡下班，這是已規劃的 [彈性-] 時段。 實際打卡下班時間與已規劃打卡下班時間之間的時間不視為缺勤，且不會提示員工選擇缺勤代碼。 該時間量會從員工的彈性帳戶中扣除，並發放給員工在 [彈性-] 時段剩餘部分 (02:15 PM 到o 03:30 PM) 的薪資。

以下是在計算之後，員工在當天的登記顯示於 **核准** 頁面上。

| 日記帳登記類型 | 開始    | 結束      | 時間 |
|---------------------------|----------|----------|------|
| 打卡上班                  | 07:00 AM | 07:00 AM |      |
| 生產作業            | 07:00 AM | 02:15 PM | 7.25 |
| 打卡下班                 | 02:15 PM | 02:15 PM |      |

這是登記轉移後產生的薪資項目。

| 工資類型     | 薪資類型 | 薪資單位 | 費率 |
|---------------|----------|-----------|------|
| 標準時間 | 1201     | 8.50      | 10   |

### <a name="scenario-4-the-worker-clocks-in-late-and-clocks-out-after-the-planned-clock-out-time-during-an-overtime-period"></a>案例 4：員工的打卡上班時間為遲到，並在加班時間時段內於規劃的打卡下班時間之後打卡下班

員工遲到，打卡上班時間為 09:30 AM，然後為了補足出勤遲到的時間，他們加班並在 05:00 PM 打卡下班。 由於員工遲到並透過加班來補償時數，因此公司不想為員工在 3:30 PM 的已規劃打卡下班時間及其實際打卡下班時間 05:00 PM 之間工作的時數發放加班費，即使這段時間在時間設定檔中定義為加班。

為了處理這種情況，可以設定缺勤代碼將加班時數扣除員工在同一天的任何不正當缺勤時數。 選取 **時間及出勤**&gt;**設定**&gt;**群組**&gt;**缺勤群組**，然後選取 **扣除加班時間** 核取方塊，從不正當缺勤時數中將加班時間扣除。

以下是在計算之後，員工在當天的登記顯示於 **核准** 頁面上。

| 日記帳登記類型         | 開始    | 結束      | 時間 |
|-----------------------------------|----------|----------|------|
| 缺勤 (不正當 - 上班遲到) | 07:00 AM | 09:30 AM | 1.5  |
| 打卡上班                          | 09:30 AM | 09:30 AM |      |
| 生產作業                    | 09:30 AM | 05:00 PM | 7.5  |
| 打卡下班                         | 05:30 PM | 05:30 PM |      |

如果針對所選的缺勤代碼勾選 **扣除加班時間** 核取方塊，則會將員工的不正當缺勤時數從加班費中扣除。 在此狀況中，在轉移登記後會產生以下的薪資項目。

| 工資類型     | 薪資類型 | 薪資單位 | 費率 |
|---------------|----------|-----------|------|
| 標準時間 | 1201     | 9.00      | 10   |
| 加班時間      | 1301     | 0.5       | 15   |

在這裡，從 07:00 AM 到 09:30 AM 的 1.5 小時不正當缺勤時數會扣掉從 03:30 PM 到 05:30 PM 的 2.0 小時加班時間。 此登記的結果為標準時間 1.5 小時，加班時間 0.5 小時。

相比之下，如果清除所選缺勤代碼的 **扣除加班時間** 核取方塊，則會向員工發放加班費，即使他們遲到且為不正當缺勤也是如此。 在此狀況中，在轉移登記後會產生以下的薪資項目。

| 工資類型     | 薪資類型 | 薪資單位 | 費率 |
|---------------|----------|-----------|------|
| 標準時間 | 1201     | 7.50      | 10   |
| 加班時間      | 1301     | 2.0       | 15   |

### <a name="scenario-5-the-worker-clocks-out-before-the-planned-clock-out-time-and-can-convert-the-absence-period-to-a-flex--period"></a>案例 5：員工在規劃的打卡下班時間之前打卡下班，並且可以將缺勤時段轉換為 [彈性-] 時段

以下範例顯示如何透過將缺勤時段轉換為 [彈性-] 時段來減少員工的彈性帳戶。

員工在 07:00 AM 打卡上班，並在 01:00 PM 打卡下班。 員工有一項合約，如果他們從彈性帳戶中扣除這些時數，他們便可以回家渡週末。 當員工在 1:00 PM 打卡下班時，系統會提示他們選擇缺勤代碼，因為該工作日受影響剩餘部分的缺勤時段不在規劃的 [彈性-] 期間內。 若要將該工作日的剩餘部分轉換為 [彈性-] 時段，員工可以選取為減少其彈性帳戶所設定的缺勤代碼。

若要為在工作日登記缺勤的員工減少彈性時數餘額，請選取 **時間及出勤**&gt;**設定**&gt;**群組**&gt;**缺勤群組**，並選取 **減少彈性** 核取方塊。

以下是在計算之前，員工在當天的登記顯示於 **核准** 頁面上。

| 日記帳登記類型 | 開始    | 結束      | 時間 |
|---------------------------|----------|----------|------|
| 打卡上班                  | 07:00 AM | 07:00 AM |      |
| 生產作業            | 07:00 AM | 01:00 PM | 6.0  |
| 打卡下班                 | 01:00 PM | 01:00 PM |      |

如果員工選取代表不正當缺勤的缺勤代碼，則轉移登記後所產生的薪資項目如下所示。

| 工資類型     | 薪資類型 | 薪資單位 | 費率 |
|---------------|----------|-----------|------|
| 標準時間 | 1201     | 6.00      | 10   |

如果員工選取代表正當缺勤的缺勤代碼，並設定缺勤代碼以減少他們的彈性帳戶，則轉移登記後產生的薪資項目如下所示。

| 工資類型     | 薪資類型 | 薪資單位 | 費率 |
|---------------|----------|-----------|------|
| 標準時間 | 1201     | 8.50      | 10   |

在此情況下，員工的彈性餘額會減去實際打卡下班時間與規劃打卡下班時間之間的時數 (即從 1:00 PM 到 03:30 PM 的 2.5 小時)。

> [!NOTE]
> 不建議您針對缺勤代碼同時選取 **扣除彈性時間** 核取方塊與 **扣除加班時間** 核取方塊，因為此設定會將不正當時數從員工的加班時數中扣除，同時減少員工的彈性帳戶。

### <a name="scenario-6-there-is-no-planned-absence-for-the-day-and-no-worker-attendance-for-the-day"></a>案例 6：當天沒有規劃缺勤，也沒有員工出勤

如果員工在工作日當天沒有現身工作，且該員工當天沒有規劃缺勤，則會使用預設的缺勤代碼來計算員工的登記。 若要定義預設缺勤代碼，請選取 **時間及出勤**&gt;**時間及出勤參數**。 然後，您可以在下列欄位中選取缺勤代碼：

- 自動插入彈性-
- 自動插入缺席

當為啟用彈性時數的員工計算每日登記時，則會使用在 **自動插入彈性-** 欄位中指定的缺勤代碼作為預設缺勤代碼。 如果員工的彈性時數未啟用，則會使用在 **自動插入缺席** 欄位中指定的缺勤代碼。 如果公司同時有已啟用彈性時數的員工及未啟用彈性時數的員工，則必須設定這兩個參數。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]