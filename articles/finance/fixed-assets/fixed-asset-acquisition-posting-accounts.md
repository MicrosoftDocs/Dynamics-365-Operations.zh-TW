---
title: 固定資產購置過帳科目
description: 本文章說明如何設定總帳過帳，方便獲得資產。
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7718ab6ad40dd135a79d2d07def19465aef68b33
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451089"
---
# <a name="fixed-asset-acquisition-posting-accounts"></a>固定資產購置過帳科目

[!include [banner](../includes/banner.md)]

本文章說明如何設定總帳過帳，方便獲得資產。

用於過帳固定資產購置的科目可能因購置資產的方法而異。 在固定資產過帳配置文件頁面的分類帳科目選項卡上，選擇採購和採購調整以設置固定資產科目以過帳到分類帳。 

在日記帳和採購訂單中，分類帳帳戶通常是資產負債表帳戶，借記新固定資產的購置價值。 此科目不顯示在日記帳中，也不能在事務處理中替換。 

抵銷賬戶也是資產負債表賬戶。 在普通日記帳和固定資產日記帳中，此帳戶通常是用於支付資產購置費用的銀行帳戶。 抵銷科目是日記帳中建議的預設科目。 如果固定資產是從供應商處購買的，則可以在日記帳中將其更改為會計科目表中的任何其他帳戶或供應商帳戶。 

當應付帳款中的發票日記帳或採購訂單用於固定資產購置時，固定資產交易記錄的抵銷帳戶將替換為為交易記錄選擇的供應商帳戶。

對於使用總帳中的庫存到固定資產日記帳過帳的購置，固定資產不是從外部來源購買的，而是從公司自己的庫存中轉移的。 因此，抵銷科目是庫存管理中庫存項目的庫存出庫科目。

有關詳細資訊，請參閱[透過採購取得資產](acquire-assets-procurement.md)。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
