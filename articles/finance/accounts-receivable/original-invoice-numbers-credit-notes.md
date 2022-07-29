---
title: 對貸項通知單中原始發票的徵詢依據
description: 本主題解釋如何在相關貸項通知單設定和列印原始發票編號。
author: ilkond
ms.date: 10/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 7147c5bea5273f385b004effe0844b5f4541a881
ms.sourcegitcommit: 2113678369f47944f8725ca656f461fa159f87f6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2021
ms.locfileid: "8451107"
---
# <a name="references-to-original-invoices-in-credit-notes"></a>對貸項通知單中原始發票的徵詢依據

[!include [banner](../includes/banner.md)]


某些國家和地區的法律要求是貸項通知單印製版須包括對原始發票的徵詢依據。 本主題解釋如何在相關貸項通知單設定和列印原始發票編號。

## <a name="prerequisites"></a>先決條件

- 在 **功能管理** 工作區開啟 **銷售和專案發票報表的信用發票開立版面** 功能。 更多資訊，請參閱[功能管理概觀](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)。
- 必要文件的列印格式必須在列印管理中配置。

本主題說明的功能適用下列商業文件：

**應收帳款**

- 普通發票貸方通知單
- 客戶貸項通知單

**專案管理和會計**

- 專案貸項通知單

## <a name="configure-accounts-receivable-parameters"></a>配置應收帳款參數

按照下列步驟設定可控制原始發票的徵詢參數是否在相關貸項通知單列印。

1. 前往 **應收帳款**\>**設定**\>**應收帳款參數**。
2. 在 **更新** 索引標籤上的 **發票** FastTab，設定 **將信用發票開立版面套用到銷售和專案發票報表** 選項為 **是**。

![應收帳款參數配置中。](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a>定義原始發票的徵詢依據

請使用下列程序，根據文件類型定義對原始發票的徵詢依據。

### <a name="free-text-credit-note"></a>普通發票貸方通知單

1. 前往 **應收帳款**\>**發票**\>**所有普通發票**。
2. 建立新貸項通知單，或選取既有的貸項通知單。
3. 打開發票。
4. 請在 **功能** 群組中，**發票** 索引標籤上的動作窗格選取 **開立貸項發票**。
5. 請輸入原始發票的徵詢依據，並選取更改原因。

![定義普通發票的徵詢依據。](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a>客戶貸項通知單

1. 前往 **應收帳款**\>**訂單**\>**所有銷售訂單**。
2. 選擇並打開必須改正，已經開立發票的銷售訂單。
3. 請在 **貸項通知單** 群組中，**銷售** 索引標籤上的動作窗格選取 **貸項通知單**。
4. 輸入改正的原因。 自動成立對原始發票的徵詢依據。

![定義銷售訂單的徵詢依據。](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a>專案貸項通知單

1. 前往 **專案管理和會計**\>**專案發票**\>**專案發票**。
2. 選取並打開必須改正的專案發票。
3. 請在 **功能** 群組中，**專案發票** 索引標籤上的動作窗格選取 **針對貸項通知單選取**。
4. 選取 **開立貸項發票**。
5. 輸入改正的原因。 自動成立對原始發票的徵詢依據。

![定義專案發票的徵詢依據。](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a>貸項通知單列印中

當您列印普通、客戶和專案貸項通知單時，它們將包括對原始發票的徵詢依據和改正原因。

![貸項通知單列印版。](media/credit-note-FTI.jpg)

> [!NOTE]
> 確定文件的列印格式已正確配置，假設將列印對原始發票的徵詢依據。

## <a name="references-to-original-invoices-in-debit-notes"></a>貸項通知單中對原始發票的徵詢依據

對原始發票的徵詢依據預設可針對貸項通知單輸入。 例如，您可以在對原始發票進行負向 (減少) 改正時輸入徵詢依據。

若要在對原始發票進行正向 (增加) 改正時輸入徵詢依據，您必須啟用 **功能管理** 工作區中的 **借方通知單中對原始發票的徵詢依據**。  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
