---
title: 設定公司間訂單的費用
description: 本主題說明如何設定公司間訂單費用
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 3786df5ce185fa8433d7c69bed5bef09b4983b8b
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447756"
---
# <a name="set-up-charges-on-intercompany-orders"></a>設定公司間訂單的費用

[!include [banner](../../includes/banner.md)]

您可以設定要新增至公司間訂單的費用。 當費用新增至公司間銷售訂單時，會自動同步至公司間訂購單。 兩種方法皆可以 – 從公司間銷售訂單至訂購單，反之亦然。

您也可以通過定義公司間費用百分比，以增加公司間銷售訂單的利潤。

當您設定要應用於公司間訂單的費用時，您可以從原始銷售訂單的淨額，計算公司間銷售訂單的內部利潤。 如果公司間廠商是以成本價向您銷售時，可能會用到此功能。 下列流程說明，如何為公司間客戶進行此操作。 您可以將同樣的流程用於廠商。

1. 前往 **應收帳款 \> 設定 \> 費用 \> 客戶費用群組**。
1. 建立費用群組。
1. 前往 **應收帳款 \> 客戶 \> 所有客戶**。 選擇客戶帳戶連結。 在動作窗格上，選擇 **客戶** 索引標籤，然後選擇 **銷售訂單** FastTab。
1. 在動作窗格上，選擇 **編輯** 以編輯欄位。 在 **收費群組** 欄位中，選擇您在步驟 2 所設定的公司間費用群組。
1. 前往 **應收帳款 \> 設定 \> 費用 \> 自動收費**。
1. 填寫相關欄位，設定費用。
1. 在 **客戶關係** 欄位中，選擇您在步驟 2 所設定的公司間費用群組。
1. 在 **行** FastTab 上，在 **類別** 欄位，選擇 **公司間百分比**。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
