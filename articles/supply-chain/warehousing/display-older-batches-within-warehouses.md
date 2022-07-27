---
title: 在行動裝置設定顯示倉庫內的舊批次
description: 本主題介紹如何設定行動裝置顯示批次早於工作線目前位置的位置清單。
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d23a259f4c16026ee36f73b427f7d2e610a4b8d938c2e21ec9715d8d2b8137b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446751"
---
# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a>在行動裝置設定顯示倉庫內的舊批次

[!include [banner](../includes/banner.md)]

**顯示倉庫內的舊批次** 設定允許您顯示批次早於工作線目前位置的位置清單。 顯示的位置清單包括有關位置中較舊批次的資訊，包括到期日和每個批次的實際庫存。 您可以選擇從新位置取貨或繼續從目前位置取貨。 
- 從新位置取貨 - 如果您選擇從新位置取貨，目前工作線將更新為使用新位置，並且工作將繼續照常使用新位置。 要使新位置有效，其中必須有足夠的可用數量用於整個工作線。 如果沒有所需數量，則不會更新工作行，並顯示清單。 
- 從目前位置繼續取貨 - 如果您繼續使用目前工作線位置，工作線的數量將繼續從原始位置進行取貨。

## <a name="where-it-applies"></a>適用處
倉庫內的舊批次是在行動裝置功能表項目設定的，會影響項目之下的批次選擇。

## <a name="set-up-display-older-batches-within-warehouse"></a>設定顯示倉庫內的舊批次
**顯示倉庫內的舊批次** 設定可於 **選擇最舊的批次** 選項設定為 **警告** 時於行動裝置功能表項目使用。

- 在 **Warehouse Management** > **設定** > **行動裝置** > **行動裝置功能表項目** 之下，將功能表項目的 **使用現有工作** 設定為 **是**，然後在 **挑選最舊批次** 欄位選擇 **警告**。 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]