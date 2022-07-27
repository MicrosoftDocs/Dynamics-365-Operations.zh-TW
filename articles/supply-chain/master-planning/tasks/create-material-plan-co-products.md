---
title: 為副產品創建物料計劃
description: 生產計劃員為副產品的物料需求進行計畫。
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: deae0d7e0295aa02f5ad512f67e9e3d2148c2e33
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449094"
---
# <a name="create-a-material-plan-for-co-products"></a>為副產品創建物料計劃

[!include [banner](../../includes/banner.md)]

生產計劃員為副產品的物料需求進行計畫。 建立此程序的示範資料公司為 USP2。

## <a name="create-requirement-for-a-co-product"></a>為副產品創建需求

1. 前往 **銷售和營銷 \> 工作區 \> 銷售訂單處理和查詢**。
1. 選擇 **新增**。
1. 選擇 **銷售訂單**。
1. 在 **客戶帳戶** 欄位中，輸入一個值。
    * 例如：US-001  
1. 選擇 **確定**。
1. 在 **項目編號** 欄位中，輸入一個值。
    * 例如：P6003  
1. 在 **數量** 欄位中，輸入一個數字。
    * 例如：50000  
1. 選擇 **儲存**。

## <a name="create-a-material-plan-for-co-products"></a>為副產品創建物料計劃

1. 關閉頁面。
1. 關閉頁面。
1. 選擇 **主要計畫**。
1. 在 **活動** 欄位中，打開下拉式按鈕以開啟查詢。
1. 在列表中，選擇所選行中的連結。
    * 例如：MasterPlan  
1. 選擇 **執行**。
1. 展開或摺疊 **紀錄包含** 部分。
1. 選擇 **篩選**。
1. 在列表中，選擇 **欄位** = *項目編號* 列。
1. 在 **條件** 欄位中，輸入一個值。
    * 例如：P6003  
1. 選擇 **確定**。
1. 選擇 **確定**。
1. 選擇 **已計畫的訂單**。
1. 使用快速篩選器尋找記錄。 例如，在 **項目編號** 欄位使用「P6000」的值進行篩選。
    * 依據您為銷售訂單與副產品項目相同的配方品項進行篩選。  
1. 在清單中，標記所選資料列。
    * 選擇任何由篩選傳回的列。  
1. 在列表中，選擇所選行中的連結。
1. 展開 **需求追蹤** 部分。
1. 在列表中，選擇所選行中的連結。
    * 計劃訂單與副產品的銷售訂單掛鉤。  
1. 關閉頁面。

## <a name="create-a-second-requirement-for-a-co-product"></a>為副產品創建第二需求

1. 前往 **銷售和營銷 \> 工作區 \> 銷售訂單處理和查詢**。
1. 選擇 **新增**。
1. 選擇 **銷售訂單**。
1. 在 **客戶帳戶** 欄位中，輸入一個值。
    * 例如：US-001  
1. 選擇 **確定**。
1. 在 **項目編號** 欄位中，輸入一個值。
    * 例如：P6003  
1. 在 **數量** 欄位中，輸入一個數字。
    * 例如：50000  
1. 選擇 **儲存**。

## <a name="create-a-second-material-plan-for-co-products"></a>為副產品創建第二物料計劃

1. 在 **活動** 欄位中，打開下拉式按鈕以開啟查詢。
2. 在列表中，選擇所選行中的連結。
    * 例如：MasterPlan  
3. 選擇 **執行**。
4. 展開或摺疊 **紀錄包含** 部分。
5. 選擇 **篩選**。
6. 在列表中，選擇 **欄位** = *項目編號* 列。
7. 在 *條件* 欄位中，輸入一個值。
    * 例如：P6003  
8. 選擇 **確定**。
9. 選擇 **確定**。
10. 選擇 **已計畫的訂單**。
11. 使用快速篩選器尋找記錄。 例如，在 **項目編號** 欄位使用「P6000」的值進行篩選。
    * 依據您為銷售訂單與副產品項目相同的配方品項進行篩選。  
12. 在清單中，標記所選資料列。
    * 選擇任何由篩選傳回的列。  
13. 在列表中，選擇所選行中的連結。
14. 展開或摺疊 **需求追蹤** 區段。
15. 在列表中，選擇所選行中的連結。
    * 計劃訂單與副產品的銷售訂單掛鉤。  
16. 關閉頁面。
17. 選擇 **主要計畫**。
18. 前往 **總規劃 \> 設定 \> 總規劃參數**。
19. 選擇 **禁用所有計劃流程** 欄位中的 *否*。
20. 關閉頁面。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]