---
title: 位置指令庫存揀貨時效
description: 本主題說明如何在揀貨期間使用先進先出 (FIFO) 和後進先出 (LIFO) 位置指令策略。
author: mirzaab
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile,WHSWorkTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 83f73052d1d9d8a29a80ce3cf1035a259cd92c17
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449121"
---
# <a name="location-directive-inventory-picking-aging"></a>位置指令庫存揀貨時效

[!include [banner](../includes/banner.md)]

本主題說明如何在揀貨期間使用先進先出 (FIFO) 和後進先出 (LIFO) 位置指令策略。 這些策略與為位置記錄的帳齡日期結合使用，以追蹤庫存首次進入倉庫的時間。 *位置指令庫存揀貨時效* 功能會使用位置上的日期來確定帳齡。 *倉庫位置狀態* 功能會根據牌照上的日期更新位置上的日期。

您可以使用先進先出與後進先出策略，以運送批次跟蹤項目和非批次跟蹤項目。 此功能對於非批次跟蹤庫存特別有用，在這些庫存中的到期日期不可用於分類。

當倉庫中首次收到或建立庫存時，系統會更新相關的牌照，以便目前日期顯示為帳齡日期。 然後，位置指令策略會使用此日期來識別倉庫中最舊或最新的庫存。 如果庫存被移動到牌照未追蹤的位置，則該位置本身會使用帳齡資訊進行更新，然後此資訊會由策略使用。

## <a name="turn-on-the-feature"></a>開啟功能

若您想要使用此功能，請在[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)依此順序啟用以下功能：

1. 倉庫位置狀態
1. 位置指令庫存揀貨時效

## <a name="feature-requirements"></a>功能要求

若要使用此功能，您必須將用於儲存庫存的每個 [位置設定檔](tasks/create-location-profile.md)的 **啟用位置狀態** 選項設定為 *是*。 如要為位置設定檔設定此選項，請前往 **倉庫管理 \> 設定 \> 倉庫 \> 位置設定檔**，然後選擇位置設定檔。 您可以在 **一般** FastTab 上找到該選項。

## <a name="feature-scenarios"></a>功能方案

本節提供的範例展示如何設定和使用 FIFO 和 LIFO 策略。

> [!TIP]
> 本節提供兩種方案，一種用於 FIFO，一種用於 LIFO。 本處提供的程序假設您將按順序執行這兩種方案。 我們建議您同時執行這兩種方案，以便您體驗兩種策略之間的差異。

### <a name="make-sample-data-available"></a>設定樣本資料為可用

要使用此處指定的範例記錄和值完成這些案例，您必須使用已安裝標準[示範資料](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md)的系統。 此外在開始之前，您必須先選擇 **USMF** 法律實體。

您還可以將這些案例作為指南，以在生產系統上使用功能。 但是，在這種情況下，請自行替換此處說明中的每個設定值。

### <a name="set-up-the-scenarios"></a><a name="demo-set-up"></a>設定方案

示範資料需要設定和庫存調整以支援方案。 按照以下步驟建立完成 FIFO 和 LIFO 方案所需的庫存資料。

1. 登入已安裝示範資料的系統，然後選擇 **USMF** 法律實體。
1. 移至 **倉庫管理 \> 設定 \> 倉庫 \> 位置設定檔**。
1. 在動作窗格上，選擇 **編輯**。
1. 在位置設定檔清單中，選擇 **FLOOR-05**。
1. 在 **一般** FastTab 上，將 **啟用位置狀態** 選項設為 *是*。
1. 選擇 **儲存**。
1. 前往 **倉庫管理 \> 設定 \> 位置指令**。
1. 在位置指令清單中，選擇 **63 揀貨貨櫃化**。
1. 選取 **編輯** 讓頁面進入編輯模式。
1. 在 **位置指令動作** FastTab 上，找到 **序號** 欄位設為 *1* 的明細，然後執行以下步驟之一：

    - 如果要設定 FIFO 方案，請變更 **策略** 欄位的值為 *位置帳齡 FIFO*。
    - 如果要設定 LIFO 方案，請變更 **策略** 欄位的值為 *位置帳齡 LIFO*。

1. 在 **位置指令動作** FastTab 上，選擇 **編輯查詢**。
1. 在查詢對話方塊中，在 **範圍** 索引標籤上選擇 **新增** 以新增明細，然後設定以下值：

    - **資料表：***位置*
    - **衍生資料表：** *位置*
    - **欄位：** *區域識別碼*
    - **條件：** *現場*

1. 選擇 **確定** 以套用設定並關閉查詢對話方塊。
1. 選擇 **儲存** 將變更儲存為位置指令。
1. 在行動裝置或在您電腦的 *Dynamics 365 for Finance and Operations - Warehousing* 應用程式中，請按照以下步驟從倉庫位置刪除現有庫存以支援方案：

    1. 使用適當的使用者識別碼與密碼登入至倉庫 *63*。
    1. 在主功能表中，選擇 **品質**。
    1. 在 **品質管理** 主功能表中，選擇 **報廢**。
    1. 在 **報廢** 頁面上，選擇 **LOC/LP** 欄位，然後輸入 *63\_ 1*。
    1. 選擇 **輸入** 或是 **確定**。
    1. 透過選擇 **輸入** 或 **確定**，以確認 **調整出去** 的 **報廢** 詳情。

    在牌照庫存為調出時，您會收到「工作已完成」訊息。

    這些步驟將庫存留在示範資料中的兩個位置。 每個位置都有不同的帳齡日期。 位置 *FL-001* 帳齡日期為 2017 年 4 月 15 日，且地點 *FL-002* 帳齡日期為 2017 年 1 月 29 日。 兩個位置都包含品項 *A0001*。

    若要檢視此資料，請前往 **庫存管理 \> 查詢和報告 \> 現有清單**，然後對倉庫進行篩選 *63* 和品項 *A0001*。 在 **位置** 欄位設為 *FL-001* 或 *FL-002* 的列中，選擇一條有正數 **實物庫存** 值的明細，然後在動作窗格上選擇 **交易**。 **實際日期** 欄位將顯示與前面提到的帳齡日期之一相對應的日期。

### <a name="scenario-1-set-up-and-use-fifo-location-aging"></a><a name="fifo-demo"></a>方案 1：設定和使用 FIFO 位置帳齡

FIFO 策略會尋找包含最早帳齡日期的位置，並根據該帳齡日期分配挑選。

1. 如果您還沒有這麼做，則此方案需要[準備樣本資料](#demo-set-up)。
1. 前往 **銷售和行銷 \> 銷售訂單 \> 所有銷售訂單**。
1. 選取 **新增**。
1. 在 **建立銷售訂單** 對話方塊中，設定以下值：

    - 在 **客戶** 快速索引標籤，設定 **客戶帳戶** 欄位為 *US-001*。
    - 在 **一般** FastTab 中，將 **倉庫** 欄位設為 *63*。

1. 選擇 **確定** 以建立銷售訂單並關閉對話方塊。
1. 此新的銷售訂單已開啟。 它會在 **銷售訂單明細** FastTab 上的格線中包含一個新的空白列。 在此訂單明細上，將 **品項編號** 欄位設為 *A0001*，**數量** 欄位則設為 *1*。
1. 在網格上方的 **庫存** 功能表上，選擇 **保留**。
1. 在 **保留** 頁面上，選擇 **保留批號**，以在選擇的倉庫庫存中預留此品項的訂購數量。
1. 關閉該 **保留** 頁面。
1. 在 **銷售訂單** 頁面上的動作窗格上，**倉庫** 索引標籤的 **動作** 群組中，選擇 **發佈到倉庫**。 您會收到提供資訊的訊息。 系統會建立一筆裝運，將它新增到一個新的裝載，並建立所需工作。
1. 在 **銷售訂單明細** FastTab 的 **倉庫** 功能表，選擇 **工作細節** 以打開為此銷售訂單建立的工作。 請注意在 **工作類型** 值為 *揀貨* 的明細會顯示一個 **位置** 值為 *FL-002*。 此位置包含具有最早帳齡日期 (FIFO) 的牌照。
1. 選擇 **倉庫 \> 裝運詳細資料**。
1. 在 **一般** FastTab 上，記下波次識別碼，以便在方案 2 中使用。

### <a name="scenario-2-set-up-and-use-lifo-location-aging"></a>方案 2：設定和使用 LIFO 位置帳齡

LIFO 策略會尋找包含最新帳齡日期的位置，並根據該帳齡日期分配挑選。 在方案 2 中，您將編輯方案 1 (FIFO) 的設定，並重新使用在該方案中建立的銷售訂單和波次。

1. 在您開始此方案之前，請設定並完成完整的 FIFO 方案，如[上一節](#fifo-demo)所述。 在此方案中，您將重新使用為該方案建立的波次和大部分設定。
1. 編輯 **63 揀貨貨櫃化** 位置指令，以便它可使用 *位置帳齡 LIFO* 策略，如[設定方案](#demo-set-up)程序的第一部分所述。

    接下來，您將修改在方案 1 中為銷售訂單建立的波次，以便使用 *位置帳齡 LIFO* 策略。

1. 前往 **倉庫管理 \> 出庫波次 \> 裝運波次 \> 所有波次**。
1. 選擇並打開包含您為 FIFO 方案建立的訂單波次。
1. 在動作窗格上，在 **工作** 索引標籤選擇 **取消** 以取消您為 FIFO 方案建立的工作。
1. 在動作窗格的 **波次** 索引標籤上，在 **波次** 群組中選擇 **處理**。
1. 當處裡完成時，在動作窗格的 **波次** 索引標籤的 **相關資訊** 群組中，選擇 **工作** 以開啟此波次已建立的工作。
1. 在 **工作** 頁面的 **概觀** 索引標籤上，應該會有兩筆明細。 選擇 **工作狀態** 欄位設為 *開啟* 的明細。
1. 請注意在 **工作類型** 值為 *揀貨* 的明細會顯示一個 **位置** 值為 *FL-001*。 此位置包含具有最新帳齡日期 (LIFO) 的牌照。

在這些方案中，您已瞭解位置帳齡策略如何將工作引導到具有最舊庫存或最新庫存的庫存位置，具體取決於所選策略。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]