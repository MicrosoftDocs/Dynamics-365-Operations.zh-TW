---
title: 客戶自有資產的維護帳單
description: 本主題說明如何建立、處理和計費對客戶擁有資產進行的維護工作。
author: johanhoffmann
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjInvoiceTable, ProjProjectsListPage, ProjTable, EntAssetWorkOrderType, EntAssetWorkOrderProjectSetup, EntAssetObjectTable, EntAssetWorkOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a48e681da1801ef3c0d1c9c03cebaa5eecd37d76349a7b1c3cfe53e892fae489
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447255"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a>客戶自有資產的維護帳單

[!include [banner](../../includes/banner.md)]

*工單帳單* 功能可讓您建立、處理和計費對客戶擁有資產進行的維護工作。 此功能允許您執行以下工作：

- 將客戶與他們擁有的資產連結起來。
- 建立工單時可選擇客戶並查看客戶擁有的資產。
- 為每個客戶設定一個父系專案。
- 根據工單登記工時、項目、支出和費用，然後稍後為客戶建立發票提案。

此外，該功能還提供以下功能：

- 客戶父系專案的專案合約會自動複製到相關的工單專案。
- 資產管理現在可以在工單預測及工單日記帳使用 *費用* 專案交易類型。

## <a name="turn-on-the-customer-billing-feature"></a>開啟客戶帳單功能

使用此功能之前，您必須先在系統中開啟。 管理員可利用[功能管理](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)設定檢查功能狀態，並開啟該功能。 在 **功能管理** 工作區，該功能會依以下方式列出：

- **模組：***專案管理和會計*
- **功能名稱：***工單帳單*

## <a name="example-scenario"></a>範例案例

如欲瞭解此功能的運作方式，請完成以下範例情境。

要使用此處指定的範例記錄和值完成此情境，您必須使用一個已安裝標準[示範資料](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md)的系統。 在開始之前，您必須先選擇 **USMF** 法律實體。

在生產系統上工作時，您還可以將此案例當作使用該功能的指南。 但是，在此情況下，您必須替換為自己的值，並且您可能會缺少標準示範資料提供的某些類型的必需記錄。

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a>第 1 步：為客戶建立新的專案合約

1. 前往 **專案管理和會計 \> 專案 \> 專案合約**。
1. 在動作窗格上，選擇 **新增**。
1. 在 **新專案合約** 對話方塊中，設定以下值：

    - **名稱：***Pelican Wholesales*
    - **資金類型：***客戶*
    - **資金來源：***US-013* (*Pelican Wholesales*)

1. 選擇 **確定**。

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a>第 2 步：為客戶建立新的父系專案

您在此處建立的父系專案將在為客戶建立工單時使用。

1. 前往 **專案管理和會計 \> 專案 \> 所有專案**。
1. 在動作窗格上，選擇 **新增**。
1. 在 **新專案** 對話方塊中，設定以下值：

    - **專案類型：***時間和材料*
    - **專案名稱：***Pelican Wholesales 工單*
    - **專案群組：***TM*
    - **專案合約識別碼：***Pelican Wholesales* (您之前建立的合約)
    - **開始日期：** 選擇今天的日期。

1. 選擇 **建立專案**。
1. 新專案已開啟。 記下 **專案識別碼** 值。 您稍後必須輸入此值。

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a>步驟 3：在資產管理中建立新的工單類型

1. 前往 **資產管理 \>設定 \>工單 \>工單類型**。
1. 在動作窗格上，選擇 **新增**。
1. 一筆新記錄新增到清單中。 為它設定以下值：

    - **工單類型：***服務*
    - **名稱：***服務工單*
    - **工單生命週期狀態：***標準*

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a>第 4 步：將客戶帳戶連結到父系專案

您現在必須將客戶帳戶連結到資產管理中專案設定的父系專案。

1. 前往 **資產管理 \> 設定 \> 工單 \> 專案設定**。
1. 在 **父系專案** 索引標籤選擇 **新增** 以新增一行。
1. 在新的明細上，設定以下值：

    - **客戶帳戶：***US-013* (*Pelican Wholesales*)
    - **專案識別碼：** 輸入您之前記下的專案識別碼。

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a>步驟 5：將專案群組和類型連結到工單專案

您應該還在 **專案設定** 頁面 (**資產管理 \> 設定 \> 工單 \> 專案設定**)。

1. 在 **專案群組** 索引標籤選擇 **新增** 以新增一行。
1. 在新的明細上，設定以下值：

    - **工單類型：***服務* (您之前建立的工單類型)
    - **專案群組：***TM*

> [!NOTE]
> 工單專案的專案合約始終繼承自父系專案。

### <a name="step-6-link-an-asset-to-the-customer-id"></a>第 6 步：將資產連結到客戶識別碼

1. 前往 **資產管理 \> 資產 \> 使用中資產**。
1. 在 **篩選** 欄位輸入 *VE-102*，並選擇依據 **資產** 篩選。
1. 選擇資產以開啟其設定。
1. 在 **客戶** FastTab，設定 **客戶帳戶** 欄位為 *US-013* (*Pelican Wholesales*)。

    **名稱** 欄位自動更新為 *Pelican Wholesales*。

### <a name="step-7-create-a-new-work-order-on-the-asset"></a>步驟 7：在資產建立新的工單

1. 前往 **資產管理 \>工單 \> 使用中工單**。
1. 在動作窗格上，選擇 **新增**。
1. 在 **建立工單** 對話方塊中，設定以下值：

    - **工單類型：***服務*
    - **說明：***修理卡車*
    - **客戶帳戶：***US-013* (*Pelican Wholesales*)
    - **資產：***VE-102*

        > [!NOTE]
        > 查詢僅顯示連結到所選客戶帳戶的資產。

    - **維護作業類型：***維修*
    - **行業：***機械*
    - **服務等級：***4*

1. 選擇 **確定**。

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a>第 8 步：檢閱工單並開始處理

在本節中，您將處理在上一節中建立的工單。

1. 按照以下步驟驗證父系專案是 *Pelican wholesales 工單* 專案：

    1. 在 **工單維護作業** 區段，選擇一行。
    1. 在 **行詳細資料** FastTab，檢查 **專案識別碼** 的值。 該值應該是 *\<Parent-Project-ID\>-\<Project-ID\>* 形式的連字符號數字。 此值是一個連結。
    1. 選擇專案識別碼連結以開啟一個頁面，您可以在其中查看父系專案和專案名稱。

1. 在動作窗格上，在 **工單** 索引標籤的 **生命週期狀態** 群組，選擇 **更新工單狀態**。
1. 在 **更新工單狀態** 對話方塊的 **選擇** 欄，在 **生命週期狀態** 欄位設定為 *進行中* 的列選擇核取方塊。
1. 選擇 **確定**。
1. 在 **生命週期狀態：進行中** 對話方塊，選擇 **確定**。

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a>第 9 步：在工單發佈花費的時數並建立新的發票提案

在本節中，您將繼續處理在上一節中處理的工單。

1. 請在動作窗格 **專案** 群組中的 **工單** 索引標籤上，選擇 **日記帳**。

    隨即出現 **工單日記帳** 頁面。 在這裡，您可以登記在工單花費的時間。

1. 在 **時數** FastTab，選擇 **新增明細**。
1. 在新行上將 **時數** 欄位設定為 *4*。
1. 在動作窗格上，選擇 **公布日記帳**。
1. 關閉 **工單日記帳** 頁面以返回工單。
1. 在動作窗格上，在 **發票** 索引標籤選擇 **新發票提案**。
1. 在 **建立發票提案** 對話方塊的 **專案交易** 區段，針對要開立發票的每一行選擇 **選擇** 核取方塊。
1. 選擇 **確定** 以關閉對話方塊並檢視新的發票提案。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]