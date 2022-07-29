---
title: 在稅務設定中新增資料欄位
description: 本主題介紹如何透過新增資料欄位來自訂稅務設定。
author: Kai-Cloud
ms.date: 10/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 590c2d62995f260ba4277e1031349b0dc43f1417
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451080"
---
# <a name="add-data-fields-in-tax-configurations"></a>在稅務設定中新增資料欄位

[!include [banner](../includes/banner.md)]

本主題說明如何使用[在稅務整合中新增的資料欄位](tax-service-add-data-fields-tax-integration-by-extension.md)自訂稅務設定。

## <a name="customize-the-tax-data-model"></a>自訂稅務資料模型

1. 在Microsoft Dynamics 365 Finance，前往 **電子報告** > **稅務設定**。
2. 在組態樹狀目錄中，選擇 **稅務計算資料模型**。 接著，在動作窗格上選取 **建立設定**。 

  > [!NOTE] 
  > 如果沒有可用的設定提供程序，請建立一個並為您的稅務設定啟用它。 更多資訊，請參閱[建立組態提供者並標示為有效](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md)。
  
3. 在下拉式對話方塊中，選擇 **源自名稱的應稅文件模型: Tax Calculation Data Model, Microsoft**，輸入新稅務資料模型的名稱，然後選擇 **建立設定**。
4. 選擇您剛才建立的稅務資料模型，然後在動作窗格中選擇 **設計工具**。
5. 展開資料模型樹，選擇 **行**，然後選擇 **新增**。
6. 在 **建立節點** 對話方塊內輸入名稱，指定項目類型，然後選擇 **新增**。
7. 新增任何需要的列。
8. 在動作窗格上，選擇 **儲存**，然後選擇 **完成**。
9. 關閉頁面，然後查看您稅務資料模型的已完成版本。

## <a name="customize-the-tax-configuration"></a>自訂稅務格式

1. 在 Finance，前往 **電子報告** > **稅務設定**。
2. 在組態樹狀目錄中，選擇 **稅務計算設定**。 接著，在動作窗格上選取 **建立設定**。
3. 在下拉式對話方塊中，選擇 **源自名稱的稅務服務設定: Tax Calculation Configuration, Microsoft**，輸入新稅務設定的名稱，然後選擇 **建立設定**。
4. 選擇您剛才建立的稅務設定，然後在動作窗格中選擇 **設計工具**。
5. 在 **屬性** 部分中，在 **資料模型** 欄位內選擇您之前建立的自訂稅務資料模型。
6. 在 **資料模型版本** 欄位內，選擇稅務資料模型的已完成版本。
7. 選擇 **新增**，新增所需的稅收措施。
8. 在動作窗格上，選擇 **儲存**，然後選擇 **完成**。
9. 關閉頁面，然後查看您稅務設定的已完成版本。

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a>在自訂的稅務設定中實施稅務功能

1. 在 Regulatory Configuration Service (RCS)，前往 **全球化功能** > **稅務**。
2. 選擇 **新增**，輸入有關新功能的資訊，然後選擇 **建立功能**。
3. 在 **版本** 索引標籤上選擇該功能，然後選擇 **編輯**。
4. 在 **一般** 索引標籤上，在 **設定版本** 欄位，選擇自訂的稅務設定和版本。
5. 在 **管理列** 對話方塊內，選擇要包含在自訂稅收措施中的標題和行列，然後選擇向右箭頭按鈕將它們新增到 **選定的列** 列表。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
