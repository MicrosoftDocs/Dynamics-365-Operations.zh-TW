---
title: 維護產品模型的路線
description: 執行此程序需要現有產品設定模型。
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88df8b867ac7f354417add0462e7999747333451
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448992"
---
# <a name="maintain-route-for-a-product-model"></a>維護產品模型的路線

[!include [banner](../../includes/banner.md)]

執行此程序需要現有產品設定模型。 此程序使用示範公司 USMF 中的高品質喇叭模型以向您說明該過程。

## <a name="add-a-route-operation"></a>新增路線作業

1. 移至 **產品資訊管理\>產品\>產品設定模型**。
1. 在清單中，尋找並選擇所需紀錄。
    * 為此練習選擇高品質喇叭型號。  
1. 在列表中，選擇所選行中的連結。
1. 展開 **路線作業** 區段。
1. 選擇 **新增**。
1. 在 **名稱** 欄位中，輸入一個值。
1. 在 **描述** 欄位中，輸入一個值。
1. 選擇 **儲存**。

## <a name="enter-route-operation-details"></a>輸入路線作業詳細資料

1. 選擇 **途程作業詳細資料**。
1. 在 **作業** 欄位中，輸入或選擇一個值。
1. 在 **作業編號** 中 在欄位輸入數字。
    * 工序編號決定了路線順序。  
    * 路線操作上的每個屬性都可以取得靜態值或對應到屬性。 對應到屬性將導致值被設為設定的一部分。  
1. 請在 **路線群組** 欄位中輸入或選擇一個值。
    * 路線群組決定了成本計算、消耗和設定的基本行為。  
1. 選擇 **設定** 索引標籤。
1. 選擇 **時間** 索引標籤。
1. 在 **處理數量** 欄位中，輸入一個數字。
    * 決定在一個作業期間將處理多少項目。  
1. 在 **小時/時間** 欄位中輸入一個數字。
    * 輸入時間比率。  
1. 選擇 **設定** 核取方塊。
1. 在 **執行時間** 欄位中輸入一個數字。
    * 決定您已指定的數量處理時間。  
1. 選擇 **資源需求** 索引標籤。
1. 選擇 **新增**。
1. 在清單中，標記所選資料列。
1. 請在 **需求類型** 欄位中選取一個選項。
    * 決定是否要指定他們必須擁有的特定資源或能力。  
1. 在 **需求** 欄位中，輸入或選擇一個值。
1. 選擇 **確定**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]