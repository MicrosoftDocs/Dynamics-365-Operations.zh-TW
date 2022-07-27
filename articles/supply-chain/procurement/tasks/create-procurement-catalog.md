---
title: 創建採購目錄
description: 本主題說明如創建採購目錄。
author: Henrikan
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef3747874d43143925bd08dbecc2d60f4e38701a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447819"
---
# <a name="create-a-procurement-catalog"></a>創建採購目錄

[!include [banner](../../includes/banner.md)]

本主題說明如創建採購目錄。 此任務通常由採購專家執行。 您還將了解員工在創建申請時使用目錄的方法。 創建目錄之前，您的系統中必須有一個採購類別階層。 階層由新產品目錄繼承，所有產品都會在階層中。 您可以在採購類別層次結構可用的演示數據公司 USMF 中使用本指南，以及過程步驟中使用的示例。


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>確保採購類別階層已存在
1. 前往 **功能窗格 > 模組 > 採購及開源 > 採購階層**。 USMF 演示數據公司中提供了採購類別層次結構，並且產品已添加到 **辦公機器/電腦** 類別。 如果您將此過程作為任務指南執行，則需要解鎖指南才能瀏覽該類別。 如果階層不可用，您可以通過按一下 **新增** 來創建。 這只能進行一次。  
2. 關閉頁面。

## <a name="create-a-catalog"></a>創建目錄
1. 前往 **功能窗格 > 模組 > 採購及開源 > 目錄 > 採購目錄**。
2. 選擇 **新採購目錄** 打開下拉對話框。
3. 在 **名稱** 欄位中，輸入一個值。
4. 選擇 **確定**。
5. 在樹狀圖中，展開 **CORP PROCUREMENT CATEGORIES**。
6. 在樹狀圖中，展開 **OFFICE MACHINES**。
7. 在樹狀圖中，選擇 **電腦**。

  - 採購目錄中的產品會顯示在列表中。 如果您想將產品添加到類別中，您需要在 **採購目錄階層** 頁或在 **商品詳情** 頁執行。  
  - **預設** 更新類型決定，已新增到採購目錄階層的新產品，是否可以立即在目錄中可見。 如果更新類型設定為 **動態**，則可以立即看見變更。 如果更新類型是 **靜態**，則只有在重新發布目錄後，使用目錄的人才能看到新產品。 **發布** 動作可用於頁面頂部的動作窗格中。 如果產品從採購類別階層中刪除，則無論 **預設** 的更新類型欄位，都可以立即看見變更。  

8. 在動作窗格上，選擇 **目錄導航** 並確保已選擇 **啟用**。
9. 選擇 **啟用目錄**。
10. 關閉頁面。

## <a name="make-the-catalog-visible"></a>使目錄可見
1. 前往 **功能窗格 > 模組 > 採購和委外 > 設定 > 政策 > 採購政策**。
2. 選擇 **採購政策 USMF**。 您需要為允許連接到您的用戶資料的工作人員訂購產品的法人實體選擇採購政策。 在 USMF 示範資料中，Admin 用戶連接到名為 **Julia Funderburk** 的工人，並且她在 USMF 中訂購的產品為預設。  
3. 選擇您剛剛創建的目錄。
4. 選擇 **確定**。

## <a name="use-the-catalog"></a>使用目錄
1. 前往 **功能窗格 > 模組 > 採購及開源 > 採購需求 > 所有採購需求**。
2. 選擇 **新增**。
3. 在 **名稱** 欄位中，輸入一個值。
4. 選擇 **確定**。
5. 選擇 **新增產品**。
6. 在清單中，尋找並選擇所需紀錄。 您可以使用左側的目錄階層，或列表頂部的篩選器來篩選產品。  
7. 選擇 **新增到行**。
8. 選擇 **確定**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]