---
title: 設定中樞附屬費用和附屬主板
description: 此程序顯示如何為中樞建立附屬主版，並使用該主版建立中樞附屬費用。
author: Henrikan
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSCarrierAccessorial,TMSAccessorialMaster, TMSHubAccessorial
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f1480dec82912d547bde5db614703164e3f8451c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448884"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>設定中樞附屬費用和附屬主板

[!include [banner](../../includes/banner.md)]

此程序顯示如何為中樞建立附屬主版，並使用該主版建立中樞附屬費用。 該程序使用 USMF 資料集。 這設定通常由運輸協調員完成。


## <a name="set-up-a-hub-master"></a>設定中樞主板
1. 轉到運輸管理 > 設定 > 評等 > 補充主版。
2. 點選 [新增]。
3. 在「補充主版」欄位中，輸入一個值。
4. 在名稱欄位中，輸入一個值。
5. 在 [附屬類型] 欄位中，選取 [中樞]。
6. 點選 [儲存]。
7. 關閉頁面。

## <a name="set-up-a-hub-accessorial-charge"></a>設定中樞附屬費用
1. 移至運輸管理 > 設定 > 評等 > 中樞附屬費用。
2. 點選 [新增]。
3. 在 [中樞附屬識別碼] 欄位中，輸入一個值。
4. 點選 [中樞] 欄位中的下拉式按鈕以開啟查詢。
5. 在清單中，尋找並選擇所需紀錄。
6. 在 [中樞位置] 欄位中，選擇一個選項。
    * 您可以建立裝貨或卸貨費用。 根據您的選擇，費用將計入您路線上的相應運輸區段。  
7. 在補充主版欄位中，按一下下拉式按鈕開啟查詢。
8. 在列表中，按一下所選行中的連結。
    * 選擇您剛剛建立的主板。  
9. 點選 [儲存]。
10. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]