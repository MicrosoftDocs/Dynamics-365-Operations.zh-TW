---
title: 設定最小-最大補貨流程
description: 此程序介紹如何設定使用最小/最大補貨策略的新補貨流程。
author: perlynne
ms.date: 10/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventFixedLocation, InventItemIdLookupSimple, WMSLocationIdLookup, WHSLocDirTable, InventLocationIdLookup, SysQueryForm, WHSWorkTemplateTable, WHSReplenishmentTemplates, UnitOfMeasureLookup, SysQueryTableLookUp, SysQueryFieldLookUp, SysRecurrence, WHSInventFixedLocation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f032f95377fdc6f8ec7fbbfa7aadab8fc448be5d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449040"
---
# <a name="set-up-a-min-max-replenishment-process"></a>設定最小-最大補貨流程

[!include [banner](../../includes/banner.md)]

此程序介紹如何設定使用最小/最大補貨策略的新補貨流程。 當庫存低於最低水準時，將建立工作以在此位置補貨。 該程序還介紹如何使用固定揀貨位置來允許補貨，即使庫存低於最低水準，以及如何使用批次作業定期執行補貨流程。 這些工作通常由倉庫經理執行。 您可以使用下方的範例值在 USMF 示範資料公司中執行此程序，也可以使用您自己的資料執行它。 如果您使用自己的資料，請確保您有為倉庫管理流程啟用的倉庫。


## <a name="create-a-fixed-picking-location"></a>建立固定揀貨位置
1. **移至瀏覽窗格 > 模組 > 倉庫管理 > 設定 > 倉庫 > 固定位置**。 這是最小-最大補貨的選擇性工作，但如果您使用固定揀貨位置，即使庫存低於最低水準，這也允許對存貨進行補貨，因為系統可以確定哪些品項需要補貨，即使沒有任何剩餘。
2. 按一下 **新增**。
3. 在 **項目號碼** 欄位中，輸入或選擇一個值。 如果您使用 USMF，則可以選取品項 A0001。  
4. 在 **站點** 欄位中，輸入或選取一個值。 如果您使用 USMF，則可以選取站點 2。  
5. 在 **倉庫** 欄位中，輸入或選取一個值。 如果您使用 USMF，則可以選取倉庫 24。  
6. 在 **位置** 欄位中，輸入或選取一個值。 如果您使用 USMF，則可以選取 CP-003。  
7. 關閉頁面。

## <a name="create-a-replenishment-location-directive"></a>建立補貨位置指令
1. 移至 **倉庫管理 > 設定 > 位置指令**。 位置指令用於確定在補貨流程中應從何處揀貨。
2. 在 **工單類型** 欄位，選取 [補貨]。
3. 在 **動作窗格** 上，按一下 **新增**。
4. 在 **名稱** 欄位中，輸入一個值。
5. 在 **工作類型** 欄位中，選取 [揀貨]。
6. 在 **站點** 欄位中，輸入或選取一個值。 如果您使用 USMF，則可以選取站點 2。  
7. 在 **倉庫** 欄位中，輸入或選取一個值。 如果您使用 USMF，則可以選取倉庫 24。  
8. 按一下 **儲存**。
9. 在 **行** 區段，點選 **新增**。
10. 在清單中，標記所選資料列。
11. 在 **數量** 欄位中，輸入一個數字。 例如，您可以將其設定為 9999。  
12. 選取 **允許拆分** 核取方塊。 如果您選擇此選項，工作建立流程將允許將工作行數量拆分到多個位置。  
13. 選取 **儲存**。
14. 在 **位置指令動作** 部分，點選 **新增**。
15. 在清單中，標記所選資料列。
16. 在 **名稱** 欄位中，輸入一個值。
17. 點選 **儲存**。
18. 在 **動作窗格** 上點選 **編輯查詢**。 您可以編輯此查詢以新增限制，以便在補貨流程中選擇庫存。 例如，可以是只應從倉庫的散裝區域使用庫存。
19. 點選 **確定**。
20. 關閉頁面。

## <a name="create-a-replenishment-work-template"></a>建立補貨工作範本
1. 移至 **倉庫管理 > 設定 > 工作 > 工作範本**。 工作範本用於指引系統必須如何建立最小/最大補貨工作。 至少必須有一個用於揀貨和放置的工作範本行。 在填寫完所有必要的資訊之前，工作範本將顯示無效。 
2. 在 **工單類型** 欄位，選取 [補貨]。
3. 在 **動作窗格** 上，按一下 **新增**。
4. 在 **工作範本** 欄位輸入值。
5. 點選 **儲存**。
6. 在 **工作範本詳細資料** 中，選取 **新增**。
7. 在 **工作類型** 欄位中，選取 [揀貨]。
8. 在 **工作類別識別碼** 欄位中，輸入或選擇一個值。 這應該是與補貨相關的工作類別。 如果您正在使用 USMF，則選取 [補貨]。  
9. 在 **工作範本詳細資料** 中，選取 **新增**。
10. 在清單中，標記所選資料列。
11. 在 **工作類型** 欄位中，選取 [放置]。
12. 在 **工作類別識別碼** 欄位中，輸入或選擇一個值。
13. 點選 **儲存**。
14. 關閉頁面。

## <a name="create-a-new-replenishment-template"></a>建立新的補貨範本
1. 移至 **倉庫管理 > 設定 > 補貨 > 補貨範本**。 補貨範本用於定義品項和數量以及補貨位置。
2. 在 **動作窗格** 上，按一下 **新增**。
3. 在 **補貨範本** 欄位輸入值。 為範本命名以表明它用於最小/最大補貨。  
4. 在 **描述** 欄位中，輸入一個值。
5. 選取 **允許波次需求使用未預留的數量** 核取方塊。 如果選擇此選項，將啟用波次需求補貨消耗與最小/最大補貨相關的數量。 例如，如果沒有立即處理最小/最大補貨工作，為避免建立不必要的需求補貨工作，這可能會很實用。
6. 在 **補貨範本詳細資料** 中，選取 **新增**。
7. 在 **序號** 欄位中輸入數字。
8. 在 **描述** 欄位中，輸入一個值。
9. 在清單中，標記所選資料列。
10. 在 **補貨單位** 欄位中，輸入或選取一個值。 例如，選取 pcs。 此設定是強制性的。 它允許比對此範本中為最小和最大庫存水準指定的單位，指定補貨工作的不同度量單位。
11. 在 **工作範本** 欄位中，輸入或選擇一個值。 選擇您之前建立的工作範本。  
12. 在 **最小數量** 欄位輸入數字。 選擇應觸發補貨的最小數量。 例如，將此項設定為 50。 如果在固定位置補貨，且 **在空的固定位置比貨** 選項設定為 [是]。 基於效能原因，還建議選取 **僅在固定位置補貨** 選項。
13. 在 **最大數量** 欄位輸入數字。 例如，將此設定為 100。  
14. 在 **單位** 欄位中，輸入或選擇一個值。 為最小和最大數量指派單位。 例如，將此設定為 pcs。  
15. 選取 **在空的固定位置補貨** 核取方塊。 選取此核取方塊以在固定位置為空時補貨。 否則，只會在有現有數量的位置補貨。
16. 選取 **僅在固定位置補貨** 核取方塊。
17. 點選 **選取產品**。 這是定義應補貨哪些產品的位置。 如果已選取 [固定揀貨位置] 選項，您還需要在此查詢中定義位置。 可使用變型查詢和產品型查詢。
18. 選取 **品項** 資料列。
19. 在 **條件** 欄位中，輸入一個值。 選取應在固定位置補貨的品項。 例如，鍵入 A* 可選擇所有以 A 開頭的品項編號。
20. 選點 **新增**。 新增位置實體 (除非它已經存在)，以便將補貨工作限制在倉庫特定區域內的固定揀貨位置。
21. 在清單中，標記所選資料列。
22. 將 **資料表** 欄位設定為 [位置]。
23. 在 **欄位** 欄位，選取 [位置設定檔識別碼]。
24. 在 **準則** 欄位中，輸入或選取一個值。
25. 選取 **確定**。
26. 關閉頁面。

## <a name="set-the-replenishment-process-to-run-as-a-batch-job"></a>設定補貨流程以將其作為批次作業執行
1. 移至 **倉庫管理 > 補貨 > 補貨**。 補貨頁面可讓您設定補貨作為批次作業執行，或要求手動啟動補貨。
2. 點選 **篩選**。
3. 在清單中，標記所選資料列。
4. 在 **準則** 欄位中，輸入或選取一個值。
5. 選點 **確定**。
6. 展開 **在背景執行** 區段。
7. 將 **批次處理** 選項設為 [是]。
8. 點選 **重複執行**。
9. 選取 **無結束日期** 選項。
10. 設定 **重複執行模式**。 例如，選取 [天數]。  
11. 點選 **確定**。
12. 選取 **確定**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]