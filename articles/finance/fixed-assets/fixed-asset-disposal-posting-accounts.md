---
title: 固定資產處置過帳
description: 本主題說明如何設定總帳過帳，方便處置資產。
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c82cb8b82f2cc8424675f76c68613a2b5aa76745
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451104"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>固定資產處置過帳

[!include [banner](../includes/banner.md)]

本主題說明在您正在處置資產時，如何設定總帳過帳。

若要設定在您處置資產時的總帳過帳，請選取 **固定資產過帳配置檔** 頁面上的 **總帳** FastTab 中的 **處置 - 出售** 和 **處置 - 廢料**。

針對這兩種交易類型 (慼藉出售或報廢處置資產)，固定資產的處置價值會計入總帳的貸方。 借方過帳到可能是銀行科目的沖銷科目 (請見範例)。 如果將固定資產出售給客戶，則使用客戶科目而不是沖銷科目。 有關詳細資訊，請參閱[將固定資產以廢料處置](dispose-of-a-fixed-asset-as-scrap.md)。

請按一下 **處置** 然後 **銷售** 或 **廢料**，然後設定明細帳以便反向計入固定資產的帳面淨值。 您也可以在 **處置參數** 頁面上的 **過帳價值** 和 **銷售價值類型** 欄位輸入資訊。 

低值池資產的交易處置只會減少處置金額的低值池帳面淨值。 然而，當資產銷售金額超過低值池的帳面淨值時，帳面淨值會減為零。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
