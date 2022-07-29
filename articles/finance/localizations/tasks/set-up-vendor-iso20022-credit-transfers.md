---
title: 設定廠商和 ISO20022 貸方轉帳的廠商銀行帳戶
description: 此程序示範如何設定 ISO20022 匯款轉帳或產生任何其他廠商付款檔案所需的廠商與廠商特定的銀行帳戶資訊。
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7a901591f9f3d1a892c29f92e59dc96c1f172143cae6bec571da33b4a50d274
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450219"
---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a>設定廠商和 ISO20022 貸方轉帳的廠商銀行帳戶

[!include [banner](../../includes/banner.md)]

此程序示範如何設定 ISO20022 匯款轉帳或產生任何其他廠商付款檔案所需的廠商與廠商特定的銀行帳戶資訊。 

用來建立此程序的示範資料公司為 DEMF。
這是五個用於說明使用電子申報設定的廠商付款流程之程序中的第四個。 此程序是 Dynamics 365 for Operations 版本 1611 中增加的功能。


## <a name="set-up-bank-details"></a>設定銀行詳細資料
1. 移至 \[應付帳款\] > \[廠商\] > \[所有廠商\]。
2. 使用快速篩選條件尋找記錄。 例如，使用值為「DE-001」的 \[廠商帳戶\] 欄位篩選。
3. 按一下 \[DE-001\] 開啟廠商詳細資料。
4. 在動作窗格上，按一下廠商。
5. 按一下 [銀行帳戶]。
6. 點選編輯。
    * 如果沒有可用的銀行帳戶，您需要建立一個新帳戶。  
7. 在 [SWIFT 代碼] 欄位中，輸入「COBADEFFXXX」。
8. 在 [IBAN] 欄位中，輸入「DE36200400000628808808」。
9. 關閉頁面。

## <a name="set-up-a-method-of-payment-for-the-vendor"></a>設定廠商的付款方式
1. 點選編輯。
2. 展開或摺疊 \[付款\] 區段。
3. 在付款方式欄位中，點選下拉式按鈕打開查閱功能。
4. 在清單中，按一下 \[SEPA CT\] 列中的連結。
5. 點選儲存。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]