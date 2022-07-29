---
title: 管理國際銀行帳號 (IBAN) 帳戶驗證
description: 本主題解釋如何管理國際銀行帳號 (IBAN) 帳戶驗證。
author: roschlom
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 210d2f57e21ec5ac38ba8ca07195e40ff507e2b9
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/23/2021
ms.locfileid: "8451200"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a>管理國際銀行帳號 (IBAN) 帳戶驗證

[!include [banner](../includes/banner.md)]

當您新增國際銀行帳號 (IBAN) 到銀行帳戶時，國際銀行帳號驗證會增加已完成驗證的數額。

有關 IBAN 結構的資訊儲存在 Microsoft Dynamics 365 Finance。 當您第一次在銀行帳戶上使用 IBAN 時，會自動載入該項資訊。 它包含 IBAN 的長度、銀行帳號和路由號碼的起始位置、銀行帳號和路由編號的長度。

## <a name="set-up-iban-structures"></a>設定 IBAN 結構

1. 請前往 **現金和銀行管理參數\>設定 \>IBAN 結構**。
2. 請注意，每個國家或地區的 IBAN 結構已自動設定。
3. 如果您希望為特定國家或地區客製化結構，您可以編輯它們。
4. 結構定義將是每個新發行版本的一部分。 您可以使用 **重設結構** 功能表在每次更新後載入最新定義。

## <a name="validate-the-iban-structure-in-a-bank-account"></a>驗證銀行帳戶的 IBAN 結構

1. 請前往 **現金和銀行管理\>銀行帳戶\>銀行帳戶**。
2. 建立銀行帳戶。
3. 請在 **額外資訊** FastTab 上輸入 IBAN。

    如果 IBAN 長度與定義的每個國家或地區長度不符，您將收到一則警告訊息。 如果 IBAN 長度與 IBAN 結構指明的長度不符，您無法繼續。

    驗證也會驗證銀行帳號是否與代表銀行帳號的 IBAN 部分相符。 如果銀行帳號不符，您將收到一則警告訊息。 本則訊息只是警告。 即使銀行帳號不符，您仍可以繼續。

    驗證也會驗證銀行路由號碼是否與代表銀行路由號碼的 IBAN 部分相符。 路由號碼包括銀行號碼以及往往包括額外的銀行分行代碼。 如果銀行路由號碼不符，您將收到一則警告訊息。 本則訊息只是警告。 即使銀行路由號碼不符，您仍可以繼續。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
