---
title: 退貨的裝箱單更新
description: 必須先更新退回品項所屬訂單的裝箱單，該品項才可以入庫。
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPackingSlipJournalHistory, SalesParmPackingSlipTrackingInformation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f586537aa2d4cb47b0e55e76e401ea6852e1d60
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449301"
---
# <a name="packing-slip-updates-for-returns"></a>退貨的裝箱單更新  

[!include [banner](../includes/banner.md)]


必須先更新退回品項所屬訂單的裝箱單，該品項才可以入庫。 正如發票更新流程是對財務交易記錄進行更新一樣，裝箱單更新流程是對庫存記錄的實體更新，這表示會認可對庫存所做的變更。 在退貨的情況下，在裝箱單更新期間會實作指派給處置動作的步驟。

裝箱單更新會在品項到貨日記帳或退貨單中處理。

作為過帳裝箱單流程的一部分，可以將客戶運送文件中的裝箱單參考號與訂單行相關聯。 此關聯是選擇性的，僅供參考。 它不會建立任何交易記錄更新。

如果並非所有預期的退貨品項都已到達，您應該在裝箱單更新中只包含已收到的數量。 將剩餘的品項留在訂單上，直到剩餘的退貨運送到達為止。

如果某個品項從檢疫區退回到運送和接收部門，例如當檢疫檢查員不知道該品項在庫存中的儲存位置時，則必須更新相應的裝箱單以正確登記，並根據因隔離而指定的處置代碼採取動作。

當您更新銷售合約中所退回品項的裝箱單時，該品項的銷售合約承諾會自動更新，以反映數量或金額的變化。 

## <a name="see-also"></a>另請參閱

[為退貨執行發票更新](perform-invoice-updates-for-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]