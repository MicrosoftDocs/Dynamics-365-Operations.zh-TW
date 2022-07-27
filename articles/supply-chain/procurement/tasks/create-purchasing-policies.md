---
title: 創建採購原則
description: 本主題說明如何創建採購原則，以與您的採購業務流程保持一致。
author: Henrikan
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicyParameters, SysPolicy, RequisitionPurposeRule
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dde2df0f04ea8ed1b200ae731df7143cc8de3aae
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449220"
---
# <a name="create-purchasing-policies"></a>創建採購原則

[!include [banner](../../includes/banner.md)]

本主題說明如何創建採購原則，以與您的採購業務流程保持一致。 在您可以創建採購原則之前，您必須設定採購原則參數。 您可以創建、修改和停用採購原則，但不能刪除採購原則。 此程序通常由採購經理執行。 您可用示範資料公司 USMF 或自己的資料來使用此程序。


## <a name="set-up-policy-parameters"></a>設定原則參數
1. 在功能窗格中，前往 **模組 > 採購和委外 > 設定 > 原則 > 採購原則**。
2. 在動作窗格上，選擇 **參數**。
- 原則的優先順序規則，應用於組織中不同的級別。 顯示的組織單位取決於您的組織級別結構，以及層次結構中的哪些級別被分配了採購內部控制的目的。 例如，您的組織可能有法人實體、成本中心、區域和部門，但可能只有其中一些具有採購內部控制的級別結構目的。 預設情況下，公司類型的組織是可用的。  
3. 選擇 **原則規則類型參數** 索引標籤。
4. 在樹狀圖中，前往 **採購原則 > 採購申請控制規則**。
- 您可以在原則級別中，定義原則解決的優先順序。 但是，對於某些原則類型，您可以覆蓋個別原則規則類型的優先順序。 例如，您可以將採購原則的優先順序定義為：成本中心、部門、公司。 針對目錄原則規則，您可能要將原則的優先順序定義為：部門、成本中心、公司。 您可以變更目錄原則規則的優先順序。 當工作人員創建申請時，顯示的目錄由原則決定，該原則與工作人員的部門相關聯，接著是其成本中心，再來是其公司。  
- 如果列出了多個組織級別，您可以使用向上/向下箭頭，來設定採購申請控制規則的優先順序。  
5. 關閉頁面。

## <a name="create-a-new-policy"></a>創建新原則
1. 選擇 **新增**。
2. 在 **名稱** 欄位中，輸入一個值。
3. 在 **描述** 欄位中，輸入一個值。
- 一個採購原則，只能應用於一個組織階層。 例如，您可以有一個名為「Geographic」的階層，和一個名為「Department」的階層，並為每個階層制定不同的採購原則。  
- 選擇要應用該原則的組織。  
4. 選擇箭頭，以新增所選組織。
- 您可以重複此程序，以新增更多組織。  

## <a name="add-a-policy-rule"></a>新增原則規則
1. 在裡面 **原則規則類型** 列表，選擇 **申請目的規則**。
- 您將創建一個規則，將預設申請用途設定為使用類型，但允許選擇補貨類型。  
2. 按一下 **創建原則規則**。
3. 在 **允許手動覆寫** 欄位選擇 **是**。
4. 選擇 **關閉**。
- 現在，您可以為採購原則設定其他原則規則。 請注意，原則規則類型在單個採購原則中，不能具有同時處於活動狀態的重疊規則。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]