---
title: Dynamics 365 Finance 中已移除或棄用的功能
description: 本主題說明已從 Dynamics 365 Finance 移除或計畫移除的功能。
author: roschlom
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: ad3df2ee9c10972dac8258b6ee41ae0a6eabfbea
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451284"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Dynamics 365 Finance 中已移除或棄用的功能

[!include [banner](../includes/banner.md)]

本主題說明已從 Dynamics 365 Finance 移除或計畫移除的功能。

- *已移除* 功能不再開放產品使用。
- *已棄用* 功能尚未開發，可能會從未來的更新版移除。

此清單原意希望幫助您思考對自己計劃中，這些功能的移除和棄用。 

> [!NOTE]
> 有關財務和營運應用程式對象的詳細資訊，可參閱[技術參考報表](/dynamics/s-e/global/axtechrefrep_61)。 您可以比較這些不同版本的報表，以了解每個版本的財務和營運應用程式中已更改或移除的對象。

## <a name="features-removed-or-deprecated-in-the-finance-10024-release"></a>Finance 10.0.24 版本中已移除或棄用的功能

### <a name="sales-tax-report-for-sweden-design-based-on-reporting-codes"></a>瑞典銷售稅報表 (以報表代碼為主的設計)

[瑞典銷售稅報表](../localizations/emea-swe-sales-tax-payment-report-sweden.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 取而代之的是增值稅申報新設計，[瑞典增值稅申報](../localizations/emea-swe-vat-declaration-sweden.md) |
| **被另一項功能取代？**   | 是 |
| **受到影響的產品領域**         | 應用程式 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：我們計畫 2022 年十二月 1 日前不再支援瑞典銷售稅報表 (瑞典報表版面)。 全新 **增值稅申報 XML (SE**) 和 **增值稅申報表 Excel (SE)** 電子報表 (ER) 格式按 **報稅** 模型引進。 |

### <a name="vat-statement-for-austria-design-based-on-reporting-codes"></a>奧地利增值稅聲明 (以報表代碼為主的設計)

[奧地利增值稅報表細節](../localizations/emea-aut-vat-statement-details.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 取而代之的是增值稅申報新設計，[奧地利增值稅申報](../localizations/emea-aut-vat-declaration-austria.md) |
| **被另一項功能取代？**   | 是 |
| **受到影響的產品領域**         | 應用程式 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：我們計劃 2022 年十二月 1 日前不再支援 **增值稅申報模型** 下方的 **增值稅申報 (AT)** 電子報表 (ER) 格式。 全新 **增值稅申報 XML (AT)** 和 **增值稅申報表 Excel (AT)** 格式按 **報稅** 模型引進。 |

### <a name="elster-declaration-for-germany-design-based-on-reporting-codes"></a>德國 ELSTER 申報 (以報表代碼為主的設計)

[VAT 報表](../localizations/emea-de-vat-declaration.md)</br>
[設定德國電子報稅](../../fin-ops-core/dev-itpro/analytics/tasks/setup-electronic-tax-declaration-germany.md)</br>
[增值稅申報電子傳輸 (ELSTER)](../localizations/tasks/de-00003-electronic-transmission-elster.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 取而代之的是增值稅申報新設計，[德國增值稅申報](../localizations/emea-deu-vat-declaration-germany.md) |
| **被另一項功能取代？**   | 是 |
| **受到影響的產品領域**         | 應用程式 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：我們計劃 2022 年十二月 1 日前不再支援 **Elster (DE)** 和 **Elster 模型** 電子報表 (ER) 格式。 全新 **增值稅申報 XML (DE)** 和 **增值稅申報表 Excel (DE)** 格式按 **報稅** 模型引進。 |

### <a name="ob-declaration-for-netherlands-design-based-on-reporting-codes"></a>荷蘭 OB 申報 (以報表代碼為主的設計)

[OB 申報](../localizations/emea-nl-vat-declaration.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 取而代之的是增值稅申報新設計，[荷蘭增值稅申報](../localizations/emea-nl-vat-declaration-netherlands.md) |
| **被另一項功能取代？**   | 是 |
| **受到影響的產品領域**         | 應用程式 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：我們計劃 2022 年十二月 1 日前不再支援 **OB 申報 (NL)** 和 **OB 申報模型** 電子報表 (ER) 格式。 全新 **增值稅申報 XML (NL)** 和 **增值稅申報表 Excel (NL)** 格式按 **報稅** 模型引進。 |

## <a name="features-removed-or-deprecated-in-the-finance-10020-release"></a>Finance 10.0.20 版本中已移除或棄用的功能

### <a name="rtir-query-invoice-data-request-hu-electronic-reporting-er-format-configuration"></a>"RTIR 查詢發票資料申請 (HU)" 電子申報 (ER) 格式組態

| &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不納入匈牙利線上發票系統互動操作的電子簡訊處理範圍 |
| **被另一項功能取代？**   | 否 |
| **受到影響的產品領域**         | 應用程式 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：我們計劃到 2022 年四月 15 日不再支援 "RTIR 查詢發票資料申請 (HU)" 格式組態。 |

### <a name="french-fec-audit-file-electronic-reporting-er-format-for-france-under-german-audit-file-output-format"></a>"法國 FEC 稽核檔案" "德國稽核檔案輸出" 格式下的法國電子報表 (ER) 格式

| &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 取而代之的是新 "FEC 稽核檔案 (FR)" 格式 |
| **被另一項功能取代？**   | 是 |
| **受到影響的產品領域**         | 應用程式 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：我們計劃到 2022 年五月 1 日不再支援 "德國稽核檔案輸出" 格式下的 "法國 FEC 稽核檔案" 電子報表 (ER) 格式。 反而在 "資料匯出模型" 下方引進新 FEC 稽核檔案 (FR) 格式。 |

## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>Finance 10.0.17 發行版本中已移除或棄用的功能

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>LCS 存放庫是電子報表組態的儲存選項

| &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 取而代之的是新監管組態服務 (RCS) 全域存放庫 |
| **被另一項功能取代？**   | 是 |
| **受到影響的產品領域**         | Dynamics 365 Finance、Supply Chain Management 和 Project Operations 產品|
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：我們計劃到 2022 年四月 1 日不再支援 Microsoft Dynamics Lifecycle Services (LCS) 存放庫作為電子報表 (ER) 組態的儲存選項。 屆時將發佈全新 Microsoft ER 組態以便專從全域存放庫下載。 全域存放庫可從 Dynamics 365 產品和 RCS 存取。 更多資訊，請參閱[從 RCS 匯入 ER 組態](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md)和 [Regulatory Configuration Service - Lifecycle Services 儲存棄用](../localizations/rcs-lcs-repo-dep-faq.md)。 |

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Finance 10.0.16 發行版本中已移除或棄用的功能

### <a name="vat-declaration-cz-and-control-statement-export-cz-electronic-reporting-formats-for-czech-republic"></a>捷克共和國的 "增值稅申報 (CZ)" 和 "控制報表匯出 (CZ)" 電子報表格式

| &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 以新格式取而代之 |
| **被另一項功能取代？**   | 是 |
| **受到影響的產品領域**         | 應用程式 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：我們計劃到 2022 年一月 22 日不再支援 "增值稅申報 (CZ)"、"控制報表匯出 (CZ)" 電子申報 (ER) 格式。 新增值稅申報 XML (CZ)、增值稅申報 Excel (CZ)、增值稅控制報表 XML (CZ) 格式改為按 “報稅" 模型引進。 |

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>比利時的 "分類帳交易匯出格式 (BE)" 電子申報格式和個別的 "分類帳交易匯出 (BE)" 模型

| &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 取而代之的是按 "標準稽核檔案 (SAF-T)" 模型的新 ER 格式。  |
| **被另一項功能取代？**   | 是 |
| **受到影響的產品領域**         | 應用程式 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：我們計劃到 2021 年十二月 1 日不再支援 "分類帳交易匯出格式 (BE)" 電子報表 (ER) 格式和個別的 "分類帳交易匯出 (BE)" 模型。 新 "總帳資料匯出 (BE)" 格式連同 "總帳資料模型測繪" 一起按 "標準稽核檔案 (SAF-T)" 模型引進。 |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>SSRS 格式的英國 "VAT 100" 報表

| &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 取而代之的是新 ER 格式 - "報稅模型" 下方的 "增值稅申報 Excel (英國)" 格式。  |
| **被另一項功能取代？**   | 是 |
| **受到影響的產品領域**         | 應用程式 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：我們計劃到 2021 年十二月 1 日不再支援 SSRS 格式的 "增值稅 100 報表"。 "報稅模型" 下的新 "增值稅申報 Excel (英國)" 格式在 [MTD 增值稅功能引進](../localizations/emea-gbr-mtd-vat-integration.md)。 |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>Finance 10.0.15 發行版本中已移除或棄用的功能

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Dynamics 365 的 Internet Explorer 11 支援版已經棄用

| &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 自 2020 年十二月起，所有 Dynamics 365 產品 的 Microsoft Internet Explorer 11 支援版已棄用，並且 2021 年八月之後將不再支援 Internet Explorer 11。<br><br>這將影響原意透過 Internet Explorer 11 界面設計使用 Dynamics 365 產品的客戶。 自 2021 年八月起，Internet Explorer 11 將不再支援此類 Dynamics 365 產品。 |
| **被另一項功能取代？**   | 我們建議客戶轉換到 Microsoft Edge。|
| **受到影響的產品領域**         | 所有 Dynamics 365 產品 |
| **部署選項**              | 全部|
| **狀態**                         | 已棄用。 2021 年八月起將不再支援 Internet Explorer 11。|

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Finance 10.0.12 發行版本中已移除或棄用的功能

### <a name="not-deprecated-polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>不棄用：波蘭 SSRS 報表：銷售增值稅登記、購買增值稅登記、歐盟彙總增值稅登記 – 功能參考 PL-00014

| &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 法律未明文要求。  |
| **被另一項功能取代？**   | 是 (附帶增值稅申報功能的標準稽核檔案 Excel 格式 - JPK_VDEK) |
| **受到影響的產品領域**         | 應用程式 |
| **部署選項**              | 全部 |
| **狀態**                         | 不棄用：自 2021 年四月 27 日起，我們計劃繼續支援 SSRS 報表：**銷售增值稅登記、購買增值稅登記、歐盟彙總增值稅登記 – 功能參考 PL-00014**。 另外也已經引進附帶增值稅申報功能 (JPK_VDEK) 的標準稽核檔案 Excel 格式範例。 |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Finance 10.0.11 發行版本中已移除或棄用的功能

### <a name="norwegian-standard-main-accounts"></a>挪威標準主科目

| &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 重新設計  |
| **被另一項功能取代？**   | 是 (取而代之的是 ER 格式應用程式特定參數) |
| **受到影響的產品領域**         | 應用程式 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：我們計劃到 2021 年四月 1 日不再支援標準主科目相關功能：參考欄位、相關資料表、資料實體。 |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Finance 10.0.7 發行版本中已移除或棄用的功能

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>工作流程申請更改對話方塊不再包括使用者選取下拉式清單

| &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 更改為含科目群組選取功能。  |
| **被另一項功能取代？**   | 是 |
| **受到影響的產品領域**         | 工作流程 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：我們計劃到 2020 年十二月 1 日不再支援不含科目群組選取的中文憑單類型設定。 更多有關新設計的細節，請參閱 [10.0.7 版本的最新消息](whats-new-changed-10-0-7.md)。 |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>先前關於已移除或棄用功能的公告
若要了解更多先前版本中已刪除或棄用的功能，請參閱[以前版本中已刪除或棄用的功能](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
