---
title: 固定資產交易過帳到過帳層
description: 本文章概述固定資產交易的過帳層功能。
author: moaamer
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 538366163bac8ba593bd5575459ddb9b0079094150187dfb8c04490f467f9798
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450588"
---
# <a name="post-fixed-asset-transactions-to-posting-layers"></a>固定資產交易過帳到過帳層

[!include [banner](../includes/banner.md)]

本文章概述固定資產交易的過帳層功能。

固定資產往往基於不同目的以不同方式折舊。 適用稅務用途的折舊是採用現行稅賦規則計算，達到盡可能最高的稅前折舊，但適用報表用途的折舊則根據會計法律和標準計算。 各種折舊在過帳層分開計算和記錄。

附在固定資產的每本帳冊都針對有整體折舊目標的特殊過帳層設定。 目前共有十個過帳層：Current、Operations、Tax 和七個自訂層。 您也可以藉由將過帳到總帳欄位設定為否的方式，停用過帳帳冊到總帳的動作。 過帳層欄位隨後自動設定為無。 不過帳到總帳的帳冊通常用於報稅用途。 這個方法讓您有額外的彈性刪除資產帳冊的歷史交易，因為它們尚未承諾給總帳。

固定資產日記帳是借助總帳 > 日記帳設定 > 日記帳名稱的日記帳名稱頁面定義。 您可以過帳折舊的每份日記帳是由僅用於一個過帳層的日記帳名稱定義。 日記帳的過帳層不能更改。 此項限制有助於保證每個過帳層的交易保持分開。 至少須為每個過帳層建立一個日記帳名稱。 如果您正在使用不過帳到總帳的帳冊，您也必須建立過帳層設定為 None 的日記帳。

您可以在固定資產過帳設定檔頁面上指定固定資產交易的總帳科目。 以每個過帳設定檔而言，您必須選取相關的交易類型和帳冊，然後指定分類帳科目。 針對將過帳到總帳的每本帳冊設定過帳設定檔記錄。

固定資產可在只支援 **目前** 過帳層的文件輸入，例如 **訂購單**、**待處理廠商發票**、**銷售訂單** 或 **普通發票**。 在任何這些文件選取固定資產識別碼時，資產帳冊會篩選出有 **Current** 過帳層的帳冊，並且當系統驗證固定資產過帳層為 **Current** 時，將自動填寫。 如果無法完成驗證，過帳流程將停止。 

> [!NOTE] 
> 藉由使用衍生帳冊，您可以同時過帳交易到不同的過帳層。 主帳冊的交易是在日記帳或來源文件建立，其中過帳層對應到帳冊的過帳層。 過帳期間，衍生帳冊交易將過帳到適當的過帳層。 


更多資訊，請參閱[衍生帳冊](derived-books.md)和[使用衍生帳冊過帳](post-derived-value-models.md)。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]