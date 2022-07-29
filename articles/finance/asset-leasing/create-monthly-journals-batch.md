---
title: 以批次建立月日記帳分錄
description: 本主題說明如何在記錄每月租賃費用時，以批次建立日記帳分錄來幫助提高效率。
author: moaamer
ms.date: 08/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 22e2892a6866123ecf0e72511bdce19fe12895df
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "8450900"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a>以批次建立月日記帳分錄

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


本主題說明如何在記錄每月租賃費用時，以批次建立日記帳分錄來幫助提高效率。 批次可用於從多個計劃建立日記帳分錄。 這些日記帳分錄可以包括租賃付款、負債攤銷、使用權 (ROU) 資產攤銷和執行成本費用。 您還可以使用批次同時對多個租賃進行初始認列，或同時為多個租賃建立過渡調整。

要設定批次作業，或處理多個租賃的付款發票、折舊或利息，請前往 **資產租賃 \> 定期 \> 建立批次日記帳**。 在出現的對話方塊中，您可以選擇建立日記帳分錄的計劃。 您還可以指定是否應為特定實體、租賃組或租賃帳簿執行批次處理。

> [!NOTE]
> 後續交易 (例如負債攤銷計劃、付款、折舊和費用) 將僅在相應租賃的初始認列過帳後才過帳。
>
> 將建立日記帳分錄，但在您選擇 **執行** 命令之前，不會過帳這些分錄。

要在租賃開始日期以外的其他日期過帳初始認列日記帳，請選擇 **指派初始認列過帳日期**。 將顯示 **日期** 欄位，以便您指定正確的過帳日期。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
