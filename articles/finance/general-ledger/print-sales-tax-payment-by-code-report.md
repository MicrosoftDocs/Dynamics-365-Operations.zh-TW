---
title: 按代碼報表列付銷售稅款項
description: 本主題提供有關需以會計或稅碼貨幣，按代碼報表列印銷售稅款項的設定和動作資訊。
author: anasyash
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 7c863308d2efc442ad16973407fe1cb72fb68cf89204c20f4468a3c98f4740c5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450798"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a>按代碼報表列付銷售稅款項 

[!include [banner](../includes/banner.md)]

若要列印 **按代碼的銷售稅** 報表，請前往 **稅賦**\>**查詢和報表**\>**銷售稅報表**\>**按代碼的銷售稅款項**。 報表金額預設以法人的記帳貨幣，針對 **銷售稅報表代碼** 頁上設定的所有報表代碼產生。

您也可以產生此報表，以便針對 **銷售稅代碼** 頁上指派給銷售稅代碼的所有報表代碼，以銷售稅代碼的貨幣顯示銷售稅款項金額。

## <a name="turn-on-the-feature"></a>開啟功能

請在 **功能管理** 工作區開啟下列功能：**以銷售稅代碼貨幣，按代碼報表產生增值稅款項**。

## <a name="run-the-report"></a>跑報表

1. 請前往 **稅賦**\>**查詢和報表**\>**銷售稅報表**\>**按代碼的銷售稅款項**。
2. 請在 **報表貨幣** 欄位，選取下列其中一值：

    - **會計貨幣** – 以會計貨幣列印報表金額。
    - **銷售稅代碼貨幣** – 以銷售稅代碼的貨幣列印報表金額。

    ![按照代碼的銷售稅款項對話方塊。](media/Sales-tax-payment-by-code.png)

下圖顯示產生的報表範例。 如果針對指派報表代碼的銷售稅代碼，**銷售稅貨幣** 欄位設定為 **歐元**，則報表會顯示報表代碼 **101** 有 **歐元** 貨幣。

![按代碼報表的銷售稅款項範例。](media/Sales-tax-payment-by-code-2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]