---
title: 代表他人設定訂購產品的權限
description: 本主題說明如何授予工作人員代表其他工作人員準備採購申請的權限。
author: Henrikan
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a29b7ebece8009f29f4313b380889635a87473b5
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448974"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a>代表他人設定訂購產品的權限

[!include [banner](../../includes/banner.md)]

本主題說明如何授予工作人員代表其他工作人員準備採購申請的權限。 換言之，採購申請「準備者」可以為另一個「申請者」建立申請。 該程序還介紹如何授予工作人員在不同的法人實體或營運單位訂購品項和服務的權限。 通常，這些任務由採購經理執行。 您可以對 USMF 示範公司的資料或您自己的資料來執行此程序。


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a>授予代表其他工作人員輸入採購申請的權限
1. 在功能窗格中，前往 **模組 > 採購和委外 > 設定 > 原則 > 採購申請權限**。 確保將 **目前檢視表** 欄位設定為 **依準備者**。 左側窗格中的清單會顯示可以被授予代表其他人準備申請權限的人員。  
2. 選擇要授予權限的人員 (準備者)。
3. 選取 **新增**。
4. 尋找並選擇要新增為要求者的人員。
    - 要求者是準備者可以代表建立申請的人。  
    - 在 **授權** 欄位中，如果準備者應該能夠代表所選工作人員建立採購申請，請選取 **特定**。 如果準備者還應該能夠代表向該工作人員報告的所有工作人員建立採購申請，請選取 **申報**。  
5. 在 **有效** 欄位中，輸入一個日期。
6. 在 **到期** 欄位中輸入日期。

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a>查看有權為所選工作人員建立採購申請的準備者
1. 在 **目前檢視表** 欄位，選擇 **依要求者**。 此檢視表顯示已被授予代表選定工作人員建立採購申請權限的準備者清單。  
2. 使用 [快速篩選] 尋找您剛剛新增為要求者的工作人員。
3. 選取 [要求者]。 準備者清單顯示有權代表左窗格中所選要求者訂購品項的人員。  您可以在此處新增其他準備者。 此檢視表還可讓您授予要求者在不是該人員的主要法人實體或營運單位的法人實體和營運單位中建立申請的權限。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]