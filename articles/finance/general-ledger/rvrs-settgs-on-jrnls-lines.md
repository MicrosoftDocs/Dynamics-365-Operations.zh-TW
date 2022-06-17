---
title: 日記帳和明細的逆轉設定
description: 本主題說明了為什麼在一般日記帳上輸入的沖銷分錄可能不會包含在過帳的交易中。
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d0659fbd814d3fb86b2f4a1ecb6162614ab8a4f125029fbb04f08cc5fb52b45c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8452877"
---
# <a name="reverse-settings-on-journals-and-lines"></a>日記帳和明細的逆轉設定

[!include [banner](../includes/banner.md)]

本主題說明了為什麼在一般日記帳上輸入的沖銷分錄可能不會包含在過帳的交易中。  

## <a name="symptom"></a>徵兆

一般日記帳的日記帳上包含沖銷分錄和沖銷日期。 日記帳過帳時，未沖銷任何憑單。 成因為何？

## <a name="resolution"></a>解決方法

當日記帳過帳時，沖銷流程只會對照憑單上 **明細** 區段的 **沖銷分錄** 和 **沖銷日期** 設定。 這種做法讓日記帳可能同時包含為了沖銷而標記的憑單及其他未標記的憑單。

日誌中的值只會在 *新增* 明細時，用作預設。 變更日記帳的值不會影響現有明細。 在本範例中，先輸入了憑單明細。 若您在將日記帳指定為沖銷日記帳之前，先輸入了明細詳細資料，指定的沖銷分錄和日期就不會套用於任何現有的明細。

變更現有明細的沖銷分錄或沖銷日期，則會將該變更傳播到同一憑單中的其他明細。 為達最佳效能，格線在將變更傳播到其他明細後，並不會重新整理。 您可以重新整理格線以顯示更新的值。


