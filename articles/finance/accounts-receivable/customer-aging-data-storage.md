---
title: 客戶帳齡資料儲存
description: 本主題介紹使用外部儲存儲存客戶帳齡資料的流程。 您可以執行客戶帳齡資料儲存流程，以使輸出可匯出到外部系統。
author: JodiChristiansen
ms.date: 10/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ecd4f5359019e3c4778e21cc4946b9998cd519f
ms.sourcegitcommit: 9f8da0ae3dcf3861e8ece2c2df4f693490563d5e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2021
ms.locfileid: "8451194"
---
# <a name="customer-aging-data-storage"></a>客戶帳齡資料儲存

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

本主題介紹使用外部儲存儲存客戶帳齡資料的流程。 在 Microsoft Dynamics 365 Finance 中，您可以執行客戶帳齡資料儲存流程，以使輸出可匯出到外部系統。 執行該流程時，系統中可用的相同帳齡報表選項可用於外部系統。 詳細資料一律包含在匯出的資料中。

在輸出包含許多客戶和/或許多交易的情況下，將客戶帳齡資料提供給外部系統進行儲存會很有幫助。 如果現有的 **客戶帳齡** 報表因資料過多無法列印導致逾時，此功能提供了另一種獲取相同資料的方法。

## <a name="enable-the-customer-aging-data-storage-feature"></a>啟用客戶帳齡資料儲存功能

使用該功能之前，必須先在系統中啟用。 系統管理員可以使用功能管理設定來檢查功能的狀態，並根據需要打開它們。 在 **功能管理** 工作區，此功能以下列方式列出：

- **模組：** 信用和收款
- **功能名稱：** 客戶帳齡資料儲存

## <a name="run-the-customer-aging-data-storage-process"></a>執行客戶帳齡資料儲存流程

1. 前往 **信用和收款 \> 查詢和報表 \> 客戶 \> 客戶帳齡資料儲存**。
2. 選取 **新增**。
3. 在 **名稱** 欄位中，輸入流程的名稱。
4. 根據需要設定其餘參數。

    > [!NOTE]
    > 一律包含交易詳細資料，並且一律在批次作業中完成處理。

5. 選取 **確定**。
6. 重新整理 **客戶帳齡資料儲存** 頁面，以查看與 **處理狀態** 值一起顯示的 **批次名稱** 和 **批次執行時間** 值。 批次作業完成後，**處理狀態** 欄位設定為 **結束**，並會設定 **帳齡行數** 欄位。 如果批次作業是定期作業，則 **處理狀態** 欄位設定為 **正在等待**。
7. 選擇 **帳齡行數** 欄位旁邊的 **篩選** 按鈕以查看已為批次作業新增的篩選。

**客戶帳齡資料儲存** 頁面不包含結果。 然而 **客戶帳齡資料儲存** 資料實體可讓您將輸出匯出為資料管理支援的任何格式。

> [!NOTE]
> 在進行匯出之前，新增一個篩選以將匯出的結果限制為最近的帳齡。 例如，新增以下條件以傳回最近的批次執行：
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchName())
>
> 或者，新增以下條件以傳回目前使用者的最近批次執行：
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchNameForCurrentUser())
