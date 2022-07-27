---
title: 設定訂購單的工作範本
description: 本主題介紹如何設定簡單的工作範本，以便在入庫收到的品項時使用。
author: Mirzaab
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 32dbdd8243c6b37cfe0c42d2e7b06adfa32a947a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448506"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a>設定訂購單的工作範本

[!include [banner](../../includes/banner.md)]

本主題介紹如何設定簡單的工作範本，以便在入庫收到的品項時使用。 工作範本確定了從接收區域移動品項時，在行動裝置上呈現給倉庫工作人員的指令集。 您可在 USMF 示範資料公司中提及的資料執行此程序。 在開始本指南之前，請建立一個工作池識別碼。 在此範例中，使用了名為 [入庫] 的工作池識別碼。 此程序供倉庫經理所用。

1. 在瀏覽窗格中，前往 **模組 > 倉庫管理 > 設定 > 工作 > 工作範本**。
2. 在 **工作訂單類型** 欄位中，選取 **訂購單**。

## <a name="create-a-work-template-header"></a>建立工作範本標題
1. 選取 **新增**。
2. 在 **序號** 欄位中輸入數字。 這是評估工作範本的順序。 如有需要，您可以修改順序。  
3. 在 **工作範本** 欄位輸入值。 這是該範本的唯一識別碼。  
4. 在 **工作範本描述** 欄位中，輸入一個值。
    - **有效** 選項在您填寫完範本所需的所有資訊，並選擇 **儲存** 後才會勾選。  
    - **訂購單** 類型的工單無法自動處理，因此將 **自動處理** 選項設定為 **否**。  
5. 在 **工作池識別碼** 欄位中，輸入一個值。 工作池識別碼可讓您將工作組織成群組。 您在此處設定的值將是使用此範本建立的所有工作的預設值。  
6. 在 **工作優先順序** 欄位，輸入 `1`。 這表示工作的重要性，您在此處設定的值將是使用此範本建立的所有工作的預設值。  
7. 選取 **儲存**。 您必須儲存工作範本標題才能使用 **編輯查詢** 按鈕。  

## <a name="set-up-the-query-for-the-work-template"></a>設定工作範本的查詢
1. 選取 **編輯查詢**。 我們將設定範本只能在特定倉庫中使用的限制。  
2. 選取 **新增**。
3. 在新行的 **欄位** 欄位，輸入 `warehouse`。
4. 在 **條件** 欄位中，輸入一個值。
5. 選取 **確定**。
6. 選取 **是**。

## <a name="set-work-template-details"></a>設定工作範本詳細資料
1. 選取 **新增**。
2. 在 **工作類型** 欄位中，選取 **揀貨**。
3. 在 **工作類別識別碼** 欄位中，輸入 `purchase`。 您在此處設定的工作類別將預設顯示在使用此範本建立的 [揀貨] 類型的所有工作行上。 無法覆寫工作訂單行上的工作類別。 工作類別會用於引導和/或限制倉庫工作人員在行動裝置上可處理的工單明細類型。  
4. 選取 **新增**。
5. 請在 **工作類型** 欄位，選取 **放置**。
6. 在 **工作類別識別碼** 欄位中，輸入一個值。 揀貨和放置指令是一組的。 每個揀料/放置組必須具有相同的工作等級。 使用您為揀料指令提供的相同工作類別。  
7. 選取 **儲存**。 請注意，現已選取 **有效** 核取方塊。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]