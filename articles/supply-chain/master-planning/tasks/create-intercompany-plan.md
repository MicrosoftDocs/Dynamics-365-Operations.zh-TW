---
title: 建立公司間規劃
description: 此程序說明如何建立公司間規劃。
author: ChristianRytt
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ef1484e6925427454f819a5effdc911f762b48b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449091"
---
# <a name="create-an-intercompany-plan"></a>建立公司間規劃

[!include [banner](../../includes/banner.md)]

此程序說明如何建立公司間規劃。 建立此程序的示範資料公司為 USMF。

## <a name="set-up-an-intercompany-planning-group"></a>設定公司間規劃群組

1. 在 **導覽窗格** 中，移至 **模組 > 主計劃 > 設定 > 公司間規劃群組**。
2. 使用快速篩選器尋找記錄。 例如，以「10」這個值來篩選名稱欄位。
3. 在清單中，標記所選資料列。
4. 選擇 **刪除**。 為了縮短公司間規劃的執行作業，必須採取此步驟。   公司間規劃將在規劃群組內的所有公司執行主計劃，從排程順序最低的公司開始。  
5. 選擇 **是**。
6. 關閉頁面。

## <a name="create-an-intercompany-master-plan"></a>建立公司間主規劃

1. 在 **導覽窗格** 中，移至 **模組 > 主計劃 > 工作區 > 主計劃**。
2. 選擇 **公司間主計劃**。  
3. 在 **公司間規劃群組** 欄位中，選擇下拉式按鈕開啟查詢。
4. 在列表中，選擇所選行中的連結。 選擇公司間規劃群組 10。  
5. 在 **公司間規劃反覆次數** 欄位中，輸入「2」。 公司間規劃群組 10 有兩個成員。 若要將延遲從來源公司 (USMF) 傳遞至客戶公司 (DEMF)，您必須在兩家公司執行兩次公司間規劃。 第一次執行會將傳遞需求，並確認來源公司 (USMF) 中的延遲。 第二次執行則會將延遲從 USMF 傳遞至 DEMF。  
6. 在 **第一次執行** 欄位，選擇「重新產生」。
7. 在 **後續執行** 欄位，選擇「重新產生」。
8. 在 **執行緒數目** 欄位中，輸入一個數字。 這代表規劃使用的平行執行緒數量。  
9. 選擇 **確定**。

## <a name="view-the-result-of-the-plan"></a>檢視規劃結果

1. 在 **活動** 欄位中，打開下拉式按鈕以開啟查詢。
2. 在列表中，選擇所選行中的連結。 選擇 StaticPlan 的連結。 您必須處於公司 USMF 之內。  
3. 選擇 **已規劃訂單**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]