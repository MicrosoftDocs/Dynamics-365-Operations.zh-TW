---
title: 單獨設定數列
description: 本主題說明如何逐個設定數列。
author: SunilGarg
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceDetails
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b95a639c593c0f126a9aa1dd50434838d09ef746
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2021
ms.locfileid: "8460176"
---
# <a name="set-up-number-sequences-on-an-individual-basis"></a>單獨設定數列

[!include [banner](../../includes/banner.md)]

本主題說明如何逐個設定數列。 數列用於為需要識別碼的主資料記錄和交易記錄產生可讀的唯一識別碼。 需要識別碼的主資料或交易記錄稱為參考。 在為參考建立新記錄之前，您必須設定數列並將其與參考相關聯。 您可以使用 **設定數列** 精靈同時設定所有必需的數列，也可以使用 **數列** 頁面建立或修改單個數列。

1. 進入 **瀏覽窗格 > 模組 > 組織管理 > 數列 > 數列**。
2. 選取 **數列**。
3. 在 **數列代碼** 欄位中，輸入一個值。
4. 在 **名稱** 欄位中，輸入一個值。
5. 在 **範圍參數** FastTab 上，選取數列的範圍並從下拉式清單中選取範圍值。 範圍定義了哪些組織使用數列。 此外，具有非 **共用** 範圍的數列可以具有與其範圍相對應的區段。 例如，範圍為 **法律實體** 的數列可以有法律實體區段。 如需範圍的相關資訊，請參閱[數列概述](../number-sequence-overview.md)。 
6. 展開 **區段** 部分。
    - 透過新增、刪除和重新排列段來定義數列的格式。  
    - 所有範圍的數列都可以包含 *常數區段* 和 *英數字元區段*。 常數段包含一組不變的英數字元字元。 使用此段類型在數列段之間新增連字元號或其他分隔符號。 英數字元區段包含數字元號 (#) 和 & 符號的組合。 這些字元代表每次使用序列中的數字時遞增的字母和數字。 使用數字元號 (#) 表示遞增的數字，使用 & 符號表示遞增的字母。 例如，格式 `#####_2014` 會建立序列 `00001_2014`、`00002_2014` 等。 必須至少存在一個英數字元區段。 不需要範圍區段，例如公司或法律實體。 但是，如果您在格式中不包括範圍段，則仍會為每個範圍產生所選參考的編號。  
7. 展開 **參考** 區段。 選取要指派此數列的文件類型或記錄。 對於為特殊應用程式使用模式定義的序列，此步驟是可選的。 在這些場景中，透過使用編號序列碼或 ID 的值來產生新編號，而不使用參考。 特殊應用程式使用模式的一個範例是用於特定日記帳名稱的憑證系列。 但是，我們不建議您使用此類模式。  
8. 展開 **一般** 區段。 在一般 FastTab 上，指定數列是手動的、連續的還是非連續的。 此外，輸入可用於數列的最小和最大數字。 我們不建議將非連續數列更改為連續數列。 數列將不是真正連續的。 此更改還可能導致資料庫中出現重複的金鑰違規。 此外，連續數列對效能的影響更大。   
9. 選取 **儲存**。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
