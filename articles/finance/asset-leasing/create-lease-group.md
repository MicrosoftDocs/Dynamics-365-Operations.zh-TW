---
title: 建立租賃群組
description: 本主題說明如何設定租賃群組。 租賃群組需要建立新的租賃。
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseGroupTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5ff4892408aa87214231762452c195274192447512525ae9c1f08dad8e318076
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450279"
---
# <a name="create-a-lease-group"></a>建立租賃群組

[!include [banner](../includes/banner.md)]

本主題說明如何設定租賃群組。 租賃群組需要建立新的租賃。 租賃帳簿與每個租賃群組相關聯。 租賃帳簿確定必須為每個租賃建立的預設帳簿。 您可以在 **租賃過帳參數** 頁面上將特定科目指派給租賃群組。

## <a name="create-a-lease-book-and-add-a-lease-group"></a>建立租賃帳簿並新增租賃群組

1. 前往 **資產租賃\>設定\>租賃群組**。
2. 在動作窗格上，選擇 **新增** 以新增租賃群組。 系統會新增一個行到格線中。
3. 在新行的 **租賃群組** 欄位，輸入一個值。
4. 在 **描述** 欄位中輸入一值。

您剛剛輸入的資訊將新增到 **新增租賃** 頁面的 **租賃群組** 欄位。

## <a name="associate-a-book-with-a-lease-group"></a>將帳簿與租賃群組關聯

建立租賃群組後，您可以將帳簿指派給每個群組。 當您建立租賃並將其指派給租賃群組時，系統會為與該租賃群組關聯的每本書建立一組計劃。

> [!NOTE]
> 必須先設定帳簿，然後才能將它們指派到租賃群組。

1. 前往 **資產租賃\>設定\>租賃群組**。
2. 選擇一個租賃群組，然後選擇 **帳簿**。
3. 選擇 **新增**，然後，在 **帳簿類型** 欄位中，選擇要指派給租賃群組的帳簿。 如果必須以不同方式對租賃進行會計處理，您可以將多個帳簿指派給一個租賃群組。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
