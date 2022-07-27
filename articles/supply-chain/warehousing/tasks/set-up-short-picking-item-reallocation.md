---
title: 設定揀料短缺品項重新分配
description: 本主題介紹如何讓倉庫工作人員在他們受指示的位置沒有足夠的庫存時，快速找到備用位置。
author: Mirzaab
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker, WHSLocationWithWorkException
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7fe17246037a35e44d12476f184af3bd4c806022
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447789"
---
# <a name="set-up-short-picking-item-reallocation"></a>設定揀料短缺品項重新分配

[!include [banner](../../includes/banner.md)]

本程序介紹如何讓倉庫工作人員在他們受指示的位置沒有足夠的庫存時，快速找到備用位置。 

重新分配流程由 **工作例外狀況** 控制，並由倉庫 **工作人員** 使用。

可以使用自動和/或手動重新分配流程：

- 自動重新分配 - 位置指令用於確定另一個位置是否提供這些貨物。 如果可以，將更新工作並將倉庫使用者導向到備用位置。
- 手動重新分配 - 允許倉庫使用者從一個或多個有未預留貨物數量的位置中進行選擇。 
- 自動和手動 - 如果系統無法執行自動重新分配，並且有位置具有未預留數量，則會提示使用者選擇位置。

## <a name="set-up-work-exceptions"></a>設定工作例外狀況
可使用不同的品項重新分配原則定義多個工作例外狀況，以使倉庫工作人員可以根據他們正在處理的裝運需求選擇一個。

建立此程序時使用的 USMF 示範資料公司。

1. 在 **瀏覽窗格** 中，移至 **倉庫管理 > 設定 > 工作 > 工作例外狀況**。
2. 點選 **新增** 
3. 在 **工作例外狀況代碼** 欄位中，輸入一個值。 這將是此例外狀況的標題。 例如，手動揀料短缺。
4. 在 **描述** 欄位中，輸入一個值。 這將是此例外狀況用法的簡短描述。 例如，揀料短缺 - 品項不可用。
5. 在 **例外狀況** 類型欄位中，選取 **揀料短缺**。
6. 選擇 **調整庫存** 核取方塊。 如果已選取，揀料短缺位置自動將庫存調整為 0。
7. 在 **預設調整類型代碼** 欄位中，輸入或選取一個值。 例如，在 USMF 中，您可以選擇 **移除 Res Adj Out**。每個調整類型代碼包含四個特徵：名稱、描述、庫存日記帳名稱和 **刪除預訂**。 如果 **刪除預訂** 啟用後，將刪除短揀訂單行的預留。  
8. 在裡面 **物品重新分配** 字段，選擇一個值，例如手動。 如果您選擇手動或自動和手動，則需要啟用倉庫工作人員才能使用手動重新分配。

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>設定工作人員以使用手動品項重新分配

建立此程序時使用的 USMF 示範資料公司。

1. 關閉頁面。
2. 在 **瀏覽窗格** 中，移至 **倉庫管理 > 設定 > 工作**。
3. 點選 **編輯**。
4. 在清單中，選取工作人員。 例如 Julia Funderburk。
5. 展開 **使用者** FastTab。
6. 在清單中，選取 **使用者識別碼**。 例如：24。
7. 展開 **工作** FastTab。
8. 在 **允許手動品項重新分配** 欄位選擇 **是**。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]