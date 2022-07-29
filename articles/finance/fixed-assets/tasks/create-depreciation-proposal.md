---
title: 建立折舊提案
description: 本主題介紹折舊批次提案的運作原理，並說明如何為固定資產提案折舊。
author: abruer
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6cf285e8764af8c6525fb3f9cbec7306917e57e832777588e8c2c1d4aeed818
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450177"
---
# <a name="create-a-depreciation-proposal"></a>建立折舊提案

[!include [banner](../../includes/banner.md)]

本主題介紹折舊批次提案的運作原理，並說明如何為固定資產提案折舊。 此工作使用 USMF 示範公司和會計角色。


## <a name="create-a-depreciation-proposal"></a>建立折舊提案
1. 在導覽窗格中，前往 **模組 > 固定資產 > 日記帳分錄 > 建立折舊提案**。
2. 在 **日記帳名稱** 欄位中，從下拉式功能表中選擇一個選項。
3. 請在 **截止日期** 欄位中輸入日期。

    - 選擇 **總結折舊** 選項，將每月折舊匯總到一個日記帳行。  
    - 例如，如果 [結束日期] 值為 2015 年 3 月 31 日，則會產生以下描述：「自 2015 年 1 月 31 日起折舊」。 然後將提案的日記帳行上的 **日期** 欄位設定為 2015 年 3 月 31 日。  
    - 可以使用 **篩選** 選項，依資產、資產群組或其他條件篩選折舊提案。  
    - 使用 **為固定資產建立購置或折舊提案** 表單時，可以分批提出折舊提案。 對於將使用較多系統資源的較大提案，建議使用此方法。 如果選擇批次選項，您仍然可以在該期間完成其他工作。 當您以這種方式提案折舊時，將為固定資產的價值模型計算折舊。  

4. 選擇 **建立日記帳**。

## <a name="review-depreciation-entries"></a>查看折舊分錄
1. 在導覽窗格中，前往 **模組 > 固定資產 > 日記帳分錄 > 固定資產日記帳**。
2. 在清單中，尋找並選取所需的記錄。
3. 選取 **行**。
4. 選取 **過帳**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]