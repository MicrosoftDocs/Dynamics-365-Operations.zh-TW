---
title: 倉庫工作的延遲處理
description: 本主題說明 Dynamics 365 Supply Chain Management 中，可以使倉庫工作放置作業延遲處理的功能。
author: Mirzaab
ms.date: 11/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-6-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f99e960ffe7ca383563cc49c2e0825592ef5de57
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449049"
---
# <a name="deferred-processing-of-warehouse-work"></a>倉庫工作的延遲處理

[!include [banner](../includes/banner.md)]

本主題說明 Dynamics 365 Supply Chain Management 中，為倉庫工作放置作業延遲處理的功能。

延遲處理功能，可以讓倉庫工作人員繼續進行其他工作，同時在背景處理放置作業。 當必須處理許多工作行並且工作人員可以讓該工作異步處理時，延遲處理很有用。 當伺服器可以臨機操作，或是遇到計劃外的時間增加時，增加的處理時間可能會影響使用者的效率，這時延遲處理也非常有用。

背景處理是通過使用 SysOperation 框架來實現的。 如需更多資訊，請參閱 [SysOperation 框架概覽](/dynamicsax-2012/developer/sysoperation-framework-overview)。

## <a name="configuring-the-work-processing-policies"></a>設定工作處理原則

若要使用延遲處理，您必須設定並使用工作處理原則。

原則在 **工作處理原則** 頁面上設定。 以下資料表說明該頁面的欄位。

| 欄位                           | 描述 |
|---------------------------------|-------------|
| 工作處理原則名稱     | 工作處理原則的名稱。 |
| 工單類型                 | 原則應用的工單類型。 |
| 作業                       | 使用原則處理的作業。 |
| 工作處理方法          | 處理工作明細的方法。 如果您將方法設定為 **即時**，該行為類似於沒有使用工作處理原則來處理該明細的行為。 如果方法設置為 **延遲**，則使用批次框架的延遲處理。 |
| 延遲處理閾值   | 一個值 **0** (零) 表示沒有閾值。 在這種情況下，則會盡可能使用延遲處理。 如果特定的閾值計算低於閾值，則會使用即時方法。 否則，如果可以使用，則使用延遲方法。 對於銷售和轉移相關的工作，閥值計算為正在處理工作與來源載入明細關聯的數量。 對於補充工作，閾值計算為正在補充的工作明細數量。 例如，通過設置閾值，銷售為 **5**，您可以確保，少於五個來源載入明細的較小工作，不會使用延遲處理，但較大的工作將使用延遲。 閥值只有在工作處理方法設定為 **延遲** 時才會生效。 |
| 延遲處理批次群組 |用於處理的批次群組。 |

若要延遲放置處理，則支持以下工單類型：銷售訂單、轉移訂單問題和補貨。

## <a name="assigning-the-work-creation-policy"></a>指派工作建立原則

可以在倉庫管理參數中指派工作建立原則。 也可以於個別倉庫層級中進行指派。 如果將原則指派給倉庫，則僅適用於為該倉庫建立的工作。 如果倉庫層級沒有指派原則，則會應用倉庫管理參數中的原則。

## <a name="viewing-the-deferred-put-processing-tasks"></a>查看延遲放置處理任務

您可以在 **延遲放置處理任務** 頁面查看延遲放置處理任務。

預設情況下，會顯示 **已完成** 的任務。

| 欄位            | 描述 |
|------------------|-------------|
| 狀態           | 工作狀態。 |
| 批次作業狀態 | 批次作業相關的狀態。 如果批次作業已處理，則批次歷史記錄會包含批次作業的記錄和資訊。 |

以下是可能狀態的解釋：

- **等待中** – 相關的批次作業，正在等待批次伺服器處理。
- **失敗** – 處理失敗。 可以使用 **處理延遲放置** 動作重新處理作業，或者使用 **取消延遲放置** 動作取消作業。
- **已完成** – 作業已完成。

## <a name="impact-on-closed-work-dates"></a>對非工作日的影響

當使用延遲放置處理時，非工作日期設定為延遲放置處理任務的創建日期/時間。 會使用非工作日，因為這是放置作業完成時的最佳預估時間。

## <a name="reprocessing-a-failed-task"></a>正在重新處理失敗的工作

您可以選擇頁面上的失敗的工作，然後選擇 **處理延遲放置**，以重新處理。 重新處理對應的情況，就像是使用者從行動裝置上完成放置，設定為立即處理一樣。

## <a name="canceling-failed-tasks"></a>取消失敗的工作

只有失敗的工作才可以取消。 取消任務時，您可以將其指派給新的使用者。 或者，該任務仍然可以指派給處理該工作的使用者。 取消對應的狀態，就像是工作重新回到行動裝置上，如同剛完成最後一步挑選步驟一樣，並且必須完成放置。 但是，使用者能夠確定該工作是「不同的」，因為它只有一個上架步驟，並且對應的位置，與第一個使用者處理工作所使用的最後放置位置一樣。

當工作取消後，工作不會再受到延遲放置處理的原因而遭到封鎖。 可以使用行動裝置對其進行重新處理。

工作取消時，會刪除工作記錄。

## <a name="configuring-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>設定行動裝置功能表，以跳過延遲處理原則

您可以設定行動裝置功能表項目，以便不使用延遲處理原則。 則工作會按照未使用延遲處理原則進行處理。 此功能可讓主管使用特定功能表，不使用延遲放置。 若要設定，請將 **延遲放置處理原則** 欄位設定為 **複寫設定並同步處理放置**。 

## <a name="restrictions-when-the-deferred-put-processing-isnt-applied"></a>未使用延遲放置處理時的限制

即使已經應用原則，也有幾種情況不會應用延遲放置處理。 這裡有些範例：

- 使用手動完成。
- 工作已自動完成。
- 已使用審核模板。


## <a name="monitoring-the-deferred-processing-tasks-from-the-outbound-work-monitoring-workspace"></a>從傳出工作監控工作區監控延遲處理任務

**傳出工作監控** 工作區有兩個圖格，可幫助您監控延遲放置處理任務：

- **延遲放置處理任務失敗** – 此圖格顯示失敗任務的數量。 如果有失敗的工作，倉庫經理必須重新處理，或是取消，因為不會自動重新處理。
- **等待中的延遲放置處理工作** – 此圖格顯示已在 **等待中** 狀態超過 10 分鐘的工作。 如果此圖格顯示數字，則可能表示批次處理過程中出現問題。 您可以手動處理 **等待中** 工作。 如果批次作業的工作，已於稍後處理完成，則只會顯示失敗，因為已經處理過。 不會有影響。

## <a name="deleting-completed-tasks"></a>刪除已完成的任務

您可以在頁面上選擇並刪除，以刪除以完成的延遲放置處理工作。

## <a name="additional-resources"></a>其他資源

- [手動庫存移動作業的延遲處理](deferred-processing-manual-inventory-movement.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]