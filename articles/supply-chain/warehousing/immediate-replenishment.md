---
title: 即時補貨
description: 本主題介紹如何在位置指令未能分配庫存時使用即時補貨來補充庫存。
author: Mirzaab
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSReplenishmentTemplates
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 15a3cc4c50e49a50c354834761425cd107c23a9d79677e022cb1d339bb48c918
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446895"
---
# <a name="immediate-replenishment"></a>即時補貨

[!include [banner](../includes/banner.md)]

即時補貨可在位置指令行未能分配庫存時用於補充庫存。 補貨是以位置指令設定中的單行為依據。 如果手頭上沒有該行指定測量單位的庫存，就會即時補貨該測量單位。

即時補貨提供了一種替代方法，其中會依據位置指令的多行分配庫存，並且在分配結束時對需求加總，以位置指令的最後一行指定的測量單位進行補貨。

使用即時補貨的好處是補貨可以受到特定單位的限制，並且可以將數量引導到特定位置。

## <a name="business-scenario"></a>商務案例

例如您有一個倉庫，其中有單獨的「箱」和「個」測量單位的揀貨區。 您希望盡可能揀選更多箱子，然後從「個」區域揀選少於一個箱子的任何剩餘數量，以最佳化揀貨流程。

在這種情況下，您可以使用即時補貨。 在位置指令中，您可以為箱子設定即時補貨，以便在為需求數量挑選箱子數量短缺時立即使用需求補貨。 透過這種方式，您可以最佳化揀貨流程，以便在揀貨時包括最多箱數。 即時補貨將產生對箱子的補貨，並且不會傳遞需求，因此會以「個」測量單位來揀選數量。 換句話說，只有應該在「個」測量單位中選取的數量 (即小於一箱的數量) 才會從「個」區域中揀選。 如果「箱」區域出現短缺，您可以從總需求中揀選盡可能多的箱子。 然後將從「個」區域中揀選剩餘的數量。

## <a name="where-it-applies"></a>適用處

如果為其設定補貨範本的位置指令行分配失敗，則在波次執行期間使用即時補貨。

## <a name="set-up-immediate-replenishment"></a>設定即時補貨

- 前往 **倉庫管理** \> **設定** \> **位置指令**，然後在 **行** 索引標籤的 **即時補貨範本** 清單中，為波次需求選擇一個補貨範本。

如果位置指令行未能分配專用測量單位，則應用補貨範本。

## <a name="troubleshooting"></a>疑難排解

如果為某個位置指令行選擇了即時補貨，但在為該位置指令行使用需求補貨範本時沒有產生補貨工作，則必須調查兩個主要原因：

- 確保套用的需求補貨範本設定為使用正確的 **補貨** 類型位置範本及工作範本。
- 確保需求補貨範本搜尋現有庫存進行補貨的位置有足夠的現有庫存。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]