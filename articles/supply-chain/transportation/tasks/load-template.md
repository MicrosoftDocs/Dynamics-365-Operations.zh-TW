---
title: 裝載範本
description: 本主題介紹如何設定裝載範本，以及如何將裝載範本與新裝載關聯。
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 694860d1ade74f9fd51a8ac579aa69fe7fb673a8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448254"
---
# <a name="load-templates"></a>裝載範本

[!include [banner](../../includes/banner.md)]

在您建立新裝載時，您可以指派裝載範本。 裝載範本包含有關設備，以及裝載的高度、寬度、深度和體積等測量資訊。

本主題介紹如何設定裝載範本，以及如何將裝載範本與新裝載關聯。

## <a name="set-up-a-load-template"></a>設定裝載範本

1. 前往 **運輸管理 \> 設定 \> 裝載建構 \> 裝載範本**。
1. 在動作窗格上，選擇 **新增** 以新增新範本或 **編輯** 以編輯現有範本。
1. 在新範本或現有範本的明細中，設定以下欄位：

    - **裝載範本識別碼** – 輸入裝載範本的唯一識別碼 (ID)。
    - **設備** – 選擇應用於裝運裝載的設備。
    - **裝載高度**、**裝載寬度**，和 **裝載深度** – 輸入裝載的維度。
    - **最大允許裝載體積** 和 **最大允許裝載重量** – 輸入裝載的最大允許體積和重量。
    - **最大允許總重** – 輸入裝載的最大允許總重量。 貨物的總重包括皮重和裝載重量。
    - **允許的最大貨運件數** – 輸入裝載可以包含的最大貨運件數。
    - **地板堆疊裝載** – 選擇此核取方塊以使用地板裝載。 在地板裝載案例中，箱子會在貨櫃內從底板到頂板、壁到壁進行堆疊，以最大化裝載容量。

1. 在動作窗格上，選擇 **儲存**。

## <a name="associate-a-load-template-with-a-new-load"></a>將裝載範本與新裝載相關聯

1. 前往 **運輸管理 \> 規劃 \> 裝載規劃工作台**。
1. 在頁面的上半部分，根據您要為建立裝載的來源文件類型，選擇以下索引標籤之一：**運送**、**銷售明細**、**轉移明細**，或是 **訂購單明細**。 
1. 選擇要規劃裝載的特定文件。
1. 在動作窗格上，在 **供應和需求** 索引標籤的 **新增** 群組中，選擇 **至新負載**。
1. 在 **裝載範本** 對話方塊的 **裝載範本識別碼** 欄位中，選取要套用的範本。
1. 選擇 **確定** 以套用範本。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]