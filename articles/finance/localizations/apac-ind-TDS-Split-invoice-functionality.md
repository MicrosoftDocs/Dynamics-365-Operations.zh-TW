---
title: 拆分發票功能
description: 本主題介紹按交貨地址和稅務帳號 (TAN) 拆分發票的設定和功能。
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
ms.openlocfilehash: f9bb4db14cbb7c9abb33ccee532ed73b378317bb
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451845"
---
# <a name="split-invoice-functionality"></a>拆分發票功能

[!include [banner](../includes/banner.md)]

本主題介紹按交貨地址和稅務帳號 (TAN) 拆分發票的設定和功能。

在 **應付帳款參數** 頁面的 **一般** 索引標籤上，選擇 **產品收據** 或 **發票** 核取方塊以過帳和拆分在 **採購訂單** 頁面上具有不同交貨地址和 TAN 的產品收據或發票。 然後，已過帳的發票將按交貨地址和 TAN 進行拆分。

在 **摘要更新** 索引標籤上，在 **拆分依據** 快速索引標籤的 **交貨資訊** 行中，將 **確認**、**揀料單**、**裝箱單** 或 **發票** 選項設定為 **是**，以過帳和拆分在 **銷售訂單** 頁面上為不同發票行定義了不同的交貨地址和 TAN 的確認、領料單、裝箱單或發票。 依次按交貨地址和 TAN 拆分發票。

> [!IMPORTANT]
> - 如果 **交貨資訊** 的選項均設定為 **是**，該發票作為單個發票過帳。 不會進行發票拆分。
> - 若要拆分和過帳發票行具有不同交貨地址和 TAN 的裝箱單，必須將 **交貨資訊** 的 **裝箱單** 選項設定為 **是**。
> - 若要拆分和過帳發票行具有不同交貨地址和 TAN 的發票，必須將 **交貨資訊** 的 **發票** 選項設定為 **是**。
> - 若要過帳發票行具有不同交貨地址，但具有相同 TAN 的發票，必須將 **交貨資訊** 的 **發票** 選項設定為 **否**。 按交貨地址拆分發票。

## <a name="example"></a>範例

在此範例中，在 **應付帳款參數** 頁面的 **摘要更新** 索引標籤上，將 **交貨資訊** 的 **發票** 選項設定為 **是**。 已過帳採購發票，其中行中的交貨地址和 TAN 設定如下：

- **品項行 1：** 交貨地址 1，TAN-ABCD12345A
- **品項行 2：** 交貨地址 1，TAN-ABCD12345A
- **品項行 3：** 交貨地址 2，TAN-ABCE12345B
- **品項行 4：** 交貨地址 3，TAN-ABCD12345A

在這種情況下，原始發票將拆分為兩張發票並按以下方式過帳：

- 針對品項行 1 和品項行 2 過帳發票 1，因為這兩個行具有相同的交貨地址和 TAN。
- 針對品項行 3 過帳發票 2。
- 針對品項行 4 過帳發票 3。
