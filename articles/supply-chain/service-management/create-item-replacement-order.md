---
title: 創建項目更換訂單
description: 通常在產品退回和檢查後，才會創建項目更換訂單。
author: josaw1
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnReplaceItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 57bbb8eb638b990914dc00f9700ff0c1925c48852862b02e09f3f26415d3e347
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446943"
---
# <a name="create-an-item-replacement-order"></a>創建項目更換訂單 

[!include [banner](../includes/banner.md)]


通常在產品退回和檢查後，才會創建項目更換訂單。 但是，如果必須在退回之前更換項目，或者當原始項目不會退回時，您可以在創建退貨單後，立即創建項目更換訂單。

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a>在收到退回的項目後創建更換訂單

1.  點擊 **銷售和營銷**\>**通用**\>**退貨單**\>**所有退貨單**。

2.  創建一個新的退貨單，或從列表中選擇一個退貨單以打開 **退貨單 - RMA 編號：%1、%2** 表單。

3.  點擊 **退回行**，然後選擇 **更換項目**。

4.  選擇要更換退回項目的項目。 輸入項目規格，然後點擊 **申請**。

5.  點擊 **裝箱單** 為退貨單生成裝箱單。 為您選擇的更換項目生成銷售訂單。
    
    為替換項目創建銷售訂單後，將自動搜索銷售合約，如果有適用的銷售合約，則將其應用於銷售訂單。

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a>在收到退回的項目之前創建更換訂單

1.  點擊 **銷售和營銷**\>**通用**\>**退貨單**\>**所有退貨單**。

2.  創建一個新的退貨單，或從列表中選擇一個退貨單以打開 **退貨單 - RMA 編號：%1、%2** 表單。

3.  如果您想識別退回項目的銷售訂單，點擊 **查找銷售訂單**。 完成 **查找銷售訂單** 表格，然後點擊 **確定** 關閉表單並返回 **退貨單 - RMA 編號：%1、%2** 表單。 退回項目的銷售訂單會複製到退貨單。

4.  點擊 **更換訂單** 以打開 **創建銷售訂單** 表格。

5.  選擇 **複製退貨單行** 核取方塊，以便從您所選的 **退貨單 - RMA 編號：%1，將詳細資訊轉換到 %2** 此銷售訂單。

6.  根據需要輸入或修改詳細信息。
    
    如果您已經在步驟 3 中識別銷售訂單，並且退回項目的銷售訂單行，與銷售合約已經建立連結，則項目更換訂單中，適用於銷售合約的識別碼將自動顯示在 **銷售合約 ID** 欄位。

7.  點擊 **確定** 以關閉 **創建銷售訂單** 表單，並打開 **銷售訂單** 表單，您可以在其中繼續輸入新的銷售訂單信息。 退貨單中任何適用的行，都將復製到新的銷售訂單中。 
    
    如果銷售合約的識別碼自動顯示在 **銷售合約 ID** 欄位，則表示銷售合約已連結到項目更換訂單的銷售訂單抬頭。 如果銷售合約中存在尚未履行的承諾用量，並且銷售訂單是於銷售合約到期之前創建，則銷售合約行和銷售訂單行之間會建立連結。 因此，銷售合約中的信息 (例如：項目價格) 將復製到新的銷售訂單行。 
  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]