---
title: 資產借出
description: 本主題介紹如何在資產管理中登記借出資產。
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 65809d9be39372412d5d6b419f7356fe2c9668a1a01ede32ef52cbd66753e6d7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447036"
---
# <a name="asset-loans"></a>資產借出

[!include [banner](../../includes/banner.md)]

 

如果您的公司那裡收到要進行修復或維護工作的資產，不論是從內部地點或客戶，並且如果您暫時將資產借給這些位置或客戶，則資產管理可以追蹤資產借出。

## <a name="register-asset-loans-on-a-maintenance-request"></a>依維護要求登記資產借出

1. 選擇 **資產管理** \> **通用** \> **維護要求** \> **所有維護要求** 或 **使用中維護要求**。
2. 選取維護要求註冊資產借出，然後選取 **編輯**。
3. 在 **要求** 頁面，選取 **發送借出資產**。
4. 選取資產，然後輸入預期歸還日期。
5. 請選取 **確定**。

> [!NOTE]
> - 只有在相同資產類型的資產可用時，您才能發送資產借出。
> - 您借出的資產必須處於可作為借出資產的資產生命週期狀態，例如 **InStorage**。 在資產借出註冊時，資產的資產生命週期狀態會自動更新為，例如，**OnLoan**。

若要查看借出給其他位置或客戶的所有資產的列表，請選擇 **資產管理**\>**一般**\>**資產借出**\>**所有資產借出**。 如果資產的 **結束** 核取方塊已選取，則該資產已登記為歸還到公司。

![管理維護要求](media/06-manage-maintenance-requests.png)

在 **現行資產借出** 頁面，您可以查看尚未歸還的所有借出資產的列表。

## <a name="register-loan-assets-as-returned"></a>將借出資產登記為歸還

1. 選取 **資產管理** \> **一般** \> **資產借出** \> **現行資產借出**。
2. 選取資產借出登記為歸還，然後選取 **歸還資產借出**。
3. 在 **歸還** 欄位，輸入日期和時間。
4. 選取 **確定**。
5. 重新整理 **現行資產借出** 列表頁面，並注意資產借出已不再出現在列表中。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]