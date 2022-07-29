---
title: 發票上的 TDS 計算
description: 本主題為在發票等級計算從源頭扣除稅款 (TDS) 的交易提供參考。
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 5a4c3e13eba76db2fae1f66560a2fea68d9a3c5f
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451809"
---
# <a name="tds-calculation-on-invoices"></a>發票上的 TDS 計算

[!include [banner](../includes/banner.md)]

本主題為在發票等級計算從源頭扣除稅款 (TDS) 的交易提供參考。

| 序號 | 交易類型                                 | 交易金額 | 頁面名稱和選擇路徑                                 | 帳戶類型和沖銷帳戶類型                         |
| ------------- | ------------------------------------------------ | ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1.            | 從廠商處購買/記錄費用   | 借方或貸方  | 普通日記帳頁面 (總帳 > 日記帳分錄 > 普通日記帳)、發票審核日記帳頁面 (應付帳款 > 發票 > 發票審核)、發票日記帳頁面 (應付帳款 > 發票 > 發票日記帳) | 分類帳 (Dr.) 廠商 (Cr.)。  僅當分類帳科目具有過帳類型 **採購** - **現金** 時，才會為廠商-分類帳組合計算扣繳稅款。 |
| 2.            | 從客戶處購買/記錄費用 | 借方或貸方  | 普通日記帳頁面 (總帳 > 日記帳分錄 > 普通日記帳)、發票日記帳頁面 (應付帳款 > 發票 > 發票日記帳) | 分類帳 (Dr.) 客戶 (Cr.)                                 |
| 3.            | 從廠商處購買固定資產              | 借方或貸方  | 普通日記帳頁面 (總帳 > 日記帳分錄 > 普通日記帳)、發票登記簿日記帳頁面 (應付帳款 > 發票 > 發票登記簿)、發票日記帳頁面 (應付帳款 > 發票 > 發票日記帳) | 固定資產 (Dr.) 廠商 (Cr.)                             |
| 4.            | 從客戶處購買固定資產            | 借方或貸方  | 普通日記帳頁面 (總帳 > 日記帳分錄 > 普通日記帳)、發票日記帳頁面 (應付帳款 > 發票 > 發票日記帳) | 固定資產 (Dr.) 客戶 (Cr.)                           |
| 5.            | 採購發票 (應付 TDS)                  |                    | 訂購單頁面 (應付帳款>訂購單 >所有訂購單) |                                                              |
| 6.            | 銷售發票 (應收 TDS)                  |                    | 銷售訂單頁面 (應收帳款 > 訂單 > 所有銷售訂單)，普通發票頁面 (應收帳款 > 發票 > 所有普通發票) |                                                              |
