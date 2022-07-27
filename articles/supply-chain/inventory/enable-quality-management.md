---
title: 啟用品質和不符合管理
description: 本主題概述在 Microsoft Dynamics 365 Supply Chain Management 設定品質及不符合管理功能的流程。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c2c8b7e9a1a8d7692e1d2215e38de1b0f4d2d82
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448008"
---
# <a name="enable-quality-and-nonconformance-management"></a>啟用品質和不符合管理

[!include [banner](../includes/banner.md)]

本主題概述在 Microsoft Dynamics 365 Supply Chain Management 設定品質及不符合管理功能的流程。

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a>啟用品質和不符合管理

按照以下步驟在您的系統上啟用品質管理。

1. 前往 **倉庫管理\>設定\>庫存和倉儲管理參數**。
1. 在 **品質管理** 索引標籤，將 **使用品質管理** 選項設定為 *是*。
1. 在 **時薪** 欄位中，輸入以當地貨幣表示的每小時人工費率。 時薪用於計算與不符合相關的作業成本。 時薪和計算成本為不符合提供參考資訊。 它們不與其他功能互動。
1. 選擇 **報告設定**。
1. 為各種報告類型新增新行，並為每個報告選擇要使用的文件類型。
1. 關閉頁面。
1. 關閉頁面。

## <a name="quality-management-configuration-process"></a>品質管理設定流程

在開始使用品質管理功能和產生品質檢驗訂單之前，您必須設定系統和先決條件。 以下是設定品質管理所需的步驟清單。

1. [啟用品質和不符合管理。](#enable-qm)
1. 選用：[設定測試儀器](quality-test-instruments.md)。
1. [設定測試](quality-tests.md)。
1. [設定測試變數和結果](quality-test-variables.md)。
1. [設定測試群組](quality-test-groups.md)。
1. 選用：[設定品質群組，並連結到產品](quality-groups.md)。
1. 選用：[設定品質關聯](quality-associations.md)。

設定完成後，您可以開始建立和處理品質檢驗訂單。 (有關如何建立及使用品質檢驗訂單的資訊，請參閱[品質檢驗訂單](quality-orders.md)。)

## <a name="nonconformance-management-configuration-process"></a>不符合管理設定流程

在開始使用不符合管理功能和產生不符合之前，您必須設定系統和先決條件。 以下是設定不符合管理所需的步驟清單。

1. [啟用品質和不符合管理。](#enable-qm)
1. [設定負責核准不符合的工作人員](quality-responsible-workers.md)。
1. [設定問題類型](quality-problem-types.md)。
1. [設定隔離區](quality-quarantine-zones.md)。
1. [設定診斷類型](quality-diagnostic-types.md)。
1. [設定作業](quality-operations.md)。
1. 選用：[設定品質費用](quality-charges.md)。

設定完成後，您可以開始建立和處理不符合。 有關如何建立和處理不符合的更多資訊，請參閱[建立和處理不符合](tasks/create-process-non-conformance.md)。

## <a name="additional-resources"></a>其他資源

- [品質管理概觀](quality-management-processes.md)
- [啟用品質和不符合項管理](enable-quality-management.md)
- [倉庫流程的品質管理](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
