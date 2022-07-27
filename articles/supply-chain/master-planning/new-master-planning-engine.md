---
title: 移轉到規劃最佳化以進行總體規劃
description: 本主題提供有關新總規劃引擎、規劃最佳化及從現有引擎移轉的資訊。
author: ChristianRytt
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: crytt
ms.search.validFrom: 2020-11-05
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8d3edeefca2e2194a8d5484afbfabf2091da4a1c1538d238351a5d389177ccfd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446760"
---
# <a name="migration-to-planning-optimization-for-master-planning"></a>移轉到規劃最佳化以進行總體規劃

[!include [banner](../includes/banner.md)]

已排程將內建的總規劃引擎淘汰 (已取代)。 Planning Optimization Add-in for Microsoft Dynamics 365 Supply Chain Management 正在取代它。 本主題提供有關對新部署和現有部署影響的資訊。 它包括與所需動作相關的資訊。

規劃最佳化讓總規劃計算在 Supply Chain Management 及其 Azure SQL 資料庫之外進行。 與規劃最佳化相關的益處包括在總規劃執行期間能提高效能，並將對 SQL 資料庫的影響降至最低。 因為即使在辦公期間也可以進行快速執行規劃，所以規劃人員可以立即對需求或參數的變化做出反應。

有關規劃最佳化的詳細資訊，請參閱[規劃最佳化概觀 ](planning-optimization/planning-optimization-overview.md)。

## <a name="obsolescence-of-the-existing-master-planning-engine"></a>現有的總規劃引擎已洶汰

Microsoft 正在淘汰內建的規劃引擎以支持規劃最佳化。 此變更會影響所有雲端環境。 內部部署不受影響。 在 10.0.16 版及更新版本中，如果您在未產生已規劃生產訂單的情況下執行內建總規劃，則會收到錯誤訊息。 但儘管出現錯誤消息，總規劃執行仍將成功完成。

有關淘汰內建規劃引擎的詳細資訊，請參閱 [Dynamics 365 Supply Chain Management 中的已刪除或已取代功能](../get-started/removed-deprecated-features-scm-updates.md)中的公告。

## <a name="migration-messages-and-exceptions"></a>移轉、訊息和例外狀況

執行內建總規劃引擎而不產生已規劃生產訂單的現有環境擁有者將收到一封電子郵件，其中提供有關例外狀況過程的詳細資料。 我們建議您與合作夥伴一起評估和規劃移轉至規劃最佳化。

如先前所述，在 10.0.16 版及更新版本中，如果您在未產生已規劃生產訂單的情況下執行內建總規劃，則會收到錯誤訊息。 此錯誤訊息包含與移轉相關的指南，以及要求例外狀況的說明。

### <a name="new-deployments"></a>新部署

規劃最佳化應視為雲端中所有新部署的預設總規劃引擎。 一般來說，規劃最佳化應該用於在總規劃期間不產生已規劃生產訂單的所有新部署。 如果新部署依賴規劃最佳化目前不支援的功能，您可以要求例外狀況，讓您可以繼續使用內建的總規劃引擎。

### <a name="existing-deployments"></a>現有部署

依賴總規劃的現有以雲端為基礎部署的擁有者應規劃移轉至規劃最佳化。 如果您的實作依賴規劃最佳化目前不支援的功能，您可以要求例外狀況，讓您可以繼續使用內建的總規劃引擎。

對於目前使用正在淘汰的總規劃程序的環境，Microsoft 會向環境管理員傳送一封電子郵件。此電子郵件將提供與移轉或要求例外狀況所需採取動作相關的資訊。

## <a name="the-exception-process"></a>例外狀況程序

如果您必須繼續使用內建總規劃引擎，您可以要求例外狀況，因為您的業務程序大幅依賴至少一項目前未在規劃最佳化中實作的功能。 有關可用功能的清單，請參閱[規劃最佳化適合度分析 ](planning-optimization/planning-optimization-fit-analysis.md)。

目前只有當您的總規劃程序未包括生產 (即由總規劃產生的已規劃生產訂單)，且您需要 10.0.15 版本之後的內建總規劃引擎時，規劃最佳化移轉的例外狀況才相關。

在所需功能可用後，Microsoft 將提供寬限期，直到例外狀況到期為止。 當所需功能可用且寬限期開始時，將通知環境管理員。

以下流程圖總結了本主題中提供的資訊，讓您快速瞭解是否應要求例外況。 如果您需要要求例外狀況，請填寫並提交[規劃最佳化移轉與例外狀況問卷](https://go.microsoft.com/fwlink/?linkid=2144962)。

![例外狀況流程圖。](media/exception-diagram.png "例外狀況流程圖")

> [!NOTE]
> 您只能為目前包含或將包含生產環境的租用戶要求例外狀況，而不是僅針對具有沙箱環境的租用戶。 如果您需要在基礎結構即服務 (IaaS) 沙箱環境中停用規劃最佳化例外狀況錯誤，請執行在[沙箱環境](#faq-sandbox)中提供的 SQL 查詢。

## <a name="frequently-asked-questions"></a>常見問題

### <a name="sandbox-environments"></a><a name="faq-sandbox"></a>沙箱環境

我可以在我的沙箱環境中使用內建的總規劃嗎？ 我需要例外狀況嗎？

**答：** 例外狀況通常與沙箱環境無關，因為規劃最佳化例外狀況錯誤不會防止內建總規劃引擎成功執行。 但是，如果錯誤訊息讓您感到不安，您可以在 IaaS (不是 Service Fabric) 沙箱環境中停用它，方法是在您的資料庫上執行以下查詢：

```sql
-- Insert or update an enabled flight:
DECLARE @flightName NVARCHAR(100) = 'ReqPlanningOptimizationExceptionToggle';
IF NOT EXISTS (SELECT TOP 1 1 FROM SysFlighting WHERE flightName = @flightName)
    INSERT INTO SYSFLIGHTING(FLIGHTNAME,ENABLED, FLIGHTSERVICEID,PARTITION)
    SELECT @flightName, 1, 12719367,RECID FROM DBO.[PARTITIONS];
ELSE
    UPDATE SysFlighting SET enabled = 1, flightServiceId = 12719367 WHERE flightName = @flightName;
```

### <a name="on-premises-environments"></a>內部部署環境

我的環境是內部部署。 我需要例外狀況嗎？

**答：** 否。 內部部署環境不需要例外狀況。 您可以繼續使用內建的總規劃。 如果需要執行任何動作，您的環境管理員將收到通知。

### <a name="production-scenarios"></a>生產案例

我們使用已規劃生產訂單，但我擔心升級到版本 10.0.16 時會發生的狀況。 我應該採取什麼動作嗎？

**答：** 您不必擔心。 您在 10.0.16 版中可以繼續使用內建的總規劃。 但是，建議您評估是否可以從目前功能開始移轉到規劃最佳化。 此外也建議您隨時瞭解新功能。

### <a name="email-from-microsoft"></a>來自 Microsoft 的電子郵件

我們的環境管理員收到來自 Microsoft 的電子郵件。 這封電子郵件指出我們應該移轉到規劃最佳化或要求例外狀況。 我需要採取任何動作嗎？

**答：** 是。 除非您按照電子郵件中的說明進行操作，否則您的環境將受到影響。 您可以在指定日期之前移轉到規劃最佳化，也可以使用電子郵件中的連結要求例外狀況。 此連結會開啟一份問卷。 完成並提交此問卷後，您將透過電子郵件收到回覆。 儘管此程序是手動的，但 Microsoft 會嘗試在提交問卷後的一週內回覆。

### <a name="error-messages"></a>錯誤訊息

我使用的是 10.0.16 或更新版本，在執行總規劃時收到以下錯誤訊息。 總規劃是否遭到阻止？

> 您收到此錯誤訊息是因為內建的總規劃引擎用於規劃最佳化支援的案例。 現在您應該移轉到規劃最佳化，因為目前的內建總規劃將被取代。 請注意，此總規劃執行確實成功完成。
>
> 如果您的移轉強烈依賴待決功能，則可以要求可繼續使用內建總規劃引擎的例外狀況。
>
> 請完成以下問卷以開始使用，如果相關，則要求移轉至規劃最佳化的例外狀況。

**答：** 否，總規劃未遭到阻止。 您的總規劃執行已成功完成，您可以按照平常的方式使用結果。 但是，為避免在未來的總規劃執行期間收到此錯誤消息，您必須立即移轉到規劃最佳化，或使用錯誤訊息中的連結要求例外狀況。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
