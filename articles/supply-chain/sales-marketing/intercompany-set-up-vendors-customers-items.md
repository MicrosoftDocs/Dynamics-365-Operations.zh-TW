---
title: 設定公司間交易的廠商、客戶和項目
description: 本主題說明如何設定公司間交易的廠商、客戶和項目
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
ms.openlocfilehash: 062b8fe956fef0f8172d26aac3df54b93e1941ef
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447723"
---
# <a name="set-up-vendors-customers-and-items-for-intercompany-trade"></a>設定公司間交易的廠商、客戶和項目

[!include [banner](../../includes/banner.md)]

若要準備組織的公司間交易，您必須定義進行內部交易的廠商和客戶。 然後，您必須將廠商與客戶，與您將要購買或銷售的項目之間建立關聯。

1. 前往 **採購和委外 \> 廠商 \> 所有廠商**。
1. 選擇要定義為公司間廠商的廠商。
1. 在動作窗格上，於 **一般** 索引標籤，選擇 **公司間**。
1. 為廠商帳戶，指定公司間設定參數。 這些參數包括客戶法律實體和帳戶、銷售訂單原則、訂購單原則、值對應，和購買合約與銷售合約原則。 您還可以指定，是否使用廠商帳戶的基本資料，或是其他法律實體中客戶帳戶的基本資料。
1. 請前往 **產品資訊管理 \> 產品 \> 已發佈的產品**。
1. 在 **已發佈產品** 清單頁面，選擇要指派給廠商的項目，以便這些項目可用於公司間交易。 針對每個項目，開啟 **已發佈產品詳細資訊** 頁面。 在 **購買** 索引標籤上，**廠商** 欄位，輸入廠商號碼。
1. 前往 **應收帳款 \> 客戶 \> 所有客戶**。
1. 選擇要定義為公司間客戶的客戶。
1. 在動作窗格上，於 **一般** 索引標籤，選擇 **公司間**。
1. 為客戶帳戶，指定公司間設定參數。 這些參數包括廠商法律實體和帳戶、訂購單原則、銷售訂單原則、值對應，和銷售合約與購買合約原則。 您還可以指定，是否使用客戶帳戶的基本資料，或是其他法律實體中廠商帳戶的基本資料。
1. 在 **客戶** 頁面上，**發票和交貨** FastTab 上，選擇 **建立公司間訂單** 核取方塊。 如果您希望將訂單直接交貨給客戶，請選擇 **直接交貨** 核取方塊。

    > [!NOTE]
    > 如果組織有部分項目的庫存，並且希望交貨給客戶，您可能不希望自動建立公司間訂單，以便使用現有庫存項目。 有時為了使用現有庫存，要為項目停用自動產生訂單，請清除 **建立公司間訂單** 核取方塊。

1. 如果您要建立與銷售訂單非直接相關的額外行，請選擇 **建立非直接相關訂單行** 核取方塊。 然後，使用者可以從公司間銷售訂單，新增額外行至原始銷售訂單。

> [!WARNING]
> 如果您允許建立非直接相關訂單行，則允許從公司間銷售訂單，向原始銷售訂單新增額外內容。 每個額外內容，都會處理給客戶，並新增至訂單和發票中。 此外，涉及銷售的每份文件，都會自動列印和發佈。 使用者不會收到額外內容的提醒。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]