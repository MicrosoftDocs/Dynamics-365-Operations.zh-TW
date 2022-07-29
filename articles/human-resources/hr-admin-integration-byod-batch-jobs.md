---
title: 最佳化的 BYOD 排程批次工作
description: 本主題說明如何在您使用 Microsoft Dynamics 365 Human Resources 搭配 Bring Your Own Database (BYOD) 功能時使效能達到最佳化。
author: andreabichsel
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: Platform update 36
ms.openlocfilehash: a2f110d105b8c04f07f219f7f11a57d24e00ce4a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452394"
---
# <a name="optimize-byod-scheduled-batch-jobs"></a>最佳化的 BYOD 排程批次工作


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明如何在您使用 Bring Your Own Database (BYOD) 功能時使效能達到最佳化。 更多有關 BYOD 資訊，請參閱[Bring Your Own Database (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)。

## <a name="performance-considerations-for-data-export"></a>資料匯出效能的考量因素

待實體發佈到目的地資料庫後，您可以使用 **資料管理** 工作區的匯出功能移動資料。 匯出功能讓您定義內含一個或多個實體的資料移動工作。 更多有關資料匯導出的資訊，請參閱[資料匯入和匯出工作概觀](../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)。

您可以使用 **匯出** 頁將資料以不同的確定目標資料格式匯出，例如逗號分隔值 (CSV) 檔案。 本頁也支援將 SQL 資料庫當作另一個目的地。

您可以建立含有多個實體的資料專案，並使用批次工作排定資料專案的執行時程。 如果您選取 **批次匯出** 選項，您可以安排定期執行資料匯出的時程。

為了有助於保存 BYOD 匯出的整體可靠性，請務必在新增多個實體到匯出專案時特別小心。 當您判定要新增到相同專案的實體數量時，請考慮使用下列參數：

- 實體的複雜性
- 每個實體的預期資料量
- 完成工作級匯出動作將需要的整體時間長度

為了達到最佳效能，請避免新增數百個實體到單一專案。 我們建議您建立多項工作，每項包含較少的實體。

## <a name="scheduling-byod-batch-jobs"></a>安排 BYOD 批次工作的時程

若要幫助減少對 Microsoft Dynamics 365 Human Resources 用戶的影響，請在晚上或下班後執行 BYOD 批次工作。 請務必檢查重複性批次工作的時區。 某些批次工作可能使用太平洋標準時間 (PST)。

為了幫助避免效能問題，請在為 BYOD 批次工作配置排程頻率時考慮下列因素：

- 完成每項批次工作所需的時間
- BYOD 資料的業務需求

將每項批次工作的頻率設定為數值，確保工作可在下次排程的執行時間之前完成。 請避免平行執行多項工作，因為這種方法會對人力資源的效能產生不利的影響。

為了達到最佳效能，請一直使用 **匯出** 頁上的 **批次匯出** 選項排程 BYOD 批次工作。 請避免在 **管理\>管理重複性資料工作** 排程重覆性匯出工作。

## <a name="incremental-export"></a>增量匯出

當您新增實體預備進行資料匯出時，您可以增量推送 (匯出) 或完整推送。 完整推送會從 BYOD 資料庫中的實體刪除所有既有的記錄。 接著它會插入人力資源實體的當前記錄集合。

若要增量推送，您必須在 **實體** 頁上為每個實體打開追蹤修訂模式。 更多資訊，請參閱[為實體啟用追蹤修訂模式](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)。

如果您選取增量推送，第一次推送務必一直是完整推送。 SQL 追蹤第一次完整推送的變更。 插入新記錄或更新或刪除記錄時，變更會反映在目的地實體中。

## <a name="time-outs"></a>逾時

以下是 BYOD 匯出的預設逾時標準：

- 截斷操作十分鐘
- BULK INSERT 操作一小時

量很大時，這些逾時設定可能不夠。 若要更新它們，請前往 **資料管理\>Framework 參數\>攜帶您自己的資料庫**。 這些逾時依公司情況而定，必須針對每間公司分開設定。

## <a name="known-limitations"></a>已知的限制

BYOD 功能的限制如下：

- 同步期間，您的資料庫不應該會有 Active Lock。 Active Lock 會導致寫入速度緩慢，甚至無法將資料匯出到 Azure SQL 資料庫。
- 您不能將複合式實體匯出到您自己的資料庫。 目前不支援複合式實體。 您必須匯出組成複合式實體的個別實體。 然而，您可以匯出同一個資料專案的兩個實體。
- 沒有唯一索引鍵的實體不能使用增量推送功能匯出。 您可能會面臨這項限制，尤其是當您嘗試從幾個現成的實體增量匯出記錄時。 由於這些實體原本設計用來啟用資料匯入功能，因此它們並沒有唯一的索引鍵。

## <a name="troubleshooting"></a>排除障礙

### <a name="incremental-push-doesnt-work-correctly"></a>增量推送無法正常工作

**問題：** 當實體發生完整推送時，您會在使用 **選取** 陳述句時在 BYOD 看到大量記錄集合。 然而，當您執行增量推送時，您只能在 BYOD 看到幾筆記錄。 似乎增量推送刪除所有記錄，只新增 BYOD 中變更的記錄。

**解決方案：** SQL 追蹤修訂資料表可能不在預期狀態。 在這種類型的情況下，我們建議您關閉實體的追蹤修訂模式，然後重新打開。 更多資訊，請參閱[為實體啟用追蹤修訂模式](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)。

### <a name="staging-tables-arent-clearing"></a>暫存資料表尚未清理

**問題：** 為專案使用暫存功能時，暫存資料表無法正確清除。 接著資料表的資料會繼續成長，導致效能問題。

**解決方案：** 七天的歷史記錄保存在暫存資料表裡。 超過七天的歷史資料會自動藉由 **匯入匯出暫存清理** 批次工作從暫存資料表清除。 如果這項工作卡住不動，資料表將無法正確清除。 重新啟動這項批次工作將繼續自動清除暫存資料表的流程。

## <a name="see-also"></a>也請參閱

[資料管理概觀](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[攜帶您自己的資料庫 (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[資料匯入和匯出作業概觀](../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[為實體啟用追蹤修訂模式](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
