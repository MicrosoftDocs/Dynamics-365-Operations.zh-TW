---
title: 廠商發票日期
description: 本主題介紹廠商發票上顯示的日期。 它還解釋了如何設定系統好讓其自動調整過帳日期。
author: sunfzam
ms.date: 2/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 064a125d448ebb3511db2d9b1f4228380805dc44
ms.sourcegitcommit: f2a78e0d7d461ca843ac2f9abff7690275db9196
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8451521"
---
# <a name="vendor-invoice-dates"></a>廠商發票日期

[!include [banner](../includes/banner.md)]

本主題介紹廠商發票上顯示的日期。 它還解釋了如何設定系統好讓其自動調整過帳日期。

在 **待處理廠商發票詳情** 頁面，發票標題顯示四個日期：發票收到日期、發票日期、過帳日期和到期日。 建立廠商發票時，預設輸入以下日期：

- **發票收到日期** – 此欄位設定為目前系統日期。
- **過帳日期** – 此欄位設定為目前系統日期。 
- **到期日** – 此欄位中的日期是根據過帳日期和付款條件計算的。
- **發票日期** – 預設情況下，此欄位為空白。 但是，您可以根據需要輸入該值。 在該情況下，**到期日** 欄位中的日期是根據發票日期和付款條件重新計算的。

有時，廠商發票可能在期間結束後很長一段時間內處於待處理狀態。 準備過帳時，仍使用過去過帳期間的舊過帳日期。 然而，那段期間現在已經結束。 因此，應付帳款 (AP) 記帳員必須手動將所有過帳日期更改為之前建立的所有待處理發票的新過帳期間。

本主題中描述的功能可讓您設定系統，使其根據業務需求自動調整過帳日期。

## <a name="parameter-for-automatically-adjusting-the-vendor-invoice-posting-date"></a>自動調整廠商發票過帳日期的參數

按照以下步驟啟用系統以自動調整廠商發票的過帳日期。

1.  前往 **應付帳款\>設定\>應付帳款參數**。
2.  在 **分類帳和銷售稅** 索引標籤，**自動調整過帳日期** 欄位，選取以下值之一：

    - **不用更改** – 過帳期間系統不會自動更改過帳日期。 預設選取此值。
    - **不斷將過帳日期更改為系統日期** – 系統在過帳時自動將過帳日期更改為系統日期。
    - **在過帳日期期間關閉或暫停時將過帳日期更改為系統日期** – 系統在過帳期間將過帳日期更改為系統日期，但前提是過帳日期的相應期間的狀態為 **關閉** 或 **暫停**。
    - **在過帳日期期間關閉或暫停時將過帳日期更改為新期間第一天** – 系統將過帳日期更改為新開啟期間第一天，但前提是過帳日期的相應期間的狀態為 **關閉** 或 **暫停**。

> [!NOTE]
> 如果自動調整的新過帳日期在新的會計年度，則發票的過帳日期不會更新。 使用者將收到錯誤訊息「會計年度已更改。 請檢查並重新輸入過帳日期。」 發票過帳日期必須更新為新的會計年度日期才能過帳。

## <a name="impact-of-posting-date-changes"></a>過帳日期更改的影響

當暫止廠商發票上的過帳日期更改時，更改會產生以下影響：

- **到期日**

    - 如果 **發票日期** 欄位為空白，到期日會根據新的過帳日期和付款條件重新計算。
    - 如果 **發票日期** 欄位之前已設定好，過帳日期更改不會影響到期日。

- **現金折扣日期**

    - 如果 **發票日期** 欄位為空白，新的過帳日期則用於計算現金折扣。
    - 如果 **發票日期** 欄位之前已設定好，現金折扣不會更改。

- **匯率** - 匯率日期由 **更新廠商會計的設定決定**，使用 **應付帳款** 參數頁面（**應付帳款\>設定\>應付帳款參數**）的 **發票** 索引標籤的發票日期選項。

    - 如果此選項設定為 **是的**，使用的發票日期和過帳日期更改不影響匯率。
    - 如果此選項設定為 **不是**，過帳日期則用於計算匯率。 更新過帳日期時，會重新計算會計和報告金額。 因此，必須再次進行比對驗證。

## <a name="validation"></a>驗證

其他兩個 **應付帳款參數** 頁面（**應付帳款\>設定\>應付賬款參數**）的 **發票** 索引標籤的欄位會影響發票處理：

- 如果 **檢查使用的發票號碼** 欄位設定為 **在會計年度內拒絕重複**，系統在發票過帳期間使用過帳日期檢查重複發票。
- 如果將 **要求廠商發票上的文件日期** 欄位設定為 **錯誤選項**，**待處理發票標題上的發票日期** 欄位為必填資訊。 如果發票日期晚於過帳日期，系統會顯示錯誤訊息。
