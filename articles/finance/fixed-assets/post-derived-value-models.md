---
title: 使用衍生帳冊過帳
description: 本文章說明如何使用衍生帳冊。
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef0c7b2ad93f4a9c4ff24052c749f7891f9e915d
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451101"
---
# <a name="post-with-derived-books"></a>使用衍生帳冊過帳

[!include [banner](../includes/banner.md)]

本文章說明如何使用衍生帳冊。

當您為內含衍生帳冊的帳冊過帳交易時，衍生帳冊交易會自動在日記帳、訂購單或普通發票過帳。 然而，如果您在固定資產日記帳中準備主要帳冊交易，您可以在過帳前檢視和修改衍生交易的金額。
-   特定帳戶如銷售稅和客戶或廠商帳戶，只藉由主帳冊過帳更新一次。 衍生帳冊交易會過帳到已經在固定資產過帳設定檔頁面定義衍生帳冊的科目。
-   取得往往當成衍生帳冊的交易類型。 當帳冊和衍生帳冊應從取得固定資產時套用到固定資產時，您可以使用此選項。
-   其他交易類型的數值也適用。 例如，如果主帳冊和衍生帳冊的銷售或處置間隔相同，則所有固定資產交易類型皆可開放設定衍生帳冊。

> [!WARNING]
> 在衍生帳冊過帳的折舊金額將與主帳冊過帳的金額相同。 如果帳冊之間的折舊方法不同，您不應使用衍生流程產生折舊交易。 |

## <a name="example"></a>範例  
下列資訊說明如何使用衍生帳冊功能設定取得交易。

1.  在帳冊頁面上建立帳冊。
    -   會計帳冊：VM 1，本年度過帳
    -   稅務帳冊：VM 2，稅賦過帳年度

2.  在 VM 1 上點選衍生帳冊索引標籤。在 Book 欄位選取 VM 2 和 Transaction 類型欄位選取 Acquisition。

接著帳冊可以附到特定固定資產。 

當 VM 1 帳冊的固定資產過帳取得時，不僅在 VM 1 過帳，也會在衍生帳冊 VM 2 過帳。 兩本固定資產帳冊的狀態皆更新為 Open。

> [!NOTE]                                                                                                         
> 如果您不使用衍生帳冊，您必須同時為 VM 1 和 VM 2 帳冊過帳固定資產的取得。

更多資訊，請參閱[衍生帳冊](derived-books.md)。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
