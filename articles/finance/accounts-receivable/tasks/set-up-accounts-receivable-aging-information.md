---
title: 設定和產生應收帳款的帳齡資料
description: 本指南將幫助您設定帳齡期間定義、帳齡客戶餘額以及查看 [帳齡餘額] 清單和 [收帳] 頁面的餘額。
author: abruer
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 996fb289c32a1819103fd67ffddc940dfd2870fb
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2021
ms.locfileid: "8451149"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a>設定和產生應收帳款的帳齡資料

[!include [banner](../../includes/banner.md)]

本指南將幫助您設定帳齡期間定義、帳齡客戶餘額以及查看 [帳齡餘額] 清單和 [收帳] 頁面的餘額。 此錄製內容使用 USMF 示範公司。


## <a name="create-an-aging-period-definition"></a>建立帳齡期間定義
1. 前往 **導覽窗格 > 模組 > 信用和收帳 > 設定 > 帳齡期間定義**。
2. 按一下 **新建**。
3. 在 **帳齡期間** 欄位中，輸入一個值。
4. 在 **描述** 欄位中，輸入一個值。
5. 按一下 **在底下加入** 插入新的帳齡期間。
6. 在 **期間** 欄位中，輸入在帳齡報告中顯示的說明。
7. 在 **單位** 欄位中，輸入一個數字。
8. 在 **間隔** 欄位中，選擇一個選項。 分類帳期間與您的分類帳日曆相符。 日、週、月、季和年定義日期類型的間隔範圍。 根據是否為首個或最後期間，無限制選擇前一期間之前或之後的所有交易。  
9. 在 **帳齡指示器** 欄位中，選擇一個選項。
10. 在網格頂部選擇期間。 更新該說明以描述帳齡期間定義的最早期間
11. 在 **期間** 欄位中，輸入帳齡期間的新說明。
12. 關閉頁面。

## <a name="age-the-balances"></a>帳齡餘額
1. 前往 **信用和收帳 > 定期任務 > 帳齡客戶餘額**。
2. 在 **帳齡期間定義** 欄位中，選擇您建立的帳齡期間定義。
    + 您可以取得每個帳齡期間定義的使用中快照。  
    + 根據預設處理所有客戶。 您可以使用此選擇計算單個收帳客戶群。  
    + 從交易中選擇您將用於帳齡的日期。  
    + 選擇帳齡的「截止」日期。 預設日期為今天，但是如果將此欄位更改為「選定的日期」，您將能夠選取所需的日期。 對於批次處理，使用今天的日期。  
3. 展開 **公司** 範圍。 您可以選擇想加入快照的公司。 預設為選擇目前的公司。
4. 按一下 **確定** 處理快照。 處理需要一些時間，因此請等待滑桿消失並檢查訊息中心的訊息。

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a>查看帳齡餘額清單和收帳頁面上的餘額
1. 前往 **信用和收帳 > 收帳 > 帳齡餘額**。 清單頁面顯示客戶餘額。 帳齡圖示顯示最早交易的帳齡期間。  
2. 選擇有餘額的客戶。
3. 展開 **帳齡速見表** 框，以查看帳齡餘額。 速見表的帳齡期間定義取自參數中設定的預設帳齡期間。 您可以使用 [收帳] 選單進行更改。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
