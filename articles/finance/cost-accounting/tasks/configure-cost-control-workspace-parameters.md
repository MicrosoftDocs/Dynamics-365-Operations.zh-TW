---
title: 設定成本控制工作區參數
description: 使用此流程設定成本控制工作區，以便組織中不同級別的經理可以深入了解其成本物件，例如成本中心和產品組。
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspaceConfigurationPerUser
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ecc775019445bbe97dd5a0e9198b9c605b1c65322006d912a95a5bb1fbdf879
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450699"
---
# <a name="configure-cost-control-workspace-parameters"></a>設定成本控制工作區參數

[!include [banner](../../includes/banner.md)]

使用此流程設定成本控制工作區，以便組織中不同級別的經理可以深入了解其成本物件，例如成本中心和產品組。 使用 USP2 示範公司建立此錄製。

1. 前往 [成本會計] > [設定] > [成本控制工作區設定]。
2. 點選 [新增]。
3. 在名稱欄位中，輸入一個值。
4. 在 [描述] 欄位中，輸入一個值。
5. 在 [已發佈] 欄位中選擇 [是]。
    * 如果將此選項設定為 [是]，則指派了以下角色之一的使用者可以在成本控制工作區中查看報表：成本會計經理、成本會計師、成本會計職員和成本物件控管者。 如果將此選項設定為 [否]，則僅指派了以下角色之一的使用者可以在成本控制工作區中查看報表：成本會計經理、成本會計師或成本會計職員。  
6. 展開 [資料篩選] 區段。
7. 在 [成本控制單位] 欄位中，輸入或選取一個值。
8. 在 [預算原始版本] 欄位中，輸入或選項值。
9. 在 [成本元素維度階層] 欄位中，輸入或選取一個值。
10. 在 [成本物件維度階層] 欄位中，輸入或選取一個值。
11. 展開 [指派計算記錄] 區段。
12. 點選 [新增]。
13. 在清單中，標示選取的列。
14. 在 [會計行事曆期間] 欄位中，輸入或選取一個值。
15. 在 [實際版本] 欄位中，輸入或選項值。
16. 展開 [每欄的會計期間] 區段。
17. 在 [目前期間] 欄位中選擇 [是]。
18. 展開 [為成本顯示的欄] 區段。
19. 在 [固定成本] 欄位中選擇 [是]。
20. 在 [變動成本] 欄位中選擇 [是]。
21. 在 [總成本] 欄位中選擇 [是]。
22. 點選 [儲存]。
23. 關閉頁面。
24. 前往 [成本會計] > [工作區] > [成本控制]。
25. 選擇報表以查看選定會計期間的固定成本、變動成本、總成本和未分類成本。
26. 在 [會計行事曆期間] 欄位中，輸入或選取一個值。
27. 在 [成本物件維度階層節點] 欄位中，輸入或選取一個值。
    * 選擇成本物件維度階層後，展開 [成本物件維度階層] 以查看所需的成本值。 例如，您可以將階層擴展到 [製造開銷] 以查看值。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]