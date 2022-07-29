---
title: 電子發票常見問題
description: 本主題提供有關電子發票的常見問題資訊。
author: gionoder
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 2d4e7c79c83b9d60469c2b87a7b9120e0d4c13a695badfb2254a85cee629c933
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450750"
---
# <a name="electronic-invoicing-faq"></a>電子發票常見問題

[!include [banner](../includes/banner.md)]

本主題提供有關電子發票資訊的解答。 電子發票擴展了 Dynamics 365 Finance、Dynamics 365 Supply Chain Management 和 Dynamics 365 Project Operations 現有的電子發票功能。 

## <a name="what-is-important-about-electronic-invoicing-and-why-should-it-matter-to-my-organization"></a>電子發票的重要性是什麼？為什麼它對我的組織很重要？

隨著組織在全球範圍內的發展和跨地區的擴張，營運複雜性和風險持續加劇。 保持合規性並適應經常變化的法規是一項日益嚴峻的挑戰，在開票方面尤為重要。 由於公司依賴紙質文件和人工密集型流程，發票傳統上成本高昂且容易出錯。  

組織已開始擺脫紙質發票，以降低成本並加快端到端流程。 政府越來越多地將電子發票作為稅收數字化的關鍵組成部分。 透過要求組織以數字方式向稅務機關提交即時稅務資訊，政府可以最大限度地減少逃稅和操縱，並減少欺詐。 

世界正在轉向無紙化文件處理，如果不實施電子發票，客戶可能會面臨合規性問題、不必要的成本和落後於競爭對手的風險。 

## <a name="doesnt-finance-supply-chain-management-and-project-operations-already-include-electronic-invoicing-functionality-what-value-does-this-provide-to-me-as-a-customer"></a>Finance、Supply Chain Management 和 Project Operations 是否已經包含電子發票功能？ 作為客戶，這對我有什麼價值？ 

電子發票擴展了 Finance、Supply Chain Management 和 Project Operations 中存在的電子發票功能。 該功能也簡化了對最新電子發票標準的遵守，並為不同地區的電子發票處理和交換提供了一致的體驗。 電子發票的功能帶來了一系列好處，包括： 

   - 更快、更輕鬆地採用國家/地區的特定要求。
   - 電子發票解決方案實施的標準化。 
   - 增強的電子發票處理可追溯性。  
   - 更容易維護以符合不斷變化的法律要求和當地商業慣例。 
   - 簡化的解決方案包裝。
   - 對大量提交的文件進行擴展，從而加快周轉速度。
   - 能夠與其他公司分享您的解決方案。

## <a name="does-electronic-invoicing-service-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>電子發票服務是否支持 Finance、Supply Chain Management 和 Project Operations 的本地安裝？ 

目前平台不允許使用本地版本，並且沒有計劃在未來支持它。

## <a name="does-electronic-invoicing-service-interface-with-the-vendor-import-automation-feature"></a>電子發票服務是否與供應商匯入自動化功能介面？

否。 有這個介面的計劃，但沒有計劃的時間表。 當計劃時，日期將在[發布計劃](/dynamics365/release-plans/)。

## <a name="how-does-electronic-invoicing-service-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>電子發票服務如何處理電子發票中檔案附件？ 將 PDF 文件嵌入 XML 文件時是否需要 SharePoint 服務器？

附加到電子發票的文件作為嵌入在 XML 元素中的二進制資料進行處理。 嵌入 PDF 檔案不需要 SharePoint 伺服器，但附件必須儲存在 Finance、Supply Chain Management 和 Project Operations 文件管理系統中。

## <a name="is-electronic-invoicing-service-available-according-to-the-regulations-of-my-countryregion"></a>電子發票服務是否符合我所在國家/地區的規定？

電子發票服務是一個全球可用的微服務平台。

Microsoft 計劃為 Microsoft 功能本地化的國家/地區發布電子發票格式和整合。 關於詳細資訊，請參閱[電子發票功能的可用性](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features)。

如果您所在國家/地區的電子發票格式未列出，則該平台的目標是在將來支持此方案。 您仍然可以從電子開票的設定功能中受益，並自己設定電子開票格式，或者您可以與合作夥伴/ISV 一起為您的組織設定這些格式。

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>Dynamics 365 for Regulatory Services 是連結到 Finance 或 Supply Chain Management 的 Human Resources 或 Project Operations 等新模組嗎？ 需要額外的費用嗎？

Dynamics 365 for Regulatory Services (RCS) 是一種用於設定全球化資源的雲端服務。 RCS 對所有 Finance、Supply Chain Management 和 Project Operations 授權持有者免費。

如需註冊 RC，請前往 <https://marketing.configure.global.dynamics.com/>。

如需相關資訊，請參閱 [Regulatory Configuration Services (RCS) - 全域功能](rcs-globalization-feature.md)。

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing-service-or-just-turn-it-on-in-feature-management"></a>我是否需要註冊才能獲得電子發票服務，或者只能在功能管理中開啟？

如果您擁有 Finance、Supply Chain Management 和 Project Operations 的授權，請參閱[開始使用電子發票附加服務管理](e-invoicing-get-started-service-administration.md)註冊電子發票。

## <a name="does-electronic-invoicing-service-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>電子發票服務是否適用於第 1 層虛擬機器？ 環境的最低要求是什麼？

與電子發票服務整合需要至少一個第 2 層虛擬機器來託管 Finance 或 Supply Chain Management。 有關環境計劃的詳細資訊，請參閱[環境計劃](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)。

## <a name="does-electronic-invoicing-service-have-a-test-mode-for-testing-invoice-submission"></a>電子發票服務是否有測試發票提交的測試模式？

這可以透過設定來實現。 要測試發票提交，您可以從用戶驗收測試 (UAT) 環境連接到 Finance 或 Supply Chain Management 並提交測試發票。 電子發票支持設定測試數位憑證，對於需要數位核准的電子發票，從稅務機關發布的測試 Web 服務中設定 URL。

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>是否有關於開箱即用特定國家/地區的電子發票功能的文件？

是的。 有關電子發票功能的可用性及其支持的格式的資訊，請參閱[電子發票功能的可用性](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features)。

## <a name="does-the-electronic-invoicing-service-allow-a-legal-entity-in-finance-or-supply-chain-management-that-is-configured-for-a-specific-country-to-consume-electronic-invoicing-features-from-different-countryregions"></a>電子發票服務是否允許為特定國家/地區設定的 Finance 或 Supply Chain Management 中的法人實體，使用來自不同國家/地區的電子發票功能？

是的。 如果以下情況屬實，則可以使用電子發票功能來處理獨立於法人所在國家/地區的業務文件提交：

   - 正在生成的業務文件使用適當的文件模型對應。
   - 業務發票與電子開票功能中設定的適用性規則匹配。

## <a name="does-the-electronic-invoicing-service-use-the-same-configuration-and-design-experience-provided-by-the-electronic-reporting-module-in-finance-and-supply-chain-management"></a>電子發票服務是否使用 Finance 和 Supply Chain Management 中電子報告模組提供的相同設定和設計體驗？ 

是的。 Finance 和 Supply Chain Management 的電子報告 (ER) 模組中使用的相同設計器工具用於建立和設定數據模型對應和文件格式設定。 這些設計器工具也用於 Regulatory Configuration Services (RCS) 中，以建立和設定用於設定電子發票功能的資料模型對應和文件格式設定。

## <a name="can-the-applicability-rules-be-extended-and-configured-so-that-they-arent-tied-to-any-specific-parameter-such-as-a-legal-entity"></a>是否可以擴展和設定適用性規則，使其不與任何特定參數 (例如法人實體) 綁定？

是的。 適用性規則是完全可設定的。 您可以添加或刪除子句、建構邏輯操作以及分組和取消分組子句。 更多資訊，請參閱[應用規則](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#applicability-rules)。

## <a name="does-the-electronic-invoicing-service-support-adding-other-er-format-configurations-to-generate-other-types-of-documents-does-it-support-sending-the-documents-electronically-to-customers-such-as-a-delivery-note"></a>電子發票服務是否支持添加其他 ER 格式設定以生成其他類型的發票？ 它是否支持以電子方式將文件發送給客戶，例如交貨單？

您可以使用其他 ER 格式設定來生成所需的輸出文件。 但是，ER 格式設定必須源自 Finance 或 Supply Chain Management 中設定的相同 ER 發票模型映射以生成業務文件。 電子發票不支持直接將輸出文件作為 EDI 交易發送給客戶。

## <a name="does-the-electronic-invoicing-service-support-exchanging-electronic-invoices-with-customers-does-it-support-configuring-different-invoice-formats-for-the-same-invoice"></a>電子發票服務是否支持與客戶交換電子發票？ 是否支持為同一張發票設定不同的發票格式？

接收和匯入廠商電子發票的功能已在路線圖中，但目前不支持自動將電子發票發送給客戶。

## <a name="does-the-electronic-invoicing-service-extend-to-support-exchanging-edi-messages-with-other-companies"></a>電子發票服務是否擴展到支持與其他公司交換 EDI 訊息？

電子發票服務的重點是交換受監管合規要求驅動的電子發票訊息類型。 接收和匯入供應商電子發票已在路線圖中，但目前不支持開箱即用地向客戶發送電子發票檔案，除非在向客戶發送電子發票是監管要求的情況下。

## <a name="does-the-electronic-invoicing-service-support-importing-or-merging-customizations-made-in-the-er-format-configurations-from-the-legacy-electronic-invoicing-feature"></a>電子開票服務是否支持從舊版電子開票功能匯入或合併在 ER 格式設定中進行的自訂？

您可以在電子發票服務中重複使用 ER 格式設定。 但是，ER 格式設定必須從對應電子發票功能設計使用的相同 ER 發票模型衍生，並且在 Finance 或 Supply Chain Management 中設定以生成業務文件。

## <a name="does-the-electronic-invoicing-service-support-issuing-electronic-invoices-from-custom-made-tables-if-so-how-do-you-create-the-er-data-model-configurations-for-these-new-tables-and-entities"></a>電子發票服務是否支持從自訂資料表開具電子發票？ 如果是這樣，您如何為這些新表和實體建立 ER 資料模型設定？

是的。 但是，這需要自訂發票模型對應並向自訂資料表新增必要的引用，或者根據複雜性建立新的發票模型對應。

## <a name="does-the-electronic-invoicing-service-support-different-web-service-endpoints"></a>電子發票服務是否支持不同的網頁服務端點？

電子發票支持不同的網路服務端點。 您可以將可設定的整合與 REST Web 服務或許多參數化的國家/地區特定網頁服務整合一起使用。 可以使用不同版本的設定為相同的網頁服務和 API 設定不同的端點。 更多詳細資料，請參閱[依照動作列出的參數列表](e-invoicing-setup.md#list-of-parameters-by-action)。

## <a name="is-electronic-invoicing-integrated-with-the-various-invoice-operators-apis-from-the-nordic-countries-or-should-that-be-handled-on-a-case-by-case-basis"></a>電子發票是否與來自北歐國家的各種發票營運商的 API 整合，還是應該根據具體情況進行處理？

Microsoft 能透過使用電子發票功能不斷擴展功能範圍以提供開箱即用的整合。 有關支持的格式和整合的更多資訊，請參閱[電子發票功能的可用性](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#availability-of-electronic-invoicing-features)。

> [!NOTE] 
> 如果您沒有找到所需的答案，請將您的問題透過電子郵件發送至產品開發團隊<D365EInvoicePreview@microsoft.com>。 我們將與您聯繫或改進此常見問題解答的覆蓋範圍。
