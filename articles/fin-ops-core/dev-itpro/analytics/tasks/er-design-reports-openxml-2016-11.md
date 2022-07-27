---
title: ER 設計用於產生 OPENXML 格式報告的設定 (2016 年 11 月)
description: 本主題描述如何創建新的電子報表設定，其中包含用於產生 OPENXML 格式的電子文件的範本。
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERModelGroupByFunctionEditor, VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c3dfe6ce9c918b5fccbd7097096fa359facdf41bbf6fd0fab6c61153171484cd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460269"
---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a>ER 設計用於產生 OPENXML 格式報告的設定 (2016 年 11 月)

[!include [banner](../../includes/banner.md)]

本主題說明系統管理員或電子報表開發人員角色的使用者如何創建新的電子報表 (ER) 設定，其中包含用於產生 OPENXML 格式的電子文件的範本。 此設定將用於處理廠商付款。

在此範例中，您將為樣本公司 Litware, Inc 創建一個設定。這些步驟可以在 GBSI 公司中執行。

若要完成這些步驟，您必須先完成「建立設定提供者並將其標記為有效」程序中的步驟。 您還必須有一個將在創建範本時匯入的 Excel 檔案。 可以從[付款報告範本](https://download.microsoft.com/download/3/f/0/3f0658b2-042c-43cf-a776-0f4c7f7cfe4e/SampleVendPaymWsReport.xlsx)存取此檔案。


## <a name="upload-the-payments-data-model-configuration"></a>上傳付款資料模型設定
1. 在瀏覽窗格中，進入 **模組 > 組織管理 > 工作區 > 電子報表**。
2. 在清單中，標記樣本公司 Litware, Inc. 的設定提供者。如果您沒有看到此設定提供者，則必須先完成[創建設定提供者並將其標記為作用中](er-configuration-provider-mark-it-active-2016-11.md)中的步驟。
3. 選取 **設定為作用中**。
4. 選取 **存放庫**。 為營運資源類型選取儲存庫 (如果可用)。 如果可用，請跳過以下有關創建新存放庫的步驟。  
5. 選取 **新增** 打開下拉式對話方塊。
6. 在 **設定存放庫類型** 欄位中，輸入 `Operations resourcesdd`。
7. 選取 **創建存放庫**。
8. 選取 **確定**。
9. 請選取 **打開**。
10. 在樹狀結構中，選取 **付款模型**。
11. 選取 **匯入**。 匯入此資料模型。 它將用作新格式設定中的資料來源。 如果已匯入此設定，請跳過此步驟。  
12. 選取 **是**。
13. 關閉頁面，直到您返回到電子報表頁面。

## <a name="create-a-new-format-configuration"></a>建立新的格式設定
1. 選取 **報表設定**。
2. 在樹狀結構中，選取 **付款模型**。
3. 選取 **創建設定** 以打開下拉式對話方塊。
4. 在 **新建** 欄位中，輸入 `Format based on data model PaymentModel`。 創建基於 PaymentModel 資料模型的格式。
5. 在 **名稱** 欄位，輸入 `Sample worksheet report`。 樣本工作表報告  
6. 在 **描述** 欄位中，輸入 `Sample worksheet report for vendors' payments`。 廠商付款的樣本工作表報告。  
7. 在 **資料模型** 定義欄位中，輸入或選取一個值。 選取 **CustomerCreditTransferInitiation** 定義。  
8. 選取 **建立設定**。

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>設計一個 OPENXML 工作表格式的新文件
1. 在樹狀結構中，選取 **付款模式\樣本工作表報告**。
2. 選取 **設計工具**。
3. 在動作窗格上，選取 **匯入**。
4. 選取 **從 Excel 匯入**。
5. 選取 **附件**。 將現有 Excel 文件附加為範本。  
6. 選取 **新建**。
7. 選取 **檔案**。 指向現有的 Excel 檔案。  
8. 關閉頁面。
9. 在 **範本** 欄位中，輸入或選取一個值。 選取要用作範本的附加 Excel 檔案。  
10. 選取 **確定**。 請注意，ER 格式組件是根據參考的 MS Excel 文件 (命名範圍) 的結構以設計格式創建的。  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>創建新資料來源以按貨幣代碼計算總額
1. 選取 **對應** 索引標籤。
2. 選取 **新增根** 打開下拉式對話方塊。
3. 在樹狀結構中，選取 **函數\分組依據**。
4. 在 **名稱** 欄位，輸入 `PaymentByCurrency`。
5. 選取 **編輯分組依據**。
6. 在樹狀結構中，展開 **模型**，然後選取 **模型\付款**。
7. 選取 **新增欄位至**。
8. 選取 **要分組的內容**。
9. 在樹狀結構中，展開 **模型\付款**，然後選取 **模型\付款\貨幣**。
10. 選取 **新增欄位至**。
11. 選取 **分組欄位**.
12. 在樹狀結構中，選取 **模型\付款\指示金額 (InstructedAmount)**。
13. 選取 **將欄位新增到**，然後選取 **彙總欄位**。
14. 在 **方法** 欄位中，選取一個選項。 選取 **SUM 彙總** 函數。  
15. 在 **名稱** 欄位，輸入 `TotalInstructuredAmount`。
16. 選取 **儲存**。
17. 關閉頁面。
18. 選取 **確定**。

## <a name="map-format-components-to-data-sources"></a>將格式組件對應到資料來源
1. 在樹狀結構中，選取 **模型\付款\發起方 (InitiatingParty)\名稱** 和 **Excel\ReportHeader\CompanyName**。
2. 選取 **繫結**。
3. 在樹狀結構中，選取 **模型\付款\債權人\識別\來源 ID (SourceID)** 和 **Excel\PaymLines\VendAccountName**。
4. 選取 **繫結**。
5. 在樹狀結構中，選取 **模型\付款\債權人\名稱** 和 **Excel\PaymLines\VendName**。
6. 選取 **繫結**。
7. 在樹狀結構中，選取 **模型\付款\債權代理人 (CreditorAgent)\名稱** 和 **Excel\PaymLines\Bank**。
8. 選取 **繫結**。
9. 在樹狀結構中，選取 **模型\付款\債權代理人 (CreditorAgent)\路由編號 (RoutingNumber)** 和 **Excel\PaymLines\RoutingNumber**。
10. 選取 **繫結**。
11. 在樹狀結構中，選取 **模型\付款\債權人帳戶 (CreditorAccount)\識別\編號** 和 **Excel\PaymLines\AccountNumber**。
12. 選取 **繫結**。
13. 在樹狀結構中，選取 **模型\付款\指示金額 (InstructedAmount)** 和 **Excel\PaymLines\Debit**。
14. 選取 **繫結**。
15. 在樹狀結構中，選取 **模型\付款\貨幣** 和 **Excel\PaymLines\Currency**。
16. 選取 **繫結**。
17. 在樹狀結構中，選取 **PaymentByCurrency\grouped\Currency** 和 **Excel\SummaryLines\SummaryCurrency**。
18. 選取 **繫結**。
19. 在樹狀結構中，選取 **PaymentByCurrency\aggregated\TotalInstructuredAmount** and **Excel\SummaryLines\SummaryAmount**。
20. 選取 **繫結**。
21. 在樹狀結構中，選取 **PaymentByCurrency** 和 **Excel\SummaryLines**。
22. 選取 **繫結**。
23. 在樹狀結構中，選取 **模型\付款** 和 **Excel\PaymLines**。
24. 選取 **繫結**。
25. 請選取 **儲存**，然後關閉此頁。

## <a name="use-the-created-configuration-for-payments-processing"></a>使用創建的設定進行付款處理
1. 選取 **更改狀態**。
2. 選取 **完成**。
3. 選取 **確定**。
4. 在瀏覽窗格中，進入 **模組 > 應付帳款 > 付款安裝 > 付款方式**。
5. 使用快速過濾器過濾值為 **電子** 的 **付款方式** 欄位。
6. 選取 **編輯**。
7. 展開 **檔案格式** 區段。
8. 在 **常用電子報表** 欄位中選取 **是**。
9. 在 **匯出格式設定** 欄位中，輸入或選取一個值。 選取 **樣本工作表報告** 設定。  
10. 選取 **儲存**。
11. 關閉頁面。

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>使用創建的設定測試付款日記帳處理
1. 在瀏覽窗格中，進入 **瀏覽窗格 > 模組 > 應付帳款 > 付款 > 付款日記帳**。
2. 選取 **新建** 建立新的付款日記帳。
3. 在 **名稱** 欄位，輸入 **VendPay**。
4. 選取 **明細**。
5. 在 **帳戶** 欄位中，指定值 `GB_SI_000001`。
6. 將 **借方** 設定到 `1000`。
7. 選取 **新建**。
8. 在 **帳戶** 欄位中，指定值 `GB_SI_000005`。
9. 將 **借方** 設定到 `2000`。
10. 在 **貨幣** 欄位，輸入 `EUR`。
11. 在 **沖銷帳戶** 欄位中，指定值 `GBSI OPER`。
12. 在 **付款方式** 欄位中，輸入 `Electronic`。
13. 選取 **儲存**。
14. 選取 **產生付款**。
15. 在 **付款方式** 欄位中，輸入 `Electronic`。
16. 在 **檔案名稱** 欄位，輸入 `Payments`。
17. 在 **銀行帳戶** 欄位，輸入 `GBSI OPER`。
18. 選取 **確定**，然後再次選取 **確定**。 查看創建的工作表，包括付款行的詳情以及此付款訊息中使用的每種貨幣代碼的總計。  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
