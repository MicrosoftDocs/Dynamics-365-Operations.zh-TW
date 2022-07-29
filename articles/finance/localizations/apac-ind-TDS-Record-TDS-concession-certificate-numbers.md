---
title: 記錄 TDS 減免憑證編號
description: 本主題說明如何記錄發放給廠商的從源頭扣除稅款 (TDS) 減免憑證編號。
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
ms.openlocfilehash: d83379b0377bdbb848158f83f1f3229e09323602
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451782"
---
# <a name="record-tds-concession-certificate-numbers"></a>記錄 TDS 減免憑證編號

[!include [banner](../includes/banner.md)]

本主題說明如何記錄發放給廠商的從源頭扣除稅款 (TDS) 減免憑證編號。

1. 前往 **稅務 \> 間接稅 \> 扣繳稅款 \> 扣繳稅款減免**。
2. 在 **稅務類型** 欄位中，選擇 **TDS** 以記錄 TDS 稅務類型的減免憑證。
3. 在 **概觀** 索引標籤上，選擇 **Alt+N** 以建立行。

    [![新行的標題。](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)

4. 在 **扣繳稅款代碼** 欄位中，選擇為其發放廠商減免憑證的 TDS 稅碼。 這 **扣繳稅款代碼名稱** 欄位顯示 TDS 稅碼的名稱。
5. 在 **開始日期** 和 **結束日期** 欄位中，定義減免憑證的有效期，該減免憑證使用 TDS 稅碼在減免基礎上為廠商計算 TDS。
6. 在 **備註** 欄位中，輸入任何備註。
7. 在 **章節** 欄位中，輸入 TDS 減免憑證可用的法律章節代碼。

    如果章節代碼為 197，則 26Q 表單中的「非扣除/降低扣除的原因」資料行和 27Q 表單中的「非扣除/降低扣除/補償費 (如果有) 的原因」資料行中均顯示 "A" 值。 如果章節代碼是 197A，則這兩個資料行中均顯示 "B" 值。

8. 選擇 **憑證** FastTab 以記錄廠商的 TDS 減免憑證編號。
9. 在 **廠商帳戶** 欄位中，選擇為其發放 TDS 減免憑證的廠商帳戶。
10. 在 **開始日期** 和 **結束日期** 欄位中，定義 TDS 減免憑證的有效期。

    根據減免的 TDS 計算為廠商建立憑證的時間段。

11. 在 **憑證** 欄位中，輸入 TDS 減免憑證編號。

    [![憑證 FastTab。](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)

12. 關閉頁面。
