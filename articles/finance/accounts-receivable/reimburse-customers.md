---
title: 向客戶請款
description: 本文解釋如何建立一組客戶的請款交易。 如果客戶有貸記餘額，您可以向客戶請款餘額。
author: JodiChristiansen
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0c313c03c6f3504f132a836eb6a67207e5f3c5636d43124c5f16d13992b9b604
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450759"
---
# <a name="reimburse-customers"></a>向客戶請款

[!include [banner](../includes/banner.md)]

本文解釋如何建立一組客戶的請款交易。 如果客戶有貸記餘額，您可以向客戶請款餘額。 

下表顯示開始前必須具備的先決行件。

| 先決行件                                                            | 描述 |
|-------------------------------------------------------------------------|-------------|
| 指明法人實體的最低請款金額。          | 在 **應收帳款參數** 頁 **一般** 區的 **最低請款** 欄位中，輸入可請款客戶溢付款的最低金額。 |
| 選項：針對可請款的客戶新增廠商帳戶。 | 在 **客戶** 頁 **其他細節** FastTab上的 **廠商帳戶** 欄位，選取客戶的廠商帳戶。 |

當您建立請款交易時，會以貸記餘額的金額開立廠商發票。 請款流程移除客戶帳戶的貸記餘額，並針對與客戶對應的廠商帳戶建立到期應付餘額。

1. 在應收帳款中執行 **請款** 流程 (**應收帳款\>定期任務\>請款**)。
2. 為了分組所有交易，不論分類帳維度為何，一律設定 **總結客戶** 選項為 **是**。 若只分組分類帳維度類似的交易，請將選項設定為 **否**。
3. 選取 **包括借記交易待完成的客戶** 為有借記金額未結算的客戶。
4. 若要請款特定客戶帳戶，請在 **預計納入的記錄** FastTab上選取 **篩選**，然後在查詢中指定客戶帳戶。

    貸記金額轉入客戶的廠商帳戶，並以普通付款處理。 如果客戶沒有廠商帳戶，會自動建立一次性廠商帳戶。

5. 若要檢視已建立的請款交易，請使用 **請款** 報表 (**應收帳款\>查詢和報表\>請款報表**)。
6. 在應付帳款中，針對經由請款流程建立的廠商發票建立付款。 有關如何支付廠商的資訊，請參閱[廠商付款概觀](../accounts-payable/Vendor-payments-workspace.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]