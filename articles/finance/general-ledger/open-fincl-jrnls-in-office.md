---
title: 在 Office 中開啟財務日記帳範本
description: 本文章描述了使用 Microsoft Excel 範本建立自訂財務日記帳時可能出現的問題。
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a29ab1cb2980ebfed6c6fa6409538bc802849156
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896339"
---
# <a name="open-financial-journal-templates-in-office"></a>在 Office 中開啟財務日記帳範本

[!include [banner](../includes/banner.md)]

本文章描述了使用 Microsoft Excel 範本建立自訂財務日記帳時可能出現的問題。

## <a name="symptom"></a>徵兆

您為財務日記帳建立了一個自訂 Excel 範本，但 **在 Excel 中開啟資料行** 功能表卻未顯示該範本。 或者，該範本確實出現在功能表上，但當您選取開啟時卻是不同的範本。

## <a name="resolution"></a>解決方法

預設的在 Excel 中開啟功能會使用目前頁面的根資料來源 (資料表)，來決定要將哪些 Office 範本或資料實體顯示為 **在 Excel 中開啟** 的功能表選項。 這種行為對於財務日記帳來說不是理想的體驗，因為財務日記帳會將相同資料表 (LedgerJournalTable 和 LedgerJournalTrans) 做為許多其他類型日記帳的根資料來源。

對於財務日記帳，在 Excel 中開啟資料行功能主要顯示的範本是專為您目前使用的日記帳環境所設計，例如一般日記帳或付款日記帳。 例如，若範本是專為搭配廠商付款日記帳使用設計，則該範本會強制將您的主要帳戶設為廠商帳戶。

如果您想推廣某個範本，以便 **在 Excel 中開啟資料行** 和 **在 Excel 中開啟** 功能表顯示該範本，您可以實作 **LedgerIJournalExcelTemplate** 介面和擴充 **DocuTemplateRegistrationBase** 類別，以提供簡單的開發人員體驗。 系統中有很多實作這種方法的範例。 其中一個可以參考的範例是 **LedgerDailyJournalExcelTemplate** 介面，其是針對一般日記帳 (或日記帳) 而建立。

當您為範本實作 **LedgerIJournalExcelTemplate** 介面時，**在 Excel 中開啟資料行** 功能表即會依據您日記帳的日記帳類型篩選範本，並僅顯示該日記帳可用的範本。 該介面還提供了一個驗證方法，可確保在未符合帳戶類型要求的情況下無法開啟日記帳範本。 例如，您可以指定帳戶類型必須為 **廠商** 或 **分類帳** 類型。

如需此功能的詳細資訊，請參閱[將範本新增到在 Excel 中開啟資料行功能表](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md)。
