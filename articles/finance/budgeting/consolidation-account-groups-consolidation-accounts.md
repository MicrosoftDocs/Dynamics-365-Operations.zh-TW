---
title: 合併科目群組和其他合併科目
description: 本主題提供有關合併科目群組和其他合併科目的資訊，並說明如何使用它們。
author: panolte
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: roschlom
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 489f5417b6044e02d4711a03a17d6c19031cc2ee
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451218"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>合併科目群組和其他合併科目

[!include [banner](../includes/banner.md)]

本主題提供有關合併科目群組和其他合併科目的資訊，並說明如何使用它們。

## <a name="consolidation-account-groups"></a>合併科目群組

合併科目群組可讓您建立要用於合併資料的帳戶群組。 通常，合併科目群組代表政府規定的會計科目表。 合併科目群組還可以將科目對應到由公司總部定義的群組。 您可以在 **合併** 模組的 **設定** 區域中找到合併科目群組。 新增新群組時，請輸入帳戶群組的唯一識別碼以及名稱。

## <a name="additional-consolidation-accounts"></a>其他合併科目
其他合併科目可讓您將現有會計科目表中的科目分配到合併科目群組。 然後，您可以指定合併科目值和名稱。 

您可以在 **合併** 模組的 **設定** 區域中找到其他合併科目。 建立新的合併科目時，您必須指定以下資訊：

-   **主科目** – 此欄位是一個查詢，其顯示您在頁面上選擇的會計科目表的所有主要科目。 當您選擇一個帳戶時，名稱會自動輸入到 **主科目名稱** 欄位。
-   **合併科目群組** – 使用此欄位指定要將帳戶分配到的群組。 如果您以兩種不同的方式進行合併，則必須將同一科目新增到所有四個合併科目群組中。
-   **合併科目** – 輸入合併科目的值。 此值可以不是會計科目表中的科目。 它可以是您需要的任何值。
-   **合併科目名稱** – 輸入您希望在查詢和報告中顯示的科目名稱。
-   **SAT 等級** – 該欄位用於向墨西哥稅務機關報告帳戶對帳單。 

當您完成建立合併科目群組和其他合併科目後，您可以在線上合併流程中選擇該群組。


有關詳細資料，請參閱[建立合併組和其他合併科目](../general-ledger/tasks/create-consolidation-groups.md)。 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
