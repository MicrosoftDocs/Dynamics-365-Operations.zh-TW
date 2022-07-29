---
title: 處理利息
description: 此段程序顯示如何建立、列印和過帳附息票據。
author: ShivamPandey-msft
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3b97515e29d04866172216fc29af9a8d992568276c5e01acd67ad9d0028ea0c5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450672"
---
# <a name="process-interest"></a>處理利息

[!include [banner](../../includes/banner.md)]

此段程序顯示如何建立、列印和過帳附息票據。 此工作使用 USMF 公司進行示範。


## <a name="set-up-interest-on-the-posting-profile"></a>在過帳設定檔上設定利息
1. 在 **導覽窗格** 中，前往 **模組 > 信貸與收款 > 設定 > 客戶過帳設定檔**。
2. 點選 **編輯**。
3. 在 **設定 fastTab** 的 **利息代碼** 欄位，從下拉式清單選取利息代碼。 如果您不希望使用此過帳設定檔計算交易利息，請將此欄位留空。 **資料表限制** fastTab 允許您更改處理利息的方式。 如果此欄位設定為是，則將計算此過帳設定檔的利息。  

## <a name="calculate-interest"></a>計算利息
1. 在 **導覽窗格** 中，前往 **模組 > 信貸與收款 > 利息 > 建立附息票據**。
2. 您必須選取將計算利息的交易類型。 這些類型的所有未結交易將納入計算。  
3. 如果你設定 **利息** 為 '是'，您將按利息計算利息。 納入這些交易之前，您可能希望查明管轄複利計算的法律。  
4. 在 **開始日期** 欄位，輸入將開始計算利息的日期。 如果你不指明 **開始日期**，則所有未過帳的附息票據將全數取消，而利息將從交易日起重新計算。
5. 在 **截止日期** 欄位，輸入利息計算會截止的日期。
6. 在 **使用過帳設定檔來源** 欄位，選取一個選項。 目前共計三個過帳設定檔選項：
    - 帳戶 – 使用指派給每張附息票據的客戶帳戶的過帳設定檔。 
    - 選取 – 使用您在過帳設定檔欄位選取的過帳設定檔。
    - 交易 – 使用交易的個別過帳設定檔計算每張附息票據的利息。 未曾指派過帳設定檔的交易，將使用在應收帳款參數表單分類帳，和銷售稅區指定的過帳設定檔。  
7. 展開 **預計納入的記錄** fastTab。
8. 點選 **篩選**。
9. 請在 **標準** 欄位，輸入客戶識別碼。 例如，輸入 'US-001'。
6. 點選 **確定**。
7. 點選 **確定**。

## <a name="print-interest-notes"></a>列印附息票據
1. 在 **導覽窗格** 中，前往 **模組 > 信貸與收款 > 利息 > 審核與處理附息票據**。
2. 請在 **狀態** 欄位，選取 '已建立'。
3. 請在 **已列印** 欄位，選取 '未列印'。
4. 點選 **列印**。
5. 展開 **預計納入的記錄** fastTab。
6. 點選 **確定**。
7. 關閉頁面。

## <a name="post-the-interest-note"></a>過帳附息票據
1. 選取準備過帳的附息票據 (狀態已建立)。
2. 點選 **過帳**。
3. 輸入附息票據的過帳日期。 選取是，建立每張附息票據的總帳交易。 如果您不選取是，則客戶的所有附息票據利息全數累積並在一次性交易中過帳到總帳。  
4. 展開 **預計納入的記錄** fastTab。
5. 點選 **確定**。
6. 請在 **狀態** 欄位，選取 '已過帳'。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]