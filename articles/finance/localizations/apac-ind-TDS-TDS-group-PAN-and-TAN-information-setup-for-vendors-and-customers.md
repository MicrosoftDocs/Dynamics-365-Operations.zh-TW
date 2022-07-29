---
title: 為廠商和客戶設定的 TDS 群組、PAN 和 TAN 資訊
description: 本主題說明如何為廠商和客戶設定有關從源頭扣除稅款 (TDS) 群組、永久帳號 (PAN) 和稅務帳號 (TAN) 的資訊。
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 808fa7b72651ab274415e48f5e0a356784ca6525
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451779"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a>為廠商和客戶設定 TDS 群組、PAN 和 TAN 資訊

[!include [banner](../includes/banner.md)]

本主題說明如何為廠商和客戶設定有關從源頭扣除稅款 (TDS) 群組、永久帳號 (PAN) 和稅務帳號 (TAN) 的資訊。

1. 前往 **應付帳款 \> 廠商 \> 所有廠商** 或 **應收帳款 \> 客戶 \> 所有客戶**。

    [![所有廠商頁面。](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)

2. 在動作窗格上，選擇 **新增** 以建立廠商或客戶，並輸入所需的詳細資料。 或者，選擇現有的廠商或客戶。
3. 在 **發票和交貨** FastTab 的 **扣繳稅款** 區段中，將 **計算扣繳稅款** 選項設定為 **是**，以計算廠商或客戶的扣繳稅款、TDS 或從源頭扣除稅款 (TCS)。
4. 採購發票的 TDS 是根據為廠商或客戶定義的預設 TDS 組計算的。 在 **TDS 群組** 欄位中，選擇預設 TDS 群組。

    > [!NOTE]
    > 當在 **TDS 群組** 欄位中選擇 TDS 群組時，**扣繳稅款群組** 欄位和 **TDS 群組** 欄位會變得無法使用。

5. 在 **稅務資訊** FastTab 上，在 **PAN 資訊** 區段的 **狀態** 欄位中，選擇廠商或客戶的永久帳號的狀態：

    - **無法使用** – 廠商或客戶沒有 PAN。
    - **已收到** – 廠商或客戶具有 PAN。
    - **已套用** – 廠商或客戶已套用 PAN。
    - **無效** – 廠商或客戶具有 PAN，但無效。

6. 如果在 **狀態** 欄位中選擇 **已收到** 來表示廠商或客戶具有 PAN，則在 **編號** 欄位中輸入 PAN。 PAN 必須包含五個字母字元、四個數字字元和一個字母字元。 範例如下：**ABCDE1260A**。
7. 如果在 **狀態** 欄位中選擇 **已套用** 來表示廠商或客戶已套用 PAN，則在 **參考編號** 欄位中輸入參考編號。
8. 在 **評估對象的性質** 欄位中，選擇廠商或客戶所屬的評估對象類別的性質：

    - 公司
    - HUF
    - 事務所
    - 個人
    - AOP
    - BOI
    - 當地政府
    - 其他

    [![稅務資訊 FastTab。](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)

9. 在動作窗格上的 **廠商** 索引標籤上，在 **登記** 群組中，選擇 **登記識別碼** 以開啟 **管理地址** 頁面。
10. 在 **管理地址** 頁面的 **稅務資訊** FastTab，選擇 **新增** 或 **編輯** 以打開 **管理稅務資訊** 頁面，您可以在其中維護稅務登記項目。
11. 在 **管理稅務資訊** 頁面的 **扣繳稅款** FastTab 上，在 **稅務帳號 (TAN)** 欄位中輸入 TAN。 TAN 必須包含四個字母字元、五個數字字元和一個字母字元。 範例如下：**AFGH54821T**。
12. 關閉頁面。
