---
title: 使用廠商集區將發票資料鍵入 AP 系統
description: 本主題說明如何使用發票登記冊建立發票。
author: abruer
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4768ee6ddbaba8ae5bab5e2f9f7df9239efeb90
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2022
ms.locfileid: "8451641"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>使用廠商集區將發票資料鍵入 AP 系統

[!include [banner](../../includes/banner.md)]

本主題說明如何使用發票登記冊建立發票。 接著使用發票集區將發票與採購訂單比對，並在廠商發票頁敲定費用。


## <a name="create-a-purchase-order"></a>建立採購訂單
1. 在瀏覽窗格前往 **模組 > 應付帳款 > 採購訂單 > 採購訂單**。
2. 選取 **新增** 建立採購訂單。
3. 在 **廠商帳號** 欄位選取下拉式清單的廠商。 例如，選取廠商 **1001**。
4. 選取 **確定**。
5. 在 **Item number** 欄位選取下拉式清單的服務項目編號。 例如，選取 **S0001**。 淨額為 75.00。  這是我們預計發票上顯示的金額。  
6. 在動作窗格上，選取 **購買**。
7. 選取 **確認**。

## <a name="create-and-post-and-invoice"></a>建立和過帳和發票
1. 在瀏覽窗格中，前往 **模組 > 應付帳款 > 發票 > 發票登記**。
2. 選取 **新增**。
3. 打開查閱功能選取您希望使用的發票登記冊名稱。
4. 選取您希望使用的發票登記冊名稱。
5. 選取 **明細** 打開登記冊並輸入費用明細數據。
6. 在查閱功能區選取廠商。 例如，選取廠商 **1001**。
7. 在 **發票** 欄位，輸入發票號碼。
8. 在 **描述** 欄位中，輸入一個值。
9. 在 **信用額度** 欄位，輸入數字。
10. 在 **採購訂單** 欄位，打開下拉式清單選取您之前建立的採購訂單。
11. 在 **核准人員** 欄位的下拉式清單重點標示核准人員，並點選 **選取**，選取該名核准人員。
12. 選取 **過帳**。

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>從集區打開發票並與採購訂單比對，完成發票流程
1. 在瀏覽窗格前往 **模組 > 應付帳款 > 發票 > 發票集區**。
2. 選取 **採購訂單** 從集區的發票建立廠商發票。
3. 選取您希望審核的發票
4. 選取 **更新比對狀態** 完成比對。
5. 在動作窗格上，選取 **選項**。
6. 選取 **更改視圖**。
7. 選取 **網格視圖**
8. 選取 **過帳**。
9. 關閉頁面。
10. 在瀏覽窗格前往 **模組 > 應付帳款 > 廠商 > 廠商**。
11. 選取採購訂單上的廠商。 例如，選取廠商 **1001**。
12. 在動作窗格上，選取 **廠商**。
13. 選取 **交易**。
14. 選取您已經建立的發票。 發票登記應計款項已經沖銷並且過帳到適當的費用科目。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
