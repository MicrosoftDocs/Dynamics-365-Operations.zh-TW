---
title: 採購收據上的應計專案成本
description: 本主題說明如何在 Microsoft Dynamics 365 Finance 追蹤採購收據的應計專案成本。
author: sunfzam
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: roschlom
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7ae2f57e0104a30492363f1576962d36a2a1b04b
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451023"
---
# <a name="project-cost-accrual-on-purchase-receipts"></a>採購收據上的應計專案成本

[!include [banner](../includes/banner.md)]

本主題說明如何在 Microsoft Dynamics 365 Finance 追蹤採購收據的應計專案成本。 

專案發票往往比貨物和服務的交付時間晚送達，這可能對專案關鍵績效指標 (KPI) 產生重大影響。 能在財務和專案報表追蹤這些交易很重要。

下列範例方案圖說這一點。 

Contoso Consulting 已經啟動新雲端部署專案。 已建立訂購單購買此專案使用的電腦。 電腦將花費 $1500，而安裝服務將花費 $150。 廠商已經交付並且安裝電腦，但發票尚未送達 Contoso Consulting。 專案經理希望在發票交付前看見 $1650 的專案應計成本。 此成本也應該反映在公司的月末財務報表。 

應計成本必須進行財務級和專案級記錄，以達到報表編製目的。 產品收據的財務更新可針對品項和採購類別追蹤。 

以品項而言，請在 **應付帳款參數** 頁面，選取 **將產品收據過帳到分類帳** 選項。
[![應付帳款參數頁面。](./media/accruals1-1024x409.png)](./media/accruals1.png) 

以採購類別而言，請在 **類別政策規則** 頁面上，選取 **購買** 政策，接著選取各類採購的 **收貨時應計採購支出**。
[![類別政策規則頁面。](./media/accruals2-1024x569.png)](./media/accruals2.png) 

**過帳設定** 的 **未開立發票的採購支出** 和 **採購應計** 科目將在過帳產品收據相關的憑單時使用。

讓我們使用相同方案，查看過帳產品收據將如何影響總帳和專案資訊。 

**步驟 1：** 建立並確認專案的新訂購單，記錄 $1500 的電腦購買和 $150 的安裝服務。
[![建立新訂購單。](./media/accruals4-1024x497.png)](./media/accruals4.png) 

確認訂購單時，會為專案建立承諾成本的交易。 
[![已建立交易。](./media/accruals5-1024x219.png)](./media/accruals5.png) 

> [!NOTE]
> 承諾成本交易的 **交易起源** 欄位設定為 **訂購單**。 建立和確認訂購單不為專案建立交易。 

**步驟 2：** 貨物和服務順利交付並登記產品收據。 

過帳產品收據將產生及過帳憑單到分類帳。 憑單將借記購買支出、未開立發票科目和貸記購買應計科目。 
[![憑單交易。](./media/accruals6-1024x214.png)](./media/accruals6.png)

> [!NOTE]
> 過帳產品收據將使用採購類別和產品的過帳設定，而不是專案類別的過帳設定。 為了正確反映購買應計項目的財務影響，這項設定需要校正。 

可以在 **採購類別** 頁測繪採購類別到專案類別。
[![採購類別頁面。](./media/accruals7-1024x390.png)](./media/accruals7.png)

**步驟 3：** 建立廠商發票草稿。 

過帳產品收據不會影響專案資訊。 您可以在過帳購買收據後直接產生廠商發票草稿，這是變通辦法。 前往 **訂購單** 頁&gt;**發票索引標籤**&gt;**產生**&gt;**發票**。 此舉建立待處理發票文件，更新專案資訊。 

建立廠商發票草稿將產生待處理的專案交易。 
[![待處理專案交易。](./media/accruals8-1024x225.png)](./media/accruals8.png) 

在 **承諾成本** 頁面中，步驟 1 建立的記錄將會關閉，並建立新記錄反映來自待處理廠商發票的承諾成本。 **交易起源** 承諾成本欄位將設定為 **廠商發票**。
[![承諾成本頁面。](./media/accruals9-1024x200.png)](./media/accruals9.png)

廠商發票將保持待處理狀態，直到實際廠商發票送達。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
