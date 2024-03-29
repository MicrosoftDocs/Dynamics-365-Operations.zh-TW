---
title: 使用安全庫存日記帳更新品項的最小涵蓋範圍
description: 本主題介紹如何使用安全庫存日記帳，根據歷史交易計算最小涵蓋範圍建議來更新品項的安全庫存數量。
author: ChristianRytt
ms.date: 10/28/2021
ms.topic: article
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, ReqItemTableSetup, ReqItemTable, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-10-28
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 59e4959898cd961582e1ac1d2285c0c0867ee7af
ms.sourcegitcommit: bc9e75c38e192664cde226ed3a94df5a0b304369
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449481"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage-for-items"></a>使用安全庫存日記帳更新品項的最小涵蓋範圍

[!include [banner](../../includes/banner.md)]

安全庫存是指為幫助降低品項庫存不足的風險，在庫存中應該持有該品項的額外數量。 安全庫存用於當接到銷售訂單，但廠商無法滿足客戶的要求裝運日期時的緩衝。

本主題介紹如何使用安全庫存日記帳，根據歷史交易計算最小涵蓋範圍建議，然後使用這些建議來更新品項的品項涵蓋範圍。

## <a name="overview-of-minimum-coverage-usage"></a>最低涵蓋範圍使用概述

安全庫存在 **品項涵蓋範圍** 頁面上為每個品項設置。 不同類型的補貨由不同的涵蓋範圍代碼表示。 (有關詳細資訊，請參閱 [品項的安全庫存履行](safety-stock-replenishment.md)。) 但是，所有涵蓋範圍代碼都使用在 **品項涵蓋範圍** 頁面上的 **最小** 欄位中為每個品項設置的值。 主要有兩種使用 **最小** 欄位的方法：

- **最小/最大用途的最小數量** – 這種方法使用最小數量和最小/最大邏輯。 這種方法適用於當相關品項或涵蓋範圍群組的 **涵蓋範圍代碼** 欄位設為 *最小/最大*。 **最小** 數量表示平均每日使用情況乘以品項的提前期。
- **庫存計劃用途的最小數量** – 這種方法使用最小數量表示庫存計劃與需求預測相結合。 這種方法適用於當相關品項或涵蓋範圍群組的 **涵蓋範圍代碼** 欄位設定為 *期間* 或 *要求*。 **最小** 數量表示反映所需客戶服務等級的庫存計劃，以幫助減少缺貨、部分裝運和交貨提前期。 最小數量反映指定品項的預測準確性百分比。 其不代表所需的庫存位置。

**最小** 值可以透過三種方式設定：

- 在 **品項涵蓋範圍** 頁面上手動設定
- 透過資料管理架構 (*品項涵蓋範圍* 資料實體)
- 透過安全庫存日記帳進行的安全庫存計算

## <a name="calculate-minimum-coverage-based-on-historical-usage"></a>根據歷史使用情況計算最小涵蓋範圍

安全庫存日記帳用於根據品項的歷史使用情況計算建議的最小數量，用於最小/最大用途或庫存計劃用途。 歷史使用情況代表指定期間內的所有發貨交易。 這些發貨交易包括銷售訂單交易和庫存調整。 此計算還確定了建議的最小數量對庫存值的影響，以及與目前最低數量相比庫存值的變化。

每個安全庫存日記帳行代表一個品項及其涵蓋範圍維度。 這些日記帳行已在 **安全庫存日記帳行** 頁面上建立和顯示 (**主計劃 \> 主計劃 \> 執行 \> 安全庫存計算**)。 本主題稍後將介紹使用安全庫存日記帳計算建議之最小數量的業務流程。

計劃員使用安全庫存日記帳根據所選期間的歷史使用情況計算所選品項的建議最小數量。 可以根據需要手動覆寫建議的最小值，且您可以查看建議的最小值對庫存值的潛在影響。 過帳日記帳時，品項涵蓋範圍中相關的最小數量會自動更新。

### <a name="create-a-new-safety-stock-journal-name"></a>建立新的安全庫存日記帳名稱

您必須至少建立一個安全庫存日記帳名稱，然後才能產生此類日記帳。 您通常可以使用多個日記帳名稱來幫助區分安全庫存計算。

1. 移至 **主計劃 \> 設置 \> 安全庫存日記帳名稱**。
1. 在動作窗格上，選擇 **新增**。
1. 在新行上，設定以下欄位：

    - **名稱** – 輸入日記帳的簡短名稱。
    - **說明** – 輸入日記帳的說明。
    - **使用者群組專用** – 若要限制目前日記帳名稱的對象，請選擇一個使用者群組。
    - **過帳後刪除行** – 選取此核取方塊可在您過帳時預設清理日記帳行。 清除它以保留所有已過帳的行。

    **日記帳類型** 欄位是唯讀的，且預設為 *安全庫存*。

1. 關閉頁面。

### <a name="create-a-safety-stock-journal-and-lines"></a>建立安全庫存日記帳和行

此步驟將建立日記帳並自動將行新增到其中。 每行標識一個品項、其涵蓋範圍以及從使用情況記錄中計算出的幾個數量。 計算的數量包括每個品項提前期的平均發貨量、每月平均發貨'量和每月標準偏差。

#### <a name="automatically-generate-journal-lines"></a>自動產生日記帳行

只有目前顯示的日記帳不存在任何行時，才能自動產生日記帳行。

按照以下步驟自動產生日記帳行。

1. 移至 **主計劃 \> 主計劃 \> 執行 \> 安全庫存計算**。
1. 在動作窗格上，選擇 **新增**。 新的安全庫存日記帳已建立。
1. 在 **日記帳標題詳細資料** FastTab 上設定以下欄位：

    - **名稱** – 選擇要新增行的安全庫存日記帳名稱。
    - **說明** – 預設值為您選擇的日記帳名稱的說明。 但是，您可以根據需要編輯該值。
    - **過帳後刪除行** – 選取此核取方塊可在您過帳時清理日記帳行。 清除它以保留所有已過帳的行。 該設定繼承自所選日記帳名稱。

    **日記帳** 欄位是唯讀的，並顯示您正在建立和新增行之日記帳的識別碼編號。

1. 在 **日記帳行** FastTab 上，選擇工具列上的 **建立行**。
1. 在 **為建議的最小庫存等級建立日記帳行** 對話方塊中，設定以下欄位：

    - **開始日期** – 選擇應在計算中包括發貨之期間的開始日期。
    - **結束日期** - 選擇應在此計算中包括發貨之期間的結束日期。 開始日期和結束日期之間必須至少相隔兩個月。
    - **計算標準差** – 將此選項設為 *是* 將計算標準差。 您必須將此選項設為 *是*，才能在計算建議時使用 **使用服務級別** 選項 (如本主題稍後所述)。

1. 在 **要包括的記錄** FastTab 上，您可以設置篩選和條件約束來定義要包含哪些品項。 (例如，您可以依 **涵蓋範圍群組** 值篩選。) 選擇 **篩選** 打開標準查詢編輯器對話方塊，您可以在其中定義選擇準則、排序準則和連接。 這些欄位的運作方式與它們用於 Microsoft Dynamics 365 Supply Chain Management 中其他類型的查詢一樣。
1. 在 **在背景執行** FastTab 上，選擇是否以批次處理模式執行作業，和/或設置定期排程。 這些欄位的運作方式與它們用於 Supply Chain Management 中其他類型的[背景作業](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md)時一樣。
1. 選取 **確定**。 為具有庫存交易記錄的維度建立行。

#### <a name="manually-add-or-remove-journal-lines"></a>手動新增或移除日記帳行

您隨時可以手動新增和/或移除日記帳行 (在自動產生行之後或代替自動產生行)。 使用 **日記帳行** FastTab 工具列上的以下按鈕：

- **新增** – 新增新行。 然後在每資料行中輸入值以定義要計算的產品並為其套用新的最小值。 因為建議的最小計算不適用於手動新增的行，因此不會為它們顯示新的 **計算出的最小數量** 值。 因此，您必須手動輸入 **新的最小數量** 值。 但是，您仍然可以查看 **新的最小數量** 值對庫存值的潛在影響，以及與目前指定的最小值相比庫存的潛在變化。
- **刪除** – 刪除所選的行。
- **刪除日記帳行** – 刪除日誌中的所有行。

### <a name="calculate-a-proposal"></a>計算建議值

此步驟會計算每個日記帳行的建議最小值，以及該行對庫存值的潛在影響。 (建議的最小值顯示為 **計算出的最小數量** 值。) 您可以根據需要多次計算。 計算將更新為所有日記帳行顯示的 **計算出的最小數量** 值。

除非您在動作窗格中選擇 **過帳**，否則顯示的計算不會影響每個產品的實際最小數量值。 此時，**新的最小數量** 值將套用於每個產品。

1. 移至 **主計劃 \> 主計劃 \> 執行 \> 安全庫存計算**。
1. 打開日記帳以計算建議值。 或者，按照本主題先前所述建立新日記帳。
1. 在 **日記帳行** FastTab 的工具列上選擇 **計算建議值**。 (您不必選擇任何行。)
1. 在 **計算最小庫存等級的建議值** 對話方塊中，設定以下欄位：

    - **在提前期使用平均發貨量** – 選擇此選項可根據指定期間的平均發貨量產生 **計算出的最小數量** 值。 然後，在 **倍增係數** 欄位中，輸入值以根據需要調整結果。 例如，輸入 *1.0* 使用精確計算的平均值或 *1.1* 以新增 10% 的額外緩衝。
    - **使用服務等級** – 選擇此選項可根據所需的服務等級計算建議的最小值。 然後，在 **服務等級** 欄位選擇您偏好的服務等級。
    - **提前期寬限期** – 輸入值以將正常提前期延長 (例如，允許管理)。
    - **使用計算出的最小數量作為新的最小數量** – 將此選項設為 *是* 將在計算完成後自動將值從所有行的 **計算出的最小數量** 資料行複製到 **新的最小數量** 資料行。 如果您將此選項設為 *否*，會將所有行的 **目前最小數量** 值複製到 **新的最小數量** 資料行。 然後，您必須根據需要手動編輯 **新的最小數量** 值。

1. 在 **在背景執行** FastTab 上，選擇是否以批次處理模式執行作業，和/或設置定期排程。 這些欄位的運作方式與它們用於 Supply Chain Management 中其他類型的[背景作業](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md)時一樣。
1. 選取 **確定**。 計算結果顯示在 **日記帳行** FastTab 上的 **計算出的最小數量** 資料行中。 目前，這些值只是尚未套用於您產品的建議值。

### <a name="update-minimum-quantity"></a>更新最小數量

您可以選擇安全庫存日記帳中的任何行並手動覆寫其 **新的最小數量** 欄位的值。

1. 移至 **主計劃 \> 主計劃 \> 執行 \> 安全庫存計算**。
1. 打開要編輯的日記帳。 或者，按照本主題先前所述建立新日記帳。
1. 在 **日記帳行** FastTab 上，找到要調整的行，然後在 **新的最小數量** 資料行中編輯值。 例如，您可以設定 **新的最小數量** 值，使其與 **計算出的最小數量** 值相符。 如果 **計算出的最小數量** 值為 *0* (零)，您可以輸入所需的未來值。

### <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>過帳新的最小數量並驗證結果

按照以下步驟過帳新的最小數量並驗證結果。

1. 移至 **主計劃 \> 主計劃 \> 執行 \> 安全庫存計算**。
1. 打開日記帳以過帳新的最小數量。 或者，按照本主題先前所述建立新日記帳。
1. 在動作窗格上，選擇 **過帳**。
1. 在 **過帳日記帳** 對話方塊中，根據需要設定 **將所有過帳錯誤轉移到新日記帳** 欄位。 然後選擇 **確定** 以過帳日記帳。
1. 如果在 **日記帳行** FastTab 上變更了行的 **新的最小數量** 值，可以按照以下步驟確認變更：

    1. 對於您編輯的行，選擇 **品項編號** 資料行中的連結。
    1. 在 **產品資訊** 對話方塊中，選擇 **品項編號** 欄位中的連結，以打開相關的已發佈產品記錄。
    1. 在動作窗格的 **計劃** 索引標籤上，在 **涵蓋範圍** 群組中選取 **品項涵蓋範圍**。
    1. 請注意，您使用已過帳的安全庫存日記帳調整的站點和倉庫的 **最小** 值現已更新以符合您進行的編輯。

## <a name="additional-resources"></a>其他資源

- [品項的安全庫存履行](safety-stock-replenishment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
