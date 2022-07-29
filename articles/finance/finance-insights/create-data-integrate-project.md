---
title: 建立資料整合專案
description: 本主題說明如何建立資料整合專案。
author: ShivamPandey-msft
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 50f435f9d461667a1908baa529d73766085c183a
ms.sourcegitcommit: 6526acd0300d9c5800d3d7675d54e23090d031df
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/10/2022
ms.locfileid: "8451527"
---
# <a name="create-a-data-integration-project"></a>建立資料整合專案

[!include [banner](../includes/banner.md)]

本主題說明如何建立資料整合專案。

1. 登入 Microsoft Dynamics 365 Finance。
2. 前往 **工作區\>數據管理**，並選擇 **資料實體**。 等到所有資料實體都已重新整理，然後再繼續下一步。
3. 打開 [Power Apps 入口網站](https://make.powerapps.com/)，然後按照以下步驟操作：

    1. 選擇適當的環境。
    2. 在左側功能窗格中，選擇 **Dataverse \> 連接器**。
    3. 連接到以下各項的相應執行個體：

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

4. 打開 [Power Apps 環境](https://admin.powerapps.com/environments)，然後按照以下步驟操作：

    1. 選取 **資料整合**。
    2. 選取 **連接集**。
    3. 選取 **新增連接集**。
    4. 輸入連接名稱。
    5. 為以下項目選擇相應的連接：

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

    6. 選擇相應的組織對應。
    7. 選取 **建立**。

5. 打開 [Power Apps 環境](https://admin.powerapps.com/environments)，然後按照以下步驟操作：  

    1. 使用您剛剛建立的連接集為以下範本建立資料整合專案：

        - 客戶付款見解結果 (CDS 到 Fin and Ops 10.0.17+)
        - 現金流時間序列結果 (CDS 到 Fin and Ops)
        - 預算時間序列結果 (CDS 到 Fin and Ops)

    2. 為每個專案設定相應的計劃。

> [!NOTE]
> 如果在 Dataverse 中未顯示所需實體，請前往 **信用和收款** > **設定** > **Finance Insights** > **Finance Insights 參數**，啟用 **客戶付款預測** 功能，然後選擇 **建立預測模型**。 AI 模型部署完成後，將部署建立整合所需的 Dataverse 實體。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
