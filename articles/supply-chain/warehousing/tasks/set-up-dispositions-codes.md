---
title: 設定處置代碼
description: 此程序側重於設定可在行動裝置上用於退貨單接收流程的處置代碼。
author: Mirzaab
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSDispositionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb83108c934e864da0df39ec4ee36a0bc7ba7588
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448686"
---
# <a name="set-up-dispositions-codes"></a>設定處置代碼

[!include [banner](../../includes/banner.md)]

此程序側重於設定可在行動裝置上用於退貨單接收流程的處置代碼。 處置代碼是接收品項時可以使用的規則集合。 例如，當工作使用者使用行動裝置接收損壞的品項時，使用者必須掃描損壞品項的處置代碼。 可以根據掃描處置代碼確定接收貨物的庫存狀態、工作範本和位置指令。 對於訂購單接收流程和生產訂單報告為完工流程，可選擇是否要使用處置代碼。 對於銷售訂單退貨接收流程，如果使用行動裝置登記品項，則必須使用處置代碼。  本指南使用 USMF 公司示範資料建立。 此程序供倉庫經理所用。 

1. 移至倉庫管理 > 設定 > 行動裝置 > 處置代碼。
2. 點選 [新增]。
    * 建立新的處置代碼以供客戶退貨使用。  
3. 在 [處置代碼] 欄位中，輸入一個值。
4. 在 [庫存狀態] 欄位中，選擇存在庫存鎖定的庫存狀態。
    * 如果您正在使用 USMF，則選取 [鎖定]。 您可以將庫存狀態新增到處置代碼以覆寫訂單行上的預設狀態。  
5. 在 [工作範本] 欄位輸入值。
    * 選用：選擇與退貨單關聯的工作範本代碼。 如果未提供任何值，將使用系統中設定的標準規則解析工作範本。 選擇工作範本將限制可以使用此處置代碼的流程。 例如，如果處置代碼具有工單類型為訂購單的工作範本，則它不能用於登記客戶退回的品項。  
6. 在 [退貨處置代碼] 欄位中，輸入一個值。
    * 退貨處置代碼可以確定已登記品項的退貨單流程的剩餘部分。 在這個例子中，客戶應收到折讓單。 新增包含 [信用] 動作的退貨處置代碼。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]