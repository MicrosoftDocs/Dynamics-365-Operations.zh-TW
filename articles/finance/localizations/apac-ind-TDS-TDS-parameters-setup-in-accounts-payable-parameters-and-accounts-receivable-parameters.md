---
title: 在應付帳款和應收帳款中設定 TDS 參數
description: 本主題說明如何在應付帳款和應收帳款中設定參數以支援從源頭扣除稅款 (TDS) 扣除。
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
ms.openlocfilehash: 6d5258d3f2f9dd32f73ba7dec9c57ab896461f7e
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451839"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a>在應付帳款和應收帳款中設定 TDS 參數

[!include [banner](../includes/banner.md)]

本主題說明如何在應付帳款和應收帳款中設定參數以支援從源頭扣除稅款 (TDS) 扣除。

1. 前往 **稅務 \> 設定 \> 參數 \> 應收帳款參數**。
2. 在 **更新** 索引標籤，選擇 **更新訂單行** 以打開 **更新訂單行** 對話方塊。
3. 在 **TDS 群組** 區段，在 **更新 TDS 群組** 欄位，指定用於在行等級更新 TDS 群組的方法。 在訂單標題上更新 TDS 群組時使用此設定。 可以使用以下選項：

    - **永不** – 在訂單標題上更新 TDS 群組時，不會在訂單行上更新它。
    - **一律** – 在訂單標題上更新 TDS 群組時，將在訂單行上自動更新它。
    - **提示** – 使用者會收到訊息，提示他們在訂單行上更新 TDS 群組。
4. 選取 **確定**。

    [![更新訂單行對話方塊。](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)

5. 前往 **稅務 \> 設定 \> 參數 \> 應付帳款參數**。
6. 在 **一般** 索引標籤的 **根據交貨資訊拆分** FastTab，將 **產品收據** 選項設定為 **是**，以過帳和拆分具有不同交貨地址和稅務帳號 (TAN) 的產品收據。 如果此選項設定為 **否**，則不能過帳具有不同交貨地址和 TAN 的採購裝箱單。
7. 將 **發票** 選項設定 **是** 以過帳和拆分具有不同交貨地址和 TAN 的採購發票。

    [![根據交付資訊拆分 FastTab。](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)

8. 關閉頁面。
