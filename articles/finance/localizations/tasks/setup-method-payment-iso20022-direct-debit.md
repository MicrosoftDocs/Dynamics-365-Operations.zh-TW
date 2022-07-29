---
title: 設置 ISO20022 直接借記的付款方式
description: 此程序顯示如何使用電子報告設定 ISO20022 直接扣款或任何其他付款類型的客戶付款方式。
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 127d5402abfedcce124b39b76a6c1036a6c818a7c1318aaeabdb0688b50f738e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450867"
---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a>設置 ISO20022 直接借記的付款方式

[!include [banner](../../includes/banner.md)]

此程序顯示如何使用電子報告設定 ISO20022 直接扣款或任何其他付款類型的客戶付款方式。 



在完成此工作之前，您必須設定匯出格式組態和付款帳戶。



本段程序使用 DEMF 示範資料公司建立。



這是五個使用電子報表組態的客戶付款流程示範程序中第三個。

1. 前往 \[應收帳款\] > \[付款設定\] > \[付款方式\]。
2. 使用快速篩選條件尋找記錄。 例如，篩選其值為 'ELECTRONIC' 的 \[付款方式\] 欄位。
3. 點選編輯。
4. 在 \[付款帳戶\] 欄位中，指定 'DEMF OPER' 值。
5. 展開檔案格式區段。
6. 在 \[一般電子報表\] 欄位中選取 \[是\]。
7. 在 \[匯出格式組態\] 欄位中輸入或選擇一個值。
    * 在清單中，選取 \[ISO20022 直接扣款 (DE)\]。  如果清單是空白的，則尚未匯入與啟用客戶付款匯出格式組態。  
8. 在 \[需要授權\] 欄位中選取 \[是\]。
    * 為客戶付款格式選取 \[需要授權\] 參數，這需要在付款訊息 (例如 SEPA 直接扣款) 中包含授權資訊。  
9. 點選儲存。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]