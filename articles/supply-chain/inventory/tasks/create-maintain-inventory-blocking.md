---
title: 創建和維護封鎖庫存
description: 本主題介紹如何使用封鎖庫存，來防止實際現有庫存遭到其他出庫文件保留。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bad7d4e5794dc543bd750912ef0d3e4460e611b1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448560"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>創建和維護封鎖庫存

[!include [banner](../../includes/banner.md)]

本主題介紹如何使用封鎖庫存，來防止實際現有庫存遭到其他出庫文件保留。 開始本主題的程序之前，您必須有一個可供實際現有庫存使用的項目。

## <a name="block-inventory"></a>封鎖庫存

若要創建封鎖庫存記錄以封鎖庫存，請遵循以下步驟。

1. 前往 **庫存管理 \> 定期任務 \> 封鎖庫存**。
1. 在動作窗格上，選擇 **新增**。
1. 在新的封鎖記錄標題上，設定您要封鎖項目的 **項目編號** 欄位，然後輸入說明。
1. 在 FastTab 的 **一般** 上，在 **數量** 欄位中，輸入要封鎖的項目數量。
1. 在 **庫存維度** FastTab 上，指定封鎖項目當前所在的地點和倉庫。
1. 在動作窗格上，選擇 **儲存**。

## <a name="update-the-conditions-of-the-inventory-blocking"></a>更新封鎖庫存條件

若要更新封鎖庫存記錄，請遵循以下步驟。

1. 前往 **庫存管理 \> 定期任務 \> 封鎖庫存**。
1. 在列表窗格中，選擇相關的封鎖記錄。
1. 根據需要編輯記錄。 例如，您可以更改 **預期日期** 欄位，以指示被封鎖的庫存何時可用於保留。 如果選擇 **預期收據** 選項，則預期交易中會出現日期。 (當您手工創建封鎖紀錄時，預設選擇此 **預期收據** 選項。)
1. 在動作窗格上，選擇 **儲存**。

## <a name="unblock-inventory"></a>解除封鎖庫存

若要移除封鎖庫存記錄，以解除封鎖庫存，請遵循以下步驟。

1. 前往 **庫存管理 \> 定期任務 \> 封鎖庫存**。
1. 在列表窗格中，選擇相關的封鎖記錄。
1. 在動作窗格上，選擇 **刪除**。
1. 系統會提示您確認作業。 選擇 **是** 繼續。
1. 關閉頁面。

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
