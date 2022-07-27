---
title: 最佳化顧問概述
description: 本主題介紹如何使用最佳化顧問幫助確保財務和營運的最佳設定。
author: roxanadiaconu
ms.date: 07/23/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: sericks
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 8039ff51dfb07bbdf5d6a102de1ff4ddbfd907a5
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8460526"
---
# <a name="optimization-advisor-overview"></a>最佳化顧問概述

[!include [banner](../includes/banner.md)]

本主題介紹如何使用最佳化顧問幫助確保財務和營運的最佳設定。

## <a name="overview"></a>概觀

不正確的模組設定和設定會對應用程式功能的可用性、系統效能和業務流程的順利執行產生不利影響。 業務資料的品質 (例如，資料的正確性、完整性和清潔度) 也會影響系統效能，以及組織的決策能力、生產力等。

**最佳化顧問** 工作區是一個工具，讓進階使用者、商務分析師、函數顧問和 IT 支援函數識別模組設定和業務資料中的問題。 最佳化顧問建議模組設定的最佳做法並識別過時或不正確的業務資料。

最佳化顧問定期執行一組最佳做法規則。 有一組預設規則可用，但使用者也可以建立特定於他們的自訂、來自獨立軟體廠商 (ISV) 的解決方案和業務資料的規則。 如需如何建立規則的相關資訊，請參閱[為最佳化顧問建立規則](./create-rules-optimization-advisor.md)。

當偵測到違反規則行為時，會產生最佳化機會並出現在 **最佳化顧問** 工作區。 使用者可以直接從 **最佳化顧問** 工作區採取適當的糾正措施。

機會可以是公司特定的或跨公司的，具體取決於設定的類型和正在驗證的資料。 可以從所有公司查看跨公司機會。 若要查看特定公司的機會，您必須先選取公司。

標準安全策略適用於最佳化機會。 例如，與 **Warehouse Management** 模組設定相關的最佳化機會僅對有權存取 Warehouse Management 並可以更改其設定的使用者顯示。

當您對一些最佳化機會採取行動時，系統會根據業務流程執行階段的減少來計算機會的影響。 不幸的是，此功能不適用於所有最佳化機會。

若要進一步了解最佳化顧問，請觀看短片[Dynamics 365 for Finance and Operations 中的最佳化顧問](https://www.youtube.com/watch?v=MRsAzgFCUSQ)。

## <a name="optimization-rules"></a>最佳化規則

若要查看最佳化顧問規則的完整清單並查看規則的評估頻率，請進入 **系統管理**&gt;**定期工作**&gt;**維護診斷驗證規則**。 僅評估狀態為 **作用中** 的規則。 評估頻率可以設定為 **每日**、**每週**、**每月**，或 **未排程**。

若要觸發對計劃外規則的評估，或在其預定義計劃之外重新評估定期規則，請進入 **系統管理**&gt;**定期工作**&gt;**計劃診斷驗證規則**。 那麼，在 **診斷規則驗證** 對話方塊中，選取評估頻率。 將重新評估具有指定頻率的所有規則。

目前的最佳化規則集可以分為以下幾類。

### <a name="module-configuration-and-setup"></a>模組設定和設定

Warehouse Management 的設定是一個複雜的過程。 為了簡化該過程，引入了一些規則來幫助驗證設定的正確性。 例如，一條規則驗證為銷售訂單和轉移訂單的固定產品變型位置設定的倉庫位置指令。

此外，一些規則會檢查是否實際使用了已啟用的功能。 例如，一條規則確定您是否使用 **主計劃** 模組。 如果規則確定您未使用該模組，則會產生最佳化機會以建議您關閉計劃流程。

### <a name="system-configuration"></a>系統設定

如果未使用設定鍵控制的特定函數，則會產生最佳化機會，建議您禁用設定鍵。 設定鍵的範例包括 **實秤重量**、**預算計劃**、**專案** 和 **核准的廠商清單**。

### <a name="business-data-consistency-and-cleanup"></a>業務資料一致性和清理

如果主資料不正確 (例如，如果您有未定義單位的計量單位轉換，或者如果您有除以 0 的計量單位轉換\[零\])，會產生一個最佳化機會，建議您更正資料。 

如果您有太多批次處理作業歷史分錄、過時項目、已啟用倉庫項目的已關閉現有分錄等，或者如果這些分錄和項目太舊，則會產生最佳化機會以建議您清理資料。 透過保持資料清潔，您可以幫助提高整體系統效能。

### <a name="best-practices"></a>最佳實務作法

如果您沒有根據最佳做法執行某些業務流程 (例如，如果您在庫存關閉之前執行庫存預關閉，或者如果您使用計劃批次進行子分類帳日記帳批次傳輸)，最佳化機會會通知您最佳做法並要求您遵循它。

## <a name="optimization-opportunities"></a>最佳化機會

若要查看最佳化規則評估過程中產生的最佳化機會，請打開 **最佳化顧問** 工作區。

在此工作區中，您可以透過選取 **更多資訊** 來查看機會的相關資訊。 如果您希望系統採取措施並更正設定、清理資料等，這樣您就不必自己打開相應的頁面，請選取 **採取行動**。

沒有最佳化機會的工作流程。 在您選取 **採取行動** 或使用 **更多資訊** 對話方塊中提供的導覽路徑後，最佳化機會將從清單中消失。 如果糾正措施不能完全解決問題，下次評估規則時將再次產生機會。

如果機會不適用於您的角色，您可以選取 **從我的清單中隱藏**。 即使稍後再次觸發此機會背後的規則，您也不會在清單中看到該機會。

若要停用特定規則的評估，請選取規則產生的機會，然後選取 **停用分析**。

## <a name="additional-resources"></a>其他資源

[為最佳化諮詢建立規則](./create-rules-optimization-advisor.md)

[Dynamics 365 for Finance and Operations (影片) 中的最佳化顧問](https://www.youtube.com/watch?v=MRsAzgFCUSQ)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]