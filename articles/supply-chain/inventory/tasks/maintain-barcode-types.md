---
title: 維護條碼類型
description: 此程序將向您展示如何設定新的條碼定義，然後將其用作揀料單報告的一部分。
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b689d1fc85d59ac87efa1903fd7122ae5ff011da
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448377"
---
# <a name="maintain-bar-code-types"></a>維護條碼類型

[!include [banner](../../includes/banner.md)]

此程序將向您展示如何設定新的條碼定義，然後將其用作揀料單報告的一部分。 您能以示範資料公司 USMF 或自己的資料走完這段程序。 如果您使用的是 USMF，您可以使用顯示的範例值。 這些工作通常由倉庫經理執行。

1. 前往 **條碼**。
1. 選擇 **新增**。
1. 在 **條碼設定** 欄位中，輸入一個值。
1. 在 **描述** 欄位中，輸入一個值。
1. 請在 **條碼類型** 欄位中選取一個選項。
    * 如果您使用 USMF，則可以選取「編碼 39」。
1. 在 **遮罩識別碼** 欄位，指定條碼遮罩識別碼。 條碼遮罩會用於建立條碼，並快速識別掃描到銷售點 (POS) 系統的條碼。 如需詳細資訊，請參閱[設定條碼遮罩](../../../commerce/set-up-bar-code-masks.md)。
1. 在 **尺寸** 欄位中，輸入數字。
1. 在 **最大長度** 欄位中，輸入數字。
1. 選擇 **儲存**。
1. 關閉頁面。
1. 前往 **庫存和倉庫管理參數**。
1. 在 **條碼設定** 欄位中，輸入或選擇一個值。
    * 選擇您之前建立的條碼設定，但請注意條碼格式必須與流程中使用的記錄類型的唯一識別碼格式相符。 例如，針對揀貨路線，條碼格式應與揀貨路線參考的格式 (通常是編號規則) 相符。  
1. 選擇 **儲存**。
1. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
