---
title: 印尼的扣繳稅款報表
description: 本主題說明如何設定和產生印尼的扣繳稅款報表。
author: sndray
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: sndray
ms.search.validFrom: 2021-12-02
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6cf2f9240ea747054578c52343af34b15c250f38
ms.sourcegitcommit: f51e74ee9162fe2b63c6ce236e514840795acfe1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2021
ms.locfileid: "8451314"
---
# <a name="withholding-tax-report-for-indonesia-id-00005"></a>印尼的扣繳稅款報表 (ID-00005)

[!include [banner](../includes/banner.md)]

本主題說明如何設定和產生印尼法人用於在 e-Bupot 應用程式中報表扣繳交易的 PPH 扣繳稅款檔案。

印尼稅務主管機關 (DGT) 確定在 KPP Pratama 註冊為所得稅 (PPh) 第 23 條和/或第 26 條的扣稅者/收稅者的應納稅企業家 (PKP) 必須使用 e-Bupot 應用程式以電子方式申報所得稅第 23 條和第 26 條報表。 

- **第 23 條** – 該報表包括來自廠商的所有扣繳交易，其中主要地址的國家/地區代碼是印尼的代碼。
- **第 26 條** – 該報表包括來自廠商的所有扣繳交易，其中主要地址的國家/地區代碼不是印尼的代碼。

## <a name="prerequisites"></a>先決條件

- 法律實體的主要地址必須在印尼。
- 在 **功能管理** 工作區中，必須啟用 **全球扣繳稅款** 功能。 有關如何啟用此功能的資訊，請參閱[功能管理概述。](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

### <a name="download-electronic-reporting-configurations"></a>下載電子報告組態

匯入檔案的產生根據電子報表 (ER) 設定。 有關可設定報告的功能和概念的更多信息，請參閱[電子報告](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md)。

對於生產和使用者驗收測試 (UAT) 環境，請遵循[從 Lifecycle Services 下載電子報表設定](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)中的說明進行作業。

要產生匯入檔案，請從存放庫上傳以下設定：

- **Tax declaration model.version.93.xml** 或更新版本
- **Tax declaration model mapping.version.93.153.xml** 或更新版本
- **WHT PPh schema import (ID).version.93.14** 或更新版本

## <a name="set-up-general-ledger-parameters"></a>設置總帳參數

1. 前往 **稅務** \> **設定** \> **總帳參數**。
2. 在 **扣繳稅款** 索引標籤的 **WHT 申報格式對應** 欄位中，選擇 **WHT PPh 結構描述匯入 (ID)**。 
3. 前往 **稅務** \> **設定** \> **扣繳稅款** \> **扣繳稅款收入類型**，設定 **Kode Bukti Potong** 扣繳稅款收入類型，然後將代碼指派給相關品項的扣繳稅款群組。 使用 e-Bupot 應用程式產生整合檔案需要這些代碼。 

## <a name="generate-the-withholding-import-file"></a>產生扣繳匯入檔案

為特定期間準備和產生 e-Bupot 檔案的過程基於在結算或繳稅後工作期間過帳的扣繳稅款交易。

按照以下步驟產生檔案。

1. 前往 **稅務** \> **申報** \> **扣繳稅款** \> **PPH 匯入檔案 e-bupot 23 和 26**。
2. 選擇報表的「開始」日期和「結束」日期，然後選擇結算期間。
3. 輸入交易日期，然後選擇 **確定**。
4. 選取語言。 所有報表均翻譯成美國英文 (**en-us**) 和印尼文 (**id**)。
5. 選擇業務類型，然後輸入支票和單據編號。 
6. 檢查報表是否已由經理簽署。 在檔案中報告的此資訊。 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
