---
title: 偵錯已執行 ER 格式的資料來源以分析資料流程和轉換
description: 本主題說明如何偵錯已執行 ER 格式的資料來源，以更好地了解設定的資料流程和轉換。
author: NickSelin
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 02aee8c6ec3b2720c2fcbb17f15791d88d688a34
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460414"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a>偵錯已執行 ER 格式的資料來源以分析資料流程和轉換

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

當您[設定](tasks/er-format-configuration-2016-11.md)電子報表 (ER) 解決方案以產生輸出文件時，您定義用於從應用程式中獲取資料並將其輸入到產生的輸出中的方法。 為了使 ER 解決方案的生命週期支援更有效，您的解決方案應包含 ER 資料模型及其對應組件，以及 ER 格式及其對應組件，以便模型對應是特定於應用程式的，而其他組件保留與應用程式無關。 因此，幾個 ER 組件可能會影響在產生的輸出中輸入資料的過程。

有時，產生的輸出資料看起來與應用程式資料庫中的相同資料不同。 在這些情況下，您需要確定哪個 ER 組件負責資料轉換。 ER 資料來源偵錯器函數顯著減少了此調查所涉及的時間和成本。 您可以中斷 ER 格式的執行並打開資料來源偵錯器介面。 在那裡，您可以瀏覽可用的資料來源並選取要執行的單個資料來源。 此手動執行模擬 ER 格式實際執行期間資料來源的執行。 結果顯示在一個頁面上，您可以在其中分析接收到的資料。

若要打開資料來源偵錯函數，請將 ER 使用者參數中的 **在格式化執行階段啟用資料偵錯** 選項設定維 **是**。 然後，您可以在執行 ER 格式以產生輸出文件時啟動資料來源偵錯。 您還可以使用 **開始偵錯** 選項為在 [ER Operation 設計工具](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document)中設定的 ER 格式啟動資料來源偵錯。

本主題提供了為執行的 ER 格式啟動資料來源偵錯的指南。 它解釋了這些資訊如何幫助您了解資料流程和資料轉換。 本主題中的範例使用業務流程進行廠商付款處理。

## <a name="limitations"></a>限制

資料來源偵錯器可用於存取以 ER 格式執行以產生輸出文件的資料來源的資料。 它不能用於偵錯旨在剖析輸入文件的 ER 格式的資料來源。

ER 格式的以下設定現行無法用於資料來源偵錯：

- 格式轉換
- 格式和對應驗證規則
- 啟用運算式
- 記憶體式資料收集的詳情

## <a name="prerequisites"></a>先決條件

- 若要完成本主題中的範例，您必須有權存取以下[角色](../sysadmin/tasks/assign-users-security-roles.md)之一：

    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

- 該公司必須設定為 **DEMF**。

- 按照本主題[附錄 1](#appendix1) 中的步驟下載處理廠商付款所需的 Microsoft ER 解決方案組件。
- 按照本主題[附錄 2](#appendix2) 中的步驟，使用您將下載的 ER 解決方案為廠商付款處理準備應付帳款。

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a>處理廠商付款以取得付款檔案

1. 按照本主題[附錄 3](#appendix3) 中的步驟處理廠商付款。

    ![正在處理廠商付款。](./media/er-data-debugger-process-payment.png)

2. 下載 ZIP 檔案並將其儲存到本地電腦。
3. 從 ZIP 檔案中提取 **ISO20022 貸記轉帳.xml** 付款檔案。
4. 使用 XML 檔案檢視器打開提取的付款檔案。

    在付款檔案中，廠商銀行帳戶的國際銀行帳號 (IBAN) 代碼不包含空格。 因此，它不同於在 **銀行帳戶** 頁面上[輸入](#enteredIBANcode)的值。

    ![沒有空格的 IBAN 代碼。](./media/er-data-debugger-payment-file.png)

    您可以使用 ER 資料來源偵錯器來了解 ER 解決方案的哪個組件用於截斷 IBAN 代碼中的空格。

## <a name="turn-on-data-source-debugging"></a>打開資料來源偵錯

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 將 **在格式化執行階段啟用資料偵錯** 選項設定為 **是**。

    > [!NOTE]
    > 此參數是使用者專用和公司專用。

    ![使用者參數對話方塊。](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a>處理廠商付款以進行偵錯

1. 按照本主題[附錄 3](#appendix3) 中的步驟處理廠商付款。
2. 在訊息方塊中，選取 **是** 以確認您要中斷廠商付款處理，而是在 **偵錯資料來源** 頁面上啟動資料來源偵錯。

    ![確認訊息方塊。](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a>偵錯付款處理中使用的資料來源

### <a name="debug-the-model-mapping"></a>偵錯模型對應

1. 在 **偵錯資料來源** 頁面，在動作窗格上，選取 **模型對應** 從這個 ER 組件開始偵錯。
2. 在左側的資料來源窗格中，選取 **\$notSentTransactions** 資料來源，然後選取 **讀取所有記錄**。

    您可以選取 **讀取 1 條記錄**、**讀取 10 條記錄**、**讀取 100 條記錄**，或 **讀取所有記錄** 來強制從選定的資料來源中讀取適當數量的記錄。 透過這種方式，您可以模擬從正在執行的 ER 格式對資料來源的存取。

3. 在右側的資料窗格中，選取 **展開全部**。

    可以看到，**記錄清單** 類型的選定資料來源包含一條記錄。

4. 展開 **\$notSentTransactions** 資料來源，並選取巢狀 **vendBankAccountInTransactionCompany()** 方法。
5. 展開 **vendBankAccountInTransactionCompany()** 方法，並選取巢狀 **IBAN** 欄位。
6. 選取 **取得價值**。

    您可以選取 **取得價值** 來強制讀取選定資料來源的選定欄位的值。 透過這種方式，您可以模擬從正在執行的 ER 格式對該欄位的存取。

7. 選取 **展開全部**。

    ![模型對應中 IBAN 欄位的值。](./media/er-data-debugger-debugging-model-mapping.png)

    如您所見，模型對應不負責截斷空格，因為它為廠商銀行帳戶返回的 IBAN 代碼包含空格。 因此，您必須繼續進行資料來源偵錯。

### <a name="debug-the-format-mapping"></a>偵錯格式對應

1. 在 **偵錯資料來源** 頁面，在動作窗格上，選取 **格式對應** 從這個 ER 組件繼續偵錯。
2. 選取 **\$PaymentByDebtor** 資料來源，然後選取 **讀取所有記錄**。
3. 展開 **\$PaymentByDebtor**。
4. 展開 **\$PaymentByDebtor.Lines**，然後選取 **讀取所有記錄**。
5. 展開 **\$PaymentByDebtor.Lines.CreditorAccount**。
6. 展開 **\$PaymentByDebtor.Lines.CreditorAccount.Identification**，然後選取 **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**。
7. 選取 **取得價值**。
8. 選取 **展開全部**。

    ![格式對應中 IBAN 欄位的值。](./media/er-data-debugger-debugging-format-mapping.png)

    如您所見，格式對應的資料來源不負責截斷空格，因為它們為廠商銀行帳戶返回的 IBAN 代碼包含空格。 因此，您必須繼續進行資料來源偵錯。

### <a name="debug-the-format"></a>偵錯格式

1. 在 **偵錯資料來源** 頁面，在動作窗格上，選取 **格式** 從這個 ER 組件繼續偵錯。
2. 展開格式元素選取 **ISO20022CTReports**\>**XMLHeader**\>**Document**\>**CstmrCdtTrfInitn**\>**PmtInf**，然後選取 **讀取所有記錄**。
3. 展開格式元素選取 **ISO20022CTReports**\>**XMLHeader**\>**Document**\>**CstmrCdtTrfInitn**\>**PmtInf**\>**CdtTrfTxInf**，然後選取 **讀取所有記錄**。
4. 展開格式元素選取 **ISO20022CTReports**\>**XMLHeader**\>**Document**\>**CstmrCdtTrfInitn**\>**PmtInf**\>**CdtTrfTxInf**\>**CdtrAcct**\>**Id**\>**IBAN**\>**BankIBAN**，然後選取 **取得值**。
5. 選取 **展開全部**。

    ![格式中 IBAN 欄位的值。](./media/er-data-debugger-debugging-format.png)

   如您所見，格式繫結不負責截斷空格，因為它為廠商銀行帳戶返回的 IBAN 代碼包含空格。 因此，設定 **BankIBAN** 元素以使用截斷空格的格式轉換。

6. 關閉資料來源偵錯器。

### <a name="review-the-format-transformations"></a>查閱格式轉換

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面，選取 **付款模型**\>**ISO20022 貸記轉帳**。
3. 選取 **設計工具**，然後展開元素來選取 **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**。

    ![格式設計工具頁面上的 BankIBAN 元素。](./media/er-data-debugger-referred-transformation.png)

    如您所見，設定 **BankIBAN** 元素以使用 **移除非英數字元** 轉換。

4. 選取 **轉換** 索引標籤。

    ![BankIBAN 元素的轉換索引標籤。](./media/er-data-debugger-transformation.png)

    如您所見，設定 **移除非英數字元** 轉換以使用從提供的文字字串中截斷空格的運算式。

## <a name="start-to-debug-in-the-operation-designer"></a>開始在 Operation 設計工具中偵錯

當您設定可以直接從 Operation 設計工具執行的 ER 格式的草稿版本時，您可以透過選取存取資料來源偵錯器 **開始偵錯** 在動作窗格上。

![格式設計工具頁面上的開始偵錯按鈕。](./media/er-data-debugger-run-from-designer.png)

正在編輯的 ER 格式的格式對應和格式組件可用於偵錯。

## <a name="start-to-debug-in-the-model-mapping-designer"></a>開始在對應模型設計工具中偵錯

當您設定可以從 **模型對應** 頁面執行的 ER 模型對應時，您可以透過在動作窗格上選取 **開始偵錯** 來存取資料來源偵錯器。

![開始偵錯按鈕模型對應設計工具頁面。](./media/er-data-debugger-run-from-designer-mapping.png)

正在編輯的 ER 對應的模型對應組件可用於偵錯。

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a>附錄 1：取得 ER 解決方案

### <a name="download-an-er-solution"></a>下載 ER 解決方案

如果您想使用 ER 解決方案為處理的廠商付款產生電子付款檔案，您可以 [下載](download-electronic-reporting-configuration-lcs.md) **ISO20022 貸記轉帳** ER 付款格式，該格式可從 Microsoft Dynamics Lifecycle Services (LCS) 的共用資產庫或全域存放庫。

![在設定存放庫頁面上匯入 ER 付款格式。](./media/er-data-debugger-import-from-repo.png)

除了所選的 ER 格式之外，以下 [設定](general-electronic-reporting.md#Configuration)必須作為 **ISO20022 貸記轉帳** ER 解決方案的一部分自動匯入您的 Microsoft Dynamics 365 Finance 實體：

- **付款模型** ER 資料模型設定
- **ISO20022 貸記轉帳** ER 格式設定
- **付款模型對應 1611** ER 模型對應設定
- **付款模型對應到目的地 ISO20022** ER 模型對應設定

您可以在 ER 架構的 **設定** 頁面上找到這些設定 (**組織管理**\>**電子報表**\>**設定**)。

![在設定頁面上匯入的設定。](./media/er-data-debugger-configurations.png)

如果設定樹狀結構中缺少之前列出的任何設定，您必須以與下載 **ISO20022 貸記轉帳** ER 付款格式相同的方式從 LCS 共用資產庫手動下載它們。

### <a name="analyze-the-downloaded-er-solution"></a>分析下載的 ER 解決方案

#### <a name="review-the-model-mapping"></a>查看模型對應

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 選取 **付款模式**\>**付款模式對應 1611**。
3. 選取 **設計工具**。
4. 選取 **付款模型對應 ISO20022 CT** 對應記錄。
5. 選取 **設計工具**，然後查看打開的模型對應。

    請注意，資料模型的 **付款** 欄位繫結到 **\$notSentTransactions** 資料來源，該資料來源返回正在處理的廠商付款明細清單。

    ![模型對應設計工具頁面上的付款欄位。](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a>查看格式對應

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 選取 **付款模式**\>**ISO20022 貸記轉帳**。
3. 選取 **設計工具**。
4. 在 **對應** 索引標籤，查看已開啟的格式對應。

    請注意，**ISO20022CTReports**\>**XMLHeader** 檔案的 **Document**\>**CstmrCdtTrfInitn**\>**PmtInf** 元素繫結到 **\$PaymentByDebtor** 資料設定為對資料模型的 **付款** 欄位的記錄進行分組的來源。

    ![格式設計工具頁面上的 PmtInf 元素。](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a>查看格式

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 選取 **付款模式**\>**ISO20022 貸記轉帳**。
3. 選取 **設計工具**，然後查看已開啟的格式。

    請注意，**Document**\>**CstmrCdtTrfInitn**\>**PmtInf**\>**CdtTrfTxInf**\>**CdtrAcct**\>**Id**\>**IBAN**\>**BankIBAN** 下的格式元素設定為在付款檔案中輸入廠商帳戶的 IBAN 代碼。

    ![格式設計工具頁面上的 BankIBAN 格式元素。](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a>附錄 2：設定應付帳款

### <a name="modify-a-vendor-property"></a>修改廠商屬性

1. 進入 **應付帳款**\>**廠商**\>**所有廠商**。
2. 選取廠商 **DE-01002**，然後在動作窗格的 **廠商** 索引標籤上的 **設定** 組中，選取 **銀行帳戶**。
3. 在 **識別** FastTab 上，在 **IBAN** 欄位，<a name="enteredIBANcode"></a>輸入 **GB33 BUKB 2020 1555 5555 55**。
4. 選取 **儲存**。

![在廠商銀行帳戶頁面上設定的 IBAN 欄位。](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a>設定付款方式

1. 進入 **應付帳款**\>**付款安裝**\>**付款方式**。
2. 選取 **SEPA CT** 付款方式。
3. 在 **檔案格式** FastTab 的 **檔案格式** 區段，將 **常用電子匯出格式** 選項設定為 **是**。
4. 在 **匯出格式設定** 欄位中，選取 **ISO20022 貸記轉帳** ER 格式。
5. 選取 **儲存**。

![付款方式頁面上的檔案格式設定。](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a>新增廠商付款

1. 進入 **應收帳款**\>**付款**\>**廠商付款日記帳**。
2. 新增新的付款日記帳。
3. 選取 **明細**，並新增新的付款明細。
4. 在 **帳戶** 欄位中，選取廠商 **DE-01002**。
5. 在 **貸方** 欄位中，輸入一個值。
6. 在 **付款方式** 欄位中，選取 **SEPA CT**。
7. 選取 **儲存**。

![在廠商付款頁面上新增了廠商付款。](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a>附錄 3：處理廠商付款

1. 進入 **應收帳款**\>**付款**\>**廠商付款日記帳**。
2. 在 **廠商付款日記帳** 頁面，選取您之前建立的付款日記帳，然後選取 **明細**。
3. 選取付款明細，然後選取 **付款狀態**\>**無**。
4. 選取 **產生付款**。
5. 在 **付款方式** 欄位中，選取 **SEPA CT**。
6. 在 **銀行帳戶** 欄位中，選取 **DEMF OPER**。
7. 在 **產生付款** 對話方塊中，選取 **確定**。
8. 在 **電子報表參數** 對話方塊中，選取 **確定**。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
