---
title: 建立廠商銀行帳戶
description: 此程序說明如何建立廠商的銀行帳戶。
author: Henrikan
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, LogisticsPostalAddressSingle
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5d24535035d26ca1313e293f9958b1b5000bb845
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448818"
---
# <a name="create-a-vendor-bank-account"></a>建立廠商銀行帳戶

[!include [banner](../../includes/banner.md)]

此程序說明如何建立廠商的銀行帳戶。 您可以在 USMF 示範公司資料中使用此程序。

1. 移至 **瀏覽窗格 > 模組 > 採購及開源 > 廠商 > 所有廠商**。
2. 選擇您要為之建立銀行帳戶的廠商，然後按一下 **廠商帳戶識別碼** 欄位的連結。
3. 在 **動作窗格** 上，按一下 **廠商**。
4. 按一下 **銀行帳戶**。
5. 在 **動作窗格** 上，按一下 **新增**。
6. 在 **銀行帳戶** 欄位中，輸入一個值。 此識別碼將用於識別廠商記錄中的銀行帳戶。  
7. 在 **名稱** 欄位中，輸入一個值。
8. 在 **銀行群組** 欄位中，輸入或選擇一個值。
9. 在 **匯款路徑編號類型** 欄位中，選擇一個選項。 此匯款路徑編號類型係用於國際支付。  
10. 在 **銀行帳號** 欄位中，輸入一個值。
11. 在 **SWIFT 代碼** 欄位中，輸入一個值。
12. 在 **IBAN** 欄位中，輸入一個值。
    - IBAN 號碼的格式必須正確。 例如，此號碼可能為 DE89370400440532013000。  
    - 若銀行帳戶的啟用日已過且仍在到期日前，則其狀態會顯示啟用中。 若啟用日和到期日欄位皆為空白，則其狀態也會顯示啟用中。 若啟用日和到期日欄位的日期都尚未到來，則無法使用電子支付。 可提供其他支付類型且銀行帳戶為啟用中。  
13. 展開 **設定** 區段。
14. 在 **文字代碼** 欄位中，輸入一個值。 此欄位指定的代碼將出現在收款人的銀行對帳單上。  
15. 在 **給銀行的訊息** 欄位中，輸入一個值。
16. 在 **匯率參考** 欄位中，輸入一個值。 此為遠期或固定匯率的參考編號。
17. 在 **貨幣** 欄位中，輸入或選擇一個值。 發佈轉帳測試時，此區段會提供狀態概觀 (待核准或已核准)。  
18. 展開 **地址** 區段。
19. 展開 **轉帳測試** 區段。
20. 展開 **連絡資訊** 區段。
21. 在 **電話** 欄位中，輸入一個值。
22. 關閉頁面。
23. 按一下 **編輯**。
24. 展開 **付款** 區段。
25. 在 **銀行帳戶** 欄位中，選擇您剛建立的帳戶。
26. 按一下 **儲存**。 若其銀行群組已指定地址，則會繼承該地址，或您可在此新增。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]