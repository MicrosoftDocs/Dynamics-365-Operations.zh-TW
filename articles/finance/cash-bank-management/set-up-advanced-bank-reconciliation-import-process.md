---
title: 設定進階銀行對帳匯入流程
description: 進階銀行對帳功能讓您匯入電子銀行對帳單，並且自動在 Microsoft Dynamics 365 Finance 中核對銀行交易。 本文介紹如何設定您銀行對帳單的匯入功能。
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 106853
ms.assetid: 45dae275-ea45-4c7e-b38f-89297c7b5352
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0efe960bee8f5c2c0b683ad641379345ce6d470180d29893b373acc6e1de8aa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450246"
---
# <a name="set-up-the-advanced-bank-reconciliation-import-process"></a>設定進階銀行對帳匯入流程

[!include [banner](../includes/banner.md)]

進階銀行對帳功能讓您匯入電子銀行對帳單，並且自動在 Dynamics 365 Finance 中核對銀行交易。 本文介紹如何設定您銀行對帳單的匯入功能。 

銀行對帳單匯入的設定因電子銀行對帳單的格式而異。 Finance 支援三種立即可用的銀行對帳單格式︰ISO20022、MT 940 和 BAI2。

## <a name="set-time-zone-preference"></a>設定時區偏好
配置銀行對帳單匯入設定時，務必考慮欲匯入銀行對帳單檔案中日期時間資料的時區。 預設情況下，假設所有日期和時間值均為協調世界時 (UTC)，因此匯入資料時不套用時區轉換。 

有一個選項可用於指定匯入資料要使用的時區。 此選項位於每個 **來源資料格式詳細資料** 頁面 (**資料管理工作區 > 配置資料來源 > 選擇資料格式 > 區域設定** FastTab) 中的 **時區偏好** 欄位內。 所輸入的時區偏好將套用在所有使用該來源資料格式的匯入。 可以建立任意數量的資料來源格式，以滿足從多個時區匯入資料的需求。  

此時區可能與使用者或公司的時區不同，因此請務必分辨清楚日期和時間資料使用的時區。 建議在設定時區偏好時，考慮以下事項。 

 - 時區偏好將套用在所有使用該來源資料格式的匯入。 可以建立任意數量的資料來源格式，以處理從多個時區匯入資料的需求。 
 
 - 時區偏好應該是匯入檔案中日期和時間資料的本地時區。 
 
 - 日期和時間資料的時區可能與使用者或公司的時區不同。
 
 - 使用者可以使用他們的 **使用者選項** 調整自己的時區。

請注意，匯入銀行對帳單時，以下操作有助於將潛在的日期和時間衝突減到最少。 

 - 避免更改任何已匯入對帳單之銀行帳戶的時區偏好。 因為時區調整，更改時區偏好可能會影響新對帳單與現有對帳單的相對排序。 
 
 - 查看所有使用所選資料來源格式的匯入。 該格式指定的時區偏好將套用在所有使用該格式的匯入專案。 驗證時區偏好適合所有使用該格式的匯入專案。

## <a name="sample-files"></a>範例檔案
對於所有三種格式，您必須有檔案，以將電子銀行對帳單從原始格式轉換為 Finance 可用的格式。 您可以在 Microsoft Visual Studio 中 Application Explorer 的 **資源** 節點下找到所需資源檔案。 找到檔案後，將它們複製到已知位置，以便在設定流程中更輕鬆地上傳。

| 資源名稱                                           | 檔案名稱                            |
|---------------------------------------------------------|--------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt              | BAI2CSV-to-BAI2XML.xslt              |
| BankStmtImport\_BAI2XML\_to\_Reconciliation\_xslt       | BAI2XML-to-Reconciliation.xslt       |
| BankStmtImport\_BankReconciliation\_to\_Composite\_xslt | BankReconciliation-to-Composite.xslt |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt   | ISO20022XML-to-Reconciliation.xslt   |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt            | MT940TXT-to-MT940XML.xslt            |
| BankStmtImport\_MT940XML\_to\_Reconciliation\_xslt      | MT940XML-to-Reconciliation.xslt      |
| BankStmtImport\_SampleBankCompositeEntity\_xml          | SampleBankCompositeEntity.xml        |

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>銀行對帳單格式和技術版面範例
下面是進階銀行對帳匯入檔案技術配置定義的範例和三個相關銀行對帳單範例檔案：[匯入檔案範例](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| 技術配置定義                             | 銀行對帳單範例檔案          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| DynamicsAXISO20022Layout                                | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout                                    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |



## <a name="set-up-the-import-of-iso20022-bank-statements"></a>設定 ISO20022 銀行對帳單的匯入
首先，您必須使用資料實體框架定義 ISO20022 銀行對帳單的銀行對帳單格式處理群組。

1.  前往 **工作區** &gt; **資料管理**。
2.  按一下 **匯入**。
3.  輸入格式名稱，例如 **ISO20022**。
4.  將 **來源資料格式** 欄位設為 **XML-Element**。
5.  將 **實體名稱** 欄位設為 **銀行對帳單**。
6.  若要上傳匯入檔案，則按一下 **上傳**，然後瀏覽以選擇先前儲存的 **SampleBankCompositeEntity.xml** 檔案。
7.  在銀行對帳單實體已上傳且對應完成後，按一下實體的 **檢視對應** 動作。
8.  銀行對帳單實體是由四個獨立實體組成的一個複合實體。 在清單中，選擇 **BankStatementDocumentEntity**，然後按一下 **檢視對應** 動作。
9.  在 **轉換** 索引標籤中，按一下 **新建**。
10. 對於序號 1，按一下 **上傳檔案**，並選擇先前儲存的 **ISO20022XML-to-Reconciliation.xslt** 檔案。 **附註：** 轉換檔案使用標準格式建立。 因為銀行不常使用這種格式，您可能必須更新轉換檔案以對應到您銀行帳單的格式。 <!-- For details about the expected format for ISO20022, see [Dynamics AX ISO20022 Layout](./media/dynamicsaxiso20022layout1.xlsx).-->
11. 按一下 **新建**。
12. 對於序號 2，按一下 **上傳檔案**，並選擇先前儲存的 **BankReconciliation-to-Composite.xslt** 檔案。
13. 按一下 **套用轉換**。

設定格式處理群組後，下一步是定義 ISO20022 銀行對帳單的銀行對帳單格式規則。

1.  前往 **現金和銀行管理** &gt; **設定** &gt; **進階銀行對帳設定** &gt; **銀行對帳單格式**。
2.  按一下 **新建**。
3.  指定對帳單格式，例如 **ISO20022**。
4.  輸入格式名稱。
5.  將 **處理群組** 欄位設為之前定義的群組，例如 **ISO20022**。
6.  選擇 **XML file** 核取方塊。

最後一步是「啟用進階銀行對帳」，並在銀行帳戶上設定對帳單格式。

1.  前往 **現金和銀行管理參數** &gt; **銀行帳戶**。
2.  選擇銀行帳戶，並開啟帳戶以查看詳細資料。
3.  在 **對帳** 索引標籤中，將 **進階銀行對帳** 選項設定為 **是**。
4.  將 **對帳單格式** 欄位設為之前建立的格式，例如 **ISO20022**。

## <a name="set-up-the-import-of-mt940-bank-statements"></a>設定 MT940 銀行對帳單的匯入
首先，您必須使用資料實體框架定義 MT940 銀行對帳單的銀行對帳單格式處理群組。

1.  前往 **工作區** &gt; **資料管理**。
2.  按一下 **匯入**。
3.  輸入格式名稱，例如 **MT940**。
4.  將 **來源資料格式** 欄位設為 **XML-Element**。
5.  將 **實體名稱** 欄位設為 **銀行對帳單**。
6.  若要上傳匯入檔案，請按一下 **上傳**，然後瀏覽以選擇先前儲存的 **SampleBankCompositeEntity.xml** 檔案。
7.  在銀行對帳單實體已上傳且對應完成後，按一下實體的 **檢視對應** 動作。
8.  銀行對帳單實體是由四個獨立實體組成的一個複合實體。 在清單中，選擇 **BankStatementDocumentEntity**，然後按一下 **檢視對應** 動作。
9.  在 **轉換** 索引標籤中，按一下 **新建**。
10. 對於序號 1，按一下 **上傳檔案**，並選擇先前儲存的 **MT940TXT-to-MT940XML.xslt** 檔案。
11. 按一下 **新建**。
12. 對於序號 2，按一下 **上傳檔案**，並選擇先前儲存的 **MT940XML-to-Reconciliation.xslt** 檔案。 **附註：** 轉換檔案使用標準格式建立。 因為銀行不常使用這種格式，您可能必須更新轉換檔案以對應到您銀行帳單的格式。 <!--- For details about the expected format for MT940, see [Dynamics AX MT940 Layout](./media/dynamicsaxmt940layout1.xlsx)-->
13. 按一下 **新建**。
14. 對於序號 3，按一下 **上傳檔案**，並選擇先前儲存的 **BankReconciliation-to-Composite.xslt** 檔案。
15. 按一下 **套用轉換**。

設定格式處理群組後，下一步是定義 MT940 銀行對帳單的銀行對帳單格式規則。

1.  前往 **現金和銀行管理** &gt; **設定** &gt; **進階銀行對帳設定** &gt; **銀行對帳單格式**。
2.  按一下 **新建**。
3.  指定對帳單格式，例如 **MT940**。
4.  輸入格式名稱。
5.  將 **處理群組** 欄位設為之前定義的群組，例如 **MT940**。
6.  將 **檔案類型** 欄位設為 **txt**。

最後一步是「啟用進階銀行對帳」，並在銀行帳戶上設定對帳單格式。

1.  前往 **現金和銀行管理參數** &gt; **銀行帳戶**。
2.  選擇銀行帳戶，並開啟帳戶以查看詳細資料。
3.  在 **對帳** 索引標籤中，將 **進階銀行對帳** 選項設定為 **是**。
4.  當系統提示您確認選擇並啟用「進階銀行對帳」時，按一下 **確定**。
5.  將 **對帳單格式** 欄位設為之前建立的格式，例如 **MT940**。

## <a name="set-up-the-import-of-bai2-bank-statements"></a>設定 BAI2 銀行對帳單的匯入
首先，您必須使用資料實體框架定義 BAI2 銀行對帳單的銀行對帳單格式處理群組。

1.  前往 **工作區** &gt; **資料管理**。
2.  按一下 **匯入**。
3.  輸入格式名稱，例如 **BAI2**。
4.  將 **來源資料格式** 欄位設為 **XML-Element**。
5.  將 **實體名稱** 欄位設為 **銀行對帳單**。
6.  若要上傳匯入檔案，請按一下 **上傳**，然後瀏覽以選擇先前儲存的 **SampleBankCompositeEntity.xml** 檔案。
7.  在銀行對帳單實體已上傳且對應完成後，按一下實體的 **檢視對應** 動作。
8.  銀行對帳單實體是由四個獨立實體組成的一個複合實體。 在清單中，選擇 **BankStatementDocumentEntity**，然後按一下 **檢視對應** 動作。
9.  在 **轉換** 索引標籤中，按一下 **新建**。
10. 對於序號 1，按一下 **上傳檔案**，並選擇先前儲存的 **BAI2CSV-to-BAI2XML.xslt** 檔案。
11. 按一下 **新建**。
12. 對於序號 2，按一下 **上傳檔案**，並選擇先前儲存的 **BAI2XML-to-Reconciliation.xslt** 檔案。 **附註：** 轉換檔案使用標準格式建立。 因為銀行不常使用這種格式，您可能必須更新轉換檔案以對應到您銀行帳單的格式。 <!--- For details about the expected format for BAI2, see [Dynamics AX BAI2 Layout](./media/dynamicsaxbai2layout1.xlsx).-->
13. 按一下 **新建**。
14. 對於序號 3，按一下 **上傳檔案**，並選擇先前儲存的 **BankReconciliation-to-Composite.xslt** 檔案。
15. 按一下 **套用轉換**。

設定格式處理群組後，下一步是定義 BAI2 銀行對帳單的銀行對帳單格式規則。

1.  前往 **現金和銀行管理** &gt; **設定** &gt; **進階銀行對帳設定** &gt; **銀行對帳單格式**。
2.  按一下 **新建**。
3.  指定對帳單格式，例如 **BAI2**。
4.  輸入格式名稱。
5.  將 **處理群組** 欄位設為之前定義的群組，例如 **BAI2**。
6.  將 **檔案類型** 欄位設為 **txt**。

最後一步是「啟用進階銀行對帳」，並在銀行帳戶上設定對帳單格式。

1.  前往 **現金和銀行管理參數** &gt; **銀行帳戶**。
2.  選擇銀行帳戶，並開啟帳戶以查看詳細資料。
3.  在 **對帳** 索引標籤中，將 **進階銀行對帳** 選項設定為 **是**。
4.  當系統提示您確認選擇並啟用「進階銀行對帳」時，按一下 **確定**。
5.  將 **對帳單格式** 欄位設為之前建立的格式，例如 **BAI2**。

## <a name="test-the-bank-statement-import"></a>測試銀行對帳單匯入
最後一個步驟是測試您是否可以匯入銀行對帳單。

1.  前往 **現金和銀行管理參數** &gt; **銀行帳戶**。
2.  選擇要啟用進階銀行對帳功能的銀行帳戶。
3.  在 **對帳** 索引標籤中，按一下 **銀行對帳單**。
4.  在 **銀行對帳單** 頁面中，按一下 **匯入對帳單**。
5.  將 **銀行帳戶** 欄位設為所選的銀行帳戶。 **對帳單格式** 欄位將根據銀行帳戶的設定自動設定。
6.  按一下 **瀏覽**，然後選擇您的電子銀行對帳單檔案。
7.  按一下 **上傳**。
8.  按一下 **確定**。

如果匯入成功，您將收到一則訊息，表示您的對帳單已匯入。 如果匯入不成功，在 **資料管理** 工作區的 **作業歷史紀錄** 區段，找到該作業。 按一下作業的 **執行詳細資料** 以開啟 **執行摘要** 頁面，然後按一下 **查看執行日誌** 查看匯入錯誤。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
