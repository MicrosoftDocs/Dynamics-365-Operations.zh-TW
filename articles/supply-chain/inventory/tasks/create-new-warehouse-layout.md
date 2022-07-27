---
title: 創建新的倉庫配置
description: 本主題介紹如何設置有關倉庫中位置的資訊。
author: yufeihuang
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf5c5203aa0a4c8522b8f9d04fc6a8cd306a64a3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449361"
---
# <a name="create-a-new-warehouse-layout"></a>創建新的倉庫配置

[!include [banner](../../includes/banner.md)]

本主題介紹如何設置有關倉庫中位置的資訊。 這僅適用於在庫存管理模組中使用「基本倉儲」所創建的倉庫，不適用於在倉庫管理模組中所創建的倉庫。 您可使用示範資料公司 USMF 或自己的資料來執行此程序。


## <a name="set-the-default-location-capacity"></a>設置預設位置容量
1. 在瀏覽窗格中，移至 **模組 > 庫存管理 > 設定 > 庫存與倉庫管理參數**。
2. 選擇 **位置** 索引標籤。
3. 在 **標準寬度** 欄位中，輸入一個數字。
4. 在 **標準深度** 欄位中，輸入一個數字。
5. 在 **標準高度** 欄位中，輸入一個數字。
6. 選擇 **儲存**。
7. 關閉頁面。

## <a name="define-the-location-name-format"></a>定義位置名稱格式
1. 在瀏覽窗格中，前往 **模組 > 庫存管理 > 設定 > 庫存明細 > 倉庫**。
2. 選擇 **新增**。
3. 在 **Warehouse** 欄位中輸入值。
4. 在 **名稱** 欄位中，輸入一個值。
5. 在 **地點** 欄位中，從查找中選擇想要的紀錄。
6. 按一下切換，展開 **位置名稱** 的部分。 此部分中的選項，說明位置名稱的預設格式。 在我們的範例中，我們將包含走道編號、貨架編號和層架編號。  
7. 將 **包含走道** 選項，設定為 **是**。
8. 將 **包含貨架** 選項，設定為 **是**。 
9. 在 **格式** 欄位，為貨架輸入一個值。
10. 將 **包含層架** 選項，設定為 **是**。
11. 在 **格式** 欄位，為層架輸入一個值。

## <a name="define-warehouse-locations"></a>定義倉庫位置
1. 在動作窗格上，選擇 **倉庫**。
2. 選擇 **位置精靈**。
3. 選擇 **下一步**。
4. 取消選擇 **出貨碼頭** 選項
5. 取消選擇 **批次位置** 選項
6. 選擇 **下一個** 直到您要的選項，然後選擇 **結束**。
7. 關閉頁面。
8. 重新整理頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]