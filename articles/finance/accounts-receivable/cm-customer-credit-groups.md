---
title: 客戶信用群組
description: 本主題提供有關客戶信用群組的資訊。
author: JodiChristiansen
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: c8a007dcaaa9e10ab36dd3a7d0f80dd49b8e4d63
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2021
ms.locfileid: "8451158"
---
# <a name="customer-credit-groups"></a>客戶信用群組

[!include [banner](../includes/banner.md)]

您可以定義具有共用信用額度的客戶群組。 還考慮在客戶發票帳戶上定義的個人信用額度。

客戶信用群組的成員可以從不同的法律實體中選擇。 當您將客戶新增到客戶信用群組中的客戶清單時，每個客戶的信用額度的到期日期將變更為分配給該組的到期日期。

您可以在 **客戶信用群組** 頁面 (**信用管理\>客戶信用群組\>客戶信用群組**) 上設定客戶信用群組。

1. 在 **群組編號** 和 **描述** 欄位，輸入群組的識別碼和描述。
2. 在 **信用額度** 和 **貨幣** 欄位中，輸入系統檢查群組中任何成員的信用額度時應使用的信用額度和貨幣。
3. 在 **信用額度結束日期** 欄位，輸入信用額度的到期日期。 客戶信用群組必須有一個到期日期。

完成客戶信用群組設定後，您可以透過指定客戶的法律實體和客戶帳戶識別碼將客戶新增到群組中。 當您將新客戶新增到客戶信用群組時，系統會在所有法律實體中搜尋相同的客戶帳戶並提示您將其新增到客戶信用群組。

使用 **帳齡餘額** 功能表以查看客戶信用群組中所有發票客戶的帳齡餘額的詳細資訊。 **帳齡餘額** 頁面會顯示發票客戶帳戶的帳齡餘額摘要。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
