---
title: 維護停機時間活動
description: 本主題說明如何使用維護停機時間，來瞭解在特定期間內對特定資產執行維護作業所需的產能。
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenanceStopCopy, EntAssetMaintenanceStopObject, EntAssetObjectProductionStop, EntAssetProductionStopType, EntAssetMaintenanceStop
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0e6168033afb97c6f4f1b8466801a6f16332df82a039927ec1b45e03aa3694b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446754"
---
# <a name="maintenance-downtime-activities"></a>維護停機時間活動

[!include [banner](../../includes/banner.md)]

維護停機時間是用於瞭解在特定期間內對特定資產執行維護作業所需的產能。 例如，您可以在生產站點 02 的生產廠房 29-A 中，為生產線 10 建立維護停機時間登記。 維護停機時間登記具有開始和結束時間，此期間表示與維修停止相關的資產不可用於生產的期間。

**維護停機時間活動** 是指定期間內相關資產的維護排程明細和工單維護作業的概觀。 與工單維護作業相關的明細，都有一個在維護停止期間內的預期開始日期。 您可以擷取實用的資訊，並對計劃的維護作業進行調整：

- 瞭解生產設備 (資產) 所需的停工期。  
- 瞭解按能力 (負責的維護工作者群組或維護工作者) 分組的計劃性維護 (工時)，例如電工、鐵工，或其他維護工作群組執行計劃性維護工作時所需的產能負載。  
- 調整與資產相關的維護排程明細或工單維護作業，例如變更明細的預期開始和結束時間，或選擇其他維護工作者，以最佳化維護工作者和維護工作者群組的工作流程。

在維護停機時間登記中選擇資產後，與使用中工單相關的所有開啟的維護排程明細和工單維護作業，都包含在維護停機時間登記中。

## <a name="maintenance-downtime-activities"></a>維護停機時間活動

按一下 **資產管理** > **通用** > **維護停機時間活動** > **所有維護停機時間活動** 以打開所有維護停機時間活動的清單，並查看與活動相關的一些資訊。 按一下 **維護停機時間活動** 欄中的連結，以打開詳細資料檢視。 下圖顯示 **維護停機時間活動** 的清單範例。

![圖 1。](media/19-preventive-maintenance.png)


## <a name="create-a-maintenance-downtime-activity"></a>建立維護停機時間活動

1. 按一下 **資產管理** > **通用** > **維護停機時間活動** > **所有維護停機時間活動** 或 **使用中維護停機時間活動**。

2. 按一下 **新增**。

3. 將識別碼插入 **維護停機時間活動** 欄位，並在 **名稱** 欄位插入名稱。

4. 在 **開始日期/時間** 與 **結束日期/時間** 欄位插入維護停止期間。

5. 在 **維護停機活動資產** FastTab 上 > 按一下 **新增明細**，以將資產一次新增到維護停機時間活動中。

6. 在新增所有資產後，按一下 **儲存**。 下圖顯示了具有相關資產和維護作業的維護停機活動範例。

7. 與所選資產相關的工單維護作業，和開啟的維護排程明細，會顯示在 **產生的工單維護作業** 和 **維護排程明細** FastTab。 在 **一般** FastTab > **工單** 群組 > **維護預測時數** 欄位，和 **一般** FastTab > **維護排程** 群組 > **維護預測時數** 欄位中，您會看到為工單維護作業和維護排程明細預測的總時數。

下圖顯示 **維護停機時間活動** 的詳細資料檢視範例。

![圖 2。](media/20-preventive-maintenance.png)

>[!NOTE]
>如果您在建立維護停機時間活動後，建立了新的工單或維護排程明細，則與所選資產相關的工單維護作業和維護排程明細會自動更新。 例如，如果您在維護停機時間活動建立的兩天後，對相關資產安排維護計劃或維護回合，則新的維護排程明細會自動新增到維護停機時間活動中。

8. 在 **所有維護停機時間活動** > **維護停機時間活動**> 中的清單選擇維護停機時間活動，並按一下 **產能負載** 以開啟 **計算產能負載** 對話方塊。 使用此對話方塊可以概覽日期、資產、資產類型，和維護作業類型等方面的產能負載。 請注意，對話方塊中顯示的日期是在 **維護停機時間活動** 中的開始與結束日期。 此計算包括與維護停機時間活動相關的資產。

9. 在 **計算產能負載** 對話方塊中，視需要編輯開始和結束時間，並選擇是否要在計算中包括工單和維護排程。 您可使用 **等級** 欄位，指定產能負載計算相關功能位置的詳細程度。 例如，如果在欄位中插入數字「1」，並且您有一個多層級的機能位置結構，則一個機能位置的所有資產 (會在維護停機時間活動中選取) 會顯示在最高層級，因此一個明細上的時數可能從位於較低層級的功能位置累加。 如果將數字「0」插入 **等級** 欄位，您將看到一個詳細的結果，其中顯示了與它們相關的所有機能位置等級上的所有產能負載明細。

10. 按一下 **確定** 以開始計算。 總時數會顯示在 **產能負載** 概觀中。 在 **產能負載** 索引標籤 >**分組依據...** 動作窗格群組上，按一下相關按鈕，以瞭解更詳細的預測時數分配。 下圖顯示了 **產能負載** 計算的結果。

![圖 3。](media/21-preventive-maintenance.png)

11. 在您取得產能負載概觀後，如果要對工單維護作業或維護排程明細進行調整，請返回到 **維護停機時間活動** 詳細資料檢視，並選擇要在 **產生的工單維護作業** 和 **維護排程明細** FastTab 上調整的明細。

12. 按一下 **調整** 按鈕並更新選定工單維護作業或維護排程明細的預期開始/結束日期、服務等級或負責的維護人員。

13. 當您完成必要調整時，請按一下 **確定**。 

>[!NOTE]
>進行調整後，未包含在維護停機時間期間內的工單維護作業和維護排程明細，將自動從 **維護停機時間活動** 移除。

14. 在 **所有維護停機時間活動** > **維護停機時間活動**> 中的清單選擇維護停機時間活動，並按一下 **品項預測** 以開啟 **計算品項預測** 對話方塊。 使用此對話方塊以計算品項 (備品和其他所需品項) 預測，並將它們分組以取得概觀，例如，按日期、資產、資產類型和維護作業類型的分組。 請注意，對話方塊中顯示的日期是在 **維護停機時間活動** 中的開始與結束日期。 此計算包括與在維護停機時間活動中選擇的資產相關備品和品項。

15. 在 **計算品項預測** 對話方塊中，視需要編輯開始和結束時間，並選擇是否要在計算中包括工單和維護排程。 您可使用 **等級** 欄位，指定產能負載計算相關功能位置的詳細程度。 例如，如果在欄位中插入數字「1」，並且您有一個多層級的機能位置結構，則一個機能位置的所有資產 (會在維護停機時間活動中選取) 會顯示在最高層級，因此一個明細上的時數可能從位於較低層級的功能位置累加。 如果將數字「0」插入 **等級** 欄位，您將看到一個詳細的結果，其中顯示了與它們相關的所有機能位置等級上的所有產能負載明細。

16. 按一下 **確定** 以開始計算。 總品項預測數目會顯示在 **品項預測** 概觀中。 在 **品項預測** 索引標籤 >**分組依據...** 動作窗格群組上，按一下相關按鈕以取得更詳細的預測品項分配概觀。下圖顯示了一個 **品項預測** 計算的結果。

![圖 4。](media/22-preventive-maintenance.png)

- 您可以將資產從一項維護停機活動複製到另一個。 在 **所有維護停機時間活動** 中，選擇 **複製維護停機時間活動** 按鈕，然後在 **從維護停機時間活動** 和 **到維護停機時間活動** 欄位進行選擇，然後按一下 **確定**。
- 在 **所有維護停機時間活動** 中，按一下 **維護排程明細** 按鈕或 **使用中的工單** 按鈕，以打開相關清單並查看與所選維護停機時間活動相關的明細。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]