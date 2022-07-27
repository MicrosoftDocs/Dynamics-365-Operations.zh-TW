---
title: 評等設定檔
description: 本主題介紹如何為評等設定檔設定資料。
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: af9051c6bbaed311f1f841a82dfd145633acab2c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448755"
---
# <a name="rating-profiles"></a>評等設定檔

[!include [banner](../../includes/banner.md)]

評等設定檔類似於物流合約 (但不是法律合約)。 它用於確定負載的運輸關稅。 

每個評等設定檔對於運輸承運人都是唯一的。 在設定檔中，將運輸承運人與主費率相關聯。 主費率定義基礎費指派和基礎費率。 基礎費率決定了承運人的費率。

您可以使用顯示所有現有評等設定檔概觀的一般頁面來設定評等設定檔。 或者，您可以直接從裝運承運商處設定評等設定檔。 在這兩種情況下，您為評等設定檔設定的資訊是相同的。

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a>在評等設定檔頁面上建立或編輯評等設定檔

在 **評等設定檔** 頁面，您可以查看所有可用的評等設定檔。 您還可以編輯現有設定檔並建立新設定檔。

1. 移至 **運輸管理** \> 設定 \> 評等 \> 評等設定檔。
1. 在動作窗格上，選擇 **新增** 將新的評等設定檔新增到格線中，或選擇 **編輯** 以編輯現有設定檔。
1. 在新的或現有評等設定檔的資料列中，設定以下欄位：

    - **評等設定檔** – 輸入評等設定檔的唯一識別碼 (ID)。
    - **名稱** – 輸入評等設定檔的描述性名稱。
    - **裝運承運人** – 選取裝運承運人。 您設定的評等設定檔也將顯示在所選承運人的 **裝運承運人** 頁面上。
    - **站點** 和 **倉庫** – 選取站點和倉庫。
    - **費率引擎** – 選擇評等設定檔的費率引擎。
    - **主費率** – 選擇評等設定檔的主費率。 您可以使用主費率來定義基礎費率類型和基礎費率。 如需詳細資訊，請參閱[設定主費率](set-up-rate-masters.md)。
    - **運輸時間引擎** – 為評等設定檔選擇傳輸時間引擎。
    - **承運人燃料指數** – 為評等設定檔選擇承運人燃料指數。
    - **生效開始日期和時間** 和 **生效結束日期和時間** – 定義評等設定檔應該處於有效狀態的時間期間。

1. 在動作窗格上，選擇 **儲存**。

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a>直接在裝運承運人頁面建立評等資料

1. 移至 **運輸管理 \> 設定 \> 承運人 \> 裝運承運人**。
1. 在清單中選取裝運承運人。
1. 在 **評等設定檔** FastTab，選擇 **新增** 以建立評等設定檔。
1. 設定新評等設定檔的欄位。 這些欄位對應至 **評等設定檔** 頁面的欄位，如本主題先前小節所述。

> [!NOTE]
> 在 **裝運承運人** 頁面建立的設定檔也顯示在 **評等設定檔** 頁面。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]