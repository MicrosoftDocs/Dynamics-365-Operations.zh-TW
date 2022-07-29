---
title: 將子公司資料匯出到檔案
description: 本主題說明如何準備從 Microsoft Dynamics 365 Finance 匯出資料然後將其匯入合併的法人實體。
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 02ae9945f7b67fb64be78a024910d7e1151c7446fd54b71034c5ba448c00b081
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450726"
---
# <a name="export-subsidiary-data-to-files"></a>將子公司資料匯出到檔案

[!include [banner](../includes/banner.md)]

您使用 **出口** 頁面 (**系統管理\>工作區\>進出口**) 準備將輔助資料匯出到文件，然後可以將其匯入合併的法人實體。 更多有關資料匯入和匯出流程的資訊，請參閱[資料匯入和匯出工作概觀](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)。

1. 讓法人實體建立好進入合併流程。 有關如何創建法人實體的資訊，請參閱[建立法人實體](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md)。 有關詳細資訊，請參閱[準備在合併過程中使用的法人實體](prepare-company-for-consolidation.md)和[為合併設立子公司法人實體](set-up-subsidiary-company-for-consolidation.md). 

2. 去 **合併\>出口公司餘額**. 在 **匯出公司餘額** 頁面上的 **標準** 選項索引標籤上，通過設置以下欄位來指定合併的詳細資訊。

    | 欄位                             | 描述 |
    |-----------------------------------|-------|
    | 主科目                      | 指定要合併的科目。 要包括所有帳戶，請將此字段留空。 |
    | 使用合併帳戶         | 如果您已指定合併科目，請將此選項設置為 **是的**。 |
    | 選取合併帳戶 | 選擇任一 **主帳戶戶** 或 **合併科目組**。 |
    | 合併帳戶群組       | 為您選擇的合併科目選擇一個合併科目組。 |
    | 合併期間              | 指定合併的「開始」和「結束」日期。 |
    | 包括實際金額            | 設定本選項為 **是** 以便包括實際數量。 |
    | 包括預算金額            | 設定本選項為 **是** 以便在合併中包括預算金額。 |
    | 預算模型                     | 指定要包括的預算模型。 |

3. 在 **財務維度** 索引標籤，指定合併的詳細資訊：

    - 指定應從明細科目中的交易轉移到合併法人中的交易的財務維度資訊。
    - 在列表中選擇財務維度。
    - 確定合併的每個財務維度的正確規範。 可用選項包括 **維度**、**群組維度**、**公司帳戶戶** 和 **帳戶**。

        > [!NOTE]
        > 這 **群組維度** 選項允許您定義正在合併的公司組使用的維度值。

    - 指定要合併的分段順序。

4. 在 **法人實體** 選項卡，按照以下步驟指定您要匯出的法人實體：

    1. 選取 **新增**。
    2. 在 **來源法律實體** 欄位中，輸入法律實體。

        如果相同的條件適用於同一資料庫中的多個子公司，您可以在單個操作中將資料從這些子公司傳輸到單獨的匯出文件：

        1. 為應將其帳戶匯出到文件的每個子公司法人實體創建一行。 這些文件稍後將匯入合併的法人實體。
        2. 對於每個子公司，輸入子公司名稱和將在匯出作業期間創建的匯出文件的名稱。

    3. 在 **帳戶戶類型轉換差異** 字段，選擇 **收益與損失** 要么 **資產負債表**.
    4. 輸入要創建的匯出文件的文件名。

5. 選取 **確定** 以執行匯出。

匯出完成後，您會收到一條訊息，顯示每個文件中保存的記錄數。 然後，您可以將文件匯入合併的法人。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]