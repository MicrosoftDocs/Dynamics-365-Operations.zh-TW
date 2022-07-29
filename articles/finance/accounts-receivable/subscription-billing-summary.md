---
title: 訂閱計費概覽
description: 本主題介紹 Microsoft Dynamics 365 Finance中的訂閱計費 。
author: JodiChristiansen
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-02-09
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: b94ac36e49d55ad42909877d77903cd40cb22cbe
ms.sourcegitcommit: 6102f70d4595d01b90afe5b23dfd8ec2ea030653
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2022
ms.locfileid: "8451578"
---
# <a name="subscription-billing-overview"></a>訂閱計費概覽

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

訂閱計費使組織能夠透過計費計劃管理訂閱收入機會和定期計費。 複雜的定價和計費模型以及收入分配很容易管理，並在行級別進行計費和確認。 多元收入分配使收入分配符合國際會計準則 (國際財務報告準則 15\[IFRS 15\]) 和公認會計原則 (US GAAP) 標準 (會計標準彙編主題 606\[ ASC 606\])。

該解決方案具有三個可以獨立使用的模組。 或者，所有三個模組都可以一起使用。

- **定期合約計費**–該模組支持定期計費和價格管理，以提供對定價和計費參數、合約續約和合併發票的控制。
- **收入和費用延遲**–該模組透過管理收入和即時洞察每月定期收入，消除手動程序和對外部系統的依賴。
- **多元收入分配**–該模組透過處理多個項目的定價和收入分配來幫助實現收入合規性。

訂閱計費透過 **功能管理** 啟用。 但是，它不能與 **收入確認** 功能一起使用。 因此，您必須先停用該功能，然後才能啟用訂閱計費。

1. 在 **功能管理** 工作區內，在 **全部** 索引標籤上，在篩選器內輸入 **收入確認**，然後選擇功能名稱作為篩選器。
2. 選擇 **收入確認** 功能，然後選擇 **停用**。
3. 在 **功能名稱** 篩選器內輸入 **訂閱計費**，然後選擇模組篩選。
4. 選擇 **訂閱計費** 功能，然後選擇 **啟用**。
5. 從上一個列表的三個模組中選擇其中一個，然後選擇 **啟用**。 對其他兩個模組中的每一個重複此步驟。

    > [!IMPORTANT]
    > 必須先啟用 **訂閱計費** 功能，然後才能啟用這三個模組中的任何一個。
