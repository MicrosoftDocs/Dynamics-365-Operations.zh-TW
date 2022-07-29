---
title: 使用核准日記帳將發票資料鍵入應付帳款
description: 本主題解釋如何使用發票登記簿建立發票，然後使用核准日記帳更新費用科目。
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ce66a4b92f26bcec0849accad3878aef2b2f658
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451536"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a>使用核准日記帳將發票資料鍵入應付帳款

[!include [banner](../../includes/banner.md)]

本主題解釋如何使用發票登記簿建立發票，然後使用核准日記帳更新費用科目。

## <a name="create-and-post-and-invoice"></a>建立和過帳和發票
1. 在瀏覽窗格中，前往 **模組 > 應付帳款 > 發票 > 發票登記**。
2. 選取 **新增**。
3. 選取您希望使用的發票登記冊名稱。
4. 選取 **明細** 打開登記冊並輸入費用明細數據。
5. 選取廠商。 例如，輸入或選取 `US-104`。
6. 在 **發票** 欄位，鍵入一值。
7. 在 **描述** 欄位中，輸入一個值。
8. 在 **信用額度** 欄位，輸入數字。
9. 在 **核准人員** 欄位中，從下拉式選單選取核准人員。
10. 選取 **過帳**。

## <a name="approve-an-invoice"></a>核准發票
1. 在瀏覽窗格中，前往 **模組 > 應付帳款 > 發票 > 發票核准**。
2. 選取 **新增**。
3. 選取您希望使用的發票核准日記帳名稱。
4. 選取 **明細** 顯示您將可以從中選取希望核准發票的頁面。
5. 選取 **尋找憑據** 顯示所有準備好核准的發票。
6. 標記您已建立的發票，然後點選 **選取**。 如上述選取的憑據會在您選取它們後移動到本清單。  
7. 選取 **確定**。
8. 選取 **帳號** 欄位新增費用科目到發票。
9. 輸入帳號並且取消欄位的索引標籤。 例如，輸入 `600120`。
10. 選取 **過帳**。
11. 選取 **憑據** 檢視已經過帳的分錄。 發票待核定核准科目隨即沖銷並以實際費用科目取代。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
