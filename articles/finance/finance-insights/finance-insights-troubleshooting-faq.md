---
title: Finance Insights 設定問題
description: 本主題列出了您在使用 Finance Insights 功能時可能出現的問題。 它也解釋了如何解決這些問題。
author: panolte
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: fc616e5fce6bbfeaa3b36ccc35f1b1cf407af4a6
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451551"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>Finance Insights 設定問題

[!include [banner](../includes/banner.md)]

本主題列出了您在使用 Finance Insights 功能時可能出現的問題。 它也解釋了如何解決這些問題。

## <a name="symptom-why-cant-i-map-the-customer-payment-insights-data-integration-template-destination-column"></a>症狀：為什麼我無法映射客戶付款洞察資料集成範本目標列？

### <a name="resolution"></a>解決方法

您可能正在使用早期版本的範本。 在 10.0.17 版本發布之前，預覽版客戶設定了 **客戶支付洞察結果（CDS 到 Fin and Ops）** 使用資料集成 (DI) 範本 **付款預測結果（預覽）** 實體。 升級到 10.0.17 及更高版本後，您應該使用 **客戶付款洞察結果 (CDS 到 Fin and Ops 10.0.17 及更高版本)** DI 範本完成映射。 您可能無法映射 DI 範本目標列，直到重新整理資料管理實體列表並且 **支付預測結果** 實體出現在其中。 若要重新整理實體列表並顯示支付預測結果，您將在 Microsoft Dynamics 365 Finance 和 Dataverse (以前稱為 Common Data Service\[CDS\] 管理入口網站)。

### <a name="in-finance"></a>在財務中

升級後，請在 Finance 中執行這些步驟。

1. 進入 **系統管理\>工作區\>資料管理**。
2. 在 **資料管理** 工作區中，選擇 **架構參數** 圖格。
3. 在 **資料導入/導出框架參數** 頁面，選擇 **實體設定**，然後選擇 **重新整理實體列表**。
4. 關閉 **資料匯入/匯出框架參數** 頁面。
5. 在 **資料管理** 工作區中，選擇 **資料實體** 圖格。
6. 搜尋「付款預測結果」。 驗證 **支付預測結果** 實體不是預覽版。 預覽版的名稱以「預覽」結尾。 如果您只看到實體的預覽版，請聯繫 Microsoft 支持。

### <a name="in-dataverse"></a>在 Dataverse 中

請按照以下步驟操作[Power Platform管理中心](https://admin.powerplatform.microsoft.com/environments)更新您的資料集成項目。

1. 如果您使用的是 Finance Insights 的預覽版，請刪除與 **客戶支付洞察結果 (CDS 到 Fin and Ops)** 範本。
2. 按照中的步驟[創建資料集成器項目](create-data-integrate-project.md). 使用 **客戶付款洞察結果 (CDS 到 Fin and Ops 10.0.17 及更高版本)** 範本。

## <a name="symptom-when-i-try-to-open-ai-builder-by-using-the-links-on-the-customer-payment-predictions-setup-page-why-do-i-receive-the-following-error-message-sorry-theres-been-a-disconnect"></a>症狀：當我嘗試打開 AI Builder 時透過使用客戶付款預測設定頁面上的連結，為什麼我會收到以下錯誤消息：「抱歉，連結已中斷」？

### <a name="resolution"></a>解決方法

Dynamics 365 Finance 使用者必須有一個 Microsoft Power Apps 環境的使用者帳戶，並且該用戶帳戶必須具有系統自訂員角色。 Microsoft Power Apps 系統管理員可以創建使用者帳戶並分配角色。 然後你可以去<https://make.preview.powerapps.com/>，使用該用戶帳戶登錄，然後重試連結。

## <a name="symptom-why-doesnt-the-cash-forecast-tab-in-the-cash-flow-forecast-workspace-show-any-data"></a>症狀：為什麼現金流量預測工作區中的現金預測選項卡不顯示任何資料？

### <a name="resolution"></a>解決方法

必須設定並啟用現金和銀行管理中的現金流量預測功能和 Finance Insights 中的現金流量預測功能，才能在 **現金流量預測** 工作區。

首先，設定並啟用現金流量預測和流動性帳戶。 如需詳細資訊，請參閱[現金流預測](../cash-bank-management/cash-flow-forecasting.md)。 如果此設定已完成，但您沒有看到預期的結果，請參閱[現金流量預測設定疑難解答](../cash-bank-management/cash-flow-forecasting-tsg.md)了解更多資訊。

接下來，確認  Finance Insights 中的現金流預測功能 (**現金和銀行管理\>設定\> Finance Insights\>現金流量預測**) 已啟用，並且 AI 模型的訓練已完成。 如果培訓尚未完成，請選擇 **現在預測** 開始模型訓練過程。

## <a name="symptom-why-isnt-the-install-a-new-add-in-button-visible-in-microsoft-dynamics-lifecycle-services"></a>症狀：為什麼安裝新加載項按鈕在 Microsoft Dynamics Lifecycle Services？

### <a name="resolution"></a>解決方法

首先，驗證 **環境管理員** 或 **專案擁有者** 角色已分配給 Microsoft Dynamics Lifecycle Services (LCS) 中 **專案資訊安全角色** 欄位中的登入使用者。 新加載項的安裝需要這些項目安全角色之一。

如果為您分配了正確的項目安全角色，您可能需要重新整理瀏覽器窗口才能看到 **安裝新插件** 按鈕。

## <a name="symptom-the-finance-insights-add-in-doesnt-seem-to-be-installing-why-is-that"></a>症狀：Finance Insights 加載項似乎沒有安裝。 這是為什麼？

### <a name="resolution"></a>解決方法

以下步驟應該已經完成。

- 驗證你在 Power Portal 系統管理中心具有 **系統管理員** 和 **系統自訂者** 存取權。
- 驗證 Dynamics 365 Finance 或等效授權適用於安裝增益集的使用者。
- 驗證以下內容Azure AD應用程序已註冊Azure AD： 

  | 應用程式                  | 應用程式識別碼           |
  | ---------------------------- | ---------------- |
  | Microsoft Dynamics ERP 微服務 CDS | 703e2651-d3fc-48f5-942c-74274233dba8 | 
  
## <a name="symptom-error-we-didnt-find-any-data-for-the-selected-filter-range-please-select-a-different-filter-range-and-try-again"></a>症狀：錯誤，“我們沒有找到所選過濾器範圍的任何資料。 請選擇不同的過濾範圍，然後重試。” 

### <a name="resolution"></a>解決方法

檢查資料集成器設定以驗證它是否按預期運行並從 AI Builder 回到財務。  
有關詳細資訊，請參閱[創建資料集成項目](../finance-insights/create-data-integrate-project.md)。

## <a name="symptom-customer-payment-prediction-training-failed-and-the-ai-builder-error-states-prediction-should-have-only-2-distinct-outcome-values-to-train-the-model-map-to-two-outcomes-and-retrain-training-report-issue-isnotminrequireddistinctnonnullvalues"></a>症狀：客戶付款預測培訓失敗 AI Builder 錯誤狀態，「預測應該只有 2 個不同的結果值來訓練模型。 映射到兩個結果並重新訓練」、「訓練報告問題：IsNotMinRequiredDistinctNonNullValues」。

### <a name="resolution"></a>解決方法

此錯誤表明過去一年中沒有足夠的歷史交易可以代表表中描述的每個類別 **準時**、**晚了** 和 **非常晚** 類別。 要解決此錯誤，請調整 **非常晚** 交易期限。 如果調整 **很晚了** 交易期不能修復錯誤，**客戶付款預測** 不是最好的解決方案，因為它需要每個類別中的資料用於培訓目的。

有關如何調整的更多資訊 **準時**、**晚了** 和 **非常晚** 類別，請參閱[啟用客戶付款預測](../finance-insights/enable-cust-paymnt-prediction.md)。

## <a name="symptom-model-training-failed"></a>症狀：模型訓練失敗

### <a name="resolution"></a>解決方法

這 **現金流量預測** 模型訓練需要包含超過一年的 100 個或更多交易的資料。 我們建議您擁有至少兩年的超過 1,000 筆交易的數據。

這 **客戶付款預測** 該功能需要在過去六到九個月內完成 100 多筆交易。 交易可以包括普通發票、銷售訂單和客戶付款。 這些資料必須分佈在 **準時**、**晚了** 和 **非常晚** 上定義的設定 **設定** 頁。    

這 **預算提案** 功能需要至少三年的預算或實際資料。 該解決方案在預測中使用了三到十年的資料。 三年以上將提供更好的結果。 當值有變化時，資料本身效果最好。 如果資料包含所有恆定資料，例如租賃費用，則培訓可能會失敗，因為缺乏變化不需要 AI 來預測金額。

## <a name="symptom-error-message-states-that-the-table-with-name-msdyn_paypredpredictionresultentities-does-not-exist-the-remote-server-returned-an-error-404-not-found"></a>症狀：錯誤消息指出，「名稱為『msdyn_paypredpredictionresultentities』的表不存在。 遠程伺服器返回錯誤：(404) Not Found...」

### <a name="resolution"></a>解決方法

環境已達到 Data Lake 服務最大表限制。 有關限制的更多資訊，請參閱 **啟用近乎即時的資料更改** 主題部分，[匯出到 Azure Data Lake 概述](../../fin-ops-core/dev-itpro/data-entities/Azure-Data-Lake-GA-version-overview.md)。
