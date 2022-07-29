---
title: 行動發票核准
description: 本主題意在藉由將廠商行動發票核准為使用案例，提供設計行動方案的務實做法。
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 83d95ef6d9fcff060ac992b11ab5773af075fea5409e43430b4826dc097570c7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450390"
---
# <a name="mobile-invoice-approvals"></a>行動發票核准

[!include [banner](../includes/banner.md)]

行動功能讓商務使用者可以設計行動體驗。 以進階方案而言，平台也讓開發人員按其需求擴充功能。 行動學習一些新概念的最有效方式是逐步完成設計一些方案的流程。 本主題意在藉由將廠商行動發票核准為使用案例，提供設計行動方案的務實做法。 本主題應可幫助您設計方案的其他變化情況，也可套用在與廠商發票無關的其他方案。

## <a name="prerequisites"></a>先決條件

| 先決條件                                                                                            | 描述                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 行程手冊預讀版                                                                                |[行動平台](../../fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| Dynamics 365 Finance                                                                              | 1611 發行版本和平台更新 3 的環境 (2016 年十一月)                   |
| 安裝 Hotfix KB 3204341。                                                                              | 任務錄製器可能誤錄下拉對話方塊的兩道關閉指令；這會納入平台更新 3 (2016 年十一月更新)。 |
| 安裝 Hotfix KB 3207800。                                                                              | Hotfix 讓附件在行動客戶端檢視；這已納入平台更新 3 (2016 年十一月更新)。           |
| 安裝 Hotfix KB 3208224。                                                                              | 行動廠商發票核准申請的申請代碼；這已納入 7.0.1 版本 (2016 年五月)。                          |
| Android 或已安裝行動應用程式的 iOS 或 Windows 裝置。 | 在適當的應用程式商店搜尋此應用程。                                                                                                                     |

## <a name="introduction"></a>簡介
廠商發票的行動審核需要 "先決條件" 章節提到的三個 Hotfix。 這些 Hotfix 不提供發票審核工作區。 若要了解行動環境的工作區，請閱讀 "先決條件" 章節提到的行動手冊。 必須設計發票審核工作區。 

每間組織都以不同方式編排和定義廠商發票的業務流程。 在您為廠商發票審核設計行動體驗之前，您應該思考下列各個層面的業務流程。 構想是盡可能使用這些資料點最佳化裝置上的使用者體驗。

-   使用者希望在行動體驗中看到發票抬頭下有哪些欄位以及按照的順序？
-   使用者希望在行動體驗中看到發票明細下有哪些欄位以及按照的順序？
-   發票有幾條發票明細？ 這裡套用 80-20 規則，並最佳化 80% 部份。
-   使用者希望審核期間在行動設備上查看會計分配 (發票編碼) 嗎？ 如果這個問題的答案是肯定，請思考下列問題：
    -   各列發票明細有多少個會計分配項目 (擴充價格、銷售稅、收費、拆分等)？ 再次套用 80-20 規則。
    -   發票的抬頭也有會計分配嗎？ 如果是，這些會計分配應該在裝置上開放使用嗎？

    > [!NOTE]
    > 本主題不解釋如何編輯會計分配，因為行動方案目前不支援此功能。

-   使用者是否希望在裝置上查看發票附件？

行動發票審核體驗設計會依照這些問題的答案而異。 目標是最佳化組織中行動業務流程的使用者體驗。 在本主題其餘部分，我們將查看上述問題答案不同的兩種設想情況變化。 

搭配行動設計師時，一般指引須確定 '發佈' 更改內容，才能防止遺漏更新。

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>為 Contoso 設計簡單的發票審核方案
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>方案屬性</th>
<th>答案</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>使用者希望在行動體驗中看到發票抬頭下有哪些欄位以及按照的順序？</td>
<td><ol>
<li>廠商名稱</li>
<li>發票總額</li>
<li>發票帳戶</li>
<li>發票編號</li>
<li>發票日期</li>
<li>發票描述</li>
<li>到期日</li>
<li>發票貨幣</li>
</ol></td>
</tr>
<tr class="even">
<td>使用者希望在行動體驗中看到發票明細下有哪些欄位以及按照的順序？</td>
<td><ol>
<li>採購類別</li>
<li>數量</li>
<li>單價</li>
<li>明細淨額</li>
<li>1099 金額</li>
</ol></td>
</tr>
<tr class="odd">
<td>發票有幾條發票明細？ 這裡套用 80-20 規則，並最佳化 80% 部份。</td>
<td>1</td>
</tr>
<tr class="even">
<td>使用者希望審核期間在行動設備上查看會計分配 (發票編碼) 嗎？</td>
<td>是</td>
</tr>
<tr class="odd">
<td>各列發票明細有多少個會計分配項目 (擴充價格、銷售稅、收費等)？ 再次套用 80-20 規則。</td>
<td>擴充價格：2 銷售稅：0 收費：0</td>
</tr>
<tr class="even">
<td>發票的抬頭也有會計分配嗎？ 如果是，這些會計分配應該在裝置上開放使用嗎？</td>
<td>未使用</td>
</tr>
<tr class="odd">
<td>使用者是否希望在裝置上查看發票附件？</td>
<td>是</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>建立工作區

1.  在瀏覽器登入應用程式。
2.  登入後，新增 **&mode=mobile** 到下方範例所示的 URL，接著重新整理頁面：https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**
3.  點選頁面右上角的 **設定** (齒輪) 按鈕，然後點選 **行動應用程式**。 行動應用程式設計器必須像任務錄製器般現身。
4.  點選 **新建** 建立新工作區。 以本範例而言，將工作區命名為 **我的核准**。
5.  輸入描述。
6.  選取工作區顏色。 工作區顏色將用在此工作區行動體驗的整體風格。
7.  選取工作區圖示。
8.  點選 **完成**
9.  點選 **發佈工作區** 儲存更改

### <a name="vendor-invoices-assigned-to-me"></a>指派給我的廠商發票

您應該設計的第一個行動頁面是指派給使用者審核的發票清單。 若要設計此行動頁面，請使用 **VendMobileInvoiceAssignedToMeListPage** 頁面。 在您完成這項程序之前，請確定至少已指派給您一張廠商發票審核，而發票明細有兩個分配項。 此項設定符合此方案要求。

1.  將 URL 中的選單項目名稱更換為 **VendMobileInvoiceAssignedToMeListPage** 以便打開 **應付帳款** 模組中的 **指派給我的待核定廠商發票** 清單頁面。 本頁面將根據系統指派給您的發票數量顯示這些發票。 若要尋找特定發票，您可以使用左側的篩選條件。 不過本範例不需要特定發票。 我們只需要指派給您一些發票，這將允許您設計行動頁面。 開放使用的新頁面一直專為行動廠商發票方案設計。 因此，您必須使用這些頁面。 URL 應仿照下列 URL，輸入後必須出現圖說顯示的頁面：https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile 

    [![指派給我的待核定廠商發票頁面。](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)
    
2.  點選頁面右上角的 **設定** (齒輪) 按鈕，然後點選 **行動應用程式**
3.  選取您的工作區並點選 **編輯**
4.  點選 **新增頁面** 建立第一個行動頁面。
5.  輸入名稱，例如 **我的廠商發票**，以及描述，例如 **指派給我審核的廠商發票**。
6.  點選 **完成**。
7.  在行動設計器的 **欄位** 索引標籤上點選 **選取欄位**。 清單頁面上的欄位必須仿照下圖。 

    [![指派給我的待核定廠商發票頁面上的欄位。](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)
    
8.  從必須向行動頁面中的使用者顯示清單頁面新增必要欄位。 您新增的順序是欄位將向最終使用者顯示的順序。 更改欄位順序的唯一方法是重新選取所有欄位。 根據此項方案要求，需要八個欄位如下。 不過，一些使用者可能認為八個欄位的資訊太多，無法在行動裝置上完整顯示。 因此，我們只會顯示行動清單視圖中最重要的欄位。 其餘欄位將在我們稍候將設計的細節視圖出現。 現在，我們將新增欄位如下。 點選這些欄位的加號 (**+**) 以便新增到行動頁面。
    - 廠商名稱
    - 發票總額
    - 發票帳戶
    - 發票編號
    - 發票日期

    待欄位新增後，行動頁面必須仿照下圖。 
    
    [![已新增欄位後的頁面。](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)

9.  您現在也必須新增下列欄位，我們日後才能啟用工作流程動作。
    - 顯示完成任務
    - 顯示委託任務
    - 顯示召回任務
    - 顯示拒絕任務
    - 顯示請求完成任務
    - 顯示重新提交任務

10. 點選 **完成** 離開編輯模式。
11. 點選 **返回** 然後 **完成**，以便離開工作區
12. 點選 **發佈工作區** 儲存您的工作。
13. 啟用 **發票** 下方，應付帳款參數表單的 **顯示待核定廠商發票清單的發票總額**。 請注意，只有啟用此參數，才會計算顯示在待核定廠商發票清單頁面上的發票總額。 這是作為先決條件 Hotfix 3208224 的部分新功能。

### <a name="vendor-invoice-details"></a>廠商發票細節

若要設定行動發票細節頁面，請使用 **VendMobileInvoiceHeaderDetails** 頁。 請注意，本頁會根據您系統的發票數量顯示最早期的發票 (最先建立的發票)。 若要尋找特定發票，您可以使用左側的篩選條件。 不過本範例不需要特定發票。 我們只需要一些發票資料就能設計行動頁面。 

[![工作流程頁面。](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)

1. 將 URL 裡的選單項目名稱更換為 **VendMobileInvoiceHeaderDetails** 以打開表單

2. 使用 **設定** (齒輪) 按鈕打開行動設計器。

3. 點選 **編輯** 按鈕在工作區開始編輯模式。

4. 選取您稍早建立的 **我的廠商發票** 頁面，然後點選 **編輯**。

5. 請在 **欄位** 索引標籤上點選 **網格** 欄位標題。

6. 點選 **屬性&gt;新增頁面**。 **註：** 當您點選 **網格** 標題並新增頁面時，與細節頁的關係會自動建立。

7. 輸入頁面標題，例如 **發票細節**，以及描述，例如 **檢視發票標頭和明細**。

8. 點選 **選取欄位**。 請注意，您新增的順序是欄位將向最終使用者顯示的順序。 更改欄位順序的唯一方法是重新選取所有欄位。 

9. 根據此項方案要求，從標題新增欄位如下：
   - 廠商名稱
   - 發票總額
   - 發票帳戶
   - 發票編號
   - 發票日期
   - 發票描述
   - 到期日
   - 發票貨幣

10. 從頁面的明細網格新增欄位如下：
    - 採購類別
    - 數量
    - 單價
    - 明細淨額
    - 1099 金額

11. 待所有欄位皆按前兩道步驟新增後，單選 **完成**。 頁面必須仿照下圖。
    
    [![顯示新增額外欄位的插圖。](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)

12. 點選 **完成** 離開編輯模式。

13. 點選 **返回** 然後 **完成**，以便離開工作區

14. 點選 **發佈工作區** 儲存您的工作

### <a name="workflow-actions"></a>工作流程動作

若要新增工作流程動作，請使用 **VendMobileInvoiceHeaderDetails** 頁面。 若要打開本頁面，更換 URL 裡的選單項目名稱，如稍早您做過的動作。 接著使用 **設定** (齒輪) 按鈕打開行動設計器。 按照下列步驟在細節頁面新增工作流程動作。 您必須具備已經指派給你，並處於適當狀態的發票，工作流程動作才能開發讓您用在接下來的設計工作。

#### <a name="record-workflow-actions"></a>記錄工作流程動作
1.  點選 **編輯** 按鈕在工作區開始編輯模式。
2.  選取您稍早建立的 **發票細節** 頁面，然後點選 **編輯**。
3.  請在 **動作** 索引標籤上點選 **新增動作**。
4.  輸入動作標題，例如 **核准**，以及描述，例如 **核准發票**。 請注意，您在這裡輸入的動作標題會成為行動應用程式中，向使用者顯示的動作名稱。
5.  點選 **完成**。
6.  點選 **選取欄位**。
7.  請在 **VendMobileInvoiceHeaderDetails** 頁面逐步完成工作流程，並完成您希望記錄的動作。 請確定您在這段流程輸入工作流程留言，以便讓留言欄位也納入行動體驗。
8.  待工作流程動作執行後，點選 **完成** 完成選取欄位任務。
9.  點選 **完成** 離開編輯模式。
10. 點選 **返回** 然後 **完成**，以便離開工作區
11. 點選 **發佈工作區** 儲存您的工作
12. 重複前面步驟記錄所有必要的工作流程動作。 

#### <a name="create-a-js-file"></a>建立 .js 檔案
1. 打開記事本或 Microsoft Visual Studio 貼上下列程式碼。 將檔案另存為 .js 檔案。 此程式碼執行下列動作：
    - 它隱藏我們稍早在行動清單頁面新增與工作流程另外相關的欄位。 我們已經新增這些欄位，應用程式在上下文就備齊資訊，可以執行下一步。
    - 根據有效執行的工作流程步驟，它會套用邏輯只顯示這些動作。

    > [!NOTE]
    > 程式碼的頁面和其他控制項名稱必須與工作區裡的名稱相同。

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }
    ```

2.  藉由選取 **邏輯** 索引標籤將程式碼檔案上傳到工作區
3.  點選 **完成** 離開編輯模式。
4.  點選 **返回** 然後 **完成**，以便離開工作區
5.  點選 **發佈工作區** 儲存您的工作

### <a name="vendor-invoice-attachments"></a>廠商發票附件

1. 點選頁面右上角的 **設定** (齒輪) 按鈕，然後點選 **行動應用程式**

2. 點選 **編輯** 按鈕在工作區開始編輯模式。

3. 選取您稍早建立的<strong>發票細節**頁面，然後點選**編輯</strong>。

4. 設定 **文件管理** 選項為 **是**，如下所示。 **註：** 如果並未要求在行動裝置顯示附件，您可以將此選項設定為 **否**，這是預設值。
   
   ![文件管理。](./media/docmanagement-216x300.png)

5. 點選 **完成** 離開編輯模式。

6. 點選 **返回** 然後 **完成**，以便離開工作區

7. 點選 **發佈工作區** 儲存您的工作

### <a name="vendor-invoice-line-distributions"></a>廠商發票明細分配

此方案要求確認只有明細等級分配，而且發票將始終只有一條明細。 因為這項方案不難，所以行動裝置使用者體驗也必須簡單到使用者不必深入幾個等級才能檢視分配情況。 廠商發票包括顯示發票抬頭下的所有分配選項。 這類體驗正是我們需要行動方案具備的。 因此，我們將使用 **VendMobileInvoiceAllDistributionTree** 頁面設計這部分的行動方案。 

> [!NOTE] 
> 了解需求有助於我們在設計方案時，決定預計使用的特定頁面以及如何恰到好處地最佳化使用者的行動體驗。 我們將在第二個方案使用不同頁面顯示分配情況，因為該方案要求不同。

1.  更換 URL 裡的選單項目名稱，如您以前做過的動作。 出現的頁面應仿照下圖。

    [![所有分配頁面。](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)

2.  使用 **設定** (齒輪) 按鈕打開行動設計器。

3.  點選 **編輯** 按鈕在工作區開始編輯模式。 **注意：** 您將看到兩個新頁面已經自動建立。 系統會建立這些頁面，因為您在上一節啟動文件管理功能。 您可以忽略這些新頁面。

4.  點選 **新增頁面**。

5.  輸入頁面標題，例如 **檢視會計**，以及描述，例如 **檢視發票會計**。

6.  點選 **完成**。

7.  在 **欄位** 索引標籤上點選 **選擇欄位**，從分配頁面選取下列欄位，然後點選 **完成**：
    1.  金額
    2.  貨幣
    3.  總帳

    > [!NOTE] 
    > 我們並未從分配網格選取 **描述** 欄位，因為此方案要求確認擴充價格是分配的唯一金額。 因此，使用者將不需要另一個欄位判定分配的金額類型。 不過我們 **將** 在下一個方案使用此項資訊，因為該方案要求指明其他金額類型已有分配項目 (例如銷售稅)。

8.  點選 **完成** 離開編輯模式。

9.  點選 **返回** 然後 **完成**，以便離開工作區

10. 點選 **發佈工作區** 儲存您的工作

#### <a name="adding-navigation-to-view-accounting-page"></a>新增瀏覽功能到 "檢視會計" 頁面

**檢視會計** 行動頁面目前尚未連結我們目前為止已經設計的任何行動頁面。 因為使用者應該能夠從行動裝置的 **發票明細** 頁面瀏覽到 **檢視會計** 頁面，我們必須提供從 **發票明細** 頁到 **檢視會計** 頁的瀏覽功能。 我們透過 JavaScript 使用額外邏輯建立這類瀏覽功能。

1.  打開您之前建立的 .js 檔案，接著新增下列程式碼中重點標示的明細。 此段程式碼做兩件事：
    1.  它有助於保證使用者不會直接從工作區瀏覽到 **檢視會計** 頁。
    2.  它建立從 **發票明細** 頁瀏覽控制 **檢視會計** 頁的功能。

    > [!NOTE] 
    > 程式碼的頁面和其他控制項名稱必須與工作區裡的名稱相同。

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }
    ```
    
2.  藉由選取 **邏輯** 索引標籤將程式碼檔案上傳到工作區，以便覆寫上一段程式碼
3.  點選 **完成** 離開編輯模式。
4.  點選 **返回** 然後 **完成**，以便離開工作區
5.  點選 **發佈工作區** 儲存您的工作

### <a name="validation"></a>驗證

請從您的行動裝置打開應用程式，並連接您的執行個體。 確定您登入已指派您審核廠商發票的公司。 您應該能夠執行下列動作：

-   查看 **我的核准** 工作區。
-   切入 **我的核准** 工作區並查看 **我的廠商發票** 頁。
-   切入 **我的廠商發票** 頁面並查看已經指派給您的發票清單。
-   切入其中一張發票，查看發票標頭細節和明細。
-   請查看細節頁面上的附件連結，並使用此連結瀏覽附件清單、檢視附件。
-   請查看細節頁面上的 **檢視會計** 頁面連結，並使用此連結瀏覽分配頁面、檢視分配情況。
-   請點選細節頁面底部的 **動作** 選單，並執行適用工作流程步驟的工作流程動作。

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>為 Fabrikam 設計複雜的發票審核方案
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>方案屬性</th>
<th>答案</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>使用者希望在行動體驗中看到發票抬頭下有哪些欄位以及按照的順序？</td>
<td><ol>
<li>廠商名稱</li>
<li>發票金額</li>
<li>發票帳戶</li>
<li>發票編號</li>
<li>發票日期</li>
<li>發票描述</li>
<li>到期日</li>
<li>發票貨幣</li>
</ol></td>
</tr>
<tr class="even">
<td>使用者希望在行動體驗中看到發票明細下有哪些欄位以及按照的順序？</td>
<td><ol>
<li>採購類別</li>
<li>數量</li>
<li>單價</li>
<li>明細淨額</li>
<li>1099 金額</li>
</ol></td>
</tr>
<tr class="odd">
<td>發票有幾條發票明細？ 這裡套用 80-20 規則，並最佳化 80% 部份。</td>
<td>5</td>
</tr>
<tr class="even">
<td>使用者希望審核期間在行動設備上查看會計分配 (發票編碼) 嗎？</td>
<td>是</td>
</tr>
<tr class="odd">
<td>各列發票明細有多少個會計分配項目 (擴充價格、銷售稅、收費等)？ 再次套用 80-20 規則。</td>
<td>擴充價格：2 銷售稅：2 收費：2</td>
</tr>
<tr class="even">
<td>發票的抬頭也有會計分配嗎？ 如果是，這些會計分配應該在裝置上開放使用嗎？</td>
<td>未使用</td>
</tr>
<tr class="odd">
<td>使用者是否希望在裝置上查看發票附件？</td>
<td>是</td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a>後續步驟

根據方案 2 要求可以完成方案 1 的變化動作如下。 您可以使用本節改善您的行動應用程式體驗。

1.  因為方案 2 預計會有更多發票明細，因此下列的設計更改將有助於最佳化行動設備的使用者體驗：
    1.  使用者可以選擇在分開的行動頁面上檢視明細，而不是在細節頁面上檢視發票明細 (如方案 1)。
    2.  因為這套方案預計會有更多發票明細，如果 **VendMobileInvoiceAllDistributionTree** 頁用來設計行動裝置分配頁 (如方案 1)，使用者可能覺得明細與分配互連讓人困惑。 因此，請使用 **VendMobileInvoiceLineDistributionTree** 頁設計分配頁。
    3.  最理想做法是分配應該在此方案的發票明細上下文中顯示。 因此，請確定使用者可以切入明細查看分配頁面。 使用頁面連結功能建立切入細查功能，如同您在方案 1 對標題和細節頁面所做的動作。

2.  因為方案 2 的分配預計會有更多金額類型 (銷售稅、收費等)，所以顯示金額類型描述會很實用。 (我們在方案 1 省略這項資訊。)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
