---
title: 報告為完成到非牌照控制的庫位 (申請表，2016 年 5 月)
description: 本工作指南說明報告為完成到非牌照控制庫位的範例。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrResourceGroup, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdParmCostEstimation, ProdParmStartUp, ProdParmReportFinished, WHSWorkTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f891b2e3b20993a08138dfac1aed4f4bab33c6b1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448935"
---
# <a name="report-as-finished-to-a-non-license-plate-controlled-location--application-may-2016"></a>報告為完成到非牌照控制的庫位 (申請表，2016 年 5 月)

[!include [banner](../../includes/banner.md)]

本工作指南說明報告為完成到非牌照控制庫位的範例。 適用的工作原則是此工作的先決條件。 先前的工作指南說明工作原則的設定。 此工作指南需要 Dynamics AX應用程式 7.0.1 或更新版本。




## <a name="set-up-an-output-location"></a>設定出庫位置
1. 移至組織管理 > 資源 > 資源群組。
2. 在清單中選取資源群組 '5102'。
3. 按一下 [編輯]。
4. 在「輸出倉庫」欄位中輸入 '51'。
5. 在「輸出庫位」中輸入 '001'。
    * 庫位 001 不是牌照控制的庫位。 只有當庫位存在適用的工作原則時，您才能設定非牌照的輸出庫位。  

## <a name="create-a-production-order-and-report-it-as-finished"></a>建立生產訂單並報告為完成
1. 關閉頁面。
2. 移至 [生產控制] > [生產訂單] > [所有生產訂單]。
3. 按一下新增生產訂單。
4. 在「項目編號」欄位中輸入 'L0101'。
5. 按一下 [建立]。
6. 在 [動作窗格] 上按一下 [產品訂單]。
7. 按下 [估計]。
8. 按一下 [確定]。
9. 按一下 [開始]。
10. 按一下「一般」索引標籤。
11. 在「自動物料清單耗用量」欄位中，選擇 [永不]。
12. 按一下 [確定]。
13. 按一下「報告為完成」。
14. 按一下「一般」索引標籤。
15. 在「接受錯誤」欄位中選擇 [是]。
16. 按一下 [確定]。
17. 在「動作窗格」上按一下 [倉庫]。
18. 按一下 [工作詳細資料]。
    * 當生產訂單報告為完成時，尚未為儲存產生工作。 發生這種情況是因為將工作原則定義為在產品 L0101 報告為完成到庫位 001 時阻止產生工作。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]