---
title: 維護計劃
description: 本主題說明資產管理中的維護計畫。
author: johanhoffmann
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectType, EntAssetCounterType, EntAssetWorkOrderLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c74505c1771354aba42ddd9df2b7eaff8f5bc4653675244be99c4ef8afa73f6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446889"
---
# <a name="maintenance-plans"></a>維護計劃

[!include [banner](../../includes/banner.md)]

維護計劃定義了何時對資產執行預先計劃的預防性維護作業。 維護計劃可以與資產、資產類型、機能位置或機能位置類型相關，但首先您要建立要在公司中使用的維護計劃。

一個維護計畫可以有多個維護計畫明細。 維護作業類型和間隔是在維護計畫明細中指定的。 維護計畫明細類型有兩種：

- 時間
- 計數器

「時間」類型的維護計劃明細用於以固定時間間隔為基礎的週期性計劃性維護。 「計數器」類型的維護計劃明細是用於根據資產計數器登記的計劃性維護或反應性維護。 維護計畫可能包括兩種類型的數個維護計畫明細。

>[!NOTE]
>如果沒有為資產上的計數器類型登記計數器值，則維護計畫明細會被省略。

首先，您會建立預防性維護作業所需的維護計畫，並選擇應與每個維護計畫相關的資產類型、資產、機能位置類型，和機能位置。 之後，如果需要，您還可以將維護計劃新增到資產或機能位置，這將在 **所有資產** \> 選擇資產 \> **資產維護計劃** FastTab，或 **所有機能位置** \> 選擇機能位置 \> **維護計劃** FastTab 中完成。

如果您將維護計劃新增到資產類型或機能位置類型，則代表當您使用這些資產類型或機能位置類型建立新資產或機能位置時，資產或機能位置將自動新增到維護計劃中。 與維護計劃的關係的開始日期將是目前日期，可能需要調整。

## <a name="set-up-maintenance-plans"></a>設定維護計畫

本節介紹如何設定維護計劃明細並提供如何使用它們的範例。

1. 前往 **資產管理 \> 設定 \> 預防性維護 \> 維護計劃**。

1. 選擇 **新增** 以建立新順序。

1. 將識別碼插入 **維護順序** 欄位，並在 **名稱** 欄位插入名稱。

1. 在 **計劃日期** 欄位中，插入可以對維護計畫進行規劃的開始日期。 請註意，以時間為根據的維護計畫明細可能有其他計畫日期。

1. 在 **使用中** 切換按鈕選擇「是」以啟動維護計畫。

    >[!NOTE]
    >如果您停用維護計劃，則在您執行排程維護計劃作業時，不會在維護排程中建立排程張貼。

1. **容差延後天數** 和 **容錯提前天數** 欄位與維護計劃明細相關，其中 **隱藏重疊的維護作業** 核取方塊已選取 (參見步驟 17)。 「容差」欄位會用於延長間隔天數，如果多個維護計劃重疊，則在維護計劃排程期間會將最全面/最大的作業建立為維護排程明細，而在維護計劃排程期間，更頻繁、重疊的作業會被省略。 在 **容差延後天數** 欄位中插入天數，例如「2」。

1. 如果您已在 **容差延後天數** 中插入了值，也在 **容錯提前天數** 欄位中插入了天數，例如「2」。

    >[!NOTE]
    >此步驟和上一步中描述的範例，代表如果多個維護計劃明細重疊，並且已為一或多筆明細選取了 **隱藏重疊的維護作業**，省略維護計劃明細的時間延長至總共五天 (維護排程明細上的預計開始日期 *和* 兩天前 *和* 該日期後兩天)。

1. **詳細資料** FastTab 上的 **詳細資料** 群組中的欄位，顯示了在維護計劃上設定的維護計劃明細數量，以及與維護計劃相關的資產和機能位置的數量。

1. 在 **明細** FastTab 上，選擇 **新增時間明細** 或 **新增資產計數器明細** 以建立新的維護計劃明細。

1. 在 **工單描述** 欄位插入明細描述。 該描述會轉移到相關的工單。

1. 在 **維護作業類型** 欄位中，選取維護計劃明細相關的作業類型。

1. 在 **維護作業類型變體** 和 **工種** 欄位中，選擇與維護工作類型相關的變體和工種。

1. 在 **幾天內完成** 和 **數小時內完成** 欄位中，您可以天或小時為單位插入預期的結束日期。 預計結束日期是相對於預期開始日期插入的，此開始日期是在建立維護計劃明細時計算的。 例如，您可以在 **幾天內完成** 欄位插入「7」，以指示相關作業應在預期開始日期後的一周內完成。

1. 在 **間隔類型** 欄位中，選擇要在維護計劃明細上使用的間隔類型，例如「重複…」或「一次…」。 請參閱以下[間隔類型概觀](#interval-types)資料表以取得間隔類型和明細類型之間的關係描述。

1. **期間** 欄位僅與以時間為基礎的明細類型有關。 選擇與週期頻率相關的周期類型。

1. 在 **期間頻率** 欄位中，插入該明細應用於規劃預防性維護作業的次數。 範例：如果您建立了「計數器」類型的明細，並且您的計數器是生產數量，而您在此欄位中插入數字「20000」，則每次您預期要生產 20,000 多個品項時，在預防性維護排程期間都會建立新的維護序列明細。

1. **隱藏重疊的維護作業** 核取方塊與根據時間和根據計數器的明細類型相關。 選取該核取方塊可刪除在同一日期建立的維護排程分錄。 例如，如果您建立了 1 個月的檢驗明細、6 個月的檢驗明細和 1 年的檢驗明細，這就有相關性。 對於 1 年期的檢驗，您只希望完成該檢驗，而不是其他兩次檢驗，這也符合時間範圍。 為了正確設定此範例，您會將 1 年檢驗明細設定為第一筆明細，將 6 個月明細設定為第二筆明細，將 1 個月明細設定為第三筆明細，然後為 1 個月和 6 個月明細選擇 **隱藏重疊的維護作業** 的核取方塊。 這樣可以確保在達到 1 年標記時，省略 1 個月和 6 個月的檢驗，並且僅為 1 年檢驗明細建立維護排程明細。

    >[!NOTE]
    >此步驟中描述的範例顯示，包含最多工作且不經常執行的最全面作業，應始終作為第一筆明細而插入。 然後按頻率順序將更頻繁的作業作為單獨的明細插入，將最頻繁的作業放在清單的底部。

1. **計數器** 欄位僅與以計數器為基礎的明細類型有關。 選取用於明細上的計數器類型。 如果計數器類型在相關資產上未啟用，則省略維護計劃明細。

1. **資產計數器時界 (以天為單位)** 欄位僅與根據計數器的明細類型有關。 插入一個數字，該數字定義在完成維護計劃排程時檢查多少天的回溯計數器登記。 這表示著資料 (現有計數器登記) 用為計算判斷建立多少維護排程明細趨勢的基礎有多遠。

    >*範例：* 如果預計每月進行一次計數器登記，您可以在此欄位中插入數字「365」，因為維護計劃排程將一律以過去 12 個月為根據，因此會根據過去一年的趨勢建立維護排程明細。 另一方面，如果您在此欄位中插入數字「10」，您預期計數器登記的頻率會更高，例如每天一次。 這代表著，在您安排維護計劃時，過去 10 天的計數器登記將用作安排維護排程明細的基礎。

1. **計劃日期** 欄位僅與以時間為基礎的明細類型有關。 如果維護計劃明細的計劃日期與整個維護計劃不同，請在明細上的 **計劃日期** 欄位選擇一個日期。

1. 在 **服務等級** 欄位中，您可以選擇工單服務等級作為維護計劃明細的進一步分隔 - 以用作工單的服務等級。

1. 如果您希望在安排維護計劃時，根據選定的維護計劃明細自動建立工單，請選擇 **自動建立** 核取方塊。

1. 如果您選擇了 **自動建立** 核取方塊，您可以在 **工單類型** 欄位為自動建立的工單選擇一種工單類型。 如果您選擇了 **自動建立** 核取方塊，並且您沒有在此欄位中選擇工單類型，則在 **資產管理 \> 設定 \> 資產管理參數 \> 工單** 連結 \> **預防性工單類型** 欄位中選定的工單類型會被使用。

1. 使用 **季節起始時間** 和 **季節結束時間** 欄位，以在 12 個月的期間內建立重複的以時間為基礎的維護計劃明細。 *範例：* 用於維護綠地的設備需要在每個春天在預定的時間內進行維修。 在 **季節起始時間** 欄位中插入要重複期間的開始日期。

1. 在 **季節結束時間** 欄位中插入要重複期間的結束日期。

1. 在 **產生的期間** 欄位中，顯示目前要重複的期間。 目前週期過去後，您開始了新的一年，此欄位中顯示的週期將更新以反映重複序列中的下一個週期。

1. 在 **資產** FastTab 上，選擇應該與維護計劃相關的資產。

1. 在 **資產類型** FastTab 上，選擇應該與維護計劃相關的資產類型。

1. 在 **機能位置** FastTab 上，選擇應該與維護計劃相關的機能位置。 如果需要，您可以透過選擇相關的資產類型、製造商和型號來使設定更為具體。

1. 在 **機能位置類型** FastTab 上，選擇應該與維護計劃相關的機能位置類型。

>[!NOTE]
>在廠商保固範圍內的資產上手動建立工單時，會顯示一個對話方塊以使用者瞭解保固。 然後工單建立便可以取消。 對於自動建立的工單，將省略對保固關係的檢查。

<a id="interval-types"></a>

## <a name="interval-types-overview"></a>間隔類型概觀

| 間隔類型和描述 | 明細類型：時間 | 明細類型：計數器 |
|---|---|---|
| **間隔類型：從計劃日期開始重複** 計數從使用的計劃日期開始。 在您排程維護計劃時，會在達到間隔時建立維護計劃明細。 | 維護計劃明細上的 **計劃日期** 已使用。 如果該明細沒有選擇計劃日期，則會使用維護計劃的 **計劃日期**。 範例：如果數字「3」被插入 **期間頻率** 欄位，且 **週期** 欄位中已選擇「年」，則每 3 年會建立一次新的維護排程明細。 | 維護計劃的 **計劃日期** 已使用。 如果計數器已被更換，則以最晚更換日期作為計劃日期。 |
| **間隔類型：從開始日期開始重複** 計數會從資產關係的開始日期開始。 該日期會在 **所有資產** 詳細資料檢視 \> **資產維護計劃** FastTab \> **開始日期** 欄位中被選取，或在 **所有機能位置** 詳細資料檢視 \> **維護計劃** FastTab \> **開始日期** 欄位中被選取。 在您排程維護計劃時，會在達到間隔時建立一個維護計劃明細。 | 已使用資產或機能位置的維護計劃明細的開始日期。 如果該欄位為空白，則使用維護計劃的 **計劃日期**。 | 已使用資產或機能位置的維護計劃明細的開始日期。 如果該欄位為空白，則使用維護計劃的 **計劃日期**。 |
| **間隔類型：從上一個工單開始重複** 計數會從具有特定維護作業類型 / 維護作業類型變體 / 工種組合的資產上完成的最新工單的實際結束日期和時間開始。 該日期和時間會顯示在 **所有工單** 詳細資料檢視中的 **實際結束** 欄位。 | 在具有特定維護作業類型 / 維護作業類型變體 / 工種組合的資產上完成的工單實際結束日期和時間。 如果找不到已完成的工單，則改用上述「從開始日期開始重複」間隔類型中使用的日期之一。 | 在資產 *和* 維護作業類型 / 維護作業類型變體 / 工種組合上完成的工單的實際結束日期和時間。 已使用。 如果工單上的結束日期時間留空，則改用上述「從開始日期開始重複」間隔類型中使用的日期之一。 |
| **間隔類型：從計劃日期開始一次** 請參閱上面「從計劃日期開始重複」間隔類型的描述。 唯一的區別是這種間隔類型只能使用一次。 | 請參閱上方「從計劃日期開始重複」間隔類型的描述。 此間隔通常用於一次性維護或維修作業。 | 請參閱上方「從計劃日期開始重複」間隔類型的描述。 此間隔通常用於一次性維護或維修作業。 **註 1：** 僅在每次執行維護或維修作業都更換計數器時，此間隔類型才有關係。 如果出於某種原因在計劃的間隔結束之前更換了計數器，則作業的新時間會從計數器更換的時間開始計算。 **註 2：** 如果計數器在維護或維修作業完成時遭更換，則此間隔類型將用作上述「從計劃日期開始重複」間隔類型。 |
| **間隔類型：從開始日期開始一次** 請參閱上面「從開始日期開始重複」間隔類型的描述。 唯一的區別是這種間隔類型只能使用一次。 | 請參閱上方「從開始日期開始重複」間隔類型的描述。 此間隔通常用於一次性維護或維修作業。 | 請參閱上方「從開始日期開始重複」間隔類型的描述。 此間隔通常用於一次性維護或維修作業。 **註 1** 以上也適用於這種間隔類型。 **註 3：** 如果計數器在維護或維修作業完成時遭更換，則此間隔類型將用作上述「從開始日期開始重複」間隔類型。 |
| **間隔類型：一旦達到上限** 此間隔類型僅與計數器有關，並用於指示在維護計劃明細上設定的上限。 維護排程分錄將擁有計數器登記的預期開始日期和時間，這代表著這些分錄將使用預期開始日期等於或早於系統日期被建立。 | 不適用 | 計數器間隔指示了上限。 如果在您建立計數器登記時超出該限制，則維護排程明細會在您安排預防性維護時建立。 |
| **間隔類型：一旦達到下限** 此間隔類型僅與計數器有關，並用於指示在維護計劃明細上設定的下限。 維護排程分錄將擁有計數器登記的預期開始日期和時間，這代表著這些分錄將使用預期開始日期等於或早於系統日期被建立。 | 不適用 | 計數器間隔指示了下限。 如果在您建立計數器登記時越過該限制，則維護排程明細會在您安排預防性維護時建立。 |
| **間隔類型：從開始日期連結** 此間隔類型僅會建立一次維護排程明細。 維護計劃可以包含更多使用此間隔類型的維護計劃明細，並且這些明細是已連結的。 通常，您將建立一個僅包含此間隔類型明細的維護計劃。 維護排成明細是透過識別具有第一個預期開始日期和時間的維護計劃明細來建立的。 | 請參閱上方「從開始日期開始一次」的描述。 範例：您在維護計劃中為汽車的維修作業建立兩筆明細：一筆根據時間的明細，期間為 1 年，一筆根據計數器的明細，限制為 25,000 公里。 為首先達到的限制建立維護排程明細。 對於此明細類型，您會建立具有 1 年期間的明細。 | 請參閱上方「從開始日期開始一次」的描述。 範例：您在維護計劃中為汽車的維修作業建立兩筆明細：一筆根據時間的明細，期間為 1 年，一筆根據計數器的明細，限制為 25,000 公里。 為首先達到的限制建立維護排程明細。 對於此明細類型，您會建立具有 25,000 公里限制的明細。 建立兩個計數器明細的範例：您還可以設定一個包含兩個連結的、根據計數器明細的維護計劃，其中第一筆明細的生產數量限制為 10,000 件，第二筆與運轉 3,000 小時後需要維修的機器或工作中心相關的明細。 |
| **間隔類型：從上一個工單連結** 此間隔類型會在每個完成的工單後建立新的維護排程明細。 維護計劃可以包含更多使用此間隔類型的明細，並且這些明細是已連結的。 通常，您將建立一個僅包含此間隔類型維護計畫明細的維護計劃。 維護排成明細是透過識別具有第一個預期開始日期和時間的維護計劃明細來建立的。 | 此間隔類型運作方式基本上與上述「從開始日期連結」一樣。 唯一的區別是間隔類型所根據的日期。 使用的日期是在資產 *和* 維護作業類型 / 維護作業類型變體 / 工種組合上完成的最新工單的實際日期和時間。 | 此間隔類型運作方式基本上與上述「從開始日期連結」一樣。 唯一的區別是間隔類型所根據的日期。 使用的日期是在資產 *和* 維護作業類型 / 維護作業類型變體 / 工種組合上完成的最新工單的實際日期和時間。 |
| **間隔類型：根據彙總值重複 (僅限計數器)** 執行維護計劃時，每次資產計數器的累計值達到週期頻率，或週期頻率的偶數倍時，將建立一個計劃維護明細。 (週期頻率會在維護計劃明細上定義。)<p>有關如何啟用和使用此功能的更多資訊，請參閱本主題後面的[根據計數器的維護增強功能](#counter-based-maintenance)一節。 | 不適用 | **範例：** 為資產 AK-101 設定一個小時計數器。 資產計劃明細也為資產進行了設定。 這筆明細的區間類型是 *根據彙總值重複 (僅限計數器)*，週期頻率為 *1000*。 執行維護計劃時，當計數器的彙總值超過 1,000 小時，將產生排程維護明細。 然後，當計數器的彙總值超過 2,000 小時，將產生另一個排程維護明細，每增加 1,000 小時便以此類推。 |
| **間隔類型：根據彙總值觸發一次 (僅限計數器)** 執行維護計劃時，資產計數器的累計值達到維護計畫明細定義的週期頻率時，將建立一個計劃維護明細。<p>有關如何啟用和使用此功能的更多資訊，請參閱[根據計數器的維護增強功能](#counter-based-maintenance)一節。 | 不適用 | **範例：** 為資產 AK-101 設定一個小時計數器。 資產計劃明細也為資產進行了設定。 這筆明細的區間類型是 *根據彙總值觸發一次 (僅限計數器)*，週期頻率為 *1000*。 執行維護計劃時，當計數器的彙總值超過 1,000 小時，將產生排程維護明細。 |

>[!NOTE]
>為根據時間的維護計劃明細建立維護排程明細時，預期時間一律會在該日的開始。 對於根據計數器的維護計劃明細，預期時間可以是一天中的任何時間。

您將在下面找到設定根據時間和根據計數器的維護計劃明細的範例：

**範例 1 - 根據時間的維護計劃明細：** 潤滑作業可以固定間隔設定，每週發生一次。 為達成此目的，請在 **間隔類型** 欄位選擇「從計劃日期開始重複」。 請參閱下圖範例。

![以固定間隔 (每週發生一次) 設定的維修作業。](media/02-preventive-maintenance.png "以固定間隔 (每週發生一次) 設定的維修作業")

**範例 2 - 根據時間的維護計劃明細：** 檢查作業可以設定為大約每週執行一次。 為達成此目的，請在 **間隔類型** 欄位選擇「從上一個工單開始重複」。 請參閱下圖範例。

![設定為大約每週進行一次的檢查作業。](media/03-preventive-maintenance.png "設定為大約每週進行一次的檢查作業")

**範例 3 - 根據計數器的維護計劃明細：** 下圖顯示了一個時數計數器，每經過 250 小時，就會為建立一個新的維護排程明細。 此根據計數器的明細間隔類型是「從開始日期開始重複」。 該開始日期是在 **所有資產** 詳細資料檢視 \> **資產維護計劃** FastTab \> **開始日期** 欄位中被選取，或在 **機能位置** 詳細資料檢視 \> **維護計劃** FastTab \> **開始日期** 欄位中的相關資產開始日期。 這是一個 *預防性* 維護計劃的範例，因為每次達到閾值 (+ 250) 時都會自動建立維護排程明細。

![定期建立維護排程明細的小時計數器。](media/04-preventive-maintenance.png "定期建立維護排程明細的小時計數器")

**範例 4 - 根據計數器的維護計劃明細：** 下圖顯示了測量煞車片磨損狀況時減少的計數器值。 當在煞車片上建立低於 20 公釐的計數器登記時，一筆維護排程明細將被建立。 此根據計數器的明細間隔類型是「一旦達到下限」或「從上次開始日期開始一次」。 這是 *反應性* 維護計劃的一個範例，因為在記錄到 20 公釐以下的測量值之前不會建立維護排程明細。

![測量煞車片磨損時減少的計數器值。](media/05-preventive-maintenance.png "測量煞車片磨損時減少的計數器值")

**範例 5 - 根據計數器的維護計劃明細：** 下圖顯示了一個閾值為攝氏 -18° 度的計數器。 當在攝氏 -18° 度以上進行計數器登記時，會建立一筆維護排程明細。 此根據計數器的明細間隔類型是「一旦達到上限」。 這是 *反應性* 維護計劃的一個範例，因為在記錄到高於攝氏 -18° 以上的測量值之前不會建立維護排程明細。

![閾值為攝氏 -18° 度的計數器。](media/06-preventive-maintenance.png "閾值為攝氏 -18° 度的計數器")

- 在您建立新資產，並且該資產使用與維護計劃相關的資產類型時，維護計劃會在 **所有物件 \> 資產維護計劃** FastTab 中自動插入。 同樣，在 **資產類型預設值** 中的 **維護計劃** FastTab 上，相關的維護計劃會自動插入。
- 如果您在 **維護計劃** 中新增或移除資產類型或機能位置類型，該變更只會反映在您進行變更後建立的新資產。
- 如果您在 **維護計劃** 中新增或移除資產或機能位置，該變更將自動在 **所有資產 \> 資產維護計劃** FastTab 中更新，或在 **所有機能位置 \> 維護計劃** FastTab 中更新。

下圖顯示了 **維護計劃** 頁面上的「卡車維修」維護計劃範例。

![卡車維修維護計劃範例。](media/07-preventive-maintenance.png "卡車維修維護計劃範例")

## <a name="add-a-maintenance-plan-to-an-asset"></a>為資產新增維護計劃

1. 前往 **資產管理 \> 通用 \> 資產 \> 所有資產** 或 **使用中資產**。

1. 選擇要設定維護計劃的資產並選擇 **編輯**。

1. 在 **資產維護計劃** FastTab 上，選擇 **新增明細** 以將維護計劃新增至資產。

1. 在 **維護計劃** 欄位中，選擇相關維護計劃。

1. 在 **開始日期** 欄位中，選擇可以完成預防性維護作業計劃的日期。 

1. 選擇 **儲存**。 **使用中** 欄位隨即自動更新。

下圖顯示了在 **所有資產** 頁面上為資產設定的維護計劃範例。

![在資產上設定的維護計劃範例。](media/08-preventive-maintenance.png "在資產上設定的維護計劃範例")

<a id="counter-based-maintenance"></a>

## <a name="counter-based-maintenance-enhancements"></a>根據計數器的維護增強功能

*根據計數器的維護增強功能* 功能介紹了以下機能：

- 在建立資產時自動插入具有 *0* (零) 值計數器的選項。 當您使用以計數器為基準的預測性維護時，此選項會很實用。 如果不使用 *根據計數器的維護增強功能*，則必須手動插入值為 *0* (零) 的計數器。
- 設定計數器的能力，以便在工單完成時可自動重設。 在您想根據自上次工單完成後的彙總值排程維護時，此功能很實用。
- 一種新類型的維護計劃間隔，名為 *根據彙總值重複 (僅限計數器)*。 每次彙總計數器達到特定值的倍數時，此類型都會觸發維護。 例如，可以每 10,000 小時觸發一次維護。 有關詳細資訊，請參閱本主題之前介紹的[間隔類型概觀](#interval-types)章節。
- 另一種新類型的維護計劃間隔，名為 *根據彙總值觸發一次 (僅限計數器)*。 在彙總計數器達到特定值時 (例如 8,000 小時)，此類型會觸發維護。 有關詳細資訊，請參閱[間隔類型概觀](#interval-types)章節。

### <a name="turn-on-the-counter-based-maintenance-enhancements-feature"></a>開啟根據計數器的維護增強功能

使用此功能之前，您必須先在系統中開啟。 管理員可利用[功能管理](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)設定檢查功能狀態，並開啟該功能。 在 **功能管理** 工作區，該功能會依以下方式列出：

- **模組：** *資產管理*
- **功能名稱：** *開啟根據計數器的維護增強功能*

### <a name="create-and-initialize-counters-when-an-asset-is-created"></a>資產建立時建立並初始化計數器

每次建立資產時，都可以自動建立會初始化為 *0* (零) 值的相關資產計數器，前提是您已設定系統並正確建立了資產。

1. 前往 **資產管理 \> 設定 \> 資產類型**。
1. 確認您擁有適用於您計劃的新資產的資產類型。 視需要建立資產類型。 確認在 **計數器** FastTab 上選擇了所有相關的計數器。
1. 前往 **資產管理 \> 設定 \> 資產類型\> 計數器**。
1. 對於每個相關的計數器，確認 **全部彙總** 欄位設為 *總和*。
1. 在 **所有資產** 頁面建立資產。
1. 將 **資產類型** 欄位設為您在步驟 2 中識別或建立的資產類型。
1. 視需要完成新資產的設定。
1. 前往 **資產管理 \> 查詢 \> 資產 \> 計數器**。 您應該能找到為您新資產設定的已初始化計數器。

> [!NOTE]
> 建立初始化資產計數器時，假設資產在新增到系統之前從未使用過。 首次執行維護排程時，該計算會使用日期和 *0* (零) 計數器值作為計算未來維護的基準。 如果資產在新增到系統時不是新資產，您可以手動調整計數器值，使其與實際計數器值相符。 如要調整計數器值，請在 **所有資產** 頁面打開相關資產，然後在動作窗格的 **資產** 索引標籤上，在 **預防性** 群組中，選擇 **計數器**。 在已選取資產的 **資產計數器** 頁面，視需要為初始計數器紀錄調整 **值** 欄位中的值。

### <a name="automatically-reset-a-counter-value"></a>自動重置計數器值

您可以將系統設定為每次相關工單達到選定狀態值時自動重設計數器。

1. 前往 **資產管理 \> 設定 \> 預防性維護 \> 維護計劃**。
1. 在清單窗格中，選擇維護計劃。 計數器重設將套用至使用此計劃的所有資產。
1. 在 **明細** 區段中，找到您要重設計數器的資產計數器明細，然後選擇該明細的 **重設計數器** 的核取方塊。 (資產計數器明細在 **計數器** 欄中有一個值。 該欄中指定的計數器，是將為相關資產重設的計數器。)
1. 前往 **資產管理 \> 設定 \> 工單 \> 生命週期狀態**。
1. 在清單窗格中，選擇應重設相關計數器的工單生命週期狀態。
1. 在 **一般** FastTab，將 **重設計數器** 選項設為 *是*。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]