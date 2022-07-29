---
title: 重新分類租賃負債的短期部分
description: 本主題說明如何建立每月日記帳分錄，以便將租賃負債部份重新分類為短期。
author: moaamer
ms.date: 04/12/2021
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
ms.openlocfilehash: 21cf81ce84d91d88a800cd250fca8fd5a9c876e66f506cd366b8d61ed480ea7e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450195"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a>重新分類租賃負債的短期部分

[!include [banner](../includes/banner.md)]

本主題說明如何建立每月日記帳分錄，以便將租賃負債部份重新分類為短期。 當批次處理選取的期程是 **短期租賃負債重新分類**，會依此建立日記帳分錄。 本分錄於來過帳當月最後一天租賃負債的目前部分。 同時，過帳截至下個月第一天為止的沖銷分錄。

租賃負債的短期部分如負債攤銷期程表所示。 當日記帳分錄過帳時，**已建立負債重新分類日記帳** 欄位就會開放使用，而且日記帳識別碼也會填寫在期程表上。

若要建立和過帳短期負債重新分類日記帳分錄，請執行下列步驟。

1. 前往 **資產租賃\>定期\>批次日記帳建立**。
2. 在 **批次日記帳建立** 對話框的 **選取期程表** 欄位，選取 **短期租賃負債重新分類**。
3. 在 **租賃群組** 欄位，選取租賃群組。 或者，在 **帳冊識別碼** 欄位，選取帳冊識別碼。
4. 開啟 **過帳** 參數。 或者，如果分錄應該建立但不過帳，讓此參數關閉。
5. 選取 **確定**。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
