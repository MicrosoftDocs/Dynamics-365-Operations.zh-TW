---
title: 在廠商設計之間切換
description: 本主題介紹如何在財務和營運應用程式和 Dataverse 之間切換廠商資料整合。
author: RamaKrishnamoorthy
ms.date: 09/20/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 80de21b5e46e4f274626fa311f16e81312a2f5ab
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460447"
---
# <a name="switch-between-vendor-designs"></a>在廠商設計之間切換

[!include [banner](../../includes/banner.md)]





## <a name="vendor-data-flow"></a>廠商資料流程 

如果您選取使用 **帳戶** 表來儲存 **組織** 類型的廠商和 **聯絡人** 表來儲存 **人員** 類型的廠商，請設定以下工作流程。 否則，不需要此設定。

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>為組織類型的廠商使用擴展廠商設計

**Dynamics365FinanceExtended** 解決方案套件包含以下工作流程範本。 您將為每個範本建立一個工作流程。

+ 在帳戶表中建立廠商
+ 在廠商表中建立廠商
+ 在帳戶表中更新廠商
+ 在廠商表中更新廠商

若要使用工作流程過程範本建立新的工作流程過程，請執行以下步驟。

1. 為 **廠商** 表建立工作流程，並選取 **在帳戶表中建立廠商** 工作流程範本。 然後選取 **確定**。 此工作流程處理 **帳戶** 表的廠商建立方案。

    ![在帳戶表工作流程中建立廠商](media/create_process.png)

2. 為 **廠商** 表建立工作流程，並選取 **在帳戶表中更新廠商** 工作流程範本。 然後選取 **確定**。 此工作流程處理 **帳戶** 表的廠商更新方案。
3. 為 **帳戶** 表建立工作流程，並選取 **在廠商表中建立廠商** 工作流程範本。
4. 為 **帳戶** 表建立工作流程，並選取 **在廠商表中更新廠商** 工作流程範本。
5. 您可以根據需要將工作流程設定為即時工作流程或後台工作流程。 若要將工作流程設定為後台工作流程，請選取 **轉換為後台工作流程**。

    ![轉換為後台工作流程按鈕。](media/background_workflow.png)

6. 啟用您為 **帳戶** 和 **廠商** 表建立的工作流程，以開始使用 **帳戶** 表來儲存 **組織** 類型廠商的資訊。

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>為人員類型的廠商使用擴展廠商設計

**Dynamics365FinanceExtended** 解決方案套件包含以下工作流程範本。 您將為每個範本建立一個工作流程。

+ 在廠商表中建立人員類型的廠商
+ 在聯絡人表中建立人員類型的廠商
+ 在聯絡人表中更新人員類型的廠商
+ 在廠商表中更新人員類型的廠商

若要使用工作流程過程範本建立新的工作流程過程，請執行以下步驟。

1. 為 **廠商** 表建立一個工作流程，並選取 **在聯絡人表中建立人員類型的廠商** 工作流程範本。 然後選取 **確定**。 此工作流程處理 **聯絡人** 表的廠商建立方案。
2. 為 **廠商** 表建立一個工作流程，並選取 **在聯絡人表中更新人員類型的廠商** 工作流程範本。 然後選取 **確定**。 此工作流程處理 **聯絡人** 表的廠商更新方案。
3. 為 **聯絡人** 表建立一個工作流程，並選取 **在廠商表中建立人員類型的廠商** 範本。
4. 為 **聯絡人** 表建立一個工作流程，並選取 **在廠商表中更新人員類型的廠商** 範本。
5. 您可以根據需要將工作流程設定為即時工作流程或後台工作流程。 若要將工作流程設定為後台工作流程，請選取 **轉換為後台工作流程**。
6. 啟用您在 **聯絡人** 和 **廠商** 表上建立的工作流程，以開始使用 **聯絡人** 表來儲存 **人員** 類型的廠商的資訊。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]