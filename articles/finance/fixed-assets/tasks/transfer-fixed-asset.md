---
title: 轉移固定資產
description: 本工作指南會將固定資產帳冊的財務資訊從一個財務維度集轉移到新的財務維度集。
author: moaamer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e573386ddbb97bf60e2e501ba92b225f8716c73a
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451212"
---
# <a name="transfer-a-fixed-asset"></a>轉移固定資產

[!include [banner](../../includes/banner.md)]

本工作指南會將固定資產帳冊的財務資訊從一個財務維度集轉移到新的財務維度集。  

1. 在瀏覽窗格中，進入 **模組> 固定資產> 固定資產> 固定資產**。
2. 在清單中，尋找並選取要轉移的固定資產。
3. 在動作窗格上，按一下 **固定資產**。
4. 按一下 **轉移固定資產**。
5. 在 **轉移日期** 欄位，輸入日期。
6. 輸入註解來描述轉移。
    
    此清單顯示了固定資產的所有帳冊。  
7. 標記要轉移到新財務維度集的帳冊。
    * 此清單顯示了所選帳冊的現有財務維度值。  
    * 如需所選的固定資產帳冊選取要更新的財務維度。  
8. 在 **財務維度** 欄位中，按一下下拉式按鈕開啟查詢。
    * 根據需要設定其他財務維度值。  
    * 發生轉移時，所有財務維度值都會發生變化，無論是輸入值還是留空。 例如，如果您輸入了 BusinessUnit 的值並將 CostCenter 和 Department 財務維度留空。 如果您的帳戶結構允許 CostCenter 和 Department 為空白值，則轉移將導致每個數值模型具有 BusinessUnit 的新值和 CostCenter 和 Department 的空白值。  
9. 按一下 **更新**。
    * 您有機會在完成轉移之前預覽更改。  
    * 在轉移固定資產帳冊之前檢閱結果。  
10. 按一下 **轉移**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
