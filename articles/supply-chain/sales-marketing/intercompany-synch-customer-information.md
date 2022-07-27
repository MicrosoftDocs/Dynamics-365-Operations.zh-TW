---
title: 同步公司間客戶資訊
description: 本主題說明如何同步公司間訂單的客戶資訊
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c82216c8391f6c447bec74f25cd16b9db18d468d
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447753"
---
# <a name="synchronize-intercompany-customer-information"></a>同步公司間客戶資訊

[!include [banner](../../includes/banner.md)]

如果建立銷售訂單時，或是變更客戶、廠商參考資料，或是客戶要求號碼時，啟用 **客戶資料**，則會同步客戶資料。

您可以隨時變更這些同步處理欄位的值。 但是，您只能通過選擇此參數，決定是否將該值複製到其他公司間訂單。 如果您已經在公司間銷售訂單上，啟用 **客戶資料** 欄位，則公司間銷售訂單上所做的變更，會同步至公司間訂購單。 如果您在公司間訂購單上，也啟用 **客戶資料** 欄位，則變更內容也會同步返回至原始銷售訂單。

> [!NOTE]
> 如果公司間訂購單和公司間銷售訂單兩者，您都啟用 **客戶資料** 欄位，則公司中某個人所進行的更新，會被另一間公司的另一個人，對同一訂單所做的更新給駁回。

最佳做法是啟用公司間訂購單的 **客戶資料** 欄位。 如此，可以啟用原始銷售訂單，和公司間訂購單之間的同步，並從公司間訂單，同步至公司間銷售訂單。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
