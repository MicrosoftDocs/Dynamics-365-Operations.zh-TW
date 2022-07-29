---
title: 會計行事曆、會計年度和期間
description: 本文討論會計日曆、會計年度和期間以及如何將它們用於法人實體、固定資產和預算。
author: aprilolson
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FiscalCalendars
audience: Application User
ms.reviewer: roschlom
ms.custom: 25851
ms.assetid: a968a5e5-585e-4389-aa4e-c885a7e23413
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87d06e9de2e4e360e92ed350dbad6350744e69ed79a30d2956ab598fdc8a9821
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450345"
---
# <a name="fiscal-calendars-fiscal-years-and-periods"></a>會計行事曆、會計年度和期間

[!include [banner](../includes/banner.md)]

本文討論會計日曆、會計年度和期間以及如何將它們用於法人實體、固定資產和預算。

會計日曆為組織的財務活動提供了一個框架。 每個會計日曆包含一個或多個會計年度，每個會計年度包含多個期間。 會計日曆可以基於日曆年的 1 月 1 日至 12 月 31 日，也可以基於您選擇的任何日期。 例如，某些組織選擇從一年的 7 月 1 日開始到次年 6 月 30 日結束的會計日曆。 

您可以創建的會計日曆的數量沒有限制，並且可以為一個會計日曆創建的會計年度的數量沒有限制。 每個會計日曆都獨立於您的組織，並且可以由組織中的多個法人實體使用。 例如，一個組織有八個部門，每個部門都是一個獨立的法人實體。 其中五個共享相同的會計日曆，三個使用不同的會計日曆。 您可以為共享同一會計日曆的五個法人創建一個會計日曆，然後為其他法人創建單獨的會計日曆。

## <a name="create-fiscal-calendars-fiscal-years-and-periods"></a>建立會計行事曆、會計年度和期間
您可以在會計日曆頁面上創建和刪除會計日曆、會計年度和期間。 您還可以劃分現有期間並創建可用於關閉會計年度的關閉期間。 

關閉期間用於分隔會計年度關閉時生成的總帳交易。 當結帳交易在一個會計期間時，更容易創建包含或排除不同類型的結帳分錄的財務報表。 如果一個會計年度分為 12 個會計期間，則結算期間通常是第 13 個期間。 但是，可以從狀態為「未結」的任何期間創建結帳期間。 

創建結束期間時，請選擇狀態為「未結」且具有您要使用的日期的期間。 新的結束期間將複製現有期間的開始日期和結束日期。 原來的時期將繼續存在。 例如，您選擇期間 12，它是會計年度的最後一個期間，日期為 8 月 1 日至 8 月 31 日。 您輸入結束期間的名稱，例如 Close。 創建新的結算期間後，您現在擁有原始期間和結算期間。 兩者的日期都從 8 月 1 日開始，到 8 月 31 日結束。

## <a name="select-fiscal-calendars-for-ledgers-fixed-assets-and-budget-cycles"></a>為分類帳、固定資產和預算週期選擇會計日曆
會計日曆用於固定資產折舊、財務交易和預算週期。 創建會計日曆時，您可以將其用於多種用途。 您可以為固定資產帳簿選擇會計日曆以使其成為固定資產日曆。 您可以為分類帳選擇一個會計日曆以使其成為分類帳日曆。 您可以為預算週期選擇一個會計日曆以使其成為預算日曆。 您可以對所有這些使用相同的會計日曆。

### <a name="select-a-fiscal-calendar-for-your-legal-entity"></a>為您的法人選擇一個會計日曆

在「分類帳」表單中選擇要用於法人分類帳的會計日曆。 必須在「分類帳」頁面上為每個法人選擇一個會計日曆。 選擇會計日曆後，您可以在「分類帳日曆」頁面上為屬於會計年度的任何期間設置期間狀態和權限。

### <a name="select-a-fiscal-calendar-for-fixed-assets"></a>選擇固定資產的會計日曆

您可以為固定資產帳簿選擇會計日曆，該會計日曆將由使用所選帳簿的固定資產使用。 您可以從財務行事曆頁面中定義的所有財務行事曆中進行選擇。

### <a name="define-budget-cycle-time-spans"></a>定義預算週期範圍

預算週期是使用預算的時間長度。 預算週期可以包括一個財政年度的一部分或多個財政年度，例如兩年的兩年預算週期或三年的三年預算週期。 預算週期時間跨度定義了預算週期中包含的周期數。 要指定預算週期時間跨度，請使用預算週期時間跨度頁面。

## <a name="maintain-periods-for-your-organization"></a>為您的組織維護期間
您可以使用「分類帳日曆」頁面查看您的組織使用的會計日曆、會計年度和期間的詳細資訊。 您還可以更改期間的狀態並選擇哪些用戶可以將會計交易過帳到期間。 例如，在新期間開始時，您可能希望一組用戶在上一期間完成發布財務交易，而其他組僅在新期間工作。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]