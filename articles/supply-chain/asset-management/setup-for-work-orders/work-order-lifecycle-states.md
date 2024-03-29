---
title: 工單生命週期狀態
description: 本主題說明在資產管理中的工單生命週期狀態。
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderLifecycleState, EntAssetWorkOrderLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fa0980438ec629ef7ae6bf711d5ae87efca131e6ab86dfcaa1f17d953725147a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447204"
---
# <a name="work-order-lifecycle-states"></a>工單生命週期狀態


[!include [banner](../../includes/banner.md)]

 

工單生命週期狀態定義了工單經歷的狀態。 例如 **已建立**、**已排程**、**進行中** 和 **已結束**。 可以手動更新工單上的工單生命週期狀態，也可以自動更新 (例如，在工單排程期間)。

必需在 **專案管理和核算參數** 頁面 (**專案管理和核算** \> **專案管理和核算參數**)，將工單所需的工單生命週期狀態必須附加到相符的專案階段。 先在專案管理和核算中設定專案階段。 然後，在資產管理中設定工單生命週期狀態和工單生命週期模型。

下表說明 **工單生命週期狀態** 頁面 (**資產管理** \> **設定** \> **工單** \> **生命週期狀態**) 的 **一般** 快速索引標籤上，**工單** 和 **排成** 區段中的選項。

![工單生命週期狀態頁面。](media/09-setup-for-work-orders.png)

| 選項名稱                   | 描述 |
|-------------------------------|-------------|
| 使用中                        | 如果工單在此生命週期狀態下應該處於使用中狀態，將此選項設定為 **是**。 |
| 新增行                      | 如果可以將工單作業新增到處於此生命週期狀態的工單，將此選項設定為 **是**。 |
| 刪除                        | 如果工單在此生命週期狀態下可以刪除，將此選項設定為 **是**。 |
| 刪除行                   | 如果可以從處於此生命週期狀態的工單刪除工單作業，將此選項設定為 **是**。 |
| 允許排程              | 如果工單在此生命週期狀態下可以排程，將此選項設定為 **是**。 |
| 設定實際開始日期              | 如果工單更新到此生命週期狀態時，應提示使用者選擇實際開始日期和時間，將此選項設定為 **是**。 |
| 設定實際結束日期                | 如果工單更新到此生命週期狀態時，應提示使用者選擇實際結束日期和時間，將此選項設定為 **是**。 |
| 過帳日記帳                 | 如果在工單更新為此生命週期狀態時，應該自動過帳工單日記帳，將此選項設置為 **是**。 如果在日記帳過帳過程中發生錯誤，則會顯示一則訊息，並取消工單生命週期狀態的更新。 要查看工單的日記帳行，請選擇 **資產管理** \> **常見** \> **工單** \> **所有工單**、**有效工單** 或 **我的有效工單**，在清單中選擇工單，然後選擇 **日記帳**。 這種在特定生命週期狀態下自動工單日記帳過帳的設定與您在 **工單日記帳** 頁面選擇 **過帳日記帳** 時相同。<p>**請注意：** 如果您將此選項設定為 **是**，且未設定核准工作流程，則會自動過帳日記帳。 如果公司使用在 **日記帳核准** 頁面 (**專案管理與核算** \> **設定** \> **日記帳** \> **日記帳核准**) 中設定的日記帳核准設定，經理或員工必須驗證並過帳消耗登記。</p> |
| 處理維護檢查清單 | 如果當工單更新到此生命週期狀態時，應處理所有附加的維護檢查清單，將此選項設定為 **是**。 在此項處理期間，將過帳在維護檢查清單中建立的任所有數器登記都，並評估整個維護檢查清單的結果。 將評估結果為 **通過** 和 **失敗** 的維護檢查清單行，並且如果至少一個行失敗，將在資產管理中把整個維護檢查清單標記為 **失敗**。 |
| 就緒                         | 如果在將工單更新為此生命週期狀態時，應該將對該工單建立的所有工單作業的工單作業排程狀態自動更新為 **就緒**，將此選項設定為 **是**。 |
| 開始                         | 如果在將工單更新為此生命週期狀態時，應該將對該工單建立的所有工單作業的工單作業排程狀態自動更新為 **已開始**，將此選項設定為 **是**。 |
| 結束                           | 如果在將工單更新為此生命週期狀態時，應該將對該工單建立的所有工單作業的工單作業排程狀態自動更新為 **已結束**，將此選項設定為 **是**。 |
| 刪除排程行         | 如果在將工單更新為此生命週期狀態時，應該刪除對在已排程的工單建立的所有工單作業進行的排程，將此選項設定為 **是**。 換言之，將刪除資產、關聯維護工作人員和關聯工具的產能預留。 例如，對名稱為 **估計** 的工單生命週期狀態，將此選項設定為 **是**。 然後，如果在因為需要重新排程時將工單復原到此生命週期狀態，則可刪除對該工單的安排。 |

## <a name="set-up-project-stages-and-work-order-lifecycle-states"></a>設定專案階段和工單生命週期狀態

1. 選擇 **專案管理和核算** \> **設定** \> **專案管理和核算參數**。
2. 在 **專案階段** 索引標籤上，對於要使用的每個階段，選取工單所需的每個專案類型的核取方塊。 專案類型定義有關允許財務工作的規則。 財務工作的範例包括建立預測、建立估算和建立期初餘額。

    > [!IMPORTANT]
    > 如果未為專案類型選擇專案階段，但將專案階段用於工單生命週期狀態，則不會以適當的方式更新工單專案。

3. 關閉 **專案管理與核算參數** 頁面。
4. 選取 **資產管理** \> **設定** \> **工單** \> **生命週期狀態**。
5. 選取 **新增** 建立工單生命週期狀態。
6. 在 **生命週期狀態** 欄位中，輸入生命週期狀態識別碼。
7. 在 **名稱** 欄位中，輸入名稱。

    在 **詳細資料** 快速索引標籤上，**生命週期模型** 欄位會顯示使用此生命週期狀態的工單生命週期模型數目。

8. 在 **一般** 快速索引標籤的 **工單** 區段，將相關選項設定為 **是**，選擇應該可用於此生命週期狀態的功能。 有關這些選項的說明，請參閱本主題前文的表格。
9. 在 **專案** 區段的 **階段** 欄位，選擇應該與此生命週期狀態相關的專案階段。
10. 如果工單處於此生命週期狀態時，應自動關閉與每個工單作業相關的專案活動，請將 **專案** 區段中的 **關閉活動** 選項設定為 **是**。

    > [!NOTE]
    > 要尋找與工單作業相關的專案活動編號，請選擇 **資產管理** \> **常見** \> **工單** \> **所有工單**、**有效工單** 或 **我的有效工單**。 打開工單，然後選擇工單作業。 在 **行詳細資料** 快速索引標籤的 **一般** 索引標籤上 **專案** 區段中的 **活動編號** 欄位中顯示活動編號。

11. 如果當工單處於此生命週期狀態時，應將工單專案預測自動複製到工單日記帳，將 **預測** 區段中的 **複製工時預測**、**複製品項預測** 和/或 **複製費用預測** 選項設定為 **是**。
12. 如果當工單處於此生命週期狀態時，應更新工單作業的排程狀態，在 **排程** 區段中的一個選項設定為 **是**。 有關 **就緒**、**開始**、**結束** 和 **刪除排成行** 選項的說明，請參閱本主題前文的表格。

    > [!NOTE]
    > 若要查看與工單作業關聯的排程行，請選擇 **資產管理** \> **常見** \> **工單** \> **所有工單**、**有效工單** 或 **我的有效工單**。 在 **工單作業** 快速索引標籤上選擇工單作業，然後在 **行詳細資料** 快速索引標籤上查看相關資訊。 **排成** 索引標籤上的 **狀態** 欄位顯示工單作業的狀態。 **狀態** 欄位可以設定為以下值：**已排程**、**就緒**、**已開始**、**已停止** 和 **已結束**。

13. 在 **維護要求** 區段的 **生命週期狀態** 欄位，選擇相關維護要求應更新到的維護要求生命週期狀態。 將自動進行此更新。 只有在用於維護要求的維護要求生命週期模型中選擇了維護要求生命週期狀態時，才能執行此操作。
14. 如果在工單更新為此生命週期狀態時，應該在 **資產 BOM** 頁中自動更新工單中使用的所有品項，請將 **資產** 區段中的 **更新資產 BOM** 選項設為 **是**。 如果在工單生命週期狀態將工單定義為已完成或已結束之類情況下，此設定可能有關。
15. 如果應該從工單集區自動刪除此生命週期狀態的工單，請將 **工單集區** 區段中的 **刪除集區參考** 選項設為 **是**。
16. 在 **驗證** 快速索引標籤上，將相關選項設為 **是**，選擇此生命週期狀態下應該啟動的驗證類型。 然後在應該選擇的每個驗證類型的 **類型** 欄位中，選擇如果尚未驗證與驗證類型關聯的必填欄位時應顯示的訊息的類型。 如果選擇 **錯誤**，則取消工單生命週期狀態的更新，直到工單上的相關必填欄位更新完畢。

    - 將把 **維護停機時間**、**維護檢查清單**、**故障異常特徵**、**故障原因** 和 **故障補救** 選項與 **工單類型** (**資產管理** \> **設定** \> **工單**\>**工單類型**) 頁面的 **強制** 區段中的選項關聯。 若要啟用這些驗證，還必須將用於工單的工單類型的相關選項設定為 **是**。
    - 如果工單更新到的生命週期狀態的 **維護檢查清單** 選項設定為 **是**，將執行驗證以驗證標記為 **強制** 的維護檢查清單行是否登記為 **已檢查** 或 **不適用**。 如果這些登記均未在必填行上進行，則在工單更新到此生命週期狀態時會顯示資訊、錯誤或警告訊息。
    - 如果工單更新到的生命週期狀態的 **承諾成本** 選項設定為 **是**，將計算每個工單作業的承諾成本總額 (即法人承諾支付的費用總額)。 如果承諾的成本金額大於 0 (零) ，則會顯示一則訊息。 在 **專案管理和核算參數** 頁面 (**專案管理和核算** \> **設定** \> **專案管理和核算參數**) 的 **成本控制** 索引標籤的 **成本承諾** 快速索引標籤中選擇要包含的成本承諾類型。
    - 如果工單更新到的生命週期狀態的 **維護停機時間** 選項設定為 **是**，將驗證與工單相關的資產維護停機時間。 如果已建立維護停機登記，但沒有 **已結束** 的登記，則當工單更新到此生命週期狀態時會顯示一則訊息。
    - 如果標準專案設定不包括資產管理設定所需的所有階段，您可以在 **專案管理和核算參數** 頁面的 **專案階段** 索引標籤上設定使用者定義的專案階段。 下圖顯示 **專案管理和核算參數** 頁面的 **專案階段** 索引標籤。

    ![為各種專案類型頁面設定專案階段。](media/10-setup-for-work-orders.png)

> [!NOTE]
> 如果將工單更新到的生命週期狀態處於非使用中狀態，則與該工單相關但尚未過帳的日記帳將自動刪除。 此行為有助於確保自動清理未使用的資料。 (如果在 **工單生命週期狀態** 頁面 **一般** 快速索引標籤上將某個生命週期狀態的 **使用中** 選項設為 **否**，則該生命週期狀態為非使用中。)
>
> 但是，如果手動將工單設為非使用中，將 **不會** 自動刪除與該工單關聯，但尚未過帳的日記帳。 (要手動停用工單，請選擇 **資產管理** \> **常用** \> **工單** \> **所有工單** 或 **使用中工單**。 打開工單，切換到 **標題** 檢視表。 在 **一般** 快速索引標籤，選擇 **編輯**，然後將 **使用中** 選項設定為 **否**。)

## <a name="relations-among-work-order-lifecycle-models-work-order-types-and-work-order-lifecycle-states"></a>工單生命週期模型、工單類型和工單生命週期狀態之間的關聯

生命週期模型參考工作流程，並按順序在生命週期模型中選擇生命週期狀態。 將為工單類型設定生命週期模型。 工單類型決定了工作流程和工作流程的大小或範圍。 例如，可以將 **維護** (這是標準工單類型) 與具有大量生命週期狀態的工單生命週期模型關聯。 相比之下，您可能有一個 **糾正** 工單類型用於尚未排程的工單，或用於因為情況緊急而在建立工單之前即已完成了作業的工單。 可將此工單類型與只有少量生命週期狀態的工單生命週期模型關聯。

使用類型的原因是，為工單或資產定義類型時，會自動定義關聯的工作流程 (即生命週期狀態)。 如需設定工單類型方式的詳細資訊，請參閱[工單類型](../setup-for-work-orders/work-order-types.md)。

> [!NOTE]
> 除工單外，生命週期狀態、生命週期模型和類型還適用於功能位置、資產和維護要求。

下圖顯示工單類型、生命週期模型和生命週期狀態之間的關聯。

![工單類型頁面與工單生命週期模型頁面的比較。](media/11-setup-for-work-orders.png)

## <a name="work-order-lifecycle-models"></a>工單生命週期模型

建立工單所需的工單生命週期狀態後，可將其劃分為工單生命週期模型。 至少應建立一個標準生命週期模型。

1. 選取 **資產管理** \> **設定** \> **工單** \> **生命週期模型**。
2. 選取 **新增** 建立工單生命週期模型。
3. 在 **生命週期模型** 欄位中，輸入生命週期模型識別碼。
4. 在 **名稱** 欄位中，輸入名稱。

    在 **詳細資料** 快速索引標籤上，**生命週期狀態** 欄位會顯示在生命週期模型中所選的生命週期狀態數目。 **工單類型** 欄位會顯示使用生命週期模型的工單類型類型數目。

5. 在 **生命週期狀態** 快速索引標籤上，選取應在生命週期模型中包含的生命週期狀態：

    - 若要在生命週期模型中包含生命週期狀態，請在 **剩餘的生命週期狀態** 區段中選取該狀態，然後選取向右箭號按鈕![向右箭號。](media/12-setup-for-work-orders.png) 將其移至 **選取的生命週期狀態** 區段。
    - 若要在生命週期模型中包含所有可用生命週期狀態，請選取 **選取所有可用階段** 按鈕![選取所有可用階段。](media/13-setup-for-work-orders.png)。 所有生命週期狀態都移到 **已選取生命週期狀態** 區段。
    - 若要將生命週期狀態從生命週期模型中移除，請在 **已選取生命週期狀態** 區段中選取該狀態，然後選取向左箭號按鈕![向左箭號。](media/14-setup-for-work-orders.png) 將其移至 **剩餘的生命週期狀態** 區段。

6. 選取 **生命週期狀態更新** 以定義會遵循所選生命週期狀態的生命週期狀態。
7. 無論工單的上一個生命週期狀態是什麼，均在 **更新** 快速索引標籤上的 **已排程狀態** 欄位中選擇始終應該為已經為其完成了工單安排的工單選擇的生命週期狀態。
8. 在 **未排程的生命週期狀態** 欄位，選擇在刪除工單排程時應一律為工單選擇的生命週期狀態。
9. 儲存工單生命週期模型。

![工單生命週期模型頁面。](media/15-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]