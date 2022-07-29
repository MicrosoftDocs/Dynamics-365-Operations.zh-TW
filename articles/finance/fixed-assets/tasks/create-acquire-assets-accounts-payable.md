---
title: 從應付帳款建立和購置資產
description: 此程序說明如何遵照採購流程來建立和購置固定資產。
author: saraschi2
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dbac069362a15b5ab1d2dbf88a732a14a3cf709d
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2021
ms.locfileid: "8450924"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>從應付帳款建立和購置資產

[!include [banner](../../includes/banner.md)]

此程序說明如何遵照採購流程來建立和購置固定資產。  本文使用會計師和應付帳款職員以及示範公司 USMF。


## <a name="set-fixed-assets-parameters"></a>設定固定資產參數
1. 在 **瀏覽窗格** 中，前往 **模組> 固定資產> 設定> 固定資產參數**。
2. 展開 **採購訂單** fastTab。
3. 選取 **允許從採購中購置資產** 核取方塊。
4. 選取 **在產品收據或發票過帳期間建立資產** 核取方塊。

## <a name="create-a-new-vendor-invoice"></a>建立新的廠商發票
1. 在 **瀏覽窗格**，前往 **模組 > 應付帳款 > 工作區 > 廠商發票分錄**。
2. 點選 **新增廠商發票**。
3. 在 **發票科目** 欄位，點選下拉式按鈕打開查閱功能。
4. 在清單中，點選已選取列的連結。
5. 在 **編號** 欄位，輸入一值。
6. 在 **過帳日期** 欄位，輸入日期。
7. 點選 **新增行項**。
8. 在 **品項編號** 欄位中，點選下拉式按鈕開啟查詢。 非庫存品項或採購類別均可用於固定資產購置。  
9. 在清單中，點選已選取列的連結。
10. 在 **數量** 欄位中，輸入一個數字。 一個發票行將只能建立一項不論數量多寡的固定資產。 發票數量欄位值將轉移到固定資產數量。  
11. 在 **單價** 欄位中，輸入一個數字。
12. 展開 **行項詳細資料** fastTab。
13. 點選 **固定資產** 索引標籤。
14. 選取 **建立新的固定資產** 核取方塊。
15. 在 **固定資產群組** 欄位中，按一下下拉式按鈕開啟查詢。
16. 在清單中，選擇建立新固定資產時要使用的固定資產群組。
17. 在清單中，點選已選取列的連結。
18. 點選 **過帳**。 將在發票過帳時建立和購置固定資產。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
