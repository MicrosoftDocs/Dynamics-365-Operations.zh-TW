---
title: 設定公司間交易
description: 本主題說明如何設定公司間交易
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage, InterCompanyTradingRelationSetupCustomer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7288cc8f336b6b1f5174fe2bef38017e0c96e560
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2021
ms.locfileid: "8449418"
---
# <a name="set-up-intercompany-trade"></a>設定公司間交易

[!include [banner](../../includes/banner.md)]

若要啟用 Microsoft Dynamics 365 Supply Chain Management 執行公司間交易，您必須設定客戶和廠商，以執行公司間交易。 您還需要設定應付帳款、應收帳款、採購和委外，及銷售和行銷。

## <a name="before-you-set-up-intercompany-trade"></a>設定公司間交易之前

設定公司間交易之前，您必須確定那些客戶是公司間客戶，那些廠商是公司間廠商。 對於 Microsoft Dynamics 365 Supply Chain Management 中的法律實體，您必須決定哪種交易原則，要應用至特定公司間客戶或廠商的公司間交易關係。

尤其是，我們建議您以及組織，熟悉公司間參數。

- 與公司間交易的每個法律實體負責的經理，討論設定所造成的影響。
- 為每個法律實體設定適當的值。

## <a name="set-up-trading-relations"></a>設定貿易關係

若要為客戶和廠商設定公司間交易，請執行以下步驟。

1. 前往 **應收帳款 \> 客戶 \> 所有客戶**。
1. 選擇客戶帳戶。
1. 在動作窗格上，於 **一般** 索引標籤，選擇 **公司間**。
1. 為客戶帳戶，指定公司間設定參數。 這些參數包括法律實體，其包含對應的廠商和廠商帳戶。 參數還包括訂購單原則、銷售訂單原則、值對應和銷售合約與購買合約的原則。 您還可以指定，是否使用客戶帳戶的基本資料，或是其他法律實體中廠商帳戶的基本資料。
1. 對法律實體中剩餘的公司間客戶，重複步驟 1 到步驟 4。
1. 移至 **應付帳款 \> 廠商 \> 所有廠商**。
1. 選擇一個廠商帳戶。
1. 在動作窗格上，於 **一般** 索引標籤，選擇 **公司間**。
1. 為廠商帳戶，指定公司間設定參數。 這些參數包括法律實體，其包含對應的客戶和客戶帳戶。 參數還包括銷售訂單原則、訂購單原則、值對應和購買合約與銷售合約的原則。 您還可以指定，是否使用廠商帳戶的基本資料，或是其他法律實體中客戶帳戶的基本資料。
1. 對法律實體中剩餘的公司間廠商，重複步驟 6 到步驟 9。

## <a name="set-up-products"></a>設定產品

若要為客戶和廠商設定公司間交易，請執行以下步驟。

1. 前往 **產品資訊管理 \> 產品 \> 所有產品和基準產品**。
1. 定義要於公司間交易，發佈至法律實體的產品。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
