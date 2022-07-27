---
title: 資產和資產類型的擔保
description: 本主題介紹如何在資產管理中設定資產和資產類型的擔保。
author: johanhoffmann
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bcfbd56f5fa1491f13ea65c5fb3d70659c3b945276813d7c1c922c849bf8e3a3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446994"
---
# <a name="warranties-on-assets-and-asset-types"></a>資產和資產類型的擔保

[!include [banner](../../includes/banner.md)]

 


本主題介紹如何在資產管理中設定資產和資產類型的擔保。

## <a name="set-up-a-warranty-on-an-asset-type"></a>為資產類型設定擔保

1. 選擇 **資產管理** \> **設定** \> **資產類型** \> **資產類型**。
2. 在左側窗格中，選擇要附加廠商擔保合約的資產類型，然後選擇 **資產類型預設值**。
3. 在 **一般** FastTab 的 **廠商擔保** 欄位，選擇合約。

## <a name="set-up-a-warranty-on-an-asset"></a>為資產設定擔保

1. 選取 **資產管理** \> **一般** \> **資產** \> **全部資產**。
2. 選擇資產，然後選擇 **編輯**。
3. 在 **廠商** FastTab **廠商擔保** 區段的 **擔保** 欄位，選擇擔保合約。
4. 在 **擔保開始日期** 和 **擔保結束日期** 欄位，選擇開始和結束日期。

    > [!IMPORTANT]
    > 如果在工單上的 **擔保開始日期** 欄位選擇日期，則該工單的擔保將從該日期開始生效。 建立工單時，**擔保開始** 欄位將自動設定為建立日期。 但是，您可以變更該日期，使其與擔保合約的開始日期等相對應。
    >
    > ![工單頁面。](media/02-warranty.png)

> [!NOTE]
> 為廠商擔保涵蓋的資產建立工單時，如果工單的預期開始日期在擔保期內，您會收到有關擔保合約的通知。 然後，您可以根據需要取消工單。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]