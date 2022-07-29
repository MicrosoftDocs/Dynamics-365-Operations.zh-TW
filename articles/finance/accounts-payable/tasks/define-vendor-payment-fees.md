---
title: 定義廠商付款費用
description: 設定廠商付款費用。
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c490bb4d15fa03742b12f337046f26976ab70d29
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451548"
---
# <a name="define-vendor-payment-fees"></a>定義廠商付款費用

[!include [banner](../../includes/banner.md)]

設定廠商付款費用。 此工作使用 USMF 公司進行示範。

1. 前往 **應付帳款 > 付款設定 > 付款費用**。
2. 點選 **新增**。
3. 在 **費用識別碼** 欄位中輸入值。
    * **費用識別碼** 應描述何時使用此費用，例如 "EFT_Fee"。  
4. 在 **名稱** 欄位中，輸入一個值。
5. 在 **費用描述** 欄位中，輸入一個值。
    * 新增描述以提供有關何時評估費用的更多詳細資訊。  
6. 在 **費用** 欄位，選擇 **廠商** 或 **分類帳**。
    * 向您的組織支付該費用時，將使用 **分類帳**。 評估廠商費用時，將使用 **廠商**。  
7. 在費用支付位置輸入主科目。
    * 只有在 **費用** 選項中選擇 **分類帳** 時，此選項才可用。  
8. 選擇可供該費用使用的日記帳。 
    * 對於廠商付款費用，您可以選擇 [廠商支付] 日記帳。  
9. 點選 **儲存**。
10. 點選 **付款費用設定**。
    * 繼續在 **付款費用設定** 中，定義何時將該費用設定為所選日記帳的預設值。  
11. 選擇 **資料表**、**群組** 或 **全部**。
    * **資料表** 用於選擇單個銀行帳戶，**群組** 用於選擇銀行群組，**全部** 是將此費用設定套用於所有銀行帳戶。  
12. 選擇銀行群組或銀行帳戶。
    * 如果您選擇的為 **群組**，查詢將顯示銀行群組；如果您選擇的為 **資料表**，查詢操作將顯示銀行帳號。  
13. 選擇用於評估該費時的付款方式。
14. 選取所選付款方式的 **付款規範**。
    * 電子資金轉帳付款方式應遵循 **付款規範**。  
15. 選擇費用是百分比、金額還是間隔。
16. 輸入費用的百分比或金額。
    * 如果 **費用** 是百分比，請輸入百分比。 如果 **費用** 是金額，請輸入費用的金額。 如果 **費用** 是一個區間，請使用 **間隔** 索引標籤以定義分層費用。  
17. 在 **費用貨幣** 欄位中，選擇評估費用的貨幣。
    * 這種貨幣用於費用。 付款貨幣用於定義何時應根據付款貨幣評估費用規則。 例如，您的銀行可能會在以歐元付款時收取費用，但對於其他付款則不會評估費用。  
18. 點選 **儲存**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
