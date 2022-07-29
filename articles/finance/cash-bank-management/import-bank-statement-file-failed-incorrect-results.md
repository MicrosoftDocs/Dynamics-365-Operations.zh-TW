---
title: 銀行對帳單檔案匯入排除障礙
description: 來自銀行的銀行對帳單檔案與 Microsoft Dynamics 365 Finance 支援的版面相符很重要。 由於銀行對帳單標準極其嚴謹，大多數整合將能正確運作。 不過對帳單檔案偶爾無法匯入或結果不正確。 這些問題通常起因於銀行對帳單檔案的微小差異。 本文解釋如何修正這些差異和解決問題。
author: panolte
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc5b9cf3449b48767a27891a019f8fe8df2a900559898e3cb1849d25bec7c987
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450594"
---
# <a name="bank-statement-file-import-troubleshooting"></a>銀行對帳單檔案匯入排除障礙

[!include [banner](../includes/banner.md)]

來自銀行的銀行對帳單檔案與 Microsoft Dynamics 365 Finance 支援的版面相符很重要。 由於銀行對帳單標準極其嚴謹，大多數整合將能正確運作。 不過對帳單檔案偶爾無法匯入或結果不正確。 這些問題通常起因於銀行對帳單檔案的微小差異。 本文解釋如何修正這些差異和解決問題。

## <a name="what-is-the-error"></a>錯誤是什麼？

待您嘗試匯入銀行對帳單檔案後，請前往資料管理工作歷程及其執行細節尋找錯誤。 錯誤可藉由點出對帳單、餘額或對帳單行幫助找出。 不過，它不太可能提供足夠的資訊幫助您辨識正造成問題的欄位或元素。

> [!NOTE]
> 匯入的銀行對帳單只能重疊於一個時間點。  例如，如果對帳單在 2021 年一月 1 日凌晨 12:00 結束，則下一次對帳單的開始日期會是 2021 年一月 1 日凌晨 12:00，12:00:00 AM。

## <a name="what-are-the-differences"></a>差異在哪裡？
比較銀行文檔案版面定義與 Finance 匯入定義，並留意欄位和元素中的任何差異。 比較銀行對帳單檔案和相關的樣本財務檔案。 在 ISO20022 檔案中，任何差異都應該很容易看出。

## <a name="time-zone-differences-on-imported-bank-statements"></a>匯入的銀行對帳單的時區差異
匯入檔案的日期時間值會與 財務與營運顯示的日期時間值不同。 為了防止這個歧異，請在 **配置資料來源** 頁輸入時區偏好。 更多有關輸入時區偏好的資訊，請參閱[設定進階銀行對帳匯入流程](set-up-advanced-bank-reconciliation-import-process.md)。

## <a name="transformations"></a>轉換
通常更改必須在三個轉換其中一個進行。 每個轉換都針對特定標準寫入。

| 資源名稱                                         | 檔案名稱                          |
|-------------------------------------------------------|------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt            | BAI2CSV-to-BAI2XML.xslt            |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt | ISO20022XML-to-Reconciliation.xslt |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt          | MT940TXT-to-MT940XML.xslt          |

## <a name="debugging-transformations"></a>BUG 轉換
### <a name="adjust-the-bai2-and-mt940-files"></a>調整 BAI2 和 MT940 檔案

BAI2 和 MT940 檔案皆為文字型檔案，需要調整才能啟用 Extensible Styleheet Language Transformations (XSLT) BUG 。 程式在匯入檔案時調整。

1.  建立 XML 檔案，並複製文字如下。

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  複製銀行對帳單檔案的內容，並貼到 XML 檔案，以便更換 **PASTESTATEMENTFILEHERE**。

### <a name="debug-the-xslt"></a>XSLT BUG 

更多資訊，請參閱 <https://msdn.microsoft.com/library/ms255605.aspx>。

1.  開始 Microsoft Visual Studio。
2.  建立主控台應用程式。
3.  打開適當的 XSLT。
4.  點選 XLST 與其屬性頁面。
5.  將輸入設定為銀行對帳單檔案的位置。
6.  定義輸出的位置和檔名。
7.  設定所需的斷點。
8.  在功能表上，點選 **XML**&gt;**開始 XSLT 偵錯**。

### <a name="format-the-xslt-output"></a>格式化 XSLT 輸出

當轉換執行時，它會建立輸出檔案，方便您在 Visual Studio 檢視。 使用 Ctrl+A、Ctrl+K 和 Ctrl+D 快速格式化輸出檔案。

### <a name="adjust-the-transformation"></a>調整變換

調整轉換以便取得銀行對帳單檔案的適當欄位或元素。 接著將該欄位或元素對應到適當的 Finance 元素。

### <a name="debitcredit-indicator"></a>借方/貸方指標

借方偶爾可能當成貸方匯入，而貸方可能當成借方匯入。 若要解決此問題，您必須更改適當的 XSLT。 如果銀行對帳單來自多間銀行，請確定它們都使用相同的借記/貸記方法，或建立單獨的轉換。

-   BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator 範本
-   ISO20022XML-to-Reconcilation.xslt GetCreditDebit 範本
-   MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator 範本

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>銀行對帳單格式和技術版面範例
下列資料表列出進階銀行對帳匯入檔案和三個銀行對帳單相關範例檔案的技術版面定義範例。 您可以這裡下載範例檔案和技術版面：[匯入檔案範例](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| 技術版面定義                             | 銀行對帳單範例檔案          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| DynamicsAXISO20022Layout                                | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout                                    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
