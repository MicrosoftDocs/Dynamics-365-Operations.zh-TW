---
title: 設定遠期支票
description: 本主題說明如何指定是否為遠期支票過帳日記帳分錄，以及用於清算分錄和廠商付款的過帳日記帳。
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fc1798836d9b905d991adb4c87d55ddce41d260bdbfdad6bf0c4b4feb846ee57
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450450"
---
# <a name="set-up-postdated-checks"></a>設定遠期支票

[!include [banner](../../includes/banner.md)]

本主題說明如何指定是否為遠期支票過帳日記帳分錄，以及用於清算分錄和廠商付款的過帳日記帳。 您還可以為簽發的支票、收到的支票和預扣稅款指定清算科目。 針對未來日期收付款而簽發的遠期支票。 您可以指定支票在到期日之前是否必須反映在會計帳簿中。



此程序的角色是 Treasurer。 此程序使用的是 USMF 示範公司。


## <a name="set-up-postdated-checks"></a>設定遠期支票
1. 前往 [現金和銀行管理] > [設定] > [現金和銀行管理參數]。
2. 點選遠期支票索引標籤。
3. 選取或清除 \[啟用遠期支票\] 核取方塊。
4. 選取或清除 \[過帳遠期支票的日記帳分錄\] 核取方塊。
5. 在 \[所簽發支票的結算帳戶\] 欄位中，指定所需的值。
6. 在 \[所收到支票的結算帳戶\] 欄位中，指定所需的值。
7. 在 \[用於清算分錄的一般日記帳\] 欄位中輸入一個值。
8. 在 \[將遠期支票轉入此廠商付款日記帳\] 欄位中輸入一個值。
9. 在 \[扣繳稅款結算帳戶\] 欄位中，指定所需的值。
10. 點選儲存。
11. 關閉頁面。
12. 進入應付帳款 > 付款安裝 > 付款方式。
13. 點選新增。
14. 在付款方式欄位，鍵入一值。
15. 選取 \[遠期支票結算過帳\] 選項，以指示將支票金額過帳到清算帳戶。
16. 在 \[帳戶類型\] 欄位中，選取 \[銀行\]。
    * 付款方式的沖銷帳戶將是銀行。  
17. 在 \[付款帳戶\] 欄位中，指定所需的值。
    * 選取用於扣除發票金額的銀行帳戶。  
18. 點選儲存。
19. 關閉頁面。
> [!NOTE]
> 為了能夠在工作階段日期晚於或等於到期日期時將遠期支票過帳到銀行帳戶，您必須啟用 **將帶有遠期支票的付款日記帳過帳到銀行帳戶的到期日驗證** 功能。 當工作階段日期晚於或等於到期日期時，此功能允許您使用遠期支票為廠商或客戶過帳付款日記帳。
> 
> 設定 **付款方式** (**應付帳款 > 付款設定 > 付款方式**) 時，請勿填寫 **過渡帳戶**。 在這種情況下，在沖銷帳戶中填寫銀行帳戶，該帳戶是在 **付款方式** 中設定的。
>  
> 如果此功能已啟用且工作階段日期早於到期日期，則當過帳付款日記帳時會顯示以下錯誤訊息: 「如果沖銷帳戶類型為銀行，則到期日期必須早於或等於工作階段日期」。 如果未啟用該功能，您可以在工作階段日期早於到期日期時，過帳帶有遠期支票的付款日記帳。
> 版本 10.0.21 或更新版本中提供此功能。    

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
