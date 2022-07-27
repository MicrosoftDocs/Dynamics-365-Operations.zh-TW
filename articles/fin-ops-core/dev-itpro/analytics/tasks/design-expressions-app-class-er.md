---
title: 設計 ER 運算式以調用應用程式類方法
description: 本主題介紹如何透過調用應用程式類的所需方法來重用電子報表設定中的現有應用程式邏輯。
author: NickSelin
ms.date: 11/02/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 81fae8d3603677afd7dd4b09b9073805f73582b4
ms.sourcegitcommit: e6b4844a71fbb9faa826852196197c65c5a0396f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "8460271"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>設計 ER 運算式以調用應用程式類方法

[!include [banner](../../includes/banner.md)]

本主題介紹如何透過在 ER 運算式中調用應用程式類的必需方法來重新使用[電子報表 (ER)](../general-electronic-reporting.md) 設定中的現有應用程式邏輯。 調用類的參數值可以在執行階段動態定義。 例如，值可以基於解析文件中的資訊，以確保其正確性。

對於本主題中的範例，您將設計一個流程來解析傳入的銀行對帳單以進行應用程式資料更新。 您將以包含國際銀行帳號 (IBAN) 代碼的文字 (.txt) 檔案形式收到傳入的銀行對帳單。 作為匯入銀行對帳單過程的一部分，您必須使用已有的邏輯來驗證 IBAN 代碼的正確性。

## <a name="prerequisites"></a>先決條件

本主題中的程序適用於已指派 **系統管理員** 或 **電子報表開發人員** 角色的使用者。

這些程序可以使用任何資料集來完成。

若要完成它們，您必須下載並儲存以下檔案：[SampleIncomingMessage.txt](https://download.microsoft.com/download/8/0/a/80adbc89-f23c-46d9-9241-e0f19125c04b/SampleIncomingMessage.txt)。

在此主題中，您將建立 Litware, Inc. 樣本公司的所需的 ER設定。 因此，在完成本主題中的程序之前，您必須執行以下步驟。

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面上，驗證 **Litware, Inc.** 樣本公司的設定提供者是否可用並標記為有效。 如果您沒有看到此設定提供者，則必須先完成[建立設定提供者並將其標記為有效](er-configuration-provider-mark-it-active-2016-11.md)中的步驟。

## <a name="import-a-new-er-model-configuration"></a>匯入新的 ER 模型設定

1. 在 **本地化設定** 頁面的 **設定提供者** 部分，選取 **Microsoft** 設定提供者的圖格。
2. 選取 **存放庫**。
3. 在 **本地化存放庫** 頁面，選取 **顯示過濾器**。
4. 若要選取全域存放庫記錄，請新增 **名稱** 過濾欄位。
5. 在 **名稱** 欄位中，輸入 **Global**。 然後選取 **包含** 過濾運算子。
6. 選取 **套用**。
7. 選取 **[開啟](../er-download-configurations-global-repo.md#open-configurations-repository)** 查看所選存放庫中的 ER 設定清單。
8. 在 **設定存放庫** 頁面上，在設定樹狀結構中，選取 **付款模型**。
9. 在 **版本** FastTab 上，如果 **匯入** 按鈕可使用，選取它，然後選取 **是**。

    如果 **匯入** 按鈕不可使用，您已經匯入了所選版本的 **付款模式** ER 設定。

10. 關閉 **設定存放庫** 頁面，然後關閉 **本地化存放庫** 頁。

## <a name="add-a-new-er-format-configuration"></a>新增新的 ER 格式設定

新增新的 ER 格式以解析 TXT 格式的傳入銀行對帳單。

1. 在 **本地化設定** 頁面上，選取 **報表設定** 圖格。
2. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，選取 **付款模型**。
3. 選取 **建立設定**。 
4. 在下拉式對話方塊中，執行以下步驟：

    1. 在 **新建** 欄位中，輸入 **Format based on data model PaymentModel**。
    2. 在 **名稱** 欄位中，輸入 **Bank statement import format (sample)**。
    3. 在 **支援資料匯入** 欄位，選取 **是**。
    4. 選取 **建立設定** 以完成建立設定。

## <a name="design-the-er-format-configuration--format"></a>設計 ER 格式設定 - 格式

設計一個 ER 格式，以 TXT 格式表示外部檔案的預期結構。

1. 對於您新增的 **銀行對帳單匯入格式 (樣本)** 格式設定，選取 **設計工具**。
2. 在 **公式設計工具** 頁面上，在左窗格的格式結構樹中，選取 **新增根**。
3. 在出現的對話方塊中，執行以下步驟：

    1. 在樹狀結構中，選取 **文字\\序列** 新增一個 **序列** 格式組件。
    2. 在 **名稱** 欄位中，輸入 **Root**。
    3. 在 **特殊字元** 欄位，選取 **新行 - Windows (CR LF)**。 基於此設定，解析檔案中的每一行都將被視為單獨的記錄。
    4. 選取 **確定**。

4. 選取 **新增**。
5. 在出現的對話方塊中，執行以下步驟：

    1. 在樹狀結構中，選取 **文字\\序列**。
    2. 在 **名稱** 欄位中，輸入 **Rows**。
    3. 在 **多重性** 欄位，選取 **一對多**。 基於此設定，解析檔案中至少會出現一個行。
    4. 選取 **確定**。

6. 在樹狀結更中，選取 **根\\資料列**，然後選取 **新增序資料列**。
7. 在出現的對話方塊中，執行以下步驟：

    1. 在 **名稱** 欄位中，輸入 **Fields**。
    2. 在 **多重性** 欄位，選取 **剛好一個**。
    3. 選取 **確定**。

8. 在樹狀結構中，選取 **根\\資料列\\欄位**，然後選取 **新增**。
9. 在出現的對話方塊中，執行以下步驟：

    1. 在樹狀結構中，選取 **文字\\字串**。
    2. 在 **名稱** 欄位中，輸入 **IBAN**。
    3.. 選取 **確定**。

10. 選取 **儲存**。

現在已設定設定，以便解析檔案中的每一行僅包含 IBAN 代碼。

![格式設計工具頁面上的銀行對帳單匯入格式 (樣本) 格式設定。](../media/design-expressions-app-class-er-01.png)

## <a name="design-the-er-format-configuration--mapping-to-a-data-model"></a>設計 ER 格式設定 – 對應到資料模型

設計一個 ER 格式對應，該對應使用來自解析檔案的資訊來填入資料模型。

1. 在 **格式設計工具** 頁面上，在動作窗格上，選取 **將格式對應到模型**。
2. 在 **對資料來源對應建模** 頁面上，在動作窗格上，選取 **新建**。
3. 在 **定義** 欄位，選取 **BankToCustomerDebitCreditNotificationInitiation**。
4. 在 **名稱** 欄位中，輸入 **Mapping to data model**。
5. 選取 **儲存**。
6. 選取 **設計工具**。
7. 在 **模型對應設計工具** 頁面上的 **資料來源類型** 樹狀結構中，選取 **Dynamics 365 for Operations\\類別**。
8. 在 **資料來源** 區段，選取 **新增根** 以新增調用現有應用程式邏輯以進行 IBAN 代碼驗證的資料來源。
9. 在出現的對話方塊中，執行以下步驟：

    1. 在 **名稱** 欄位中，輸入 **Check\_codes**。
    2. 在 **類別** 欄位中，輸入或選取 **ISO7064**。
    3. 選取 **確定**。

10. 在 **資料來源類型** 樹狀結構，請按照下列步驟操作：

    1. 展開 **格式** 資料來源。
    2. 展開 **format\\Root: Sequence(Root)**。
    3. 展開 **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Rows)**。
    4. 展開 **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Rows)\\Fields: Sequence 1..1 (Fields)**。

11. 在 **資料模型** 樹狀結構，請按照下列步驟操作：

    1. 展開資料模型的 **付款** 欄位。
    2. 展開 **Payments\\Creditor Account(CreditorAccount)**。
    3. 展開 **Payments\\Creditor Account(CreditorAccount)\\Identification**。
    4. 展開 **Payments\\Creditor Account(CreditorAccount)\\Identification\\IBAN**。

12. 按照以下步驟將設定格式的組件繫結到資料模型欄位：

    1. 選取 **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Rows)**。
    2. 選取 **付款**。
    3. 選取 **繫結**。 基於此設定，解析檔案中的每一明細都將被視為單一付款。
    4. 選取 **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Rows)\\Fields: Sequence 1..1 (Fields)\\IBAN: String(IBAN)**。
    5. 選取 **Payments\\Creditor Account(CreditorAccount)\\Identification\\IBAN**。
    6. 選取 **繫結**。 基於此設定，**IBAN** 資料模型的欄位將填入解析檔案中的值。

    ![將格式組件繫結到模型對應設計工具頁面上的資料模型欄位。](../media/design-expressions-app-class-er-02.png)

13. 在 **驗證** 索引標籤上，按照以下步驟新增[驗證](../general-electronic-reporting-formula-designer.md#Validation)規則，該規則會為解析檔案中包含無效 IBAN 代碼的任何行顯示錯誤訊息：

    1. 選取 **新建**，然後選取 **編輯條件**。
    2. 在 **公式設計工具** 頁面的 **資料來源** 樹狀結構中，展開代表 **ISO7064** 應用程式類的 **Check\_codes** 資料來源以查看此類可用的方法。
    3. 選取 **Check\_codes\\verifyMOD1271\_36**。
    4. 選取 **新增資料來源**。
    5. 在 **公式** 欄位，輸入以下 [運算式](../general-electronic-reporting-formula-designer.md#Binding)：**check\_codes.verifyMOD1271\_36(format.Root.Rows.Fields.IBAN)**。
    6. 請選取 **儲存**，然後關閉此頁。
    7. 選取 **編輯訊息**。
    8. 在 **公式設計工具** 頁，在 **公式** 欄位，輸入 **CONCATENATE("Invalid IBAN code has been found:&nbsp;", format.Root.Rows.Fields.IBAN)**。
    9. 請選取 **儲存**，然後關閉此頁。

    基於這些設定，驗證條件將透過調用 **ISO7064** 應用程式類的現有 **verifyMOD1271\_36** 方法對任何無效 IBAN 代碼回傳 *[FALSE](../er-formula-supported-data-types-primitive.md#boolean)*。 請注意，IBAN 代碼的值在執行階段根據解析文字檔案的內容動態定義為調用方法的參數。

    ![模型對應設計工具頁面上的驗證規則。](../media/design-expressions-app-class-er-03.png)

14. 選取 **儲存**。
15. 關閉 **模型對應設計工具** 頁面，然後關閉 **資料來源對應的模型** 頁。

## <a name="run-the-format-mapping"></a>執行格式對應

出於測試目的，請使用您之前下載的 SampleIncomingMessage.txt 檔案執行格式對應。 產生的輸出將包括從所選文字檔案匯入並在實際匯入期間移植到自訂資料模型的資料。

1. 在 **資料來源對應的模型** 頁面上，選取 **執行**。
2. 在 **電子報表參數** 頁面，選取 **瀏覽**，瀏覽您下載的 **SampleIncomingMessage.txt** 檔案，然後選取它。
3. 選取 **確定**。
4. 請注意，**資料來源對應的模型** 頁面顯示有關無效 IBAN 代碼的錯誤訊息。

    ![在資料來源對應模型頁面上執行格式對應的結果。](../media/design-expressions-app-class-er-04.png)

5. 查看 XML 格式的輸出，該輸出表示已從選定檔案匯入並移植到資料模型的資料。 請注意，只有三行匯入的文字檔案被正確處理。 IBAN 代碼在第 4 行無效並被跳過。

    ![XML 輸出](../media/design-expressions-app-class-er-05.png)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
