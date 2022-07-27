---
title: 倉庫管理現有項目清理作業
description: 本主題介紹現有項目清理作業，該作業可識別和刪除相關但不需要的記錄，而有助於提高系統效能。
author: perlynne
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-04-03
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: b2bdfb7fa0c9c4d9e1f630a41357dc405f0082bc
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450042"
---
# <a name="warehouse-management-on-hand-entries-cleanup-job"></a>倉庫管理現有項目清理作業

[!include [banner](../includes/banner.md)]

用於計算現有庫存的查詢效能受所涉及表格中記錄數的影響。 有助於提高效能的一種方法就是減少資料庫必須考慮的記錄數。

本主題介紹現有項目清理作業，該作業會刪除 InventSum 和 WHSInventReserve 表中不需要的記錄。 這些表格會儲存針對倉庫管理處理而啟用的現有資訊。 (這些項目稱為 WHS 項目。) 刪除這些記錄可以顯著提高現有計算的效能。

## <a name="what-the-cleanup-job-does"></a>清理作業的用途

現有項目清理作業會刪除 WHSInventReserve 和 InventSum 表格中任何欄位值為 *0* (零) 的記錄。 這些記錄可以刪除，因為它們對於現有資訊沒有貢獻。 該作業僅刪除低於 **位置** 層級的記錄。

如果允許負實際庫存，則清理作業可能無法刪除所有相關項目。 造成這種限制的原因是，該作業必須允許一個牌照具有多個序號，而其中一個序號變為負數的這種特殊情況。 例如，當牌照有 +1 件的序號為 1，有 –1 件的序號為 2 時，系統在牌照層級的現有項目數為零。 對於這種特殊情況，作業會執行廣度優先刪除，亦即它會嘗試先從較低層級刪除。

## <a name="schedule-and-configure-the-cleanup-job"></a>排程和設定清理作業

現有項目清理作業位於 **庫存管理 \> 定期任務 \> 清理 \> 倉庫管理現有項目清理**。 使用標準作業設定可控制執行作業的範圍與排程。 此外，還提供以下設定：

- **如果以下天數後不更新即刪除** – 輸入該作業在刪除數量已降至零的現有項目之前應等待的最少天數。 使用此設定有助於降低刪除仍在使用中現有項目的風險。 如果您希望盡快進行清理，請輸入 *0* (零) 或將該欄位留空。
- **執行時間上限 (小時)** – 輸入清理作業的執行時間上限，以小時為單位。 如果在到達此時間上限前未完成作業，便會儲存目前為止已完成的工作，然後自行關閉。 此功能與具有高庫存使用量的實作特別相關。 在這些情況下，您應該安排作業在系統負載盡可能輕的時候執行。 如果您希望批次作業繼續執行直到完成，請輸入 *0* (零) 或將該欄位保留空白。 此設定僅在相關功能已[在您的系統中開啟](#max-execution-time)時才可供使用。

儘管您可以在正常工作時間執行該作業，但建議您在非工作時間執行。 透過這種方式，有助於防止若有使用者在正在使用清理中的記錄時可能會發生的衝突。

如果當另一個使用者正在使用某個項目的記錄時，作業嘗試刪除該記錄，則清理作業或使用者會發生鎖死錯誤。

當作業執行時，它的認可大小為 100。 換句話說，每刪除 100 次便會嘗試認可一次。 但是，由於某些刪除是以集為基礎的，因此可能會有同一個交易中會刪除超過 100 條記錄的情況。 因此，有時仍會發生鎖定升級。

## <a name="possible-user-impact"></a>可能的使用者影響

如果現有項目清理作業刪除指定層級 (例如牌照層級) 的所有記錄，使用者可能會受到影響。 在這種情況下，用於查看先前在牌照層級現有可用庫存的功能可能無法如預期般運作，因為相關的現有項目不再可用。 例如，在以下情況下可能會遇到這種情況：

- 在 **現有清單** 中，當使用者取消選取 **數量\<\> 0** 的條件，或選取 **尺寸顯示** 設定中的 **已關閉的交易** 條件時。
- 在過去期間的 **按庫存尺寸的實際庫存** 報告中，當使用者設定 **截至日期** 參數時。

但是，清理作業所提供的效能改善應該可以彌補功能方面的這些小損失。

## <a name="make-the-maximum-execution-time-setting-available"></a><a name="max-execution-time"></a>讓執行時間設定上限可用

**執行時間上限** 設定僅在 *倉庫管理現有項目清理作業的執行時間上限* 功能開啟時才可供使用。 從 Supply Chain Management 版本 10.0.25 開始，此功能預設開啟。 管理員可以開啟或關閉此功能，方法是搜尋 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區中的 *倉庫管理現有項目清除作業的執行時間上限* 功能。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]