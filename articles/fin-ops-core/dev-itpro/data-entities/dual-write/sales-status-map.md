---
title: 設定銷售訂單狀態欄的對應
description: 本主題說明如何設定雙重寫入的銷售訂單狀態欄。
author: dasani-madipalli
ms.date: 06/25/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: damadipa
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 53d824ca2fb1eadf34e62bf9c08b837db3efaf42
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8460451"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-columns"></a>設定銷售訂單狀態欄的對應

[!include [banner](../../includes/banner.md)]

指示銷售訂單狀態的資料欄在 Microsoft Dynamics 365 Supply Chain Management 和 Dynamics 365 Sales 中具有不同的列舉值。 需要額外設定才能在雙重寫入中對應這些資料欄。

## <a name="columns-in-supply-chain-management"></a>Supply Chain Management 中的資料欄

在 Supply Chain Management 中，兩欄反映了銷售訂單的狀態。 您必須對應的資料欄是 **狀態** 和 **檔案狀態**。

**狀態** 列舉指定訂單的整體狀態。 此狀態顯示在訂單標題上。

**狀態** 列舉具有以下值：

- 未結訂單
- 已交貨
- 已請款
- 已取消

**檔案狀態** 列舉指定為訂單產生的最新文件。 例如，如果訂單已確認，則此文件為銷售訂單確認。 如果銷售訂單部分開票，然後確認剩餘行，則文件狀態保持為 **發票**，因為發票是在流程後期產生的。

**文件狀態** 列舉具有以下值：

- 確認
- 揀料單
- 裝箱單
- 發票

## <a name="columns-in-sales"></a>Sales 中的資料欄

在 Sales 中，兩欄指示了銷售訂單的狀態。 您必須對應的資料欄是 **狀態** 和 **處理狀態**。

**狀態** 列舉指定訂單的整體狀態。 它有以下的值：

- 使用中
- 已提交
- 已履行
- 已請款
- 已取消

**處理狀態** 引入了列舉，以便可以使用 Supply Chain Management 更準確地對應狀態。

下表顯示了 Supply Chain Management 中 **處理狀態** 的對應。

| 處理狀態   | Supply Chain Management 中的狀態 | Supply Chain Management 中的文件狀態 |
|---------------------|-----------------------------------|--------------------------------------------|
| 使用中              | 未結訂單                        | 無                                       |
| 已確認           | 未結訂單                        | 確認                               |
| 已領料              | 未結訂單                        | 揀料單                               |
| 部分交貨 | 未結訂單                        | 裝箱單                               |
| 已交貨           | 已交貨                         | 裝箱單                               |
| 已部分開立發票  | 已交貨                         | 發票                                    |
| 已請款            | 已請款                          | 發票                                    |
| 已取消           | 已取消                         | 不適用                             |

下表顯示了 Sales 和 Supply Chain Management 之間的 **處理狀態** 對應。

| 處理狀態   | Sales 狀態 | Supply Chain Management 中的狀態 |
|---------------------|-----------------|-----------------------------------|
| 使用中              | 使用中          | 未結訂單                        |
| 已確認           | 已提交       | 未結訂單                        |
| 已領料              | 已提交       | 未結訂單                        |
| 部分交貨 | 使用中          | 未結訂單                        |
| 已部分開立發票  | 使用中          | 未結訂單                        |
| 已部分開立發票  | 已履行       | 已交貨                         |
| 已請款            | 已請款        | 已請款                          |
| 已取消           | 已取消       | 已取消                         |

## <a name="setup"></a>設定

若要設定銷售訂單狀態欄的對應，您必須啟用 **IsSOPIntegrationEnabled** 和 **isIntegrationUser** 屬性。

若要啟用 **IsSOPIntegrationEnabled** 屬性，請執行以下步驟。

1. 在瀏覽器中，前往 `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`。 將 **\<test-name\>** 替換為貴公司的銷售連結。
2. 在打開的頁面上，找到 **organizationid**，並記下該值。

    ![尋找 organizationid。](media/sales-map-orgid.png)

3. 在 Sales 中，打開瀏覽器控制台，然後執行以下指令碼。 使用第 2 步中的 **organizationid** 值。

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on row update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![瀏覽器控制台中的 JavaScript 代碼。](media/sales-map-script.png)

4. 驗證 **IsSOPIntegrationEnabled** 已設定為 **True**。 使用步驟 1 中的 URL 檢查值。

    ![IsSOPIntegrationEnabled 已設定為 True。](media/sales-map-integration-enabled.png)

若要啟用 **isIntegrationUser** 屬性，請執行以下步驟。

1. 在 Sales 中，進入 **設定\>自訂\>自訂系統**，選取 **使用者表**，然後開啟 **表單\>使用者**。

    ![開啟使用者表單。](media/sales-map-user.png)

2. 在檔案總管中，尋找 **整合使用者模式**，然後按兩下將它新增到表單中。 儲存您的變更。

    ![將整合使用者模式列新增到表單。](media/sales-map-field-explorer.png)

3. 在 Sales 中，進入 **設定\>安全性\>使用者**，並將檢視表從 **已啟用的使用者** 更改到 **應用程式使用者**。

    ![將檢視表從啟用使用者更改為應用程式使用者。](media/sales-map-enabled-users.png)

4. 選取 **DualWrite IntegrationUser** 的兩個分錄。

    ![應用程式使用者清單。](media/sales-map-user-mode.png)

5. 將 **整合使用者模式** 欄的值更改為 **是**。

    ![更改整合使用者模式欄的值。](media/sales-map-user-mode-yes.png)

您的銷售訂單現已對應。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]