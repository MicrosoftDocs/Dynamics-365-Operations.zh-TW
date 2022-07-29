---
title: 設定租賃日記帳名稱
description: 本主題說明如何定義租賃日記帳名稱。 租賃日記帳名稱會指定要將源自資產租賃的分錄過帳到的日記帳。
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b9d8136ae4f960a586b9526751fc8bf6e7675c8d
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451272"
---
# <a name="set-up-lease-journal-names"></a>設定租賃日記帳名稱

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


租賃日記帳名稱會指定要將資產租賃交易過帳到的日記帳。 僅指派給 **資產租賃** 日記帳類型的日記帳名稱會顯示在 **資產租賃參數** 頁面上的 **初始認列** 與 **每月日記帳名稱** 欄位中。 僅 **廠商發票記錄** 日記帳類型可以指派給 **發票日記帳名稱** 欄位。

系統鎖定某些財務欄位，使其不能編輯，以防止交易和計劃之間出現任何差異。 已鎖定的欄位包括：**帳戶**、**金額**、**財務維度**、**貨幣** 和 **交易類型**。 此外，您將無法在任何資產租賃日記帳分錄中新增或刪除日記帳分錄行，因為這可能會導致計劃和交易之間出現差異。


若要設定租賃日記帳名稱，請完成以下步驟。

1. 前往 **資產租賃\>設定\>資產租賃參數**。
2. 在 **一般** 索引標籤上的 **初始認列日記帳名稱** 欄位中選擇一個日記帳。 所有初始認列日記帳分錄將過帳至此日記帳名稱。
3. 在 **發票日記帳名稱** 欄位中選擇一個日記帳。 如果租賃帳冊的 **向廠商付款** 選項設定為 **是**，則租賃和費用付款發票將過帳到此日記帳名稱。
4. 在 **租賃日記帳名稱** 欄位中選擇一個日記帳。 所有折舊、利息和短期重新分類分錄將過帳至到此日記帳名稱。 如果租賃帳冊的 **向廠商付款** 選項設定為 **否**，則租賃付款和費用付款分錄也將過帳到此日記帳名稱。
5. 在 **租賃修改日記帳名稱** 欄位中選擇一個日記帳。 租賃調整、終止和減值交易將過帳至此日記帳名稱。 您選取的日記帳名稱不應獲指派工作流程或核准。 如果未定義租賃修改日記帳名稱，則租賃調整、終止和減值交易將過帳至在 **租賃日記帳名稱** 欄位中選取的日記帳名稱。 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
