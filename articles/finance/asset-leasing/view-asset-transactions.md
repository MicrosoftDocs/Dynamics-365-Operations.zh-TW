---
title: 檢視負債、資產和費用交易
description: 本主題說明如何檢視租賃資產的交易記錄。 這些交易包括已過賬的租賃負債交易和執行費用交易。
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 58a57b2a1237b41c99e44cf40c57d80257fc9b5b77188586aab6735a8a3f4984
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450684"
---
# <a name="view-liability-asset-and-expense-transactions"></a>檢視負債、資產和費用交易

[!include [banner](../includes/banner.md)]

本主題說明如何檢視租賃資產的交易記錄。 這些交易包括已過賬的租賃負債交易和執行費用交易。 負債和使用權 (ROU) 資產的帳面價值在多份報告中使用。 它們還用於計算調整值。

## <a name="liability-transactions"></a>負債交易

若要檢視租賃負債交易，請選取 **租賃摘要** 頁面上的租賃，然後選取 **帳冊** 打開附加到租賃記錄的帳冊。 在初始確認、發票或利息日記帳過帳後，選取 **負債交易**。

**負債交易** 頁面顯示增加或減少租賃負債的交易。 此頁面上的負數表示標準應用程式中的信用交易。 任何應計利息均顯示為負值並增加總租賃負債。 任何租賃調整均顯示為正值或負值，具體取決於租賃帳冊的性質和影響。 所選租賃的目前租賃負債淨總額顯示在頁面左下方。

## <a name="asset-transactions"></a>資產交易

若要檢視租賃資產交易，請選取 **租賃摘要** 頁面上的租賃，然後選取 **帳冊** 打開附加到租賃記錄的租賃帳冊。 然後選取 **資產交易**。

**資產交易** 頁面顯示增加或減少租賃資產和累計折舊帳戶的交易。 借方顯示為正值，貸方顯示為負值，如 **負債交易** 頁面。 已過帳的初始確認和下一個累計折舊顯示在頁面左下方作為資產餘額。 

## <a name="expenses-transactions"></a>費用交易

若要檢視租賃費用交易，請選取 **租賃摘要** 頁面上的租賃，然後選取 **帳冊** 打開附加到租賃記錄的租賃帳冊。 然後選取 **費用交易**。

**費用交易** 頁面顯示已針對租賃過帳的所有費用，例如利息費用、折舊費用和任何執行費用。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
